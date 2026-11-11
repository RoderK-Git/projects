# RelativeRelations

> **Beziehungen werden nicht freigeschaltet. Sie entstehen.**

**Konzeptstand:** 11. November 2026 · **Status:** Ideensammlung und Architekturkonzept, keine Implementierung.

RelativeRelations ist eine geplante, generische Skyrim-Mod zur immersiveren sozialen Interaktion mit NPCs. Sie soll bereits vorhandene Weltzustände, Quests, Tagesabläufe, Beziehungen, Familien, Berufe und kulturelle Hintergründe nutzen, um NPCs persönlicher, aufmerksamer und langfristig interessanter zu machen.

**Grundidee:** Nicht möglichst viele neue Inhalte schaffen, sondern den vorhandenen Inhalten mehr soziale Konsequenzen geben. Keine generative KI als Voraussetzung, keine vollständige Lebenssimulation und keine erzwungenen Dialoge.

## Leitgedanken

1. **Vorhandenes zuerst.** Vanilla-Daten und bereits implementierte Veränderungen auswerten, statt sie zu duplizieren.
2. **Wissen ist individuell.** Weltzustand, Wissensstand des Drachenbluts, Wissen eines NPCs und gemeinsame Erfahrung unterscheiden.
3. **Der Spieler entscheidet, was er erzählt.** Kein automatisch aufgezwungenes Ausplaudern; für den Spieler selbst zunächst kein separates Wissensregister.
4. **Aufmerksamkeit ohne Zwang.** NPCs dürfen beiläufig etwas sagen; ein Gespräch beginnt erst, wenn der Spieler darauf eingeht.
5. **Weniger, aber passende Optionen.** Gesprächsangebote werden beim Start kontextabhängig ausgewählt und begrenzt.
6. **Beziehungen sind kein Belohnungsautomat.** Sympathie, Vertrauen, Nähe und Romantik sind verschieden; Zuneigung lässt sich nicht durch Penetranz erzwingen.
7. **Kultur prägt, Persönlichkeit entscheidet.** Loretreue ohne starre Rassenstereotype.
8. **Entkoppelt und modübergreifend.** Bestehende Quests und ihre Stages bleiben unangetastet. Spezialmods können das Framework erweitern.
9. **Reaktionen statt Dauersimulation.** Zustände vorzugsweise erst bei Begegnung, Gespräch oder Regionswechsel prüfen.
10. **Organische Konsequenzen.** Charakterentwicklung darf stattfinden, muss aber weder immer eintreten noch ausschließlich dem Drachenblut dienen.

## Dokumentation

- [Vision und Gestaltungsprinzipien](vision.md)
- [Wissen, Quests und Ereignisse](knowledge-and-events.md)
- [Dialoge und Gesprächsanlässe](dialogues.md)
- [Persönlichkeit, Kultur und Beziehungen](relationships-and-culture.md)
- [NPC-Alltag, Eigenentwicklung und Beispiele](npc-life-and-examples.md)
- [Technische Architektur und Integration](architecture.md)
- [Umsetzungsphasen, offene Fragen und Prüfaufträge](roadmap-and-open-questions.md)

## Beispiel: Ysolda

Ysolda ist ein guter möglicher Prototyp: Als angehende Händlerin kennt sie Waren, Karawanen und Kunden. Einem Abenteurer kann sie Heiltränke empfehlen oder später bestimmte Waren beschaffen. Begegnet sie ihm nach Feierabend im Gasthaus, kann sie beiläufig mitteilen, dass die Bestellung eingetroffen ist. Die Übergabe findet erst statt, wenn sie wieder im Geschäft ist. Sie bleibt damit auch außerhalb ihrer Arbeitszeit eine Person und wird nicht zum rund um die Uhr verfügbaren Händler-Menü.

Auch ein durch Vanilla-Logik ausgelöster Wechsel ihrer geschäftlichen Situation soll nur *wahrgenommen und besprochen* werden; RelativeRelations muss ihn nicht selbst nachbauen. Ob und unter welchen exakten Bedingungen Ysolda Belethors Geschäft übernimmt, ist vor der Umsetzung an den Vanilla-Daten zu verifizieren.

## Verhältnis zu anderen Projekten

[What a Braith](../whatABraith/README.md) soll **keine Kopie** der generischen Mechaniken enthalten. Braith kann sie als Companion verwenden und mit charakter- und questbezogenen Reaktionen erweitern: Sie erlebt Quests selbst und spricht später, etwa während einer Ruhephase, darüber. Andere NPC-Erweiterungen nutzen dieselben Basissysteme.

## Abgrenzung

Dieses Projekt ist ein **Entwurf**, keine bereits getestete technische Spezifikation. Beispieltexte sind Dialogillustrationen, keine nachgewiesenen Vanilla-Zitate. Bei Lore, Questbedingungen, Faction-Records und SKSE/Papyrus-APIs ist eine separate Überprüfung vorgesehen.
