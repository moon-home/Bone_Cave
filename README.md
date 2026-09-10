# Bone Cave — Quest 2 VR Action Game Prototype

A modular, event-driven VR action prototype built in Unity 2022.3 (Android/Quest 2 deployment) using the XR Interaction Toolkit. Designed for an **AI Agentic Workflow** (Claude Code / Roo Code / Cursor), maintaining a strict separation between core script architecture and art/audio asset pipelines.

---

## Agentic AI Rules & Context (For Claude Code / AI Agents)

When operating as an AI agent writing code for this repository, adhere strictly to the following architectural conventions:

* **Decoupled Architecture:** Build systems using interfaces (`IWeapon`, `IDamageable`) and Unity Events (`OnFire`, `OnReload`). Do not hardcode direct visual dependencies into core logic.
* **Primitive-First Prototyping:** Implement core mechanics using Unity primitives (cubes, spheres, rays) before wiring up final 3D meshes or audio clips.
* **Inspector Fields:** Expose serializable references (`[SerializeField]`) for mesh swapping, spawn points (`Transform firePoint`), and interaction references (`InputActionProperty`).
* **Input System:** Use Unity's **Input System Package** and **XR Interaction Toolkit** (`ActionBasedController`, `XRI RightHand/Activate`).
* **Unity Project Constraints:** Never edit scene files (`.unity`) or prefab configurations (`.prefab`) directly via code agents unless generating serialized C# components. Maintain single responsibility per C# script.

---

## 7-Day Implementation Roadmap & Progress Tracker

**Phase 1: Pure Mechanics & Architecture**

* [x] **Day 1: Player Rig & Interaction Framework**
* Set up XR Origin, hand containers, and controller input bindings.


* [ ] **Day 2: Core Weapon Logic (In Progress — Step 3)**
* [x] Basic `CrossbowController.cs` input reading and reload cooldown structure.
* [x] Dual-mesh state handling (Relaxed State vs. Cocked State swap).
* [ ] Bolt projectile instantiation & physics force impulse on fire.


* [ ] **Day 3: Target & Enemy System Primitives**
* Implement `IDamageable` interface, target colliders, and health/hit logic.



**Phase 2: Game Loop & State Management**

* [ ] **Day 4: Game Manager & Wave Logic**
* State machines (Menu, Active, Game Over) and round/wave timer loops.


* [ ] **Day 5: VR Haptics & Feedback Pipeline**
* Unified `HapticManager` and `AudioManager` hooked to game events.



**Phase 3: Asset Swap & Polishing**

* [ ] **Day 6: Mesh & Visual Asset Swap**
* Relink primitive placeholders to final Crusader Castle `.fbx` models and environment assets.


* [ ] **Day 7: Audio, Particle Polish & Build Verification**
* Sound effects, impact particles, and Quest 2 Standalone APK build verification.



---

## Development Environment Setup

* **Unity Version:** `2022.3.9f1` (Android Build Support installed)
* **IDE:** VS Code with **C# Extension** (OmniSharp mode enabled)
* **Required Unity Packages:**
* `XR Interaction Toolkit`
* `Input System`
* `Visual Studio Editor` (v2.0.20+)



### Quick Start

1. Clone the repository:
```bash
git clone https://github.com/YOUR_USERNAME/Bone-Cave.git

```


2. Open the top-level project folder in **Unity Hub** (`2022.3.9f1`).
3. In Unity, open **Window > Package Manager** and ensure all dependencies compile.
4. In VS Code, open the repository root folder to edit C# scripts in `Assets/Scripts/`.

---