# Architektur und Prototyping — unverbindliche Skizze

Die Komplexität liegt voraussichtlich weniger in einzelnen Assets als in den numerischen Wechselwirkungen. Bei einer tatsächlichen Umsetzung sollten wir die Bausteine zuerst identifizieren und schrittweise modellieren (iSAQB-orientierte Zerlegung).

## Kandidaten für Bausteine
1. Genetik, Ursprungsprofile und Kreation
2. Visueller Charaktereditor und Morphing
3. Psyche, Emotionen und Bedürfnisse
4. Beziehungen, sozialer Austausch und Gruppenbildung
5. Identitätsdiskrepanz und psychologische Intervention
6. Werte, Gesetze, Rollen und Ordnungshüter
7. Aufgaben, Räume, Ressourcen und Expeditionen
8. Ereignisse und emergente Dramaturgie
9. Persistenz, Simulationstakt und Balancing
10. UI, KI-Begleitung und optionale Mod-Schnittstellen

Die Grenzen und Datenflüsse sind noch zu prüfen. Keine Festlegung auf ECS, GOAP oder konkrete Engine-Architektur.

## Technischer Experimentierpfad
1. Ein numerisches Modell einer Kreation **ohne Grafik** simulieren.
2. Zwei Kreationen mit Emotionen und gerichteten Beziehungen.
3. Eine Intervention und ihre unsichere zeitliche Wirkung.
4. Eine einfache Regel, deren Befolgung von individuellen Werten abhängt.
5. Erst danach Wohnraum, Aufgaben und visuelle Darstellung integrieren.

So lassen sich Zustandsverläufe und Balancing früh testen, bevor aufwendige Assets nötig werden.

## Charaktermodelle / Godot
Angedacht ist, auf Erfahrungen und eventuell Assets der Skyrim-Modding-Community zurückzugreifen (CBBE/3BA/HIMBO). Ein denkbarer technischer Pfad führt über Blender, Shape Keys/Blendshapes und glTF nach Godot. Rigging, Animation, Kleidung und Laufzeitperformance sind gesonderte Themen.

**Lizenzvorbehalt:** Die Nutzung von Skyrim-Mod-Assets in einem eigenständigen Spiel ist nicht automatisch gestattet. Rechte müssen für jedes Asset geklärt werden; für öffentliche Builds gegebenenfalls eigene oder separat lizenzierte Modelle einsetzen.

Gesichtsübertragung aus Fotos ist ein eigenes Forschungs- und Rechte-Thema (Einwilligung, Persönlichkeitsrechte, Verbreitung).
