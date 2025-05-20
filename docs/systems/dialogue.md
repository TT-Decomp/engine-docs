# Dialogue & Localization System

Telltale's dialogue system is tightly integrated with their scripting engine, with **Lua scripts** playing a central role in:

- Defining dialogue flows
- Handling branching and conditions
- Triggering animations, sounds, and camera changes

## 📋 Subtitle & Localization Handling

Interestingly, localization strings and subtitles are **not** managed via static resource files or localization-only databases. Instead, they are embedded and handled **within Lua scripts** themselves.

This implies:
- Localization and dialogue data are script-driven
- Dynamic branching can include translated strings at runtime
- Subtitle timing may be influenced directly by script timing/events

This approach suggests a tight coupling between gameplay logic and localization assets.

---

*Additional notes will be added as we reverse more subtitle & localization script examples.*