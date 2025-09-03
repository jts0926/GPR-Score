# GPR Score Pipeline & Prediction

This repository provides the implementation of the **Generalized Patellofemoral Radiomics (GPR) Score**, as described in our manuscript. It includes two main workflows:  

1. **Model Training Pipeline** (`GPR_Score_pipeline.ipynb`)  
   - Full end-to-end pipeline to train the GPR Score model using radiomics features.  
   - Due to data privacy restrictions, the training data used in the manuscript cannot be shared directly.  
   - This notebook is provided for reproducibility and reference only.  

2. **Model Inference / Prediction** (`GPR_Score_Prediction.ipynb`)  
   - Apply a trained GPR Score model (saved as `.joblib`) to new datasets.  
   - Input must be radiomics features extracted from knee X-ray images.  
   - A **fake dataset** is provided for testing the workflow.  
   - For real applications, please prepare radiomics features as described below.  

---

## 🔑 Radiomics Feature Extraction

Before running prediction, extract radiomics features from medical images into a CSV format.  
We recommend using the [PatellaRadiomics](https://github.com/John136219655/PatellaRadiomics) toolkit, which is tailored for knee X-rays.  

- Each row = one subject/sample  
- First column = unique subject ID  
- Columns 1–754 = radiomics features  

---

## 🚀 Usage

### 1. Environment Setup
Install dependencies using the provided `requirements.txt`:

```bash
pip install -r requirements.txt
```

### 2. Training (Pipeline Notebook)
Open and run **`GPR_Score_Pipeline.ipynb`** to see the training workflow.  
⚠️ *Note: Data used in the manuscript cannot be shared, so this notebook is for demonstration/reference only.*

### 3. Prediction (Inference Notebook)
Open and run **`GPR_Score_Prediction.ipynb`**:  

- Loads the trained GPR Score model (`.joblib`) from `artifacts/models/`.  
- Loads radiomics features CSV (ID + 754 features).  
- Selects the required features and computes **GPR Score** for each sample.  
- Outputs predictions as a new CSV.  

---

## ⚠️ Notes on Data Privacy
- Patient data used in the manuscript is not publicly available due to privacy regulations.  
- The included fake dataset mimics the structure of the real dataset and can be used to test the prediction workflow.  
- To apply on new datasets, please extract radiomics features with [PatellaRadiomics](https://github.com/John136219655/PatellaRadiomics) and follow the format described above.  

---

## 📜 License
This repository is released under the MIT License. See [LICENSE](LICENSE) for details.
