# Industrial Robot Control: Cube Palletizing into Letter Shapes (UR5)

This project involves programming a **Universal Robots (UR5)** robotic arm to perform complex precision tasks: tracing the outline of specific letters and palletizing cubes inside them. The project demonstrates advanced robot motion control, gripper usage, spatial coordinate management, and a modular logic implementation, developed and validated in the **URSim** simulator.

---

## 🎯 Project Goal
The main goal is to develop a robust, modular program capable of executing process tasks (marker tracing) and manipulation tasks (cube palletizing). The objectives focus on managing linear-motion precision, optimizing trajectories through safety points, and implementing conditional logic based on digital sensors.

---

## ⚙️ Overview and Features
The UR5 robot program provides the following key features:

* **Automatic Task Selection**: The robot identifies, via digital inputs (`DI[1], DI[2], DI[3]`), which letter to build: **L, i, or H**.
* **Marker Outline Tracing**: The robot picks up a writing tool and executes precise trajectories to draw the letter on the work plane.
* **Cube Palletizing**: After tracing, the robot moves to the manipulation phase, sequentially picking up cubes and placing them in predefined locations to fill the outline.
* **Optimized Motion**: Use of `MoveJ` for fast movements and `MoveL` for precise linear tracing.
* **Gripper Management**: Synchronizing gripper open/close with wait times (`Wait`) for object stability.
* **Modular Structure**: The code is split into subprograms (e.g., `Desen_L`, `Umple_P1_L`), making maintenance and debugging easier.

---

## 🛠️ Technologies and Tools Used
* **URSim (Universal Robots Simulator):** Essential environment for testing programs without risking damage to a physical robot.
* **UR5 Robotic Arm:** The simulated industrial model with 6 degrees of freedom.
* **URScript / Polyscope:** Used for writing the control logic and motion sequences.
* **Oracle VirtualBox:** The platform used to run the URSim virtualization environment.

---

## 🧠 Program Logic and Implementation
The project is structured modularly to manage the complexity of the process:

1. **Initial Setup**: Defining the work plane, the tool center point (**TCP**) calibrated at approximately 0.270 m, and the payload parameters.
2. **Drawing Subprograms (`Desen_X`)**:
    * Movements toward the marker area.
    * Tracing the outline through X, Y, Z coordinates using precise linear movements.
3. **Palletizing Subprograms (`Umple_PX_X`)**:
    * Pick-up cycles from the feeding area.
    * Movement through intermediate safety waypoints to avoid collisions.
    * Releasing the cube at the final location inside the letter.

---

## 🚀 Running and Usage
1. **Installation**: Make sure you have **VirtualBox** and the **URSim** image correctly configured.
2. **Load Project**: Download the `proiecFinalHILT_cri.script` and `proiecFinalHILT_cri.urp` files into the virtual machine.
3. **Open**: In the Polyscope interface, go to "Run Program" and open the `.urp` file.
4. **Activation**: Set the digital inputs in the I/O tab to choose the desired letter and press **Start**.

---

## 👨‍💻 Author
Project by **Nicolae-Bogdan Proaspătu**
*Automation and Applied Informatics student, Technical University of Civil Engineering Bucharest*
Academic year 2024–2025.

---

## ⚖️ License
Created for educational use as part of the **Industrial Robot Control** course.
