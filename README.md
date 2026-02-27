🌍 *Read this in other languages: [English](#english-version) | [Deutsch](#deutsche-version)*

---

# <a id="english-version"></a>Live Logik-Editor - Ultimate Smart Routing ⚡

A powerful, browser-based logic circuit editor and live simulator. This tool automatically converts simple text-based boolean expressions into a fully interactive Function Block Diagram (FBD/FBS) with smart cable routing and real-time simulation.

<p align="center">
  <a href="/Logik Editor Preview.png" target="_blank">
    <img src="/Logik Editor Preview.png" alt="Startbildschirm" width="600">
  </a> 
</p>

## ✨ Features

* **Text-to-Diagram Generation**: Write logic in a clean text editor, and the app instantly compiles it into a graphical node-based circuit.
* **Smart Auto-Routing**: Wires (edges) automatically calculate clean, non-overlapping paths and trunk lines between logic blocks.
* **Live Interactive Simulation**: 
  * Automatically generates UI controls (Toggle Switches for states, Push-buttons for impulses).
  * Real-time LED indicators for output tracking.
  * **Visual Graph Feedback**: Active lines, nodes, and pins glow dynamically when their state is `true` during the simulation.
* **Native RS Flip-Flop Support**: The compiler automatically detects variables like `S1`, `R1`, and `Q1` and wraps them into dedicated RS-Glied (Reset-Set) flip-flop blocks.
* **Syntax Highlighting**: Custom, non-blocking text highlighting for operators, assignments, and logic states to keep your code readable.
* **SVG Export**: Download your cleanly routed logic diagrams as `.svg` files for documentation or presentations.
* **Auto-Save**: Never lose your work; the editor state is automatically continuously saved to your browser's `localStorage`.
* **Pan & Zoom Interface**: Effortlessly navigate complex diagrams using the integrated pan-and-zoom SVG canvas.

## 🚀 Quick Start

Since this is a vanilla HTML/JS/CSS application, no build steps or bundlers are required.

1. Clone or download the repository.
2. Open `index.html` in any modern web browser.
3. Start typing your logic in the left panel, or click **"Beispiel laden"** to load the default example.

## 📖 Syntax & Logic Rules

The editor uses a straightforward, pseudo-code style syntax to define logic gates and assignments. 

### Operators
* **`:=`** : Assignment (e.g., `OUTPUT := INPUT`)
* **`&&`** : AND Gate (UND)
* **`||`** : OR Gate (ODER)
* **`¬`** : NOT / Inverter (NICHT)
* **`()`** : Parentheses for execution order and grouping

### Special Variables (RS Flip-Flops)
If you name your variables using `S`, `R`, and `Q` followed by a number (e.g., `1`), the engine automatically groups them into an **RS Flip-Flop block**:
* `S1 := ...` (Set condition for Flip-Flop 1)
* `R1 := ...` (Reset condition for Flip-Flop 1)
* `Q1` represents the output of Flip-Flop 1.

### Example Code
```text
S1 := START_BTN
R1 := STOP_BTN || EMERGENCY_STOP
SYSTEM_ACTIVE := Q1 && ¬ERROR_STATE
```

## 🎮 Simulation Mode

1. Write your logic in the editor.
2. The UI will automatically populate the **Eingänge** (Inputs) and **Ausgänge** (Outputs) panels based on your variables.
   * *Hint:* Suffixes matter! Variables ending in `_SCHALTER` or named `NH`/`NA` will render as toggle switches. Other inputs render as momentary push-buttons (TASTER).
3. Click **"Simulation starten"** (Start Simulation).
4. Interact with the switches and buttons. Watch the logic propagate through the SVG FBD graph in real-time.

## 🛠️ Built With

* **HTML5 / CSS3 / Vanilla JavaScript**
* [svg-pan-zoom](https://github.com/bumbu/svg-pan-zoom) (v3.6.1) for canvas manipulation.

---
---

# <a id="deutsche-version"></a>Live Logik-Editor - Ultimate Smart Routing ⚡

Ein leistungsstarker, browserbasierter Logikschaltungs-Editor und Live-Simulator. Dieses Tool wandelt einfache textbasierte Boolesche Ausdrücke automatisch in einen vollständig interaktiven Funktionsbausteinplan (FBP/FBS) mit intelligentem Auto-Routing und Echtzeit-Simulation um.

<p align="center">
  <a href="/Logik Editor Preview.png" target="_blank">
    <img src="/Logik Editor Preview.png" alt="Startbildschirm" width="600">
  </a>
</p>

## ✨ Funktionen

* **Text-zu-Diagramm Generierung**: Schreiben Sie Ihre Logik in einen übersichtlichen Texteditor, und die App kompiliert sie sofort in eine grafische, knotenbasierte Schaltung.
* **Intelligentes Auto-Routing**: Kabel (Verbindungen) berechnen automatisch saubere, überlappungsfreie Pfade und Kabelkanäle zwischen den Logikbausteinen.
* **Interaktive Live-Simulation**: 
  * Generiert automatisch UI-Bedienelemente (Schalter für Zustände, Taster für Impulse).
  * Echtzeit-LED-Anzeigen zur Überwachung der Ausgänge.
  * **Visuelles Graphen-Feedback**: Aktive Linien, Knoten und Pins leuchten während der Simulation dynamisch auf, wenn ihr Zustand `true` ist.
* **Native RS-Flip-Flop Unterstützung**: Der Compiler erkennt automatisch Variablen wie `S1`, `R1` und `Q1` und fasst sie in speziellen RS-Glied-Bausteinen (Reset-Set) zusammen.
* **Syntax-Hervorhebung**: Benutzerdefiniertes, nicht-blockierendes Highlighting für Operatoren, Zuweisungen und Logikzustände, um den Code lesbar zu halten.
* **SVG-Export**: Laden Sie Ihre sauber gerouteten Logikdiagramme als `.svg`-Dateien für Dokumentationen oder Präsentationen herunter.
* **Auto-Save**: Verlieren Sie nie Ihre Arbeit; der Editor-Zustand wird kontinuierlich im `localStorage` Ihres Browsers gespeichert.
* **Pan & Zoom Benutzeroberfläche**: Navigieren Sie mühelos durch komplexe Diagramme dank der integrierten SVG-Pan-und-Zoom-Funktion.

## 🚀 Schnellstart

Da es sich um eine reine HTML/JS/CSS-Anwendung handelt, sind keine Build-Schritte oder Bundler erforderlich.

1. Klonen oder laden Sie das Repository herunter.
2. Öffnen Sie die Datei `index.html` in einem beliebigen modernen Webbrowser.
3. Beginnen Sie, Ihre Logik im linken Bereich einzutippen, oder klicken Sie auf **"Beispiel laden"**, um das Standardbeispiel aufzurufen.

## 📖 Syntax & Logik-Regeln

Der Editor verwendet eine einfache Syntax im Pseudocode-Stil, um Logikgatter und Zuweisungen zu definieren.

### Operatoren
* **`:=`** : Zuweisung (z.B., `AUSGANG := EINGANG`)
* **`&&`** : UND-Gatter (AND)
* **`||`** : ODER-Gatter (OR)
* **`¬`** : NICHT / Invertierung (NOT)
* **`()`** : Klammern für Ausführungsreihenfolge und Gruppierung

### Spezielle Variablen (RS-Flip-Flops)
Wenn Sie Ihre Variablen mit `S`, `R` und `Q` gefolgt von einer Zahl (z.B. `1`) benennen, gruppiert die Engine diese automatisch in einen **RS-Flip-Flop-Baustein**:
* `S1 := ...` (Setz-Bedingung für Flip-Flop 1)
* `R1 := ...` (Rücksetz-Bedingung für Flip-Flop 1)
* `Q1` repräsentiert den Ausgang von Flip-Flop 1.

### Beispielcode
```text
S1 := START_BTN
R1 := STOP_BTN || EMERGENCY_STOP
SYSTEM_ACTIVE := Q1 && ¬ERROR_STATE
```

## 🎮 Simulationsmodus

1. Schreiben Sie Ihre Logik im Editor.
2. Die Benutzeroberfläche füllt die Panels **Eingänge** und **Ausgänge** automatisch basierend auf Ihren Variablen.
   * *Tipp:* Suffixe sind wichtig! Variablen, die auf `_SCHALTER` enden oder `NH`/`NA` heißen, werden als rastende Schalter gerendert. Andere Eingänge werden als Taster gerendert.
3. Klicken Sie auf **"Simulation starten"**.
4. Interagieren Sie mit den Schaltern und Tastern. Beobachten Sie, wie sich die Logik in Echtzeit durch den SVG-Graphen ausbreitet.

## 🛠️ Erstellt mit

* **HTML5 / CSS3 / Vanilla JavaScript**
* [svg-pan-zoom](https://github.com/bumbu/svg-pan-zoom) (v3.6.1) für die Canvas-Manipulation.
