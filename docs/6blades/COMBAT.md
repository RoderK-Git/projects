# Kampfsystem und Schwertslots

## Physische und logische Struktur

- **Sechs frei belegbare Slots** sind der Ausgangspunkt; ein Slot enthält maximal eine unmittelbar einsatzbereite Klinge oder ist leer.
- Jeder Slot hat eine eindeutige, jederzeit verfügbare Eingabe über drei Aktionstasten plus gehaltenen Modifier.
- Die Zugehörigkeit zu einer physischen Körperseite ist für Spieler und Bedienung **irrelevant**; wichtiger ist eine unveränderliche Slot→Taste-Zuordnung.
- Jeder Schwerthieb verwendet im Normalfall genau die Klinge des gewählten Slots: **ziehen → schlagen → wieder einstecken**, oftmals bei nahezu jedem Schlag.
- Schwerter können als Special-Move geworfen, abgelegt oder durch andere Aktionen aus dem Slot entfernt werden.
- Slots und Klingen sind getrennte Konzepte: Die Ausrüstung kann wechseln, die Tastenbindung des Slots nicht.

## Konsequente Wechselregel

**Derselbe Slot darf nicht unmittelbar zweimal nacheinander aktiviert werden.** Eine andere Schwertaktion muss dazwischenliegen. Die vorgeschlagene Regel soll **für jede Schwertnutzung** einheitlich gelten: Angriff, Block, Konter, Wurf und elementare Bewegungsaktion.

Beispiele:
- Feuer auf Slot 1, Feuer auf Slot 4: `1 → 4` ermöglicht **Feuer + Feuer**.
- Nur Feuer auf Slot 1: `1 → 1` ist unzulässig.
- `1 → 2 → 1` ist zulässig, wenn Slot 2 benutzbar ist.
- Ein Element ist **nicht** mit dem Slot identisch. Die gleiche Elementfolge benötigt verschiedene entsprechend ausgerüstete Plätze.

**Zu testen:** Ob Sperren nach Abwehr oder Bewegung flüssig bleiben und welche Rückmeldungen dafür notwendig sind. Die Sperre ist als sequenzbasierte Regel gedacht; ein bloßes Warten soll sie nicht zwingend aufheben. Das Zeitverhalten ist noch nicht empirisch erprobt.

## Elementketten

Der Spieler stellt seine Angriffsfolgen aus dem gegenwärtigen Schwert-Setup zusammen. Doppelte Elementbelegung ist eine bewusste Investition. Unterschiedliche Elemente bieten größere Vielfalt; mehrfach gleiche ermöglichen engere, mächtigere oder spezielle Folgenreihen.

```text
Slot 1 Feuer ──┐
               ├─ 1 → 4: Feuer + Feuer
Slot 4 Feuer ──┘

Slot 2 Wasser ─┐
               ├─ 2 → 3: Wasser + Eis
Slot 3 Eis ────┘
```

Die exakte Semantik von Angriffsketten (Trefferzwang, zeitliches Fenster, Reihenfolge, Kombolänge) ist **offen**. Erwünscht ist ein systemisches, Magicka-artiges Kombinieren statt einer riesigen Tabelle isolierter Spezialfähigkeiten.

## Defensive

Die Slotwahl funktioniert auch für **Blocken und Kontern**. Eine gehaltene Blocktaste kann die Angriffstasten als „Block mit gewähltem Schwert“ interpretieren. Der Modifier bleibt erhalten und wählt weiterhin eine der zwei HUD-Zeilen.

Beispiel: Ryu blockt einen gegnerischen Wasserstoß mit Eis → temporäre Wand/Plattform; mit Feuer → heiße, schädliche Dampfwolke.

Ein Block ist **keine elementneutralisierte Pauschalaktion**: Die beteiligten Elemente reagieren. Der Gegner kann damit bewusst oder ungewollt die Bühne für eine neue Kombo liefern.

Zu testen: Unterschied normaler/perfekter Blocks, Paradenfenster, Kontertiming, Umgang mit gleichzeitigen bzw. sehr schnellen Attacken und Wechselsperre nach Block.

## Special-Moves

Rudimentäre **Street-Fighter-artige Richtungseingaben** plus Slotwahl. Beispiele als **Ideen, nicht endgültige Belegung**:

- Richtungsfolge + Slot: Klinge werfen statt normal zuschlagen.
- Richtungsfolge + Slot: schwertindividuelles Manöver, spezieller Stich oder Konter.

Die Special-Moves wirken mit der **konkreten Klinge** im gewählten Slot. Ein Wurf leert diesen Slot, bis eine Klinge wieder hineingesteckt wird.

## Flow und Animation

Angriffe sind schnell und sollen als choreografierte Übergänge wirken. Für direkte Folgeeingaben sind Eingabepuffer und flüssige Animationstransitionen eine naheliegende technische Hypothese; wie Cancel-Fenster, Recovery, Kollision und Kontinuität implementiert werden, ist ungeklärt.

## Was das System nicht ist

- Keine sechs gleichzeitig geschwungenen Schwerter.
- Kein klassisches Waffenrad, kein dauerhaftes Waffeninventar, kein ständiges Menü.
- Kein starres „Slot 1 = Feuer“.
- Kein auf reguläre Angriffe beschränktes Elementsystem.
