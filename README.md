Project: Case-Based Legal Reasoning

Deskripsi

Repository ini mengimplementasikan case-based reasoning untuk putusan Mahkamah Agung Republik Indonesia:

Tahap 1: Unduh dan bersihkan HTML → teks mentah & bersih.

Tahap 2: Ekstraksi metadata & feature engineering → cases.csv, vektor TF-IDF.

Tahap 3: Case Retrieval dengan TF‑IDF + Faiss → fungsi retrieve_faiss().

Tahap 4: Solution Reuse (voting & weighted) → prediksi solusi.

Tahap 5: Model Evaluation → metrics & visualisasi.

Struktur Direktori

├── data
│   ├── raw
│   │   ├── html/             # HTML downloaded
│   │   ├── text/             # teks mentah & bersih
│   ├── processed
│   │   ├── cases.csv         # metadata & ekstraksi isi
│   │   ├── cases_cleaned.csv # hasil cleaning final
│   ├── vectors
│   │   ├── tfidf_fulltext_vec.pkl
│   │   ├── tfidf_fulltext_matrix.csv
│   ├── eval
│   │   ├── queries.json      # query uji & ground_truth
│   │   ├── retrieval_metrics.csv
│   │   ├── prediction_metrics.csv
│   └── results
│       └── predictions.csv   # hasil prediksi solusi
├── logs
│   └── cleaning.log
├── notebooks
│   ├── 01_case_base.ipynb
│   ├── 02_case_representation.ipynb
│   ├── 03_case_retrieval.ipynb
│   ├── 04_solution_reuse.ipynb
│   ├── 05_evaluation.ipynb
│   └── 06_model_evaluation.ipynb
├── requirements.txt
└── README.md

Instalasi

Clone repository

git clone <URL_REPO>
cd <NAMA_FOLDER>

Buat virtual environment (opsional namun direkomendasikan)

python3 -m venv venv
source venv/bin/activate   # Linux/Mac
venv\Scripts\activate    # Windows

Install dependencies

pip install -r requirements.txt

Eksekusi Notebook

Jalankan urut dari 01_case_base.ipynb hingga 06_model_evaluation.ipynb:

01_case_base.ipynb: Download & ekstrak HTML → simpan di data/raw/html.

02_case_representation.ipynb: Ekstraksi metadata, buat cases.csv & cases_cleaned.csv.

03_case_retrieval.ipynb: Bangun TF‑IDF + Faiss, definisi retrieve_faiss().

04_solution_reuse.ipynb: Prediksi solusi menggunakan voting/weighted; simpan predictions.csv.

05_evaluation.ipynb: Simpan results.json & retrieval_metrics.csv.

06_model_evaluation.ipynb: Hitung metrik retrieval & prediksi, visualisasi, simpan prediction_metrics.csv.

Catatan: Pastikan data/ sudah ada dan subfoldernya sesuai struktur. Gunakan kernel Python 3.8+.

Output

data/processed/cases.csv: Metadata kasus.

data/processed/cases_cleaned.csv: Teks bersih.

data/vectors/: Model & matriks TF‑IDF.

data/results/predictions.csv: Hasil prediksi solusi.

data/eval/retrieval_metrics.csv: Precision@1 & @5.

data/eval/prediction_metrics.csv: Accuracy, Precision, Recall, F1.

Logging

File logs/cleaning.log mencatat panjang raw vs clean setiap file HTML.