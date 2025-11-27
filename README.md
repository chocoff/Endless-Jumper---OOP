# Documentation needs to be updated
## PDF Report on this project (which includes demonstrations) is provided [in the project section of my LinkedIn profile](https://www.linkedin.com/in/fernando-rojaschoco/)
## 🚀 Skylimit: An Endless 2D Pixel-Art Jumper

Skylimit is a challenging and engaging 2D Pixel-Art endless jumper game where players must continuously jump from platform to platform, ascending to achieve the highest possible score. Inspired by popular titles like *Doodle Jump*, the game offers a smooth and responsive gameplay experience through performance optimization in C++.

---

## ✨ Key Features

* **Endless Jumper Gameplay:** Players control a character that auto-jumps, soaring over procedurally generated platforms while avoiding obstacles.
* **Progressive Difficulty:** The challenge increases as the player advances, with features like progressively spaced platforms and the introduction of moving and spiked platforms.
* **Entity-Component System (ECS):** The game is built using the **ECS architecture** for a highly modular, efficient, and easily maintainable codebase, leveraging **composition over inheritance**.
* **C++ and SFML:** Developed in **C++** using the **Simple and Fast Multimedia Library (SFML)** for graphics, audio, and input handling, ensuring fast execution speed and responsive gameplay.
* **Fluid Camera Movement:** Utilizes **Linear Interpolation** (Lerp) to smooth out camera transitions, which slowly approaches a target position to create a fluid, non-static feel.
* **Parallax Background:** Implements a **vertical parallax effect** using multiple background layers moving at varying speeds to create an illusion of depth in the 2D environment.

---

## 💻 Technical Architecture

The core architecture of Skylimit is based on the **Entity-Component System (ECS)** pattern, separating object identity, data, and logic.

### Key Classes

The system is composed of several key C++ classes:

| Class Name | Purpose |
| :--- | :--- |
| **GameEngine** | The central part of the code; runs assets, renders windows, and manages game state. |
| **EntityManager** | Handles all **Entity** creation, deletion, modification, and updates. |
| **Entity** | Represents a general-purpose object in the game. |
| **Component** | The base class for defining specific aspects of an Entity. |
| **Assets** | Manages a map of all game components that can be perceived, such as animations, textures, sounds, and fonts. |
| **Scene** | Manipulates different scenes in the game (e.g., updates, renders, sets dimensions). |
| **Vec2** | Represents a two-dimensional vector used for physics calculations like collisions, speed, and height. |
| **Action** | Takes keyboard input (simple numbers from SFML) and assigns an action name and state (starting or ending). |

### Component Classes

Components are derived from the base `Component` class and characterize an entity's aspects.

| Component Name | Functionality |
| :--- | :--- |
| **CTransform** | Manages everything related to an entity's position or velocity. |
| **CBoundingBox** | Defines the size and **hitbox** of an object, crucial for collision detection. |
| **CGravity** | Defines how strongly an entity is affected by gravity. |
| **CAnimation** | Defines if an entity has a looping animation (e.g., player movement). |
| **CInput** | Establishes the inputs an entity can receive (e.g., moving right/left for the player). |
| **CKill** | Defines if an entity can kill the player (e.g., spiked logs). |
| **CMove** | Defines an entity that is capable of movement (e.g., moving platforms/logs). |
| **CState** | Defines the current state of the entity (e.g., jumping, falling, moving). |

---

## 🎮 Gameplay and Controls


### Game Objective
The primary goal is to jump from platform to platform to achieve the highest possible score without falling. The game is designed to be endlessly looping.

### Controls

Players can choose between two control settings, adjustable in the settings menu:

* **Arrow Keys**
* **WASD**

In the menu system, controls are:
* **Up/Down** (or **W/S**) to move through options
* **Enter** to select an option.
* **Esc** to return to the previous menu or exit the pause/death menu.
* **R** to restart the game from the death/pause menu.
* **P** to pause the game.

### Obstacles and Challenges

The game features platforms that serve as obstacles:

* **Static Platforms with Spikes:** If the player falls on one of these, they die instantly.
* **Moving Platforms with Spikes:** These move unpredictably, and touching them kills the player.


---

## 🖼️ User Interface & Visuals


* **Menu System:** Features a Main Menu with options to **Start the game**, visit the **Shop**, or access **Settings**.
* **In-Game Shop:** Allows players to purchase and change their character's skin using coins collected during gameplay. The default skin is free.
* **Settings Menu:** Provides options to **Adjust the game volume**, **Enable or disable background music** (character sound effects remain if music is off), and **Change the control settings** (Arrow Keys or WASD).
* **Score and Progress:** The score is constantly updated as the player progresses. Upon losing, the highest score is displayed, encouraging players to beat their record.

---

## 🛠️ Development & Credits

This project was a collaborative effort leveraging advanced game development techniques.

### Core Technologies

* **Language:** C++ 
* **Library:** SFML (Simple and Fast Multimedia Library) 
* **Architecture:** Entity-Component System (ECS) 
* **Development Environment:** Visual Studio Community 2022 
* **Dependency Manager:** vcpkg 
