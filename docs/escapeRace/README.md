# EscapeRace (Arbeitstitel)

> **Alternative Realism™** — Die Physik ist nicht falsch. Sie folgt einer alternativen Realität.

**Status:** Konzeptphase · **Stand:** November 2026

## Elevator Pitch

Ein überdrehtes, kompetitives **Fahrzeug-Geschicklichkeits- und Parkour-Spiel**: Autos driften, springen, rollen, fahren auf zwei Rädern, an Wänden und Decken und wechseln fließend zwischen sogar **bewegten** Oberflächen. Währenddessen verwandeln Weltuntergangskatastrophen eine dreidimensionale Stadt in einen ständig neuen Skatepark. Die Fahrer überleben nicht nur das Chaos, sondern nutzen es für spektakuläre Manöver. **Echter Skill** entscheidet; nicht das Auswendiglernen fester Strecken und nicht klassische Rubberband-Geschwindigkeitstricks.

**Kurzform:** *Tony Hawk auf vier Rädern, während die Welt untergeht.* Ein Anfänger flieht vor dem einstürzenden Hochhaus; ein Profi nutzt es als Rampe.

## Designpfeiler

1. **Easy to learn, hard to master:** Zugängliches Arcade-Fahren, hohe Beherrschungstiefe.
2. **Spieleragency statt QTE:** Tricks entstehen aus frei kombinierbaren Steuerungs- und Physikmechaniken, nicht aus geskripteten Spezialanimationen.
3. **Alternative Realism:** Absurde, aber konsistente, lesbare und erlernbare Regeln statt Realismuszwang.
4. **Fahren in 3D:** Straße, Wand, Decke, Fassadenschlucht, Fahrzeug, Zug und kollabierendes Gebäude können Fahrflächen sein.
5. **Beherrschbarkeit jederzeit:** Auch in der Luft, auf zwei Rädern und nach Kollisionen soll der Spieler möglichst kontrollieren und retten können.
6. **Flow ist Leistung:** Präzision bewahrt oder erhöht Momentum; kleine Patzer erzeugen kurze Tempoeinbußen und akustisches Rumpeln.
7. **Katastrophen sind Gefahr *und* Gelegenheit:** Wann und wo ein Ereignis passiert, ist nicht fix. Seine kurzfristigen Warnzeichen und sein Verhalten sollen erlernbar sein.
8. **Plausibles kompetitives Balancing:** Ein Ereignis betrifft Fahrer je nach Position und Ankunftszeit unterschiedlich; der Director eröffnet Chancen, garantiert keine Aufholjagd.
9. **Sichtbare Folgen ohne ruiniertes Handling:** Optischer Schaden kommuniziert Health, wirkt sich zunächst nicht auf die Steuerung aus; Reparatur im Fahrfluss.
10. **Ein Kernsystem, viele Modi:** Rennen, Überleben, Verfolgung und Capture the Flag verwenden dieselbe Bewegungsmechanik.

## Dokumentation

| Datei | Inhalt |
|---|---|
| [Vision und Designregeln](01-vision.md) | Identität, Inspiration, Spielerfantasie, UX, Abgrenzung |
| [Fahrzeugsteuerung und Parkour](02-movement.md) | Drifts, Air Control, Booster, Wall-/Ceiling-Rides, Sidewheel, Momentum |
| [Oberflächen und bewegte Geometrie](03-surfaces.md) | Kontaktmodell, stürzende Gebäude, Züge, relative Geschwindigkeiten |
| [Katastrophen und Director](04-catastrophes.md) | Unvorhersehbarkeit, Warnsignale, Phasen, Balancing |
| [Spielmodi und Leveldesign](05-modes-world.md) | Rennen, Last Man Standing, CTF, Pursuit, Stunts, Städte |
| [Schaden, Reparatur und Audiodesign](06-feedback.md) | Visuelle Health, Reparaturen, Eleganz-Sound, Kamera |
| [Technische Architektur und Prototyp](07-prototype.md) | Systeme, minimale Tests, Reihenfolge, Messkriterien |
| [Entscheidungen und offene Fragen](08-decisions.md) | Festgelegtes vs. Vorschlag, Risiken, Validierung |

## Leitbeispiel: Die Stadt ist ein dynamischer Skatepark

Ein Auto rast auf eine Häuserfront zu, fährt **senkrecht** hinauf, springt über die Häuserschlucht, rollt in der Luft und setzt weich zum Wallride auf der Gegenseite an. Ein Haus kippt um: Der Spieler springt auf die *fallende* Fassade, surft auf ihrer Bewegung und stößt sich rechtzeitig ab. Anschließend nutzt er die Seitenwand eines vorbeifahrenden Zuges als **vertikales Förderband**: Er klettert relativ zum Waggon nach oben und wird gleichzeitig vom Zug durch die Stadt getragen. Ein perfekt abgestimmter Absprung überträgt dessen Momentum auf die nächste Bewegung. Währenddessen bricht womöglich ein Hai aus einem Gulli.

Nichts davon soll eine vorgefertigte Stuntsequenz voraussetzen; die Kunststücke sollen durch die generellen Regeln möglich werden.

## Inspirationsquellen (keine direkten Übernahmen)

- **Vanellope von Schweetz, Shank und Slaughter Race** (*Ralph Breaks the Internet*): unverschämte Fahrzeugskills, überdrehte Verfolgungsjagden, absurd gefährliche Welt.
- **Tony Hawk:** Trickkombinationen, Übung, Flow und persönliche Meisterschaft.
- **Mirror's Edge:** Parkour-Routen, Verfolgungen, Stadt als mehrdimensionaler Bewegungsraum.
- **MotorStorm: Apocalypse / Split/Second:** Spektakel und sich verändernde Strecken (vergleichbare existierende Ansätze).
- **Trackmania / Distance / Rocket League:** Vergleichspunkte für Präzision, Wand- und Luftbewegung (keine Festlegung auf deren Steuerung).

**Hinweis:** *EscapeRace* ist ebenso wie „Alternative Realism™“ ein Arbeitstitel/Claim; das ™ ist hier ein stilistischer Platzhalter, keine Aussage über registrierte Markenrechte. Popkultur-Anspielung „Alternative Facts“ aus Trumps Umfeld ist humoristisch intendiert. Keine Rechte oder Verwendbarkeit wurden geprüft.
