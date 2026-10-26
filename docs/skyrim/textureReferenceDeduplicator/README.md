# Texture Reference Deduplicator

## Idee und Motivation

Skyrim-Mods, insbesondere NPC-Replacer, liefern häufig Kopien bereits vorhandener Texturen (z. B. für Haut, Haare, Augen oder Rüstungen) unter eigenen Dateipfaden aus. Obwohl die DDS-Dateien inhaltlich identisch sein können, führen unterschiedliche Pfade möglicherweise zu getrennten Texturressourcen im Grafikspeicher.

Ziel ist es, identische Texturen über **gemeinsame Referenzpfade** wiederzuverwenden, ohne Texturen zu verändern oder zusätzliche Kopien in einem Ressourcenpool anzulegen. Erwartet wird primär ein geringerer VRAM-Bedarf und eventuell weniger Nachladeruckler; ein messbarer FPS-Gewinn ist nicht garantiert. Die tatsächliche Ressourcenwiederverwendung und das Einsparpotenzial müssen empirisch überprüft werden.

## Grundprinzip: Generator nach Nemesis-Vorbild

Das Werkzeug arbeitet **offline und profilabhängig**. Es wird bei Bedarf nach Änderungen an der Modliste erneut ausgeführt, nicht bei jedem Spielstart. Grundlage ist die im jeweiligen Mod Organizer 2 (MO2)-Profil zur Laufzeit wirksame Ressourcen- und Plugin-Konfiguration.

1. Aktives MO2-Profil, Modaktivierung und -prioritäten sowie Plugin-Loadorder erfassen.
2. Effektiv verfügbare Ressourcen ermitteln: lose DDS-/NIF-Dateien, Plugins sowie Inhalte aktiver BSA-Archive.
3. DDS-Dateien anhand ihrer Inhalte (zunächst bytegenau per Hash, z. B. SHA-256) gruppieren.
4. Verweise auf Texturen in **NIFs** (z. B. `BSShaderTextureSet`) und in Plugin-**TXST**-Records ermitteln.
5. Für jede Gruppe identischer Texturen einen zur Laufzeit verfügbaren Zielpfad bestimmen.
6. Nötige Referenzänderungen als Patch-Mod(s) generieren und Analysebericht erstellen.

Dabei sind zwei Sichten wichtig: physische Mod-Dateien samt Herkunft und die **effektive virtuelle Dateisicht** unter MO2-Prioritäts- und Überschreibungsregeln. Bei BSA-Archiven ist zusätzlich zu prüfen, ob Skyrim das jeweilige Archiv tatsächlich lädt; allein das Vorhandensein genügt nicht.

## Original-Provider und Auswahl des Zielpfads

Eine kuratierte, konfigurierbare Liste bevorzugter **Ressourcen-Provider** (z. B. KS Hairdos oder The Eyes of Beauty) hilft, möglichst auf eigenständige Original-Ressourcenmods zu verweisen. Ihre tatsächliche Urheberschaft einzelner DDS-Dateien ist technisch nicht sicher feststellbar; daher sind dies **Präferenzen**, keine Wahrheitsbehauptungen.

Modnamen können abweichen. Soweit verfügbar, sollen MO2-Metadaten wie Nexus-Mod-ID, Spielzuordnung und Modname zur Wiedererkennung dienen. Zu prüfen ist konkret, welche Metadaten die eingesetzte MO2-API bereitstellt.

Auswahlregel:

1. Bevorzugter Provider ist im aktuellen Profil aktiv **und** die betreffende identische Textur ist unter dem gewählten Pfad effektiv verfügbar: diesen Pfad bevorzugen.
2. Andernfalls einen anderen nachweislich verfügbaren Pfad mit identischem Inhalt wählen; dabei Abhängigkeiten berücksichtigen.
3. Fehlt ein sicherer Kandidat, die ursprüngliche Referenz unverändert lassen.

Keine DDS-Dateien kopieren oder löschen. Eine mögliche Redundanz auf der Festplatte bleibt damit bestehen, doch die resultierende Patch-Mod enthält ausschließlich geänderte NIFs und gegebenenfalls Plugin-Records.

## Ausgabevarianten

- **Gesamt-Patch-Mod:** Eine Mod enthält sämtliche generierten Änderungen für das aktuelle MO2-Profil.
- **Individuelle Patch-Mods:** Änderungen getrennt nach der **zu patchenden Ursprungsmod** (nicht nach dem Provider), damit sich einzelne Patches in MO2 selektiv aktivieren oder deaktivieren lassen.

Individuelle Patches dürfen nicht stillschweigend auf Ressourcen einer inzwischen deaktivierten Mod zeigen. Der Generator soll externe Provider-Abhängigkeiten je Patch dokumentieren, vor der Generierung validieren und bei geänderter Modliste erneut laufen. Eine wirklich unabhängige Selektierbarkeit ist nur möglich, wenn die benötigten Ressourcen weiterhin verfügbar sind.

## Technische Umsetzung und Sicherheit

- **MO2-Anbindung:** Profilstatus, Modprioritäten und ggf. Mod-Metadaten über MO2-Schnittstellen ermitteln; prüfen, welche Informationen über das virtuelle Dateisystem direkt zugänglich sind. Der Generator kann als eigenständiges, über MO2 gestartetes Programm mit optionaler MO2-Integration ausgeführt werden.
- **Archive:** BSA-Inhalte erfassen und tatsächliche Laderegeln prüfen; BSA-Dateien nicht verändern.
- **NIFs:** Relevante Texturpfade umschreiben, ohne andere Material-/Shader-Einstellungen zu verändern.
- **Plugins:** TXST-Verweise gezielt über Overrides patchen; Konflikte und bestehende Winning Overrides beachten, damit keine fremden Änderungen überschrieben werden. Weitere indirekte Referenzmechanismen sind zu untersuchen.
- **Reproduzierbarkeit:** Originalmods niemals verändern. Patches atomar erzeugen und pro Durchlauf einen Bericht mit Profil, Änderungen, Zielpfaden und Abhängigkeiten ausgeben.
- **Konservative Erkennung:** Zunächst ausschließlich byteidentische DDS-Dateien zusammenführen. Dekodierte Pixelgleichheit oder visuelle Ähnlichkeit sind mögliche spätere Erweiterungen, jedoch mit erhöhtem Validierungsbedarf.

## Offene Fragen / Validierung

1. Welche MO2-APIs stellen Profil, Modidentität/-metadaten, effektiv gewinnende Dateien und Archivinformationen tatsächlich bereit?
2. Wie werden BSA-Ressourcen und ihre Priorität bei der konkreten Skyrim-Version zuverlässig aufgelöst?
3. Welche Texturpfade entstehen über NIFs, TXST und weitere Pluginsysteme; welche Formate müssen unterstützt werden?
4. Verwendet Skyrim identische Pfade unter realen Bedingungen tatsächlich als gemeinsame GPU-Ressource? Dazu Benchmarks mit VRAM-Verbrauch, Frametimes und Ladeverhalten vor/nach Patch.
5. Wie werden Konflikte bei Einzel-Patches, Überschreibungsprioritäten und nachträglich deaktivierten Ressourcenmods sicher erkannt?
6. Wie lassen sich nur tatsächlich zur Laufzeit erreichbare Referenzen erfassen, ohne benötigte Varianten zu übersehen?

## Vorschlag für ein MVP

1. Aktives MO2-Profil einlesen; zunächst lose DDS- und NIF-Dateien unterstützen.
2. Duplikatgruppen aus byteidentischen DDS-Dateien und ihren Pfaden samt Ursprungsmod ermitteln.
3. NIF-Referenzen erfassen und einen **Dry-Run** mit vorgeschlagenen Ersetzungen und Abhängigkeiten erstellen.
4. Selektiv NIF-Patches für das Profil generieren; beide Ausgabevarianten unterstützen.
5. Anschließend TXST-/Plugin-Patches und BSA-Unterstützung ergänzen und den tatsächlichen Performanceeffekt messen.
