# 📊 Final Project Data Mining

## Rekomendasi Bundling Produk Minimarket Menggunakan Algoritma Apriori

Repository ini merupakan **Final Project Mata Kuliah Data Mining** yang membahas penerapan **Association Rule Mining (Algoritma Apriori)** untuk menghasilkan **rekomendasi bundling produk** berdasarkan data transaksi minimarket.

---

## 👥 Kelompok 7

- Arifatus Fitriani
- Yumna Kamilah Mahdiyah
- Amelia Rizki Andini

---

## 🎯 Tujuan Penelitian

Penelitian ini bertujuan untuk:

* Menganalisis pola pembelian konsumen pada minimarket
* Menemukan hubungan antar produk menggunakan algoritma Apriori
* Memberikan rekomendasi bundling produk berdasarkan nilai **support, confidence, dan lift**

---

## 📂 Struktur Repository

```
FP-Data-Mining-Kelompok-7
│
├── FP_KEL7_DATMIN.ipynb     # Notebook analisis (EDA & Apriori)
├── StrukDetail.xlsx        # Dataset transaksi minimarket
└── README.md               # Dokumentasi proyek
```

---

## 📊 Dataset

Dataset yang digunakan merupakan **data transaksi minimarket** dengan karakteristik:

* Total data: **2321 baris**
* Jumlah kolom: **13**
* Tidak terdapat missing value
* Merupakan data transaksi selama 1 minggu

Kolom utama yang digunakan dalam analisis Apriori:

* `NO.TRANSAKSI`
* `ITEM`

Kolom numerik lainnya digunakan untuk **EDA**, seperti:

* `QTY`
* `TOTAL PENJUALAN`
* `KEUNTUNGAN`
* `MARGIN (%)`

---

## 🔍 Tahapan Penelitian

### 1️⃣ Exploratory Data Analysis (EDA)

EDA dilakukan untuk memahami karakteristik data, meliputi:

* Produk terlaris berdasarkan frekuensi transaksi
* Analisis waktu transaksi (pagi, siang, sore, malam)
* Analisis total penjualan (revenue)
* Analisis margin keuntungan
* Deteksi outlier menggunakan boxplot

📌 Outlier ditemukan pada beberapa kolom numerik, namun **tidak dihapus** karena merupakan kondisi wajar pada data transaksi minimarket dan tidak memengaruhi algoritma Apriori.

---

### 2️⃣ Preprocessing Data

Tahapan preprocessing meliputi:

* Pemilihan kolom `NO.TRANSAKSI` dan `ITEM`
* Pembersihan teks item (uppercase, penghapusan simbol)
* Penghapusan duplikasi item dalam satu transaksi
* Pengelompokan item berdasarkan ID transaksi

---

### 3️⃣ One-Hot Encoding

Data transaksi diubah menjadi bentuk **matriks biner (0/1)** menggunakan `TransactionEncoder`, di mana:

* **1/True** menunjukkan item dibeli dalam transaksi
* **0/False** menunjukkan item tidak dibeli

Tahap ini diperlukan agar algoritma Apriori dapat menghitung **frequent itemset** dan **aturan asosiasi**.

---

### 4️⃣ Association Rule Mining (Apriori)

Algoritma Apriori digunakan untuk menemukan pola pembelian konsumen.
Evaluasi dilakukan menggunakan metrik:

* **Support**
* **Confidence**
* **Lift**

Beberapa skenario pengujian dilakukan dengan variasi nilai support dan confidence untuk memperoleh aturan asosiasi terbaik yang dapat dijadikan rekomendasi bundling.

---

### 5️⃣ Visualisasi Network

Hubungan antar produk divisualisasikan dalam bentuk **network graph**, sehingga relasi antara **antecedent** dan **consequent** dapat dilihat secara visual.

---

## 📓 Notebook (Google Colab / Jupyter)

Seluruh proses analisis dapat diakses melalui notebook berikut:

📘 **FP_KEL7_DATMIN.ipynb**
Notebook ini mencakup:

* EDA
* Preprocessing
* One-Hot Encoding
* Apriori & Association Rules
* Visualisasi hasil

---

## 🌐 Aplikasi Streamlit

Hasil analisis juga ditampilkan dalam bentuk aplikasi interaktif menggunakan **Streamlit**.

🔗 **Link Streamlit App:**
👉 [https://coloristic-calista-nonmodificative.ngrok-free.dev/](https://coloristic-calista-nonmodificative.ngrok-free.dev/)

Aplikasi ini menampilkan:

* Pengaturan minimum support, confidence, dan lift
* Menampilkan rekomendasi bundling dan peletakan produk (jika memenuhi threshold)

---

## 📌 Kesimpulan Singkat

Berdasarkan hasil analisis menggunakan algoritma Apriori, diperoleh beberapa pasangan produk yang memiliki nilai **confidence dan lift tinggi**, sehingga berpotensi digunakan sebagai **strategi bundling produk** pada minimarket.

---

## 🛠 Tools & Library

* Python
* Pandas
* Matplotlib / Seaborn
* Mlxtend
* NetworkX
* Streamlit

---
