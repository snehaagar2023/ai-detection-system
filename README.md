# AI Detection System

**Contributors:** Sneha Agarwal, Kevin Lu, Samuel Perrott  
**Course:** CS162 — UCLA

---

## Project Overview

This project is a binary text classification system designed to detect whether a given text is AI-generated or human-written. We developed and evaluated multiple models for this task, including RoBERTa, stylometric feature extraction using Random Forest, and fine-tuned Google T5 models. This work was conducted as part of the CS162 final project at UCLA.

We trained our models primarily using the [Human ChatGPT Comparison Corpus (HC3)](https://huggingface.co/datasets/Hello-SimpleAI/HC3), along with additional human-written data from the [IELTS Writing Task Evaluation dataset](https://huggingface.co/datasets/chillies/IELTS-writing-task-2-evaluation/viewer/default/train?p=1&views%5B%5D=train). Our models were evaluated on a provided dev set consisting of both AI-generated and human-written text across multiple domains, including academic writing, open QA, Reddit-style discussions, and other open-ended text domains.

Our best-performing model is `t5-ethics-ai-human-detector`, a fine-tuned version of Google's T5 model.

---

## Repository Contents

This repository contains all code, data files, and evaluation results required to reproduce our results and run inference on the dev set.

Note: You have to download the models from [here](https://drive.google.com/file/d/1a0l7UakV_sqBDMJimBj_BsW3zrVllCo1/view?usp=sharing)

```
├── README.md
├── requirements.txt
├── cs162-final-dev-main/                    # Provided dev set for evaluation
├── initial-roberta-ai-detector/             # RoBERTa training folder
├── initial-roberta-ai-detector.ipynb
├── initial-t5-ai-detector/                  # Initial T5 training folder
├── initial-t5-ai-detector.ipynb
├── t5-ethics-ai-human-detector/             # Final fine-tuned T5 model directory
├── t5-ethics-ai-human-detector.ipynb
├── t5-large-ai-detector/                    # Experiments with larger T5 variant
├── t5-large-ai-detector.ipynb
├── gptzero.ipynb                            # Stylometric feature extraction experiments
├── gpt-zero-comparison/                     # GPTZero comparison files
├── extracted_features.csv                  # Extracted stylometric features
├── ai_samples_for_zerogpt_2.csv            # External GPTZero test samples
├── combined_sample.csv                      # Combined dataset for model training
└── moredata-roberta-ai-detector.ipynb
```

---

## Setup Instructions

### Clone Repository

```bash
git clone [your-github-repo-url].git
cd [your-repo-name]
```

### Create Environment & Install Dependencies

```bash
python -m venv venv
source venv/bin/activate      # Mac/Linux
# venv\Scripts\activate       # Windows

pip install -r requirements.txt
```

---

## Dataset Summary

### Training Datasets:
- **Human ChatGPT Comparison Corpus (HC3)** - Primary training dataset
- **IELTS Writing Task Evaluation Dataset** (Hugging Face) - Additional human-written data

### Dev Set:
- Provided `cs162-final-dev-main/` folder for evaluation

---

## Models Developed

1. **RoBERTa-based classifier** - Initial approach using pre-trained RoBERTa
2. **Stylometric feature extraction with Random Forest** - Traditional ML approach using writing style features
3. **T5-small fine-tuned models** - Multiple variants of fine-tuned T5 models
4. **T5-large experiments** - Experiments with larger T5 variants
5. **t5-ethics-ai-human-detector** - Our best-performing final model

---

## Evaluation Domains

The models were evaluated across multiple text domains:
- Academic writing
- Open QA responses
- Reddit-style discussions
- Other open-ended text domains

---

## Usage Notes

- All Jupyter notebooks contain detailed experiments and model training processes
- The final model directory contains the complete fine-tuned model ready for inference
- Feature extraction results are saved in CSV format for analysis
- GPTZero comparison files are included for baseline comparisons

All experiments ran on an Nvidia A10 GPU. Compute provided by Bruin AI
