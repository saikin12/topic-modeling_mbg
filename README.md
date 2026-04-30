# Analisis MBG (Makan Bergizi Gratis) - Data TikTok Comments

Analisis data komentar TikTok tentang program Makan Bergizi Gratis (MBG) Indonesia menggunakan teknik EDA, Text Processing, Representasi Teks (LDA & BERTopic), Topic Modeling, dan Visualisasi.

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
│   ├── normalisasi_slang.csv       # Dataset hasil normalisasi & n-gram
│   ├── representasi.csv            # Representasi teks (LDA + BERTopic)
│   ├── topic_summary.csv           # Summary semua topik
│   ├── bow_countvectorizer.csv     # Bag-of-Words untuk LDA
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
│   ├── lda_optimal_topics.png      # Pencarian topik optimal LDA
│   ├── lda_topic_distribution.png  # Distribusi topik LDA
│   ├── bertopic_visualize_topics.html # Visualisasi interaktif BERTopic
│   ├── bertopic_barchart.html      # Bar chart BERTopic
│   ├── bertopic_hierarchy.html     # Hierarchical topics BERTopic
│   ├── bertopic_topic_distribution.png # Distribusi topik BERTopic
│   ├── lda_vs_bertopic_comparison.png  # Perbandingan LDA vs BERTopic
│   └── wordcloud_per_topic.png     # WordCloud per topik
├── eda_cleaning.ipynb              # Notebook EDA & Cleaning
├── preprocessing_data.ipynb        # Notebook Preprocessing
├── normalisasi_slang.ipynb         # Notebook Normalisasi Slang & N-Gram
├── representasi_teks.ipynb         # Notebook Representasi Teks (LDA + BERTopic)
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
- [x] Output: `data/normalisasi_slang.csv`

### Fase 4: Representasi Teks (LDA & BERTopic) ✅
- [x] LDA (Latent Dirichlet Allocation) berbasis TF-IDF
- [x] Evaluasi LDA (Coherence Score, Perplexity)
- [x] Pencarian jumlah topik optimal
- [x] BERTopic berbasis Sentence Embedding (Sentence Transformers)
- [x] Perbandingan LDA vs BERTopic (Coherence, jumlah topik, outlier)
- [x] Visualisasi topik (bar chart, pie chart, wordcloud per topik)
- [x] Visualisasi interaktif BERTopic (HTML)
- [x] Output: `data/representasi.csv`, `data/topic_summary.csv`

### Fase 5: Topic Modeling 🔄 (Next Step)
- [ ] LDA/NMF dengan hasil representasi
- [ ] Evaluasi & tuning model
- [ ] Interpretasi topik

### Fase 6: Visualisasi
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
- bertopic>=0.15.0  # Topic modeling berbasis embedding
- sentence-transformers>=2.2.0  # Sentence embedding
- umap-learn>=0.5.0  # Dimensionality reduction untuk BERTopic
- hdbscan>=0.8.33  # Clustering untuk BERTopic

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
    jupyter notebook representasi_teks.ipynb
    # Jalankan semua cell
    # (future) jupyter notebook topic_modeling.ipynb
    ```

## 📈 Hasil Yang Diharapkan

- Identifikasi topik-topik utama yang dibahas masyarakat
- Pemahaman sentimen publik terhadap program MBG
- Visualisasi word cloud dan distribusi topik
- Perbandingan pendekatan LDA vs BERTopic
- Insights untuk evaluasi program MBG

## 🔬 Metode yang Digunakan

1. **Preprocessing Teks**:
   - Stopword Removal (custom + default Bahasa Indonesia)
   - Stemming (Sastrawi Stemmer)
   - Normalisasi Slang (kamus 500+ kata gaul/singkatan)
   - Ekstraksi Bigram & Trigram (Gensim Phrases)

2. **Representasi Teks**:
   - LDA (Latent Dirichlet Allocation) → TF-IDF based
   - BERTopic → Sentence Embedding (paraphrase-multilingual-MiniLM)

3. **Evaluasi**:
   - Coherence Score (Cv)
   - Perplexity
   - Visualisasi interaktif (BERTopic HTML, pyLDAvis)

## 📊 Output File

| File | Deskripsi |
|------|-----------|
| `data/data_cleaned.csv` | Dataset setelah EDA & cleaning |
| `data/data_preprocessed.csv` | Dataset setelah preprocessing |
| `data/normalisasi_slang.csv` | Dataset setelah normalisasi slang & n-gram |
| `data/representasi.csv` | Representasi teks per dokumen (LDA + BERTopic) |
| `data/topic_summary.csv` | Summary semua topik dari LDA dan BERTopic |
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
- BERTopic menggunakan model multilingual untuk embedding
