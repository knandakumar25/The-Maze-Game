# The Maze Game

[![PuzzleScript](https://img.shields.io/badge/Engine-PuzzleScript-red.svg)](https://www.puzzlescript.net/)
[![Platform](https://img.shields.io/badge/Platform-Web_Browser-orange.svg)]()
[![Genre](https://img.shields.io/badge/Genre-Tile--Based_Puzzle-blue.svg)]()
[![Author](https://img.shields.io/badge/Author-Karthik_Nandakumar-green.svg)]()

> A retro tile-based puzzle game combining block-pushing (Sokoban), match-3 clearing, key-door gating, and colored portal teleportation across 4 increasingly complex puzzle labyrinths.

---

## Overview

**The Maze Game** is an original puzzle game developed with the [PuzzleScript](https://www.puzzlescript.net/) engine by Karthik Nandakumar. 

Players navigate a maze filled with obstacles, pits, colored blocks, locked gates, and spatial portals. To reach the green exit portal on each level, you must plan your movement sequences carefully: push blocks out of the way, align triplets of identical blocks to vaporize them, collect keys to unlock sealed doorways, and leverage dual-way teleporters to cross impassable barriers.

---

## Gameplay Mechanics

```
   [Player] ────> [Key] ────> [Unlock Door] ────> [Teleport] ────> [EndPoint]
                     │
                     └───> [Align 3 Blocks] ──> [Clear Pathway]
```

### 1. Block Pushing & Physics
- The player can push standalone colored blocks through open corridors.
- Blocks cannot be pushed into solid outer walls (`Wall`), static interior barriers (`WallBlock`), or closed doors.

### 2. Match-3 Block Elimination
- Aligning **three identical colored blocks** in a straight row instantly vaporizes all three:
  - `[ PinkBlock | PinkBlock | PinkBlock ] -> [ | | ]`
  - `[ RedBlock | RedBlock | RedBlock ] -> [ | | ]`
  - `[ PurpleBlock | PurpleBlock | PurpleBlock ] -> [ | | ]`
  - `[ OrangeBlock | OrangeBlock | OrangeBlock ] -> [ | | ]`
  - `[ BlackBlock | BlackBlock | BlackBlock ] -> [ | | ]`
- Use this rule tactically to clear pathways blocked by clustered blocks!

### 3. Hazard Pits (`GrayHole`)
- Dark gray pit traps obstruct both player and blocks. Pushing blocks into holes blocks passage unless carefully navigated around.

### 4. Keys & Doors
- Stepping onto a yellow **Key (`+`)** unlocks the associated brown **Closed Door (`C`)**, transforming it into an **Open Door (`J`)** and allowing passage into restricted chambers.

### 5. Color-Coded Teleportation Portals
Stepping onto an active teleportation pad and pressing the **Action** button instantly beams the player to the linked portal:
- **Red Portal (`D`)** $\longleftrightarrow$ **Purple Portal (`I`)**
- **Blue Portal (`A`)** $\longleftrightarrow$ **Orange Portal (`F`)**
- **Green Portal (`M`)** $\longleftrightarrow$ **Gray Portal (`L`)**

### 6. Win Condition
- Guide the player sprite onto the green **EndPoint (`E`)** tile to conquer the maze and advance to the next level.

---

## Controls

| Key | Action |
| :--- | :--- |
| **Arrow Keys** / **W, A, S, D** | Move Player (Up, Down, Left, Right) / Push Blocks |
| **X** / **Spacebar** | Action (Activate Teleporters) |
| **Z** / **U** | Undo previous step |
| **R** | Restart current level |
| **Esc** | Pause / Options |

---

## Levels

The game features **4 handcrafted levels** designed with an escalating difficulty curve:
1. **Level 1 (Introduction)**: Fundamental movement, block pushing, and basic pit navigation.
2. **Level 2 (The Labyrinth)**: Tight corridor navigation with black block sorting and spatial constraints.
3. **Level 3 (Lock & Key)**: Introduces the yellow key, locked gates, and strategic block placement.
4. **Level 4 (Dimensional Gateways)**: The ultimate test combining multiple two-way portal networks (Blue-Orange, Red-Purple, Green-Gray), locked doors, and precision routing.

---

## How to Play

No build step or local dependency installation is required!

1. Clone or download this repository:
   ```bash
   git clone https://github.com/knandakumar25/The-Maze-Game.git
   ```
2. Open `The Maze Game.html` directly in any web browser:
   ```powershell
   Start-Process ".\The Maze Game.html"
   ```

You can also copy the embedded PuzzleScript source code directly into the [PuzzleScript Online Editor](https://www.puzzlescript.net/editor.html) to play, inspect, or modify the rules and levels.

---

## Project Structure

```
The-Maze-Game/
├── The Maze Game.html   # Standalone HTML5 canvas game containing complete PuzzleScript runtime, rules, and levels
└── README.md            # Project documentation
```

---

## Author & Attribution

- **Creator**: Karthik Nandakumar
- **Engine**: [PuzzleScript](https://www.puzzlescript.net/) by Stephen Lavelle (increpare)
