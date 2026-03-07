🌍 *Read this in other languages: [English](#english-version) | [Deutsch](#deutsche-version)*

---

# <a id="english-version"></a>Virtual Automation, Logic & Industrial Simulator (VALIS)⚡

A powerful, browser-based logic circuit IDE, electrical schematic generator, and 2D physics factory simulator. This tool automatically converts text-based boolean expressions into fully interactive Function Block Diagrams (FBD/FBS), IEC Circuit Diagrams, and connects them to a live 2D Digital Twin sandbox.

<p align="center">
  <a href="/VALIS2.png" target="_blank">
    <img src="/VALIS2.png" alt="Startbildschirm" width="600">
  </a> 
</p>

## ✨ Features

### 🖥️ Multi-Panel IDE Workspace
* **Customizable Layout:** Open up to 3 views simultaneously (Logic, Circuit, Factory). Resize panels dynamically using draggable splitters, or toggle between vertical/horizontal layouts.
* **Auto-Save & Project Files:** Never lose your work. The editor auto-saves to `localStorage`. You can also export/import your entire project (code, components, and 2D layout) as `.leasave` files or copy-paste raw JSON. The save system is fully backwards-compatible.

### 🧠 Logic Engine & Code Editor
* **Native RS & SR Flip-Flop Support:** Variables starting with `S`, `R`, and `Q` followed by a number are automatically detected and wrapped into dedicated Flip-Flop logic blocks. You can explicitly create Reset-dominant (RS) or Set-dominant (SR) flip-flops by appending the respective suffixes (`_RS` or `_SR`).
* **Syntax Highlighting:** Custom, non-blocking text highlighting for operators, assignments, and logic states.
* **Native RS Flip-Flop Support:** Variables named `S1`, `R1`, and `Q1` are automatically detected and wrapped into dedicated RS-Glied (Reset-Set) flip-flop logic blocks.
* **Pulse-Catch / Afterglow:** Extremely fast logical impulses trigger an atmospheric "afterglow" fade-out effect in the visual diagrams, ensuring you never miss a split-second signal.

### 📐 Smart Auto-Routing (3 Views)
1. **Logikplan (FBD/FBS):** Instant generation of graphical node-based logic gates with smart, non-overlapping cable routing.
2. **Schaltplan (IEC):** Automatic generation of traditional electrical circuit diagrams (relays, contacts, valves, LEDs). Adapts dynamically to NC (Normally Closed) and NO (Normally Open) logic.
3. **SVG Export:** Download your cleanly routed diagrams as `.svg` files (retains CSS rendering properties).

### 🏭 2D Factory Physics Simulator (Digital Twin)
* **Background Simulation:** The physics engine runs seamlessly in the background. If a sensor triggers in the factory, the logic gate switches, and the IEC relay activates—all in real-time.
* **Kinematics & Attachments:** Mount objects (like pushers, windows, or sensors) to cylinder rods. When the cylinder extends, all attached children move with it perfectly synchronized.
* **Physics & Collisions:** Fully integrated OBB (Oriented Bounding Box) math engine. Items interact with conveyor belts, fall via gravity, and collide with walls, pushers, or frames.
* **Advanced Sensors:** * `Inductive`: Detects only metallic objects (FE items, metal frames, aluminum window edges).
  * `Capacitive` / `Optical`: Detects all physical objects.
  * `Magnetic (Reed)`: Snaps directly to cylinders to detect rod extension/retraction.
* **Sandbox Controls:** Multi-select, copy/paste (Ctrl+C / Ctrl+V), rotate, scale, and delete components. Drag & drop elements like Spawners, Despawners, Safety Doors (Alu/Glass), Presses, and L-shaped Pushers.

## 🚀 Quick Start

Since this is a vanilla HTML/JS/CSS application, no build steps or bundlers are required.

1. Clone or download the repository.
2. Open `index.html` in any modern web browser.
3. Start typing your logic in the left panel, or click **"Beispiele..."** (Load Example) to load a fully configured sorting plant.

## 📖 Syntax & Logic Rules

The editor uses a straightforward, pseudo-code style syntax to define logic gates and assignments. 

### Operators
* **`:=`** : Assignment (Aliases: `=`, `<-`, `IST`)
* **`&&`** : AND Gate (Aliases: `&`, `∧`, `AND`)
* **`||`** : OR Gate (Aliases: `|`, `∨`, `OR`)
* **`¬`** : NOT / Inverter (Aliases: `!`, `NOT`)
* **`()`** : Parentheses for execution order and grouping

### Special Variables (RS & SR Flip-Flops)
If you name your variables using `S`, `R`, and `Q` followed by a number (e.g., `1`), the engine automatically groups them into a **Flip-Flop block**. You can define priority behavior by adding suffixes:
* **RS (Reset-dominant, Default):** `S1` / `S1_RS` and `R1` / `R1_RS` create an RS block with the output `Q1` / `Q1_RS`. If both inputs are true simultaneously, Reset wins (Standard for machine safety).
* **SR (Set-dominant):** `S1_SR` and `R1_SR` create an SR block with the output `Q1_SR`. If both inputs are true simultaneously, Set wins.

### Example Code
```text
// Reset-dominant Flip-Flop (Standard)
S1 := START_BTN
R1 := STOP_BTN || EMERGENCY_STOP

// Set-dominant Flip-Flop
S2_SR := OVERRIDE_START
R2_SR := TIMEOUT

SYSTEM_ACTIVE := Q1 && Q2_SR
```

## 🎮 UI Configuration & Control

1. Write your logic in the editor.
2. The UI will automatically populate the **Eingänge** (Inputs) and **Ausgänge** (Outputs) panels.
3. Use the **dropdowns** next to each variable to assign physical hardware types:
   * **Inputs:** Push-buttons (NO/NC), Toggle Switches (NO/NC), Emergency Stops, or Sensors.
   * **Outputs:** LEDs, Solenoid Valves, Relays.
   *(Hint: Switching between NO and NC will automatically invert the visual rest-state of the hardware in the diagrams and simulation!)*
4. Click **"Simulation starten"** and interact with the 2D plant or the UI switches.

## 🛠️ Built With
* **HTML5 / CSS3 / Vanilla JavaScript**
* Custom OBB Kinematics Physics Engine
* [svg-pan-zoom](https://github.com/bumbu/svg-pan-zoom) (v3.6.1) for canvas manipulation.

---
---

# <a id="deutsche-version"></a>Virtueller Automatisierungs-, Logik- & Industrie-Simulator (VALIS) ⚡

Eine leistungsstarke, browserbasierte Logik-IDE, Schaltplangenerator und 2D-Physik-Anlagensimulator. Dieses Tool wandelt textbasierte Boolesche Ausdrücke automatisch in interaktive Funktionsbausteinpläne (FBP/FBS) und IEC-Stromlaufpläne um und koppelt sie mit einer Live-2D-Simulations-Sandbox.

<p align="center">
  <a href="/VALIS2.png" target="_blank">
    <img src="/VALIS2.png" alt="Startbildschirm" width="600">
  </a>
</p>

## ✨ Funktionen

### 🖥️ Multi-Panel IDE Workspace
* **Dynamisches Layout:** Öffnen Sie bis zu 3 Ansichten gleichzeitig (Logik, Schaltplan, 2D Anlage). Verschieben Sie die Zwischenräume (Splitter) stufenlos oder wechseln Sie zwischen vertikaler und horizontaler Anordnung.
* **Auto-Save & Projektdateien:** Der Editor speichert kontinuierlich im `localStorage`. Projekte (inkl. Code, Bauteilzuweisungen und der kompletten 2D-Matrix) können als `.leasave`-Datei exportiert/importiert oder als Raw-JSON kopiert werden. Alte Speicherstände sind aufwärtskompatibel.

### 🧠 Logik-Engine & Code-Editor
* **Native RS- & SR-Flip-Flop Unterstützung:** Der Compiler erkennt Variablen mit `S`, `R` und `Q` (gefolgt von einer Zahl) automatisch und fasst sie in speziellen Speicherbausteinen zusammen. Über die Suffixe `_RS` und `_SR` können Sie explizit zwischen rücksetzdominanten und setzdominanten Gliedern wählen.
* **Syntax-Hervorhebung:** Benutzerdefiniertes Highlighting für Operatoren, Zuweisungen und RS-Glieder.
* **Native RS-Flip-Flop Unterstützung:** Der Compiler erkennt Variablen wie `S1`, `R1` und `Q1` automatisch und fasst sie in speziellen RS-Glied-Bausteinen zusammen.
* **Pulse-Catch / Afterglow:** Extrem kurze Logik-Impulse (die für das menschliche Auge zu schnell wären) erzeugen in den Plänen einen atmosphärischen "Nachleucht"-Effekt (Fade-Out), sodass kein Signal unbemerkt bleibt.

### 📐 Smart Auto-Routing (3 Ansichten)
1. **Logikplan (FBS):** Sofortige Generierung von knotenbasierten Logikgattern mit intelligenter, überlappungsfreier Kabelführung.
2. **Schaltplan (IEC):** Automatische Erstellung von klassischen Stromlaufplänen (Relais, Kontakte, Ventile, Meldeleuchten). Passt sich dynamisch an Öffner (NC) und Schließer (NO) an.
3. **SVG-Export:** Laden Sie die Pläne als saubere `.svg`-Dateien herunter.

### 🏭 2D Anlagen-Physiksimulator (Digitaler Zwilling)
* **Hintergrund-Simulation:** Die Physikengine läuft nahtlos im Hintergrund weiter. Löst ein Sensor in der 2D-Fabrik aus, schaltet das Logikgatter und zieht den IEC-Schütz an – alles synchron in Echtzeit.
* **Kinematik & Anbauteile:** Montieren Sie Objekte (wie Schieber, Schutztüren oder Sensoren) per Rechtsklick an Zylinderkolben. Fährt der Zylinder aus, bewegen sich alle montierten Bauteile physikalisch korrekt mit.
* **Physik & Kollision:** Echte Mathematik-Engine. Werkstücke fallen auf Förderbänder, werden transportiert und kollidieren mit Wänden, L-Schiebern und Pressen.
* **Erweiterte Sensorik:** * `Induktiv`: Erkennt nur metallische Objekte (Metallblöcke, Riffelblech, Alu-Rahmen von Türen).
  * `Kapazitiv` / `Optisch`: Erkennt alle physischen Objekte.
  * `Magnetisch (Reed)`: Lässt sich an Zylinder anheften, um die Endlagen des internen Magneten abzufragen.
* **Sandbox-Steuerung:** Multi-Select (Auswahlrahmen), Kopieren/Einfügen (Strg+C / Strg+V), Drehen, Skalieren und Löschen von Bauteilen.

## 🚀 Schnellstart

Da es sich um eine reine HTML/JS/CSS-Anwendung handelt, sind keine Build-Schritte erforderlich.

1. Klonen oder laden Sie das Repository herunter.
2. Öffnen Sie die Datei `index.html` in einem beliebigen modernen Webbrowser.
3. Beginnen Sie, Ihre Logik einzutippen, oder klicken Sie auf **"Beispiele..."**, um eine voll funktionsfähige Sortieranlage zu laden.

## 📖 Syntax & Logik-Regeln

Der Editor verwendet eine einfache Syntax im Pseudocode-Stil, um Logikgatter und Zuweisungen zu definieren.

### Operatoren
* **`:=`** : Zuweisung (Aliase: `=`, `<-`, `IST`)
* **`&&`** : UND-Gatter (Aliase: `&`, `∧`, `AND`)
* **`||`** : ODER-Gatter (Aliase: `|`, `∨`, `OR`)
* **`¬`** : NICHT / Invertierung (Aliase: `!`, `NOT`)
* **`()`** : Klammern für Ausführungsreihenfolge

### Spezielle Variablen (RS- & SR-Flip-Flops)
Wenn Sie Ihre Variablen mit `S`, `R` und `Q` gefolgt von einer Zahl (z.B. `1`) benennen, gruppiert die Engine diese automatisch in einen **Flip-Flop-Baustein**. Über Suffixe bestimmen Sie das Dominanz-Verhalten:
* **RS (Rücksetz-dominant, Standard):** `S1` / `S1_RS` und `R1` / `R1_RS` erzeugen ein RS-Glied mit dem Ausgang `Q1` / `Q1_RS`. Liegen beide Signale an, gewinnt das Rücksetzen (Industrieller Sicherheitsstandard).
* **SR (Setz-dominant):** `S1_SR` und `R1_SR` erzeugen ein SR-Glied mit dem Ausgang `Q1_SR`. Liegen beide Signale an, gewinnt das Setzen.

### Beispielcode
```text
// Rücksetz-dominantes Flip-Flop (Standard)
S1 := START_BTN
R1 := STOP_BTN || EMERGENCY_STOP

// Setz-dominantes Flip-Flop
S2_SR := ZWANGS_START
R2_SR := ZEITABLAUF

SYSTEM_AKTIV := Q1 && Q2_SR
```

## 🎮 UI-Konfiguration & Steuerung

1. Schreiben Sie Ihre Logik im Editor.
2. Das UI füllt die Panels **Eingänge** und **Ausgänge** automatisch ab.
3. Nutzen Sie die **Dropdown-Menüs** neben den Variablen, um physische Hardware zuzuweisen:
   * **Eingänge:** Taster (NO/NC), rastende Schalter (NO/NC), Not-Halt oder diverse Sensoren.
   * **Ausgänge:** LEDs, Magnetventile, Hilfsrelais.
   *(Tipp: Ein Wechsel zwischen Öffner (NC) und Schließer (NO) invertiert automatisch den Ruhezustand der Hardware in den Plänen und der Simulation!)*
4. Drücken Sie **"Simulation starten"** und bedienen Sie die Schalter im Panel oder interagieren Sie mit der 2D-Anlage.

## 🛠️ Erstellt mit
* **HTML5 / CSS3 / Vanilla JavaScript**
* Eigene OBB-Kinematik-Physikengine
* [svg-pan-zoom](https://github.com/bumbu/svg-pan-zoom) (v3.6.1) für die Canvas-Manipulation.
