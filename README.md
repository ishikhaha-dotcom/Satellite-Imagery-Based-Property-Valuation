# Satellite-Imagery-Based-Property-Valuation

---

# Multimodal Property Price Prediction

This project predicts property prices by combining **traditional housing data** with **satellite imagery analysis**, demonstrating how structured tabular features and visual context can be fused to achieve more accurate and interpretable real-estate valuations.



## Project Overview

The project follows a **multimodal machine learning pipeline**:

### 1. Exploratory Data Analysis (EDA)

* Analyzed property price distributions
* Studied relationships between price and features such as:

  * Location
  * Area
  * Number of rooms

### 2. Tabular Data Modeling

Trained and evaluated multiple regression models on structured housing data:

* **Linear Regression (LR)**
* **Polynomial Regression**
* **XGBoost (XGB)**

XGBoost achieved the best performance among tabular models.

### 3. Image-Based Modeling

To capture spatial and environmental context:

* Trained a **CNN using ResNet18** on satellite images
* Chosen for its lightweight architecture and computational efficiency
* Satellite images were fetched using the **Google Maps Static API**

### 4. Model Interpretability

* Applied **Grad-CAM** to visualize image regions most influential in CNN predictions
* Helps understand how surroundings impact property valuation

### 5. Multimodal Fusion Model

* Combined predictions from:

  * Tabular XGBoost model
  * Image-based CNN model
* Used **stacking** with a **meta-learner**
* Achieved better performance than individual models

**Result:** A more accurate and interpretable property price prediction system using both numerical and visual data.



## Project Files

| File Name                              | Description                                               |
| -------------------------------------- | --------------------------------------------------------- |
| **23410039_report.pdf**                | Comprehensive project report with methodology and results |
| **23410039_final.csv**                 | Final test-set prediction outputs                         |
| **preprocessing+model-training.ipynb** | Main notebook for preprocessing, training, and evaluation |
| **data_fetcher.ipynb**                 | Script to download satellite images using Google Maps API |

---

## Dataset

* **Dataset Name:** Data-CDC
* **Source:** Kaggle
* **Size:** ~3.1 GB

Due to its size, the dataset is **not included in this repository** and must be downloaded separately.

**Kaggle Dataset URL:**
[https://www.kaggle.com/datasets/tasteing/data-cdc](https://www.kaggle.com/datasets/tasteing/data-cdc)

---

## Downloading the Dataset

### 1. Install Kaggle CLI

```bash
pip install kaggle
```

### 2. Configure Kaggle API Token

Place your `kaggle.json` file in the correct directory and set permissions:

```bash
chmod 600 ~/.kaggle/kaggle.json
```

### 3. Download and Extract Dataset

```bash
mkdir -p data
kaggle datasets download -d tasteing/data-cdc -p data
unzip data/data-cdc.zip -d data
```



## Expected Data Structure

```text
data/
 ├── images_train/
 ├── images_test/
 ├── train.csv
 └── test.csv
```



## Getting Started

1. Download the dataset using the steps above
2. Run **`data_fetcher.ipynb`** (optional) to fetch additional satellite images
3. Execute **`preprocessing+model-training.ipynb`** to train models and generate predictions
4. Refer to **`23410039_report.pdf`** for detailed methodology and analysis
5. Check **`23410039_final.csv`** for final prediction results



## Key Takeaways
* Multimodal learning improves prediction accuracy
* Satellite imagery provides valuable spatial context
* Grad-CAM enhances interpretability of CNN-based models
* Fusion models outperform single-modality approaches


