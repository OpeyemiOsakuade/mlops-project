# Practical MLOps with Vertex AI: End-to-End Model Deployment Examples

This repository contains a collection of hands-on, production-focused MLOps workflows using **Google Cloud Vertex AI**.  
Each folder demonstrates a different model deployment pattern, including custom PyTorch containers, pretrained Hugging Face model deployment, and AutoML tabular pipelines.

The goal of this project is to provide practical, reproducible examples that show how modern ML systems are trained, packaged, deployed, and served on Vertex AI.

---

## Repository Structure

### `bert_agnews/` — Custom PyTorch BERT Deployment (Custom Container + FastAPI)
This example demonstrates how to deploy a **fine-tuned DistilBERT text classifier** using a **custom prediction container**.

Key features:
- Training a lightweight BERT classifier on a small AG News subset  
- Packaging a PyTorch model (`model.pt`) with custom inference logic  
- FastAPI-based prediction service (`server.py`)  
- Reproducible Docker image built using Cloud Build  
- Deployment to a Vertex AI Endpoint  
- Real-time predictions over HTTP  

This example shows how to deploy **any PyTorch model** using a custom container approach without requiring TorchServe.

---

### `imdb_model/` — Deploying a Pretrained Hugging Face Model on Vertex AI
This example focuses on **deploying an existing Hugging Face model** with minimal setup.

It demonstrates:
- Loading a pretrained sentiment model  
- Creating a simple inference wrapper for Vertex AI  
- Uploading the model to Vertex Model Registry  
- Deploying directly to a managed Endpoint  
- Making real-time sentiment predictions  

This serves as an easy quickstart for using Vertex AI with pretrained transformer models.

---

### `dry_beans/` — AutoML Tabular Example
This folder contains a complete **AutoML Tabular pipeline** using Vertex AI.

It covers:
- Uploading the Dry Beans dataset to Cloud Storage  
- Creating a Vertex AI Dataset  
- Running AutoML model training  
- Evaluating the generated model  
- Deploying the AutoML model to an Endpoint  

Perfect for users who want a **no-code / low-code** introduction to Vertex AI training and deployment.

---

## Session Context

This repository was created for the workshop:

**Practical MLOps with Vertex AI: Deploying ML Models**  
DevFest Scotland 2025  
29 November 2025, 2:30–3:30 PM GMT

Participants learned the complete MLOps workflow—from data preparation to deployment—through three fully working, real-world examples.

---

## Requirements

To run these examples, you will need:
- A Google Cloud project  
- Vertex AI API enabled  
- Cloud Build + Artifact Registry enabled (for custom containers)  
- Python 3.9+  
- Google Colab or Vertex AI Workbench  
- Basic familiarity with Python and machine learning concepts  

---
```mermaid
flowchart TD

    %% BERT AG NEWS (Custom Container)
    A[bert_agnews] --> A1[Train BERT on AG News]
    A --> A2[Build Custom Docker Container]
    A --> A3[Deploy to Vertex AI Endpoint]

    %% IMDB HUGGINGFACE (Pretrained Deployment)
    B[imdb_model] --> B1[Load Pretrained HuggingFace Model]
    B --> B2[Wrap Inference Code]
    B --> B3[Upload to Vertex Model Registry]
    B --> B4[Deploy to Endpoint]

    %% AUTO ML (Tabular)
    C[dry_beans] --> C1[Upload Tabular Dataset]
    C --> C2[AutoML Training]
    C --> C3[Evaluate Model]
    C --> C4[Deploy AutoML Model]

    root[Repository] --> A
    root --> B
    root --> C
## License

MIT License

---


