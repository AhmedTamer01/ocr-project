# OCR & LLM-Powered Text Correction Pipeline 📄🤖

An end-to-end Optical Character Recognition (OCR) system that not only extracts text from images but leverages Large Language Models (LLMs) to intelligently correct misspellings and grammatical errors caused by noisy scans.

## 🚀 Project Overview

Traditional OCR engines often fail when dealing with low-resolution images, handwritten notes, or unusual fonts. The extracted text is usually littered with spelling mistakes and formatting errors. 

This project solves that by adding a post-processing layer using an advanced **Large Language Model (LLM)**. After the OCR engine extracts the raw text, the text is fed into a fine-tuned causal language model that understands contextual semantics and corrects the errors seamlessly.

## ⚙️ Methodology & Architecture

1. **Text Extraction (OCR)**: Extracts raw bounding boxes and text from images or scanned documents.
2. **LLM Integration & Quantization**:
   - Leveraged the `transformers` library to load a massive Causal Language Model.
   - Utilized **BitsAndBytesConfig** (4-bit or 8-bit quantization) to load the LLM efficiently on consumer-grade GPUs without running out of VRAM.
   - Integrated `accelerate` and `xformers` to speed up inference and optimize memory usage.
3. **Prompt Engineering for Correction**: Designed strict zero-shot and few-shot prompts instructing the model to act as a proofreader, returning only the corrected text.
4. **User Interface**: Built an interactive web application using **Gradio** allowing users to upload images and see the raw vs. LLM-corrected text side by side.

## 🛠️ Tech Stack & Libraries Used

- **Deep Learning / NLP:** Hugging Face `transformers`, `torch` (PyTorch)
- **Model Optimization:** `bitsandbytes`, `accelerate`, `xformers`
- **Frontend / UI:** Gradio
- **Data Handling:** `requests`, `regex`

## 📈 Key Results

- Significantly reduced the Word Error Rate (WER) of standard OCR outputs by applying contextual LLM corrections.
- Successfully deployed a lightweight UI via Gradio for easy demonstration and testing.

---
*This repository is part of my AI Engineer / Data Scientist Portfolio.*
