# Project-A-Kelompok-4-PBA-Genap-2026

## Analisis Sentimen Artikel Berita Online tentang PT Pertamina Menggunakan TF-IDF, Logistic Regression, dan IndoBERT

---

### 📄 Deskripsi Proyek
Repositori ini berisi proyek **Natural Language Processing (NLP)** untuk menganalisis sentimen artikel berita daring yang membahas PT Pertamina. Penelitian ini bertujuan untuk mengetahui persepsi publik terhadap Pertamina melalui perbandingan tiga metode analisis sentimen: **Logistic Regression berbasis TF-IDF, IndoBERT, dan TextBlob**. TF-IDF digunakan sebagai representasi fitur untuk model klasik, sedangkan IndoBERT memanfaatkan pendekatan deep learning berbasis transformer. TextBlob digunakan sebagai baseline analisis polaritas dan subjektivitas.

---

### 🛠 Built With
<p align="left">

  <!-- Core -->
  <img src="https://img.shields.io/badge/Python-3.10-blue?style=for-the-badge&logo=python">
  <img src="https://img.shields.io/badge/Jupyter-Notebook-orange?style=for-the-badge&logo=jupyter">
  <img src="https://img.shields.io/badge/Google-Colab-yellow?style=for-the-badge&logo=googlecolab">

  <br>

  <!-- Data & ML -->
  <img src="https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas">
  <img src="https://img.shields.io/badge/NumPy-Numerical-013243?style=for-the-badge&logo=numpy">
  <img src="https://img.shields.io/badge/Scikit--Learn-ML-F7931E?style=for-the-badge&logo=scikitlearn">
  <img src="https://img.shields.io/badge/NLTK-NLP-9cf?style=for-the-badge">

  <br>

  <!-- NLP Tools -->
  <img src="https://img.shields.io/badge/Sastrawi-Stemming-green?style=for-the-badge">
  <img src="https://img.shields.io/badge/SpaCy-NLP-09A3D5?style=for-the-badge&logo=spacy">
  <img src="https://img.shields.io/badge/Stanza-NLP-red?style=for-the-badge">

  <br>

  <!-- Visualization -->
  <img src="https://img.shields.io/badge/Matplotlib-Visualization-blue?style=for-the-badge">
  <img src="https://img.shields.io/badge/Seaborn-Visualization-76B900?style=for-the-badge">
  <img src="https://img.shields.io/badge/WordCloud-Text%20Viz-lightgrey?style=for-the-badge">
  <img src="https://img.shields.io/badge/TextBlob-Sentiment-yellowgreen?style=for-the-badge">

  <br>

  <!-- Scraping -->
  <img src="https://img.shields.io/badge/Newspaper3k-Scraping-black?style=for-the-badge">
  <img src="https://img.shields.io/badge/BeautifulSoup-Parsing-8A2BE2?style=for-the-badge">
  <img src="https://img.shields.io/badge/Requests-HTTP-blueviolet?style=for-the-badge">
  <img src="https://img.shields.io/badge/Selenium-Automation-43B02A?style=for-the-badge&logo=selenium">

</p>

---

### 📂 Struktur File
```bash
Data/                           # Semua dataset & hasil EDA
├── EDA/                        # Visualisasi EDA
│   ├── 1_distribusi_token.png
│   ├── 2_perbandingan_kata_stopwords.png
│   ├── 3_distribusi_sentimen.png
│   ├── 4_word_cloud.png
│   ├── 5_tp15_kata_persentimen.png
│   ├── 6a_tag_persentimen.png
│   ├── 6b_heatmap_sentimen_pertag.png
│   ├── 7_berdasarkan_penerbit.png
│   ├── 8_boxplot_panjang_berita_per_sentimen.png
│   └── 9_sentiment_pertahun.png
├── Kelompok 4 Link Artikel Pertamina - Scrap .csv
├── hasil_scraping_berita.csv
├── hasil_preprocessing_bert.csv
├── hasil_textblob_sentiment.csv
├── hasil_textblob_logreg_sentiment.csv
├── hasil_all_methods_sentiment.csv
└── hasil_final_perbandingan_sentimen.xlsx

Notebook/                       # Semua notebook
├── 1_Scraping_Artikel.ipynb
├── 2a_Preprocessing.ipynb
├── 2b_Preprocessing_Bert.ipynb
├── 3_EDA.ipynb
├── 4_POS_NER.ipynb
├── 5_Sentiment_TextBlob.ipynb
├── 6_TFIDF_Logreg.ipynb
├── 7_Sentiment_IndoBERT.ipynb
└── 8_Compare_Evaluate_Export.ipynb

README.md                        # File README ini
```    
  
---

### 🔬 Tahapan Penelitian

#### 1. Data Acquisition
- Pengumpulan **manual** artikel berita dari portal nasional dan BUMN terkait Pertamina.  
- Jumlah awal: 2.500 artikel (2016–2026), setelah validasi tersisa 1.829 artikel.  
- Sumber: Detik, Kompas, Tribunnews, Tempo, Bisnis.com, Kontan, Antara News, CNN Indonesia, serta situs resmi Pertamina dan BUMN.  
- Kata kunci: Pertamina, BBM, LPG, SPBU, MyPertamina, subsidi energi, transisi energi, kilang, minyak.  
- Filter tanggal: memastikan artikel relevan sesuai periode publikasi.  

#### 2. Preprocessing
- Case folding (lowercase)  
- Cleaning: hapus URL, simbol, boilerplate, angka, tanda baca  
- Tokenization  
- Stopword removal (Indonesia + Inggris)  
- Stemming (Sastrawi) untuk Logistic Regression/TF-IDF  
- Preprocessing minimal untuk IndoBERT agar konteks kalimat tetap utuh  

#### 3. Exploratory Data Analysis (EDA)
- Analisis distribusi token, frekuensi kata, dan proporsi sentimen  
- Visualisasi: bar chart, pie chart, area chart, word cloud  
- Analisis tren artikel per tahun dan distribusi tag  

#### 4. POS Tagging & Named Entity Recognition (NER)
- POS tagging dengan Stanza Bahasa Indonesia  
- NER menggunakan IndoBERT-NER untuk mendeteksi ORG, LOC, PER, DAT, PRD  
- Digunakan untuk memahami struktur teks dan entitas penting  

#### 5. Feature Extraction dan Modeling
- **TF-IDF + Logistic Regression**: teks stemmed → matriks numerik → prediksi sentimen  
- **TextBlob**: baseline berbasis polarity dan subjectivity  
- **IndoBERT**: model transformer untuk Bahasa Indonesia, digunakan inference  

#### 6. Evaluation Metrics
- Accuracy, Precision, Recall, F1-score (weighted)  
- Confusion matrix untuk analisis kesalahan prediksi  
- Perbandingan distribusi prediksi antara ketiga metode  

---

### 📝 Hasil Utama
- **TextBlob:** cenderung netral, akurasi 36%  
- **Logistic Regression + TF-IDF:** performa terbaik, akurasi 85% pada seluruh data, test set 67,2%  
- **IndoBERT:** akurasi 47%, lebih baik dari TextBlob namun di bawah Logistic Regression  
- Analisis POS & NER: kata benda dan entitas terkait Pertamina (BBM, SPBU, kilang) dominan dalam artikel  

---

### ⚡ Cara Menjalankan
1. Jalankan notebook sesuai urutan di folder `Notebook/`.  
2. Pastikan dataset CSV berada di folder `Dataset/`.  
3. Notebook otomatis menampilkan hasil preprocessing, EDA, POS & NER, WordCloud, distribusi waktu, dan evaluasi model.  

---

### 👥 Anggota Kelompok

| NRP | Nama |
|-----|------|
| 5026231033 | Ayu Alfia Putri |
| 5026231066 | Burju Ferdinand |
| 5026231116 | I Putu Febryan |
| 5026231125 | Ayesha Hana Aziya |
| 5026231135 | Fachreza Aptadhi |

---
