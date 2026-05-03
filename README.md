# AstroDock-2D-Autonomous-Spacecraft-Proximity-Operations-Docking-Control






# AstroDock-2D 🚀

AstroDock-2D is a Python-based 2D simulation suite designed to model the final phase of spacecraft docking. It focuses on the "Chaser" craft's ability to navigate from various initial conditions to a "Target" docking port while maintaining orientation. Features include PID-based waypoint navigation, Bézier-curve path planning, and avoiding orbital debris (obstacles) using artificial potential fields. 





## 🌟 Key Features
* **Gymnasium-Compatible Environment**: Standardized RL-ready interface for spacecraft dynamics.
* **Advanced Path Planning**: 
    * **SmartPath**: Dynamic trajectory generation using Quadratic Bézier curves.
    * **Up-and-Over**: Strategic waypoint logic for complex obstacle clearance.
* **Obstacle Avoidance**: Implementation of **Artificial Potential Fields (APF)** where obstacles exert a repulsive force ($1/d^3$) on the chaser.
* **4-Stage Docking Logic**: Visual color-coded feedback based on proximity to the docking axis.
* **Automated Visualization**: Built-in Matplotlib animation engine that exports high-quality `.mp4` logs of every maneuver.

## 🛠️ Technical Stack
* **Language**: Python 3.x
* **Physics/Math**: NumPy (Transformation matrices & Vector calculus)
* **Environment**: Gymnasium
* **Visualization**: Matplotlib (Animation & Patches)
* **Rendering**: FFMPEG

## 📐 Control Theory Overview
The chaser utilizes a Proportional (P) Control law to minimize the error between the **Probe Tip** and the current **Waypoint**.

$$u = K_p (x_{target} - x_{probe})$$

In the obstacle avoidance module, the control input is augmented with a gradient-based repulsion vector:
$$F_{repulsion} = \eta \left( \frac{1}{\rho} - \frac{1}{\rho_0} \right) \frac{1}{\rho^2}$$

## 🚀 Getting Started

### Prerequisites
```bash
pip install gymnasium numpy matplotlib
# Ensure ffmpeg is installed on your system for video saving
```


Running Simulations
The repository is organized by control complexity:

- Basic Docking: python spacecraft_way_point_dock_control.py

- Smart Pathing: python spacecraft_way_point_dock_control2.py

- Potential Field Avoidance: python spacecraft_way_point_dock_control3.py

📊 Visualizing Results
The scripts generate animations showing the chaser (Red) docking with the target (Grey).

- Blue/Cyan: Long-range approach.

- Gold: Final alignment.

- Red: Precision docking insertion

<img width="789" height="804" alt="image" src="https://github.com/user-attachments/assets/a21f2be3-7dc5-4d76-bec5-f43191540b13" />






<img width="791" height="780" alt="image" src="https://github.com/user-attachments/assets/fa842492-7c0f-484b-b922-02d7832e0736" />





<img width="776" height="755" alt="image" src="https://github.com/user-attachments/assets/8da4badd-a060-419b-8db6-936191ab2db0" />


