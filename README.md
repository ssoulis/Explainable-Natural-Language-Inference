# Explainable-Natural-Language-Inference

This repository contains the code and datasets used for the paper "Natural Language Inference with Transformer Ensembles and Explainability Techniques" by Isidoros Perikos and Spyro Souli.

## Getting Started

* [Introduction](#introduction)
* [Features](#features)
* [Project Structure](#project-structure)
* [Datasets](#datasets)
* [Installation](#installation)
* [Usage](#usage)
* [Results](#results)
* [Explainability Methods](#explainability-methods)
* [Future Work](Future-Work)

## Introduction

Natural Language Inference (NLI) is a challenging task in Natural Language Processing (NLP) that involves determining whether a given hypothesis can be inferred from a given premise. This repository provides the implementation of transformer-based models, such as  ALBERT, RoBERTa and DeBERTa, for NLI tasks across several datasets including SNLI, GLUE, and ANLI.
We also incorporate explainability techniques such as LIME and SHAP to interpret the decision-making processes of the models. Ensemble methods like stacking are utilized to improve accuracy and robustness.


## Features

*  Implementation of multiple transformer models: ALBERT, RoBERTa and DeBERTa
*  Stacking ensemble methods for improved inference accuracy.
*  Explainability with LIME and SHAP to interpret how models make decisions.
*  Support for MNLI, ANLI, and SNLI datasets for NLI tasks.
*  Detailed result analysis and performance comparisons.
  

## Project Structure

```bash
├── Datasets/                     # Folder containing datasets (SNLI, MNLI, ANLI)
├── Explainability/                # Code for LIME and SHAP explainability techniques. There is also code for the Attention Visulization method.
├── Figures and Charts/            # Performance charts and visualizations
├── LIME explanations/             # LIME explanations for NLI tasks
├── Models/                        # Ensemble transformer models 
├── NLI/                           # Scripts for training and evaluating NLI tasks
├── Predictions/                   # Folder for storing model predictions
├── SHAP explanations/             # SHAP explanations for NLI tasks
└── README.md                      # Readme file with project details
```

## Datasets

This repository uses several widely recognized datasets for NLI:

*  [SNLI](https://www.kaggle.com/datasets/stanfordu/stanford-natural-language-inference-corpus) (Stanford Natural Language Inference): Provides around 570k sentence pairs.
*  [MNLI](https://www.kaggle.com/datasets/thedevastator/nli-dataset-for-sentence-understanding) (Multi-Genre Natural Language Inference): Includes over 400k sentence pairs from different genres.
*  [ANLI](https://www.kaggle.com/datasets/thedevastator/anli-a-large-scale-nli-benchmark-dataset) (Adversarial NLI): Contains more challenging examples, focusing on adversarially constructed sentence pairs.

All datasets are available through the HuggingFace Datasets library or can be downloaded manually from kaggle.

## Installation 

To use the code in this repository clone the repository:
   ```bash
    git clone https://github.com/ssoulis/Explainable-Natural-Language-Inference.git
    cd Explainable-Natural-Language-Inference
   ```

## Usage

1. Setup and Run in Jupyter Notebook
    ```bash
    pip install jupyter
    ```
   Once installed, launch Jupyter Notebook:
   ```bash
    jupyter notebook
   ```
  After launching, navigate to the Explainable-Natural-Language-Inference directory in the Jupyter interface, and open the relevant notebook files, located in the 
  NLI or Explainability directories. The notebooks will guide you through running model training, evaluation, and explainability analysis.

2. Model Training/Evaluating in Jupyter Notebook
   Inside the NLI directory, open the **deberta.ipynb** notebook. This notebook will guide you through training a transformer model for NLI tasks.
   This example will use the DeBERTa model.
   
   Navigate to the directory:
   ```bash
   cd NLI
    ```
   Open the notebook:
   ```bash
   jupyter notebook deberta.ipynb
   ```

3. Ensemble Model Training in Jupyter Notebook

   For training an ensemble of models, open the **ensemble_xxx.ipynb** notebook under the **NLI directory**:
   For this example we are going to train a CapsuleNet ensemble model.
   ```bash
   jupyter notebook ensemble-CapsuleNet-simple.ipynb
    ```

4. Explainability Analysis in Jupyter Notebook
   To generate LIME explanations, open the **deberta-lime.ipynb** notebook from the **Explainability directory**
   ```bash
   jupyter notebook deberta-lime.ipynb
   ```
   To generate  SHAP explanations, open the **deberta-shap.ipynb** notebook from the **Explainability directory**:
   ```bash
   jupyter notebook deberta-shap.ipynb
   ```





