# Technische Einordnung, erster Prototyp und offene Fragen

## Ein gemeinsames fachliches Modell (Empfehlung)

Welt, Gebäude, Produktionsstätten, NPC-Angestellte, Helden, Ressourcen, Inventare, Quests, Monsterregionen und Bosse sollten als fachliche Objekte bzw. Regeln modelliert werden – möglichst unabhängig von der konkreten grafischen Perspektive.

Zwei unterschiedliche Simulationsdetailgrade sind denkbar:
- **Wirtschaftsansicht:** Abstrahierte Abläufe, Handel, autonome Entscheidungen und Produktionssimulation.
- **Begehbare Heldenansicht:** Konkret bewegte Figuren, Echtzeitkämpfe, Interaktionen, Animationen und bei Multiplayer synchronisierte Zustände.

Wichtig: Eine Wirtschaftssimulation stellt nicht automatisch alle Bausteine für ein Action-MMORPG bereit. Bewegung, Kampf, Kamera, Physik, Netzwerkbetrieb und Synchronisation sind separate große Entwicklungsaufgaben.

Der mögliche MMORPG-Modus sollte die Modellierung früh beeinflussen, aber die erste Implementierung **nicht** dominieren.

## Kleinster sinnvoller Prototyp (Empfehlung, noch kein Beschluss)

Eine kleine Karte mit:
- einer Warenart (Heiltrank) und Rohstoff (Essenz roter Blobs);
- einem einfachen Laden/Händler und Questgeber;
- einer kleinen Population roter Blobs inklusive Wiederkehr;
- etwa drei eigenständig entscheidenden Helden;
- Auftrag mit variabler Eggspi-/Geldbelohnung;
- Produktion, Verkauf, Inventar- und Geldfluss.

**Testfrage:** Kann der Spieler allein durch Quest- und Preisgestaltung zuverlässig genug Ressourcen beschaffen, Heiltränke herstellen und verkaufen, während Helden frei entscheiden? Entstehen daraus interessante Entscheidungen und unerwartete Situationen?

Danach mögliche Erweiterungsfolge: mehrere Ressourcen → Ausrüstung → Monsterzucht → Personal → Städte → Dungeons → besondere Bosse → Sandbox → begehbare Welt.

## Designprinzipien zur Machbarkeit

- **Erst wirtschaftlich interessant**, dann aufwendiger.
- Systemische Wechselwirkungen vor handgeschriebenen Geschichten.
- Nicht sämtliche Figuren benötigen tiefe Lebenssimulation; MMORPG-artige Ziele genügen zunächst.
- Simulationsumfang, genaue Weltgröße, Performance und Wegefindung schrittweise messen.
- Ein Sandbox-Schalter für unbegrenzte Ressourcen sollte möglichst dieselbe Simulationslogik weiterverwenden.
- Humor über Betriebsabläufe, Eigenheiten und Animationen statt ausschließlich durch Skripte.

## Fragenkatalog

### Wirtschaft
- Wie entstehen Preise, Einnahmen, Kosten und Gold?
- Was bedeutet unbegrenztes Eggspi wirtschaftlich, wie wird es mit Levelprogression balanciert?
- Wann und warum kaufen Helden Ausrüstung, Heiltränke und Dienstleistungen?
- Welche Rohstoffverbräuche, Transport- und Lagermechaniken gibt es?

### Helden und Personal
- Welche minimalen Entscheidungsparameter machen Helden glaubwürdig autonom?
- Wie werden Gruppen und Raid-Teilnahmen gebildet?
- Welche Arbeitskräfte sind normale NPC-Angestellte, welche Monster und welche Stars?
- Welche Folgen hat die Abwerbung durch externe, nicht sichtbar auftretende Unternehmen?

### Monstergebiete
- Wie genau gelingt der Schritt von ursprünglicher Wildnis zu RPG-Inc.-Gebiet?
- Wie funktioniert Respawn, und wie werden die Kosten abgebildet?
- Welche Monster werden gezüchtet, welche engagiert?
- Wie frei können Dungeons, Bosskämpfe und Loot gestaltet werden?

### Modi und Community
- Welche Parameter lassen sich beim Publizieren einfrieren?
- Wird veröffentlichter Zustand versioniert oder später aktualisiert?
- Wie groß sind Zielpopulation, regionale Kontingente und Vorrangregeln für Menschen?
- Wie viel Action-RPG-Kampf und Multiplayertechnik ist nötig, bevor „Betreten“ Spaß macht?
- Wie wird eine kreative Sandbox-Welt ohne Wirtschaftszwang sinnvoll veröffentlicht?

## Bewusst nicht entschieden

Engine, Sprache, Netzwerkarchitektur, Renderer, Geschäftsmodell des realen Spiels, konkrete Weltgröße, Serverbetrieb, Persistenzschema, Modding-Schnittstellen und genaue Progressionskurven. Diese Entscheidungen sollten nicht voreilig aus der langfristigen MMO-Vision abgeleitet werden.
