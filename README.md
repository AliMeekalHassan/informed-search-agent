# Dynamic Pathfinding Agent

A grid-based pathfinding visualizer built in Python using Tkinter. The agent navigates from a start node to a goal node using informed search algorithms, with support for real-time obstacle spawning and automatic re-planning.

---

## Features

- **A\* Search** and **Greedy Best-First Search** algorithms
- **Manhattan** and **Euclidean** heuristic functions
- Interactive grid editor — click or drag to place and remove walls
- Move the start and goal nodes anywhere on the grid
- Random maze generation with adjustable obstacle density
- Dynamic obstacle mode — new walls spawn while the agent is moving
- Automatic re-planning when the current path is blocked
- Animated visualization of visited nodes, frontier, and final path
- Real-time metrics: nodes visited, path cost, and execution time

---

## Requirements

- Python 3.8 or higher
- Tkinter (included with Python by default)

No third-party packages are required.

If Tkinter is missing on your system, install it with:

```bash
# Ubuntu / Debian
sudo apt-get install python3-tk

# Fedora
sudo dnf install python3-tkinter

# Mac (Homebrew Python)
brew install python-tk

# Windows
# Tkinter is included in the official Python installer from python.org
# If missing, re-run the installer and make sure tcl/tk is checked
```

---

## How to Run

```bash
python main.py
```

---

## How to Use

### Setting Up the Grid

| Control | What it does |
|---|---|
| Click a cell | Toggle wall on or off |
| Click and drag | Draw walls across multiple cells |
| Edit Mode: Move Start | Click any cell to move the start node |
| Edit Mode: Move Goal | Click any cell to move the goal node |
| Generate Maze | Randomly fills the grid with walls at the chosen density |
| Clear Grid | Removes all walls and resets the grid |

### Running a Search

1. Select an **Algorithm** — A* or Greedy Best-First Search
2. Select a **Heuristic** — Manhattan or Euclidean
3. Press **Run**

The visualization plays in three stages:
- **Blue cells** show nodes that were visited and expanded
- **Yellow cells** show the frontier (nodes in the queue but not yet expanded)
- **Cyan cells** show the final path from start to goal

Press **Stop** at any time to cancel.

### Dynamic Obstacle Mode

Enable the **Dynamic Mode** checkbox before pressing Run. While the agent is moving along the path, new walls will randomly appear on the grid. If a wall blocks the planned route, the agent immediately recalculates a new path from its current position and continues toward the goal.

Use the **Spawn Probability** slider to control how frequently new walls appear.

---

## Metrics Panel

After each run the panel on the left updates with:

- **Nodes visited** — total number of nodes expanded during the search
- **Path cost** — number of steps in the final path
- **Execution time** — how long the search algorithm took in milliseconds
- **Replans** — how many times the agent had to recalculate its path (dynamic mode only)

---

## Algorithm Overview

### Greedy Best-First Search

Selects the next node based only on the heuristic estimate to the goal:

```
f(n) = h(n)
```

Fast and efficient in open environments but does not guarantee the shortest path. Can make poor decisions when obstacles force detours.

### A* Search

Combines the actual cost from the start with the heuristic estimate:

```
f(n) = g(n) + h(n)
```

Guarantees the shortest path as long as the heuristic does not overestimate. More thorough than Greedy, expanding more nodes to ensure optimality.

### Heuristics

**Manhattan Distance** — counts the total horizontal and vertical steps between two cells. Well suited for 4-directional grid movement.

**Euclidean Distance** — straight-line distance between two cells. Admissible on grids but can underestimate since diagonal movement is not allowed.

---

## Project Structure

```
.
├── main.py        # Main application — run this
└── README.md      # This file
```

---

## Color Reference

| Color | Meaning |
|---|---|
| White | Empty cell |
| Dark grey | Wall |
| Green | Start node |
| Red | Goal node |
| Blue | Visited / expanded node |
| Yellow | Frontier node |
| Cyan | Final path |
| Orange | Agent current position (dynamic mode) |
