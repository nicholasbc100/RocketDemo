# Rocket Game Starter Guide (Windows + Lenovo Slim 7)

This guide is for building a **pretty, fun rocket simulator** where you launch from Florida and fly to the Moon.

## Recommended stack (best balance for beginners)

- **Game engine:** Unity 6 LTS
- **Language:** C#
- **Why this is best for you:**
  - Easier than C++ for a first serious game.
  - Strong physics and UI tools.
  - Huge number of tutorials and assets.
  - Runs well on a Lenovo Slim 7 if project scope is controlled.

### When to pick Unreal instead

Choose Unreal Engine (C++/Blueprints) only if your #1 priority is ultra-high-end visuals and you are okay with a steeper learning curve and heavier performance requirements.

## Game concept outline

### Core loop
1. Build/select rocket and mission profile.
2. Launch from a Florida pad (e.g., Cape area inspired setting).
3. Ascend to orbit with autopilot available.
4. Execute trans-lunar injection.
5. Coast to Moon and perform lunar orbit insertion.
6. Optional landing/challenges/scoring.

### Player control style
- **Automation-first:** autopilot handles nominal trajectory.
- **Manual override controls:**
  - Pitch / yaw / roll
  - Throttle
  - Stage separation
  - SAS / RCS toggles
  - Time warp
- **Mission panels:** fuel, velocity, apoapsis/periapsis, delta-v, alerts.

## Visual quality without frying your laptop

- Use URP (Universal Render Pipeline) in Unity.
- Keep textures mostly 1K/2K, not 4K everywhere.
- Use baked lighting for static scenes.
- Use post-processing carefully (bloom + color grading, light touch).
- Target **60 FPS at 1080p** first.

## 12-week build roadmap

### Weeks 1–2: Foundation
- Create Unity project (3D URP).
- Implement camera system and input mapping.
- Block out launchpad scene.

### Weeks 3–4: Rocket physics MVP
- Basic rocket body + mass + thrust model.
- Gravity + drag approximation.
- Stage system and fuel burn.

### Weeks 5–6: Guidance + autopilot
- PID-like attitude stabilization.
- Autopilot ascent script (gravity turn profile).
- Orbital parameter readouts.

### Weeks 7–8: Moon transfer
- Two-body patched-conic simplification.
- Injection burn planning UI.
- Lunar encounter and orbit insertion logic.

### Weeks 9–10: UI/UX polish
- Flight HUD and warnings.
- Mission timeline and checklists.
- Accessibility options (sensitivity presets, larger text).

### Weeks 11–12: Performance + release prep
- Profiling and frame-time optimization.
- Audio + particles + finishing pass.
- Build playable demo.

## Minimal technical architecture

- `RocketController` (thrust, staging, fuel)
- `GuidanceComputer` (autopilot modes)
- `OrbitCalculator` (apoapsis/periapsis, transfer checks)
- `MissionManager` (phase progression)
- `HUDController` (instruments and alerts)

## Useful starter assets/tools

- Unity Input System
- Cinemachine
- TextMeshPro
- Unity Profiler + Frame Debugger
- Optional: procedural skybox + volumetric clouds package

## First playable milestone (what to build first)

A vertical slice where the player can:
- Launch from Florida pad
- Reach a stable Earth orbit
- Trigger a guided Moon transfer burn
- See a cinematic Moon flyby

If this works smoothly, you can expand into full landing gameplay.

## Quick setup checklist (Windows)

1. Install Unity Hub + Unity 6 LTS.
2. Install Visual Studio 2022 with Unity workload.
3. Create a 3D URP project.
4. Set up Git + GitHub repo.
5. Commit after every small milestone.
6. Keep a task board (Notion/Trello/GitHub Projects).

## Reality check on language choice

If your goal is to **actually finish** a polished game:
- Start with **C# + Unity**.
- Add realism gradually.
- Avoid overbuilding physics in week 1.

A completed "very good" game beats an unfinished "perfect" simulator.
