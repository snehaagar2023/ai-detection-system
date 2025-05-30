# AI Detection System — CS162 Final Project

Contributors: Sneha Agarwal, Kevin Lu, Samuel Perrott

This project is a binary classifier that classifies text as human-written and AI-generated, built as part of the CS162 final project at UCLA.

We trained a RoBERTa-based transformer model using the [HC3 dataset](https://huggingface.co/datasets/Hello-SimpleAI/HC3) and evaluated it against a hidden dev set. The model identifies text written by ChatGPT versus real human responses across various domains including academic, Reddit-style, and open QA.

