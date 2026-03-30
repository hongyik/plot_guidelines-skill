---
name: academic-plot-styler
description: ALWAYS APPLY when the task involves data visualization, plotting, generating charts, or writing code (Python/Matplotlib or Matlab) that produces figures. Triggers on keywords: plot, visualize, matplotlib, pyplot, scatter, surf, imagesc, figure, chart.
---

# Overview
This skill ensures all scientific visualizations follow a specific "No-Frills Academic" style (1:1 aspect ratio, LaTeX fonts, specific line weights) suitable for high-quality journal publications.

# Instructions (When to Apply)
- **Automatic Trigger**: If the user asks to "plot," "visualize," "show data," or "generate a figure," implement these standards immediately.
- **Code Scanning**: If the generated code includes libraries like `matplotlib.pyplot` or Matlab plotting functions (`plot`, `imagesc`, `surf`), apply the styling parameters below.

# Strict Formatting Rules
Regardless of the language (Python or Matlab), ALWAYS apply these constraints:
1. **No Title**: Never include a chart title.
2. **No Grid**: Ensure background grids are turned off.
3. **Legend (No Frame)**: Always include a legend for multi-series data, but it MUST have NO border/frame.
4. **1:1 Aspect Ratio**: The final output must be a perfect square.
5. **LineWidth**: Set to 2.0 for all plot lines.
6. **Colorbar**: Always include a colorbar for heatmaps, surfaces, or 2D scalar fields.
7. **LaTeX Interpreter**: Use LaTeX for all text (labels, ticks, axis titles).
8. **Font Size**: Standardize between 10pt and 14pt (Default to 12pt).

# Language-Specific Implementation

### For Python (Matplotlib)
Use the following configuration at the start of the plotting script:
```python
import matplotlib.pyplot as plt

plt.rcParams.update({
    "text.usetex": True,
    "font.family": "serif",
    "font.size": 12,
    "axes.grid": False,
    "lines.linewidth": 2.0,
    "legend.frameon": False  # Crucial: Removes the legend box
})

# For 1:1 ratio: fig, ax = plt.subplots(figsize=(5, 5))
# For colorbar: plt.colorbar()
# For legend: plt.legend() # frameon=False is already set globally
```
### For Matlab
Use these property sets:

```Matlab
% Global settings
set(groot, 'defaultAxesTickLabelInterpreter','latex');
set(groot, 'defaultLegendInterpreter','latex');
set(groot, 'defaultTextInterpreter','latex');

% Current axes settings
set(gca, 'FontSize', 12, 'LineWidth', 2, 'Box', 'on');
axis square; % Mandatory 1:1 ratio
grid off;

% Legend without frame
lgd = legend();
set(lgd, 'EdgeColor', 'none', 'Color', 'none'); 

% colorbar;
```