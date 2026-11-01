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

> **Note:** the trained model weights (`model.h5`) are not included in this repository due to size. Train the model yourself (below) or place an existing Keras model at the repo root as `model.h5`. The model expects 224×224 RGB input.

## Training

`train.ipynb` trains the CNN from scratch and saves the weights as `model.h5` (the file `app.py` loads).

It expects the dataset in a `dataset1/` folder at the repo root, with one subfolder per class:

```
dataset1/
├── No_DR/
├── Mild/
├── Moderate/
├── Severe/
└── Proliferate_DR/
```

Each subfolder contains the retinal images for that class (e.g. from the [APTOS 2019 / Kaggle DR dataset](https://www.kaggle.com/competitions/aptos2019-blindness-detection)). Images are resized to 224×224 and normalized; the notebook also prints a classification report and confusion matrix on a held-out 20% test split.
