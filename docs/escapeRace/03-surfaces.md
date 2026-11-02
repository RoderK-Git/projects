# 03 — Bewegte Oberflächen, Relativbewegung und Weltgeometrie

## Allgemeines Flächenprinzip

Jede **geeignete** Fläche kann temporäre Fahrbahn sein: Straßen, Fassaden, Dächer, Brückenunterseiten, Züge, andere Fahrzeuge, umstürzende Bauwerke, kenternde Schiffe, rotierende Strukturen, große Kreaturen. Es soll möglichst **ein und dasselbe** Kontakt-/Bewegungssystem verwendet werden; keine Spezialanimation je Objekt.

Oberflächen können übersetzt, gedreht und/oder deformiert werden. **Die Bewegung des Fahrzeugs ist relativ zu dieser Fläche zu verstehen.**

## Referenzmodell

Für eine annähernd starre Fläche mit linearer Geschwindigkeit `v_s`, Winkelgeschwindigkeit `ω_s`, Zentrum `c_s` und Kontaktpunkt `p` ist ihre momentane Geschwindigkeit am Kontaktpunkt:

`v_surface(p) = v_s + ω_s × (p - c_s)`

Die relative Kontaktgeschwindigkeit ist:

`v_rel = v_vehicle(p) - v_surface(p)`

Die Fahrzeuggeschwindigkeit am Kontaktpunkt kann gegebenenfalls zusätzlich die eigene Drehbewegung des Fahrzeugs enthalten. Für weiche Kollisionen, Landegüte und Geschwindigkeitsübertragung ist **Relativbewegung am Kontaktpunkt** wichtiger als bloße Weltgeschwindigkeit.

**Spielregeln sind bewusst nicht realistisch:** Haftung, Oberfläche-als-Boden, Booster und perfekte-Übergang-Boni dürfen diese Werte arcadehaft modifizieren. Die obige Betrachtung dient nur der konsistenten Grundlage.

## Umstürzendes Hochhaus: bewegte Rampe

1. Gebäude beginnt zu kippen; visuelle und akustische Warnsignale.
2. Spieler springt auf die **fallende Fassade**.
3. Fassade rotiert weiter; Spieler fährt relativ zu ihr, korrigiert Kurs und Lage.
4. Sauberer Kontakt und angepasste Orientierung erlauben Flow ohne abrupte Bremsung.
5. Vor dem Aufschlag springt er ab und übernimmt gezielt einen Teil des Oberflächenmoments.
6. Der Trümmerhaufen bietet später eine **andere** Route bzw. Rampe.

Kern: derselbe Weltuntergang erzeugt je nach Zeitpunkt andere Spielmöglichkeiten; die Fassade ist nicht nur Hindernis, sondern temporäre Fahrbahn.

## Zug als „vertikales Förderband“

**Besonders reizvolles Beispiel aus dem Gespräch.** Ein schnell vorbeifahrender Zug transportiert das Auto durch die Stadt, während es auf der Waggonseite eigene Bewegungen ausführt.

- **Mit dem Zug fahren:** Relativbewegung an der Seitenwand plus Zugbewegung kann hohe Weltgeschwindigkeit ergeben.
- **Gegen die Fahrtrichtung:** Eigene Bewegung kann die Zuggeschwindigkeit teilweise kompensieren.
- **Vertikal die Waggonseite hoch:** Zug bewegt Auto horizontal; Fahrer erklimmt die Seitenwand relativ zum Zug — ein **vertikales Förderband**.
- **Absprung:** Der Wagen kann die seitliche Transportgeschwindigkeit des Zuges beim Sprung mitnehmen; ideal für den Wechsel auf eine Hausfassade.
- **Kurvenfahrt:** Waggon und seine Kontaktfläche ändern Ausrichtung und Richtung — dynamische Korrekturen erforderlich.
- **Zwei entgegenfahrende Züge:** spektakulärer, aber sehr anspruchsvoller Wandwechsel; große relative Geschwindigkeit muss durch Timing/Booster und die großzügigen Spielregeln beherrschbar bleiben.

**Wichtige Präzisierung:** Geschwindigkeiten werden vektoriell addiert. „Mitfahren = schneller“ gilt nur je nach Richtung; die schräge, senkrechte oder entgegengesetzte Bewegung muss korrekt transformiert werden.

## Weitere Oberflächenexperimente

- **Rotierendes Riesenrad / Maschinenteil:** tangentiale Geschwindigkeit nutzen.
- **Kenterndes Schiff:** Neigung und Kontaktfläche ändern sich kontinuierlich.
- **Großes Monster:** Rücken als deformierende, mobile Strecke.
- **Andere Fahrzeuge:** als improvisierte Rampen, seitliche Anfahrflächen oder Sprungplattformen.
- **Fliegende Trümmer:** sehr kurzfristige Bewegungsmöglichkeiten.

Diese Beispiele sind Szenarioideen und keine zugesagten Features. Dynamische/verbiegende Körper sind deutlich anspruchsvoller als starre Rigid Bodies.

## Architekturregeln und Risiken

- Fläche im **Weltkoordinatensystem** und in ihrem **lokalen Koordinatensystem** beschreiben.
- Normale/Tangenten an Kontakt- und Zielstelle abfragen; Kontaktpunktgeschwindigkeit korrekt aus Translation und Rotation herleiten.
- Neue Zieloberflächen ermitteln, ohne den Spieler „magnetisch“ automatisch zum Ziel zu lenken.
- Übergang **am Ort und zu der Zeit** bewerten, nicht nur als fixen Animationszustand.
- Keine Teleports oder unmotivierten Snaps, die die Illusion handwerklicher Kontrolle brechen.
- Vorsicht bei rotierender/deformierter Geometrie, durchgehender Kollisionsdetektion, Tunneling, deterministischen Replays und Online-Synchronisation.

**Früh testen:** kleine bewegte Wand oder Plattform, danach rotierender Quader, zuletzt ein mehrteiliger fahrender Zug. Ein vollständiges einstürzendes Hochhaus ist für den ersten Prototyp unnötig.
