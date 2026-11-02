# Controller, Eingaben und HUD

## Primärer PlayStation-Entwurf

Drei Schwerttasten: **□ (Viereck), △ (Dreieck), ○ (Kreis)**. Ein **gehaltener** Modifier (Beispiel **L1**) bestimmt die Zeile. **Kein Toggle per Tastendruck.**

| Modifierzustand | □ | △ | ○ |
|---|---|---|---|
| L1 **gehalten** | Slot 1 | Slot 2 | Slot 3 |
| L1 **losgelassen** | Slot 4 | Slot 5 | Slot 6 |

Welche Zeile oben oder unten und welche am Körper links/rechts liegt, kann geändert werden, **ohne** das Grundkonzept zu berühren. Ausschlaggebend ist die **eindeutige, verlässliche** Tastenzuordnung.

## HUD-Vorschlag

Die HUD-Matrix zeigt **zwei Zeilen à drei Felder**, in jeder Zeile exakt die Reihenfolge □, △, ○. Sie zeigt je Slot:

- Belegung bzw. Leere;
- Element(e), visuell leicht erkennbar;
- zuletzt verwendeten/aktuell unzulässigen Slot;
- aktive Zeile aufgrund des gegenwärtigen Modifierzustands.

```text
                 □            △            ○
   L1 gehalten  [🔥 Slot 1]  [❄ Slot 2]   [⚡ Slot 3]
   L1 frei      [💧 Slot 4]  [🔥 Slot 5]   [🌪 Slot 6]
```

Dies ist **ein illustratives Setup**. Bei Umrüstung ändert sich die Anzeige nur am betreffenden Platz. **Keine automatische Sortierung** und kein Springen von HUD-Feldern: Die räumliche Konstanz unterstützt das Muskelgedächtnis. Farben sollten mit eindeutigen Symbolen kombiniert sein.

## Schwertauswahl beim Blocken

Eine **gehaltene Blocktaste** modifiziert die drei Angriffstasten zu Block-Aktionen. Zusammen mit L1 sind auch hier alle sechs Plätze ansprechbar.

Beispielhafte Eingabehierarchie:
- `□`: Angriff mit dem zugeordneten Slot.
- `L1 + □`: Angriff mit dem Slot der anderen Zeile.
- `Block halten + □`: Block mit der ausgewählten Klinge.
- `Block halten + L1 + □`: Block mit der Klinge der anderen Zeile.

Die konkrete Blocktaste (z. B. L2) ist noch nicht endgültig festgelegt. Grundbewegungen wie Lauf, Sprung und Ausweichen benötigen weiterhin Zugriff auf Controllerfunktionen. Elementare Bewegungsaktionen könnten über Richtungs-/Special-Eingaben der entsprechenden Schwertslots laufen.

## Eingabetechnische Konsequenzen

- Bei der Betätigung wird **Slot und Modifierzustand zu diesem Zeitpunkt** aufgelöst; ein Loslassen des Modifiers darf den bereits begonnenen Befehl nicht auf eine andere Klinge umlenken (technischer Vorschlag).
- Schnelle Kombinationen sollten Eingabepuffer und korrektes Timing besitzen, ohne die Slotidentität nachträglich zu verändern.
- Kombinationen wie L1 + Block + Angriffstaste müssen ergonomisch geprüft werden.
- Aktionen dürfen nicht unvorhersehbar werden, weil eine Animation die Klinge körperlich gerade an einer anderen Seite zeigt.
- Vorhersehbarkeit und Muskelgedächtnis sind wichtiger als anatomisch exakte Schwertpositionen.

## Noch offen

- Konkrete Funktion der übrigen Tasten und Trigger.
- Wie Special-Move-Richtungsfolgen mit Bewegung/Jump/Evade interagieren.
- Timing, Eingabepuffer, Zugänglichkeit, alternative Tastaturbelegung.
- Ob andere Slotzahlen als sechs (8/10/12) sinnvoll und bedienbar sind.
- Farb-/Formgestaltung, visuelles Feedback für Komboketten und Blockzustände.
