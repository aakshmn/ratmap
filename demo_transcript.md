# RatMap v0.3 Demo Script

## Introduction

Hello and welcome, all you brilliant minds of laboratory science! Today I'm thrilled to introduce you to RatMap version 0.3, an intuitive web-based tool designed specifically for experimental scientists like yourselves who work with multi-well plates.

Whether you're designing assays, planning experimental layouts, or trying to keep track of what went where in your plates, RatMap is here to make your life easier and your data cleaner.

Look at you there, with your unkempt whiskers and that suspicious stain on your lab coat. You probably can't even remember which samples you put in which wells yesterday. Don't worry, you festering little lab vermin, RatMap is going to rescue you from your own filthy disorganization.

## Let's start with a High-Level Overview

So what exactly is RatMap? At its core, RatMap is a specialized mapping tool that helps you design, document, and track your plate-based experiments. It supports both 96-well and 384-well plate formats, which covers most standard laboratory workflows.

The key problems RatMap solves are:

1. **Experiment Design**: Plan your plate layouts before stepping into the lab
2. **Metadata Management**: Document what's in each well across multiple information layers
3. **Quadrant Mapping**: Easily transfer from 96-well to 384-well plates
4. **Data Export**: Generate clean, analysis-ready CSV files that work seamlessly with your analysis tools

RatMap runs entirely in your browser - there's no installation, no account creation, and no data sent to external servers. Your experimental data stays private, on your machine.

The interface is designed to be intuitive and responsive. You can select wells individually, in groups, or entire rows and columns. You can also save your work and come back to it later.

## Basic Functionality

Let's start with the basics of the interface:

**At the top of the screen**, you'll find:
- The application title and version
- Save and Load buttons to preserve your work
- Plate selection checkboxes to choose which plates to display

**In the controls section**, you have:
- A layer dropdown for selecting which metadata layer you're working with
- A value input field where you'll type your metadata
- Buttons for assigning values, clearing data, and undoing actions
- Mapping controls for transferring data between plates

**The main area** displays your selected plates, with separate sections for 96-well and 384-well plates that appear when the respective plate types are checked.

Let's walk through a basic workflow:

1. **Select a plate** by checking one of the plate checkboxes at the top
2. **Select wells** by clicking on them individually, or click and drag to select multiple
3. **Enter metadata** in the input field
4. **Click "Assign"** to add that information to your selected wells
5. When you're done, **click "Export CSV"** to download your data in a structured format

That's the basic process! Of course, there's much more to RatMap than that, which we'll cover as we go deeper.

## Allow Me To Demonstrate

Let's put this into practice with a simple example. Imagine we're setting up a dose-response experiment with a drug treatment.

1. I'll check the "P01_96w" checkbox to display our first 96-well plate.

2. For our first metadata layer, let's rename it to something meaningful. I'll select the layer dropdown, type "Compound" in the metadata field, and click "Rename."

3. Now I'll select column 1 by clicking its header. This selects all wells in column 1.

4. I'll type "DMSO" in the metadata input field and click "Assign." Notice how all selected wells now contain that value and the wells are automatically color-coded to visualize this assignment.

5. Let's select column 2 and enter "Drug A" as the compound. You can immediately see how the visualization changes to show a different color for this new value.

6. Now let's add concentration information. I'll select layer 2 from the dropdown and rename it to "Concentration."

7. I'll select row A and enter "0 µM" for our control concentration.

8. For rows B through H, I'll select them all by dragging, then enter "0.1, 0.3, 1, 3, 10, 30, 100" in the input field. RatMap will distribute these values across the selected wells in order.

9. Finally, I'll click the "Export CSV" button to get our plate data in an analysis-ready format.

That's it! In just a few clicks, we've designed a simple dose-response experiment and exported the data.

Listen here, you disgusting cheese nibbler. I just showed you how to organize data without using your usual method of scribbling on soiled post-its with marker you've fished out of the biohazard bin. Try to pay attention, even if your tiny rodent brain is distracted by the smell of that half-eaten sandwich rotting in your desk drawer.

## Deep Dive into Core Functionalities

Now let's explore some of RatMap's more powerful features in detail.

### Metadata Layers

RatMap supports 9 different metadata layers, allowing you to track multiple parameters for each well. For example, these could include things like:
- Compound identity
- Concentration
- Cell type
- Treatment duration
- Replicate number
- And anything else you need to track

To work with layers effectively:
1. Use the layer dropdown to select which layer you're editing
2. Rename layers using the "Rename" button for clarity
3. Toggle between layers to build a complete experimental picture
4. Use keyboard shortcuts (Ctrl/Cmd + [1-9]) to quickly switch between layers

### Advanced Selection Techniques

RatMap offers several ways to select wells:

- **Click and drag** for rectangular selections
- **Click row/column headers** to select entire rows or columns
- **Click the top-left corner** to select the entire plate
- **Use keyboard shortcuts** (Ctrl/Cmd + Alt + Shift + [number]) to select all wells in a specific plate
- **Single well auto-advance**: When a single well is selected, assigning a value automatically advances to the next well - column-major by default, or row-major when holding Shift. Repeatedly pressing Enter (or Shift+Enter) allows for rapid sequential assignments.

### Bulk Data Entry

For efficiency, RatMap allows entering multiple values at once:

1. Select multiple wells in the order you want to assign values
2. Enter comma or space-separated values in the input field
3. The number of values must match the number of selected wells
4. Click "Assign" or press Enter

Let me demonstrate this with a practical example. I'll select a rectangular region from wells A01 to D03 - that's 12 wells total. Now I'll enter "1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12" in the metadata input field.

When I click "Assign," watch carefully how these values are distributed. By default, RatMap applies values in column-major order, meaning it goes down each column before moving to the next. So A01 gets "1", B01 gets "2", C01 gets "3", and so on down the columns.

Now let's use the "Undo" button to revert that assignment.

If I want to assign these values in row-major order instead - going across each row before moving to the next - I can hold the Shift key while clicking "Assign" or pressing Enter.

With Shift held down, now A01 gets "1", A02 gets "2", A03 gets "3", then B01 gets "4", and so on across the rows.

This flexibility allows you to quickly populate your plates in whichever pattern makes the most sense for your experimental design.

### Automatic Metadata Visualization

A powerful feature of RatMap v0.3 is the automatic visualization of metadata values. As you assign values to wells, they are automatically color-coded based on their unique values in the current layer. This provides an immediate visual overview of your plate layout, making it easy to:

- Quickly identify patterns in your data
- Spot errors or inconsistencies in your assignments
- Verify that your experimental design matches your intentions

The visualization updates dynamically as you:
- Assign new values
- Switch between metadata layers
- Toggle plates on and off

This continuous visual feedback helps ensure accuracy throughout your experimental setup process.

### Quadrant Mapping

One of RatMap's most powerful features is its ability to map from 96-well to 384-well plates. This is essential when scaling up experiments or combining multiple conditions into a single plate for high-throughput screening.

Let's continue with our bulk data entry example. We created a pattern in wells A01 to D03 using values 1 through 12. Now, let's imagine we've prepared four different 96-well plates:

1. Plate P01_96w has our numbered pattern we just created in wells A01 to D03 (values 1-12)
2. Plate P02_96w contains the same 12 values but arranged in a different pattern
3. Plate P03_96w has these values in yet another distinct arrangement
4. Plate P04_96w uses the same values in a fourth unique pattern

Now we want to combine all four plates into a single 384-well plate for a comprehensive screening run.

First, let me explain how quadrants work in a 384-well plate. The plate is divided into four quadrants:
- Quadrant 1 (Q1): Top-left (odd rows, odd columns)
- Quadrant 2 (Q2): Bottom-left (even rows, odd columns)
- Quadrant 3 (Q3): Top-right (odd rows, even columns)
- Quadrant 4 (Q4): Bottom-right (even rows, even columns)

To map our four plates:

1. First, I'll select P01_96w from the source dropdown and P01_384w_Q1 from the destination dropdown
2. When I click "Map," all the metadata from our first 96-well plate maps to Quadrant 1 of the 384-well plate
3. Now I'll select P02_96w as the source and P01_384w_Q2 as the destination
4. Click "Map" again, and our second plate's data goes into Quadrant 2
5. Next, I'll map P03_96w to P01_384w_Q3
6. Finally, I'll map P04_96w to P01_384w_Q4

Now our 384-well plate contains data from all four 96-well plates, each in its own quadrant. This gives us a comprehensive plate with four different patterns of the same values, which is perfect for comparing different experimental layouts.

When we map plates this way, RatMap not only transfers all the metadata values but also maintains a record of the source plate and well. This is crucial for traceability, especially when troubleshooting unexpected results.

In the exported CSV file, you'll see columns for the source plate and well alongside your metadata, creating a complete record of your experimental setup.

## Specialized Features and Pro Tips

Let's cover some additional features and tips that will make you a RatMap power user:

### Save and Load Functionality

Let's set up a more complex experiment to demonstrate the save and load features. 

First, I'll check a few plates - let's select P01_96w through P04_96w by clicking their checkboxes.

Now I'll set up multiple metadata layers:
1. I'll rename Layer 1 to "Specimen" which already has these values assigned to various wells.
2. For Layer 2, I'll rename it to "Tissue" and assign different tissues across rows: "Blood" for rows A & E, "Spleen" for rows B & F, "Liver" for rows C & G, and "Kidney" for rows D & H.
3. In Layer 3, I'll add "Timepoint" information: "T0" for the left half of each plate and "T1" for the right half.

Perfect! We've created a multi-dimensional experiment. Now, let's map all this data to our 384-well plate. I'll select P01_96w as source and P01_384w_Q1 as destination, then click "Map" - and repeat for all four plates into their respective quadrants.

At this point, you'd definitely want to save this complex setup. Here's how the save and load features work:

1. **Saving Data**:
   - Click the "Save" button to download a JSON file containing all your metadata
   - The default filename is "ratmap_data.json" but can be changed after downloading
   - Each save includes a timestamp for reference

2. **Loading Data**:
   - Click the "Load" button to upload a previously saved JSON file
   - All plates with data will automatically be toggled on for visibility
   - Be sure to review your data by switching through all metadata layers

### Export Options

When exporting your data, you can:
1. Provide an experiment ID to prefix all plate and well identifiers (or leave it blank to skip)
2. Export only the plates that are currently visible
3. Get a CSV file in "long format" that's ready for analysis in tools like R or Python

For 384-well plates that have been populated via quadrant mapping, the export includes additional columns to track the source 96-well plate and well information.

### Clearing Metadata

RatMap provides two different options for clearing metadata from wells:

- **Clear button**: Removes only the values from the currently selected metadata layer in the selected wells. This is useful when you want to keep most of your metadata intact but need to correct values in just one layer.

- **Empty button**: Removes all metadata values across all layers from the selected wells. This is more drastic - think of it as a "start fresh" option for specific wells. The app will display a confirmation dialog before proceeding.

To demonstrate, let's select a few wells that have values in multiple layers. If I click "Clear" while on Layer 2, only the Tissue values are removed, but the Specimen information in Layer 1 and Timepoint information in Layer 3 remains intact. However, if I click "Empty", all metadata from all layers is wiped from these wells completely.

This flexibility allows you to clean up your data at different levels of granularity, depending on your needs.

### Keyboard Shortcuts

RatMap offers numerous keyboard shortcuts to speed up your workflow. Press **Ctrl/Cmd + /** at any time to view the full list of shortcuts. They include:

- **Ctrl/Cmd + S**: Save your data
- **Ctrl/Cmd + O**: Load saved data
- **Ctrl/Cmd + /** : View all keyboard shortcuts
- **Ctrl/Cmd + [1-9]**: Jump to metadata layer 1-9
- **Enter**: Assign values in column-major order
- **Shift + Enter**: Assign values in row-major order
- **Shift + Alt/Option + Enter**: Rename the current layer
- **Ctrl/Cmd + Alt/Option + [1-8]**: Toggle 96-well plates P01-P08
- **Ctrl/Cmd + Alt/Option + [9-0]**: Toggle 384-well plates P01-P02
- **Ctrl/Cmd + Alt/Option + Shift + [number]**: Select all wells in the corresponding plate
- **Ctrl/Cmd + Esc**: Deselect all wells

Holy rat droppings! You're actually getting good at this, aren't you? I was convinced your paws were too filthy to click on the right wells, but you're proving me wrong. Maybe there's hope for you yet, even though your lab notebook looks like it was dragged through the sewers of New York.


## Common Pitfalls and Troubleshooting

Let me warn you about some common pitfalls:

1. **Unsaved data**: RatMap stores data in browser memory. Always save your work before closing the browser! The app will warn you if you try to leave with unsaved changes.

2. **List assignment errors**: When entering lists of values, the number must exactly match your selected wells.

3. **Plate visibility**: Only visible plates will be exported to CSV. Make sure you've selected all plates you want to include.

4. **Memory limitations**: For very large datasets, you might see a memory warning. Save your work and refresh the page if this happens.

5. **Table dimensions**: When multiple plates are visible, RatMap equalizes table dimensions for consistent appearance. This is normal behavior.

If you encounter issues, the Undo button is your friend - it will revert your last action. And don't forget to use Save/Load to create snapshots of your work.

## Conclusion and Call to Action

That concludes our tour of RatMap version 0.3! As you've seen, this tool offers an intuitive yet powerful way to design and document your plate-based experiments, making your scientific workflow more efficient and reducing errors.

To get started:
1. Visit [aakshmn.github.io/ratmap](https://aakshmn.github.io/ratmap)
2. Try loading the example data file to explore a pre-configured setup
3. Check out the README for more detailed documentation

I hope RatMap becomes an invaluable part of your laboratory toolkit, helping you design better experiments, track your metadata consistently, and analyze your results with confidence.

Alright, you miserable excuse for a lab scientist, now scurry back to your bench! Those samples won't process themselves while you sit there with your jaw hanging open. Make mama rat proud and try not to contaminate everything with your filthy little paws this time. Remember, even disgusting sewer dwellers like you deserve clean, organized data - now go make it happen!

Thank you for watching, and happy mapping!
