# Desi Rider - Project Submission Report

## Team Name

CABIN

## Team Members

1. Aniket Patil (124cs0081)
2. Sumit Kumar (124cs0085)
3. Ankur Dhanraj (124cs0087)
4. Lakshya Patidar (524cs0008)

## 1. Project Title

Desi Rider: A 2D Physics-Based Endless Offroad Game

## 2. Abstract

Desi Rider is a 2D side-scrolling offroad driving game developed in Godot 4 using GDScript. The player controls a vehicle over procedurally generated terrain, collects coins and medals, performs jumps/backflips, and uses nitro strategically to maximize score and distance. The game demonstrates practical implementation of physics simulation, procedural content generation, event-driven UI, scoring systems, and persistent settings management.

## 3. Problem Statement

Traditional static-level driving games lose replay value quickly once players memorize tracks. The objective of this project is to design a lightweight game architecture that creates a replayable endless experience through runtime-generated terrain while maintaining smooth vehicle control, clear HUD feedback, and robust menu/settings flow.

## 4. Objectives

- Build an endless gameplay loop using procedural terrain generation.
- Implement physically believable vehicle movement using rigid bodies and wheel dynamics.
- Provide rewarding progression via distance, collectibles, and stunt scoring.
- Add player quality-of-life systems: pause menu, settings, and persistent configuration.
- Organize project modules for maintainability and future feature extensions.

## 5. Technology Stack

- Game Engine: Godot 4.x
- Language: GDScript
- Rendering: 2D (GL Compatibility)
- Platform Setup: Desktop-focused project configuration with input support for keyboard and gamepad

## 6. Core Gameplay Flow

1. Player starts from the main menu.
2. Game scene loads with car and terrain initialized.
3. Terrain sections are generated around the camera as the player advances.
4. Player accelerates, balances the car, uses brakes and nitro, and collects items.
5. Score updates continuously from distance, coins, jumps, backflips, and medals.
6. Crash or surrender triggers game-over state and summary screen.
7. Player can retry instantly or return to main menu.

## 7. Major Modules and Implementation

### A. Vehicle Physics and Control

- Uses `RigidBody2D` for realistic movement.
- Rear and front wheels receive torque impulses based on input.
- Mid-air control is supported through rotational torque.
- Nitro applies additional directional force and consumes a limited resource.
- Collision of the rider head with obstacles/terrain triggers game-over.

### B. Procedural Terrain System

- Terrain height is generated from `FastNoiseLite` (simplex noise).
- World is divided into fixed sections; only nearby sections are active.
- Old far-away sections are freed to optimize memory/performance.
- Difficulty naturally scales over distance via slope and noise influence.

### C. Items and Rewards

- Coins increase score.
- Nitro pickups refill nitro meter.
- Medals act as milestone rewards and contribute bonus points.
- Rocks and environmental objects increase challenge and variation.

### D. Scoring System

The total score combines:

- Distance score
- Coin score
- Jump score
- Backflip score
- Medal bonus

This multi-factor model rewards both survival and skillful play.

### E. UI and Game State Flow

- Main menu: Play, Settings, Exit.
- In-game HUD: live score and nitro bar.
- Pause menu: Resume, Settings, Surrender, Exit to main menu.
- Game-over screen: animated summary and final score with replay option.

### F. Settings and Persistence

- Music and FX volumes are independently adjustable.
- Fullscreen and HDR toggles are available.
- Configuration is stored in `user://config.cfg` and loaded at startup.

## 8. Key Programming Concepts Demonstrated

- Procedural generation for endless content
- Real-time rigid-body physics and force application
- Signal-based decoupled communication between gameplay and UI
- Scene instantiation and lifecycle management in Godot
- Persistent configuration handling via file I/O and JSON

## 9. Challenges Faced and Solutions

- Challenge: Maintaining smooth gameplay in an endless world.
  - Solution: Keep only nearby terrain sections loaded and free distant sections.

- Challenge: Balancing realism and playability in vehicle controls.
  - Solution: Tune torque, rotational impulse, and nitro force for responsive handling.

- Challenge: Preventing repetitive gameplay.
  - Solution: Add dynamic terrain, collectibles, stunt scoring, and random obstacles.

## 10. Future Scope

- Add leaderboard and high-score persistence.
- Introduce additional vehicle types with unique handling.
- Expand localization to more languages.
- Add weather/day-night variations and new biome themes.
- Create mission/challenge mode in addition to endless mode.

## 11. Division of Work (Team of Four)

### Member 1: Aniket Patil (124cs0081) - Gameplay and Vehicle Physics Lead

Responsibilities:

- Designed and implemented vehicle movement logic.
- Integrated acceleration, braking, tilt control, and nitro behavior.
- Implemented crash detection and game-over trigger conditions.
  Deliverables:
- Stable and responsive core driving mechanics.

### Member 2: Sumit Kumar (124cs0085) - Procedural Terrain and World Systems Lead

Responsibilities:

- Implemented section-based terrain generation using noise.
- Managed dynamic section creation/removal for endless gameplay.
- Added item/obstacle placement logic tied to terrain sections.
  Deliverables:
- Infinite terrain system with scalable difficulty and performance control.

### Member 3: Ankur Dhanraj (124cs0087) - UI/UX and State Flow Lead

Responsibilities:

- Built menu, HUD, pause, settings, and game-over interfaces.
- Connected score and nitro updates to the HUD.
- Implemented UI focus navigation and menu state transitions.
  Deliverables:
- Complete user interface and polished game-state navigation.

### Member 4: Lakshya Patidar (524cs0008) - Systems Integration, Assets, and Testing Lead

Responsibilities:

- Integrated audio buses, project settings, and configuration save/load.
- Managed asset organization (sprites, particles, fonts, and scene resources).
- Performed integration testing and gameplay balancing.
  Deliverables:
- Cohesive final build with stable settings persistence and consistent polish.

## 12. Testing Summary

- Functional testing for menu flow and scene transitions.
- Input testing for keyboard controls and pause behavior.
- Gameplay testing for score increments, item collection, and nitro usage.
- Crash testing for game-over state and restart/exit paths.
- Settings testing for persistence across relaunches.

## 13. Conclusion

Desi Rider successfully demonstrates a complete 2D game pipeline: from physics-driven control and procedural generation to UI flow and user settings persistence. The project is modular, replayable, and suitable as a course submission showing practical game development and teamwork.
