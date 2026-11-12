# Gefälligkeiten, Gegenseitigkeit und soziale Erwartungen

> **Status:** Zukunftskonzept. Die bedarfsgebundene Delegation ist ein vergleichsweise früher Kandidat; Eifersucht und Wissen über Beziehungen Dritter sind eine ausdrücklich spätere, optionale Ausbaustufe.

## 1. Bedarfsgebundene Gefälligkeiten

Das Drachenblut kann NPCs um die **Beschaffung konkret benötigter Questgegenstände** bitten, wenn die Aufgabe zu ihren Fähigkeiten, ihrem Alltag und der Beziehung passt. Kein allgemeiner, beliebig wiederholbarer Beschaffungsautomat.

**Beispiel Aela:** Eine aktive Quest verlangt Felle, die noch fehlen. Aela könnte sie auf einer Jagd besorgen. Das dauert womöglich länger, als selbst loszuziehen; der Spieler kann währenddessen andere Dinge tun. Delegation spart eigene Aufmerksamkeit und Wege, nicht zwangsläufig Spielzeit.

**Beispiel Ysolda:** Sie beschafft passende Handelswaren eher gegen Bezahlung, über Kontakte und im Rahmen ihrer Geschäftszeiten. Gleiche Infrastruktur, andere Motivation.

Voraussetzungen für das Angebot:
- tatsächlich bestehender und noch offener Bedarf;
- definierte Zuordnung zwischen Quest-/Aufgabenstand und fehlendem Gegenstand (nicht universell automatisch aus jeder Quest ableitbar);
- plausible Kompetenz und Beschaffungsmöglichkeit des NPCs;
- dessen Bereitschaft und zeitliche Verfügbarkeit;
- keine unpassenden parallelen Aufträge oder unbegrenzte Mengen.

Vereinfachter Ablauf: Anfrage → Annahme/Ablehnung → Wartezeit → Beschaffungsergebnis → Benachrichtigung → Übergabe. Es muss **keine reale Jagd oder Händlerreise simuliert** werden. Ein Auftrag kann fehlschlagen oder länger dauern, wenn das zur Figur und Aufgabe passt; die genaue Mechanik bleibt offen.

## 2. Beziehung, Dankbarkeit und Beanspruchung unterscheiden

Die Rückgabe von **Amrens Familienschwert** kann zunächst hohe Bereitschaft zu einem Gegengefallen erzeugen. Wiederholte Bitten sollen aber nicht unbegrenzt auf derselben Dankesschuld beruhen.

Drei getrennte Größen:
- **Beziehung:** dauerhaftere grundsätzliche Haltung zu einer Person.
- **Dankbarkeit / empfundene Gegenseitigkeit:** Anlass, sich für eine konkrete frühere Hilfe erkenntlich zu zeigen. Die Erinnerung bleibt, auch wenn der gefühlte Ausgleich längst erfolgt ist.
- **Beanspruchung:** kürzlich erbetene oder geleistete Gefälligkeiten, deren Aufwand und Häufigkeit. Sie kann mit der Zeit abklingen.

**Illustrativer Verlauf, keine feste Fünf-Stufen-Regel:**
1. „Nach dem, was du für meine Familie getan hast? Natürlich!“
2. „Sicher, ich helfe dir gern.“
3. „Du hältst mich ganz schön auf Trab.“
4. „Ich habe auch eigene Dinge zu erledigen.“
5. „Langsam sind wir wohl quitt, meinst du nicht?“

Nicht jede Bitte zählt gleich viel. Eine kleine Lieferung ist nicht mit einer gefährlichen Expedition vergleichbar. Eine **abgelehnte Anfrage** verbraucht nicht automatisch einen Gefallen. Ablehnung bedeutet auch nicht zwingend schlechtere Beziehung. Nach aufgebrauchter Dankbarkeit kann Amren weiterhin aus Freundschaft helfen, muss es aber nicht.

Mögliche wechselseitige Entwicklung: Ein NPC, der dem Drachenblut wiederholt geholfen hat, könnte selbst um etwas bitten. Das ist kein einklagbarer Schuldschein, sondern eine sozial plausible Erwartung.

**Leitgedanke:** Vergangene Hilfe schafft Bereitschaft. Wiederholte Inanspruchnahme kann sie erschöpfen. Die Beziehung entscheidet, was danach bleibt.

## 3. Soziale Erwartungen und Eifersucht – spätere Iteration

Hier entsteht aus den bislang überwiegend **dyadischen** Beziehungen (NPC ↔ Drachenblut) ein kleines **soziales Geflecht**. Ein NPC muss erfahren können, dass das Drachenblut jemand anderem hilft, Aufmerksamkeit schenkt oder Zusagen einhält, während eine eigene Erwartung offen ist.

Beispiel: Ysolda wartet auf eine zugesagte Besorgung. Sie erfährt, dass das Drachenblut Amren mehrfach geholfen hat. Je nach Persönlichkeit, Kontext und Beziehung könnte sie anmerken:

> „Für Amren findest du offenbar immer Zeit.“

Das setzt **drei getrennte Bedingungen** voraus:
1. **Erwartung:** eine Zusage, Bitte, Verabredung, erhoffte Aufmerksamkeit oder Verlässlichkeit;
2. **Wahrnehmung:** sie beobachtet die Hilfe, hört von Amren davon oder erfährt ein Gerücht;
3. **Bewertung:** sie empfindet das als Zurücksetzung, freut sich für Amren, ist gleichgültig oder interpretiert die Information falsch.

**Eifersucht ist nicht automatisch romantisch.** Sie kann in Freundschaften, Familien, unter Gefährten oder Geschäftspartnern entstehen. Ein NPC kann die gleiche Lage anders deuten als ein anderer. Eine offene Erwartung ist nicht zwangsläufig ein *berechtigter Anspruch* auf das Drachenblut.

### Anschluss an das vorhandene Wissensmodell

Die schon entworfene Ereignisstruktur lässt sich erweitern:

```text
Akteur → Handlung → Begünstigter → Beobachter/Informationsquelle
Drachenblut → hilft → Amren → Ysolda erfährt davon
```

Das Ereignis selbst und seine **Verbreitung** sind getrennt. Ohne Beobachtung, Mitteilung oder glaubhaftes Gerücht gibt es keine informierte Reaktion. Ob die Nachricht wahr, verzerrt oder veraltet ist, kann später über die vorhandene Wissens-/Gerüchtelogik modelliert werden.

Mögliche, noch nicht verbindliche Daten:
- `expectation`: Wer erwartet was von wem, aus welchem Grund, mit welcher Verbindlichkeit?
- `socialEvent`: Wer tat was für wen, wann und in welchem Kontext?
- `knownBy` / `source`: Wer hat davon erfahren und wie?
- `interpretation`: Was bedeutet es dieser Figur?
- `responseState`: Wurde die Sache bereits angesprochen oder beigelegt?

**Keine globale permanente Überwachung aller NPC-Beziehungen.** Nur ausgewählte, relevante Ereignisse erfassen und bei Gespräch/Begegnung kontextabhängig auswerten. Persistente Wissensentscheidungen verhindern erneutes Auswürfeln.

### Schutz vor Pflichtmanagement

RelativeRelations soll kein System werden, in dem der Spieler fortwährend die Erwartungen aller Bekannten abarbeiten muss. Figuren dürfen enttäuscht, eifersüchtig oder verärgert sein, aber ihre Erwartungen sind **keine automatischen Ansprüche**. Ebenso wichtig wie die Erwartung selbst ist die Persönlichkeit: Wie geht ein NPC mit ihrer Nichterfüllung um? Direkte Aussprache, Gelassenheit, Rückzug, Neid oder Missverständnis sind mögliche Reaktionen.

## 4. Technische und spielerische offene Punkte

- Wie erkennen wir questbezogenen Bedarf robust? Anfangs explizite Quest-/Item-Zuordnungen statt allgemeiner Extraktion.
- Wie werden Teilmengen, Kosten, Verzögerungen, mehrere Anbieter und laufende Aufträge behandelt?
- Wie groß ist ein Gefallen im Verhältnis zu früherer Hilfe? Brauchen wir Werte oder reichen Kategorien?
- Welche Zeitwirkung hat Beanspruchung; wie lange hält Dankbarkeit als Bereitschaft an?
- Welche Erwartungen sind wirklich verbindlich (ausdrückliche Zusage vs. einseitige Hoffnung)?
- Welche sozialen Ereignisse dürfen NPCs voneinander erfahren, und über welche Quellen?
- Wie verhindern wir unpassende, repetitive Vorwürfe und dauerhafte Eifersuchts-Dialoge?
- Wie bleiben die Modelle optional und leichtgewichtig?

## 5. Einordnung

**Früher möglich:** Questbedarf → NPC-Kompetenz/Beziehung → verzögerte Delegation; einfache abnehmende Bereitschaft durch beanspruchte Gefälligkeiten.

**Später, wenn das Wissensmodell trägt:** NPC-übergreifende Informationen, Zusagen, soziale Erwartungen, Eifersucht und Fehlinterpretationen.

Beide Erweiterungen sollen auf den bereits entworfenen Systemen für **NPC-Wissen, Ereignisse, Gesprächsanlässe und Persönlichkeit** aufbauen – nicht als parallele Vollsimulation.
