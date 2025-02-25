# RatMap v0.1  
*An opinionated plate mapping tool for filthy festering lab rats.* 💩🐀  

---

## Table of Contents
1. [Introduction](#introduction)
2. [Overview](#overview)  
3. [Setup and General Use](#setup-and-general-use)  
4. [Key Features](#key-features)  
5. [Using RatMap](#using-ratmap)  
6. [Keyboard Shortcuts](#keyboard-shortcuts)  
7. [Memory Usage & Data Management](#memory-usage--data-management)  
8. [Troubleshooting & Pro Tips](#troubleshooting--pro-tips)  
9. [Security & Privacy](#security--privacy)  
10. [Credits](#credits)

---

## Introduction
Welcome, you scurrying, smelly lab rat! If you're reading this, it's clear you're one of those filthy, wretched creatures whose data is as disorganized as your personal hygiene. Fear not—RatMap is here to help you sort out your experimental mess, one well at a time. Now, get off your paws and start mapping!

---

## Overview
RatMap is a web-based tool designed to help you map and manage your 96-well and 384-well plate data with precision. With features like metadata layer management, CSV export, and interactive quadrant mapping, this app is as nimble as a rat on the lam. Even if you're as dirty as the rest of your scavenging brethren, this tool will help you keep your data from becoming a total catastrophe.

---

## Setup and General Use

### Requirements
- **Modern Web Browser:** RatMap runs best on modern browsers that comfortably handle up to 200MB of data.
- **Password Protection:** When the app loads, you'll be prompted for a password. Enter "whiskers" (or maybe you already knew that, you sneaky rodent).

### General Setup
- **Select Your Plates:**  
  - Use the checkboxes to display your desired 96-well and/or 384-well plates.
- **Customize Metadata Layers:**  
  - Rename the default metadata layers to custom names via the dropdown menu and Rename button.
- **Proceed with Data Entry:**  
  - Make well selections to assign experimental metadata values to specific wells.  
  - If your lab experiment requires it, utilize the quadrant mapping feature (common in 96-to-384 well stamping with liquid handlers) to map wells accordingly.
- **Export Data:**  
  - When ready, export the CSVs with the "Export 🧀" button to aid in downstream data analysis and merge with your raw measurement files.

---

## Key Features
- **Interactive Plate Mapping:**  
  - Click or Shift+Click to select wells.  
  - Toggle entire rows, columns, or complete plates.
- **Metadata Management:**  
  - Rename metadata layers to suit your experiment using the dropdown menu and Rename button.
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
- **Quadrant Mapping:**  
  - Map data from 96-well plates to specific quadrants on 384-well plates using the Source and Destination dropdowns.
- **CSV Export:**  
  - Exports metadata in an analysis-ready format following long-form (tidy) conventions using the "Export 🧀" button.  
  - **For 96-well Plates:**  
      - Includes a unique `sample_id_96w` (a combination of the experiment ID, plate ID, and well ID), Plate and Well IDs, and all assigned metadata columns.  
  - **For 384-well Plates:**  
      - Includes a unique `sample_id_384w`, Plate and Well IDs, quadrant information, and—if quadrant mapping was used—additional mapping columns such as `sample_id_96w`, `Src_Plate_96w`, and `Src_Well_96w`, along with all metadata columns.  
  - These exports are designed to be intuitive, making it simple even for you, you filthy lab rat, to merge and map your metadata with raw experimental data.
- **Undo Functionality:**  
  - One-level undo to revert accidental changes using the Undo button.
- **Memory Monitoring:**  
  - A memory usage indicator helps you keep track of your session's memory usage.

---

## Using RatMap

### Global Controls Panel
The global controls are now organized into two rows:

#### Top Row: Metadata Controls
- **Layer Selection and Renaming:**  
  - Select a metadata layer from the dropdown, input a new name in the value field, and click **Rename**.
- **Value Assignment:**  
  - With a layer selected, enter a value in the text field and click **Assign**.
  - For single-well selections, the app will automatically advance to the next well.
  - For multiple wells, all selected wells will receive the value.
  - For comma/space-separated lists, each well will receive its corresponding value.
- **Clear Button:**
  - Clears only the currently selected metadata layer for the selected wells.

#### Bottom Row: Mapping & Undo/Reset
- **Quadrant Mapping:**  
  - Choose a source 96-well plate and a destination quadrant for a 384-well plate, then click **Map Wells**.
- **Undo Button:**
  - Reverts your last action.
- **Empty 🤮 Button:**
  - Clears ALL metadata values across ALL layers for selected wells.
- **Memory Usage:**
  - Shows the current memory usage of your session in KB or MB.

### Plate Sections
- **96-well Plates:**  
  - Display available plates via checkboxes.  
  - Each plate grid shows well IDs and metadata.
  - "Export 🧀" button for exporting 96-well plate data.
- **384-well Plates:**  
  - Similar layout with additional mapping columns (e.g., source well details).
  - "Export 🧀" button for exporting 384-well plate data.

### Selection Mechanics
- **Simple Click:** Toggle selection of an individual well.
- **Shift+Click:** Select a rectangular group of wells between the last clicked and current well.
- **Header Click:** Toggle selection of an entire row, column, or the full plate.

---

## Keyboard Shortcuts

| Shortcut Combination                   | Action Description                                                             |
| -------------------------------------- | ------------------------------------------------------------------------------ |
| **Ctrl/⌘ + Shift + L**                 | Focus & select the metadata value input                                        |
| **Ctrl/⌘ + Shift + M**                 | Focus & select the metadata value input (alternative)                          |
| **Ctrl/⌘ + Shift + S**                 | Focus the "Source" dropdown                                                    |
| **Ctrl/⌘ + Shift + D**                 | Focus the "Destination" dropdown                                               |
| **Ctrl/⌘ + Shift + O**                 | Focus the "Export 🧀" button (96-well Plates)                                  |
| **Ctrl/⌘ + Shift + P**                 | Focus the "Export 🧀" button (384-well Plates)                                 |
| **Enter**                              | Apply value to selected wells (column-major order)                              |
| **Shift + Enter**                      | Apply value to selected wells (row-major order)                                |
| **Shift + Alt/Option + Enter**         | Perform layer rename operation                                                 |
| **Plate Toggling (Windows/Mac)**       | <ul><li>**Without Shift:** Toggle plate checkbox (Ctrl + Alt + [number] / Cmd + Option + [number])</li><li>**With Shift:** Simulate a click on the plate's select-all header (Ctrl + Alt + Shift + [number] / Cmd + Option + Shift + [number])</li></ul> |

*Keep these shortcuts handy—like a well-hidden stash of cheese!*

---

## Memory Usage & Data Management
- **Memory Usage Indicator:**  
  - Displays the current memory usage of your session in KB or MB.  
  - **Warning:**  
    - At 200MB, a warning is triggered. While modern browsers can handle this load, it's advisable to clear unnecessary data if you see this warning.  
    - **Empty Action:** Clicking the **Empty 🤮** button will clear **all metadata** from selected wells.  
    - Also, be aware that browser actions such as refresh, back, or forward will erase all metadata.
  
*Don't let your data hoard become a trap—regular purges keep the system squeaking along nicely, unlike your sorry excuse for lab hygiene.*

---

## Troubleshooting & Pro Tips

### Common Issues
- **No Wells Selected:**  
  - Ensure you select at least one well before assigning a metadata value.
- **List Assignment Error:**  
  - The number of values in your comma/space-separated list must match the number of selected wells.
  - Values must be from a single plate for list assignments.
- **Memory Warning:**  
  - If you receive a memory alert, consider clearing unnecessary data to prevent browser crashes.

### Pro Tips
- **Efficient Selection:**  
  - Use Shift+Click for quick rectangular selections instead of clicking each well individually.
- **Layer Management:**  
  - Keep your metadata layers succinct. Rename them to reflect their purpose.
- **Value Assignment Shortcuts:**
  - Use **Enter** to assign and advance to the next well in column-major order.
  - Use **Shift+Enter** to assign and advance in row-major order.
  - Use **Shift+Alt/Option+Enter** to quickly rename the current layer.
- **Quoted Values:**
  - Enclose values in double quotes (") to include commas or spaces within a single value.
- **Exporting Data:**  
  - Verify the visible plates' checkboxes before exporting CSV files to ensure all desired data is included.
  - Always provide an Experiment ID when exporting to keep your data organized.
- **Undo Usage:**  
  - Use the Undo button immediately after an error—it's your safety net in the maze of data.

---

## Security & Privacy
- **Local Processing Only:**  
  - RatMap is built entirely with HTML, CSS, and JavaScript. All code runs on your local computer.
- **No Data Transmission:**  
  - Any data you enter is stored in your browser's memory (client-side) and is not submitted or transmitted to any external server.
- **Data Volatility:**  
  - Since your metadata is stored locally, browser actions (such as refresh, back, or forward) will erase all data. Be sure to export your data regularly if needed.
- **Password Protection:**
  - A simple password barrier ("whiskers") keeps away non-rats. It's not high security, but it adds a touch of exclusivity to your rodent club.

---

## Credits
- **Created by:** [aakshmn](https://github.com/aakshmn)  
- **Documentation:** This README is maintained alongside the source code for clarity and ease of use.

*Remember: even if you're a filthy, scavenging lab rat, a bit of organization goes a long way in saving you from a data disaster!*
