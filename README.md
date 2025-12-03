# CAFA-6 Protein Function Prediction – Weighted Ensemble Model

## Overview
This project implements a weighted ensemble model for protein function prediction as part of the CAFA-6 competition on Kaggle. The objective is to predict Gene Ontology functional terms for proteins by combining outputs from multiple base models to improve accuracy and reliability.

The weighted ensemble approach enables the model to integrate strengths from different methods, resulting in better performance on unseen protein sequences.

## Dataset
This work uses the CAFA-6 Protein Function Prediction dataset provided by the competition organizers on Kaggle.

Competition link  
https://www.kaggle.com/competitions/cafa-6-protein-function-prediction

Reference notebook  
https://www.kaggle.com/code/mafiosoquasar/cafa-6-protein-weighted-ensemble

## Architecture Description

### Data Processing
Raw protein sequences are loaded and processed to extract meaningful numerical features. This includes sequence cleanup, tokenization, encoding, and optional metadata extraction such as domain or alignment information.

### Base Models
Multiple base models are used to generate predictions for Gene Ontology terms. Each model focuses on different biological or sequence-based features. These predictors may include machine learning models, similarity-based methods, or deep learning models.

### Weighted Ensemble
Predictions from all base models are combined using a weighted averaging strategy. Weights are determined based on model performance or confidence scores. The ensemble produces the final probability distribution for each GO term associated with a protein.

### Output Generation
The final predictions are formatted according to the CAFA-6 submission structure. The system supports multi-label outputs because proteins frequently perform multiple biological functions.

### Evaluation
When ground truth annotations are available, evaluation metrics such as precision, recall, and F1 score are computed. This step assists in tuning the ensemble and analyzing performance.

## Project Structure
data_processing  
sequence_loader.py  
feature_extractor.py  

models  
base_model_1.py  
base_model_2.py  

ensemble  
weighted_ensemble.py  
aggregator.py  

evaluation  
metrics.py  
evaluation_pipeline.py  

output  
submission_formatter.py  

main.py  
README.md

## Key Features
Weighted ensemble model for enhanced predictive accuracy  
Modular design that supports easy integration of additional models  
Supports multi-label protein function prediction  
Compatible with CAFA-6 submission format  
Capable of processing large protein datasets  

## How to Run
Open the notebook and execute the pipeline including feature extraction, model inference, and ensemble prediction.  
Modify ensemble weights as needed for tuning.  
Export the final predictions in CAFA-6 submission format.

## Notes
The predictive performance depends significantly on the quality of input features and the diversity of the base models. Incorporating additional feature extraction techniques or new base models can further improve performance.

