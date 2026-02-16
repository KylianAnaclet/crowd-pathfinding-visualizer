# CROWD PATHFINDING VISUALIZER
A Python-based interactive simulation tool that models crowd movement and trajectory optimization in a constrained environment.

![Demo Simulation](https://github.com/KylianAnaclet/crowd-pathfinding-visualizer/blob/main/demo.gif?raw=true)

## NOTE
This project was originally developed as part of a coursework in France. Source code variables and GUI elements are in French, but this documentation has been translated for accessibility.

## OVERVIEW
The goal of this project is to simulate autonomous agents (pedestrians) navigating from a starting point to a destination while avoiding static obstacles and dynamic user-placed barriers.

Unlike global pathfinding algorithms (like Dijkstra or A*), agents in this simulation use a reactive local search approach: they observe their immediate neighborhood and make decisions based on heuristic distance to the target and memory of past positions to avoid loops.

## KEY FEATURES

1. Interactive Dashboard (main.py)
   - Manage map files (obstacles and agents).
   - Select agent configurations.
   - Launch simulations with specific parameters.

2. Built-in Map Editor (dessinercarte.py)
   - Draw custom maps with the mouse.
   - Place obstacles, start points, and end points intuitively.
   - Save and load your creations.

3. Real-Time Simulation (simulation.py)
   - Adjust simulation speed on the fly.
   - Dynamic Interaction: Add or remove walls *during* the simulation to test agent adaptability.
   - Pause/Resume control.

## HOW IT WORKS (ALGORITHM)

The simulation logic relies on a custom Agent class ('Personnage'). The movement logic follows these rules:

1. Perception: At each step, the agent scans its immediate neighboring cells.
2. Heuristic Decision: It calculates the distance from each free neighbor to the destination and selects the closest one.
3. Memory (Tabu Search): To prevent agents from getting stuck in loops (moving back and forth), each agent maintains a list of recently visited positions.
4. Stuck Recovery: If an agent is trapped (no valid moves), it clears its memory to allow backtracking and finding a new path.

## CONTROLS

### Map Editor
- Draw Obstacles: Hold Right Click
- Erase: Hold Left Click
- Set Start/End: Click "Mode" button -> 1st click (Start), 2nd click (End)
- Confirm Start/End: Spacebar

### Simulation
- Pause / Resume: Spacebar (or UI Button)
- Place Wall (Live): Left Click
- Remove Wall (Live): Right Click
- Speed: Use the slider in the UI

## PROJECT STRUCTURE

- data/ : Stores map files 
- main.py : Application entry point (Menu & Dashboard)
- dessinercarte.py : Map Editor (Drawing tool)
- simulation.py : Core Simulation Logic

## GETTING STARTED

1. Clone the repository
2. Run the application: python main.py
3. Select a map from the list (or create a new one via the Editor)
4. Click "Lancer Simulation"


## Authors & Contributors

This project was built by a team of two:

* **[Kylian]** - [KylianAnaclet](https://github.com/KylianAnaclet)
* **[Elorien]** - [bordaelorien](https://github.com/bordaelorien)
