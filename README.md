## academic-plot-styler

This repository contains the `academic-plot-styler` Cursor skill, which enforces a consistent, journal-ready plotting style for scientific figures.

The skill is defined in `SKILL.md` and is designed to be **automatically applied** whenever you (or an AI agent) generate plotting code in Python/Matplotlib or Matlab.

## What this skill enforces

- **No title** on figures  
- **No grid** in the background  
- **Legend without a frame** for multi-series plots  
- **1:1 aspect ratio** (square figures)  
- **Line width = 2.0** for all plot lines  
- **Colorbar required** for heatmaps/surfaces/2D scalar fields  
- **LaTeX text rendering** for all labels/ticks/axis titles  
- **Font size between 10pt and 14pt** (default 12pt)

See `SKILL.md` for the full specification and language-specific code snippets.

## Usage

- **In Cursor**: Add this repo as a skill in your Cursor setup so that the assistant can automatically apply these guidelines whenever it generates plots.
- **In your own code**: Copy the configuration snippets from `SKILL.md` into your Python/Matplotlib or Matlab plotting scripts to standardize your figures manually.

