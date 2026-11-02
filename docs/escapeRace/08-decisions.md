# 08 — Festlegungen, Vorschläge und offene Designfragen

## Als gemeinsame Richtung ausdrücklich bestätigt

- **EscapeRace** ist Arbeitstitel.
- Vehicle-Skill-/Parkour-Game statt lediglich klassischer Rennsimulation.
- **Easy to learn, hard to master** mit sehr hohem Skill-Ceiling.
- Verrückte, übertriebene Bewegungen, aber **tatsächliche Steuerungskunst** statt geskripteter Tricks.
- Driften, harte Turns, Rückwärtsfahrt, Wallrides, Flips, seitliches Aufstellen auf Räder, Luftkontrolle, Booster.
- **Deckenfahrt** zulässig.
- **Senkrecht Hauswände eine Weile hochfahren**, vertikale Flächenwechsel und weiche Wallride-Flip-Wallride-Folgen.
- **Bewegte Oberflächen** wie fallende Hausfassaden; Züge insbesondere als **vertikales Förderband** nutzen.
- Gute Manöver erhalten oder steigern Geschwindigkeit; kleinere Patzer kosten kurz Tempo.
- **Akustische Eleganz:** präzise Kontakte überraschend leise, Fehler rumpeln.
- **Visuelle Schäden**, anfangs ohne fahrdynamische Nachteile; optische Health-Anzeige möglich.
- **Reparatur im Fahren:** sammelbare Items, durchfahrbare Zonen und aktivierbare Items.
- **Unvorhersehbare** Katastrophen bezüglich **Zeitpunkt/Ort**, aber **kurzfristig erlernbare Warnsignale**.
- Dynamische Ereignisse können natürliches **Balancing ohne klassisches Rubberbanding** schaffen.
- Genannte Modi: klassisches Rennen, Last Man Standing, Capture the Flag durch die Stadt; Verfolgungs-Parkour mit mehreren Spielern.
- Stark gewollte Inspiration: Vanellope/Shank/Slaughter Race, Tony Hawk, Mirror's Edge.
- Humorvoller Slogan **„Alternative Realism“** mit augenzwinkerndem „Alternative Facts“-Bezug.

## Konzeptionelle Vorschläge, noch nicht beschlossen

- Spezifische Boosteraufteilung und Gamepad-Tastenbelegung.
- Kontinuierliche mathematische Qualitätsfunktion und mögliche Flow-Zusatzboni.
- Catastrophe Director mit Eventscheduling, Cooldowns und Fairnesskriterien.
- Modusvarianten Stunt Run/Survival Escape.
- Reparaturinszenierung, Schadensschwellen, Todes-/Respawnlogik.
- Kamera mit stabilisiertem Horizont und bewegungsabhängigen Übergängen.
- Allgemeine modulare Systemarchitektur, konkrete Implementierungspfade und MVP-Reihenfolge.
- Flaggenhalter ohne Nachteile; Zahl und Verteilung der Reparaturstationen.
- Monster, Schiffe, Riesenräder, Tsunami, Vulkane etc. als zusätzliche Event-/Flächenideen.

## Offene Entscheidungen

1. **Steuerung:** Wie viel Roll/Pitch/Yaw auf welche Eingaben? Wie funktionieren Booster in und ohne Oberflächenkontakt?
2. **Oberflächenhaftung:** Wann „klebt“ das Auto an Wand/Decke; wann springt es ab; wie viel automatische Stütze fühlt sich legitim an?
3. **Speed-/Flow-Modell:** Bonusgrößen, natürliche vs. künstliche Grenzen, Kollisionstoleranz, Spielbarkeit bei sehr hoher Geschwindigkeit.
4. **Rettung und Ausfall:** Welche Kollisionen machen nur Schaden und welche führen zum Tod? Wie funktioniert Recovery auf dem Dach?
5. **Health/Repair:** Wie liest man Schaden ohne HUD, wann und wo gibt es Reparaturen, was bewirkt Schaden in verschiedenen Modi?
6. **Director:** Fairnessmetriken, Ereignishäufigkeit, Persistenz und Anti-Exploit-Regeln.
7. **Welt:** offene Stadt, modularer Kurs, Arenen, wie groß/vertikal, welche Eventthemen zuerst?
8. **Spielmodi:** genaue Regeln, Spieleranzahl, Teams, Spawns, Sieg-/Fangbedingungen, Kooperation.
9. **Netzwerk:** Synchronisierung von dynamischer Zerstörung und Oberflächenbewegung.
10. **Präsentation:** Kamera, Zugänglichkeit bei schnellen Rotationen, Soundmix, optischer Stil.
11. **Produkt:** Plattformen, Engine, Umfang, Progression, Fahrzeuge, Titel- und Markenprüfung.

## Priorität der nächsten Erkenntnisse

1. **Steuerung fühlt sich fantastisch an.**
2. **Manöver sind bewusst und wiederholbar, nicht nur Glück.**
3. **Schneller, sauberer Flow ist mechanisch und akustisch spürbar.**
4. **Bewegte Flächen funktionieren nach denselben Regeln.**
5. **Ereignisse überraschen fair und verbessern Wettkämpfe, ohne Können zu entwerten.**

## Abgrenzung

Diese Dokumente sind eine **Konzeptbasis**, kein bereits entwickeltes Spiel und keine Zusicherung technischer Machbarkeit. Wo das Gespräch keine endgültige Entscheidung liefert, sind Varianten bewusst als **Vorschlag** oder **offen** markiert.
