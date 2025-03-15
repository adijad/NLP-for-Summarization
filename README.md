# Clinical Text Summarization: NLP-Based Summarization of Doctor Notes  

## Overview  
This project focuses on developing an **NLP-based summarization system** to automatically generate concise summaries from **extensive doctor notes**. The goal is to **help healthcare professionals quickly access key patient details**, enabling **faster decision-making** in clinical settings.  

Medical documentation is **often lengthy and complex**, making it difficult for doctors to extract relevant information quickly. Our **summarization model** simplifies this process by condensing doctor notes into **short, structured summaries** while preserving essential details.  

---

## System Architecture  
![System Architecture](https://github.com/adijad/NLP-for-Summarization/blob/main/System_Architecture.png)  

The system follows a **hybrid summarization approach**, combining **Extractive Summarization** and **Abstractive Summarization** to generate high-quality, readable summaries.  

1. **Extractive Summarization** identifies **key sentences** using **MMR (Maximal Marginal Relevance)**, ensuring relevance and diversity.  
2. **Abstractive Summarization** rephrases content using **PEGASUS**, producing natural and concise summaries.  
3. **Synthetic Summary Generation** allows the **creation of labeled datasets** for training the summarization model.  

The **final summary** serves as a **concise representation of the patient data**, enhancing usability in clinical workflows.  

---

## Motivation  
Healthcare providers deal with **large volumes of patient data** daily. Reviewing extensive doctor notes is **time-consuming**, increasing the risk of missing critical details.  

- **Improves Efficiency** → Summarized data helps doctors make faster clinical decisions.  
- **Enhances Communication** → Ensures medical teams **share concise and relevant patient details**.  
- **Supports Patient Safety** → Highlights important **conditions, treatments, and diagnoses**.  

---

## Dataset  
Two medical datasets were used for model training:  

1. **Open Patients Dataset** → Contains **180,142 patient descriptions** from **clinical trials, PubMed case reports, and MedQA-USMLE**.  
2. **Medical Transcriptions Dataset** → Real-world **doctor notes and case histories**, categorized by **medical specialty**.  

These datasets provide diverse, **real-world medical records** for training and evaluating the summarization model.  

---

## Evaluation Metrics  
To ensure **high-quality summaries**, the system is evaluated using **standard NLP metrics**:  

- **ROUGE Score** → Measures content overlap between generated and reference summaries.
- **BLEU Score** → Evaluates n-gram precision to check fluency and readability.  
- **MMR Score** → Ensures a balance between relevance and diversity in extractive summarization.  
- **Error Analysis** → Identifies missing details, irrelevant content, and language inconsistencies.  

These metrics **validate the effectiveness** of both **extractive and abstractive summarization** methods.  

---

## Methodology  

### **1. Extractive Summarization (MMR-Based Sentence Selection)**  
Extractive summarization **identifies and selects the most relevant sentences** from doctor notes.  

**Key Techniques Used**:  
- **Tokenization & Stopword Removal** → Prepares text for analysis.  
- **TF-IDF & Named Entity Recognition (NER)** → Extracts key medical terms.  
- **Sentence Embedding & Cosine Similarity** → Determines sentence importance.  
- **MMR Scoring** → Balances **relevance** and **diversity** of selected sentences.  

### **2. Abstractive Summarization (PEGASUS Model)**  
Abstractive summarization **rephrases extracted content** into **natural and concise summaries**.  

**Models Used**:  
- **PEGASUS-XSum** → Generates **concise, sentence-level summaries**.  
- **T5 (Text-to-Text Transfer Transformer)** → Produces **detailed, paragraph-length summaries**.  

### **3. Hybrid Summarization (Combining Extractive & Abstractive Approaches)**  
Hybrid summarization ensures:  
- **Factual Accuracy** (from extractive summarization).
- **Fluent & Readable Summaries** (from abstractive summarization).  

---

## Results & Comparative Analysis  

### Extractive vs. Abstractive vs. Hybrid Summarization Performance  
| **Approach**   | **BLEU Score** | **ROUGE-1** | **ROUGE-2** | **ROUGE-L** |
|---------------|--------------|-------------|-------------|-------------|
| **PEGASUS (Abstractive)** | 0.0011 | 0.1189 | 0.0530 | 0.0902 |
| **T5 (Abstractive)** | 0.0493 | 0.1468 | 0.0465 | 0.1131 |
| **Hybrid (Extractive + Abstractive)** | **0.0823** | **0.3937** | **0.2814** | **0.3234** |

**Hybrid Summarization outperforms purely abstractive models**, generating summaries that are **concise, fluent, and factually accurate**.  

### Multi-Document Summarization Performance
- **Relevance Scores** → Summaries maintain **high relevance** across medical conditions.  
- **Diversity Scores** → Ensures information is **not repetitive**, improving coverage.  
- **MMR Scores** → Balances **relevance & diversity**, optimizing extracted content.  

---

## Synthetic Summary Generation  
To train the **summarization model**, **synthetic summaries** were generated using:  

- **Hybrid Summarization Pipeline** → Produces **high-quality labeled training data**.  
- **PEGASUS-XSum** → Generates compact, high-accuracy summaries.  
- **Fine-Tuned PEGASUS-Large Model** → Used for model training & real-world testing.  

This **preprocessing step** ensures that the summarization model learns from **realistic, high-quality summaries**, improving performance.  

---
