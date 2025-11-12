---
layout: default
title: "HW5 – Licenses Visualization"
permalink: /hw5/
---

# HW5 – Professional Licenses Visualization (IS445)

## Links

- **The Data:**  
  [licenses_fall2022.csv](https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/licenses_fall2022.csv)

- **The Analysis (Notebook):**  
  https://github.com/aditidahare/aditidahare.github.io/blob/main/hw5/hw5.ipynb

---

## Plot 1 – Number of Licenses by License Type

<iframe src="chart1.html" width="800" height="500" style="border:none;"></iframe>

### Description
This plot shows the distribution of professional licenses across different License Types in the Illinois licensing dataset. Each bar represents a license category, and the bar height represents the number of licenses issued.

### Design Choices – Encodings
The x-axis encodes License Type as a nominal variable. The y-axis uses a quantitative encoding for the count of licenses. The bar chart mark makes category comparison straightforward. Color also encodes License Type to visually separate categories.

### Design Choices – Colormaps
A categorical color palette is used because License Type is a nominal variable without an inherent order.

### Data Transformations
No complex transformation was required. Altair performs aggregation using count() directly on the License Type field.

---

## Plot 2 – Licenses Over Time by License Type (Interactive)

<iframe src="chart2.html" width="800" height="500" style="border:none;"></iframe>

### Description
This interactive plot shows how license issuance trends change over time for different License Types. Each line represents the number of licenses issued in a given year.

### Design Choices – Encodings
The x-axis encodes IssueYear as an ordinal temporal variable. The y-axis encodes the count of issued licenses. Color distinguishes License Types. Line thickness and opacity adjust dynamically based on the selected License Type.

### Design Choices – Colormaps
A categorical colormap is used to distinguish License Types. When a License Type is selected, the line becomes thicker and more opaque compared to the others.

### Data Transformations
A new column, IssueYear, was created by converting Original Issue Date to a datetime and extracting the year. Rows without valid dates were removed.

---

## Interactivity Discussion
The dropdown control highlights a selected License Type by increasing its line thickness and opacity while fading out others. This reduces visual clutter and makes it easier to analyze trends for a specific profession.
