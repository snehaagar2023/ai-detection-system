# AI Detection System — CS162 Final Project

**Contributors:** Sneha Agarwal, Kevin Lu, Samuel Perrott  
**Course:** CS162 — UCLA

---

## Project Overview

This project is a binary text classification system designed to detect whether a given text is AI-generated or human-written. We developed and evaluated multiple models for this task, including RoBERTa, stylometric feature extraction using Random Forest, and fine-tuned Google T5 models. This work was conducted as part of the CS162 final project at UCLA.

We trained our models primarily using the [Human ChatGPT Comparison Corpus (HC3)](https://huggingface.co/datasets/Hello-SimpleAI/HC3), along with additional human-written data from [IELTS Writing Task Evaluation](https://huggingface.co/datasets/chillies/IELTS-writing-task-2-evaluation). Our models were evaluated on a provided dev set consisting of both AI-generated and human-written text across multiple domains, including academic writing, open QA, Reddit-style discussions, and other open-ended text domains.

Our best-performing model is `t5-ethics-ai-human-detector`, a fine-tuned version of Google's T5 model.

---

## Repository Contents

This repository contains all code, data files, trained models, and evaluation results required to reproduce our results and run inference on the dev set.

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

## Loading the Trained Model

The fine-tuned T5 model is saved in the `t5-ethics-ai-human-detector/` directory. You can manually load the model for inference as follows:

```python
from transformers import T5Tokenizer, T5ForSequenceClassification

model = T5ForSequenceClassification.from_pretrained("t5-ethics-ai-human-detector")
tokenizer = T5Tokenizer.from_pretrained("t5-small")
```

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
