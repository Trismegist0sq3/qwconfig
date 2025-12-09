---

# QWConfig

Modular configuration system for ezQuake / QuakeWorld

## Overview

This repository contains a structured, modularized QuakeWorld configuration designed for ezQuake-based clients.
Instead of maintaining a single monolithic configuration file, settings are separated into logically grouped files for clarity, manageability, and version control.

The configuration is loaded through a central `autoexec.cfg`, which initializes the client and imports every component in the correct order.

This structure makes it easy to update or replace individual sections without affecting unrelated settings, and helps track changes in configuration history through Git.

---

## How It Works

The root of the configuration contains:

* `autoexec.cfg` – the master loader
* `cfg/` – a directory containing grouped configuration files

The autoexec file executes each modular configuration in sequence:

```
exec cfg/aliases.cfg
exec cfg/binds.cfg
exec cfg/client.cfg
exec cfg/enemy.cfg
exec cfg/graphics.cfg
exec cfg/hud.cfg
exec cfg/input.cfg
exec cfg/misc.cfg
exec cfg/player.cfg
exec cfg/render.cfg
exec cfg/sound.cfg
exec cfg/system.cfg
exec cfg/uservar.cfg
exec cfg/video.cfg
```

Each file is responsible for one category of settings, keeping concerns separated and configurations readable.

---

## Configuration File Roles

Below is a summary of what each file contains:

### `aliases.cfg`

Contains command aliases, weapon scripts, automation bindings, and connect behaviors.

### `binds.cfg`

Key and mouse button bindings for movement, weapon control, interaction, recording, and utility functions.

### `client.cfg`

Client behavior settings, networking behavior, game logic preferences, and interaction mechanics.

### `enemy.cfg`

Rules for enemy models, colors, skins, and visibility preferences.

### `graphics.cfg`

Particle system settings, lighting modes, muzzle flash suppression, texture handling, contrast, gamma, and effect-driven tuning.

### `hud.cfg`

HUD layout, indicator ordering, scoreboard positioning, and onscreen informational elements.

### `input.cfg`

Mouse sensitivity values, filtering, pitch/yaw scaling, forward/back movement speeds, and related control parameters.

### `misc.cfg`

Utility configuration values, console behavior, Qizmo directory references, screenshot format, and other ungrouped engine settings.

### `player.cfg`

Player identity configuration — name, colors, team tag, rate, gender, and skin selections.

### `render.cfg`

Rendering effect behaviors such as explosion lights, rocket trails, nail trails, outline mode, shaft behaviors, model rendering, and visual clarity adjustments.

### `sound.cfg`

Sound handling, ambient levels, sampling rate, volume, and static sound suppression.

### `system.cfg`

Engine and file resolution behavior, home directory usage, download rules, scoreboard behavior, and general execution environment adjustments.

### `uservar.cfg`

User-defined variables intended for state tracking, script storage, toggles, and temporary game configuration values.

### `video.cfg`

Display resolution, window position, fullscreen flags, refresh rates, renderer choices, framebuffer usage, and related video backend settings.

---

## Installation & Usage

Place the repository contents in your QuakeWorld configuration directory, typically:

```
~/.ezquake/
```

The `autoexec.cfg` will load automatically when ezQuake starts.
Alternatively, it may be invoked explicitly:

```
+exec autoexec.cfg
```

---

## Why Modular?

This configuration design achieves:

* Cleaner structure
* Easier maintenance
* Better compatibility across client updates
* Trackable configuration history through Git
* Ability to replace or tune individual subsystems without impacting others

For competitive play or experimentation, this makes iteration significantly easier.

---

## Future Enhancements

Planned expansions include:

* Profile-based configs (Duel / FFA / Practice modes)
* Color-coded status echo messages
* Optional presets for “clean competitive visibility” tuning

---

## Notes

This configuration assumes you are familiar with ezQuake directory layout conventions.
If your install stores configs elsewhere, adjust paths accordingly.

---
