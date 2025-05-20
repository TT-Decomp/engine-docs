# Telltale Engine Documentation

This repository serves as the central hub for all technical documentation related to the proprietary engine used in Telltale Games titles — with a primary focus on **Minecraft: Story Mode – Season 1 Complete Edition**.

Our goal is to provide an in-depth, organized reference of the engine’s internal systems, scripting language, asset formats, and runtime behavior, to aid reverse engineering, tool development, and preservation efforts.

---

## 📚 Index

### 🧠 Core Architecture
- [Engine Overview](docs/core/engine-overview.md)
- [Initialization & Main Loop](docs/core/main-loop.md)
- [Virtual Machine Structure](docs/core/virtual-machine.md)
- [Script Execution Pipeline](docs/core/script-runtime.md)

### 🗃️ File Formats
- [TTARCH Archives](docs/formats/ttarch.md)
- [Lua Bytecode (`*.luac`)](docs/formats/luac.md)
- [Textures (`*.d3dtx`)](docs/formats/d3dtx.md)
- [Audio Files (`*.fsb`, `*.bnk`)](docs/formats/audio.md)
- [Scene Graph Data (`*.landb`, `*.scene`, etc.)](docs/formats/scene-data.md)

### 🧩 Game Systems
- [Dialogue System](docs/systems/dialogue.md)
- [Inventory/State Tracking](docs/systems/state.md)
- [Camera & Cinematics](docs/systems/camera.md)
- [Quick-Time Events (QTEs)](docs/systems/qte.md)

### 🛠 Tools & Pipelines
- [Build & Packaging Tools](docs/tools/ttbuilder.md)
- [Editor Tooling](docs/tools/editor.md)
- [Localization Pipeline](docs/tools/localization.md)

---

## ✅ Status

| Section                | Status       |
|------------------------|--------------|
| Engine Overview        | 🟡 In Progress |
| Lua Bytecode           | 🔴 Not Started |
| TTARCH Format          | 🔴 Not Started |
| Dialogue System        | 🔴 Not Started |
| VM Internals           | 🔴 Not Started |

(✅ = Mostly Complete, 🟡 = Work in Progress, 🔴 = Not Started)

---

## ✍️ Contribution Guide

We welcome contributions! To help:

1. Fork the repository.
2. Use existing markdown files or create new ones under `docs/`.
3. Follow naming conventions and keep sections modular and clear.
4. Submit a pull request with a short summary of your changes.

---

## ⚠️ Disclaimer

This documentation is for **educational and research purposes only**.  
We do **not** distribute proprietary game content or binaries. All information has been derived via legal reverse engineering practices under fair use.

---

## 🧵 Related Repositories

- [mcs1-decomp](https://github.com/TT-Decomp/mcs1-decomp) – Decompiled logic and runtime structures

---

*Let’s preserve Telltale’s history, one doc at a time.*

—
**TT-Decomp Team**
