# Titanic Survival Prediction

Proyek data mining untuk memprediksi keselamatan penumpang Titanic menggunakan Python dan algoritma Random Forest. Dibangun sebagai proyek belajar end-to-end: dari eksplorasi data hingga evaluasi model.

---

## Temuan utama

Dari analisis feature importance, dua faktor paling berpengaruh terhadap keselamatan penumpang adalah:

- **Gender** - penumpang wanita memiliki survival rate 74%, dibanding pria hanya 19%. Kebijakan "women and children first" terbukti secara statistik.
- **Fare (harga tiket)** - berkorelasi kuat dengan kelas kabin dan akses ke sekoci. Penumpang kelas 1 memiliki survival rate 63%, kelas 3 hanya 24%.

---

## Hasil model

| Metrik | Nilai |
|---|---|
| Algoritma | Random Forest Classifier |
| Akurasi | 82.58% |
| Precision (kelas selamat) | 0.79 |
| Recall (kelas selamat) | 0.74 |
| F1-Score (kelas selamat) | 0.76 |

---

## Struktur project

```
titanic-survival-prediction/
├── titanic_analysis.ipynb   # Notebook utama (semua langkah)
├── requirements.txt         # Library yang dibutuhkan
└── README.md
```

---

## Langkah-langkah analisis

**1. Load data** - Dataset diambil langsung dari URL publik GitHub (tidak perlu download manual).

**2. Exploratory Data Analysis (EDA)** - Memeriksa distribusi data, missing values, dan korelasi antar fitur menggunakan Pandas dan Seaborn.

**3. Preprocessing** - Mengisi missing values kolom `Age` dengan median, drop kolom `Cabin` (77% kosong), dan encoding kolom kategorikal (`Sex`, `Embarked`).

**4. Visualisasi** - Heatmap korelasi, survival rate per gender, distribusi usia, dan feature importance chart.

**5. Modeling** - Membangun Random Forest Classifier dengan 100 estimators dan max depth 5, dilatih pada 80% data.

**6. Evaluasi** - Mengukur performa dengan accuracy score, classification report, dan confusion matrix pada 20% data test.

---

## Dataset

- **Sumber:** [Titanic Dataset — Kaggle](https://www.kaggle.com/datasets/yasserh/titanic-dataset)
- **Ukuran:** 891 baris × 12 kolom
- **Target:** Kolom `Survived` (0 = meninggal, 1 = selamat)

---

## Rencana pengembangan

- [ ] Feature engineering lanjutan — ekstrak `Title` dari nama, buat fitur `FamilySize` dan `IsAlone`
- [ ] Hyperparameter tuning dengan GridSearchCV
- [ ] Coba algoritma XGBoost dan ensemble/stacking
- [ ] 10-fold cross-validation untuk estimasi performa yang lebih robust

---

*Project ini dibuat sebagai bagian dari perjalanan belajar data mining dan machine learning.*
