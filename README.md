# 261002_RVT_demo

This repository contains a small pyRevit command that creates a real demo Revit
project from an open Revit session.

The Codex environment used to prepare this repo does not include Autodesk Revit,
so it cannot generate a native `.rvt` file directly. No fake `.rvt` file is
included. Instead, run the included pyRevit command on a machine with Revit to
create the real demo model.

## What the demo command creates

- Project Information fields for a demo project.
- Two levels.
- A simple rectangular room/building shell.
- Walls, floor, door, and windows when matching family symbols exist.
- Grid lines.
- A floor plan view and a sheet.
- A text note in the generated plan.
- A saved `.rvt` file under your Windows Documents folder.

Default output:

```text
%USERPROFILE%\Documents\261002_RVT_demo_output\261002_RVT_demo_project.rvt
```

## Requirements

- Autodesk Revit.
- pyRevit installed and attached to the same Revit version.
- A blank Revit project open before running the command.

## Install the pyRevit extension

From this repository root, run:

```powershell
pyrevit extensions add 261002_RVT_demo "$PWD\pyrevit\DemoModel.extension"
pyrevit reload
```

If `pyrevit` is not available in PowerShell, add the extension folder manually in
pyRevit:

1. Open Revit.
2. Open pyRevit settings.
3. Add this folder as an extension:

   ```text
   pyrevit\DemoModel.extension
   ```

4. Reload pyRevit.

## Generate the real RVT file

1. Open Revit.
2. Create or open a blank project.
3. In the pyRevit ribbon, open `Demo > Model`.
4. Click `Create Demo Project`.
5. The script modifies the active document and saves it to:

   ```text
   %USERPROFILE%\Documents\261002_RVT_demo_output\261002_RVT_demo_project.rvt
   ```

## Existing Revit/MCP setup

At the time this repository was checked, the GitHub repository was empty, so
there were no existing Revit add-ins, pyRevit extensions, MCP server files, or
MCP configuration files to preserve.

For MCP-based workflows, point the Revit-side MCP tool at the generated `.rvt`
after running this pyRevit command, or expose this command through the local
Revit automation layer used by your MCP server.
