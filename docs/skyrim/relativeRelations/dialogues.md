# Dialoge und Gesprächsanlässe

## Ziel

Kein endloses Dialogmenü. Erst bei Aufnahme eines Gesprächs wird aus dem tatsächlichen Kontext eine begrenzte, interessante Auswahl vorbereitet. Sie berücksichtigt den aktuellen Queststand, das NPC-Wissen, die Gesprächshistorie, Beziehung, Ort, Zeit, Tagesablauf und mögliche offene Anliegen.

## Auswahl

Geplante Größenordnung: **etwa drei bis sechs zusätzliche Gesprächsoptionen**, randomisiert und limitiert – nicht zwingend ein Mindestwert. Wenn nur ein sinnvolles Thema vorliegt, ist eine Option besser als Füllmaterial.

Priorisierung (Beispiel, noch keine festgelegten Gewichte):
1. Direkt zuvor angesprochene Anliegen, etwa „Meine Bestellung ist da“ – **garantiert zugänglich**.
2. Bedeutende neue Informationen und gemeinsam erlebte Ereignisse.
3. Offene Fäden früherer Gespräche.
4. Regionale/Weltereignisse.
5. Persönlichkeit, Interessen und Alltag.
6. Allgemeiner Smalltalk.

Vor der Zufallsauswahl müssen Conditions und Verfügbarkeit geprüft werden. Innerhalb eines geöffneten Gesprächs bleibt die Auswahl stabil. Das ständige Schließen/Öffnen sollte nicht zum mechanischen Durchrotieren aller Themen führen; wie lange eine Auswahl „klebt“, ist offen.

**Wichtig:** Die Begrenzung betrifft RelativeRelations-Zusatzthemen, nicht notwendigerweise sämtliche Vanilla-Dialogoptionen. Bestehende Dialoginhalte dürfen nicht entfernt oder unterdrückt werden.

## Initiative ohne Unterbrechung

NPCs dürfen bei Nähe einen kurzen, situationsbezogenen Satz äußern (z. B. ein Hello/Bark), **ohne** automatisch den Dialogmodus aufzurufen:

> „He, ich habe übrigens die Zutaten auftreiben können, nach denen du gefragt hast!“

Der Spieler kann stehen bleiben und reden oder weitergehen. Der Anlass bleibt im Gedächtnis. Kein Questmarker nötig, keine erzwungene Unterbrechung. Häufigkeit und Cooldowns verhindern nerviges Hinterherrufen.

## Ysolda: Gespräch in und außerhalb der Arbeit

- Während des Tages: Bestellungen annehmen, beschaffte Ware übergeben, Handelsgespräche.
- Abends im Gasthaus: „Deine Bestellung ist angekommen. Komm morgen im Laden vorbei.“
- Die Ware ist beschafft; die Übergabe ist aber an passende Arbeitszeiten, Ort und ggf. Inventarlogik gebunden.
- Bestellung, Beschaffung, Informieren und Übergabe sind **unabhängige Zustände**.
- Die konkrete Einkaufsmechanik ist ein optionaler Ausbau, nicht Teil der notwendigen Gesprächsgrundlage.

## Wiedersehen

NPCs beziehen sich auf früher Gesagtes:
- „Hast du den Händler gefunden?“
- „Du wolltest mir noch erzählen, was aus der Sache geworden ist.“
- Nach mehreren vergeblichen Nachfragen: Thema vorerst ruhen lassen.

Ob erneutes Nachfragen zeitgesteuert, begegnungsgesteuert oder beides ist, entscheidet **die jeweilige Anlassdefinition**, nicht ein universeller Automat.

## Braith: gemeinsame Erlebnisse reflektieren

Braith begleitet das Drachenblut und wird Zeugin der Questfortschritte. Während einer Ruhephase – etwa am Lagerfeuer – kann sie das Erlebte von sich aus aufgreifen:

> „Weißt du noch, wie dieser Draugr aus dem Sarg gesprungen ist?“

Oder ernster:

> „Glaubst du, wir hätten das anders machen können?“

Die Reaktion richtet sich nach Persönlichkeit, Erleben, Beziehung und Situation. Nicht jedes Ereignis wird sofort bei der nächsten Rast „abgearbeitet“; manche bleiben als langfristige Erinnerung relevant.

## Praktische Grenzen

Skyrims reguläres Dialogsystem nutzt vordefinierte Topics, Infos und Conditions. Ein frei erzeugbares Dialogmenü aus beliebigen Strings ist **nicht** als vorhandene Vanilla-Funktion vorauszusetzen. Zu prüfen sind ein kuratierter Pool vordefinierter Topics, versteckte/aktivierte Alternativen und geeignete Skript-/Plugin-Unterstützung. Vanilla-Topics müssen kompatibel bleiben.

Dialogtexte benötigen je nach Vertonung ein Voice-/Subtitle-Konzept. Gerade für ein generisches Framework kann der Content- und Vertonungsaufwand höher sein als der eigentliche Zustandsvergleich.
