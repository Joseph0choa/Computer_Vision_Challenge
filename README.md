# Table Structure Detection

This project provides a computer vision solution for automatically detecting and visualizing table structures in interface screenshots. The algorithm uses prototype images to learn table dimensions and then applies this knowledge to identify tables in actual screenshots.

## Features

- **Prototype-based Learning**: Analyzes prototype images to understand table structure parameters
- **Automatic Table Detection**: Identifies tables in various interface screenshots
- **Structural Elements Recognition**:
  - Header rows detection
  - Table rows detection
  - Column separators detection
- **Visual Output**: Generates color-coded visualizations with:
  - 🟥 Table boundaries (red)
  - 🟩 Header rows (green)
  - 🟨 Data rows (yellow)
  - ⬛ Column separators (black)

## How It Works

The solution works in two main phases:

### 1. Prototype Analysis
- Detects horizontal lines in a prototype image using Hough Line Transform
- Filters detected lines to remove noise and duplicates
- Calculates the header height (largest distance between lines)
- Determines the standard row height (second largest distance)

### 2. Table Structure Detection
- Analyzes screenshot images to find vertical lines defining table boundaries
- Applies scaling to handle different screen resolutions
- Creates a visual representation of the detected table structure with:
  - Table frame outlined in red
  - Header section highlighted in green
  - Data rows marked in yellow
  - Column separators in black

## Technical Approach

### Image Processing Pipeline
1. **Pre-processing**:
   - Convert images to grayscale
   - Apply binary thresholding to isolate table structures
   - Use morphological operations to enhance features

2. **Line Detection**:
   - Use Hough Line Transform with optimized parameters
   - Filter lines based on orientation (horizontal/vertical)
   - Sort and group lines to identify structural elements

3. **Structure Recognition**:
   - Identify table boundaries from vertical lines
   - Apply prototype-based measurements to reconstruct row structure
   - Scale measurements based on screen resolution differences

4. **Visualization**:
   - Generate color-coded output with different structural elements

## Technologies Used

- **Python 3.8+**
- **OpenCV 4.8.1**: For all image processing and computer vision operations
- **NumPy 1.24.3**: For numerical operations and array manipulation
- **Matplotlib 3.7.2**: For visualization of results

## Computer Vision Techniques

- **Thresholding**: To isolate table structures from backgrounds
- **Morphological Operations**: To enhance line structures
- **Hough Line Transform**: To detect straight lines in images
- **Spatial Filtering**: To remove noise and duplicate detections
- **Contour Analysis**: For structure boundary detection

## Installation

```bash
# Clone the repository
git clone https://github.com/Joseph0choa/Computer_Vision_Challenge
cd Computer_Vision_Challenge

# Create and activate virtual environment (optional but recommended)
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

## Usage

1. **Prepare Files**:
   - Place prototype images in the project directory (named `prototype_SAP.png`, `prototype_WEB.png`, etc.)
   - Place target screenshots in the project directory (named `SAP.png`, `WEB.png`, etc.)

2. **Run Detection**:
   - Open and execute the Jupyter Notebook `Table_detector.ipynb`

3. **View Results**:
   - The notebook will display visualizations of detected table structures
   - Results show table boundaries, headers, and rows with different colors
