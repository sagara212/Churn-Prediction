

---

# 🔍 **Churn Prediction Menggunakan Machine Learning dan Neural Network**

Proyek ini bertujuan untuk memprediksi kemungkinan churn nasabah menggunakan algoritma Machine Learning (ML) dan Neural Network (NN). Kami mengevaluasi model-model yang berbeda untuk menentukan siapa nasabah yang berisiko tinggi berhenti menggunakan layanan, serta memahami faktor-faktor yang mempengaruhi keputusan tersebut.

---

## 📂 **Dataset**

**Sumber Data**: KAGGLE

**Isi Dataset**:
- **Fitur**:

        1. RowNumber: Angka urutan baris di dataset. Variabel ini tidak memiliki informasi yang relevan untuk analisis atau prediksi, karena hanya digunakan sebagai indeks.
              
        2. CustomerId: ID unik untuk setiap pelanggan dalam dataset.
        
        3. Surname: Nama belakang pelanggan.
        
        4. CreditScore: Skor kredit pelanggan. Skor ini bisa mencerminkan kemampuan finansial pelanggan.
        
        5. Geography: Lokasi geografis pelanggan. Informasi ini relevan karena lokasi bisa memengaruhi perilaku pelanggan (misalnya, akses layanan berbeda-beda di tiap wilayah).
        
        6. Gender: Jenis kelamin pelanggan. Gender dapat berpengaruh pada analisis churn jika ditemukan pola perilaku berbeda berdasarkan jenis kelamin.
        
        7. Age: Usia pelanggan. Usia bisa menjadi faktor penting dalam memahami perilaku pelanggan terkait churn.
        
        8. Tenure: Lama waktu pelanggan telah menjadi anggota (dalam tahun). Tenure dapat mencerminkan loyalitas pelanggan terhadap perusahaan.
        
        9. Balance:  Saldo rata-rata dalam rekening pelanggan. Variabel ini penting karena saldo tinggi atau rendah bisa memengaruhi keputusan pelanggan untuk tetap menggunakan layanan.
        
        10. NumOfProducts: Jumlah produk yang digunakan pelanggan. Pelanggan dengan lebih banyak produk mungkin lebih kecil kemungkinannya untuk churn.
        
        11. HasCrCard:  Apakah pelanggan memiliki kartu kredit (1 = Ya, 0 = Tidak). Variabel ini relevan karena mencerminkan keterlibatan pelanggan dengan layanan.
        
        12. IsActiveMember: Status keaktifan pelanggan (1 = Aktif, 0 = Tidak Aktif). Pelanggan aktif mungkin lebih kecil kemungkinannya untuk churn.
        
        13. EstimatedSalary: Estimasi gaji pelanggan. Gaji dapat memengaruhi keputusan pelanggan terkait layanan.
        
        14. Exited: Target variabel (label) yang menunjukkan apakah pelanggan churn (1) atau tidak (0). Variabel ini adalah output utama dalam model prediksi.

- **Label**:
  - **1**: Nasabah churn (berhenti menggunakan layanan)
  - **0**: Nasabah aktif
- **Jumlah Data**: 10.0000

**Langkah Persiapan Data**:
- **Preprocessing**:
  - Normalisasi fitur numerik
  - Mengonversi variabel kategorikal menjadi format numerik (one-hot encoding)
  - Menangani nilai hilang
  - Pembagian data menjadi set pelatihan dan pengujian
- **Feature Engineering**: Menambahkan fitur-fitur baru yang relevan berdasarkan analisis awal.

---

## 🛠️ **Pemodelan dan Evaluasi**

Kami menggunakan berbagai model Machine Learning dan Neural Network untuk memprediksi churn nasabah:

### **Model Machine Learning (ML)**

1. **K-Nearest Neighbors (KNN)**
   - **Akurasi**: 82.77%
   - **Precision**: 60.18%
   - **Recall**: 33.90%
   - **F1-Score**: 43.37%

2. **Decision Tree (DT)**
   - **Akurasi**: 80.70%
   - **Precision**: 50.41%
   - **Recall**: 52.40%
   - **F1-Score**: 51.39%

3. **Random Forest (RF)**
   - **Akurasi**: 87.17%
   - **Precision**: 77.72%
   - **Recall**: 47.77%
   - **F1-Score**: 59.17%

4. **Naive Bayes (NB)**
   - **Akurasi**: 81.47%
   - **Precision**: 53.24%
   - **Recall**: 39.38%
   - **F1-Score**: 45.28%

5. **Support Vector Machine (SVM)**
   - **Akurasi**: 85.70%
   - **Precision**: 84.44%
   - **Recall**: 32.53%
   - **F1-Score**: 46.97%

### **Model Neural Network (NN)**

- **Epoch 42/100**
  - **Akurasi**: 86.12% (Training)
  - **AUC**: 88.32%
  - **Loss**: 0.3352
  - **Validation Accuracy**: 85.67%
  - **Validation AUC**: 84.92%
  - **Validation Loss**: 0.3657
  - **Learning Rate**: 5.0000e-04

**Langkah-Langkah**:
1. **Eksplorasi Data**: Meneliti karakteristik churn nasabah dan faktor-faktor penyebab churn.
2. **Feature Engineering**: Membangun fitur baru yang lebih informatif untuk meningkatkan kinerja model.
3. **Pelatihan Model**:
   - Melatih model ML menggunakan teknik seperti K-Nearest Neighbors, Decision Tree, Random Forest, Naive Bayes, dan SVM.
   - Melatih Neural Network dengan representasi vektor data nasabah.
4. **Evaluasi Model**: Menggunakan metrik akurasi, precision, recall, dan F1-score untuk menilai kinerja model.

---

## 🏆 **Hasil**

### **Kinerja Model**
| Model                    | Akurasi  | Precision | Recall  | F1-Score |
|--------------------------|----------|-----------|---------|----------|
| KNN                      | 82.77%   | 60.18%    | 33.90%  | 43.37%   |
| Decision Tree (DT)       | 80.70%   | 50.41%    | 52.40%  | 51.39%   |
| Random Forest (RF)       | 87.17%   | 77.72%    | 47.77%  | 59.17%   |
| Naive Bayes (NB)         | 81.47%   | 53.24%    | 39.38%  | 45.28%   |
| Support Vector Machine (SVM) | 85.70% | 84.44% | 32.53%  | 46.97%   |
| Neural Network (NN)      | 86.12% (Train), 85.67% (Val) | - | - | - |

**Kesimpulan Awal**:
- Model Neural Network (NN) menunjukkan performa yang sangat baik, dengan akurasi tinggi pada data pelatihan dan validasi.
- Random Forest (RF) memiliki kinerja yang solid dengan akurasi 87.17% dan precision tinggi, namun recall-nya lebih rendah.
- K-Nearest Neighbors (KNN) dan Naive Bayes (NB) menunjukkan kinerja lebih rendah dibandingkan dengan model lainnya.

---

## 💻 **Teknologi yang Digunakan**

- **Python**: Untuk pengolahan data dan pemodelan.
- **TensorFlow & Keras**: Untuk membangun dan melatih model Neural Network.
- **Scikit-learn**: Untuk implementasi model Machine Learning (ML).
- **Matplotlib & Seaborn**: Untuk visualisasi hasil analisis dan kinerja model.
- **Pandas & NumPy**: Untuk manipulasi dan analisis data.

---

## 📈 **Visualisasi**

Kami menyediakan grafik untuk:
- Perbandingan hasil akurasi antara model ML dan Neural Network.
- Kurva loss dan akurasi selama pelatihan model Neural Network.
- Confusion Matrix untuk model-model ML dan Neural Network.

---

## 🔗 **Langkah Selanjutnya**
1. **Optimasi Model Neural Network**: Menggunakan hyperparameter tuning untuk meningkatkan performa pada data validasi.
2. **Analisis Lanjutan**: Mengidentifikasi fitur-fitur penting yang mempengaruhi keputusan churn.
3. **Penerapan**: Mengembangkan sistem prediksi churn secara real-time yang dapat diterapkan di industri perbankan untuk meningkatkan retensi nasabah.

---

