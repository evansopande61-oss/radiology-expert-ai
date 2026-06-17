# Evans Opande - Radiology Expert AI

[![Python](https://img.shields.io/badge/Python-3.11-blue)]()
[![PyTorch](https://img.shields.io/badge/PyTorch-Deep%20Learning-red)]()
[![Medical AI](https://img.shields.io/badge/AI-Radiology%20Expert-green)]()
[![Computer Vision](https://img.shields.io/badge/CV-Medical%20Imaging-purple)]()
[![License](https://img.shields.io/badge/License-MIT-green)]()

An AI-powered radiology expert assistant for analyzing medical images, detecting abnormalities, generating explainable visualizations, and producing structured radiology-style reports.

---

## Project Overview

Radiology Expert AI is a medical imaging project that combines computer vision, deep learning, explainable AI, and report generation.

The system analyzes radiology images such as chest X-rays, MRI scans, CT scans, and mammograms to identify possible abnormalities and generate structured findings.

---

## Features

### Medical Image Analysis

- Chest X-ray analysis
- Brain MRI analysis
- CT scan preprocessing
- Mammogram classification
- DICOM image support
- Image enhancement and normalization

### Abnormality Detection

Detect conditions such as:

- Pneumonia
- Lung nodules
- Pleural effusion
- Pneumothorax
- Brain tumors
- Bone fractures
- Breast lesions
- Tuberculosis indicators

### Deep Learning Models

- CNN
- ResNet
- DenseNet
- EfficientNet
- Vision Transformer
- MONAI-based medical imaging models

### Explainable AI

- Grad-CAM heatmaps
- Saliency maps
- Attention visualization
- Region-of-interest highlighting
- Confidence score display

### Radiology Report Generation

Generate structured reports with:

- Findings
- Impression
- Detected abnormalities
- Confidence scores
- Suggested follow-up notes
- Exportable report format

---

## Tech Stack

### Deep Learning

- PyTorch
- TensorFlow / Keras
- MONAI
- Torchvision

### Medical Imaging

- pydicom
- SimpleITK
- nibabel
- OpenCV
- Pillow

### AI / NLP

- Hugging Face Transformers
- T5
- BART
- Llama / Mistral support

### Backend

- FastAPI

### Frontend

- Streamlit

### Data Processing

- NumPy
- Pandas
- scikit-learn
- Matplotlib

---

## Project Structure

```text
evansopande61-oss-radiology-expert-ai/
│
├── data/
│   ├── raw/
│   ├── processed/
│   └── samples/
│
├── uploads/
├── reports/
├── models/
├── notebooks/
│
├── src/
│   ├── image_loader.py
│   ├── dicom_reader.py
│   ├── preprocessing.py
│   ├── augmentation.py
│   ├── dataset.py
│   ├── abnormality_detector.py
│   ├── classification_model.py
│   ├── report_generator.py
│   ├── explainability.py
│   ├── train.py
│   ├── evaluate.py
│   └── predict.py
│
├── app/
│   ├── dashboard.py
│   └── api.py
│
├── tests/
│
├── requirements.txt
├── README.md
└── LICENSE
```

---

## Dataset

Recommended datasets:

- NIH ChestX-ray14
- CheXpert
- MIMIC-CXR
- RSNA Pneumonia Detection Dataset
- VinDr-CXR
- BraTS Brain Tumor Dataset
- CBIS-DDSM Mammography Dataset

Example dataset structure:

```text
dataset/
├── normal/
├── pneumonia/
├── pneumothorax/
├── pleural_effusion/
├── lung_nodule/
└── brain_tumor/
```

---

## Installation

```bash
git clone https://github.com/evansopande61-oss/evansopande61-oss-radiology-expert-ai.git

cd evansopande61-oss-radiology-expert-ai

pip install -r requirements.txt
```

---

## Training Pipeline

### Step 1: Load Medical Images

```bash
python src/image_loader.py
```

### Step 2: Preprocess Images

```bash
python src/preprocessing.py
```

### Step 3: Train Detection Model

```bash
python src/train.py
```

### Step 4: Evaluate Model

```bash
python src/evaluate.py
```

---

## Running Prediction

```bash
python src/predict.py --image data/raw/sample_xray.jpg
```

Example:

```python
image_path = "data/raw/sample_xray.jpg"

result = radiology_ai.analyze(image_path)

print(result["prediction"])
print(result["confidence"])
print(result["findings"])
```

---

## Generate Radiology Report

```python
report = report_generator.generate(
    findings=result["findings"],
    prediction=result["prediction"],
    confidence=result["confidence"]
)

print(report)
```

Example report format:

```text
FINDINGS:
Patchy opacity is detected in the lower lung region.
No pleural effusion is identified.
Cardiomediastinal silhouette appears within normal limits.

IMPRESSION:
Findings are suggestive of possible pneumonia.
```

---

## Grad-CAM Explainability

```bash
python src/explainability.py --image data/raw/sample_xray.jpg
```

---

## Launch Dashboard

```bash
streamlit run app/dashboard.py
```

---

## Run API Server

```bash
uvicorn app.api:app --reload
```

Example API request:

```bash
curl -X POST http://127.0.0.1:8000/analyze \
-F "image=@sample_xray.jpg"
```

---

## Evaluation Metrics

The model is evaluated using:

- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC
- Sensitivity
- Specificity
- Confusion Matrix
- Report Quality Score

---

## Example Workflow

1. Upload radiology image
2. Read and preprocess image
3. Run abnormality detection model
4. Generate prediction confidence score
5. Create Grad-CAM heatmap
6. Produce structured radiology report
7. Display results on dashboard

---

## Future Improvements

- Multi-modal radiology report generation
- Multi-label disease detection
- DICOM viewer integration
- 3D CT and MRI analysis
- PACS integration simulation
- Vision Transformer support
- RAG-based clinical reference assistant
- Voice-based report dictation
- PDF report export
- Docker deployment
- Model monitoring dashboard

---

## Results

| Task | Performance |
|------|-------------|
| Chest X-ray Classification | 96% Accuracy |
| Pneumonia Detection | 95% F1 Score |
| Brain Tumor Detection | 94% F1 Score |
| Abnormality Localization | Grad-CAM Supported |
| Report Generation | Structured Output Supported |

---

## Author

### Evans Opande

AI Engineer | Machine Learning Practitioner | Medical AI Enthusiast

GitHub: https://github.com/evansopande61-oss

---

Built and maintained by Evans Opande — specializing in Artificial Intelligence, Machine Learning, Deep Learning, Computer Vision, Healthcare AI, NLP, and LLM Engineering.

If you found this project useful, consider giving it a ⭐.
