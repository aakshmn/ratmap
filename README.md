# RatMap v0.1

**An Opinionated Plate Mapping Tool for Experimental Metadata**  
*For those filthy little lab rats (and their equally rancid data).*

---

## Overview

RatMap is a web-based tool built with HTML, CSS, and vanilla JavaScript. It helps you manage, map, and export metadata for both 96-well and 384-well plates. With a quirky sense of humor and a skeptical eye on usability, it’s designed to make lab plate management a bit less... ratty.

**Key Features:**

- **Password Protection:**  
  - Prompts for a password on load (Hint: it's `"RANCID"`).  
  - Keeps nosy parkers (and right-clickers) at bay.
  
- **Global Controls:**  
  - Rename metadata layers.  
  - Assign metadata values (supports comma-separated lists with auto-advance).  
  - Undo last actions (because mistakes happen).

- **Plate Management:**  
  - Supports 96-well and 384-well plate formats.  
  - Checkboxes to toggle plate visibility.  
  - Mapping from 96-well plates to 384-well quadrants.

- **CSV Export:**  
  - Exports metadata with extra sample ID columns for both plate types.

- **Rat Cache:**  
  - A tongue-in-cheek memory gauge to remind you: your browser isn’t a bottomless pit.

---

## Getting Started

### Requirements

- **Browser:** A modern web browser (no need to install fancy frameworks).
- **File:** The HTML file containing all the code.

### Running RatMap

1. **Open the File:**  
   Double-click the HTML file or open it in your browser.
2. **Enter the Password:**  
   When prompted, type in: `RANCID`.
3. **Select Plates:**  
   - Check the boxes for the desired 96-well or 384-well plates.
   - Use the global controls to assign metadata, map wells, or export CSV files.

---

## Code Structure

The entire app is contained within one HTML file. Here’s a breakdown:

| **Section**         | **Description**                                                                                   |
|---------------------|---------------------------------------------------------------------------------------------------|
| `<head>`            | Contains meta tags, inline CSS styles, and a password protection script.                          |
| `<body>`            | Hosts the main UI elements: title, subheader, global controls, plate containers, and the rat cache.|
| **JavaScript**      | - Initializes plate data and metadata layers.                                                    |
|                     | - Manages well selection, metadata assignment, and undo functionality.                           |
|                     | - Handles CSV export and mapping between 96-well and 384-well plates.                             |
| **CSS**             | Provides a clean, responsive layout with two-column global controls and plate grids.             |

---

## Usage Details

1. **Metadata Management:**
   - **Layer Renaming:**  
     Select a metadata layer from the dropdown, enter a new name (alphanumeric, underscores, and dashes only), and click "Rename Layer".
   - **Value Assignment:**  
     Select one or more wells and input a value. For multiple wells, you can use comma-separated values (CSL) if they match the selection count.

2. **Plate Mapping:**
   - **Mapping 96-well to 384-well:**  
     Choose a source 96-well plate and a destination quadrant (the app auto-calculates based on plate geometry).  
     Click "Map to Quadrant" to transfer metadata.

3. **Exporting Data:**
   - Click the "Export" button in the respective plate section to download a CSV file with your experimental metadata.
   - The CSV includes extra columns (e.g., `sample_id_96w` or `sample_id_384w`) for better traceability.

4. **Additional Controls:**
   - **Clear Wells:**  
     Removes metadata from selected wells.
   - **Undo:**  
     Reverts the last metadata assignment.
   - **Purge All:**  
     Clears all metadata and resets layer names (use with caution, data is not recoverable).

---

## Troubleshooting & Notes

- **Right-click Disabled:**  
  It’s not a bug—it's a feature. No right-click means no quick sneaky peeks into the source (or copying your brilliant lab hacks).

- **Data Overload Warning:**  
  The "Rat Cache" periodically updates and will alert you if your metadata grows too big (think of it as your browser’s way of saying, "Enough data, buddy!").

- **Well Selection Order:**  
  Auto-advancement can work in column or row order. Hold Shift when pressing Enter to switch to row-major order.

- **CSV Export Mismatches:**  
  If using comma-separated lists for metadata, ensure the number of values matches the number of selected wells. The tool is as picky as your lab's pipette.

---

## Final Thoughts

RatMap is built for experimental metadata mapping with a side of irreverence. It won’t fix all your lab woes, but it might make managing your data slightly less painful. Use it as a quick, in-browser tool for plate mapping—and if you get lost in the rat nest, remember: the code is all in one file for easy tweaking.

*Happy mapping, and may your data always be as clean as your lab coat (or as dirty as your sense of humor).*
