# Engine Overview

The Telltale Tool engine — used in titles such as *Minecraft: Story Mode – Season 1 Complete Edition* — is a modular, script-driven architecture centered around a custom virtual machine and a Lua-based runtime.

This document provides a broad overview of the engine's core design, logging behavior, and third-party dependencies.

---

## 🧱 Architecture Summary

- Modular subsystems (e.g., Scene, Dialogue, Lua VM, Animation, Save/Load).
- Heavy reliance on Lua scripting for logic, events, UI, and localization.
- Each system appears to follow a consistent interface and shutdown protocol.
- Custom tooling likely built using C++ with source references retained in strings.
- Built using a proprietary toolchain with embedded references to build environments.

---

## 🧩 Debug Logging and Source Path Metadata

A notable engine behavior is the embedding of **source file path strings** (e.g., `.cpp` files) in the binary's `.rdata` section. These are **not** compiled source code — they are debug strings, likely inserted using macros such as `__FILE__`, and are used by internal logging systems.

These paths are referenced when engine systems are shut down. This logging function is located at **offset `0x1ECAC0`**, which has been named:

```

TT_LogShutdown() — user-defined label in IDA

```

This function logs messages that include the path of the source file associated with the subsystem being shut down. This behavior provides valuable insight into the structure of the engine and its components.

### Example `.cpp` Paths Found in `.rdata`:

```

c:\buildbot\working\2015\_07\_Minecraft\Engine\GameEngine\GameEngine.cpp
c:\buildbot\working\2015\_07\_Minecraft\Engine\GameEngine\Scene.cpp
c:\buildbot\working\2015\_07\_Minecraft\Engine\GameEngine\SaveLoadManager.cpp
c:\buildbot\working\2015\_07\_Minecraft\Engine\GameEngine\GameLoop.cpp
c:\buildbot\working\2015\_07\_Minecraft\Engine\GameEngine\Http\_Curl.cpp

```

These strings reveal a modular architecture and give hints as to the organization of the original source code.

---

## 🔗 Third-Party Libraries

Strings in the binary also show that the engine statically links or includes the following library versions:

- **libcurl 7.38.0**
```

c:\buildbot\working\2015\_07\_Minecraft\Engine\GameEngine\ThirdPartyShipping\curl-7.38.0\lib\vtls\openssl.c

```

- **OpenSSL 1.0.1j**
```

c:\buildbot\working\2015\_07\_Minecraft\Engine\GameEngine\ThirdPartyShipping\openssl-1.0.1j\ssl\ssl\_lib.c

```

These references help date the engine and provide insight into the dependencies used in networking and security features.

---

## 🚧 Ongoing Goals

- Reconstruct the subsystem lifecycle (initialization, shutdown).
- Catalog all source file references embedded in `.rdata`.
- Explore how Lua integrates with and controls each system.
- Identify additional diagnostic/logging behaviors.
