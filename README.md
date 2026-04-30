# Analisis MBG (Makan Bergizi Gratis) - Data TikTok Comments

Analisis data komentar TikTok tentang program Makan Bergizi Gratis (MBG) Indonesia menggunakan teknik EDA, Text Processing, Topic Modeling, dan Visualisasi.

## 📋 Deskripsi Proyek

Proyek ini bertujuan untuk menganalisis sentimen dan topik-topik utama yang dibahas masyarakat Indonesia dalam kolom komentar TikTok tentang program Makan Bergizi Gratis (MBG).

## 📊 Dataset

- **File**: `data/hasil_processing.csv`
- **Jumlah**: ~17,658 komentar TikTok
- **Sumber**: Video TikTok @badangizinasional.ri tentang MBG
- **Kolom Utama**:
  - `text`: Teks komentar asli
  - `diggCount`: Jumlah likes
  - `replyCommentTotal`: Jumlah reply
  - `createTimeISO`: Timestamp komentar
  - `uniqueId`: Username commenter
  - `tokens`: Token hasil processing

## 📁 Struktur Direktori

```
Analisis MBG/
├── data/
│   ├── hasil_processing.csv        # Data mentah hasil scraping
│   ├── data_cleaned.csv            # Data setelah EDA & cleaning
│   ├── data_preprocessed.csv       # Data setelah preprocessing
│   ├── bow_countvectorizer.csv      # Bag-of-Words untuk LDA
│   └── tfidf_vectorizer.csv        # TF-IDF untuk NMF
├── output/
│   ├── missing_values.png          # Missing values analysis
│   ├── distribution_diggcount.png  # Distribusi engagement
│   ├── distribution_text_length.png # Distribusi panjang teks
│   ├── comments_per_date.png       # Komentar per tanggal
│   ├── top_words.png               # Top kata EDA
│   ├── eda_summary.png             # Summary EDA
│   ├── step1_before_stopword.png   # Sebelum stopword removal
│   ├── step2_after_stopword.png    # Setelah stopword removal
│   ├── step3_after_stemming.png    # Setelah stemming
│   ├── preprocessing_comparison.png # Perbandingan preprocessing
│   ├── wordcloud_final.png         # WordCloud hasil preprocessing
│   ├── text_length_distribution.png # Distribusi panjang teks preprocessing
│   ├── top_bigrams.png             # Top 20 bigram terbentuk
│   ├── top_trigrams.png            # Top 20 trigram terbentuk
│   ├── token_count_comparison.png  # Perbandingan jumlah token per tahap
│   ├── wordcloud_normalisasi.png   # WordCloud hasil normalisasi slang
│   └── normalisasi_slang.csv       # Dataset hasil normalisasi & n-gram
├── eda_cleaning.ipynb              # Notebook EDA & Cleaning
├── preprocessing_data.ipynb        # Notebook Preprocessing
├── normalisasi_slang.ipynb         # Notebook Normalisasi Slang & N-Gram
├── topic_modeling.ipynb            # Notebook Topic Modeling (future)
├── requirements.txt
├── README.md
└── todolis.md
```

## 📝 Tahapan Analisis

### Fase 1: EDA & Data Cleaning ✅
- [x] Eksplorasi dataset
- [x] Analisis missing values & duplikat
- [x] Analisis engagement
- [x] Analisis temporal
- [x] Data cleaning & normalisasi
- [x] Output: `data/data_cleaned.csv`

### Fase 2: Preprocessing (Stopword & Stemming) ✅
- [x] Setup stopwords bahasa Indonesia + custom untuk konteks MBG
- [x] Setup stemmer Sastrawi (Bahasa Indonesia)
- [x] Stopword removal
- [x] Stemming
- [x] Visualisasi setiap langkah
- [x] WordCloud & distribusi panjang teks
- [x] Output: `data/data_preprocessed.csv`, `data/bow_*.csv`, `data/tfidf_*.csv`

### Fase 3: Normalisasi Slang & Ekstraksi N-Gram ✅
- [x] Kamus normalisasi slang bahasa Indonesia (500+ entri)
- [x] Normalisasi token slang ke bentuk baku
- [x] Ekstraksi bigram menggunakan Gensim Phrases
- [x] Ekstraksi trigram berdasarkan output bigram
- [x] Visualisasi top bigram, trigram, dan wordcloud
- [x] Output: `output/normalisasi_slang.csv`

### Fase 4: Topic Modeling 🔄 (Next Step)
- [ ] LDA (Latent Dirichlet Allocation)
- [ ] NMF (Non-negative Matrix Factorization)
- [ ] Evaluasi & tuning model
- [ ] Interpretasi topik

### Fase 5: Visualisasi
- [ ] WordCloud per topik
- [ ] Distribusi topik
- [ ] Interactive visualization (pyLDAvis)

## 🔧 Dependencies

```bash
pip install -r requirements.txt
```

### Requirements:
- pandas>=1.5.0
- numpy>=1.23.0
- matplotlib>=3.6.0
- seaborn>=0.12.0
- nltk>=3.8.0
- Sastrawi>=1.0.0  # Stemming Bahasa Indonesia
- scikit-learn>=1.2.0
- gensim>=4.3.0
- pyLDAvis>=3.4.0
- wordcloud>=1.9.0

## 🚀 Cara Menjalankan

1. **Clone/Download repository ini**

2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Jalankan Notebook secara berurutan**:
    ```bash
    jupyter notebook eda_cleaning.ipynb
    # Jalankan semua cell
    jupyter notebook preprocessing_data.ipynb
    # Jalankan semua cell
    jupyter notebook normalisasi_slang.ipynb
    # Jalankan semua cell
    # (future) jupyter notebook topic_modeling.ipynb
    ```

## 📈 Hasil Yang Diharapkan

- Identifikasi topik-topik utama yang dibahas masyarakat
- Pemahaman sentimen publik terhadap program MBG
- Visualisasi word cloud dan distribusi topik
- Insights untuk evaluasi program MBG

## 🔬 Metode yang Digunakan

1. **Preprocessing Teks**:
   - Stopword Removal (custom + default Bahasa Indonesia)
   - Stemming (Sastrawi Stemmer)
   - Normalisasi Slang (kamus 500+ kata gaul/singkatan)
   - Ekstraksi Bigram & Trigram (Gensim Phrases)

2. **Topic Modeling**:
   - LDA (Latent Dirichlet Allocation)
   - NMF (Non-negative Matrix Factorization)

3. **Evaluasi**:
   - Coherence Score
   - Perplexity
   - Visualisasi interaktif (pyLDAvis)

## 📊 Output File

| File | Deskripsi |
|------|-----------|
| `data/data_cleaned.csv` | Dataset setelah EDA & cleaning |
| `data/data_preprocessed.csv` | Dataset setelah preprocessing |
| `output/normalisasi_slang.csv` | Dataset setelah normalisasi slang & n-gram |
| `data/bow_countvectorizer.csv` | Matriks Bag-of-Words |
| `data/tfidf_vectorizer.csv` | Matriks TF-IDF |

## 👥 Kontributor

Analisis dilakukan untuk keperluan riset dan evaluasi program Makan Bergizi Gratis.

## 📅 Tanggal

April 2026

## ⚠️ Catatan

- Dataset berisi komentar publik dari TikTok
- Analisis bersifat deskriptif dan eksploratif
- Hasil dapat digunakan sebagai masukan evaluasi program
- Stemmer Sastrawi khusus untuk Bahasa Indonesia