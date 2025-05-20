# Virtual Machine Architecture

The Telltale Tool engine runs game logic on a custom virtual machine (VM) designed to execute compiled **Lua bytecode** (`.luac`) scripts.

This VM interacts closely with core engine systems such as dialogue, scenes, user input, and save/load mechanisms.

---

## 🧠 Lua Runtime Characteristics

- Executes precompiled Lua bytecode in a custom or modified Lua interpreter.
- Lua drives gameplay logic, cinematics, interaction, and UI.
- Subtitles and localization strings are dynamically defined in Lua scripts.
- Lua-based scripting often integrates with runtime systems like camera, dialogue, and sound.

---

## 🛠 Integration with Native Systems

The VM bridges high-level scripting and low-level C++ engine systems by exposing native functionality through Lua bindings.

Common examples:
- Scene and state transitions
- Dialogue trees and event triggers
- QTE sequences and logic branching

Lua scripts appear to orchestrate nearly all gameplay behavior.

---

## 📋 Logging Hooks & Source Path Usage

A notable internal function located at **offset `0x1ECAC0`** — which has been user-labeled as `TT_LogShutdown()` — logs subsystem shutdown events along with the originating `.cpp` file path (e.g., `Scene.cpp`, `GameLoop.cpp`, etc.). These strings are embedded in the `.rdata` section and were likely added using `__FILE__` or similar macros for debug logging.

Although these are not executable code, they are valuable indicators of how the engine source was structured and which subsystems exist.

Example subsystem file references:
```

c:\buildbot\working\2015\_07\_Minecraft\Engine\GameEngine\AnimationManager.cpp
c:\buildbot\working\2015\_07\_Minecraft\Engine\GameEngine\SaveLoadManager.cpp

```

This reinforces the modular design of the engine and hints at its internal component boundaries.
