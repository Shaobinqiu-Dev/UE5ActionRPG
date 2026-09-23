# UE5 Action RPG Prototype

A single-player action RPG prototype built with **Unreal Engine 5** and **C++**.
All gameplay logic is implemented in C++, covering character & enemy state machines,
combat, enemy AI, a treasure system, and audio/VFX integration.

## Overview

A personal prototype focused on building a clean, reusable gameplay framework in C++,
rather than shipping a complete game. The goal was to implement the core action RPG
loop end to end: move, fight, defeat enemies, and collect loot.

### Character & Enemy State Machines
- Character states: death / grounded / in air / landing — driving movement, jump,
  hit reaction and death animation transitions
- Enemy states: idle / walk / run / death
- Flying enemies fall to the ground on death instead of floating in place

### Combat
- 3 enemy types (Paladin / Dinosaur / Flying Bug) with 3 / 2 / 1 attack animations
- Player attack and dodge animations with full hit reactions
- Weapon swing trail and hit blood-splash effects

### Enemy AI
- Complete behavior chain: patrol → chase → attack

### Data-Driven Enemy Setup
- Enemy setup abstracted into a Blueprint template: new enemies can be derived from
  the template and tuned through a custom C++-defined panel, instead of being
  hand-assembled item by item

### Treasure System
- Bottles and defeated enemies spawn treasure that descends from the air and lands on the ground
- Pickups include souls and weapons

### UI
- HUD built with UMG: portrait, health bar, stamina bar

### Audio & VFX
- MetaSound-driven audio system (dinosaur roar, player hit and attack sounds)
- Niagara particle effects around treasure items and Pickup Weapons

### Tools
- Rebuilt missing root bones for character models using a Blender add-on

## Tech Stack

| Layer | Tech |
| --- | --- |
| Engine | Unreal Engine 5 |
| Gameplay | C++, Blueprints |
| Gameplay Framework | State machines, AI behavior chain, data-driven templates |
| UI | UMG |
| Audio | MetaSound |
| VFX | Niagara |
| Modeling | Blender |

## Getting Started

### Prerequisites
- Unreal Engine 5.6
- Visual Studio 2022 with the "Game development with C++" workload
- Windows 11

### Build & Run
1. Clone the repository
2. Right-click the `.uproject` file → **Generate Visual Studio project files**
3. Open the generated `.sln`, set the configuration to **Development Editor**, and build
4. Open the `.uproject` in Unreal Editor and press **Play**

## Controls

| Action | Key |
| --- | --- |
| Move | W A S D |
| Attack | Left Mouse Button |
| Dodge | Right Mouse Button |
| Jump | Space |

## Roadmap

- [ ] Additional enemy types and attack patterns
- [ ] Equipment and inventory system
- [ ] Save / load
