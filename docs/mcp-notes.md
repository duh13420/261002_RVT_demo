# Revit / MCP notes

This repo currently uses pyRevit as the direct Revit automation layer because a
native `.rvt` file can only be produced by Autodesk Revit or compatible Autodesk
APIs running in a licensed Revit environment.

## Suggested MCP flow

1. Start Revit locally.
2. Open a blank project.
3. Run the pyRevit command in this repo to generate and save the demo model.
4. Use your Revit MCP server to inspect the active document or the saved RVT.

If your MCP server supports invoking named Revit commands, register the pyRevit
command path below as the generation step:

```text
pyrevit/DemoModel.extension/Demo.tab/Model.panel/Create Demo Project.pushbutton/script.py
```

## Why there is no placeholder RVT

An `.rvt` file is a proprietary binary Revit project. Creating an arbitrary file
with an `.rvt` extension would not be useful and could mislead downstream Revit
or MCP tests. This repository therefore stores the reproducible source command
that creates a real RVT inside Revit.
