<div align="center">

  # 🤖 NexusPath: AGV Warehouse Floor Dispatcher & Pathfinding Simulator

  **An interactive HTML5 Canvas warehouse automation simulation featuring multi-AGV fleet management, real-time BFS grid pathfinding, and dynamic obstacle handling.**

  [![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
  [![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
  [![Canvas API](https://img.shields.io/badge/Canvas_API-000000?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)
  [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)

</div>

---

## 📌 Overview

**NexusPath** is an interactive, browser-based Automated Guided Vehicle (AGV) warehouse floor simulator and routing engine. It models an automated fulfillment center where autonomous robots navigate through storage racks and dynamic obstacles (like aisle spills) from charging docks to target pods and packing stations using Breadth-First Search (BFS) pathfinding.

---

## ✨ Key Features

* **🧠 Grid-Based BFS Pathfinding:** Implements Breadth-First Search to calculate optimal collision-free routes across the warehouse floor matrix.
* **🤖 Multi-AGV Fleet Dispatching:** Dispatch and manage multiple AGVs simultaneously, each tracking independent pick-up, transit, and delivery states.
* **⚠️ Interactive Obstacle Placement:** Click anywhere on the warehouse floor grid in real time to place or clear aisle blockages and spills, forcing AGVs to dynamically recalculate paths.
* **📊 Live Warehouse Telemetry:** Real-time logging console tracking task assignments, routing status, obstacles, and completed delivery metrics.
* **🎨 Modern Cyberpunk Warehouse UI:** Dark-mode canvas layout featuring clearly designated storage racks, charging start docks, and packing stations.

---

## 🛠️ Tech Stack

* **Frontend:** Vanilla HTML5, CSS3
* **Rendering Engine:** HTML5 2D Canvas API
* **Algorithm & Logic:** Vanilla JavaScript (ES6+ Classes, Grid Matrix Manipulations, BFS Pathfinding)

---

## 🏗️ Pathfinding & Dispatch Logic

The simulation coordinates AGV routing through grid-based traversal:

```mermaid
graph TD;
    A[AGV Assigned New Task / Target] --> B[Run BFS Pathfinding on Warehouse Grid];
    B --> C{Is Path Found?};
    C -- Yes --> D[Follow Waypoints to Target Pod];
    C -- No --> E[Wait for Clearance / Obstacle Removal];
    D --> F[Arrive at Pod & Return to Packing Station];
    F --> G[Increment Delivery Count & Assign New Cycle];
