# REBO — project profile (learning evidence)

**Application repo:** [REBO](https://github.com/LouisLi1020/REBO)  
**Type:** Cross-platform Flutter client (minimal game / utility)  
**Primary goal:** G4 (multi-platform system design)

## Tech stack

| Layer | Technologies |
|-------|----------------|
| UI | Flutter, Dart |
| Targets | iOS, Android, Web, Windows, macOS, Linux |
| State / storage | Feature folders + `storage_service` for local persistence |

## What the app does

- Phase 1: red button interaction, score, haptics, persisted high score
- Roadmap (repo): dual button, food decider — not all shipped

## G4 evidence

- [REBO multi-platform architecture](../goals/G4-system-design-cloud/rebo-multiplatform-architecture.md)

## What I learned

- One Dart codebase for six runners trades binary size for delivery speed on a solo project.
- Feature-folder layout scales better than a flat `lib/screens/` tree when adding mini-apps.
