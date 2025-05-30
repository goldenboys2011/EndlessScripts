# EndlessScripts

> Scripting language for the [EndlessClient](https://github.com/goldenboys2011/EndlessLauncher)

  [![version](https://img.shields.io/badge/version-2.0-green.svg)](https://github.com/goldenboys2011/EndlessLauncher/releases/tag/2.0)
  [![discord](https://img.shields.io/badge/Discord-join-7289DA.svg)](https://discord.gg/yPpfjwNzVy)
  [![license](https://img.shields.io/badge/License-GPL_3.0-blue.svg)](https://github.com/goldenboys2011/EndlessLauncher/blob/latest/LICENSE)
  
## API

### Structure

```ini
[SCRIPT] "Script Name"

[COMMAND]
  [NAME]
  [ONRUN] "JavaScript code"

[HACK]
  [NAME] Hack name shown in GUI
  [COLOR] Minecraft color code (§b)
  [ONINIT] "JavaScript code (runs once on load)"
  [ONRUN] "JavaScript code (runs every tick if enabled)"
```

### Custom variables/functions

Variable    | Description
----------- |------------
thePlayer   | Access the local player
mc          | Access all Minecraft-related objects (world, input, etc.)
print       | Print text to the console
MathHelper  | Utility for math functions (sin, cos, etc.)

---

### Example

Default script located at: `/Default.enscript`

```ini
[SCRIPT] "ExampleScript"

[COMMAND]
  [NAME] SayHi
  [ONRUN] "print('Hello from command!')"

[HACK]
  [NAME] AutoJump
  [COLOR] §a
  [ONINIT] "print('AutoJump enabled')"
  [ONRUN] "if (thePlayer.onGround) { thePlayer.jump(); }"
```

---

### Loading Scripts

1. Place `.enscript` files into the `/scripts` folder inside your EndlessClient directory.
2. Scripts load automatically on client launch if formatted correctly.
3. `[HACK]` modules will appear in the GUI and can be toggled.
4. `[COMMAND]` can be called manually through chat.

---

### JavaScript Support

- Uses basic JavaScript (recommended: ES5-style)
- Standard syntax for variables, functions, `if`, `while`, etc.
- No support for imports, `require()`, or async functions
- `[ONRUN]` runs every game tick (~20 times per second)
- All code needs to be in line

> If you need help with the inline please visit [here](https://goldencube.dev/endless)
---

### More Info

See the [Rhino Documentation](https://mozilla.github.io/rhino/) for detailed APIs and advanced usage.

---
