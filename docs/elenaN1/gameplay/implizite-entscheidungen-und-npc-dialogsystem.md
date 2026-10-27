# Implizite Entscheidungen, NPC-Reaktionen und Dialogarchitektur

Status: Designkonzept; technische Verfahren noch offen. Stand: 27.10.2026.

## Leitidee

**Das Spiel fragt nicht ständig, was Elena tun möchte. Es stellt den Spieler in eine Situation und lässt ihn handeln.**

Die Fähigkeiten Elenas gelten grundsätzlich auch in Gesprächen. Eine Dialogszene ist kein separater Modus, der Bewegung, Blicksteuerung, Interaktion oder Angriffe abschaltet. Das Spiel markiert Handlungen und Unterlassungen nicht zwingend als „Entscheidung“. Die Welt reagiert auf das, was geschieht – und NPCs interpretieren es anhand ihres Wissens und ihrer Persönlichkeit. Das gilt auch für Schweigen, Weggehen, Nichtstun, Beobachten, Helfen und Angreifen.

Spieler sollen diese Freiheit selbst entdecken können; die Möglichkeit, ein Gespräch zu verlassen oder jemanden mitten im Satz anzugreifen, wird **nicht eigens erklärt oder als Dialogoption ausgeschildert**. Die Grundsteuerung muss natürlich erlernbar sein. Die Entdeckung liegt darin, dass die üblichen künstlichen Beschränkungen fehlen.

## Gesprächsinteraktion

- Dialogoptionen erscheinen möglicherweise erst, wenn der Spieler aktiv „bereit zu antworten“ signalisiert (Taste; genaue UX offen).
- Ohne diesen Impuls kann Elena schweigen, zuhören, sich umsehen, interagieren, gehen oder angreifen.
- Gesprächspartner warten nicht unbegrenzt. **Zeitgrenzen und Auslöser für Interpretation bleiben verborgen**; kein Countdown und keine künstliche Aufforderung „Jetzt antworten“.
- Geduld, Nachfragen, Abbruch und Eskalation hängen von Charakter, Situation, Beziehung und Vorgeschichte ab; keine starre globale Schweige-Frist.
- Schweigen ist zunächst nur ein beobachtbares Verhalten, keine automatisch festgelegte Gesinnung. Es kann als Unsicherheit, Trotz, Unwissen, Gleichgültigkeit, Überforderung oder bewusste Verweigerung gelesen werden.
- Die Interpretation des NPC muss nicht der tatsächlichen Spielerabsicht entsprechen.
- Körperliche Einschränkungen sind möglich, aber müssen aus der Spielwelt kommen (z. B. Festhalten), nicht aus einem künstlichen Dialogmodus.

## Architektur: Wahrnehmung → Interpretation → Absicht → Ausdruck

**1. Wahrnehmung:** Was konnte der NPC überhaupt sehen/hören? Handlung, Richtung, Distanz, Zeitpunkt, Aufmerksamkeit, Zeugen, Kontext. Keine Allwissenheit.

**2. Interpretation:** Welche Bedeutung schreibt der NPC dem Ereignis zu? Abhängig von Wissen, Erwartungen, Persönlichkeit, Zielen, Stimmung, Beziehung und gemeinsamen Erfahrungen. Mehrere Deutungen können plausibel sein; Unsicherheit zulassen.

**3. Reaktionsabsicht / Handlungswahl:** Was will der NPC erreichen? Etwa Gespräch fortsetzen, Autorität behaupten, deeskalieren, fliehen, helfen, festhalten, angreifen, Informationen gewinnen, ignorieren. Diese Ebene soll weitgehend generalisierbar sein.

**4. Ausdruck:** Körperhandlung, Mimik, Schweigen oder Sprache. Sprache ist nur *eine* Ausdrucksform. Die Aussage wird erst aus einer feststehenden kommunikativen Absicht und dem erlaubten Wissensstand formuliert – nicht umgekehrt.

**5. Gedächtnis / Rückkopplung:** NPC merkt sich relevante Vorfälle, eigene Reaktionen und die Reaktion Elenas darauf. Wiederholtes Ignorieren kann von Nachfragen über Ungeduld zu Abbruch oder konkreten Maßnahmen führen. Nicht einfach dieselbe Zeile erneut abspielen.

## NPC-Parametrisierung

Gemeinsames Verhaltenssystem, individuelle Profile. Mögliche Parameter:

- Wissen, Überzeugungen, Unsicherheiten, Interessen, Ziele und Prioritäten
- Beziehungen, Vertrauen, Respekt, Furcht, Feindseligkeit und gemeinsame Geschichte
- Geduld, Impulskontrolle, Konfliktbereitschaft, Direktheit, Selbstsicherheit
- Bildung, Beruf, Milieu, Wortschatz, Satzbau, Register und typische Redewendungen
- aktueller Zustand (Stress, Angst, Wut, Müdigkeit usw.)
- Wahrnehmungsfähigkeit, Aufmerksamkeit und situative Handlungsmöglichkeiten

Die Parameter sollen **unterschiedliche Interpretationen und Handlungen**, nicht nur unterschiedliche Textvarianten bewirken.

Beispiel: Elena verlässt mitten im Gespräch den Raum.
- Cornelius deutet dies womöglich als Verhandlungsverweigerung und versucht sachlich, das Gespräch fortzusetzen.
- Amanda empfindet es womöglich als Missachtung ihrer Autorität und reagiert scharf oder handelt.
- Tabetha könnte es als erneutes Verlassenwerden erleben.
- Ein Wachmann sieht möglicherweise eine Flucht aus einer Kontrolle und stellt sich in den Weg.

Dies sind *mögliche*, keine stets deterministischen Reaktionen. Der Verlauf kann je nach Vorgeschichte anders sein.

## Vermeidung identischer NPC-Aussagen

Zehn NPCs sollen nicht bloß zehn Formulierungen für dieselbe Standardreaktion besitzen. **Zuerst Vielfalt der Wahrnehmung, Deutung, Motivation und Handlung**, danach sprachliche Vielfalt.

- Nicht jede Handlung muss kommentiert werden. Schweigen, Nachsehen, Wegversperren, Weglaufen, Alarmieren oder Erstarren können natürlicher sein.
- Sprachliche Unterschiede folgen einem stabilen persönlichen Stil statt beliebiger Synonymrotation.
- Gewohnheitsformulierungen und gelegentliche Wiederholungen sind menschlich; *mechanisch identische* Antworten auf wiederholte Situationen sind zu vermeiden.
- Wiederholung muss den Kontext verändern können: Nachfragen → Frustration → Abbruch oder Maßnahme.
- Nicht jeder NPC muss sprachlich kreativ sein; situationsgerechte kurze Sätze („Stehen bleiben!“) sind legitim.
- Wichtige Charaktere erhalten stärkere individuelle Textgestaltung; Nebenfiguren können gemeinsame Ressourcen nutzen, ohne identisch zu wirken.

## Drei mögliche Stufen der sprachlichen Umsetzung

1. **Handgeschriebene charakter- und situationsspezifische Dialoge** für dramaturgisch zentrale Begegnungen. Sie werden dennoch durch die generische Reaktionsarchitektur ausgelöst.
2. **Kontextabhängige, kuratierte Äußerungsbausteine** für wiederkehrende kommunikative Absichten. Auswahl anhand von Persönlichkeit, Situation, Wissen, Gedächtnis und bisher verwendeten Formulierungen; keine bloße Zufallsrotation. Voraussichtlich der tragende Ansatz.
3. **Optional: regelbasierte oder generative Formulierung zur Laufzeit** für unvorhergesehene Fälle. Noch nicht entschieden, insbesondere nicht auf generative KI festgelegt.

**Qualitätsvorgabe:** Natürlichkeit, Verständlichkeit und Charaktertreue vor Variation. Kein unbeholfenes Satz-Puzzle, keine dämlichen oder konstruiert wirkenden Aussagen. Generierung darf **keine Fakten, Kenntnisse, Versprechen oder Plotinformationen erfinden**, die dem NPC nicht zur Verfügung stehen. Wenn keine überzeugende Äußerung verfügbar ist, lieber eine sichere, passende Handlung oder Schweigen als fragwürdiger Text.

Die Spielmechanik kennt bereits Wahrnehmung, Interpretation und Absicht; das Sprachmodul realisiert diese nur. Es darf keine neuen Entscheidungen oder Tatsachen nachträglich aus der Formulierung ableiten. So bleibt die Texttechnologie austauschbar.

## Verbindung zur emergenten Erzählung

- Entscheidungen sind nicht auf Menüs beschränkt; auch Nichtstun hat mögliche Folgen.
- Spielerabsicht, tatsächliche Handlung und Fremdinterpretation können auseinanderfallen.
- NPCs reagieren auf Geschichte und Beziehungen, nicht auf einen universellen Gut/Böse-Wert.
- Konsequenzen dürfen verzögert, unsichtbar oder uneindeutig bleiben.
- Moralische Konflikte erhalten keine vorgefertigte richtige Lösung.
- Eine Welt, die auch ohne explizite Dialogauswahl weiterläuft, unterstützt unterschiedliche Durchläufe und hohe Replayability.

## Umsetzung und Validierung (Vorschlag, keine Festlegung)

1. Kleinen Prototyp mit ca. fünf charakterlich unterschiedlichen NPCs und **handgeschriebenen** Äußerungen bauen.
2. Dieselben Situationen durchspielen: schweigen, weggehen, wiederholt ignorieren, überraschend angreifen, auf Gegenstände achten.
3. Prüfen, ob Figuren **verschieden handeln**, plausibel interpretieren und sich an Vorfälle erinnern.
4. Prüfen, ob Spieler die Grundsteuerung intuitiv übertragen können, ohne versteckte Handlungsoptionen eigens erklärt zu bekommen.
5. Erst danach sprachliche Variation und ggf. Generierung experimentell erweitern.
6. Testkriterien: keine unberechtigte NPC-Allwissenheit, keine semantischen Widersprüche, keine unnatürlichen Textkonstruktionen, keine repetitiven Standardreaktionen, nachvollziehbare Eskalation.

## Offene technische Fragen

- Wie wird „bereit zu antworten“ konkret bedient, ohne andere Aktionen zu blockieren?
- Welche Ereignisse werden wie lange im individuellen NPC-Gedächtnis gehalten?
- Welche Reaktionsparameter sind kontinuierlich, welche regel- oder zustandsbasiert?
- Wie werden Dialogressourcen lokalisiert und sprachliche Persönlichkeit über Sprachen hinweg erhalten?
- Welche Qualitätskontrolle und Fallbacks wären für Laufzeitgenerierung notwendig?
- Wie lassen sich Sonderfälle wichtiger Figuren gestalten, ohne die allgemeinen Regeln zu unterlaufen?

**Kernprinzip:** *Spielmechaniken beschreiben Elenas Fähigkeiten, nicht die vom Entwickler vorgesehenen Lösungen.*
