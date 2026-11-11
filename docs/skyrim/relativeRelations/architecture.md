# Technische Architektur und Integrationsstrategie

> **Status:** Vorschlag aus der Konzeptdiskussion. Noch keine durch Creation Kit, xEdit oder einen Skyrim-SE-Testlauf bestätigte Implementierung.

## Randbedingungen

- Bestehende Vanilla- und fremde Quest-Stages **nicht setzen, umbenennen oder manipulieren**.
- Keine notwendigen Edits an den Skripten fremder Quests.
- Daten sparsam persistieren; möglichst keine Dauerschleife über alle NPCs.
- Framework und individueller Dialogcontent werden getrennt.
- Vanilla-Dialogoptionen bleiben erhalten.
- Falls eine Funktion SKSE oder ein Plugin benötigt, klar ausweisen; nicht als Vanilla-Funktion darstellen.

## Vorgeschlagene logische Komponenten

```text
Vanilla-/Mod-Quests, Locations, Factions, Relationships,
AI Data, Packages, Zeit, Besitz, NPC-Dialogdefinitionen
                         |
              Zustand lesen / Event empfangen
                         |
                 Context Resolver
                         |
               Knowledge / Event Store
                         |
            Conversation Opportunity Engine
                    /           \
             Bark/Hello       Topic-Auswahl
                    \           /
                 NPC-spezifische Inhalte
```

### 1. Kontextquellen / Resolver

Liest existierende Records, Bedingungen und Queststände. Transformiert sie in **inhaltliche Meilensteine** und kontextuelle Aussagen, ohne Originaldaten zu verändern.

### 2. Ereignismodell

Beispiel eines konzeptionellen Ereignisses:

```yaml
id: civilwar.whiterun.control_changed
scope: regional
region: Whiterun
source:
  quest: <konkrete Quest/Condition später verifizieren>
facts:
  - control_changed
  - dragonborn_involvement_unknown_by_default
```

Ein Source-Adapter kann eine Kombination aus Queststages, Globals, Locations, anderen registrierten Quellen usw. abfragen. Die Beispiele sind **kein gültiges Plugin-Konfigurationsschema**, sondern eine Denkstütze.

### 3. NPC-Kenntnis

Pro relevantem NPC und Thema möglichst wenig speichern:
- bekannter Meilenstein
- Quelle / eigene Erfahrung, sofern erforderlich
- Inhalt oder Variante einer mitgeteilten Aussage
- letzte relevante Interaktion
- optionaler Zweifel / Korrekturstatus

Nicht von Anfang an eine komplette Wissensdatenbank für jeden NPC erzeugen. Kenntnis vorzugsweise erst beim ersten Bedarf anlegen.

### 4. Gesprächsanlässe

Speichern oder ableiten:
- `topicId`
- `eligible` (aus Conditions)
- `importance` / Gewicht
- `lastOfferedAt` / `lastDiscussedAt`
- `followUpCount` und ggf. `cooldown`
- Flag „gerade vom NPC beiläufig angesprochen“

Jeder Anlass darf eigene Auslöseregeln für Zeit, Begegnung, Ruhephase, Ort und Beziehung definieren.

### 5. Individuelle Content-Module

Ysolda, Aela, Braith, ein generischer Stadtbewohner etc. bekommen keine eigene Kopie der Mechanik. Sie registrieren passende Ereignisse, Bewertungen, Antwortvarianten und ggf. Spezialaktionen.

## Zustandsabfrage versus Hooks

**Einfachste Stufe:** `GetStage()`, `GetStageDone()` und passende Condition-Funktionen nur dann verwenden, wenn ein NPC/Spielkontext relevant wird. Dabei sind Stages nicht immer monoton und einzelne Quests haben verzweigte Verläufe.

**Vanilla-Ereignisse:** Story Manager, Quest-Skripte und Papyrus-Events existieren, bilden aber keinen voraussetzungslosen globalen Eventbus für *alle* fremden Quest-Stage-Änderungen.

**SKSE / Drittanbieter-Erweiterungen:** In der Diskussion wurde powerofthree's Papyrus Extender als mögliche Quelle für Quest-Stage-Benachrichtigungen genannt. **API-Name, konkrete Registrierung, Signatur, Verhalten bei Save/Load und Versionen vor Nutzung anhand aktueller Dokumentation und Tests prüfen.** Kein ungeprüftes Beispiel als funktionsfähigen Code übernehmen.

Ein Event ist eine Optimierung oder Lösung für zeitkritische Fälle, kein Muss. Eine Zustandsabfrage beim Gespräch/Regionswechsel funktioniert auch, wenn der Event nicht gesendet wurde. Registrierungen können ggf. Neuinitialisierung nach Save-Load verlangen.

## Skyrim-Dialogsystem

Vanilla-Dialoge bestehen aus definierten Topics/Infos und Bedingungen. Die Idee einer Laufzeit-Zufallsauswahl ist deshalb von der **tatsächlichen Dialog-UI-Unterstützung** abhängig.

Zu prüfen:
- Wie lassen sich vordefinierte Zusatz-Topics zuverlässig ein-/ausblenden?
- Wie bleibt die Auswahl während eines Gesprächs stabil?
- Wie bleiben Vanilla- und Drittmod-Themen unberührt?
- Wie werden Prioritäten, Bark-Äußerungen und entsprechende Dialogoptionen gekoppelt?
- Wie erfolgt Vertonung oder Untertitel-Ausgabe kompatibel mit Voice Types?

**Nicht festgelegt:** Papyrus-only, SKSE-basiert, native SKSE-Erweiterung oder externe Konfigurationsdaten. Zunächst soll das kleinstmögliche Verfahren gewählt werden.

## Optionale Pseudologik

```text
onConversationStart(player, npc):
    context = readRelevantVanillaState(npc)
    known = loadNpcKnowledge(npc)
    candidates = gatherAuthoredTopics(context, known)
    eligible = candidates.filter(conditionsSatisfied)
    pinned = eligible.filter(mustBeAccessible)
    selected = pinned + weightedSample(eligible - pinned, limit)
    freezeForThisConversation(selected)

onNpcReceivesInformation(npc, topic, statement):
    persistNpcKnowledge(npc, topic, statement)
    updateFollowUpState(npc, topic)

onRelevantRegionEntered(region):
    markRegionalFactsForLazyEvaluation(region)
```

Dies ist **Architektur-Pseudocode**, kein ausführbares Skyrim-Skript.

## Daten- und Kompatibilitätsgrundsätze

- Additiv statt überschreibend.
- Bestehende Records möglichst nicht direkt verändern.
- Keine globale Iteration aller NPCs pro Tick.
- Regionale Zustände einmal ermitteln, individuellen Wissensstand lazy auflösen.
- Einmal erworbenes Wissen nicht bei der nächsten Zufallsauswertung „vergessen“.
- Zustände für Save/Load stabil und ggf. migrationsfähig halten.
- Aufwand und Erweiterbarkeit in Balance halten: „Drei Dialogzeilen“ dürfen kein Konfigurationsmonster benötigen.
