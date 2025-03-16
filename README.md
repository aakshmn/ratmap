# RatMap v0.3  
*An opinionated plate mapping tool for filthy festering lab rats.* 💩🐀  

---

## Table of Contents
1. [Introduction](#introduction)
2. [Overview](#overview)  
3. [Setup and General Use](#setup-and-general-use)  
4. [Key Features](#key-features)  
5. [Using RatMap](#using-ratmap)  
6. [Keyboard Shortcuts](#keyboard-shortcuts)  
7. [Troubleshooting & Pro Tips](#troubleshooting--pro-tips)  
8. [Security & Privacy](#security--privacy)  
9. [Credits](#credits)

---

## Introduction
Welcome, you scurrying, smelly lab rat! If you're reading this, it's clear you're one of those filthy, wretched creatures whose data is as disorganized as your personal hygiene. Fear not—RatMap is here to help you sort out your experimental mess, one well at a time. Now, get off your paws and start mapping!

RatMap is a web-based tool designed to help you map and manage your 96-well and 384-well plate data with precision. With features like metadata layer management, CSV export, and interactive quadrant mapping, this app is as nimble as a rat on the lam. Even if you're as dirty as the rest of your scavenging brethren, this tool will help you keep your data from becoming a total catastrophe.

---

## Setup and General Use

### Requirements
- **Modern Web Browser:** RatMap runs best on modern browsers that comfortably handle up to 200MB of data.

### Video Walkthrough
A walkthrough and demo of RatMap (v0.1) is available. Even though it is an older version, the functionality and principles still hold. There are chapters so that you can jump to topics of interest.

- **Watch the demo video:** [RatMap Walkthrough (v0.1)](https://www.google.com/)

### Quick Start Guide
1. **Open the App:** Go to [RatMap](https://aakshmn.github.io/ratmap/)
2. **Select Your Plates:**  
   - Use the checkboxes at the top to toggle which 96-well and/or 384-well plates to display
3. **Add Metadata:**
   - Select wells by clicking on them
   - Enter values in the input field and click "Assign" (or press Enter)
4. **Export Your Data:**
   - Click the "Export CSV" button in the plate section to download your metadata

---

## Key Features
- **Interactive Plate Mapping:**  
  - Click to toggle selection of individual wells
  - Click and drag to select multiple wells in rectangular regions
  - Toggle entire rows, columns, or complete plates with a single click
- **Metadata Management:**  
  - Rename metadata layers to suit your experiment using the dropdown menu and Rename button
  - **Value Assignment:**  
    - **Basic Assignment:** Enter a single value to assign to one or multiple selected wells. When a single well is selected, the app auto-advances (by default in column-major order) to the next well.  
    - **Bulk Assignment with Comma or Space-Separated Values:**  
      - Enter a comma or space-separated list of values to assign to multiple selected cells at once.  
      - **Note:** The number of values must exactly match the number of selected wells.  
      - **Assignment Order:**  
        - **Default (Column-Major):** Values are assigned from top to bottom, left to right.  
        - **Row-Major Option:** Hold the **Shift** key when clicking **Assign** (or pressing Enter) to assign values in row-major order.
    - **Quoted Assignment:**
      - Values enclosed in double quotes will be treated as a single entry, even if they contain commas or spaces.
- **Metadata Visualization:**
  - Use the **Visualize** button to toggle a color-coded view of your metadata
  - Color gradients are automatically assigned to unique values in the selected metadata layer
  - Toggle between normal selection mode and visualization mode with the same button
  - Click any well to exit visualization mode and return to selection mode
- **Quadrant Mapping:**  
  - Map data from 96-well plates to specific quadrants on 384-well plates using the Source and Destination dropdowns
- **CSV Export:**  
  - Exports metadata in an analysis-ready format following long-form (tidy) conventions
  - **For 96-well Plates:**  
      - Includes a unique `sample_id_96w` (a combination of the experiment ID, plate ID, and well ID), Plate and Well IDs, and all assigned metadata columns.  
  - **For 384-well Plates:**  
      - Includes a unique `sample_id_384w`, Plate and Well IDs, quadrant information, and—if quadrant mapping was used—additional mapping columns such as `sample_id_96w`, `Src_Plate_96w`, and `Src_Well_96w`, along with all metadata columns.  
  - **Experiment ID:** You can provide an optional Experiment ID during export or skip it by leaving it blank.
- **Save and Load:**
  - Save your current plate configuration and metadata for later use
  - Load previously saved data to continue your work
  - **Example Data:** Try loading this [example data file](https://github.com/aakshmn/ratmap/blob/main/ratmap_data_20250314.json) to see a pre-configured plate setup
- **Undo Functionality:**  
  - One-level undo to revert accidental changes using the Undo button
- **Keyboard Shortcuts Help:**
  - Press Ctrl/⌘ + / to view a comprehensive list of available keyboard shortcuts

---

## Using RatMap

### Interface Layout
The interface in v0.3 has been optimized for efficiency:

- **Top Section:**
  - App title and tagline
  - Plate selection checkboxes with visual indicators for active plates
  - Save and Load buttons

- **Controls Section:**
  - **Layer & Metadata Controls:**
    - Layer dropdown
    - Rename button
    - Metadata value input field
    - Assign and Clear buttons
    - Visualize button for toggling metadata visualization mode
  - **Mapping Controls:**
    - Source plate selection
    - Destination quadrant selection
    - Map, Undo, and Empty buttons

- **Plate Sections:**
  - **96-well Plates:** 
    - Displayed when at least one 96-well plate is selected
    - Export CSV button for exporting data
  - **384-well Plates:**
    - Displayed when at least one 384-well plate is selected
    - Export CSV button for exporting data

### Selection Mechanics
- **Simple Click:** Toggle selection of an individual well
- **Click and Drag:** Select a rectangular group of wells by clicking one corner and dragging to the opposite corner
- **Header Click:** Toggle selection of an entire row, column, or the full plate by clicking the corresponding header

### Visualization Mode
- **Automatic Visualization:** Wells are automatically color-coded based on their metadata values in the currently selected layer
- **Color Coding:** Each unique value in the selected metadata layer is assigned a color from a gradient
- **Layer Selection:** 
  - Change the visualized layer using the metadata layer dropdown
  - Use keyboard shortcuts (Ctrl/⌘ + [number]) to quickly switch between layers for rapid assessment of different metadata parameters
  - Visual transitions between layers are smooth, allowing for quick comparison of different experimental conditions
- **Empty Wells:** Wells without assigned values in the current layer appear without color coding

---

## Keyboard Shortcuts

The app features a built-in shortcuts help popup (Press Ctrl/⌘ + / to view). Available shortcuts include:

### General Controls
| Shortcut | Action |
|---------|--------|
| Ctrl/⌘ + Shift + L or M | Focus and select the metadata value input |
| Ctrl/⌘ + Shift + S | Focus the Source dropdown |
| Ctrl/⌘ + Shift + D | Focus the Destination dropdown |
| Ctrl/⌘ + Shift + O | Focus the 96-well plates Export button |
| Ctrl/⌘ + Shift + P | Focus the 384-well plates Export button |
| Ctrl/⌘ + / | Toggle shortcuts help popup |
| Esc | Close shortcuts help popup |

### Plate Toggling
| Shortcut | Action |
|---------|--------|
| Ctrl/⌘ + Alt/Option + 1-8 | Toggle 96-well plates P01 through P08 |
| Ctrl/⌘ + Alt/Option + 9-0 | Toggle 384-well plates P01 and P02 |
| Ctrl/⌘ + Alt/Option + Shift + 1-0 | Select all wells in the corresponding plate |

### Metadata Assignment
| Shortcut | Action |
|---------|--------|
| Enter | Assign value to selected well(s) in column-major order |
| Shift + Enter | Assign value to selected well(s) in row-major order |
| Shift + Alt/Option + Enter | Rename the current layer |

---

## Troubleshooting & Pro Tips

### Common Issues
- **No Wells Selected:**  
  - Ensure you select at least one well before assigning a metadata value.
- **List Assignment Error:**  
  - The number of values in your comma/space-separated list must match the number of selected wells.
  - Values must be from a single plate for list assignments.
- **Memory Warning:**  
  - If you receive a memory alert, consider clearing unnecessary data or saving and refreshing the page.
- **Visualization Not Showing:**
  - Make sure the current metadata layer contains values for the wells you want to visualize.
- **Table Dimensions Inconsistent:**
  - The app automatically equalizes table dimensions when multiple plates are visible, but you may need to refresh or toggle plates to fix alignment issues.

### Pro Tips
- **Efficient Selection:**  
  - Use click-and-drag for quick rectangular selections instead of clicking each well individually.
  - Use the keyboard shortcuts to select entire plates (Ctrl/⌘ + Alt/Option + Shift + [number]).
  - Click on row or column headers to toggle entire rows or columns quickly.
- **Layer Management:**  
  - Keep your metadata layers succinct. Rename them to reflect their purpose (e.g., "Temperature", "Compound", "Concentration").
  - When working with multiple metadata types, switch between layers frequently to build a complete dataset.
- **Value Assignment Shortcuts:**
  - Use **Enter** to assign and advance to the next well in column-major order.
  - Use **Shift+Enter** to assign and advance in row-major order.
  - Use **Shift+Alt/Option+Enter** to quickly rename the current layer.
- **Quoted Values:**
  - Enclose values in double quotes (") to include commas or spaces within a single value.
  - Example: `"PBS, 1X"` will be treated as a single value.
- **Visualization Usage:**
  - The automatic color-coding helps quickly identify patterns or errors in your plate layout
  - Use keyboard shortcuts to rapidly switch between metadata layers for comparing different parameters
  - Color gradients make it easy to spot missing values or outliers in your data
  - The immediate visual feedback helps verify correct metadata assignment
- **Save Your Work:**
  - Use the Save button frequently to prevent data loss, especially during long mapping sessions.
  - Downloaded save files can be shared with colleagues for collaborative work.
- **Exporting Data:**  
  - Verify the visible plates' checkboxes before exporting CSV files to ensure all desired data is included.
  - The Experiment ID is optional during export - provide one for better organization or leave it blank to skip.
  - Export early and often to backup your work, especially for complex mappings.
- **Undo Usage:**  
  - Use the Undo button immediately after an error—it's your safety net in the maze of data.
- **Keyboard Shortcuts:**
  - Learn the keyboard shortcuts for frequent actions to speed up your workflow.
  - The shortcuts help popup (Ctrl/⌘ + /) is your friend.

---

## Security & Privacy
- **Local Processing Only:**  
  - RatMap is built entirely with HTML, CSS, and JavaScript. All code runs on your local computer.
- **No Data Transmission:**  
  - Any data you enter is stored in your browser's memory (client-side) and is not submitted or transmitted to any external server.
- **Data Volatility:**  
  - Your metadata is stored locally in browser memory. Use the Save button to create a backup file of your data.
  - Browser actions (such as refresh, back, or forward) may erase unsaved data.
- **Browser Protection:**
  - The app includes safeguards like preventing right-click context menus and displaying confirmation dialog when attempting to leave the page with unsaved changes.

---

## Credits
- **Created by:** [aakshmn](https://github.com/aakshmn)  
- **Documentation:** This README is maintained alongside the source code for clarity and ease of use.

*Remember: even if you're a filthy, scavenging lab rat, a bit of organization goes a long way in saving you from a data disaster!*