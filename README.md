# Live Logik-Editor - Ultimate Smart Routing ⚡

A powerful, browser-based logic circuit editor and live simulator. This tool automatically converts simple text-based boolean expressions into a fully interactive Function Block Diagram (FBD/FBS) with smart cable routing and real-time simulation.

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

 <a href="/Logik Editor Preview.png" target="_blank">
          <img src="/Logik Editor Preview.png" alt="Startbildschirm" width="600">
