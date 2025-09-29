Table Detection Challenge Solution
This repository contains two computer vision solutions for automatically detecting and highlighting table structures in different interface screenshots:

SAP Table Detector - Specialized for SAP interface screenshots
WEB Table Detector - Optimized for web interface tables
Both solutions leverage a prototype-based approach where the algorithm first learns from a prototype image before applying detection to actual screenshots.

Overview
The challenge involved creating computer vision algorithms that can:

Identify table structures in interface screenshots
Distinguish between header rows and body rows
Visualize the detected structures with clear highlighting
Handle different table layouts and screen resolutions
SAP Table Detector
The SAP_Table_Detector.ipynb notebook provides a solution specialized for SAP interface tables.

Approach:
Prototype Analysis:

Analyzes a prototype SAP table image to learn the expected row height
Uses contour detection and statistical mode to identify the most common row height
Table Detection:

Identifies the main table area by finding large rectangular contours with specific aspect ratios
Extracts horizontal lines using morphological operations and Hough line detection
Separates header from body rows based on spacing patterns
Highlights the table structure with colored rectangles:
Table frame (red)
Header (green)
Body rows (yellow)
Vertical Line Detection:

Identifies column separators using vertical line detection
WEB Table Detector
The WEB_Table_Detector.ipynb notebook provides a solution optimized for web-based tables.

Approach:
Prototype Analysis:

Learns both header height and average body row height from a prototype image
Records the prototype dimensions for scaling calculations
Adaptive Detection:

Scales measurements based on screen dimensions to handle different resolutions
Uses clustering algorithms to identify consistent row patterns
Employs filtering techniques to clean up detected lines
Table Structure Recognition:

First identifies the body rows as the main cluster of consistent lines
Then attempts to locate the header based on expected positioning
Uses percentiles to determine table boundaries horizontally
Visualizes results with colored rectangles:
Table frame (red)
Header (green)
Body rows (yellow)
Technologies Used
Python with OpenCV for image processing
NumPy for numerical operations
Matplotlib for visualization
Computer vision techniques including:
Thresholding
Morphological operations
Contour detection
Hough line detection
Connected component analysis
