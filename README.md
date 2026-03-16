## 🎮 How to Play

**Goal:** Storm the castle and kill everybody before the timer runs out to win!

* **Movement:** Use `W` `A` `S` `D` to move.
* **Combat:** Aim with the mouse, and shoot spells with `Left Click`.
* **Mana:** "Reload" your mana points with `Right Click`.
* **Pro-Tips:** For better aiming, stand still and shoot slower. Take a breather in the sandy areas—there are no enemies there!

---

## 🎯 Design Focus

**Recoil** is the prototype's core design pillar and shapes every player decision. 

* **Movement:** Transform-based, ensuring motion is deterministic and recoil remains predictable.
* **Spells:** Prefab-driven, meaning damage, lifetime, and spread can be tuned without changing core code.
* **Enemies:** Behavior uses raycast line-of-sight to spawn projectile prefabs, keeping combat tight and performant. 
* **Environment & UI:** Tilemaps and a UI layer updated by gameplay scripts allow level and HUD iteration to happen quickly.

---

## ⚙️ Technical Implementation

I prioritised **WebGL** stability and rapid iteration by avoiding heavy physics and complex camera systems. Manual collision handling and prefab instantiation made features fast to prototype, and audio layering provided dramatic weight without needing a large state machine. 

> **Trade-offs:** The main technical trade-offs are runtime allocations from frequent `Instantiate` calls and predictable enemy patterns that reduce replay tension.

---

## 📈 Results and Next Steps

Playtests showed the recoil mechanic delivers skillful satisfaction, and the timer adds genuine drama. However, players tend to discover safe patterns over repeated runs. 

**Planned Improvements:**
* Implement **object pooling** to remove Garbage Collection (GC) spikes.
* Add **enemy behaviour variety** and dynamic spawns to break predictable routines.
* Introduce **gamepad support** for broader accessibility.

---

## 📜 Credits & Assets

* **Made by:** Christopher Kendrick
* **Music:** ["Hitman" by Kevin MacLeod](https://incompetech.com) | Licensed under Creative Commons: By Attribution 4.0 License.
* **Audio/Visuals:** [Tiny Dungeon & Impact Sounds by Kenney](https://kenney.nl)
