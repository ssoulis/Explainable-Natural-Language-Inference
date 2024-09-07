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
* [Future Work](#Future-Work)
* [License](#license)

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
├── Datasets/                      # Folder containing datasets (SNLI, MNLI, ANLI)
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

4. Ensemble Model Training in Jupyter Notebook

For training an ensemble of models, open the **ensemble_xxx.ipynb** notebook under the **NLI directory**:
For this example we are going to train a CapsuleNet ensemble model.
```bash
   jupyter notebook ensemble-CapsuleNet-simple.ipynb
```

5. Explainability Analysis in Jupyter Notebook
   
To generate LIME explanations, open the **deberta-lime.ipynb** notebook from the **Explainability directory**
```bash
   jupyter notebook deberta-lime.ipynb
   ```
To generate  SHAP explanations, open the **deberta-shap.ipynb** notebook from the **Explainability directory**:
```bash
   jupyter notebook deberta-shap.ipynb
   ```

## Results 


Our experimental results demonstrated significant performance improvements using stacking ensemble techniques. The best-performing ensemble model surpassed the best individual transformer model by 5.31% on the MNLI-m and MNLI-mm tasks.

Performance of different models on NLI tasks:
| Model        | MNLI-m Accuracy | MNLI-mm Accuracy |
|--------------|-----------------|---------------|
| RoBERTa(Large)| 90.2%          | 90.2%         | 
| ALBERT(XXLarge V1)| 90.8%      |90.8%             | 
| DeBERTa(Large V3  | 91.8%           | 91.9%         | 
| T5(11B)           | 92.2%           | 91.9%         |
| **CapsuleNet(Ensemble)** | **96.7%**        | **96.8%**        |


## Explainability Methods

We implemented the LIME and SHAP explainability techniques to provide insights into the decision-making process of the transformer models. This helps visualize how the models utilize words and contextual information for their predictions.

* [LIME](https://github.com/marcotcr/lime) (Local Interpretable Model-agnostic Explanations): Provides instance-specific interpretations.
* [SHAP](https://github.com/shap/shap) (SHapley Additive exPlanations): Gives both local and global explanations for the model’s behavior.


## Future Work

Future work will focus on addressing the limitations identified in this research. 

* One of the primary areas for improvement is enhancing the model's ability to identify and evaluate semantic connections between sentences.
* This will involve refining the model's understanding of more complex relationships, such as metaphorical or inferential reasoning.
* Additionally, we will explore different types of training data to reduce biases that may emerge during model training. This will help the model generalize better across a wider range of scenarios.
* We also plan to test more sophisticated techniques, including dynamic reweighting of inputs, which would allow the model to adjust the importance of input features based on context.
* Furthermore, we will investigate domain adaptation strategies to improve the model's performance in handling specific domains.
* Lastly, we will use explainability methods such as **Attention Visualization** to explore the model's behavior more deeply, particularly in cases where the model produces incorrect inference results. These methods will help us better understand why errors occur and guide further improvements.

Some initial code for the Attention Visualization technique is already written and available in the **Explainability folder**.

Open the notebook below to run the Attention Visualization explainer:
```bash
jupyter notebook deberta-explainability-attention-visualization.ipynb
```
## License 

This repository is licensed under the MIT License. See the [LICENSE](https://github.com/ssoulis/Explainable-Natural-Language-Inference/blob/main/LICENSE) file for more details.

