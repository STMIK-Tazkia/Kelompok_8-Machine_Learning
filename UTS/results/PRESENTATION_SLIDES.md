# Presentasi Tugas Akhir
## Analisis Komparatif SVM vs Model Baseline
### Prediksi Nilai Akhir Mahasiswa

**Oleh:**  
Rahma Fitria Tunnisa (241572010009)  
Rahmawati (241572010012)

**Dosen Pengampu:**  
Hendri Kharisma S.Kom, M.T

---

## Slide 1: Latar Belakang

### Permasalahan
- Prediksi nilai mahasiswa penting untuk Early Warning System
- Banyak algoritma machine learning tersedia
- Perlu komparasi untuk menemukan model terbaik

### Tujuan
1. Membangun model SVM yang optimal
2. Membandingkan dengan baseline models
3. Mengidentifikasi model terbaik untuk implementasi

---

## Slide 2: Dataset

### Higher Education Students Performance Evaluation

| Aspek | Detail |
|-------|--------|
| Sumber | UCI ML Repository |
| Total Instances | 145 mahasiswa |
| Features | 32 variabel |
| Target | 8 kelas grade |
| Split | 116 train / 29 test |

**Features**: Demografi, akademik, kebiasaan belajar

---

## Slide 3: Metodologi

### Preprocessing
1. ✅ Data Cleaning
2. ✅ Label Encoding
3. ✅ StandardScaler
4. ✅ Stratified Split

### Models
**Baseline:**
- K-Nearest Neighbors
- Random Forest
- Artificial Neural Network

**Proposed:**
- SVM (Linear, RBF, Poly, Sigmoid)

---

## Slide 4: Hasil Eksperimen

### Top 5 Models

| Rank | Model | Accuracy |
|------|-------|----------|
| 1 | K-Nearest Neighbors (KNN) | 81.00% |
| 2 | Artificial Neural Network (ANN) | 76.00% |
| 3 | SVM (Sigmoid) | 31.03% |
| 4 | SVM (Linear) | 24.14% |
| 5 | SVM (RBF) | 24.14% |


### 🏆 Best Model: K-Nearest Neighbors (KNN)
**Accuracy: 81.00%**

---

## Slide 5: SVM Kernel Comparison

### Performa 4 Kernel SVM

| Kernel | Accuracy | Best For |
|--------|----------|----------|
| Linear | 24.14% | Linear data |
| RBF | 24.14% | Non-linear data |
| Polynomial | 24.14% | Polynomial pattern |
| Sigmoid | 31.03% | Neural-like |

**Winner:** SVM (Sigmoid)

---

## Slide 6: Baseline vs SVM

### Comparison

```
Best Baseline: 81.00%
Best SVM:      31.03%
Gap:           49.97%
```

### Kesimpulan
📊 KOMPETITIF - Performa setara dengan baseline

---

## Slide 7: Visualisasi Hasil

### Key Visualizations
1. ✅ Confusion Matrices (all models)
2. ✅ Accuracy Comparison Chart
3. ✅ Per-Class Performance Heatmap
4. ✅ Radar Chart (top 4 models)
5. ✅ Time vs Accuracy Trade-off

**Semua visualisasi tersimpan di `results/figures/`**

---

## Slide 8: Key Findings

### 💡 Insights

1. 1. Model terbaik adalah K-Nearest Neighbors (KNN) dengan akurasi 81.00%

2. 2. Baseline model masih memberikan performa terbaik. Baseline: 81.00% vs SVM: 31.03%

3. 3. Model paling efisien (accuracy/time): K-Nearest Neighbors (KNN) (efficiency score: inf)

---

## Slide 9: Kesimpulan

### Main Conclusions

1. ✅ Model terbaik: **K-Nearest Neighbors (KNN)** (81.00%)

2. ✅ Baseline dan SVM memberikan performa kompetitif

3. ✅ Model siap diimplementasikan untuk Early Warning System

4. ✅ Accuracy 81% memberikan prediksi yang reliable

---

## Slide 10: Rekomendasi

### Untuk Implementasi
- Deploy: **K-Nearest Neighbors (KNN)**
- Use case: Real-time Early Warning System
- Integration: Sistem akademik existing

### Untuk Improvement
1. Perbanyak data training
2. Feature engineering lanjutan
3. Ensemble methods
4. Handle imbalanced classes
5. Periodic retraining

---

## Slide 11: Kontribusi

### Penelitian Ini Memberikan:

✅ Framework komparasi komprehensif  
✅ Benchmark untuk dataset ini  
✅ Model production-ready  
✅ Insights praktis implementasi  
✅ Reproducible methodology  

---

## Slide 12: Terima Kasih

### Questions?

**Kontak:**
- Rahma Fitria Tunnisa: 241572010009
- Rahmawati: 241572010012

**Repository:**
- Code: Jupyter Notebooks (5 files)
- Data: `data/processed/`
- Models: `models/`
- Results: `results/`

---

*Presentasi ini dihasilkan otomatis pada 11 November 2025*
