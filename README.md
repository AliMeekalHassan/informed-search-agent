# Dynamic Pathfinding Agent

## Dependencies

This project uses only Python's standard library. No extra packages need to be installed.

Python's `tkinter` comes built-in with most Python installations. If it is missing, install it with:

```
# Windows
tkinter is included with the standard Python installer from python.org

# Ubuntu / Debian
sudo apt-get install python3-tk

# Mac (if using Homebrew Python)
brew install python-tk
```

## How to Run

Make sure you have Python 3.8 or higher installed.

Open a terminal in the folder where the files are saved, then run whichever iteration you want:

```
python iteration1.py
python iteration2.py
python iteration3.py
```

On some systems you may need to use `python3` instead of `python`.

## What Each File Does

| File | Description |
|------|-------------|
| iteration1.py | Grid environment with Greedy Best-First Search |
| iteration2.py | Adds A* Search alongside Greedy |
| iteration3.py | Full version with dynamic obstacles and agent re-planning |

## How to Use the App

1. Select your algorithm and heuristic from the left panel
2. Click on the grid to place or remove walls
3. Drag across the grid to draw walls quickly
4. Use Generate Maze to create a random obstacle layout
5. Press Run to start the search
6. Press Stop to cancel at any time
