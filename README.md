# BCG Signal Processing for Heart Rate Estimation

## Project Overview
This project processes Ballistocardiogram (BCG) signals to estimate heart rate (HR) and compares the results with reference electrocardiogram (ECG) measurements. The workflow includes:

1. Data loading and synchronization of BCG and reference RR interval data
2. Signal preprocessing (resampling, filtering, artifact removal)
3. Feature extraction using wavelet decomposition
4. Heart rate estimation
5. Performance evaluation against reference data

## Key Features
- Robust timestamp handling for data synchronization
- Signal processing pipeline for BCG analysis
- Comprehensive error metrics (MAE, RMSE, MAPE)
- Visualization tools (Bland-Altman plots, correlation analysis)

## Setup Instructions

### Prerequisites
- Python
- Required Python packages (install via pip):

```bash
pip install numpy pandas matplotlib scipy pywavelets heartpy pyfftw seaborn scikit-learn
```

### Data Structure
Place your data in the following structure:
```
data/
└── dataset/
    └── data/
        ├── 01/          # Subject folder (01-32)
        │   ├── bcg/     # BCG data files
        │   └── reference/RR/  # Reference RR interval files
        ├── 02/
        │   ├── bcg/
        │   └── reference/RR/
        ... (remaining subjects)
```

### Running the Analysis
1. Open `course_project.ipynb` in the `code` folder
2. Update the `dataset_folder` path in the notebook to point to your data directory
3. Run the Jupyter notebook cells sequentially:
   - First load the data
   - Then perform synchronization
   - Run the analysis pipeline
   - View the results and visualizations

## Output Files
The analysis generates:
- Resampled BCG data files
- Performance metrics (MAE, RMSE, MAPE)
- Visualization plots:
  - Bland-Altman plots
  - Correlation plots
  - Boxplots of HR distributions

Saved in the `results` directory specified in the notebook.

## Customization
To analyze different subjects:
1. Modify the `selected_file` variable to choose which BCG file to process
2. Adjust processing parameters (filter cutoffs, wavelet settings) as needed
