# 07 — Architekturhypothesen und Prototypstrategie

> Technische Vorschläge, **keine** verbindliche Engine-/Stack-Entscheidung.

## Modulare Verantwortlichkeiten

1. **VehicleMotion:** Arcade-Fahren, Drift, Vortrieb, Trägheit, Luftimpulse, kontrollierte Roll-/Pitch-/Yaw-Ausrichtung.
2. **SurfaceContact:** Kontaktpunkte, Flächennormalen, Zieloberflächen, Grip/Adhäsion, Wechsel zwischen Boden/Wand/Decke.
3. **MovingSurfaceFrame:** Transform, lineare und Winkelgeschwindigkeit der Fläche am Kontaktpunkt; Relativgeschwindigkeit, Impulsübertragung.
4. **TransitionQuality / Momentum:** Güte eines Übergangs, Tempoerhalt/-bonus oder Verlust; konsistenter Output für Physik und Audio.
5. **DamageVisual / Health:** Schaden unabhängig von Handling, Reparatur und Zerstörung/Respawn.
6. **AudioFeedback:** kontinuierliche Klangparameter basierend auf Fahrpräzision.
7. **CameraRig:** fahr- und oberflächenbewusst, glättet ohne Verlust der Steuerbarkeit.
8. **CatastropheEvents:** Vorzeichen, Aktivität, Nachwirkung, räumliche/geometrische Veränderung.
9. **Director:** Eventauswahl unter Fairness-, Timing- und Modusbedingungen.
10. **GameMode:** Regeln für Ziele, Siege, Spawns, Matchzeit, Reparaturverfügbarkeit.

Diese Aufteilung soll eine spätere Zusammenführung in eine Engine nicht verhindern. Sie macht aber die Kernfragen unabhängig testbar.

## Prototyp in aufeinanderfolgenden Schritten

### P0 — Fahrgefühl auf neutraler Testfläche
- Ein Fahrzeug, einfaches Beschleunigen/Lenken/Bremsen, Drift und Rückwärtsfahren.
- Einfache Rampe; Sprung, Luftrotation, Korrekturboost einschließlich Abwärtsboost.
- Schon hier prüfen: Wiederholbarkeit, Recovery, Lesbarkeit und „macht Bewegung allein Spaß?“.

### P1 — Stationäre 3D-Parkourflächen
- Zwei gegenüberliegende Wände mit Häuserschlucht.
- Wallride → Flip → Wallride; senkrechte Fassadenfahrt.
- Sidewheel-Fahrt durch einen Spalt; Wand- und Deckenübergänge.
- Kamera und Präzisions-Audio gleichzeitig mit entwickeln.

### P2 — Moving Surfaces
- Fahrende rechteckige Plattform; rotierender Quader.
- Waggonwand mit Translationsgeschwindigkeit; vertikales „Förderband“.
- Sprung zwischen bewegter und statischer Fläche; Momentum-Übertragung.
- Erst danach fallende/freie Gebäudegeometrie.

### P3 — Visuelles Damage/Repair und Flow
- Schaden verändern, **ohne** Handling zu beeinflussen.
- Einfaches Health/Repair-Item oder Reparaturzone.
- Saubere Kontakte klingen weich; Fehler rumpeln und reduzieren kurz Speed.
- Evaluieren, ob explizite Flow-Boni gegenüber rein aus Impulsen entstehendem Speed sinnvoll sind.

### P4 — Eine Katastrophe
- Zum Beispiel einstürzende Wand/Gebäude oder Hai-Gulli.
- Warnung → Ereignis → Nachwirkung.
- Mehrere zufällige Zeit-/Ortsvarianten in derselben Testkarte.
- Verifizieren: unvorhersehbar **und** fair telegraphiert.

### P5 — Kompetitiver Test
- Zwei bis wenige Fahrzeuge; zunächst einfache Rennen/Verfolgung.
- Director-Balancing ohne Rubberbanding.
- Erst anschließend Multiplayer, weitere Modi und Massendestruktion im benötigten Umfang.

## Testfragen und Messgrößen

**Beherrschbarkeit:** Wie zuverlässig schaffen Spieler absichtlich dieselben Trickketten? Wie viele Fehlversuche sind auf Timing vs. unklare Steuerung zurückzuführen?

**Lernkurve:** Können Anfänger sofort fahren, zeigen sich aber messbare Vorteile nach Übung (z. B. saubere Landungen, Durchschnittsgeschwindigkeit, gesparte Korrekturzeit)?

**Momentum:** Wird ein makelloser Übergang tatsächlich schneller/angenehmer? Ist ein kleiner Fehler kurz und verständlich spürbar statt unverhältnismäßig bestraft?

**Bewegte Flächen:** Funktioniert der Übergang von stationärer zu bewegter Wand samt Rotation ohne Ruck, falsche Impulse oder „Verkleben“?

**Katastrophen:** Erkennt man das Warnsignal, obwohl Zeitpunkt/Ort unbekannt sind? Profitieren unterschiedliche Positionen nachvollziehbar? Ist das System durch absichtlich langsames Fahren ausnutzbar?

**Audio/Kamera:** Kann man die Qualität des Kontakts ohne HUD erkennen/hören? Wird den Spielern bei Rollen, Deckenfahrt und Kippbewegungen schwindelig?

## Besondere Risiken

- Physik-Assistenz fühlt sich wie Autopilot an oder bleibt zu unvorhersehbar.
- Klassische Kollisionserkennung/Simulation schafft rechtwinklige und extrem schnelle Kontakte nicht robust.
- Frei deformierende Trümmer und rotierende Gebäude sprengen Performance/QA.
- Dynamische Zerstörung erschwert Multiplayer-Netcode, Replays und Synchronisation stark.
- Top-Speed übersteigt Reaktions- und Warnfenster.
- Audiocues gehen zwischen Katastrophen und Motoren unter.
- Visuelle Health wird bei komplexen Schadensbildern unlesbar.
- Director tarnt lediglich eine unfairere Form des Rubberbanding.

**Scope-Prinzip:** Zuerst beweisen, dass **ein einzelnes Fahrzeug in einer leeren Häuserschlucht Spaß macht**. Ohne diesen Nachweis ist die aufwendige Apokalypse nur Kulisse.
