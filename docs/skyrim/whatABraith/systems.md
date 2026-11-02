# Spielmechaniken: Zeit, Ermittlungen und Wahrnehmung

## 1. Persistente Zeit statt wartender Quest
Der Transport von Braith beginnt im normalen Spielzeitfluss. Der Dragonborn muss nicht sofort reagieren, doch die Welt schreitet voran.

**Wichtige Korrektur des Entwurfs:** Früh abfangen, im Herrenhaus nachforschen oder später suchen sind **verschiedene Einstiege in denselben übergreifenden Dämonenreich-Plot**. Es gibt **keinen** vorgesehenen Hauptzweig, in dem die Quest nach einer Karrenrettung vollständig endet.

| Eintritt in die Untersuchung | Ausgangslage | Braiths Handlungsmacht | Spielerfahrung |
|---|---|---|---|
| Sehr früh | Wagen/Transport erreichbar | Erkennt Verdacht, arbeitet freiwillig verdeckt weiter | gemeinsame Detektivgeschichte |
| Mittel | Braith im Herrenhaus | Baut Beziehungen und interne Informationswege auf | parallele offene/verdeckte Ermittlungen |
| Spät | Freundinnen überführt; Braith folgt | Agiert zunächst weitgehend allein | Spurenlesen, Verfolgung, spätes Wiedersehen |

**Designregel:** Zeit soll Folgen schaffen, nicht unbemerkt Inhalte für immer abschneiden. Wie Fristen kommuniziert werden, wann Ereignisse simuliert oder nachgeladen werden und welche Informationen retrospektiv zugänglich bleiben, ist offen.

## 2. Zwei parallele Ermittlungsrollen
**Braith: verdeckt**
- Teilnahme am Kinderalltag, Beobachtung, Beziehungsaufbau, Geheimwege, Flüstern, mögliche verdeckte Übermittlung.
- Ihre Tarnung darf durch das Auftreten des Dragonborn Schaden nehmen.
- Sie ist aktiv und kann ohne Spielerkommando eigenständige Entscheidungen treffen.

**Dragonborn: offen**
- Händler und Personal befragen, Spuren und Zahlungen prüfen, Transporte verfolgen, magische Hinweise untersuchen.
- Gewalt oder Einschüchterung sind denkbar, aber nicht immer klug.
- Überlegtes Vorgehen kann Braith schützen und Zugang zu Informationen eröffnen.

**Zusammenspiel:** Keine bloß dekorative Begleiter-KI. Ermittlungserkenntnisse sollen gegenseitig verwendbar sein; ein übereilter Zugriff kann Konsequenzen haben. Konkrete Informations- und Questflags noch designen.

## 3. Zeitdilatation
Die Dämonensphäre besitzt einen **schnelleren Zeitverlauf**. Die Zeit in der Sphäre ist für Braith real; ihr Körper und ihre Persönlichkeit entwickeln sich weiter.

**Zu definieren:** Verhältnis Skyrim-Zeit : Dämonenzeit; wann Portalversatz beginnt; mögliche Mindest-/Höchstaltersgrenzen; wie Anwesenheitszeit des Dragonborn wirkt; Plausibilität von Mitreisenden; ob mehrere Begegnungsalter tatsächlich umgesetzt werden.

**Emotionaler Effekt:** Dragonborn kann wenige Tage abwesend gewesen sein; Braith hat subjektiv Jahre auf ihn gewartet und ist deshalb zunächst sehr wütend. Ihre Gefühle dürfen nicht mit einer einzigen „Zeit läuft anders“-Dialogzeile weggeerklärt werden.

## 4. Kontextuelle Trauer- und Erinnerungseffekte
Wird die Bindung vor dem Verschwinden eng, kann das Spiel die Wahrnehmung des Dragonborn verändern:
- Er hört manchmal eine bekannte Bemerkung von Braith, obwohl niemand da ist.
- Er sieht sie vielleicht für einen Augenblick an vertrauten Orten.
- Ein Skeever trägt kurz den Namen des gemeinsam dressierten Skeevers, **nur falls es dieses gemeinsame Erlebnis tatsächlich gab**.
- Andere gemeinsame Erlebnisse können andere Wahrnehmungsfetzen auslösen.

Je länger die Verfolgung aufgeschoben wird, desto stärker können solche Eindrücke werden. **Nicht** als plumpes lineares Spuk-Skript: Auslöser sollten Ort, Situation, Erinnerungen und Beziehungsintensität berücksichtigen. Mehrdeutig halten, ob psychologischer Effekt oder übernatürliche Einwirkung.

Datenbedarf: erlebte Szenen, Beziehungsentwicklung, letzter Kontakt, vergangene Zeit, Kontext-Trigger, Intensitätsgrenzen und Schutz vor Wiederholungsnervigkeit.

## 5. Beziehung und Eigenständigkeit
Nicht nur ein Affinitätsbalken. Speichere erinnerbare gemeinsame Ereignisse, Vertrauensbeweise, Streitpunkte, Hilfe für andere Kinder und Konsequenzen.
- Braith kann sich weigern, höflich zu werden, und trotzdem Vertrauen zeigen.
- Sie kann dem Dragonborn widersprechen.
- Die Bindung prägt spätere Wiedersehens-Dialoge und Erinnerungseffekte.
- Braiths Pläne sollen ihrer Situation und ihren Zielen folgen statt unbegründet an Questscripten zu hängen.

## 6. Variantenverwaltung (Designvorschlag)
Persistente Marker z. B. `transport_started`, `transport_intercepted`, `braith_at_manor`, `birch_met`, `friends_selected`, `braith_entered_realm`, `player_entered_realm`, `realm_elapsed`, `shared_skeever_name`, `braith_trust`. Namen sind Vorschläge, **keine** implementierte API.

Die sich unabhängig entwickelnde Welt benötigt robuste Behandlung von Warten, Schnellreise, Spielständen, NPC-Tod und inkompatiblen Questzuständen.
