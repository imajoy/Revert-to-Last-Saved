# Revert to Last Saved — One-Click Scene Revert for Maya

![Maya Tool](https://img.shields.io/badge/Autodesk%20Maya-Tool-blue)
![Python](https://img.shields.io/badge/Python-PySide2%20%2F%20PySide6-blue)
![License](https://img.shields.io/badge/License-Proprietary-red)

<p align="center">
  <img src="Images/Preview.png" alt="Revert to Last Saved Preview" width="92%">
</p>

**Revert to Last Saved** is a Maya utility for quickly returning the current
scene to its last saved state.

Instead of navigating through Maya's file menus, the tool provides a simple
one-click workflow for discarding unwanted changes and reopening the last
saved version of the current scene.

The latest version also adds a safety backup before reverting and restores
the previous camera view and object selection when possible.

## 🛒 Get the Tool

The complete **Revert to Last Saved — One-Click Scene Revert for Maya**
is available on Gumroad.

**[👉 Purchase & Download on Gumroad](https://ajoyp.gumroad.com/l/ckhvds)**

The full source code and commercial tool package are not included in this
public GitHub repository.

> **Commercial Tool**
>
> The complete software package is available through Gumroad.
> This GitHub repository contains product information, documentation,
> installation information, and demonstration materials only.
>
> The full source code and commercial tool package are not included in this
> repository.

---

## Features

### One-Click Revert

Quickly reload the current Maya scene from its last saved state.

No need to manually navigate through:

**File → Open Recent**

### Safety Backup Before Reverting

When the current scene contains unsaved changes, the tool creates a safety
backup of the current scene state before performing the revert.

The backup is saved automatically with a timestamp so the unsaved state can
still be recovered if needed.

### Confirmation Before Revert

When unsaved changes are detected, the tool displays a confirmation dialog
before proceeding.

This helps prevent accidentally discarding work.

### Restore Camera View

The tool stores the current camera position and rotation before reopening the
saved scene and restores the view afterward when possible.

### Restore Selection

The current object selection is stored before reverting.

After the saved scene is reopened, objects that still exist are selected again
when possible.

### Unsaved Scene Protection

If the current Maya scene has never been saved, the tool detects that there
is no saved version to revert to and safely stops the operation.

### Shelf Button

The tool can create a dedicated shelf button on the currently active Maya
shelf for quick access.

The shelf button reloads the tool module before running the revert function.

### PySide Compatibility

The tool uses PySide6 when available and falls back to PySide2 when needed.

---

## Installation

The complete tool is available through Gumroad.

After downloading the tool, make sure `revert_tool.py` is placed somewhere
that Maya can access through its Python path.

Open the **Python Script Editor** in Maya and run:

```python
import importlib

import revert_tool

importlib.reload(revert_tool)

revert_tool.revert_to_last_saved()
