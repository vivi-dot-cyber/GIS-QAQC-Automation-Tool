# GIS-QAQC-Automation-Tool
Python-based QA/QC automation tool for ArcGIS Pro that cleans point and line datasets, enforces boundary constraints, and generates detailed error logs.

# GIS-QAQC-Automation-Tool/
│
├── README.md
├── qaqc_tool.py
├── toolbox.tbx  (optional if you include your script tool)
├── sample_data/
│     ├── points.gdb
│     ├── lines.gdb
│     └── boundary.gdb
├── project_writeup.pdf

This project automates QA/QC for point and polyline datasets in ArcGIS Pro. It removes points outside a boundary, clips and extends lines to boundary edges, fixes common geometry issues, and generates a detailed error log. Designed for flexible use with adjustable tolerances and optional boundary enforcement

# Features
- Removes points outside a boundary polygon
- Clips lines to boundary
- Extends undershooting lines to boundary edges
- Snap, Trim, Extend geometry corrections
- Detailed CSV/TXT error log
- Adds corrected dataset to ArcGIS Pro automatically
- Fully parameterized script tool

# How to run 
1.	Open ArcGIS Pro and load the toolbox containing the QA/QC script tool.
2.	Run the tool by selecting:
    o	Input feature class (point or polyline dataset).
    o	Output folder or geodatabase.
    o	Error log format (CSV or TXT).
    o	Snap, Trim, and Extend tolerances (optional; defaults to 100 meters).
3.	Execute the tool. The script will:
    o	For points: remove duplicates, invalid coordinates, and fill missing
  	attributes.
    o	For lines: apply Snap, Trim, and Extend edits using the specified tolerances.
    o	Validate topology rules (Must Not Have Dangles, Must Not Overlap).
5.	Check outputs:
    o	A corrected dataset saved in the geodatabase.
    o	An error log file listing OBJECTIDs with actions taken (Removed, Kept,
  	Snapped, Trimmed, Extended, Unfixed, Needs manual fix).
    o	The corrected dataset automatically added to the current ArcGIS Pro map.
7.	Verify functionality by comparing the corrected dataset against the original to confirm that errors were fixed or flagged.
