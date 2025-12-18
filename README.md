# 📘 Prediksi Jumlah Penyewaan Sepeda (Bike Sharing Prediction)
*Proyek UAS Data Science - Analisis & Prediksi Permintaan Sepeda Menggunakan Machine Learning*

## 👤 Informasi Mahasiswa
- **Nama:** Zahy Nadhir Nashrullah
- **NIM:** 233307060
- **Kelas:** TI-5B
- **Repo:** https://github.com/zahynadhirnashrullah/UAS-Bike-Sharing-Prediction.git
- **Video Penjelasan:** https://youtu.be/__mTu-6IgZU 

---

# 1. 🎯 Ringkasan Proyek
Proyek ini bertujuan untuk memprediksi jumlah total penyewaan sepeda (*cnt*) berdasarkan faktor lingkungan dan waktu. Proyek ini mencakup end-to-end data science lifecycle mulai dari pembersihan data hingga evaluasi model.

- Menyelesaikan permasalahan prediksi permintaan (*demand forecasting*) pada sistem Bike Sharing.
- Melakukan data preparation (Cleaning, Scaling, Splitting).
- Membangun 3 model eksperimen: **Linear Regression (Baseline)**, **Random Forest (Advanced ML)**, dan **Deep Learning (MLP)**.
- Melakukan evaluasi menggunakan metrik MAE & RMSE untuk menentukan model terbaik.

---

# 2. 📄 Problem & Goals
**Problem Statements:**
- Bagaimana memprediksi jumlah penyewaan sepeda secara akurat untuk menghindari kekurangan/kelebihan stok di stasiun?
- Faktor cuaca (suhu, kelembaban) dan waktu (jam, musim) apa yang paling mempengaruhi jumlah penyewaan?

**Goals:**
- Membangun model regresi yang mampu memprediksi jumlah penyewaan sepeda dengan error seminimal mungkin.
- Membandingkan performa antara model Statistik Konvensional, Machine Learning, dan Deep Learning.

---
## 📁 Struktur Folder
```text
project/
│
├── data/                   # Dataset
│   └── hour.csv            # Dataset utama (Bike Sharing UCI)
│
├── notebooks/              # Jupyter notebooks
│   └── Bike_Sharing_Prediction.ipynb  # File Kodingan Utama
│
├── src/                    # Source code (Opsional)
│   └── .gitkeep
│
├── models/                 # Saved models (Model yang sudah dilatih)
│   ├── model_baseline.pkl  # Linear Regression
│   ├── model_rf.pkl        # Random Forest
│   └── model_dl.h5         # Deep Learning (Keras)
│
├── images/                 # Visualizations (Opsional)
│
├── requirements.txt        # Dependencies library Python
├── .gitignore              # File yang diabaikan git
└── README.md               # Dokumentasi Proyek

```

# 3. 📊 Dataset
- **Sumber:** UCI Machine Learning Repository - Bike Sharing Dataset
- **Jumlah Data:** 17,379 baris (jam)  
- **Tipe:** Tabular & Time Series Regression  

### Fitur Utama
| Fitur | Deskripsi |
| cnt |Target: Jumlah total sepeda yang disewa|
| hr | Jam peminjaman (0-23) |
| temp | Temperatur normalisasi (Celsius) |
| hum | Kelembaban normalisasi |
| weathersit | Kondisi cuaca (1: Cerah, 4: Hujan Lebat) |
| season | Musim (1: Semi, 2: Panas, 3: Gugur, 4: Dingin) |

---

# 4. 🔧 Data Preparation
Langkah-langkah preprocessing yang dilakukan:
1. Cleaning: Menghapus fitur yang tidak relevan (instant, dteday) dan fitur bocoran/data leakage (casual, registered).

2. Transformasi: Melakukan standardisasi (StandardScaler) pada fitur numerik (temp, hum, windspeed) agar skala data seragam untuk Deep Learning.

3. Splitting: Membagi dataset menjadi 80% Training set dan 20% Testing set.

---

# 5. 🤖 Modeling
- Model 1 – Baseline (Linear Regression): Model sederhana sebagai patokan dasar (benchmark). Cepat dilatih namun memiliki error yang cukup tinggi karena hubungan data tidak sepenuhnya linear. 
- Model 2 – Advanced ML (Random Forest Regressor): Model ensemble berbasis pohon keputusan. Mampu menangkap pola non-linear yang kompleks dan terbukti menjadi model dengan performa terbaik. 
- Model 3 – Deep Learning (Multilayer Perceptron / MLP): Jaringan saraf tiruan menggunakan TensorFlow/Keras dengan arsitektur 3 Hidden Layers, aktivasi ReLU, dan Dropout untuk mencegah overfitting.

---

# 6. 🧪 Evaluation
Evaluasi dilakukan menggunakan metrik MAE (Mean Absolute Error) dan RMSE (Root Mean Squared Error).

Hasil Evaluasi:
1. Linear Regression: Error Tertinggi (Underfitting).
Random Forest: Error Terendah (Best Model).

2. Deep Learning: Performa cukup baik, namun sedikit di bawah Random Forest pada dataset ini.

Kesimpulan: Random Forest dipilih sebagai model terbaik karena ketangguhannya dalam menangani data tabular dengan fitur campuran kategorikal dan numerik.

---

# 7. 🏁 Kesimpulan
Berdasarkan hasil analisis dan evaluasi model, diperoleh kesimpulan sebagai berikut:
- **Model Terbaik:** Random Forest Regressor terpilih sebagai model terbaik karena memiliki nilai MAE dan RMSE terendah dibandingkan Linear Regression dan Deep Learning.
- **Faktor Penting:** Analisis *Feature Importance* menunjukkan bahwa jam peminjaman (`hr`) dan suhu (`temp`) adalah dua faktor paling dominan yang memengaruhi jumlah penyewaan sepeda.
- **Pola Penggunaan:** Permintaan sepeda mencapai puncaknya pada jam sibuk (08.00 pagi dan 17.00 sore), serta meningkat signifikan saat cuaca cerah dan suhu hangat.

---

# 8. 🔮 Future Work (Pengembangan Selanjutnya)
Beberapa hal yang dapat dikembangkan untuk meningkatkan kualitas proyek ini di masa depan:
- [ ] **Hyperparameter Tuning:** Menggunakan GridSearch atau RandomSearch untuk mencari parameter optimal pada model Random Forest dan Deep Learning.
- [ ] **Feature Engineering:** Menambahkan fitur baru seperti "Jam Sibuk" atau "Hari Libur Nasional" untuk membantu model belajar lebih baik.
- [ ] **Model Deployment:** Mengembangkan aplikasi web sederhana (menggunakan Streamlit/Flask) agar model dapat digunakan secara langsung oleh pengguna.
- [ ] **Time Series Analysis:** Mencoba algoritma LSTM (Long Short-Term Memory) yang spesifik untuk data deret waktu.

---

# 9. 🔁 Reproducibility
Berikut adalah langkah-langkah untuk menjalankan proyek ini di komputer lokal:

### 1. Clone Repository
Unduh kode sumber proyek ini ke komputer Anda:
```bash
git clone [https://github.com/zahynadhirnashrullah/UAS-Bike-Sharing-Prediction.git]
cd [NAMA FOLDER REPO]