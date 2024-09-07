# Explainable-Natural-Language-Inference

This repository contains the code and datasets used for the paper "Natural Language Inference with Transformer Ensembles and Explainability Techniques" by Isidoros Perikos and Spyro Souli.

## Getting Started

* [Introduction](#introduction)
* [Features](#features)
* [Project Structure](#project-structure)
* [Datasets](#datasets)
* [Installation](#installation)
* [Results](#results)
* [Explainability Methods](#explainability-methods)
* [To Do - Future Work](#To-Do---Future-Work)

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

```python 
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
*  [MNLI] (Multi-Genre Natural Language Inference): Includes over 400k sentence pairs from different genres.
*  [ANLI] (Adversarial NLI): Contains more challenging examples, focusing on adversarially constructed sentence pairs.


