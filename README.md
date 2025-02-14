# RatMap v0.1  
*An Opinionated Plate Mapping Tool for Your Lab Rats*  

---

## Table of Contents
1. [Overview](#overview)  
2. [Setup and General Use](#setup-and-general-use)  
3. [Key Features](#key-features)  
4. [Using RatMap](#using-ratmap)  
5. [Keyboard Shortcuts](#keyboard-shortcuts)  
6. [Memory Gauge & Data Management](#memory-gauge--data-management)  
7. [Troubleshooting & Pro Tips](#troubleshooting--pro-tips)  
8. [Security & Privacy](#security--privacy)  
9. [Credits](#credits)

---

## Overview
RatMap is a web-based tool designed to help you map and manage your 96-well and 384-well plate data with precision. With features like metadata layer management, CSV export, and interactive quadrant mapping, this app is as nimble as your favorite rodent—if not more!

*Just remember: even if you're in a rat race, don't let your data scamper out of control.*

---

## Setup and General Use

### Requirements
- **Modern Web Browser:** RatMap runs best on modern browsers that comfortably handle up to 200MB of data.
- **Password Protection:** When the app loads, you'll be prompted for a password. It is required to proceed.

### General Setup
- **Select Your Plates:**  
  - Use the checkboxes to display your desired 96-well and/or 384-well plates.
- **Customize Metadata Layers:**  
  - Optionally rename the default metadata layers to custom names via the Layer Naming control.
- **Proceed with Data Entry:**  
  - Make well selections to assign experimental metadata values to specific wells.  
  - If your lab experiment requires, utilize the quadrant mapping feature (commonly used with 96-to-384 well stamping in liquid handlers) to map wells accordingly.
- **Export Data:**  
  - When ready, export the CSVs to aid in downstream data analysis.

---

## Key Features
- **Interactive Plate Mapping:**  
  - Click or Shift+Click to select wells.  
  - Toggle entire rows, columns, or complete plates.
- **Metadata Management:**  
  - Rename metadata layers to suit your experiment.
  - **Value Assignment:**  
    - **Basic Assignment:** Enter a single value to assign to one or multiple selected wells. When a single well is selected, the app auto-advances (by default in column-major order) to the next well.  
    - **Bulk Assignment with Comma-Separated Values:**  
      - If you have a custom list of values, enter them all at once as a comma-separated list.  
      - **Note:** The number of comma-separated values must exactly match the number of selected cells.  
      - **Assignment Order:**  
        - **Default (Column-Major):** Values are assigned from top to bottom, left to right.  
        - **Row-Major Option:** Hold the **Shift** key when clicking **Assign** (or pressing Enter) to assign values in row-major order.
- **Quadrant Mapping:**  
  - Map data from 96-well plates to specific quadrants on 384-well plates.
- **CSV Export:**  
  - Exports metadata in an analysis-ready format following long-form (tidy) conventions.  
  - All metadata appears in dedicated columns, making it intuitive and well-suited for joining with raw sample or well measurement data.
- **Undo Functionality:**  
  - One-level undo to revert accidental changes.
- **Memory Monitoring:**  
  - A “Rat Cache” gauge helps you keep track of your data memory usage.

---

## Using RatMap

### Global Controls Panel
- **Layer Naming:**  
  - Select a metadata layer from the dropdown, input a new name, and click **Rename**.
- **Value Assignment:**  
  - **Basic Assignment:**  
    - Choose a metadata layer, enter the desired value, and click **Assign**.  
    - *Auto-Advance:* When a single well is selected, the selection automatically advances to the next well in column-major order.  
    - To advance in row-major order for single-cell entries, simply hold the **Shift** key during assignment.
  - **Bulk Assignment with Comma-Separated Values:**  
    - Enter a comma-separated list of values to assign to multiple selected wells.  
    - Ensure that the number of values exactly matches the number of selected cells.  
    - Use the **Shift** key to switch the assignment order from the default column-major to row-major.
- **Mapping to Quadrant:**  
  - Choose a source 96-well plate and a destination quadrant for a 384-well plate, then click **Map Wells**.

### Plate Sections
- **96-well Plates:**  
  - Display available plates via checkboxes.  
  - Each plate grid shows well IDs and metadata.
- **384-well Plates:**  
  - Similar layout with additional mapping columns (e.g., source well details).

### Selection Mechanics
- **Simple Click:** Toggle selection of an individual well.
- **Shift+Click:** Select a rectangular group of wells between the last clicked and current well.
- **Header Click:** Toggle selection of an entire row, column, or the full plate.

---

## Keyboard Shortcuts

| Shortcut Combination                   | Action Description                                                             |
| -------------------------------------- | ------------------------------------------------------------------------------ |
| **Ctrl/⌘ + Shift + L**                 | Focus & select the "Name:" input box                                           |
| **Ctrl/⌘ + Shift + M**                 | Focus & select the "Value:" input box                                          |
| **Ctrl/⌘ + Shift + S**                 | Focus the "Source" dropdown                                                    |
| **Ctrl/⌘ + Shift + D**                 | Focus the "Destination:" dropdown                                              |
| **Ctrl/⌘ + Shift + O**                 | Focus the "Export" button (96-well Plates)                                     |
| **Ctrl/⌘ + Shift + P**                 | Focus the "Export" button (384-well Plates)                                    |
| **Plate Toggling (Windows/Mac)**       | <ul><li>**Without Shift:** Toggle plate checkbox (Ctrl + Alt + [number] / Cmd + Option + [number])</li><li>**With Shift:** Simulate a click on the plate’s select-all header (Ctrl + Alt + Shift + [number] / Cmd + Option + Shift + [number])</li></ul> |

*Keep these shortcuts handy—like a well-hidden stash of cheese!*

---

## Memory Gauge & Data Management
- **The Rat Cache:**  
  - **User Testing Notice:** This gauge is provided while the web app is still in the user testing phase.  
  - It displays the current memory usage of your session.  
  - **Warning:**  
    - At 200MB, a warning is triggered. While modern browsers can handle this load, it’s up to you to **Purge** the cache if things get too cheesy.  
    - **Purge Action:** Clicking the **Purge 🤮** button will clear **all metadata** from the app.  
    - Also, be aware that browser actions like refresh, back, or forward will erase all metadata.
  
*Don't let your data hoard become a trap—regular purges keep the system squeaking along nicely.*

---

## Troubleshooting & Pro Tips

### Common Issues
- **No Wells Selected:**  
  - Ensure you select at least one well before assigning a metadata value.
- **Comma-Separated Assignment Error:**  
  - The number of values in your comma-separated list must match the number of selected wells.
- **Memory Warning:**  
  - If you receive a memory alert, consider purging unnecessary data to prevent browser crashes.

### Pro Tips
- **Efficient Selection:**  
  - Use Shift+Click for quick rectangular selections instead of clicking each well individually.
- **Layer Management:**  
  - Keep your metadata layers succinct. Rename them to reflect their purpose.
- **Exporting Data:**  
  - Verify the visible plates' checkboxes before exporting CSV files to ensure all desired data is included.
- **Undo Usage:**  
  - Use the Undo button immediately after an error—it’s your safety net in the maze of data.

---

## Security & Privacy
- **Local Processing Only:**  
  - RatMap is built entirely with HTML, CSS, and JavaScript. All code runs on your local computer.
- **No Data Transmission:**  
  - Any data you enter is stored in your browser's memory (client-side) and is not submitted or transmitted to any external server.
- **Data Volatility:**  
  - Since your metadata is stored locally, browser actions (such as refresh, back, or forward) will erase all data. Be sure to export your data regularly if needed.
- **User Testing Phase:**  
  - During this phase, your input data remains entirely on your machine, ensuring your experiment details stay private and secure.

---

## Credits
- **Created by:** [aakshmn](https://github.com/aakshmn)  
- **Documentation:** This README is maintained alongside the source code for clarity and ease of use.

*Remember: In the world of lab rats, staying organized isn’t just a whisker of wisdom—it’s essential!*
