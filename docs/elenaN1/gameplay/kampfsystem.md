# Kampfsystem – taktische Martial Arts (Konzept / Prototyp)

**Stand:** 27.10.2026 · **Status:** Designrichtung zum Ausprobieren, keine finalisierte Mechanik.

## Leitbild
- 2.5D-Präsentation, im Kampf zunächst **eine echte 2D-Bewegungsebene**, ähnlich frühen *Street Fighter*-Spielen: Übersicht und Steuerbarkeit vor räumlicher Komplexität. Dreidimensionale Choreografie bleibt möglich.
- Stark auf Martial Arts ausgerichtet, aber **kein komplexes Combo-Beat-'em-up** und kein stumpfes Lebenspunkte-Herunterprügeln.
- **Jeder Kampf soll taktische Entscheidungen erfordern**, auch wenn Gegner optisch identisch sind.
- Der Spieler wählt **Aktion, Ziel/Richtung und Gewaltabsicht**; Elena wählt die passende **Choreografie**, nicht eigenmächtig die Move-Kategorie.
- Kernformel: **Der Spieler kämpft nicht mit Elenas Reflexen, sondern trifft Entscheidungen mithilfe ihrer Reflexe.**

## Eingaben und taktischer Kern
Kleines, zunächst hypothetisches Repertoire: **Angreifen, Blocken, Ausweichen, Kontern, Greifen/Überwältigen**, plus Bewegung. Schere-Stein-Papier-artige Wechselwirkungen zwischen Aktionen; nicht zwingend eine starre Farbtabelle. Timing, Distanz, Position, gegnerische Absicht und Finten bestimmen den Erfolg. Farbliche Signale könnten die Sensoranalyse der Shell abbilden, um strategische Entscheidungen auch ohne Fighting-Game-Reflexe zu ermöglichen. Signale dürfen nicht zu unfehlbaren Vorhersagen werden.

**Mehrere Gegner:** Alle dürfen gleichzeitig angreifen; kein künstliches Abwarten. Der Spieler kann eine **Richtung bzw. Bedrohung** mit der Aktion kombinieren (z. B. links + Konter). Positionierung, Ausweichen und Würfe können mehrere gleichzeitige Angriffe entschärfen. Ziel ist eine überschaubare, taktische Mehrgegnermechanik ohne vollständige Arkham-Freeflow-Automatisierung. Eine zusätzliche Tiefenachse ist vorerst **nicht beschlossen**.

## Gegner: parametrisierte Kampffähigkeit
Gleich aussehende Menschen, kybernetische Spezialeinheiten oder Androiden können unterschiedlich gefährlich sein: Wahrnehmung, Reaktion, Bewegungsvermögen, Präzision, Antizipation, Defensive, Aggressivität, Anpassungsfähigkeit und Zusammenarbeit sind mögliche Parameter. Eliteeinheiten können Angriffe koordinieren. Gegnerstärke soll nicht einfach durch mehr Lebenspunkte oder automatische Levelskalierung entstehen.

- **Normale Polizisten/Kriminelle:** Elena ist körperlich haushoch überlegen; sie kann überheblich, lässig oder verspielt reagieren. Die Herausforderung kann im schonenden Umgang liegen.
- **Kybernetisch unterstützte Menschen:** ernsthafte Gegner mit individuellen Stärken und Schwächen.
- **Vollständige Kampfmaschinen:** potenziell überlegen, echte Gefahr für die Shell; Flucht kann sinnvoll sein.
- Die Kräfteverhältnisse sind **weltlogisch**, nicht an Spielstunden angepasst. Spätere alternative Körper verändern Möglichkeiten und Verwundbarkeit, aber möglichst nicht das Grundschema der Steuerung.

## Persönlichkeit, Emotion und Gewalt
Elenas gewachsene Haltung und momentane Stimmung beeinflussen **Ausführung, Körpersprache und Choreografie**:
- Empathische/freundliche Entwicklung: eher kontrollierte, Aikido-artige, nichtletale Techniken.
- Kompromisslose/aggressive Entwicklung: härtere Muay-Thai-artige Techniken, visuelle Referenz Tony-Jaa-Filme.
- Bei unterlegenen Gegnern kann sie spielerisch/überheblich agieren, bei ernster Gefahr konzentriert.
- Der Spieler behält grundsätzlich **volle Kontrolle über Verschonen oder Töten**. Überwältigen und Töten sind unterschiedliche Absichten, nicht nur verschiedene Schadenswerte.
- **Seltene emotionale Ausnahmen:** Bei extremer Wut, etwa unmittelbar nach Tabethas Entführung, könnte Elena aus Affekt auch dann tödlich handeln, wenn der Spieler das nicht beabsichtigt. Solche Kontrollverluste müssen dramaturgisch besonders begründet und sparsam bleiben.

## Wahrnehmung, Zeitlupe und Physik
Drei strikt getrennte Größen:
1. **Wahrnehmungs-/Verarbeitungsgeschwindigkeit:** Wie rasch eine Situation erkannt und analysiert wird.
2. **Reaktionsgeschwindigkeit:** Wie rasch daraus eine Handlung eingeleitet werden kann.
3. **Physische Bewegungsgeschwindigkeit:** Was Aktuatoren, Kraft, Beschleunigung und Trägheit tatsächlich erlauben.

Zeitlupe ist primär eine **Darstellung von Elenas beschleunigter Wahrnehmung und eine Entscheidungshilfe für den Spieler**, kein Verbiegen der Physik. Höhere Gegner können vergleichbare Fähigkeiten besitzen; relative Geschwindigkeiten bestimmen taktische Entscheidungsfenster. Ob die Zeitlupe automatisch, manuell oder gemischt ausgelöst wird, ist offen.

**Physikalische Konsistenz:** Ein schneller denkender Körper fällt nach einem Sprung nicht schneller oder langsamer; ohne äußeren Impuls bleibt seine Flugbahn ballistisch. Auch Masse, Trägheit, Bremsweg, Reichweite und Aktuatorleistung gelten weiter. Schnelle Wahrnehmung garantiert kein erfolgreiches Ausweichen.

### Cinematischer Referenzmoment
Elena wird aus einiger Entfernung von Security gestellt. Ein Sicherheitsmann schießt; sie verschiebt beinahe beiläufig nur ihren Oberkörper aus der Schussbahn. Die Wahrnehmungszeitlupe macht die unspektakulär kleine Bewegung spektakulär. Plausibel ist **Antizipation der Schussabgabe** anhand Haltung, Zielbewegung und Abzugsvorgang statt erst einer bereits fliegenden Kugel auf kürzeste Distanz auszuweichen.

## Vorläufiger Prototyp
1. Zuerst ein **Duell** mit wenigen Aktionen, Richtungs-/Distanzbezug und lesbaren Angriffsabsichten.
2. Danach **zwei bis drei gleichzeitig angreifende Gegner** in derselben 2D-Ebene: Aktion + Richtung, Mehrfachbedrohungen, Positionierung.
3. Geschwindigkeitsparameter und Wahrnehmungszeitlupe hinzufügen; auf faire Entscheidungsfenster achten.
4. Nichtletale/tödliche Absicht und stimmungsabhängige Choreografie getrennt testen.
5. Erst bei Bedarf schmale Tiefenbewegung vergleichen.

**Noch offen:** konkrete Eingabebelegung, Angriffsklassen und Konterbeziehungen, Darstellung der Signale, automatischer/manueller Fokus, Regeln für Affekt-Kontrollverlust, Gegner-Koordination, Schaden/Stabilität/Überwältigung, Kameraführung und Körper-spezifische Animationen.

## Schadensmodell und kampfunabhängige Bedienung (27.10.2026)

**Leitentscheidung:** Keine sichtbaren oder bloß unsichtbar herunterzuprügelnden Lebensbalken als Kampfkern. Gegner werden strategisch außer Gefecht gesetzt (z. B. Entwaffnung, Fixierung, Bewusstlosigkeit, Ausfall entscheidender Technik); Schwachstellen und Situation statt Damage-per-Second. Die genaue technische Abbildung bleibt offen.

**Elenas Schäden sind dauerhaft bis zur Reparatur.** Ein kybernetischer Körper regeneriert nicht biologisch: beschädigte Motoren, zerstörte Gelenke oder abgetrennte Gliedmaßen bleiben beschädigt. Reparaturen sind erzählerisch unkompliziert, etwa per Zeitblende oder beiläufig während eines Gesprächs mit einem Ingenieur wie Kensuke. Keine Reparatur-Minispiele, Materialwirtschaft oder erforderliche technische Expertise Elenas; allenfalls rudimentäres Verständnis.

**Gameplay-Kontinuität trotz Beschädigung:** Der Spieler verwendet weiterhin dieselben Kampfaktionen, Richtungs- und Absichtseingaben. Schaden verändert **vor allem die Choreografie und visuelle Darstellung**, nicht das grundlegende Moveset, die Steuerung oder den taktischen Regelkern. Elena findet eigenständig eine zum verbliebenen Körper passende Ausführung. Ein Angriff kann unbeschädigt als Tritt, mit fehlenden Gliedmaßen als akrobatischer Abstoß und Schlag realisiert werden. Keine kleinteilige Simulation einzelner Aktuatoren als Pflicht für den Spieler. Schwere Schäden können letztlich Kampfunfähigkeit und narrative Folgen bewirken; die genaue Schwelle ist noch zu definieren.

**Referenz:** Alitas Kampf gegen Grewcica: selbst auf einen verbliebenen Arm reduziert, balanciert sie darauf, stößt sich ab und trifft den Gegner am Auge. Ähnlich spektakuläre, schadensabhängige Bosskampf-Choreografien sind erwünscht, aber **nicht als obligatorische geskriptete Verletzung**: Unterschiedliche Spielerleistungen erzeugen unterschiedliche Kampfverläufe und Inszenierungen. Schaden soll selten und bedeutsam bleiben, ohne den Spielfluss mit Strafmechaniken zu belasten.

**Gesundheitsanzeige durch den Körper:** Zunehmende Beschädigung ist an fehlenden oder defekten Gliedmaßen, Körperhaltung und zunehmend improvisierter Bewegung unmittelbar ablesbar; kein klassischer Gesundheitsbalken nötig. Eine interne Zustandsrepräsentation ist möglich, darf aber nicht zum bloßen verdeckten HP-Balken verkommen. Körpervertrautheit beeinflusst Souveränität, Schäden beeinflussen die Art der Ausführung. Beides ändert nicht die Entscheidungshoheit des Spielers über das *Was*.

**HUD-Grundsatz:** Informationen möglichst diegetisch über Welt, Elenas Sensorik, Körper und Wahrnehmung vermitteln; klassisches HUD nur, falls Verständlichkeit sonst nicht erreichbar ist.
