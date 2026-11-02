# Prototyp: Hypothesen, Prioritäten, offene Fragen

## Ziel

**Zuerst prüfen, ob sich das Spiel tatsächlich gut anfühlt.** Noch keine Produktionszusage, keine festgelegte Engine, kein vollständiger Featureumfang. Primäre Risikofaktoren: Controller-Ergonomie, mentaler Überblick über Slots, Animation/Flow und dynamisches Waffenmanagement unter Zeitdruck.

## Vorschlag für einen minimalen Vertical-Slice-Prototyp

### Stufe A – Slotgefühl

- Eine einfache Figur und Testgegner/Trainingsdummy.
- Sechs immer direkt adressierbare Slots.
- HUD: 2×3, gleiche Reihenfolge □ △ ○ in beiden Zeilen, gehaltenes L1 als Modifier.
- Drei exemplarische Elemente; freie und leere Plätze.
- Ziehen/Hieb/Einstecken ohne künstlerischen Feinschliff.
- Letzter verwendeter Slot ist für die nächste Schwertaktion gesperrt.

**Frage:** Verinnerlicht man diese Eingabeform, oder verhindert das Mapping einen flüssigen Kampf?

### Stufe B – Verteidigung und Elemente

- Gehaltener Blockmodifier + Schwertslot.
- Eingehender Wasserangriff: Eisblock → temporäres Hindernis, Feuerblock → Dampfeffekt.
- Kurze Angriffsketten und einfache regelbasierte Elementreaktionen.

**Frage:** Fühlt sich das als durchgehendes System an, statt als isolierte Spezialeffekte?

### Stufe C – Physische Waffenwirtschaft

- Klinge werfen, in Wand/Boden stecken lassen, Slot leeren.
- Während Bewegung/Ausweichen Klinge aufnehmen.
- Belegung ändert HUD und Wirkung des Slots sofort.
- Ein improvisierter Eiszapfen mit begrenzter Nutzung.

**Frage:** Ist Umrüstung mitten im Kampf spannend oder wirkt sie hakelig?

### Stufe D – Elementare Fortbewegung

- Windklinge löst einen Midair-Jump aus.
- Test mit zwei abwechselnd verwendeten Windklingen.
- Prüfen, ob absichtlich unbegrenzte Sprünge funktionieren dürfen, ob sie Spaß machen und welche Encounter-Designfolgen entstehen.

### Stufe E – Mini-Boss

- Mindestens zwei Zustände mit unterschiedlicher Elementanforderung.
- Mehr benötigte Waffen im Verlauf als gleichzeitig tragbare Plätze.
- Umgebung stellt zwingend erforderliche Klingen wieder zur Verfügung.
- Testfälle für verlorene Klingen und nicht mehr lösbare Situationen.

## Priorisierte offene Entscheidungen

| Thema | Aktuelle Richtung | Experiment |
|---|---|---|
| Slotzahl | Sechs | Erst nach Ergonomietests über 8/10/12 nachdenken |
| Direkt-Wiederholung | Verboten | Gilt einheitlich für Angriff, Block, Wurf, Bewegung? |
| Wiederholungssperre | Sequenzbasiert | Prüfen, ob Warten keine Freigabe bewirken soll |
| HUD | 2×3, □△○ pro Reihe | Lesbarkeit bei häufigem Waffenwechsel |
| Schwertanimationen | Schnell, ineinander übergehend | Eingabepuffer, Interrupts, glaubwürdiger Flow |
| Block | Gehaltener Modifier + Slot | Handhaltung und Reaktionstempo |
| Special-Moves | Einfache Richtungsfolgen + Slot | Erkennung ohne Fehleingaben |
| Aufheben | Während Bewegung/Ausweichen | Zielauswahl und welcher freie Slot belegt wird |
| Elemente | Wenige Regeln, systemische Effekte | Kombinatorik, Orientierung, Balance |
| Wind-Doppelsprung | Eventuell unendlich | Zuerst erlauben und Spielwirkung beobachten |
| Unique-Klingen | Optional | Garantiert wiederbeschaffbar |
| Boss-Softlocks | Niemals dauerhaft unlösbar | Regenerierbare Ressourcen, Validierung |
| Story-Enthüllung | Nicht festgelegt | Wann/ob Ryu Shirakaba erkennt |

## Explizit nicht als feste Zusagen behandeln

- Konkrete Schwertarten pro Slot, spezielles Komborezept oder fixe Elementliste.
- Konkretes Blocktiming, exakte Eingabefolgen für Würfe, einzelne Bossphasen.
- Schmied als tatsächlich implementierter Unique-Recovery-Dienst.
- Dauerhafte Einschränkung unbegrenzter Windbewegung.
- Ein bestimmtes Ende oder der Zeitpunkt der Enthüllung von Shirakaba.

## Definition eines gelungenen Gameplay-Beweises

Ein Testspieler kann nach einer Eingewöhnung:
1. die sechs Plätze ohne Denkpause ansteuern;
2. eine beabsichtigte Elementfolge wiederholbar auslösen;
3. einen Wasserangriff absichtlich mit Eis oder Feuer blocken;
4. ein Schwert werfen, während des Ausweichens eine andere Klinge einsammeln und mit der geänderten Slotbelegung weiterkämpfen;
5. eine kurze Begegnung durch spontanes Umrüsten und elementare Reaktionen gewinnen.

Erst dann ist die zentrale Behauptung gestützt: **6 Blades lebt von schnellem, bewusstem Schwertmanagement, nicht bloß von spektakulären Animationen.**
