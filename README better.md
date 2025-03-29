
# Skill-Bridge AI Tool

## Overview

**Skill-Bridge** is an AI-powered system designed to help job seekers assess their compatibility with job listings and recommend personalized online courses to bridge any skill gaps. It uses a combination of Named Entity Recognition (NER) and Retrieval-Augmented Generation (RAG) to extract skills from job descriptions and user profiles and match them with relevant courses.

This tool was developed as part of a project at the Technion – Israel Institute of Technology.

---

## Highlight: AI Architectures

### 1. NER Model (`NER_model.ipynb`)
- This notebook performs **three key tasks**:
  1. **Training** a custom Named Entity Recognition model using SpaCy.
  2. **Loading** pre-trained models and embeddings (Word2Vec, GloVe).
  3. **Evaluating** models using multiple metrics such as IoU, precision, and semantic similarity.
- The model identifies and extracts skill entities from job descriptions, critical for calculating job-user fit.

### 2. RAG Pipeline (`RAG_architecture.ipynb`)
- This notebook contains both the **construction** and **usage** of the Retrieval-Augmented Generation system.
- It handles:
  - **Dataset creation and embedding** of online courses using sentence-transformers.
  - **Indexing into Pinecone** to build the vector search database.
  - **Running queries** using job descriptions and user skill profiles.
  - **Evaluating** the quality of recommendations using compatibility improvements.
- ⚠️ **Note:** Users must insert their own **API keys** for Pinecone and Cohere for this to function properly.

---

## Scraping Job Listings (`scraping_jobs_info.ipynb`)

- This script scrapes job listings from **Glassdoor** using Selenium and BeautifulSoup.
- It queries **3,000 random companies** and collects up to **30 listings per company**, totaling over 17,000 job postings.
- The scraped data includes **job titles, descriptions, and company names**, forming the foundation of the NER training set and the skill recommendation engine.

---

## Project Structure

```
AI_Architectures/
    NER_model.ipynb           # Train, load, and evaluate NER skill extraction
    RAG_architecture.ipynb    # Build & evaluate course recommender using Pinecone + LLM

Data_Preprocessing/
    Users Preprocessing.ipynb # Cleans and formats user profile data

Scraping_Data/
    scraping_jobs_info.ipynb  # Scrapes job data from Glassdoor

Data Analytics/
    Data Analytics.ipynb      # Evaluates overall pipeline performance
```

---

## Installation

1. Clone the repository:
```bash
git clone https://github.com/RanSela-033/Skill-Bridge_AI_tool.git
cd Skill-Bridge_AI_tool
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

---

## Usage

Run the Jupyter notebooks in the following order:

1. `Scraping_Data/scraping_jobs_info.ipynb` – Gather job listings for training and inference.
2. `Data_Preprocessing/Users Preprocessing.ipynb` – Format user profile data for skill extraction.
3. `AI_Architectures/NER_model.ipynb` – Train/load skill extraction models and evaluate them.
4. `AI_Architectures/RAG_architecture.ipynb` – Generate Pinecone dataset, run recommendations, and evaluate.
5. `Data Analytics/Data Analytics.ipynb` – Visualize results and performance.

---

## Requirements

See `requirements.txt` for full dependency list.

---

## License

[Specify your license here]

---

## Authors

Bar Muller, Bar Redel, Ran Sela  
Technion – Israel Institute of Technology
