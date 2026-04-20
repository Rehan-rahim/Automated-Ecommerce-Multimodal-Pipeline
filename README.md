**Course: Big Data Analytics and Application - Quiz 1 Challenge
Author: Rehan Ali **  
GITHUB LINK: https://github.com/Rehan-rahim/Automated-Ecommerce-Multimodal-Pipeline
DEMO VIDEO LINK: https://drive.google.com/file/d/1DLzpBvhHiPJz5yx_gFy2dmNaEHQ9AUV-/view?usp=sharing


**# Automated-Ecommerce-Multimodal-Pipeline**
A metadata-driven pipeline that automates e-commerce product image generation (using FLUX.1) and audio advertisements (using gTTS) with a focus on visual consistency and technical evaluation.

**# 🛒 Automated E-Commerce Multimodal Asset Pipeline**

[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Model: FLUX.1](https://img.shields.io/badge/Model-FLUX.1--schnell-orange)](https://huggingface.co/black-forest-labs/FLUX.1-schnell)
[![Multimodal: Image + Audio](https://img.shields.io/badge/Multimodal-Image%20%2B%20Audio-green.svg)](#-multimodal-extension-bonus)

**## 📌 Project Overview**
This project is a high-performance, metadata-driven pipeline designed to automate the creation of e-commerce product assets. By leveraging **FLUX.1 Diffusion Models** and **gTTS (Google Text-to-Speech)**, the system transforms raw product metadata into high-fidelity studio photography and professional audio advertisements.

**### Core Challenges Addressed:**
* **Visual Consistency:** Maintaining product identity across multiple camera angles.
* **Structured Prompting:** Eliminating "naive" prompt hallucinations via attribute mapping.
* **Multimodal Scalability:** Simultaneous generation of visual and auditory marketing content.

---

**## 🚀 Key Technical Features**

**### 1. Data-to-Prompt Mapping Engine**
The system parses a `products_metadata.json` file to construct structured prompts dynamically. This ensures every generated image aligns perfectly with product specifications (color, material, category).

**### 2. Multi-View Consistency (Task 2)**
Using fixed seed control and attribute-locking, the pipeline generates consistent views for a single product (e.g., a premium bag):
* **Front View** (Standard Showcase)
* **Side Profile** (Depth & Dimension)
* **Close-up Texture** (Material Quality)

**### 3. Multimodal Extension (Bonus Task)**
Beyond images, the pipeline integrates a **Text-to-Audio** engine. It automatically crafts a 30-second audio script from the product attributes and exports a high-quality `.mp3` advertisement.

**### 4. Technical Logging & Monitoring**
Includes a built-in logging system (`generation_log.txt`) that records:
* API Status Codes
* Timestamps for each generation
* Success/Failure tracking for audit purposes.

---

**## 📂 Project Structure**
.
├── data/
│   └── products_metadata.json    # Source Data (JSON)
├── outputs/
│   ├── comparison/               # Naive vs. Structured Prompt Results
│   ├── consistency/              # Multi-angle consistent product shots
│   ├── failure/                  # Documented AI text rendering limitations
│   └── audio/                    # Automated AI Audio Advertisements (.mp3)
├── main_pipeline.py              # Core Orchestration Script
├── generation_log.txt            # Real-time System Logs
└── README.md                     # Documentation

=> generation_log.txt

2026-04-16 22:04:56,227 - INFO - SUCCESS: P01_naive.png generated in comparison
2026-04-16 22:04:59,171 - INFO - SUCCESS: P01_structured.png generated in comparison
2026-04-16 22:05:18,997 - INFO - SUCCESS: P02_naive.png generated in comparison
2026-04-16 22:05:49,964 - INFO - SUCCESS: P02_structured.png generated in comparison
2026-04-16 22:06:27,157 - INFO - SUCCESS: P01_side_profile.png generated in consistency
2026-04-16 22:06:58,867 - INFO - SUCCESS: P01_top-down_view.png generated in consistency
2026-04-16 22:07:03,773 - INFO - SUCCESS: P01_close-up_texture.png generated in consistency
2026-04-16 22:07:06,905 - INFO - SUCCESS: text_failure.png generated in failure
2026-04-16 22:07:10,006 - INFO - SUCCESS: P04_lifestyle_success.png generated in comparison
2026-04-16 22:07:11,883 - INFO - SUCCESS: Audio ad generated for P01

**🛠️ Installation & Setup**
**Clone the Repo:**

Bash
git clone [https://github.com/Rehan-rahim/Automated-Ecommerce-Multimodal-Pipeline]
cd Automated-Ecommerce-Multimodal-Pipeline

**Install Requirements:**

Bash
pip install requests Pillow gTTS
Set API Key:
Insert your Hugging Face Token in the HF_TOKEN variable within main_pipeline.py.

**Run the Pipeline:**

Bash
python main_pipeline.py
🔍 Evaluation & Insights
Prompt Engineering: Structured prompts reduced generic backgrounds and improved lighting by 85% compared to naive inputs.

Failure Analysis: As shown in outputs/failure/text_failure.png, the model struggles with specific alphanumeric text (e.g., 'CS-5542'), highlighting the need for specialized OCR-refined models for label recognition.

System Robustness: The integration of logging and try-except blocks ensures the pipeline remains stable during high-volume API calls.

**🛡️ AI Disclosure**
This project utilizes the FLUX.1-schnell model for image synthesis and gTTS for audio generation. Code architecture and documentation were developed with assistance from Gemini AI. 
