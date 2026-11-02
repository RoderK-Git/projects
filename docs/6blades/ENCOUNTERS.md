# Bosskämpfe, Arenen und Fortschritt

## Bosskämpfe als dynamische Umrüstungsaufgabe

Bosszustände können verschiedene Kombinationen erfordern. Ein Bosskampf könnte insgesamt **zehn verschiedene Elementarwaffen** erfordern, während Ryu nur **sechs gleichzeitig** trägt.

Folge: Die ursprüngliche Sechs-Slot-Konfiguration reicht nicht durchgängig. Spieler müssen **im laufenden Kampf** Klingen freigeben, aufnehmen und ihre Tastenbelegung bewusst neu interpretieren.

Die zehn Waffen sind **ein erklärendes Beispiel**, keine feste Minimalzahl für alle Bosse.

## Woher kommen erforderliche Waffen?

Die Arena, der Boss und die Umgebung können die Klingen bereitstellen, wenn der Spieler sie nicht selbst mitgebracht hat:

- bereits in Boden/Wänden steckende Schwerter;
- von Ryu zuvor geworfene Klingen;
- gegnerische Waffen, die erbeutet werden können (Designoption);
- **improvisierte Waffen**, insbesondere ein Eiszapfen;
- durch Bossangriffe entstehende oder freigelegte Ressourcen (Designoption).

Die Bereitstellung soll **kreativ** und möglichst in die Arena eingebettet sein.

## Konkretes Beispielszenario (illustrativ)

1. Feuerboss verlangt in einer Phase Wasser+Eis.
2. Ryu hat ein Wasserschwert, aber keinen Eis-Slot.
3. Ein Eiszapfen hängt in der Arena. Bossangriff oder Ryus Handlung lässt ihn abbrechen.
4. Ryu wirft ein anderes Schwert und schafft Platz.
5. Während er ausweicht, sammelt er den Eiszapfen ein.
6. Er blockt/kontert oder attackiert mit neuem Elementsetup.
7. Der Eiszapfen ist temporär. Ryu benötigt später eventuell seine zuvor platzierte Klinge.

Dieses Beispiel **veranschaulicht** das Prinzip und legt keinen konkreten Boss als kanonisch fest.

## Leveldesign und Mindestkonfiguration

Hindernisse dürfen **eine bestimmte minimale Elementausstattung erzwingen**, solange die notwendigen Ressourcen nachvollziehbar beschaffbar sind. Die bevorzugte Richtung ist, nach Möglichkeit mehrere systemisch gültige Lösungen zuzulassen, statt jede Interaktion an ein starres Skript zu koppeln.

Beispiel: Windklingen überspringen eine Passage; ohne Wind lässt sich über blockierte Wasserangriffe und erzeugte Eisplattformen vielleicht ein anderer Weg schaffen. Das ist eine Option, keine festgelegte Levelkarte.

## Anti-Softlock-Design

**Anforderung:** Das Spiel muss ungewinnbare Situationen vermeiden bzw. erkennen und korrigieren.

Zwei getrennte Klassen:
1. **Waffe unerreichbar:** im Abgrund, außerhalb der Navmesh, in einem unzugänglichen Bereich, durch Physikfehler verloren. Für Unique-Schwerter: sicherer Recovery-Pfad.
2. **Kombination unerreichbar:** Kein zugänglicher Weg mehr, die für den Kampf notwendige Elementsequenz aufzubauen. Arena/Boss muss wieder genügend Quellen liefern oder einen alternativen Siegweg ermöglichen.

Praktische Designstrategie (Vorschlag): Keine globale vollständige Lösbarkeitsberechnung voraussetzen, sondern pro Begegnung **garantierte, regenerierbare Lösungsquellen** planen. Kann ein Boss beispielsweise Eiszapfen von der Decke schlagen, lässt sich verlorenes Eis organisch ersetzen. Das muss keine sichtbare „Hilfsfunktion“ sein.

## Schwierigkeit

- Hohe Reaktionsanforderung allein reicht nicht: Entscheidungsdruck entsteht aus **unterschiedlichen Bosszuständen, Elementinteraktionen und Waffenpositionen**.
- Spieler können Waffen vorbereitend platzieren; Bossbewegungen und Umweltereignisse können diese Planung verändern.
- Schwerter sind austauschbar; wichtiger als Besitz ist, **wo** sie liegen und **wann** sie gebraucht werden.
- Eine fortgeschrittene Herausforderung ist der Echtzeitwechsel der eingeübten Tasten→Element-Zuordnung.

## Testfragen

- Erkennen Spieler, welche Waffe in welcher Phase fehlt?
- Ist ein Slotwechsel unter Beschuss motorisch machbar und fair?
- Welche Frustration entsteht, wenn eine gute Klinge weit entfernt steckt?
- Wie verlässlich lassen sich Softlocks schon im Encounter-Design vermeiden?
- Führt die Möglichkeit unendlicher Wind-Midair-Jumps zu willkommenen Abkürzungen oder trivialisiert sie Begegnungen?
