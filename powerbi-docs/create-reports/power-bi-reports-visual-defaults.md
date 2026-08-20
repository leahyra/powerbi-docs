---
title: Visual defaults in Power BI reports
description: Learn about base themes in Power BI, including Fluent 2, Classic 2026, and Classic 2018, and how they define the default look of your report visuals.
author: JulCsc
ms.author: juliacawthra
ms.reviewer: zoedouglas
ms.service: powerbi
ms.subservice: pbi-reports-dashboards
ms.topic: concept-article
ms.date: 08/01/2026
LocalizationGroup: Create reports
---
# Visual defaults in Power BI reports

**Applies to:** [!INCLUDE [applies-to-desktop-service](../includes/applies-to-version/desktop-service.md)]

Every Power BI report has a *base theme* that defines the default colors, fonts, and styles for all visuals. The base theme provides the foundation for your report's appearance. When you apply a [custom theme](desktop-report-themes.md), it layers on top of the base theme, overriding specific styles while inheriting the rest.

Power BI offers multiple base themes to choose from:

| Base theme | Description |
|------------|-------------|
| **Fluent 2** | Default base theme for new reports. Modern styling aligned with the Microsoft Fluent 2 design system. |
| **Classic 2026** | Previous default base theme. Incremental refresh of Classic 2018. |
| **Classic 2018** | Original base theme for legacy compatibility. |

## Fluent 2

The Fluent 2 base theme provides a modern look aligned with the Microsoft Fluent 2 design system. This base theme helps you produce polished reports without manual formatting for each visual. New reports created in Power BI Desktop or the Power BI service use Fluent 2 by default.

<iframe title="Modern Visual Defaults" width="800" height="486" src="https://msit.powerbi.com/view?r=eyJrIjoiYWUzNGY5ZDEtZThkYi00ZDhjLTk1ZjItYzUxMDVhMDljNTg3IiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9" frameborder="0" allowFullScreen="true"></iframe>

### Canvas and background

The Fluent 2 base theme updates the default canvas:

- **Canvas size**: New pages default to 1920x1080, giving you more space.
- **Background colors**: The wallpaper and background are now shades of grey, providing better contrast and making visuals stand out more clearly.

> [!NOTE]
> Existing reports and existing pages don't update their page size when you switch to the new base theme. Only new pages use the new default canvas size.

### Uniform visual styling

All visuals share consistent structural styling:

- **Fonts**: Uniform font style, colors, and sizes across visuals
- **Titles**: Titles and subtitles are on by default; axis titles are off by default
- **Padding and borders**: Increased padding with rounded corners applied across visuals

These styles use structural colors throughout the theme. When you customize the current theme through **View** > **Themes** > **Customize current theme**, your changes flow to all visuals.

### Style presets by visual type

Many visuals include built-in style presets so you can quickly shift to a different look with a single selection.

#### Charts

Chart visuals offer presets that adjust axis and label visibility:

- **Default**: Shows the axis without labels
- **Data labels**: Turns off the axis in favor of data labels and markers—useful for small multiples

#### Line charts

Line charts use smooth lines by default and include more presets:

- Straight lines with data labels
- Straight lines without data labels

#### Tables and matrix

Table and matrix visuals keep their existing style presets, updated to match the new modern styling.

#### Buttons and navigators

Buttons and navigators use Fluent 2 styling by default. The button color uses your first theme data color, and each button has styles for default, hover, and pressed states.

Button style presets include:

- **Default**: Standard button appearance
- **Outline**: Border only, no fill
- **Transparent**: No border or fill
- **Icon & Text**: Icon displayed alongside button text

Navigator style presets include:

- **Default**: Standard button appearance
- **Tab**: Tab-style navigation

#### Cards

The card visual uses less padding and no reference label background for a cleaner look.

#### Small multiples

Small multiples consolidate to the categorical axis. Instead of a 2x2 arrangement, small multiples begin in a 1x4 or 4x1 layout depending on orientation, providing a more logical default view.

## Classic 2026

Classic 2026 was the default base theme for new reports before Fluent 2. It includes incremental improvements over Classic 2018 while maintaining compatibility with existing reports.

## Classic 2018

Classic 2018 is the original base theme from Power BI's earlier releases. Reports created before 2026 use this base theme. You might choose to keep this base theme for:

- Legacy reports where changing the visual style isn't desired
- Consistency with existing reports in your organization

## Update to the latest base theme

New reports created in Power BI Desktop or the Power BI service automatically use the latest base theme (Fluent 2).

For existing reports, you can update to the latest base theme:

1. On the **View** ribbon, toggle on the **Theme** pane.
1. If an update is available, a banner appears in the Theme pane.
1. Select **Update theme** to apply the latest base theme.

You can also select the **Reset to default** tile (the first theme in the Power BI section of the Themes dropdown) to remove any custom theme and apply the latest base theme to your report.

The **Reset to default** tile in the **View** ribbon's **Themes** dropdown removes any customizations to the current theme or custom theme applied to the report, leaving only the chosen base theme. It doesn't affect styling you set on individual visuals from the formatting pane. To revert an individual visual to the current theme's defaults, use **Reset to default** on the visual's formatting pane (see [Reset formatting](#reset-formatting)).

> [!TIP]
> If your custom theme doesn't work with the new modern defaults, you can undo the update to revert to the previous base theme until you're ready to update your custom theme.

## Choose a base theme

You can switch to a different base theme at any time:

1. On the **View** ribbon, toggle on the **Theme** pane.
1. In the **Theme settings** section at the top of the Theme pane, select the **Base theme** dropdown.
1. Choose the base theme you want: **Fluent 2**, **Classic 2026**, or **Classic 2018**.

Your report visuals update to reflect the new base theme's default styles.

## Reset formatting

When you format a visual directly using the formatting pane, your customizations take precedence over the base theme or custom theme. To return to theme defaults:

### Reset individual sections

You can reset individual sections in the formatting pane to their default values. This targeted approach avoids resetting data-bound formatting or actions configured on the visual.

### Reset entire visual

To reset all formatting on a visual, select **Reset to default** in the visual's formatting pane. This returns the visual to the current theme's default styling.

> [!NOTE]
> **Reset to default** also removes actions on buttons and images, conditional formatting rules, images from URLs or data-bound fields, and other data-bound items like reference labels.

## Customize current theme from the Theme pane

You can customize your report's theme defaults directly from the Theme pane. On the **View** ribbon, toggle on the **Theme** pane.

Your report updates immediately with each change. Switch between pages to see the impact as you adjust the theme.

The Theme pane displays the following options:

- **Theme settings**: Set the base theme and import, export, or remove a theme.
- **Colors**: Select a color palette and customize data, structural, sentiment, and divergent colors.
- **Text**: Customize default text styles for your report.
- **Visual properties**: Turn visual elements on or off and customize their appearance.
- **Page**: Configure canvas settings, background, and wallpaper.
- **Filter pane**: Customize the filter pane appearance.
- **Filter cards**: Adjust filter card formatting for the current page and all new pages.

These changes create a custom theme layered on top of your base theme. Styling applied directly to individual visuals or pages takes precedence over custom theme defaults.

### Colors

Expand **Colors** to customize the color scheme for your report:

- **Color palette**: Select a built-in palette such as Sunset, Accessible Default, or Electric. The palette updates your report's colors while preserving other customizations.
- **Data**: Customize colors used for data series in visuals.
- **Structural**: Customize colors for visual structure elements.
- **Sentiment**: Customize colors for positive, neutral, and negative sentiment.
- **Divergent colors**: Customize colors for divergent scales.

### Visual properties

Expand **Visual properties** to configure defaults that apply to all visuals across your report:

- **Background**: Customize the color and transparency of all visual and group backgrounds.
- **Border**: Turn borders on or off and customize color, thickness, and corner radius.
- **Header icons**: Turn header icons on or off and customize their appearance.
- **Tooltip**: Turn tooltips on or off and customize their appearance.
- **Shadow**: Turn shadows on or off and customize color, size, and position.
- **Padding**: Adjust the default padding for all visuals.

These settings update existing visuals that use default styling, while preserving any customizations you made to individual visuals. New visuals you add inherit the theme defaults.

### Page

Expand **Page** to update page settings across all pages at once:

- **Canvas settings**: Set the default page size for new pages.
- **Canvas background**: Change the background color across all pages.
- **Wallpaper**: Change the wallpaper color across all pages.

### Export your custom theme

Export your custom theme for reuse:

1. In the Theme pane, expand **Theme settings**.
1. Select **Export theme** to save your theme as a JSON file.
1. Use the exported theme in other reports or add it to your [organizational themes](desktop-organizational-themes.md).

## Related content

- [Use report themes in Power BI](desktop-report-themes.md)
- [Create custom report themes](report-themes-create-custom.md)
- [Organizational themes](desktop-organizational-themes.md)
