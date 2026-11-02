# 06 — Schaden, Reparatur, Sound, Kamera und Feedback

## Schadensmodell

**Besprochen und gewünscht:** Ein **visuelles Schadensmodell**; zumindest zunächst **keine Einschränkung der Fahrphysik** durch Beschädigung. Das Fahrzeug kann zunehmend ramponiert wirken, aber weiterhin präzise springen, driften und boosten. Optische Schäden können eine klassische Health-Bar teilweise oder ganz ersetzen.

Beispiele: Dellen, verformte Karosserie, fehlende Stoßstange, lose Tür, zerbrochene Scheiben, abgefallene Teile. Extrem-Schrottkarre kann weiterhin großartig fahren — der absurde Kontrast ist gewollt.

**Designvorschlag:** Intern Gesundheitswert/Schadensstufen führen, visuell klar kommunizieren. Bei kritisch niedrigem Wert eindeutige visuelle/akustische Warnung, damit Spieler den Zustand nicht missverstehen. Was bei „0“ passiert (Explosion, Knockout, Respawn), bleibt modusabhängig zu klären. Auch wenn das Aussehen ein Health-Indikator ist, sollen kleine Schäden keine heimlichen Fahr-Nerfs auslösen.

## Reparatur während der Fahrt

Ohne Anhalten/Unterbrechung des Spielflusses:

- Reparatur-Items überfahren/einsammeln.
- Reparatur-Zonen durchfahren.
- Einsetzbare Reparatur-Items aktivieren.

Beispielhafte Inszenierung (Vorschlag): völlig zerbeultes Auto rast durch eine Reparaturzone und kommt wenige Augenblicke später frisch zusammengesetzt heraus. **Offen:** Cooldowns, Häufigkeit, vollständige/partielle Wiederherstellung, Balance von Last Man Standing.

## Eleganz durch Sound

**Zentrale Idee des Nutzers:** Ein sauberer Trick darf selbst bei tonnenschweren Fahrzeugen **fast geräuschlos** wirken. Kleine Patzer **rumpeln kurz**. Die Soundlandschaft vermittelt Eleganz und Präzision, nicht nur Masse/Realismus.

| Fahrgefühl | Sound |
|---|---|
| Perfekter Wandkontakt | sanftes Aufsetzen, nahezu kein Störgeräusch |
| Präzise Trickkette | harmonischer Motor, dezentes Booster-Zischen |
| Leichte Fehlausrichtung | kurzes Rumpeln oder Scharren |
| Unsanfte Landung | metallisches Scheppern, Reifenquietschen |
| Voller Crash | harte, laute Kollision, Teileschaden |

Die **Abwesenheit** von Klappern ist die Belohnung. Keine zwingenden „Perfect!“-Fanfaren; es darf sich wie virtuos gespieltes Instrument anfühlen. Die umgebende Katastrophe bleibt laut und gefährlich: **Kontrast zwischen kontrolliertem Fahrer und chaotischer Welt**.

**Ein gemeinsamer Präzisionswert** kann Fahrreaktion, Soundmischung, Kontaktpartikel und Kamera-Feedback konsistent ansteuern. Kontinuierlich statt eines nur binären Perfekt/Fehler-Soundsystems.

## Visuelles Bewegungsfeedback

- Perfekt: weicher, nahezu verlustfreier Übergang von einer Kontaktfläche zur nächsten.
- Leichter Patzer: kurzer Ruck, etwas Schlingern, vielleicht Funken.
- Grober Patzer: heftiges Rumpeln, Tempoverlust, sichtbare Beschädigung.
- Rettung: Spieler korrigiert Lage nach Crash selbst, soweit möglich.

Die Informationsvermittlung soll möglichst **diegetisch** sein: sichtbarer Zustand statt dauerhaft dominanter Balken; Fahrgefühl und Sound statt ständiger Performance-Anzeige.

## Kamera

Bei Wand-, Decken- und Luftfahrt ist eine gewöhnliche am Fahrzeug festgeklebte Kamera potenziell desorientierend.

**Experimenteller Vorschlag:**

- Kameraposition folgt Bewegungsrichtung und räumlichem Ziel, nicht jeder Roll-Rotation der Karosserie.
- Horizont/Orientierung bleibt so stabil wie für Lesbarkeit nötig, kann bei vertikaler Fahrt langsam kippen.
- Bei Flips zeigt Kamera die Fahrzeugrotation statt sie vollständig mitzudrehen.
- Katastrophen-Telegraphen müssen auch bei hohem Tempo, auf einer Wand und beim Rückwärtsfahren erkennbar bleiben.
- Optionen für Kameraempfindlichkeit, Bewegungsreduktion und Sichtbarkeit prüfen.

Kameraregeln sind noch **nicht entschieden** und gehören zu den wichtigsten Prototypfragen.

## Gefahrenkommunikation

Ein Hai aus einem Gulli darf überraschend sein, aber das Warnsignal (klappernder Deckel, Wasserspritzen, Sound) muss erlernbar und bei typischen Geschwindigkeiten rechtzeitig wahrnehmbar sein. Gefahr darf nicht mit unlesbarer Willkür verwechselt werden.
