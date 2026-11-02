# Physische Waffen und Schwertmanagement

## „Schwerter sind Wegwerfware“

Ein zentrales Alleinstellungsmerkmal: **Wegwerfen, Verlieren, Aufheben, Tauschen und Positionieren** von Klingen gehört zum laufenden Kampf. Das Spiel soll Spieler nicht dazu erziehen, ein einziges Lieblingskatana niemals loszulassen.

Ryu hat nur **sechs direkt nutzbare Slots**. Kein weiteres verborgenes Arsenal am Körper, kein Rucksack oder Menü als Ersatzlager. Eine für eine Bosssituation erforderliche zehnte Klinge muss aus der Spielwelt verfügbar sein, nicht aus einem Menü hervorgezaubert werden.

## Waffen sind echte Weltobjekte

Eine Klinge kann:
- in einem Schwertslot stecken;
- im Flug sein;
- im Boden oder einer Wand stecken;
- auf einer Oberfläche liegen;
- aufgenommen, umgesteckt oder erneut geworfen werden;
- bei provisorischen Waffen verbraucht/zerbrochen sein;
- vorübergehend oder dauerhaft unerreichbar sein (mit Schutzmechanismus bei besonderen Waffen).

**Abgelegte/geworfene Klingen verschwinden nicht einfach.** Ihre Position beeinflusst spätere taktische Optionen. Der Spieler kann sie bewusst günstig oder ungünstig platzieren.

## Slotwechsel ohne Menü

1. Ryu schafft einen freien Slot – z. B. durch einen Schwertwurf.
2. Er nähert sich einer erreichbaren Klinge.
3. Er nimmt sie **während der Bewegung oder einer Ausweichbewegung** auf und belegt den freien Platz.
4. Die zugehörige Schwerttaste ruft ab jetzt die neue Klinge auf; das HUD ändert sich unmittelbar.

Noch zu entwerfen: genaue Interaktions-/Slotzuweisung, Animation, Geschwindigkeit und ob der direkte Austausch eines vollen Slots erlaubt ist. Es soll **keine versteckte Inventaroberfläche** geben.

## Improvisierte, temporäre Waffen

Die Umgebung kann selbst Klingen liefern. **Konkretes Kernbeispiel:** Ein großer **Eiszapfen** wird abgebrochen und als improvisiertes, temporäres Eisschwert genutzt. Eine solche Waffe darf zerbrechen, abschmelzen oder nur wenige Aktionen aushalten.

Weitere **Ideen, nicht zugesagt**: Bambusspieß, Bruchstücke von Dämonenwaffen, Lavaklingen, Ritualsplitter. Entscheidend ist die glaubwürdige Klingenform und eine klare zeitlich begrenzte Nutzung.

## Unique-Schwerter

Unique-Schwerter sind **möglich, nicht zwingend**. Falls vorhanden:
- Sie sollen im Kampf grundsätzlich denselben physischen Regeln folgen (werfbar, austauschbar, zurücklassbar).
- **Dauerhaft unerreichbar werden dürfen sie nicht.**
- Dafür ist ein verlässlicher Wiederbeschaffungs-/Recovery-Mechanismus erforderlich.

**Möglicher, nicht festgelegter Ansatz:** verlorene einzigartige Klingen bei einem Schmied wiederherstellen oder später abholen. Der Verlust im aktuellen Bosskampf darf trotzdem reale taktische Folgen haben.

## Mögliche Datenmodell-Kerne für einen Prototyp

```text
Sword:
  id
  element(s)
  unique: bool
  temporary: bool
  durability?      # experimentell
  world_position?
  state: slotted | flying | embedded | grounded | consumed | recovery
  slot_id?          # nur bei slotted

Slot:
  index: 1..6
  sword_id?         # optional leer

CombatState:
  last_used_slot?
```

Invarianten:
- Eine Klinge befindet sich zu einem Zeitpunkt in genau einem Zustand.
- Kein Schwert darf zwei Slots gleichzeitig belegen.
- Gewöhnliche Wurf-/Drop-Aktionen löschen ein Objekt nicht stillschweigend.
- Die letzte notwendige Elementquelle eines verpflichtenden Kampfabschnitts muss langfristig wiederherstellbar sein.
- Unique-Schwerter brauchen eine definierte Rückholroute, wenn reguläre Physik-/Navigationswege scheitern.

Das Datenmodell ist **ein technischer Vorschlag**, keine gewählte Engine-/Implementationsarchitektur.
