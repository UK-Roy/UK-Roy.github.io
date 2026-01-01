---
title: Task-Space Control of a Medical Manipulator in Isaac Gym
description: PD, task-space, and Jacobian-based IK control of a medical manipulator using GPU-accelerated simulation.
category: hobby
order: 6
year: 2024
role: BioRobotics Course Project
preview: panda.png
video: ""
github: https://github.com/UK-Roy/LLM-based-Reward-based-RL-training
---

## Overview

This project investigates **classical control and task-space manipulation** of a medical robotic arm using **NVIDIA Isaac Gym**, with the goal of understanding the strengths and limitations of analytical controllers before transitioning to learning-based frameworks such as **Isaac Lab**.

The focus is on **simulation-first experimentation**, not sim-to-real transfer, emphasizing control stability, task-space behavior, and GPU-accelerated physics.

---

## Motivation

Modern robotic manipulation research increasingly relies on **reinforcement learning frameworks** (e.g., Isaac Lab).  
However, learning-based methods are best understood when grounded in **classical control baselines**.

This project was designed to:

- Establish a **stable joint-space PD controller**
- Extend control to **task-space (end-effector) objectives**
- Explore **Jacobian-based inverse kinematics (IK)**
- Identify failure modes that motivate **MPC and RL-based approaches**

---

## Simulation Environment

- **Simulator:** NVIDIA Isaac Gym (Preview 4)
- **Physics Engine:** GPU PhysX
- **Platform:** Ubuntu Linux, NVIDIA RTX GPU
- **Robot Model:** Custom medical manipulator (URDF-based)
- **Control Frequency:** Fixed-step GPU simulation loop

The manipulator is evaluated in a constrained workspace resembling **medical tool navigation**, including corridor-like target regions.

---

## Control Pipeline

### 1. Joint-Space PD Control
A classical **PD controller** is applied at the joint level:

\[
\tau = K_p (q_{des} - q) + K_d (\dot{q}_{des} - \dot{q})
\]

This controller ensures:
- Stable simulation
- Correct DOF indexing
- Proper torque application
- Baseline dynamic behavior

**Outcome:**  
Stable but incapable of precise end-effector positioning in constrained task spaces.

---

### 2. Task-Space Control (End-Effector)
The task objective is defined in **Cartesian space**, focusing on the tool tip position.

End-effector error:
\[
e = x_{target} - x_{tip}
\]

The controller attempts to reduce this error indirectly through joint torques.

**Limitation:**  
Pure task-space error without proper Jacobian handling leads to slow convergence and poor constraint handling.

---

### 3. Jacobian-Based Inverse Kinematics (IK)
A differential IK controller is implemented using the manipulator Jacobian:

\[
\dot{q} = J^\top (x_{target} - x_{tip})
\]

This enables:
- Explicit task-space reasoning
- Directional joint updates
- Better alignment with end-effector goals

**Observed Issues:**
- Sensitivity to Jacobian conditioning
- Difficulty near singular configurations
- No explicit handling of joint limits or obstacles

---

## Results

- The robot **successfully moves toward the target**, validating Jacobian-based control.
- However, **precise convergence is not guaranteed**, especially in constrained corridors.
- Oscillations and slow settling occur under PD + IK control.

This behavior is expected and highlights the **fundamental limitations of purely analytical controllers** in complex task spaces.

---

## Key Insights

- PD control is reliable for **stability**, not task completion
- Task-space objectives require **explicit geometric reasoning**
- Jacobian-based IK improves directionality but lacks robustness
- These limitations naturally motivate:
  - Model Predictive Control (MPC)
  - Learning-based policies (RL)

---

## Why This Leads to Isaac Lab

This project serves as a **control-grounded entry point** to Isaac Lab:

- Isaac Gym → understanding physics + control
- Isaac Lab → policy learning on top of validated dynamics

By first exposing controller limitations, the motivation for **reinforcement learning** becomes clear and principled rather than ad hoc.

---

## Images
{% include figure.liquid
  path="assets/img/project_preview/panda.png"
  caption="Panda Robot is pushing an object based on the given reward by the LLaMA2"
  class="img-fluid rounded z-depth-1"
  zoomable=true
%}


---
## Future Extensions

- MPC-based trajectory tracking
- Constraint-aware optimization
- RL policy learning using Isaac Lab
- Human-aware or safety-aware manipulation objectives

---

## Links
- [Code]({{ page.github }})
- [Video]({{ page.video }})

