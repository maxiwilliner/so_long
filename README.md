# so_long - A 2D Graphical Journey into Map Parsing | 42 Madrid

*This project has been developed as part of the 42 curriculum by mwilline.*

## 📖 Overview
**so_long** is a 2D game developed in C using the **MiniLibX** graphical library. The objective is to navigate a character through a map, collect all items, and reach the exit in the minimum number of moves.

Beyond the gameplay, this project is a deep dive into **Window Management**, **Event Handling** (keyboard/mouse), and, most importantly, **Data Parsing and Validation**.

---

## 🏗️ Technical Highlights
* **Graphical Rendering:** Utilizing **MiniLibX** to manage windows, textures, and real-time image rendering.
* **Map Parsing:** Developed a robust parser to read `.ber` files and convert them into 2D memory structures.
* **Event-Driven Programming:** Implementation of hooks to handle user input (WASD/Arrows) and window events (closing/minimizing) seamlessly.
* **Memory Management:** Efficient allocation and deallocation of textures and map data to ensure zero memory leaks.

---

## 🧬 Data Engineering Relevance: The "Data Pipeline"
This project mirrors a real-world data ingestion pipeline:
1.  **Extraction:** Reading the `.ber` map file (the "Raw Data").
2.  **Transformation:** Parsing characters into a 2D coordinate system.
3.  **Validation (Data Quality):** * Ensuring the map is rectangular and enclosed by walls.
    * Verifying essential elements (1 Exit, 1 Start, at least 1 Collectible).
    * **Pathfinding Algorithm:** Implementing **Flood Fill** to ensure that every collectible and the exit are reachable, preventing "corrupted" or unsolvable data scenarios.

---

## 🧠 Core Algorithm: Path Validation
To guarantee map solvability, I implemented a **Flood Fill algorithm**. This graph traversal technique explores the map from the player's starting position to verify that the path to every item and the exit is not blocked by walls. This logic is fundamental for ensuring data integrity before processing.



---

## 🛠️ Instructions

### Compilation
The project includes a Makefile with standard rules:
```bash
make        # Compiles the game
make clean  # Removes object files
make fclean # Removes objects and the executable
make re     # Recompiles from scratch
