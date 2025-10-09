This is code regarding whether CNN can detect cancerous tissue from pathology slides.

Source of images: Spanhol, F., Oliveira, L. S., Petitjean, C., Heutte, L., A Dataset for Breast Cancer Histopathological Image Classification, IEEE Transactions on Biomedical Engineering (TBME), 63(7):1455-1462, 2016. [pdf]

Dataset: BreakHis (Breast Cancer Histopathological Database): 
- Total Images:** 7,909
- Total Patients:** 82
- Categories:** Benign (31.4%), Malignant (68.6%)
- Magnifications:** 40X, 100X, 200X, 400X
- Image Size:** 700 × 460 pixels
- Format:** PNG, RGB

Data Splits (Patient-Level): 
- Training: 5,213 images (56 patients)
- Validation: 1,319 images (13 patients)
- Test: 1,377 images (13 patients)

Quick Start

Clone this repository:
```bash
   git clone https://github.com/YOUR-USERNAME/pathology-cnn-classification.git
   cd pathology-cnn-classification
```

DATA ACCESS GUIDE

1. Mount Google Drive first
from google.colab import drive
drive.mount('/content/drive')

2. Import Libraries
import os
import numpy as np
import matplotlib.pyplot as plt
import h5py
import pandas as pd
from PIL import Image
import tqdm as tqdm

3. Define paths
RESULTS_PATH = '/content/drive/MyDrive/pathology_cnn_project/results'

4. Load train/val/test split
train_df = pd.read_csv(f'{RESULTS_PATH}/breakhis_train_split.csv')
val_df = pd.read_csv(f'{RESULTS_PATH}/breakhis_val_split.csv')
test_df = pd.read_csv(f'{RESULTS_PATH}/breakhis_test_split.csv')

print(f"Train: {{len(train_df)}} images")
print(f"Val: {{len(val_df)}} images")
print(f"Test: {{len(test_df)}} images")
