# Tugas 3 Mata Kuliah Machine Learning Universitas Terbuka
## Segmentasi Pelanggan (Customer Personality Analysis) - K-Means Clustering

Repositori ini berisi penyelesaian Tugas 3 mata kuliah Machine Learning. Proyek ini mengimplementasikan algoritma *Unsupervised Learning* (K-Means) untuk melakukan segmentasi pelanggan berdasarkan data kepribadian dan perilaku pembelian mereka.

## 📁 Struktur Repositori

```text
tugas-3-machine-learning/
├── data/
│   └── cpa.csv                     # Dataset mentah
├── Tugas3b.ipynb                   # Source code utama pada Jupyter Notebook atau Google Colab
├── README.md                       # Dokumentasi proyek
└── .gitignore                      # File untuk mengabaikan file sistem atau cache Git
```

## 🎯 Tujuan Proyek
Melakukan analisis dan segmentasi pelanggan untuk membantu perusahaan merumuskan strategi pemasaran yang lebih tepat sasaran. Segmentasi dilakukan dengan mengelompokkan pelanggan yang memiliki karakteristik dan kebiasaan belanja yang serupa.

## 🛠️ Alur Kerja (Workflow)
1. **Eksplorasi Data Awal:** Memuat dataset, mengecek tipe data, dan melihat distribusi data.
2. **Preprocessing Data & Feature Engineering:** 
   - Mengekstrak `Year_Birth` menjadi fitur `Umur`.
   - Mengekstrak `Dt_Customer` menjadi fitur `Lama_Berlangganan` (dalam hari).
   - Melakukan imputasi pada *missing values*.
   - Melakukan *One-Hot Encoding* untuk data kategorikal.
   - Standardisasi data (*Scaling*) menggunakan `StandardScaler`.
3. **Penentuan Jumlah Klaster (K):** Menggunakan metode **Elbow** dan **Silhouette Score** untuk menemukan jumlah klaster yang paling optimal (berdasarkan analisis, ditetapkan K=2).
4. **Klastering:** Melatih model K-Means dengan K=2.
5. **Visualisasi PCA:** Mereduksi dimensi data menjadi 2 dimensi (PCA 2D) untuk memvisualisasikan persebaran klaster pelanggan secara jelas.
6. **Profiling & Interpretasi:** Menganalisis rata-rata nilai fitur pada tiap klaster untuk menarik kesimpulan bisnis.

## 📊 Hasil Analisis (Kesimpulan)
Berdasarkan hasil pemodelan, pelanggan dibagi menjadi dua segmen utama:

* **Cluster 1 (Pelanggan Loyal Kelas Atas):** Pelanggan dengan rata-rata pendapatan tinggi, pengeluaran besar untuk produk tersier (wine, daging, emas), dan tidak memiliki tanggungan anak kecil di rumah. Mereka gemar berbelanja di berbagai platform dan mudah merespons *campaign* atau promo.
* **Cluster 0 (Pelanggan Hemat dan Pemburu Diskon):** Pelanggan dengan pendapatan menengah ke bawah dan umumnya memiliki tanggungan anak kecil. Mereka memiliki tingkat kunjungan website yang tinggi (sering *window shopping*) namun jarang melakukan transaksi kecuali jika ada diskon yang signifikan.

## 🚀 Cara Menjalankan Proyek
1. *Clone* repositori ini: `git clone https://github.com/rifkyh/tugas-3-machine-learning.git`
2. Buka Google Colab atau Jupyter Notebook lokal Anda.
3. *Upload* file `Tugas3b.ipynb`.
4. Pastikan Anda mengunggah dataset `cpa.csv` ke dalam *environment* Colab Anda sebelum menjalankan *cell* kode.
5. Jalankan (*Run All*) seluruh sel secara berurutan.

## 💻 Library yang Digunakan
* Pandas & NumPy (Manipulasi Data)
* Scikit-Learn (Preprocessing, K-Means, PCA, Metrics)
* Matplotlib & Seaborn (Visualisasi Data)
