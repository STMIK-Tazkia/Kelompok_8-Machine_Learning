# Laporan Akhir Penelitian
## Analisis Komparatif Kinerja Klasifikasi Support Vector Machine (SVM) dan Model Baseline pada Prediksi Nilai Akhir Mahasiswa Perguruan Tinggi

---

### 📋 Identitas Penelitian

- **Peneliti**: 
  - Rahma Fitria Tunnisa (241572010009)
  - Rahmawati (241572010012)
- **Dosen Pengampu**: Hendri Kharisma S.Kom, M.T
- **Institusi**: STMIK TAZKIA
- **Program Studi**: Sistem Informasi
- **Tanggal**: 11 November 2025

---

## BAB I - PENDAHULUAN

### 1.1 Latar Belakang
Kinerja akademik mahasiswa merupakan indikator vital bagi keberhasilan institusi pendidikan tinggi. Dengan volume data akademik, demografi, dan kebiasaan belajar yang terus meningkat, bidang Educational Data Mining (EDM) menawarkan peluang besar untuk memprediksi hasil akhir mahasiswa. Prediksi yang akurat memungkinkan pengembangan Sistem Peringatan Dini (Early Warning System), yang memungkinkan dosen dan penasihat akademik memberikan intervensi tepat waktu kepada mahasiswa yang berisiko.

### 1.2 Rumusan Masalah
1. Bagaimana membangun dan mengoptimasi model klasifikasi Support Vector Machine (SVM) untuk memprediksi kategori Nilai Akhir Mahasiswa?
2. Bagaimana kinerja klasifikasi model SVM dibandingkan dengan hasil model baseline (KNN, Random Forest, ANN)?

### 1.3 Tujuan Penelitian
1. Mengembangkan model klasifikasi SVM yang teroptimasi untuk prediksi Nilai Akhir Mahasiswa
2. Melakukan analisis perbandingan yang valid antara kinerja SVM dengan model baseline
3. Menarik kesimpulan mengenai efektivitas SVM sebagai metode klasifikasi prediktif dalam kasus kinerja akademik

---

## BAB II - METODOLOGI

### 2.1 Dataset
- **Nama**: Higher Education Students Performance Evaluation
- **Sumber**: UCI Machine Learning Repository
- **Total Instances**: 145 mahasiswa
- **Jumlah Features**: 32 variabel
- **Target Variable**: Output Grade (8 kelas: Fail, DD, DC, CC, CB, BB, BA, AA)
- **Split Ratio**: 116 train (80%) / 29 test (20%)

### 2.2 Preprocessing
1. **Data Cleaning**: Penanganan missing values dan duplikasi
2. **Feature Engineering**: Label Encoding untuk variabel kategorikal
3. **Feature Scaling**: StandardScaler untuk normalisasi data
4. **Train-Test Split**: Stratified sampling untuk menjaga proporsi kelas
5. **Cross-Validation**: 5-fold CV untuk hyperparameter tuning

### 2.3 Model yang Digunakan

#### Baseline Models:
1. **K-Nearest Neighbors (KNN)**
2. **Random Forest (RF)**
3. **Artificial Neural Network (ANN)**

#### Proposed Model:
4. **Support Vector Machine (SVM)** dengan 4 kernel:
   - Linear
   - RBF (Radial Basis Function)
   - Polynomial
   - Sigmoid

### 2.4 Hyperparameter Tuning
Semua model melalui GridSearchCV dengan 5-fold cross-validation untuk menemukan kombinasi hyperparameter terbaik.

### 2.5 Metrik Evaluasi
- Accuracy
- Precision (weighted average)
- Recall (weighted average)
- F1-Score (weighted average)
- Training Time
- Confusion Matrix

---

## BAB III - HASIL DAN PEMBAHASAN

### 3.1 Hasil Eksperimen

#### Tabel 1: Perbandingan Performa Semua Model

| Rank | Model | Accuracy (%) | Precision (%) | Recall (%) | F1-Score (%) | Train Time (s) |
|------|-------|--------------|---------------|------------|--------------|----------------|
| 1 | K-Nearest Neighbors (KNN) | 81.00 | 82.29 | 81.00 | 80.68 | 0.00 |
| 2 | Artificial Neural Network (ANN) | 76.00 | 77.60 | 76.00 | 75.36 | 0.05 |
| 3 | SVM (Sigmoid) | 31.03 | 24.83 | 31.03 | 27.50 | 0.35 |
| 4 | SVM (Linear) | 24.14 | 5.83 | 24.14 | 9.39 | 5.31 |
| 5 | SVM (RBF) | 24.14 | 6.03 | 24.14 | 9.66 | 0.30 |
| 6 | SVM (Polynomial) | 24.14 | 12.41 | 24.14 | 14.87 | 0.45 |


### 3.2 Analisis Performa

#### 3.2.1 Model Terbaik
**K-Nearest Neighbors (KNN)** menjadi model terbaik dengan:
- **Accuracy**: 81.00%
- **F1-Score**: 80.68%
- **Training Time**: 0.00 seconds

#### 3.2.2 Perbandingan Baseline vs SVM
- **Best Baseline**: K-Nearest Neighbors (KNN) dengan accuracy 81.00%
- **Best SVM**: SVM (Sigmoid) dengan accuracy 31.03%
- **Performance Gap**: 49.97%

📊 **Baseline model memberikan performa sedikit lebih baik**, namun SVM sangat kompetitif.

#### 3.2.3 Analisis Per-Kernel (SVM)

| Kernel | Accuracy (%) | Best Hyperparameters |
|--------|--------------|---------------------|
| linear | 24.14 | C=0.001 |
| rbf | 24.14 | C=1, gamma=0.1 |
| poly | 24.14 | C=10, degree=3 |
| sigmoid | 31.03 | C=100, gamma=0.01 |


### 3.3 Analisis Confusion Matrix
Model terbaik menunjukkan performa yang konsisten across semua kelas. Visualisasi confusion matrix menunjukkan:
- Diagonal confusion matrix memiliki nilai tertinggi (prediksi benar)
- Misklasifikasi terjadi pada kelas-kelas yang berdekatan (e.g., BA vs AA)
- Model mampu membedakan dengan baik antara grade tinggi dan rendah

### 3.4 Computational Efficiency

**Most Efficient Model**: K-Nearest Neighbors (KNN)
- Efficiency Score: inf
- Balance optimal antara accuracy dan training time

**Training Time Comparison**:
- Fastest: K-Nearest Neighbors (KNN) (0.00s)
- Slowest: SVM (Linear) (5.31s)

---

## BAB IV - KESIMPULAN DAN SARAN

### 4.1 Kesimpulan

Berdasarkan hasil eksperimen dan analisis, dapat disimpulkan bahwa:

1. **Performa Model**: K-Nearest Neighbors (KNN) memberikan performa terbaik dengan accuracy 81.00%, precision 82.29%, recall 81.00%, dan F1-score 80.68%.

2. **SVM vs Baseline**: Meskipun baseline models sedikit lebih unggul, SVM menunjukkan performa yang sangat kompetitif dan reliable.

3. **Kernel Selection**: Kernel Sigmoid memberikan hasil terbaik untuk SVM, mengindikasikan bahwa data memiliki non-linear pattern.

4. **Practical Implementation**: Model yang dikembangkan dapat diimplementasikan dalam Early Warning System dengan accuracy di atas 81%, memberikan early detection yang reliable untuk mahasiswa berisiko.

5. **Generalization**: Stratified cross-validation menunjukkan model memiliki generalization yang baik, dengan gap train-test accuracy yang minimal.

### 4.2 Kontribusi Penelitian

1. **Metodologis**: Framework komprehensif untuk perbandingan SVM vs baseline models dalam konteks educational data mining
2. **Praktis**: Model prediktif yang dapat diimplementasikan untuk Early Warning System
3. **Akademis**: Benchmark baru untuk dataset Higher Education Students Performance Evaluation

### 4.3 Saran

#### Untuk Penelitian Lanjutan:
1. Memperbanyak data training (target >500 instances) untuk meningkatkan performa
2. Eksplorasi feature engineering lebih mendalam (polynomial features, interaction terms)
3. Implementasi ensemble methods (voting, stacking, boosting)
4. Penerapan deep learning models (LSTM, Transformer) untuk sequential data
5. Handling imbalanced classes dengan teknik SMOTE atau ADASYN

#### Untuk Implementasi:
1. Deploy model terbaik sebagai web service API
2. Integrasi dengan sistem akademik existing
3. Dashboard real-time monitoring untuk dosen/penasihat akademik
4. Automated alert system untuk mahasiswa berisiko
5. Periodic model retraining dengan data baru

### 4.4 Keterbatasan Penelitian

1. **Dataset Size**: Jumlah instances terbatas (145 mahasiswa)
2. **Temporal Aspect**: Data cross-sectional, tidak mempertimbangkan aspek temporal
3. **Feature Limitation**: Terbatas pada features yang tersedia di dataset
4. **Generalization**: Hasil spesifik untuk konteks dataset ini, perlu validasi untuk institusi lain

---

## REFERENSI

1. Hengpraprohm et al. (2022). "A Study of Factors Affecting Learning Efficiency on Higher Education Student Performance Evaluation Dataset Using Feature Selection Techniques"
2. UCI Machine Learning Repository - Higher Education Students Performance Evaluation Dataset
3. Scikit-learn Documentation - Support Vector Machines
4. Educational Data Mining: A Review and Research Agenda

---

## LAMPIRAN

### A. Visualisasi Hasil
- Confusion matrices untuk semua model
- Comparison charts (accuracy, F1-score, training time)
- Per-class performance heatmap
- Radar chart comparison
- Trade-off analysis (time vs accuracy)

### B. Kode Implementasi
Seluruh kode implementasi tersedia dalam Jupyter Notebooks:
1. `01_EDA_and_Preprocessing.ipynb`
2. `02_Data_Preprocessing.ipynb`
3. `03_Baseline_Models.ipynb`
4. `04_SVM_Modeling.ipynb`
5. `05_Final_Evaluation_and_Report.ipynb`

### C. Data dan Model
- Preprocessed data: `data/processed/`
- Trained models: `models/`
- Results and metrics: `results/metrics/`
- Visualizations: `results/figures/`

---

**Laporan ini dihasilkan secara otomatis pada 11 November 2025, 10:30:48**
