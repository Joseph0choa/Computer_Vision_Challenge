# Table Detection Challenge Solution

This repository contains two computer vision solutions for **automatically detecting and highlighting table structures** in different interface screenshots:

- **SAP Table Detector** → Specialized for SAP interface screenshots  
- **WEB Table Detector** → Optimized for web interface tables  

Both solutions use a **prototype-based approach**:  
The algorithm first learns from a prototype image (to understand row heights and structure) before applying detection to actual screenshots.

---

##  Overview
The challenge involved creating computer vision algorithms that can:

- Identify table structures in interface screenshots  
- Distinguish between **header rows** and **body rows**  
- Visualize the detected structures with clear highlighting  
- Handle different table layouts and screen resolutions  

---

##  SAP Table Detector
 Notebook: `SAP_Table_Detector.ipynb`  

### Approach:
- **Prototype Analysis** → Analyzes a prototype SAP table image to learn the expected row height, using contour detection and statistical mode.  
- **Table Detection** → Identifies the main table area, extracts horizontal lines, separates header and body rows, and highlights with colors:  
  - 🟥 Table frame (**red**)  
  - 🟩 Header (**green**)  
  - 🟨 Body rows (**yellow**)  
  - ⬛ Column separators(**black**)

---

##  WEB Table Detector
 Notebook: `WEB_Table_Detector.ipynb`  

### Approach:
- **Prototype Analysis** → Learns both header height and average row height from a prototype.  
- **Adaptive Detection** → Scales measurements to different resolutions, clusters row patterns, and filters noisy lines.  
- **Table Structure Recognition** → Finds consistent body rows, locates header by position, calculates horizontal boundaries, and visualizes with:  
  - 🟥 Table frame (**red**)  
  - 🟩 Header (**green**)  
  - 🟨 Body rows (**yellow**)  

---

## Technologies Used
- **Python 3.9+**  
- **OpenCV** → image processing  
- **NumPy** → numerical operations  
- **Matplotlib** → visualization  

### Computer Vision Techniques
- Thresholding  
- Morphological operations  
- Contour detection  
- Hough line detection  
- Connected component analysis  

---

## Installation & Setup

Follow these steps to set up and run the project locally:

# 1. Clone the repository
git clone https://github.com/Joseph0choa/Computer_Vision_Challenge
cd Computer_Vision_Challenge

# 2. Create a virtual environment
python -m venv venv

# 3. Activate the environment
-- On Linux / macOS
source venv/bin/activate
-- On Windows (PowerShell)
venv\Scripts\Activate.ps1
-- On Windows (Command Prompt)
venv\Scripts\activate.bat

# 4. Install dependencies
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
