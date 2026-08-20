---
title: See What's New in the August 2026 Power BI Update
description: "Discover the August 2026 Power BI update. See the latest feature highlights across Power BI and links to detailed documentation."
author: julcsc
ms.author: juliacawthra
ms.reviewer: ''
ms.service: powerbi
ms.subservice: pbi-fundamentals
ms.custom: intro-whats-new
ms.topic: concept-article
ms.date: 8/18/2026
LocalizationGroup: Get started
no-loc: [Copilot]
ms.collection: ce-skilling-ai-copilot
ai-usage: ai-assisted
---
# What's new in Power BI? August 2026 update

The August 2026 Power BI update introduces new capabilities across reporting, modeling, data connectivity, mobile, and embedded analytics. Highlights include modern visual defaults and the Theme pane reaching general availability, granular semantic model refresh controls, OneLake image URLs in visuals, and expanded slicer and matrix formatting options.

For a quick summary of August features, read on. For a detailed look at these updates and more enhancements, see the [Power BI August 2026 Feature Summary](https://community.fabric.microsoft.com/blog/fbc_pbiupdatesblog/power-bi-august-2026-feature-summary/5348434). You can also [watch the August demos](https://youtu.be/-GcSAYvvv94).

> **Download** the [August 2026 version of Power BI Desktop](https://www.microsoft.com/download/details.aspx?id=58494).

To stay up to date on **bug fixes and improvements** as they're announced, visit the [change log for Power BI Desktop](desktop-change-log.md).

## General

| Feature | Description | Currently in preview |
|---------|-------------|:------:|
| Deprecation of old file picker experience in Power BI Desktop | Starting in October, users with Power BI Desktop versions from March 2026 or earlier will no longer be able to save and share files to OneDrive and SharePoint. Update Power BI Desktop to keep using this functionality. |        |

## Copilot and AI

| Feature | Description | Currently in preview |
|---------|-------------|:------:|
| Updates to required semantic model permissions for Fabric Apps | By the end of August, Fabric App consumers need only Read permission on the underlying semantic model, instead of Build permission. App authors still require Build permission. For more information, see [Create an app connected to a semantic model](/fabric/apps/data-apps-template). |        |
| Copilot Summary and Copilot Narrative can now read visuals hidden behind bookmarks | Copilot Summary and the Copilot Narrative visual can now read visuals that are hidden by default and revealed by a display-only report bookmark. RLS and OLS permissions remain enforced. For more information, see [Summarize a report with Copilot](../explore-reports/copilot-pane-summarize-content.md) and [Create a narrative visual with Copilot for Power BI](../create-reports/copilot-create-narrative.md). |        |

## Reporting

| Feature | Description | Currently in preview |
|---------|-------------|:------:|
| Modern visual defaults and customize themes formatting panes (Generally Available) | New reports start with the Fluent 2 base theme. Use the Theme pane to set a base theme, adjust color palettes, change text styles, set visual and page properties, and import or export custom themes in Desktop or on the web. Font overrides are removed from the base theme so the Text section now applies consistently across all visuals. For more information, see [Visual defaults in Power BI reports](../create-reports/power-bi-reports-visual-defaults.md). |        |
| Date picker for Slicer visual (Generally Available) | Date pickers support relative selections that roll forward with time, a calendar, and a slider for manual date range or single-date selection. A new **Single date** setting under **Visual** > **Slicer settings** > **Selection controls** restricts the slicer to one date at a time. Selections can also be cleared from a header icon. For more information, see [Slicers in Power BI](../visuals/power-bi-visualization-slicers.md). |        |
| Center value for donut chart (Generally Available) | Donut charts can display a value in the center without an overlaid card. Configure value format, display units, font, optional labels, images, and background in the formatting pane. The center value updates automatically with filtering, cross-highlighting, drill-down, and slice selection. For more information, see [Add a center value to a donut chart](../visuals/power-bi-visualization-doughnut-charts.md). |        |
| Comments support for reports in org apps | Users can comment on report pages and visuals in org apps, start discussions, and use @mentions to notify others. Comments capture the current report context. For more information, see [Comments in Power BI reports](../explore-reports/end-user-comment.md). |        |
| Matrix: Expand and collapse for column headers (Generally Available) | Column headers in the matrix visual now support expand and collapse using +/- icons when more than one field is in the Columns field well. Icon color and size are customizable under **Column headers** > **+/- icons** in the format pane. For more information, see [Expand and collapse row and column headers](../visuals/power-bi-visualization-matrix-visual.md). |        |
| Matrix: Set the default freeze state for row headers in the format pane | Report authors can set the default freeze state for matrix row headers using the **Row headers** toggle under **Layout** > **Freeze** in the format pane. This default is saved with the report. The right-click freeze options remain available for transient per-session changes. For more information, see [Freeze row headers](../visuals/power-bi-visualization-matrix-visual.md). |        |
| OneLake file URLs for report visuals and maps (Generally Available) | Image files stored in OneLake can be used as image sources in the image visual, table and matrix cells, the card visual, button and list slicers, and custom icons in the Icons cell element. Power BI authenticates on the viewer's behalf. Reference layer maps and shape map files can also be linked from OneLake URLs. For more information, see [Use OneLake file URLs in Power BI reports](../visuals/power-bi-onelake-files.md), [Display images in a table, matrix, or slicer](../create-reports/power-bi-images-tables.md), and [Image visual in Power BI](../visuals/power-bi-visualization-image-visual.md). |        |
| Outer padding for bar, column, line, ribbon, and waterfall charts (Generally Available) | An **Outer padding** setting under **Layout** controls the space between the plot area edges and the first and last categories. Set to 0% to fill the plot area; combine with **Space between categories** at 0% to fully fill. For more information, see [Customize x-axis and y-axis properties](../visuals/power-bi-visualization-customize-x-axis-and-y-axis.md). |        |
| Azure Maps reference layer shape-matching improvements (Generally Available) | Shape matching in Azure Maps reference layers now renders faster, and interactions like filtering, cross-highlighting, and zoom respond more smoothly. No configuration change is required. For more information, see [Add a reference layer to the Azure Maps Power BI visual](/azure/azure-maps/power-bi-visual-add-reference-layer?context=/power-bi/create-reports/context/context). |        |
| Azure Maps loads filtered selection and autozoom (Generally Available) | When you filter to a smaller data set, the Azure Maps visual reloads to include data points that were outside the initial 30,000-point limit. The map also automatically zooms to fit the currently filtered area. For more information, see [Azure Maps visual for Power BI](/azure/azure-maps/power-bi-visual-getting-started?context=/power-bi/create-reports/context/context). |        |
| Slicer visual dropdown border color, open icon, and hierarchy expand and collapse icon colors (Generally Available) | A new **Dropdown** section in the Visual formatting pane adds controls for dropdown border color, rounded corners, and open icon color and transparency, plus an **Accent bar** option. A new **Hierarchy** section lets you color the expand and collapse icons for hierarchy slicers. For more information, see [Slicers in Power BI](../visuals/power-bi-visualization-slicers.md). |        |

## Modeling

| Feature | Description | Currently in preview |
|---------|-------------|:------:|
| More control over semantic model refresh in Power BI Service | The **Refresh** button now offers three options: **Refresh schema and data**, **Sync schema only**, and **Refresh data only**. Refresh operations can also be performed at the table level. For more information, see [Data refresh in Power BI](../connect-data/refresh-data.md). |        |

## Data connectivity

| Feature | Description | Currently in preview |
|---------|-------------|:------:|
| Theming improvements for better accessibility | Color contrast and readability improvements across light and dark themes in the Power Query UI produce cleaner, more legible interface elements. For more information, see [Get data in Power BI Desktop](desktop-getting-started.md). |        |
| Better contrast for connector icons in Dark Mode | Connector icons with transparent backgrounds now automatically receive a white background in Dark Mode. For more information, see [Get data in Power BI Desktop](desktop-getting-started.md). |        |

## Mobile

| Feature | Description | Currently in preview |
|---------|-------------|:------:|
| Rotate view in the mobile report footer | The **Rotate view** button in the Power BI Mobile report footer lets you switch layouts with one tap, even when the phone is locked in portrait orientation. Rolling out to iOS and Android. For more information, see [Explore reports in the Power BI mobile apps](../explore-reports/mobile/mobile-reports-in-the-mobile-apps.md). |        |
| Export data to Excel in the Power BI mobile app | Data from report visuals can be exported to Excel directly from the Power BI mobile app for iOS and Android, via focus mode or the visual's **More options** (**…**) menu. The export reflects current filters, slicers, drill state, and row-level security. For more information, see [Export data from a Power BI visualization](../visuals/power-bi-visualization-export-data.md). |        |

## Embedded analytics

| Feature | Description | Currently in preview |
|---------|-------------|:------:|
| Enhancements to Power BI embedding in SharePoint Online | A new UI lets you browse and select a workspace directly, instead of copying and pasting a URL. You can also embed a single visual using the **Embed a single visual** toggle. For more information, see [Add a Power BI report to SharePoint Online](../collaborate-share/service-embed-report-spo.md). |        |

## Developers and APIs

| Feature | Description | Currently in preview |
|---------|-------------|:------:|
| Faster PBIP development with instant reloads and VS Code integration | Power BI Desktop detects external changes to PBIP project files and prompts you to apply them with a single click. A built-in entry point opens the project directly in Visual Studio Code. For more information, see [Power BI Projects overview](../developer/projects/projects-overview.md). |        |

## Visualizations

| Feature | Description | Currently in preview |
|---------|-------------|:------:|
| Third-party custom visuals | Browse hundreds of custom visuals in AppSource, available directly from Power BI Desktop, or develop your own. Publish to AppSource or share across your organization. |        |

## Resources

Want to learn about Power BI through videos and other engaging content? Check out these video sources and content:

- See [all Power BI playlists on YouTube](https://www.youtube.com/@MicrosoftPowerBI/playlists).
- [Power BI YouTube channel](https://www.youtube.com/user/mspowerbi): Official Microsoft Power BI channel.
- Follow Power BI on X [@MSPowerBI](https://twitter.com/mspowerbi).
- Go to the [Power BI forums in the Microsoft Fabric Community](https://community.fabric.microsoft.com/t5/Power-BI-forums/ct-p/powerbi).

> [!NOTE]
> Some resources use earlier versions of Power BI Desktop or the Power BI service.

If your organization needs an earlier version, download it. Use the most recent version of Power BI Desktop when possible. Earlier versions have these limitations:

- Previous releases of Power BI Desktop aren't serviced. Use the most recent release for the latest features and updates.
- Previous versions can't open files created or saved in newer releases of Power BI Desktop.
- If you load a report from a newer release, get a warning, and then save it in a previous version, you lose information related to new features.
- Only English versions of Power BI Desktop are archived.

> **Download** the [August 2026 version of Power BI Desktop](https://www.microsoft.com/download/details.aspx?id=58494).

## Past updates

Find previous monthly Power BI updates in the [Power BI monthly updates archive](desktop-latest-update-archive.md).
