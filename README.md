# 🧬 Biomedical Document Summarization using BART & BERTSUMEXT

This project focuses on extractive and abstractive summarization of biomedical documents using transformer models like **BART** and **BERTSUMEXT**, applied on datasets such as **TREC CDS** and **OHSUMED**.

---

## 📌 Highlights

- ✅ Loads TREC-CDS 2014 via `ir_datasets`  
- ✅ Extracts & parses OHSUMED dataset from `tar.gz` format  
- ✅ Generates summaries using `facebook/bart-large-cnn`  
- ✅ Compares summaries using ROUGE metrics  
- ✅ Also includes `bert-extractive-summarizer` for extractive summarization  
- ✅ Fully compatible with Google Colab  

---

## 📦 Libraries Used

- 🤖 `transformers` (Hugging Face)  
- 🧬 `ir_datasets` (for TREC CDS)  
- 📦 `sentencepiece`, `torch`, `nltk`  
- 📈 `evaluate` (ROUGE metric)  
- 📂 `tarfile`, `os`, `pandas`  
- 🧠 `bert-extractive-summarizer` (BERT-based sentence extractor)  

---

## 🗃️ Dataset Sources

### 📚 TREC-CDS 2014

- Loaded via: `ir_datasets.load("pmc/v1/trec-cds-2014")`  
- Contains PMC biomedical documents with titles and abstracts

### 🧾 OHSUMED (first 20,000 docs)

- Extracted from `.tar.gz` and parsed using Python  
- Assumes title is first line, abstract is remaining text  
- Format:
  ```
  Title
  Abstract line 1
  Abstract line 2
  ...
  ```

---

## 🚀 Model Summarization Flow

### 🔹 Abstractive Summary (BART)

- Loads `facebook/bart-large-cnn`  
- Summarizes abstract into 50–150 word output  
- Evaluated using ROUGE metrics  

### 🔹 Extractive Summary (BERTSUMEXT)

- Uses `bert-extractive-summarizer`  
- Picks top N sentences from abstract  
- Also evaluated with ROUGE  

---

## 📈 ROUGE Evaluation

- ROUGE scores are computed for both models  
- Compares generated summary with full abstract as reference  
- Sample output:
  ```
  ROUGE-1: 0.6224
  ROUGE-2: 0.4893
  ROUGE-L: 0.6011
  ```

---

## 📂 Project Structure (Colab-style)

```
📄 biomedical_summarizer.ipynb       # Main notebook
📦 ohsumed-first-20000-docs.tar.gz  # Local dataset (uploaded)
📁 /content/OHSUMED/                 # Extracted docs
```

---

## 🧪 How to Run in Google Colab

1. Upload `ohsumed-first-20000-docs.tar.gz`  
2. Run all cells step-by-step:
   - Install libraries
   - Extract data
   - Load datasets
   - Generate summaries
   - Evaluate with ROUGE

---

## 🔮 Possible Improvements

- ⚙️ Add GUI using Gradio or Streamlit  
- 🧠 Train or fine-tune on domain-specific biomedical summarization tasks  
- 🧪 Add support for PubMedQA-style queries  
- 📦 Package into a standalone Python app

---

