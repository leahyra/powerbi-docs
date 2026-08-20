---
title: Use OneLake image and map files in Power BI reports
description: Learn how to store image and map files in OneLake and use their URLs in Power BI report visuals.
author: julcsc
ms.author: juliacawthra
ms.reviewer: ''
ms.custom:
ms.service: powerbi
ms.subservice: pbi-visuals
ms.topic: how-to
ms.date: 08/12/2026
ai-usage: ai-assisted
LocalizationGroup: Visualizations
# customer intent: As a Power BI report creator, I want to use image and map files stored in OneLake so that I can add secured content to report visuals.
---
# Use OneLake image and map files in Power BI reports

**Applies to:** [!INCLUDE [applies-to-desktop-service](../includes/applies-to-version/desktop-service.md)]

Store image files and shape map files in Microsoft OneLake when you want to use authenticated files in Power BI reports. Power BI uses each report viewer's Microsoft Entra identity to load OneLake files. The files don't need anonymous access, but each viewer needs permission to read them.

This article shows you how to upload files to a lakehouse, copy a file URL, and use the URL in a report.

## Prerequisites

- A [Microsoft Fabric workspace](/fabric/fundamentals/create-workspaces) where you can create a lakehouse and upload files.
- Power BI Desktop or permission to edit a report in the Power BI service.
- To configure viewer access, a workspace **Admin** or **Member** role, or assistance from someone with one of these roles.

## Upload images to OneLake

A lakehouse provides a **Files** area for storing images and other unstructured files in OneLake.

1. [Create a lakehouse](/fabric/onelake/quickstart-get-data#create-a-lakehouse) in your Fabric workspace.
1. Open the lakehouse, and then expand **Files** in the Lakehouse explorer.
1. Open the context menu for **Files** or a folder, and then select **Upload** > **Upload files**.
1. Select the image files, and then select **Upload**.

You can also upload images with [OneLake file explorer](/fabric/onelake/onelake-file-explorer). Drag files from a local folder into the lakehouse **Files** folder in Windows File Explorer.

## Copy the OneLake file URL

Copy the URL for each image that you want to use in a report.

1. In the Lakehouse explorer, locate the image under **Files**.
1. Open the image file's context menu, and then select **Properties**.
1. In the **Properties** pane, copy the **URL** value.

The URL uses the OneLake HTTPS format. For example:

```http
https://onelake.dfs.fabric.microsoft.com/<workspace-guid>/<item-guid>/Files/<path>/<file-name>
```

For more information about OneLake paths, see [OneLake URI syntax](/fabric/onelake/onelake-access-api#uri-syntax).

## Add the URL to a report

How you add the URL depends on whether the report uses one image or selects images based on data.

### Enter a URL in the format pane

Use this method when a visual displays one image.

1. Select a visual that supports an image URL, such as an image or card visual.
1. In the **Format visual** pane, open the settings for the image.
1. For the image source, select **Enter URL**.
1. Paste the OneLake file URL.

The location and name of the image settings vary by visual. For an example, see [Create an image visual](power-bi-visualization-image-visual.md#create-an-image-visual).

### Use an image URL column

Use a column when each row or category can display a different image.

1. Add the OneLake file URLs to a column in your source data.
1. In Power BI Desktop, open **Table** view and select the column.
1. On the **Column tools** tab, set **Data category** to **Image URL**.
1. Add the column to a visual that supports images from data.

For more information, see [Specify data categories in Power BI Desktop](../transform-model/desktop-data-categorization.md) and [Display images in a table, matrix, or slicer](../create-reports/power-bi-images-tables.md).

### Use an image URL measure

Use a Data Analysis Expressions (DAX) measure when the image URL must respond to the report's filter context. The following example returns one OneLake file URL:

```dax
Image URL = "https://onelake.dfs.fabric.microsoft.com/<workspace-guid>/<item-guid>/Files/<path>/<file-name>"
```

1. Create a measure that returns the OneLake file URL.
1. Select the measure, and then open the **Measure tools** tab.
1. Set **Data category** to **Image URL**.
1. Add the measure to a visual or use it as the field for an image setting.

For more information about creating measures, see [Create measures for data analysis in Power BI Desktop](../transform-model/desktop-measures.md).

## Use OneLake images in visuals

You can use OneLake image URLs in these report scenarios:

- **Image visuals**: Enter a URL or bind the image to a column or measure. For more information, see [Create an image visual](power-bi-visualization-image-visual.md).
- **Card visuals**: Use an image URL for an image, callout image, or category header background. For more information, see [Create a card visual](power-bi-visualization-card.md#add-an-image).
- **Tables, matrices, slicers, and multi-row cards**: Add a column categorized as **Image URL**. For more information, see [Display images in a table, matrix, or slicer](../create-reports/power-bi-images-tables.md).
- **Conditional formatting**: Use an image URL column for custom table or matrix icons. For more information, see [Use a custom icon from a URL](../create-reports/desktop-conditional-table-formatting.md#use-a-custom-icon-from-a-url).
- **Azure Maps marker layers**: Use a URL to an SVG file for one marker image, or bind an image URL field to markers. For more information, see [Add a marker layer to an Azure Maps Power BI visual](/azure/azure-maps/power-bi-visual-add-marker-layer#marker-types).
- **Shape map custom maps**: Reference a TopoJSON or GeoJSON file in OneLake as the custom map source. For more information, see [Add a map from URL](power-bi-shape-map.md#add-a-map-from-url).

Other scenarios might exist because visuals continue to add support for image URLs. Check the documentation for the visual that you want to use to confirm whether it accepts an image URL.

## Give report viewers access

Report viewers can see a OneLake image only when they have access to the report and read access to the image file in OneLake. Access to the report or semantic model doesn't automatically grant access to the file.

Grant each viewer **Read** permission on the lakehouse item. Then grant OneLake security **Read** permission on the folder that contains the image. Alternatively, grant **ReadAll** permission on the lakehouse item to provide access to all content under **Tables** and **Files**. Follow the principle of least privilege and grant access only to the folders that viewers need.

For details, see [OneLake security access control model](/fabric/onelake/security/data-access-control-model#onelake-security-and-item-permissions) and [Best practices for OneLake security](/fabric/onelake/security/best-practices-secure-data-in-onelake#least-privilege).

## Considerations

- Power BI supports BMP, JPG, JPEG, GIF, PNG, and SVG image URLs. Azure Maps marker images require SVG files.
- Moving or renaming a file changes its path. Update the URL in the report or semantic model after either change.
- Large images can increase the time required to render a report page. Use image dimensions and file sizes that are appropriate for the visual.
- OneLake URLs require authentication. Report viewers who don't have permission to read a file don't see its image.
- Publish to web and other anonymous embed scenarios don't support OneLake file URLs because those scenarios can't authenticate to OneLake.
- Deployment pipelines don't rewrite OneLake image URLs. A report deployed to a new stage continues to reference files in the original workspace. To point to images in the target stage, use parameters or update the URLs after deployment.

## Related content

- [Create an image visual](power-bi-visualization-image-visual.md)
- [Create a card visual](power-bi-visualization-card.md)
- [Display images in a table, matrix, or slicer](../create-reports/power-bi-images-tables.md)
- [Apply conditional table formatting](../create-reports/desktop-conditional-table-formatting.md)
- [Create Shape Map visualizations](power-bi-shape-map.md)
- [Quickstart: Get data into OneLake](/fabric/onelake/quickstart-get-data)
- [Use OneLake file explorer to access Fabric data](/fabric/onelake/onelake-file-explorer)
- [Troubleshoot Power BI visualizations](power-bi-visualization-troubleshoot.md#image-urls)