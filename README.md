# 📊 Prediksi Klaim Asuransi Perjalanan untuk Efisiensi Bisnis: Pendekatan Machine Learning
Proyek ini bertujuan untuk membangun model klasifikasi untuk memprediksi kemungkinan pelanggan membeli asuransi perjalanan berdasarkan data profil dan histori mereka.

# 🧠 Problem Statement
Perusahaan asuransi ingin meningkatkan efektivitas kampanye marketing dengan cara mengidentifikasi pelanggan yang kemungkinan besar akan membeli asuransi perjalanan. Diperlukan model prediktif untuk membantu pengambilan keputusan berbasis data.

# 📁 Dataset
Dataset berisi berbagai fitur dan dikelompokkan menjadi dua tipe data yaitu:
- Numerical: `Duration`, `Commission`, `Net Sales`, `Age`
- Categorical : `Agency`, `Agency Type`, `Distribution Channel`, `Product Name`, `Gender`, `Destination`
Yang menjadi Target/Label yang akan diprediksi oleh model yaitu `Claim` yang merupakan Status Klaim yang diklasifikasikan dalam bentuk biner dengan output 0 = untuk tidak klaim dan 1 = untuk Klaim

# 🔧 Tools & Library
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-Learn
- Joblib (model deployment)

# ⚙️ Metodologi
1. Eksplorasi Data
   - Analisis distribusi umur, Commision, dan korelasi antar variabel
   - Penanganan missing value & encoding fitur kategorikal
2. Modeling
   - Menggunakan K-Nearest Neighbors (KNN)
   - Pipeline preprocessing + modeling
   - Hyperparameter tuning dengan GridSearchCV
3. Evaluasi
   - Akurasi, Precision, Recall
   - Confusion Matrix

# 📈 Conclusion
1. Ketidakseimbangan Data
   - Mayoritas data: pelanggan tidak mengajukan klaim.
   - Model awal cenderung bias ke kelas mayoritas.
   - Solusi: Random Under Sampling → hasilkan model dengan recall lebih baik.
2. Evaluasi Model
   - Model terbaik: K-Nearest Neighbors (KNN).
   - Recall tinggi → bagus untuk mendeteksi sebanyak mungkin klaim.
   - Precision rendah → banyak prediksi klaim yang tidak benar (false positive).
   - Trade-off precision vs recall dapat diatur via threshold
3.Feature Importance (Recall-Based)
  - Fitur paling berpengaruh:
    - Product Name
    - Destination
    - Net Sales
  - Fitur kurang penting/negatif:
    - Age
    - Duration
   
# 💡Recommendation
1. Fokus pada Produk & Destinasi
   - Produk asuransi dan tujuan perjalanan terbukti paling memengaruhi klaim.
   - Gunakan untuk pengaturan premi & strategi penawaran.
2. Deteksi Dini Risiko Klaim
   - Model dapat menandai calon nasabah berisiko tinggi.
   - Lanjutkan dengan verifikasi manual atau mitigasi.
3. Eksperimen Model Lanjutan
   Coba pendekatan seperti:
   - SMOTE (oversampling)
   - Random Forest / XGBoost
   - Class weight adjustment
   - Threshold tuning
4. Uji di Data Nyata
   - Validasi performa pada data real untuk uji generalisasi.
5. Integrasi Operasional
   - Terapkan model ke sistem underwriting atau pengelolaan risiko.
