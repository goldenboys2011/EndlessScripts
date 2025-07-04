# EndlessScripts

> Scripting language for the [EndlessClient](https://github.com/goldenboys2011/EndlessLauncher)

  [![version](https://img.shields.io/badge/version-0.1-green.svg)](https://github.com/goldenboys2011/EndlessScripts/releases/tag/0.1)
  [![discord](https://img.shields.io/badge/Discord-join-7289DA.svg)](https://discord.gg/yPpfjwNzVy)
  [![license](https://img.shields.io/badge/License-GPL_3.0-blue.svg)](https://github.com/goldenboys2011/EndlessScripts/blob/main/LICENSE)
  
## API

### Structure

```ini
[SCRIPT] "Script Name"

[COMMAND]
  [NAME]
  [ONRUN] "JavaScript code"

[HACK]
  [NAME] Hack name shown in GUI
  [COLOR] Minecraft color code for the HUD (E.x "§b")
  [ONINIT] "JavaScript code (runs once on load)"
  [ONRUN] "JavaScript code (runs every tick if enabled)"
```

### Custom variables/functions

Variable    | Description
----------- |------------
thePlayer   | Access the local player
theWorld    | Acces to world related stuff
mc          | Access all Minecraft-related objects (world, input, etc.)
print       | Print text to the console
MathHelper  | Utility for math functions (sin, cos, etc.)

---

### Example

Default script located at: `/Default.enscript`

```ini
[SCRIPT] "goldens Default Script"

[COMMAND]
  [CMDNAME] "example"
  [ONCMDRUN] "java.lang.System.out.println('command activated')"

[HACK]
  [NAME] "swing-every-2s"
  [ONINIT] "var swingTimer = 0;"
  [ONRUN] "swingTimer++; if (swingTimer >= 40) { thePlayer.swingItem(); java.lang.System.out.println('Swung hand at tick: ' + swingTimer); swingTimer = 0; }"
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

### API Interaction with Game:

- Anything with minecraft, available through `mc` variable (full list available [here](https://github.com/goldenboys2011/EndlessScripts/blob/main/MCLIST.md))
- All player related functions and variables through `thePlayer` variable (full list available [here](https://github.com/goldenboys2011/EndlessScripts/blob/main/MCLIST.md))

---

### More Info

See the [Rhino Documentation](https://mozilla.github.io/rhino/) for detailed APIs and advanced usage.

---
