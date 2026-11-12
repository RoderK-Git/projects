# Roadmap, offene Fragen und Prüfpunkte

## Prioritäten

### Phase 0 – Vanilla-Daten kennenlernen

Mit SSEEdit/xEdit bzw. Creation Kit zunächst einige aussagekräftige NPCs untersuchen (z. B. Ysolda, Aela, Braith, Talen-Jei, Keerava, Dunmer aus Windhelm, Mitglieder der Grau-Mähnen/Kampf-Geborenen):
- Factions und Rank, insbesondere Familien/Job/Politik
- Relationships
- Packages, Arbeitszeiten, Wohnorte
- AI Data
- Quests, Dialogbedingungen und vorhandene Themen
- Ownership und wohnungsbezogene Objekte
- tatsächliche Religions-/Kulturinformationen in Records versus bloßen Dialogtexten

**Ziel:** Vorhandenes nutzen, bevor neue Attribute definiert werden.

### Phase 1 – Kleiner, überprüfbarer Prototyp

- Ein bis zwei Figuren, bevorzugt Ysolda.
- Wenige authored Themen auf Basis von existierenden Quest-/Weltbedingungen.
- Minimaler persistenter Wissensstand: „zuletzt mitgeteilt“.
- Einfache situationsabhängige Gesprächsoptionen, kein vollständiges Menü-Replacement.
- Ein optionaler, kurzer Bark mit nachfolgendem Dialog.
- Gesprächsauswahl begrenzen, ohne Vanilla-Topics zu beeinflussen.

### Phase 2 – Gesprächskontinuität

- Wiedersehen, offener Gesprächsfaden, bis zu drei gestaffelte Nachfragen.
- Zeit-, Begegnungs- und situationsbasierte Regeltypen.
- Priorisierte gewichtete Auswahl und stabile Angebotsliste.
- Regionale, bei Bedarf aufgelöste Ereignisse.

### Phase 3 – NPC-Lebensbezug

- Berufliche Anliegen und optionale Beschaffung (Ysolda).
- Wissen durch gemeinsames Erleben (Braith als Integrationsbeispiel).
- Ruhephasenreflexion und unterschiedliche Perspektiven.
- Besserer Umgang mit Todesfällen/Trauer (nur soweit kompatibel).

### Phase 3b – Bedarfsgebundene Gefälligkeiten

- Questbezogene Beschaffungsaufträge an passende NPCs delegieren, mit Wartezeit statt Sofortbelohnung.
- Beziehung, Dankbarkeit und aktuelle Beanspruchung getrennt berücksichtigen.
- Siehe [Gefälligkeiten und soziale Erwartungen](favors-and-social-expectations.md).

### Phase 4 – Sozialer und kultureller Tiefgang

- Individuelle Vorbehalte, Politik, Religion, Herkunft.
- Kulturell unterschiedliche Werbung und Hochzeitstraditionen.
- Freiwillige, gegenseitige Beziehungsentwicklung ohne generelles Freischalten.
- Gerüchte, Lügen, Widersprüche und Quellenvertrauen.

### Phase 4b – Soziales Geflecht (optionale spätere Ausbaustufe)

- Erwartungen und Zusagen als eigenständige soziale Anlässe.
- Wissen über Hilfen und Beziehungen zwischen Dritten, einschließlich Beobachtungen und Gerüchten.
- Individuelle Bewertungen: Eifersucht, Gleichgültigkeit, Freude oder Missverständnis.
- Keine automatische Berechtigung auf Aufmerksamkeit oder Gefälligkeiten.

### Phase 5 – Umgebung und Hausrat

- Bücher, Gegenstände, Besitz und Wohnumgebung als Kontext.
- Optional veränderte Einrichtung bzw. tatsächlich betrachtete Gegenstände.

## Offene Entwurfsfragen

1. **Questdefinition:** Wie werden verzweigte Stages sauber auf inhaltliche Meilensteine abgebildet?
2. **Speicher:** Welche Kombination aus Papyrus-Variablen, Quest-Aliasen, SKSE-Persistenz oder externer Datenstruktur ist für NPC × Thema praktikabel?
3. **Dialoglimit:** Wie viele Zusatzoptionen verträgt die Vanilla-UI, und wie lassen sich Topics während eines Gesprächs stabilisieren?
4. **Verfügbarkeit:** Sollen hervorgehobene Themen dauerhaft angeboten werden, bis sie beantwortet sind?
5. **Ereignisverbreitung:** Wann und wie häufig dürfen NPCs nach einem regionalen Ereignis erneut Kenntnis erwerben? Wie verhindern wir „Wissen verschwindet“?
6. **Selbst erlebt:** Wie erkennt eine Begleiterfigur zuverlässig, ob sie bei einem konkreten Meilenstein tatsächlich dabei war?
7. **Lügen und Gerüchte:** Wie viel Quellen- und Widerspruchsmodell ist sinnvoll, ohne den Ansatz aufzublähen?
8. **Kulturelle Merkmale:** Welche NPCs haben loregestützte Traditionen? Wie unterscheiden wir Religion, Herkunft, Kultur und Rasse?
9. **Trauer:** Welche Vanilla-Reaktionen haben permanente Conditions/Packages und wie lassen sie sich additiv verbessern?
10. **Hausrat:** Wie erkennt die Mod Besitz/Betrachtung von Büchern zuverlässig und effizient?
11. **Sprachausgabe:** Wie weit ist generischer Content ohne hochwertige Vertonung attraktiv?
12. **Kompatibilität:** Wie interagiert die Mod mit SDA, bestehenden Follower-, Ehe- und Dialogmods?
13. **SKSE-Events:** Sind die im Konzept genannten Quest-Stage-Listener aktuell verfügbar und zuverlässig, und wann ist ein Listener nötig?
14. **Spielerfreiheit:** Welche Aussageformen sollen später verfügbar sein (offen, verschweigen, lügen, scherzen), ohne künstliche Pflichtentscheidungen?

15. **Gefälligkeiten:** Wie lassen sich tatsächliche Questbedarfe, Auftragsdauer und Kapazitäten sinnvoll zuordnen?
16. **Dankbarkeit:** Wie unterscheiden wir vergangene Hilfe von wiederholter Beanspruchung und dauerhafter Freundschaft?
17. **Soziales Geflecht:** Wie erfahren NPCs voneinander, ohne dass jede Beziehung dauerhaft simuliert werden muss?

## Beschlossen vs. denkbar

**Relativ klarer Konsens aus dem Gespräch:**
- Name: **RelativeRelations** (Arbeitstitel), optionaler Untertitel *Contextual NPC Interactions*.
- Generisches, unabhängiges Framework; What a Braith nutzt es mit Spezialcontent.
- Vorhandene Skyrim-Systeme auswerten; nicht unnötig neue Systeme aufbauen.
- Keine Manipulation fremder Quests; Quest-/Regionsabfragen nach Bedarf.
- NPC-Gedächtnis statt Spieler-Gedächtnis; Spieler kontrolliert seine Aussagen.
- NPC-Initiative als unverbindlicher Bark ohne aufgezwungenen Dialog.
- Themenauswahl beim Gesprächsbeginn, randomisiert und begrenzt.
- Loretreue, Individualität, Freiwilligkeit als Designprinzipien.

**Konzeptionell erwogen, noch nicht verbindlich:**
- Exakte Gewichtungen, Zustandsmodelle und Zahlenlimits.
- Beschaffungslogik, Trauerentwicklung, romantische Subsysteme.
- Gerüchte-/Lügenausbreitung und regionale Wissenswahrscheinlichkeiten.
- Bücher-/Besitzinteraktionen.
- Die konkrete Implementierung mit Papyrus, SKSE oder weiteren Plugins.

## Qualitätsmaßstäbe

- Fühlt sich eine Figur nach mehreren Begegnungen mehr wie dieselbe Person an?
- Reagiert sie sinnvoll auf bekannte, tatsächlich stattgefundene Ereignisse?
- Wird sie bei fehlendem Gesprächsbedarf auch einfach still?
- Kann der Spieler bewusst preisgeben, zurückhalten oder (später) verfälschen?
- Respektiert die Mod Tagesabläufe, NPC-Autonomie und Grenzen?
- Bleibt sie ressourcenschonend, additiv und modkompatibel?
- Gibt es einen erkennbaren Mehrwert, bevor neue Mechaniken hinzukommen?
