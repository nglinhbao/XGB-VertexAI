# XGBoost Model Training Pipeline with Ray Tune

This repository contains a machine learning pipeline that processes data, performs distributed hyperparameter tuning using Ray Tune, and trains an XGBoost model at scale.

## Notebooks Overview

### 1. Data Processing (`data_processing.ipynb`)
Handles initial data preparation and cloud setup:
- Processes raw dataset
- Creates BigQuery dataset and table
- Uploads processed data to Google Cloud Storage
- Sets up necessary GCP infrastructure

Key components:
- BigQuery table creation
- Data transformation pipeline
- GCS bucket configuration
- Data upload procedures

### 2. Hyperparameter Tuning (`hyper_tuning.ipynb`)
Implements distributed model training and hyperparameter optimization:
- Loads data from BigQuery
- Performs distributed training using Ray
- Optimizes hyperparameters using Bayesian search
- Saves best model and metrics

Key features:
- Distributed data loading from BigQuery
- XGBoost model training with Ray's XGBoostTrainer
- Bayesian optimization for hyperparameter tuning
- Parallel trial execution
- Model checkpoint management

## Model Training

The training pipeline:
1. Loads data from BigQuery using Ray's distributed data loading
2. Trains XGBoost models with different hyperparameter configurations
3. Uses 2-way concurrent training for efficiency
4. Optimizes for minimum RMSE
5. Saves model checkpoints and metrics

## Results

The pipeline outputs:
- Best hyperparameters found
- Optimal model performance metrics (RMSE)
- Model checkpoints for the best performing configuration
- Training history and metrics