# To-Do List: Analisis MBG (Makan Bergizi Gratis)

## Fase 1: EDA & Data Cleaning ✅
- [x] Load dan eksplorasi dataset
- [x] Analisis missing values
- [x] Analisis duplicate data
- [x] Analisis distribusi engagement (diggCount, replies)
- [x] Analisis panjang teks dan token
- [x] Analisis temporal (waktu komentar)
- [x] Analisis kata yang sering muncul
- [x] Cleaning data (hapus kosong, duplikat, normalisasi)
- [x] Simpan data cleaned ke `data/data_cleaned.csv`

## Fase 2: Preprocessing (Stopword & Stemming) ✅
- [x] Setup stopwords bahasa Indonesia + custom MBG
- [x] Setup stemmer Sastrawi untuk Bahasa Indonesia
- [x] Stopword removal
- [x] Stemming
- [x] Visualisasi setiap langkah preprocessing
- [x] WordCloud hasil preprocessing
- [x] Simpan hasil preprocessing ke `data/data_preprocessed.csv`
- [x] Buat Bag-of-Words (CountVectorizer)
- [x] Buat TF-IDF Vectorizer

## Fase 3: Normalisasi Slang & Ekstraksi N-Gram ✅
- [x] Load data hasil preprocessing (hasil_processing.csv)
- [x] Buat kamus normalisasi slang bahasa Indonesia
- [x] Normalisasi token slang ke bentuk baku
- [x] Ekstraksi bigram menggunakan Gensim Phrases
- [x] Ekstraksi trigram berdasarkan output bigram
- [x] Visualisasi top bigram dan trigram
- [x] WordCloud hasil normalisasi
- [x] Simpan hasil ke `data/normalisasi_slang.csv`

## Fase 4: Representasi Teks (LDA & BERTopic) ✅
- [x] LDA (Latent Dirichlet Allocation) berbasis TF-IDF
- [x] Evaluasi LDA (Coherence Score, Perplexity)
- [x] Pencarian jumlah topik optimal
- [x] BERTopic berbasis Sentence Embedding
- [x] Perbandingan LDA vs BERTopic
- [x] Visualisasi topik (bar chart, pie chart, wordcloud)
- [x] Simpan hasil ke `data/representasi.csv`

## Fase 5: Topic Modeling (Mendatang)
- [ ] Implementasi LDA/NMF dengan hasil representasi
- [ ] Tunning hyperparameter (jumlah topik optimal)
- [ ] Evaluasi model (Coherence Score, perplexity)
- [ ] Interpretasi setiap topik

## Fase 6: Visualisasi Hasil Modeling
- [ ] WordCloud per topik
- [ ] Distribusi topik dalam corpus
- [ ] Topic evolution over time
- [ ] Interactive visualization (pyLDAvis)
- [ ] Network visualization kata-kata terkait
- [ ] Heatmap korelasi antar topik

## Fase 7: Analisis Tambahan (Opsional)
- [ ] Sentiment Analysis (positif/negatif/netral)
- [ ] Entity Recognition (orang, organisasi, dll)
- [ ] Hashtag analysis
- [ ] User engagement analysis

## Fase 8: Dokumentasi & Pelaporan
- [ ] Update README dengan hasil analisis
- [ ] Buat presentation slides
- [ ] Ringkasan temuan utama
- [ ] Rekomendasi/action items

---

## File yang Sudah Dibuat

| File | Status | Deskripsi |
|------|--------|-----------|
| `eda_cleaning.ipynb` | ✅ Selesai | EDA dan data cleaning |
| `preprocessing_data.ipynb` | ✅ Selesai | Stopword removal & stemming |
| `normalisasi_slang.ipynb` | ✅ Selesai | Normalisasi slang, bigram & trigram |
| `representasi_teks.ipynb` | ✅ Selesai | Representasi teks (LDA + BERTopic) |
| `todolis.md` | ✅ Updated | Task list tracking |
| `README.md` | 🔄 Updated | Dokumentasi proyek |
| `requirements.txt` | 🔄 Updated | Dependencies |

## File Data yang Dihasilkan

| File | Deskripsi |
|------|-----------|
| `data/data_cleaned.csv` | Data setelah cleaning |
| `data/data_preprocessed.csv` | Data setelah preprocessing |
| `data/normalisasi_slang.csv` | Data setelah normalisasi slang & n-gram |
| `data/representasi.csv` | Representasi teks (LDA + BERTopic) per dokumen |
| `data/topic_summary.csv` | Summary semua topik dari LDA dan BERTopic |
| `data/bow_countvectorizer.csv` | Matriks BoW untuk LDA |
| `data/tfidf_vectorizer.csv` | Matriks TF-IDF untuk NMF |

## Visualisasi yang Dihasilkan

| File | Deskripsi |
|------|-----------|
| `output/missing_values.png` | Missing values analysis |
| `output/distribution_diggcount.png` | Distribusi engagement |
| `output/distribution_text_length.png` | Distribusi panjang teks |
| `output/comments_per_date.png` | Komentar per tanggal |
| `output/top_words.png` | Top kata EDA |
| `output/eda_summary.png` | Summary EDA |
| `output/step1_before_stopword.png` | Sebelum stopword |
| `output/step2_after_stopword.png` | Setelah stopword |
| `output/step3_after_stemming.png` | Setelah stemming |
| `output/preprocessing_comparison.png` | Perbandingan preprocessing |
| `output/wordcloud_final.png` | WordCloud hasil preprocessing |
| `output/text_length_distribution.png` | Distribusi panjang teks preprocessing |
| `output/top_bigrams.png` | Top 20 bigram terbentuk |
| `output/top_trigrams.png` | Top 20 trigram terbentuk |
| `output/token_count_comparison.png` | Perbandingan jumlah token per tahap |
| `output/wordcloud_normalisasi.png` | WordCloud hasil normalisasi slang |
| `output/lda_optimal_topics.png` | Pencarian topik optimal LDA |
| `output/lda_topic_distribution.png` | Distribusi topik LDA |
| `output/bertopic_visualize_topics.html` | Visualisasi interaktif BERTopic |
| `output/bertopic_barchart.html` | Bar chart BERTopic |
| `output/bertopic_hierarchy.html` | Hierarchical topics BERTopic |
| `output/bertopic_topic_distribution.png` | Distribusi topik BERTopic |
| `output/lda_vs_bertopic_comparison.png` | Perbandingan LDA vs BERTopic |
| `output/wordcloud_per_topic.png` | WordCloud per topik |

## Progress
- Dataset: hasil_processing.csv (17,658 komentar)
- Tanggal: April 2026
- Fase saat ini: Representasi Teks (LDA & BERTopic) ✅ Selesai
- Selanjutnya: Topic Modeling dengan representasi teks
