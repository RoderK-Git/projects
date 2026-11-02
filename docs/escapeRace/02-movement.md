# 02 — Fahrzeugbewegung, Steuerung und Momentum

## Ziel

**Easy to learn, hard to master.** Einsteiger können beschleunigen, lenken, bremsen und driften. Fortgeschrittene setzen dieselben Grundwerkzeuge in 3D ein, bis sie sich an jeder Oberfläche wie zu Hause fühlen.

Die Steuerung soll nach Möglichkeit **jederzeit** Einfluss erlauben — selbst frei fliegend, auf dem Dach oder seitlich auf zwei Rädern. Boostersysteme dürfen Bewegungen ermöglichen, die real nicht funktionieren.

## Bewegungswerkzeuge

| Werkzeug | Spielerischer Nutzen | Anspruch |
|---|---|---|
| Beschleunigen/Bremsen/Lenken | Einfach zugängliches Fahren | Präzises Tempo und Position |
| Drift / harter Turn | Richtungswechsel, Ausrichten, enge Kurven | Kontrollierter Winkel und Speed-Erhalt |
| Rückwärtsfahrt | Taktik, überraschende Routen | Vollwertige Technik, nicht nur Notbehelf |
| Sprung/Absprung | Flächen wechseln, Hindernisse überfliegen | Timing, Flugbahn |
| Roll/Pitch/Yaw in der Luft | Räder auf neue Kontaktfläche ausrichten | Eigenständige Rotationskontrolle statt Auto-Trick |
| Seitenräder-Fahrt | Enge Lücken, Wandwechsel vorbereiten | Gezielt kippen und wieder stabilisieren |
| Wallride / vertikale Fassadenfahrt | Alternative Fahrbahn und Höhengewinn | Winkel, Boost, Kontakt, Orientierung |
| Deckenfahrt | Oberflächen vollständig räumlich nutzen | Übergänge kontrollieren |
| Boosterimpulse | Luftkorrektur, Abwärtsbeschleunigung, Seitenversatz, Absprung | Dosierung, Timing, Kombinierbarkeit |
| Kollisionsrettung | Sich aus Fehlversuchen fangen | Kontrolle nach kleinem oder größerem Patzer |

### Beispiele für organische Kombinationen

- **Wallride → Flip → Wallride** an der gegenüberliegenden Wand; möglichst nahtloser Übergang.
- **Vertikaler Walljump:** Fassade hochfahren; zur Gegenfassade abspringen und dort erneut aufwärtsfahren; bei guter Ausführung mehrfach möglich.
- **Sidewheel → schmale Lücke → Wallride** aus einem einzigen Bewegungsfluss.
- **Drift → Rückwärtsfahrt → Rampensprung → Abwärtsboost → Landung.**
- **Wand → Decke → Wand** ohne geskriptete Animationen.
- **Abflug → Roll → Kontakt auf fahrender/fallender Oberfläche** (siehe [03-surfaces](03-surfaces.md)).

## Booster als allgemeine Impulsgeber

**Gesprächskern:** Booster erlauben Luftkontrolle, insbesondere auch **rasch nach unten**; sie helfen beim Wandkontakt, Flächenwechsel und beim außergewöhnlich langen vertikalen Fahren.

**Mögliche Richtungen (Entwurfsvarianten, keine festgelegte Hardware):**

- Nach vorne: Vortrieb/Absprung.
- Seitlich: Lateralversatz, Wandwechsel und präzise Korrektur.
- Nach oben: Sprünge/Höhe.
- Nach unten: gezielte schnelle Landung oder Haftung an einer Oberfläche.
- Rotatorisch: Roll-/Pitch-/Yaw-Korrektur.

Nicht fünf eigene Knöpfe voraussetzen: **Kontext und Richtungseingabe** können einen kleinen, gut erlernbaren Satz von Controls bilden. Kontextabhängigkeit muss stabil und verständlich sein.

## Fahr-/Flugmodell

Vorgeschlagene Trennung:

- **Position und Bewegung:** lineare Geschwindigkeit, Fahrtrichtung, beabsichtigter Impuls.
- **Orientierung:** Fahrzeugrotation unabhängig von Flugbahn steuerbar.
- **Oberflächenbezug:** Orientierung und Grip relativ zur gerade befahrenen Fläche.
- **Kamera:** unabhängig von der Fahrzeugrotation; Details in [06-feedback](06-feedback.md).

Keine harten, unüberwindbaren Zustandsgrenzen zwischen Straße, Wand, Decke und freiem Flug. Die Übergänge müssen sich natürlich anfühlen, trotz bewusst erfundener Kräfte.

### Rechtwinklige Architektur

Städte haben harte 90°-Kanten. Ein adaptives Kontakt-/Adhäsionsmodell kann bei geeigneter Ausrichtung, Geschwindigkeit und Eingabe einen **weichen Übergang Boden → Wand** oder **Wand → Decke** ermöglichen. Der Spieler veranlasst und steuert das Manöver; das System verhindert bloß physikalisch unproduktives Hängenbleiben.

### Senkrecht die Wand hoch

Explizit gewünscht: **für eine Weile** senkrecht fahren können. Ob Dauer aus Geschwindigkeit, Boosterenergie, Untergrund, Schwerkraftregeln oder mehreren Faktoren folgt, ist noch zu testen; keine frühzeitige, starre Begrenzung festlegen.

## Präzision und Momentum

**Gesprächsentscheidung:** Exakte Manöver **erhalten oder erhöhen Geschwindigkeit**. Kleine Patzer bremsen **kurz**. Grobe Fehler bremsen stärker, verursachen Schaden und sind möglichst rettbar.

| Qualität | Bewegungsfolge | Akustik |
|---|---|---|
| Perfekt | Tempo bleibt, ggf. Bonus / nützlicher Oberflächenimpuls | Weich, leise, fast schwerelos |
| Sauber | Geringe/keine Tempoeinbuße | Dezenter Kontakt |
| Kleiner Patzer | Kurze Tempoeinbuße | Rumpeln, Schleifen |
| Grober Patzer | Starkes Bremsen, Abweichung, optischer Schaden | Scheppern, harte Impulse |
| Misslungen | Sturz/Crash; Recovery ggf. möglich | Chaotische Kollision |

**Technischer Vorschlag:** kontinuierliche Gütefunktion statt ausschließlich diskreter Trick-Kategorien. Parameter etwa Kontaktwinkel, Relativbewegung zur Oberfläche, Ausrichtung, Aufsetzpunkt und Korrektureingaben. Bewegungsresultat, Sound und sichtbare Reaktion sollen denselben Qualitätswert widerspiegeln.

### Flow statt bloßer Score

Saubere Bewegung belohnt den Spieler in allen Modi direkt mit Fortschritt, Speed, Wegvorteil und einem angenehmen Gefühl. Optional später Trickscore/Style-Modus, aber nicht als Ersatz für das Skillmodell.

**Offen:** Die Boni vollständig aus Oberflächen-/Impulsübertragung berechnen oder eine kleine, transparente Flow-Hilfe hinzufügen? Hard-Cap vs. abnehmende Geschwindigkeitsboni vs. keine künstliche Grenze? Prototypisch testen. Tempo darf spektakulär hoch werden, ohne Reaktionsfähigkeit und Lesbarkeit auszuschalten.

## Steuerungsprototyp

**Nur als Ansatz, nicht beschlossen:** klassische Beschleunigungs-/Bremstrigger; linker Stick lenkt; rechter Stick bzw. kontextuelle Schultertasten regeln Luftlage/Boost. Muss zusammen mit Kamera und Flächenwechsel experimentell optimiert werden. Wichtig ist einfache Grundsteuerung bei enormem Expertenpotenzial.
