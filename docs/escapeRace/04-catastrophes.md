# 04 — Katastrophen, Signale und dynamisches Balancing

## Ausgangsidee

**Unvorhersehbare Katastrophen statt Rubberbanding.** Die vorderen Fahrer treffen ein Ereignis zuerst und haben wenig Vorlaufzeit; Nachfolgende können Spuren sehen, besser reagieren oder von neu entstandenen Routen profitieren. **Aber:** manchmal schafft der Führende es über eine Brücke vor deren Einsturz und die Verfolger müssen umfahren. Das Balancing soll **situativ, plausibel und nicht garantiert** sein.

Katastrophen sind gleichzeitig Gefahren, Hindernisse, neue Routen, fahrbare Flächen und Werkzeuge für Experten. Spieler dürfen sich nicht dauerhaft durch absichtliches Zurückfallen Vorteile erkaufen können.

## Eventphasen

1. **Vorzeichen:** spezifische, erlernbare Signale (Geräusch, Bewegung, Wasser, Risse, Schatten, Licht, Vibration).
2. **Ausbruch:** räumlicher/zeitlicher Trigger; Unmittelbarkeit und Möglichkeit zur Reaktion.
3. **Aktive Gefahr:** laufende Bedrohung, die Ausweichen, Geschick und Entscheidungen verlangt.
4. **Nachwirkung:** zerstörte Straße, offene Lücke, Trümmer als Rampe, veränderte Zugänge oder andere Hindernisse.

**Ungewiss** bleibt **wann und wo** ein Event beginnt, nicht seine grundlegende Sprache. Hohe Geschwindigkeit muss auf lesbare Warnzeiten, Kameraperspektive und Audiohinweise abgestimmt sein.

## Beispiele

| Katastrophe | Sofortige Gefahr | Möglichkeit / Nachwirkung |
|---|---|---|
| **Hai aus einem Gulli** | Anspringen/Beißen, Kollision, Ablenkung | Öffnung, veränderte Fahrbahn, ggf. Hai als kurioser Impulsgeber |
| **Zombiehorde hinter Kurve** | Zunächst Abbremsen und Blockieren; bei zu langem Verweilen Tod | Andere Route, hindurchdriften, Umfahren |
| **Umstürzender Wolkenkratzer** | Trümmer, Kollisionsgefahr | Fallende Fassade als Wallride, spätere Trümmerrampe |
| **Zusammenbrechende Brücke** | Abgrund, Sperrung | Früh genug hinüber oder neue Umwege/Sprungpfade |
| **Erdbeben** | Straßenspalten, neue Höhenunterschiede | Unterirdischer Durchgang, Sprung-/Wallride-Stellen |
| **Tsunami / Flut** | Überrollen/Abdrängen | Treibende Objekte, Wellenimpulse, geänderte Routen |
| **Alien-/Monsterangriff** | Trampeln, Tentakel, zerstörte Wege | Mobile/temporäre Fahrflächen |
| **Vulkanausbruch** | Lava, Trümmer, Sichtbehinderung | Neu geformte und riskante Strecken |

Beispiele sollen abwechslungsreiche Szenarien illustrieren, nicht alle in den MVP.

### Hai-Beispiel

Ankündigung: Deckel klappert und hebt sich, Wasser schießt hoch, typischer Sound. Ausbruch: Hai schießt aus dem Gulli; Gefahr: Sprung und Schnappen; Nachwirkung: offener Gulli, beschädigte Straße, womöglich Fahrzeuge in neuer Position. Im Optimalfall kann ein Meisterfahrer den Impuls sogar für einen Trick verwenden.

## Catastrophe Director (Designvorschlag)

Das System verfolgt unter anderem:

- Positionen, Abstände, Geschwindigkeiten, Fahrtrichtungen, erreichbare Routen.
- Bereits ausgelöste Ereignisse, Cooldowns und persistent veränderte Geometrie.
- Modus (Rennen vs. CTF vs. Verfolgung etc.), Zeitpunkt/Phase und vorhandene Gefahren.
- Sichtbarkeit, Warnzeit, Reaktionsfenster und vorhandene Ausweichoptionen.

Aus einem Pool **valider Ereignisse** wählt es Ereignisart, Ort und Zeitpunkt. Es darf eine auseinandergezogene Gruppe dynamischer zusammenführen, sollte aber die Leistung des Führenden nie neutralisieren oder den Sieg durch versteckte Bremsen erzwingen.

**Director-Leitplanken:**

- Möglichst keine garantierten Treffer, unausweichliche Soforttode oder völlig ungelesenen Überraschungen.
- Kein gezieltes Bestrafen immer desselben Fahrers; Verteilung über Zeit und Raum.
- Keine deterministische „Führender verliert immer“-Logik.
- Ausnutzen durch freiwilliges Zurückfallen prüfen.
- Ereignisse dürfen auch Führenden *belohnen*; die Welt handelt nicht zwangsläufig gegen Platz 1.
- Modusabhängige Fairness: in CTF ist Flucht/Abfangen anders zu balancieren als in Last Man Standing.
- Katastrophen verändern **Möglichkeiten**, nicht heimlich die maximalen Fahrzeugwerte.

## Beispiel: drei Fahrer und ein Gebäude

Fahrer A sieht die Fassade kippen und kann riskant den noch bewegten Teil als Fluchtweg nutzen. Fahrer B erkennt die Situation früher und fährt außen herum. Fahrer C erreicht später die entstandene Trümmerrampe. Gleiche Katastrophe, andere Herausforderung und anderer Vorteil.

## Offene Implementierungsfragen

- Vorausberechnete Event-Szenarien vs. physikalisch freies Zerstörungsmodell; hybride Lösung?
- Was ist die minimale Warnzeit bei hohen Geschwindigkeiten?
- Wie erkennt Director „faire“ und erreichbare Wege ohne enorme Simulation?
- Wie viel Zerstörung bleibt dauerhaft pro Match?
- Replays/Netzwerksynchronisation bei zufälligen Event-Triggern.
- Wie werden PvP-Modi vor gezieltem Katastrophen-Farming geschützt?
