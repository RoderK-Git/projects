# 6 Blades

> **Konzeptstand:** 1.–2. November 2026 · **Status:** Spielkonzept, nicht prototypisch validiert  
> **Arbeitstitel:** *6 Blades* — möglicherweise 8/10/12 Slots, falls Bedienbarkeit und Prototypen das rechtfertigen.

## Pitch

Ein schnelles, strategisches Schwertkampf-Actionspiel in einem fantastischen japanischen Samurai-/Ninja-Setting. Ryu, Sohn eines vernichteten Clanführers, entwickelt einen ungewöhnlichen Kampfstil: Er zieht für nahezu jeden Schlag eine andere Klinge, führt die Aktion aus und steckt sie wieder zurück – oder wirft die Waffe weg. Maximal **sechs physische Schwertplätze** sind direkt bedienbar. Elementare Schwerter machen Angriffe, Blocks, Konter, Fortbewegung und Umgebungsmanipulation zu einem gemeinsamen, kombinatorischen System.

**Kernidee:** Nicht der Besitz eines legendären Schwerts macht Ryu stark, sondern seine Fähigkeit, situativ mit immer neuen Klingen zu kämpfen. **Schwerter sind buchstäblich Wegwerfware.** Waffenwechsel geschehen in Echtzeit in der Spielwelt, niemals über ein pausierendes Inventarmenü.

Die scheinbar dämonische Rivalin, die Ryu ständig herausfordert und trainiert, ist in Wahrheit **Shirakaba (Björk)** – die Frau, die ihn beim Untergang seines Clans rettete und ihren Tod inszenierte, um seinen gebrochenen Lebenswillen durch Rache zu ersetzen.

## Dokumentation

| Dokument | Inhalt |
|---|---|
| [Vision und Designprinzipien](VISION.md) | Genre, Spielerfantasie, Kernschleife, Grenzen |
| [Geschichte und Figuren](STORY.md) | Shirakaba/Björk, Ryu, Katanagari, Prolog, Enthüllung |
| [Kampfsystem und Slots](COMBAT.md) | Ziehen/Schlagen/Stecken, Sperrregel, Blocks, Konter, Special-Moves |
| [Controller und HUD](CONTROLS.md) | PlayStation-Belegung, Modifier, HUD-Matrix, Eingabeverarbeitung |
| [Elemente und Fortbewegung](ELEMENTS.md) | Reaktionen, elementare Verteidigung, Movement, Emergenz |
| [Waffen und Welt](WEAPONS.md) | Physisches Schwertmanagement, improvisierte Waffen, Unique-Schwerter |
| [Boss- und Leveldesign](ENCOUNTERS.md) | Dynamische Konfiguration, Arena-Waffen, Softlock-Vermeidung |
| [Prototyp und offene Fragen](PROTOTYPE.md) | Tests, Hypothesen und noch nicht entschiedene Details |

## Bereits festgelegte Grundlagen

1. **Sechs direkt adressierbare Slots** als Ausgangspunkt, nicht sechs gleichzeitig geschwungene Schwerter.
2. **Slotwahl ≠ Menünavigation.** Drei Gesichtstasten und ein gehaltener Modifier bestimmen die sechs Slots.
3. **Jede Schwertaktion** (auch Block, Konter und elementare Bewegung) zählt zur Wechselregel: derselbe Slot darf nicht zweimal direkt aufeinander folgen. Die genaue Umsetzung ist zu testen.
4. **Frei belegbare Plätze und Elemente:** Mehrere Schwerter desselben Elements sind sinnvoll und für bestimmte direkte Elementkombinationen erforderlich.
5. **Elementinteraktionen** gelten auch beim Blocken sowie in der Umgebung (z. B. Wasser + Eis → Eiswand/Plattform; Wasser + Feuer → schädlicher Dampf).
6. **Waffen bleiben physisch in der Spielwelt:** Geworfene oder abgelegte Klingen stecken in Boden/Wänden oder liegen dort und können wieder aufgenommen werden.
7. **Kein Ersatzinventar:** Sechs Slots sind die gesamte mitgeführte Waffenkapazität. Ersatzwaffen müssen aus der Umgebung kommen.
8. **Temporäre, improvisierte Waffen** wie Eiszapfen sind erwünscht.
9. **Die Welt darf nicht dauerhaft ungewinnbar werden.** Boss-/Arenadesign oder Korrekturmechanismen gewährleisten erneut beschaffbare notwendige Elemente.
10. **Emergente Lösungen zuerst zulassen und testen:** Zwei Windklingen könnten durch abwechselnde Verwendung unbegrenzte Midair-Jumps ermöglichen; ob das begrenzt wird, ist offen.

## Inspirationshinweise

- Jet-Li-Filmszene (Filmtitel vom Ideengeber **unsicher**, als „Iron Tiger“ erinnert): mehrere Schwerter an beiden Seiten, rasches Ziehen und Wechseln, verbundene Augen beim Kampf gegen ehemalige Verbündete. **Inspiration, keine geplante Szenenübernahme.**
- *Magicka*: systemische Elementkombinationen.
- *Street Fighter*: rudimentäre richtungsbasierte Special-Moves.
- *Onimusha 2*, insbesondere Gogandantess: visuelle Inspiration für Shirakabas hochrangige Dämonenverkleidung.
- *Mistress of Time and Space*: verwandtes dramatisches Motiv der wiederkehrenden Gegner-/Lehrerfigur, keine bislang festgelegte direkte Storyverbindung.

> **Dokumentationsprinzip:** „Festgelegt“ bezeichnet gemeinsame Konzeptentscheidungen, **nicht** durch Tests bewiesene Spielbarkeit. Beispiele und Vorschläge sind als solche gekennzeichnet.
