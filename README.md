<!-- badges: start -->
[![Python](https://img.shields.io/badge/python-3.8%2B-blue)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/license-MIT-green)](/LICENSE)
<!-- badges: end -->

# 🏛️ Case-Based Legal Reasoning

Implementasi *case-based reasoning* untuk putusan Mahkamah Agung Republik Indonesia.
Pengadilan Negeri Surabaya Putusan 2022 Tentang Pencurian

---

## 📖 Deskripsi

1. **Tahap 1** – Unduh & bersihkan HTML → teks mentah & bersih  
2. **Tahap 2** – Ekstraksi metadata & feature engineering → `cases.csv`, vektor TF-IDF  
3. **Tahap 3** – Case Retrieval dengan TF-IDF + Faiss → fungsi `retrieve_faiss()`  
4. **Tahap 4** – Solution Reuse (voting & weighted) → prediksi solusi  
5. **Tahap 5** – Model Evaluation → metrics & visualisasi  

---

## 🗂️ Struktur Direktori

```text
.
├── data
│   ├── raw
│   │   ├── html/             # HTML hasil download
│   │   └── text/             # teks mentah & bersih
│   ├── processed
│   │   ├── cases.csv         # metadata & ekstraksi isi
│   │   └── cases_cleaned.csv # teks bersih final
│   ├── vectors
│   │   ├── tfidf_fulltext_vec.pkl
│   │   └── tfidf_fulltext_matrix.csv
│   ├── eval
│   │   ├── queries.json      # query uji & ground-truth
│   │   ├── retrieval_metrics.csv
│   │   └── prediction_metrics.csv
│   └── results
│       └── predictions.csv   # hasil prediksi solusi
├── logs
│   └── cleaning.log          # log pembersihan teks
├── notebooks
│   ├── 01_case_base.ipynb
│   ├── 02_case_representation.ipynb
│   ├── 03_case_retrieval.ipynb
│   ├── 04_solution_reuse.ipynb
│   ├── 05_evaluation.ipynb
│   └── 06_model_evaluation.ipynb
├── requirements.txt
└── README.md
