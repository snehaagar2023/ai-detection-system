# AI Detection System — CS162 Final Project

This project is a binary classifier that distinguishes between human-written and AI-generated text, built as part of the CS162 final project at UCLA.

We trained a RoBERTa-based transformer model using the [HC3 dataset](https://huggingface.co/datasets/Hello-SimpleAI/HC3) and evaluated it against a hidden development set. The model identifies text written by ChatGPT versus real human responses across various domains including academic, Reddit-style, and open QA.

