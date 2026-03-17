## 🎮 How to Play

**Goal:** Storm the castle and kill everybody before the timer runs out to win!

* **Movement:** Use `W` `A` `S` `D` to move.
* **Combat:** Aim with the mouse, and shoot spells with `Left Click`.
* **Mana:** "Reload" your mana points with `Right Click`.
* **Pro-Tips:** For better aiming, stand still and shoot slower. Take a breather in the sandy areas—there are no enemies there!

---

## 🎯 Design Focus

**Recoil** is the prototype's core design pillar and shapes every player decision. 

* **Pacing:** Pacing is driven organically by level design. Safe zones (like the sand) simply lack enemy placement, giving players a natural breather to manage their recoil and mana.
* **Predictability:** Transform-based movement ensures player motion is deterministic, which keeps the core recoil mechanic feeling fair and predictable.

---

## ⚙️ Technical Implementation

I prioritised **WebGL** stability and rapid iteration by avoiding heavy physics engines and complex camera systems.

* **Dynamic Recoil Math:** A recoil variable increases whenever the player moves or shoots. When a spell is fired, this variable determines how far "off" the shot will deviate from the mouse's exact aim point. A timer constantly decays this recoil variable, and the decay rate accelerates when the player stops moving and shooting.
* **Combat Systems:** Spells are prefab-driven, allowing independent tuning of damage and spread without touching core code. Characters use lightweight variables to track health internally rather than relying on UI-heavy health bars.
* **Raycasting Enemy Logic:** Enemies use raycasting to determine line-of-sight. Breaking LOS triggers a basic finite state machine (Idle → See Player → Shoot) that spawns projectile prefabs, keeping the loop tight and performant.
* **Environment & UI:** Tilemaps and a UI layer updated by gameplay scripts allow level and HUD iteration to happen quickly.

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
