# Wissen, Quests und Ereignisse

## Informationsmodell

Vier Perspektiven sind zu trennen:

1. **Weltwahrheit:** tatsächliche Quest-Stages, Todesfälle, Besitzerwechsel, Bürgerkriegsverlauf und sonstige Spielzustände.
2. **Verfügbares Spielerwissen:** zunächst pragmatisch aus dem tatsächlichen Spielstand abgeleitet. Kein eigener Wissensspeicher des Drachenbluts nötig; der Spieler entscheidet über Offenbarung und Lügen.
3. **NPC-Wissen:** Was wurde einer Figur erzählt, was hat sie beobachtet, gehört oder anderweitig erfahren?
4. **NPC-Erfahrung und Deutung:** Teilnahme an einem Ereignis, subjektive Bewertung und ggf. falsche Schlussfolgerung.

**Kenntnis eines Ereignisses ist nicht Kenntnis der Urheberschaft.** Ein NPC kann von der Ermordung des Kaisers oder dem Wechsel der Herrschaft in Weißlauf erfahren haben, ohne zu wissen, ob das Drachenblut beteiligt war.

## Quest- und Stage-Fortschritt

Quest-Stages dienen als objektive Quelle für relevante Meilensteine. Eine NPC-Figur kann den letzten bekannten Stand aus dem Gespräch mit dem Drachenblut erhalten. Der Questfortschritt des Drachenbluts verändert sich später, der NPC bleibt beim alten Wissensstand.

Beispiel:
- Das Drachenblut erwähnt eine vermisste Person bei Quest-Meilenstein 20.
- Die Quest ist inzwischen bei 60.
- Beim nächsten Treffen fragt der NPC nach dem Schicksal der Person.
- Erst nach einer tatsächlichen Mitteilung erfährt er den neuen Stand.

Eine wichtige Ausnahme: Ein begleitender NPC wie Braith kann den Fortschritt aus eigener Anschauung erfahren. Für sie haben Erinnerung und Interpretation dann eine andere Qualität als bei bloßem Hörensagen.

### Meilensteine statt beliebiger Stage-Zahlen

Viele Skyrim-Quests verwenden Stages mit Abständen von zehn. Diese Zwischenräume inspirierten die Idee, z. B. drei zunehmend konkrete Nachfragen zu führen und anschließend zu schweigen. **Nicht die Original-Stages ändern!** Im Framework besser getrennt halten:
- `knownMilestone`
- `followUpCount`
- `lastAskedAt`
- `conversationState`

Die tatsächlichen Stage-Nummern und ihre Reihenfolge sind questabhängig; es gibt keine garantierte 10er-Systematik und keinen sicheren Schluss aus `GetStage()` allein auf die erzählte Bedeutung. Inhaltliche Meilensteine müssen zugeordnet werden.

## Gesprächsfäden

Ein einmal begonnenes Thema bleibt beim NPC bestehen. Es darf mehrfach, aber nicht endlos nachgefragt werden.

Beispiel für ein Thema:
1. „Und, wie ist die Sache ausgegangen?“
2. Einige Begegnungen oder Tage später: „Du hast mir noch nichts darüber erzählt.“
3. Später, NPC-typisch: „Jetzt machst du aber ein Geheimnis daraus!“
4. Der NPC lässt es gut sein.

Die Regeln können zeit-, begegnungs- und kontextabhängig sein oder kombiniert werden. Keine global vorgeschriebene Frist! Ein neues Ereignis kann ein ruhendes Thema erneut relevant machen. Nicht jede Figur fragt überhaupt nach.

## Welt- und Regionalereignisse

- **Überregional:** Ausgang des Bürgerkriegs, Ermordung des Kaisers, große politische Umbrüche.
- **Regional:** Schlacht um Weißlauf, lokale Machtwechsel, Konflikte.
- **Lokal/sozial:** Tod eines Händlers, Veränderungen in der Nachbarschaft, Familienangelegenheiten.
- **Persönlich:** gemeinsam erlebter Kampf, ausgesprochene Bestellung, privates Gespräch.

Kenntnis kann durch Nähe, verstrichene Spielzeit, Zugehörigkeit, Beruf, soziale Kontakte und Zufall beeinflusst sein. Bewohner des Schauplatzes erfahren ein Großereignis tendenziell früher als weit entfernte Figuren. Das Ergebnis einer Wissensprüfung muss **persistent** sein, statt bei jedem Gespräch wieder neu ausgewürfelt zu werden.

### Wahrheit und Gerücht

Wissen muss nicht wahr sein:
- Aussage des Drachenbluts kann ehrlich, beschönigt, irreführend oder gelogen sein.
- Ein Gerücht kann der tatsächlichen Questlage widersprechen.
- Mehrere Quellen können sich widersprechen.
- Eine spätere Beobachtung kann Zweifel auslösen.

Dies ist eine **optionale spätere Vertiefung**, keine Voraussetzung für den Prototyp. Zunächst reicht der getrennte Kenntnisstand; Quellen und Verlässlichkeit können ergänzt werden.

## Heikles Erzählen: Kampf-Geborene und Grau-Mähnen

Thorald Grau-Mähne wurde aus der Gefangenschaft befreit. Das Drachenblut könnte dies einem Mitglied der rivalisierenden Kampf-Geborenen erzählen – aus Naivität, Ehrlichkeit oder als Provokation. Der Spieler wählt selbst. Das System prüft Questfortschritt, Empfänger, ggf. Kenntnis der Familienbeziehungen und frühere Aussagen; der Gesprächspartner reagiert abhängig von seiner individuellen Haltung. Nicht alle Familienmitglieder müssen gleich reagieren.

**Kein automatisch herausplatzender Dragonborn-Dialog.** Spielerwissen, Familienkonflikt und Motive müssen nicht intern vollständig modelliert werden.

## Erfassungszeitpunkte

Bedarfsgesteuert statt globaler Dauerschleife:
- Gesprächsbeginn: relevante Quest- und NPC-Zustände prüfen.
- Regionaler Zell-/Location-Wechsel: mögliche regionale Ereignisse berücksichtigen.
- Optional: registrierte Quest-Events für Fälle mit echtem unmittelbarem Bedarf.
- Bei gemeinsamer Unternehmung: Companion-Ereignisse bzw. Meilensteine erfassen, soweit technisch zuverlässig.

Bei einem Regionswechsel nicht zwingend alle NPCs aktualisieren; ein regionsweiter Zustand plus spätere individuelle Auswertung ist sparsamer.
