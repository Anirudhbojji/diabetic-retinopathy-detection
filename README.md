# Diabetic Retinopathy Detection

A deep-learning web app that classifies retinal fundus images by diabetic retinopathy severity. Built as a B.Tech mini project by Anirudh Bojji & Siddharth Bollu.

Diabetic retinopathy (DR) is a chronic eye disease that affects people with diabetes and is a leading cause of blindness in diabetic patients. Early detection and treatment can prevent severe vision loss — machine learning models can help by classifying retinal images automatically.

## How it works

A CNN (Keras/TensorFlow) classifies an uploaded retinal image into one of five classes:

| Class | Meaning |
|---|---|
| `No_DR` | No diabetic retinopathy |
| `Mild` | Mild non-proliferative DR |
| `Moderate` | Moderate non-proliferative DR |
| `Severe` | Severe non-proliferative DR |
| `Proliferate_DR` | Proliferative DR |

The Streamlit UI shows the predicted class along with recommended precautions.

## Running locally

```bash
pip install -r requirements.txt
streamlit run app.py
```

> **Note:** the trained model weights (`model.h5`) are not included in this repository due to size. Place your trained Keras model at the repo root as `model.h5` before running. The model expects 224×224 RGB input.
