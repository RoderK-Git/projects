# Emergent Storytelling – Designprinzipien und NPC Decision Inspector

Stand: 2026-11-08 · Konzept / noch keine Implementierung

## Zentraler Leitsatz

> **Unvorhersehbarkeit im Ergebnis, Nachvollziehbarkeit in der Ursache.**

Elena Prime soll eine systemische, dynamische Geschichte ermöglichen, deren konkreten Ablauf selbst die Entwickler nicht vollständig vorhersehen können. Die Welt folgt konsistenten Regeln, aber das Zusammenspiel von Charakteren, Wissen, Zielen und Ereignissen erzeugt neue Entwicklungen. Nicht bloß zufällige Questvarianten oder verzweigte, vorab geschriebene Dialoge.

## Ziele und Prinzipien

- **Emergenz statt Skriptpflicht:** NPCs handeln aus individuellen Motivationen, Beziehungen, Wahrnehmungen, Informationen, Fähigkeiten und Weltzuständen heraus.
- **Kausale Nachvollziehbarkeit:** Jede relevante Entscheidung muss auf überprüfbare Ursachen zurückgeführt werden können. Unerwartet ist erwünscht, unbegründet nicht.
- **Begrenztes Wissen:** Figuren dürfen nicht allwissend sein. Wahrnehmung, Informationsquellen, Erinnerungen, Evidenzketten, Glaubwürdigkeit und Fehlinformationen beeinflussen ihre Einschätzungen.
- **Autonomie abseits der Spielfigur:** Ereignisse und Konflikte können ohne Elena stattfinden; sie erlebt gegebenenfalls nur deren spätere Auswirkungen.
- **Dramaturgie ohne willkürliche Eingriffe:** Das System soll interessante Handlungsmöglichkeiten begünstigen, ohne die innere Logik der Welt oder die Autonomie der Figuren zu brechen.
- **Modulare Erweiterbarkeit als langfristige Option:** Unabhängig entwickelte Community-Module könnten neue NPCs, Orte und Ereignisse beitragen. Figuren aus verschiedenen Modulen sollen idealerweise miteinander interagieren können, ohne dass ihre Autoren einander kennen oder gemeinsame Dialoge skripten. Voraussetzung sind gemeinsame semantische Verträge für Ereignisse, Eigenschaften, Wissen und Handlungsoptionen.
- **Community und Kanon:** Freie Module könnten von Spielern bewertet werden; eine Übernahme als offizieller Inhalt würde zusätzliche Qualitäts-, Konsistenz- und Rechteprüfungen erfordern. Noch keine Festlegung, ob Mods auch die Kernmechanik erweitern dürfen.

## NPC Decision Inspector – Debugmodus

### Zweck

Entwickler sollen im laufenden Spiel nachvollziehen können, **warum** ein NPC etwas getan oder unterlassen hat. Der Inspector ist ein Diagnosewerkzeug, keine nachträgliche, frei erfundene Erklärung.

### Geplante Funktionen

1. **NPC auswählen:** Aktuelle Ziele, Bedürfnisse, Persönlichkeit/Reaktionstendenzen, Beziehungen, relevante Erinnerungen und wahrgenommener Weltzustand.
2. **Entscheidungs-Timeline:** Zeitlich geordnete Aktionen und Entscheidungen, einschließlich Hintergrundsimulation außerhalb der Sichtweite Elenas.
3. **Entscheidungsdetails:** Auslöser, verfügbare Handlungsalternativen, Voraussetzungen, Prioritäten/Nutzwerte (sofern das jeweilige Modell solche verwendet), Ausschlussgründe und ausgewählte Aktion.
4. **Wissens- und Evidenzgraph:** Was glaubt die Figur, warum glaubt sie es, von wem stammt die Information, wie zuverlässig erscheint die Quelle und welche widersprechenden Hinweise liegen vor?
5. **Kausalkette:** Rückverfolgung einer Entscheidung zu vorherigen Ereignissen, Beziehungen, Wahrnehmungen und Bewertungen; Verknüpfung mit IDs statt nur narrativer Zusammenfassung.
6. **Konflikte und Modulherkunft:** Kennzeichnung, aus welchem Basisspiel- oder Community-Modul Figuren, Regeln, Ereignisse und Daten stammen.
7. **Replay und Vergleich (Ausbauziel):** Deterministische Reproduktion, soweit technisch möglich, über Seed, Ereignisprotokoll, Modell-/Regelversion und Snapshot; Vergleich alternativer Entscheidungen bei geänderten Bedingungen.

### Beispiel

Tabetha misstraut Elena, obwohl eine enge Freundschaft als Ausgangslage vorgesehen war.

Der Inspector könnte zeigen:
- Tabetha erhielt einen widersprüchlichen Bericht über Elena.
- Eine von Tabetha als zuverlässig eingeschätzte Quelle bestätigte einen Teil davon.
- Elena widersprach der Darstellung, konnte aber keine überzeugende Evidenz vorlegen.
- Tabethas Misstrauen überschritt eine modellierte Handlungsschwelle.
- Sie entschied sich, eine Information vor Elena zurückzuhalten.

Das Ergebnis überrascht den Entwickler; die Ursachen bleiben prüfbar.

## Technische Leitplanken

- **Strukturierte Decision Traces:** Maschinenlesbare Einträge für Entscheidung, Alternativen, Faktoren, Eingabewerte, Ergebnis, beteiligte Entitäten, Regelversion und kausale Referenzen.
- **Event-Sourcing-nahe Historie:** Eindeutige Ereignis-IDs, Zeitstempel/Simulations-Ticks, Provenienz und Verknüpfungen. Nicht zwingend vollständiges Event Sourcing für die gesamte Engine.
- **Beobachtbarkeit statt Erklärungsfiktion:** Bei probabilistischen, heuristischen oder KI-basierten Entscheidungen nur Faktoren ausweisen, die tatsächlich erfasst wurden; Unsicherheiten ausdrücklich anzeigen.
- **Performance und Datenschutz:** Konfigurierbare Trace-Tiefe, Ringpuffer/selektive Aufzeichnung und klare Trennung von Spieleransicht und Entwicklermodus. Keine unbegrenzte Vollprotokollierung.
- **Debug- und Release-Trennung:** Debugdaten dürfen keine geheimen Informationen in die reguläre Spieloberfläche leaken.
- **Testbarkeit:** Invarianten wie „NPC verwendet nur verfügbares Wissen“, konsistente Evidenzreferenzen und nachvollziehbare Entscheidungsursachen automatisiert prüfen.

## Offene Fragen

- Welche Entscheidungsmodelle verwenden wir konkret (Regeln, Utility AI, Planung, generative Komponenten)?
- Welche Ereignisse laufen vollständig im Hintergrund, welche nur abstrahiert?
- Wie sichern wir semantische Kompatibilität zwischen unabhängig erstellten Modulen?
- Wie weit dürfen Community-Module Regeln und Mechaniken verändern?
- Welche dramaturgischen Leitplanken sind legitim, ohne die Simulation zu verfälschen?

## Umsetzungsvorschlag

Zunächst ein kleiner vertikaler Prototyp: zwei NPCs, ein gemeinsames Ereignis, voneinander abweichende Informationsstände, mehrere plausible Handlungsalternativen und ein vollständiger Decision Trace. Erst danach Hintergrundsimulation, modulübergreifende Interaktionen und komfortable grafische Inspektionsoberfläche ausbauen.
