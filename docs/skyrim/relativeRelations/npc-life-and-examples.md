# NPC-Alltag, Eigenentwicklung und Beispiele

## Mehr Eigenleben durch das, was schon existiert

NPCs besitzen bereits Tagesabläufe, Wohnräume, berufliche Rollen, Quests, Beziehungen und zum Teil Zustandswechsel. RelativeRelations soll diese **sozial wahrnehmbar** machen. Ein NPC muss weder ständig für das Drachenblut bereitstehen noch sein gesamtes Leben durch neue Skripte simulieren.

## Ysolda als Kandidatin für den ersten Prototyp

Ysolda hat Handelsambitionen und Kontakte. Je nach Entwicklungsstand der Mod könnte sie:
- beiläufig Heiltränke für Abenteuer empfehlen;
- über bevorzugte Speisen und Getränke sprechen;
- auf Handelskontakte, Karawanen und besondere Waren verweisen;
- eine konkret beauftragte Ware innerhalb einiger Spieltage beschaffen;
- bei einem zufälligen Treffen im Gasthaus deren Eintreffen erwähnen;
- die Ware erst beim nächsten passenden Dienst-/Geschäftszeitpunkt übergeben;
- spätere Änderungen ihres Händlerstatus thematisieren.

Das Gespräch über eine Änderung im Geschäft soll **eine vorhandene Vanilla-Entwicklung lesen**, nicht die Entwicklung selbst replizieren. Der im Chat genannte mögliche Fall einer Übernahme von Belethors Laden bei dessen Tod ist als **zu verifizierender Vanilla-Anknüpfungspunkt** zu behandeln (auch tatsächliche Conditions, Ersatzhändler-Logik und Package-Veränderung prüfen).

Trennung der Zustände: `ordered`, `procured`, `informed`, `collected`. Geschäftsbedingte Beschaffung und persönliche Anteilnahme sind zwei unterschiedliche Motive.

## Aela

Aela besitzt bereits eine durch Gefährten, Jagd und Werwolfsein geprägte Identität. Neue Gespräche können daran anknüpfen: gemeinsame Abenteuer, Beurteilung riskanter Entscheidungen, mögliche Beschaffung von Jagdmaterial, eigene Vorstellungen von Loyalität. Eine enge Beziehung muss nicht bedeuten, dass sie allem zustimmt.

## Braith und What a Braith

Die Spezialmod **What a Braith** nutzt die Framework-Mechanik, statt ein eigenes allgemeines Wissens-/Dialogsystem zu duplizieren. Als Begleiterin erlebt Braith Quest-Meilensteine selbst. Beim Rasten kann sie sich erinnern, Fragen stellen, Ereignisse anders bewerten als das Drachenblut oder später auf früher Erlebtes zurückkommen. Ihre Individualität liefert die Spezialmod, die Infrastruktur RelativeRelations.

So kann auch eine weitere Begleiterfigur dasselbe Abenteuer anders wahrnehmen. Gemeinsames Erleben ist von bloß berichteten Quests zu trennen.

## Bürgerkrieg und regionale Veränderungen

Ein NPC erfährt ggf. mit Zeitversatz, dass Weißlauf den Besitzer gewechselt hat; ein lokaler Bewohner weiß früher davon als jemand außerhalb der Region. Kenntnis der Rolle des Drachenbluts ist eine zusätzliche Information. Dieselbe Nachricht kann bei verschiedenen Figuren Erleichterung, Angst, Ablehnung oder Zustimmung auslösen.

## Kampf-Geborene / Grau-Mähnen

Das Drachenblut entscheidet, ob es jemandem aus der rivalisierenden Familie von Thorald Grau-Mähnes Befreiung berichtet. Das Thema wird passend zum Gesprächspartner angeboten; er kann heftig, reserviert oder unerwartet positiv reagieren. Hier wirkt vorhandene Familien-/Fraktionsinformation als Kontext.

## Trauer und Tod

Anstoß war Skyrims häufig langanhaltende, repetitive Trauer nach dem Tod eines Angehörigen. Ein optionales System könnte zwischen frühem Schock, anhaltender Trauer und einem allmählichen Wiederfinden des Alltags unterscheiden, abhängig von Beziehung, Todesumständen und Persönlichkeit. Erinnerungen an die verstorbene Person dürfen weiterhin auftauchen. **Trauer nicht einfach als universell ablaufenden Countdown modellieren.**

Realisierbarkeit hängt davon ab, welche Vanilla-Trauerdialoge und -Packages konditioniert oder ergänzt werden können, ohne fremde Records destruktiv zu überschreiben.

## Hausrat, Bücher, Umgebung (spätere Iteration)

Wohnzellen, Ownership und platzierte Bücher/Gegenstände können zusätzliche Gesprächsanlässe liefern:
- Warum besitzt ein NPC ein bestimmtes Buch?
- Hat er es gelesen, geerbt, geschenkt bekommen oder hält er wenig davon?
- Welche Verbindung haben Gegenstände zu Arbeit, Interessen oder Lebensgeschichte?

Der Drachenblutbesuch kann zu einer optionalen Nachfrage oder zu einer beiläufigen Äußerung führen. **Ein Objekt im Haus ist kein Beweis für ein persönliches Interesse.** Besitz-/Ownership- und Zellzugehörigkeit müssen geprüft werden; Änderungen des Inventars/der Einrichtung sind eine mögliche spätere Erweiterung.

## Leitmotiv

Nicht jeder NPC muss viel erzählen. Entscheidend ist, dass ein einzelner Satz zu seinem Leben, seiner Erinnerung und der aktuellen Situation passt.
