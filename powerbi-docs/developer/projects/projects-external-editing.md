---

title: Edit Power BI Desktop project files in Visual Studio Code
description: Learn how to edit Power BI Desktop project (PBIP) report and semantic model definitions in Visual Studio Code and reload changes in Power BI Desktop.

ms.topic: how-to
ms.date: 08/17/2026
ms.custom: doc-kit-assisted
ai-usage: ai-generated
ms.reviewer: slammini
ms.author: billmath
author: billmath

#customer intent: As a Power BI developer, I want to edit project files in Visual Studio Code and reload the changes so that I can update report and semantic model definitions without reopening the project.
---

# Edit PBIP files externally 

When you save your work as a [Power BI Desktop projects](projects-overview.md), you save report and semantic model item definitions as individual plain text files in a simple, intuitive folder structure. You can edit these files by using any code editor or external tool.

In this article, you learn:
- How to open [Visual Studio Code](https://code.visualstudio.com/) directly from Power BI Desktop as a convenient entry point for editing project files.
- How Power BI Desktop detects and reloads changes that you make to [Power BI Desktop projects](projects-overview.md) files outside Power BI Desktop.


## Prerequisites for editing PBIP files externally

- Install the August release or later of [Power BI Desktop](/power-bi/fundamentals/desktop-get-the-desktop) on your Windows machine.
- In Power BI Desktop, select **File** > **Options and settings** > **Options** > **Preview features**, enable **Power BI Project (.pbip) save option**, and then restart Power BI Desktop.
- Install [Visual Studio Code](https://code.visualstudio.com/) or another code editor or external tool.
- Save a Power BI Desktop project in PBIP format. For more information, see [Power BI Desktop projects](projects-overview.md).
- Store the PBIP root folder in a location that keeps each project file path under the Windows 260-character path limit.

## Open the PBIP folder in VS Code

Power BI Desktop provides a built-in entry point that opens Visual Studio Code without leaving Power BI Desktop. When you select this button, Visual Studio Code opens with the project folder as the active workspace, so you immediately have access to report and semantic model definition files. 

:::image type="content" source="media/projects-external-editing/external-3.png" alt-text="Screenshot of using VS Code.":::


> [!NOTE]
>VS Code launches the folder path of the opened file, which might be either *.pbip or *.pbir.

## How Power BI Desktop modifies your PBIP files

When you save your work as a Power BI Project (PBIP), Power BI Desktop saves report and semantic model item definitions as individual plain text files in a simple, intuitive folder structure.

Power BI Desktop doesn't write changes you make back into your files until you select **Save**.
> [!NOTE]
> If you work in both Power BI Desktop and an external tool such as Visual Studio Code, save your changes in Power BI Desktop before you edit the files externally.



## How Power BI Desktop detects and reloads external changes 
When you modify PBIP files outside of Power BI Desktop, such as in Visual Studio Code, Power BI Desktop detects those changes and displays an **Apply external changes** banner. Select **Apply external changes** to reload the updated files in Power BI Desktop.

:::image type="content" source="media/projects-external-editing/external-1.png" alt-text="Screenshot of Apply external changes banner.":::


If unsaved changes exist in Power BI Desktop, selecting **Apply external changes** displays a warning dialog indicating that those changes will be overwritten. Selecting **Apply external changes** in the dialog replaces the unsaved changes in Power BI Desktop with the latest contents of the PBIP files. Selecting **Cancel** cancels the reload operation and preserves both the unsaved changes in Power BI Desktop and the unapplied changes in the external files.

:::image type="content" source="media/projects-external-editing/external-2.png" alt-text="Screenshot of overwrite message.":::


>[!NOTE]
> Power BI Desktop and external tools can overwrite each other's changes. Before you switch between them, save or apply the current changes so that both tools use the same project definitions.

### Reload external changes by using the Power BI Desktop Bridge 
You can also reload external changes by using the [Power BI Desktop Bridge](../agentic/power-bi-desktop-bridge-overview.md). 

## Considerations and limitations


- The Power BI Desktop Bridge is currently in **preview**. Features and behavior might change before general availability.
- External editing and reloading apply to PBIP projects, not `.pbix` files.
- Power BI Desktop reloads the entire report, semantic model, or both. It doesn't reload individual files or visuals.
- Power BI Desktop doesn't reload `cache.abf`.
- Reloading resets filters and some user interface elements.
- Not all project files support external editing. During preview, you can't edit `definition.pbir`, `report.json`, `mobileState.json`, or `semanticModelDiagramLayout.json` outside Power BI Desktop.
- If a project contains `unappliedChanges.json`, apply those changes before you edit semantic model expressions externally. Otherwise, Power BI Desktop discards the external expression changes when it applies the pending changes.


## Related Power BI Desktop project and Bridge documentation


- [Power BI Desktop projects overview](projects-overview.md).
- [Power BI Desktop project semantic model folder](projects-dataset.md).
- [Power BI Desktop project report folder](projects-report.md).
- [What is the Power BI Desktop Bridge? (Preview)](/power-bi/developer/agentic/power-bi-desktop-bridge-overview).
- [Power BI Desktop Bridge CLI on npm](https://www.npmjs.com/package/@microsoft/powerbi-desktop-bridge-cli).
