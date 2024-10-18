<p align="center">
  <img src="https://drive.google.com/uc?export=view&id=1k13Bw7WwHaIotaWjNy1wuA1qp1VFVOAt" alt="My Image" width="900" height="200">
</p>

---

# Repository Overview

1. **[Dataset]()**
Dalam repository ini, terdapat 3 file CSV yang digunakan untuk berbagai keperluan dalam analisis dan deployment:

  - **`bank-additional-full.csv`**: Dataset awal dari ICU yang berisi informasi lengkap tentang data yang akan digunakan sebagai dasar pemodelan.
  - **`df2_processed.csv`**: Dataset yang telah melalui proses cleansing dan feature engineering, siap untuk diolah lebih lanjut dan dianalisis untuk mendapatkan insights bisnis.
  - **`sample_input.csv`**: Dataset yang digunakan sebagai data percobaan untuk prediksi di aplikasi web lokal yang telah dibuat.

2. **[Notebook]()**
Terdapat 3 notebook utama yang digunakan untuk berbagai keperluan analisis, insights bisnis, dan pemodelan:

  - **`EDA_&_Pre_processing.ipynb`**: Notebook yang berisi Exploratory Data Analysis (EDA) yang berfokus pada proses cleansing data dan feature engineering.
  - **`EDA_Business_Insights.ipynb`**: Notebook khusus yang fokus pada penggalian dan eksplorasi insights bisnis dari data yang telah dibersihkan.
  - **`Modelling.ipynb`**: Notebook yang berisi lanjutan dari pre-processing khusus untuk pemodelan, mencakup proses modelling, simulasi bisnis, serta persiapan sebelum deployment.

3. **[Deployment]()**
Struktur file dan folder untuk deployment aplikasi web yang telah dibangun menggunakan Flask:

  - **`app.py`**: File utama yang berisi kode Flask untuk menjalankan aplikasi web, memungkinkan pengguna untuk melakukan prediksi.
  - **`model_deposito_all_in_one.pkl`**: File pickle yang berisi model, target encoder, dan urutan encoding. File ini memungkinkan aplikasi untuk melakukan prediksi berdasarkan input pengguna.
  - **`templates/`**: Folder yang berisi file HTML untuk tampilan antarmuka pengguna.
    - **`index.html`**: Halaman utama yang menampilkan form input kepada pengguna.
    - **`predict.html`**: Halaman yang menampilkan hasil prediksi.
  - **`static/`**: Folder yang menyimpan file statis seperti CSS untuk mengatur styling tampilan.
    - **`style.css`**: File CSS yang digunakan untuk mengatur tampilan antarmuka pengguna.

4. **[Assets]()**
Terdapat folder **`assets/`** yang berisi gambar-gambar yang digunakan di file README, untuk memberikan ilustrasi tentang tampilan aplikasi dan proses analisis.

---

# **Background of the Problem**
---

Dalam konteks krisis ekonomi global yang dimulai pada tahun 2008, sebuah bank di Portugal meluncurkan kampanye promosi produk deposito berjangka. Dari total 41.188 nasabah yang menjadi target, 11,3% berhasil dikonversi menjadi pelanggan produk tersebut. Pencapaian ini dapat dikatakan standar mengingat situasi ekonomi yang menantang, namun fakta bahwa 88,7% nasabah target tidak merespons positif menunjukkan adanya ruang yang signifikan untuk peningkatan.

Penerapan machine learning untuk prediktif modeling direkomendasikan sebagai solusi yang menjanjikan untuk meningkatkan tingkat konversi secara signifikan. Dibandingkan dengan metode tradisional seperti analisis statistik, segmentasi manual, atau rule-based systems, machine learning menawarkan keunggulan dalam kemampuan analisis data kompleks, akurasi prediksi yang lebih tinggi, personalisasi kampanye yang lebih efektif, serta adaptabilitas terhadap perubahan pasar. Landasan rekomendasi ini diperkuat oleh proyeksi yang menunjukkan potensi peningkatan tingkat konversi hingga 30%. Dengan basis nasabah yang besar, peningkatan persentase ini dapat berdampak substansial.

---

# **Goal**
---

**Optimize term deposit campaign through predictive modeling to increase conversion and cost efficiency amid economic challenges.**

---

# **Objectives**
---

- Mengoptimalkan efisiensi biaya kampanye dengan meminimalkan pengeluaran yang tidak perlu, sambil tetap mencapai hasil yang diinginkan. Fokusnya adalah mengurangi biaya per pelanggan tanpa mengorbankan kualitas kampanye.
- Meningkatkan tingkat konversi melalui strategi pemasaran yang lebih efektif dan terarah, dengan tujuan mengubah lebih banyak prospek menjadi pelanggan dalam setiap kampanye yang dilakukan.
- Menurunkan biaya akuisisi pelanggan dengan strategi pemasaran yang efisien, menggunakan sumber daya yang lebih sedikit untuk mendapatkan setiap pelanggan baru, sehingga meningkatkan laba per pelanggan.
- Meningkatkan Return on Investment (ROI) kampanye pemasaran dengan memaksimalkan pendapatan yang diperoleh dari setiap pengeluaran. Fokusnya adalah mendapatkan nilai yang lebih besar dari investasi yang dikeluarkan melalui optimasi proses dan strategi, sehingga menghasilkan keuntungan yang lebih tinggi dalam setiap kampanye.

---

# **Metrics**
---
**Business Metrics**

1. **Saving Cost**: Mengoptimalkan pengeluaran kampanye dengan mengurangi biaya yang tidak efisien. Targetnya adalah mencapai penghematan biaya sebesar 60% dibandingkan baseline, sambil tetap mempertahankan efisiensi kampanye.

2. **Conversion Rate (Persen)**: Meningkatkan persentase konversi dari prospek menjadi pelanggan. Targetnya adalah meningkatkan conversion rate sebesar 20% dibandingkan baseline, untuk konversi yang lebih optimal dari prospek menjadi pelanggan.

3. **Customer Acquisition Cost (CAC)**: Menurunkan biaya per pelanggan yang didapatkan. Targetnya adalah mengurangi CAC hingga 60% dibandingkan baseline, guna meningkatkan efisiensi biaya akuisisi pelanggan.

4. **Return on Investment (ROI)**: Mengukur efektivitas kampanye berdasarkan laba yang dihasilkan dibandingkan dengan biaya yang dikeluarkan. Targetnya adalah meningkatkan ROI sebesar 50% dibandingkan baseline, untuk memastikan pengeluaran memberikan keuntungan yang stabil dan signifikan.

**Model Metrics**
- Recall: Penting untuk menghindari kehilangan peluang bisnis. Dengan Recall tinggi, bank bisa mengidentifikasi sebagian besar calon nasabah. Jika Recall tinggi, model berhasil mengidentifikasi sebagian besar nasabah yang akan membuka deposito, sehingga bank tidak kehilangan calon nasabah potensial.

- ROC-AUC: Cocok untuk data tidak seimbang dan memberikan gambaran menyeluruh tentang kinerja model. ROC-AUC mengukur kemampuan model membedakan antara nasabah yang akan dan tidak akan membuka deposito sehingga menyeimbangkan antara Confusion metriks yang dihasilkan

---

# **About the Dataset**
---

Dataset ini didasarkan pada dataset **["Bank Marketing" UCI](http://archive.ics.uci.edu/ml/datasets/Bank+Marketing)**. Data ini diperkaya dengan penambahan lima fitur/atribut sosial dan ekonomi baru (indikator nasional dari negara dengan populasi sekitar ~10 juta), yang dipublikasikan oleh **[Banco de Portugal](https://www.bportugal.pt/estatisticasweb)**. Dataset ini memiliki **41188 baris**, dengan kolom sebagai berikut:

Table 1. Data Dictionary

| **Nama Kolom**      | **Deskripsi**                                                                                             | **Tipe Data** |
|---------------------|----------------------------------------------------------------------------------------------------------|---------------|
| `age`               | Usia klien bank                                                                                           | Numerik       |
| `job`               | Jenis pekerjaan klien                                                                                     | Kategorikal   |
| `marital`           | Status perkawinan klien                                                                                   | Kategorikal   |
| `education`         | Tingkat pendidikan klien                                                                                  | Kategorikal   |
| `default`           | Apakah klien memiliki kredit macet?                                                                       | Kategorikal   |
| `housing`           | Apakah klien memiliki pinjaman perumahan?                                                                 | Kategorikal   |
| `loan`              | Apakah klien memiliki pinjaman pribadi?                                                                   | Kategorikal   |
| `contact`           | Jenis komunikasi kontak terakhir                                                                          | Kategorikal   |
| `month`             | Bulan kontak terakhir                                                                                     | Kategorikal   |
| `day_of_week`       | Hari kontak terakhir dalam seminggu                                                                       | Kategorikal   |
| `duration`          | Durasi kontak terakhir dalam detik                                                                        | Numerik       |
| `campaign`          | Jumlah kontak selama kampanye ini untuk klien                                                             | Numerik       |
| `pdays`             | Jumlah hari sejak klien terakhir kali dihubungi dalam kampanye sebelumnya (999 jika belum pernah dihubungi)| Numerik       |
| `previous`          | Jumlah kontak sebelum kampanye ini                                                                        | Numerik       |
| `poutcome`          | Hasil kampanye pemasaran sebelumnya                                                                       | Kategorikal   |
| `emp.var.rate`      | Tingkat variasi pekerjaan - indikator triwulanan                                                          | Numerik       |
| `cons.price.idx`    | Indeks harga konsumen - indikator bulanan                                                                 | Numerik       |
| `cons.conf.idx`     | Indeks kepercayaan konsumen - indikator bulanan                                                           | Numerik       |
| `euribor3m`         | Tingkat Euribor 3 bulan - indikator harian                                                                | Numerik       |
| `nr.employed`       | Jumlah karyawan - indikator triwulanan                                                                    | Numerik       |
| `y`                 | Apakah klien berlangganan deposito berjangka?                                                             | Biner         |


---

# **EDA & Pre-Processing**
---


Tabel 2. EDA & Pre-Processing

| **Tahapan EDA &  Pre-Processing**                      | **Deskripsi**                                                                                     |
|---------------------------------------|---------------------------------------------------------------------------------------------------|
| Menghapus nilai kosong                | Menghapus baris/kolom yang berisi nilai `unknown` yang dianggap sebagai nilai kosong.              |
| Menangani duplikat                    | Mengidentifikasi dan menghapus baris yang duplikat di seluruh dataset.                             |
| Feature Engineering                   | Menambahkan 16 kolom baru sebagai hasil dari analisis tambahan dan kombinasi fitur yang relevan.   |
| Business Insight                      | Melakukan analisis untuk menemukan wawasan bisnis yang dapat diambil dari data.                    |
| Menghapus fitur bias                  | Menghapus fitur yang bias secara teoretis atau keputusan bisnis, seperti `durations`, `emp.var.rate`, dan `nr.employed`. |
| Menghapus fitur dengan banyak kategori| Fitur dengan terlalu banyak kategori dihapus karena dapat meningkatkan kompleksitas tanpa nilai tambah. |
| One-hot encoding                      | Mengaplikasikan one-hot encoding pada fitur kategorikal nominal untuk mengubahnya menjadi bentuk numerik. |
| Label encoding                        | Menerapkan label encoding pada fitur kategorikal ordinal untuk menjaga urutan kategori.            |
| Split data                            | Membagi data menjadi 70% untuk train dan 30% untuk test.                                           |
| Menangani class imbalance             | Menangani ketidakseimbangan kelas pada data train menggunakan teknik SMOTE (Synthetic Minority Over-sampling Technique). |

---

# **Business Insights**
---

Telah ditemukan banyak sekali business insights yang dapat diakses pada notebook **[EDA: Business Insights]()**. Namun, dalam pembahasan ini akan ditampilkan fokus pada **Euribor 3 Month** yang berpengaruh signifikan pada keputusan deposito di masa krisis.

**Gambar 1.**  

<p align="center">
  <img src="https://drive.google.com/uc?export=view&id=1x-Pk7nGKcKg6NZC9JsAEPp4lVJE2qMch" alt="Deskripsi Gambar"
</p>

Sebelum tahun 2008, suku bunga yang lebih tinggi cenderung mendorong masyarakat untuk menyimpan lebih banyak uang. Namun, setelah krisis keuangan 2008, pola ini berubah drastis. Suku bunga rendah kini justru menjadi pendorong utama bagi individu untuk menabung lebih banyak sebagai respons terhadap ketidakpastian ekonomi yang melanda yang dapat dilihat pada Gambar 1.

Dari tahun 2008 hingga 2010, Portugal mengalami gejolak ekonomi yang signifikan akibat krisis keuangan global dan krisis utang Eropa. Selama periode ini, terdapat fenomena menarik di mana suku bunga yang lebih rendah (Euribor 3M) berkorelasi dengan peningkatan jumlah deposito berjangka. Hal ini menunjukkan bahwa dalam keadaan ekonomi yang tidak stabil, suku bunga rendah dapat mendorong orang untuk lebih memilih menyimpan uang mereka dalam bentuk deposito yang dianggap lebih aman dibandingkan investasi lainnya yang berisiko.

**Kemungkinan Penyebab:**
- **Ketidakpastian Ekonomi:** Ketika masyarakat merasa tidak pasti mengenai masa depan ekonomi, mereka cenderung lebih memilih untuk menabung sebagai langkah pencegahan.
- **Alternatif Investasi yang Terbatas:** Dalam situasi krisis, pilihan investasi yang aman menjadi semakin terbatas, mendorong masyarakat untuk memilih deposito sebagai opsi yang lebih stabil.
- **Persepsi Risiko:** Suku bunga yang rendah memberikan rasa aman, dan membuat orang merasa lebih nyaman untuk menyimpan uang dalam bentuk deposito, meskipun imbal hasilnya lebih rendah.

Dengan pemahaman ini, kita dapat melihat bagaimana **Euribor 3 Month** berperan dalam memengaruhi perilaku menabung masyarakat selama masa krisis, serta alasan di balik peningkatan deposito meskipun suku bunga rendah.

---

# **Modeling**
---

Tabel 3. Model Evaluation

| Model                           | Data              | Recall | ROC-AUC |
|---------------------------------|-------------------|--------|---------|
| **Logistic Regression**         | Cross-Val Train   | 0.87   | 0.95    |
|                                 | Cross-Val Test    | 0.84   | 0.94    |
| **Decision Tree**               | Cross-Val Train   | 1.00   | 1.00    |
|                                 | Cross-Val Test    | 0.89   | 0.89    |
| **Decision Tree Tuning 1**      | Cross-Val Train   | 0.93   | 0.99    |
|                                 | Cross-Val Test    | 0.86   | 0.91    |
| **Decision Tree Tuning 2**      | Cross-Val Train   | 0.61   | 0.80    |
|                                 | Cross-Val Test    | 0.60   | 0.80    |
| **XGBoost**                    | Cross-Val Train   | 0.93   | 0.99    |
|                                 | Cross-Val Test    | 0.87   | 0.97    |
| **XGBoost Tuning 1**           | Cross-Val Train   | 0.97   | 0.99    |
|                                 | Cross-Val Test    | 0.88   | 0.97    |
| **XGBoost Tuning 2**           | Cross-Val Train   | 0.93   | 0.97    |
|                                 | Cross-Val Test    | 0.89   | 0.96    |
| **🟩 XGBoost Tuning 3**         | Cross-Val Train   | 0.94   | 0.97    |
|                                 | Cross-Val Test    | 0.90   | 0.96    |


Model terbaik yang dihasilkan dari analisis ini adalah XGBoost Tuning 3. Model ini menunjukkan performa terbaik dengan Recall tertinggi pada test set, yaitu 0.90. Selain itu, model ini juga menunjukkan stabilitas yang tinggi pada nilai ROC AUC, dengan nilai 0.96. Hal ini menunjukkan bahwa XGBoost Tuning 3 tidak hanya mampu mengidentifikasi positif dengan baik, tetapi juga memiliki kemampuan yang baik dalam membedakan antara kelas positif dan negatif, menjadikannya pilihan yang paling efektif untuk aplikasi ini.

---

# **Business Simulation**
---

**Gambar 2. Simulation Business**

<p align="center">
  <img src="https://drive.google.com/uc?export=view&id=1Z4POFLq_GT46UUpprPfrmc_pDL24fP_r" alt="Deskripsi Gambar">
</p>

### **Conclusion**

Kesimpulan ini menunjukkan bahwa penggunaan model machine learning (ML) tidak hanya memenuhi target yang ditetapkan, tetapi juga melebihi ekspektasi. Dengan optimasi 100% dalam penghematan biaya dibandingkan dengan skenario baseline, terlihat jelas bahwa model ML dapat secara signifikan meningkatkan efisiensi operasional. Selain itu, peningkatan tingkat konversi sebesar 28,66% menunjukkan bahwa penggunaan ML dapat menarik lebih banyak pelanggan dengan biaya yang lebih rendah.

Pengurangan biaya akuisisi nasabah sebesar 78,34% dibandingkan dengan metode baseline memperkuat bukti bahwa strategi berbasis machine learning jauh lebih efektif dalam mendapatkan nasabah baru. Skenario baseline menunjukkan kerugian, sementara penerapan machine learning berhasil mencatatkan peningkatan sebesar 112%. Hal ini menunjukkan potensi besar dari teknologi ML dalam meningkatkan kinerja bisnis dan mencapai hasil yang lebih baik dari yang ditargetkan.

Jika ingin melihat perhitungan dengan detail dan lebih jelas akses **[SpreedSheet](https://docs.google.com/spreadsheets/d/1ZVc7tCzEfSmsqYxFG-VR-BgNx5eoxaik3ZmFWb-uXJQ/edit?usp=sharing)** pada sheet **"Final Result (English Version)"**

---

# **Deployment**
---

Untuk deployment model machine learning, dilakukan dengan menyimpan model yang telah dilatih dalam bentuk objek biner. Metode ini sangat cocok karena memungkinkan penggunaan langsung model untuk prediksi tanpa perlu proses pelatihan ulang, sehingga menghemat waktu dan sumber daya. Penyimpanan dalam format objek biner juga memastikan bahwa semua komponen penting, seperti encoder target dan urutan encoding, disimpan dalam satu file. Hal ini membuat manajemen model menjadi lebih mudah dan terstruktur.

**Latency dan Proses Batch**

Penggunaan pendekatan batch processing yang periodik dapat membantu mengelola latency. Pendekatan ini cocok untuk situasi di mana prediksi tidak perlu dilakukan secara real-time, tetapi dapat dilakukan dalam interval waktu tertentu. Dengan cara ini, sejumlah data dapat diproses sekaligus, mengurangi beban server, dan memaksimalkan efisiensi.

Namun, untuk menyediakan akses prediksi secara langsung melalui web, penggunaan Flask dapat diimplementasikan. Flask memungkinkan pembangunan antarmuka web yang memungkinkan pengguna untuk melakukan prediksi secara interaktif.

Sebelum melakukan deployment, langkah pertama yang perlu dilakukan adalah menyimpan model dengan kode berikut:

```python
# Combine all elements into a single dictionary
saved_objects = {
    'model': best_xgb2,
    'target_encoder': target_encoder,
    'encoding_order': encoding_order
}

# Save everything into a single pickle file
with open("model_deposito_all_in_one.pkl", "wb") as f:
    pickle.dump(saved_objects, f)

print("The model, target encoder, and encoding order have been saved in a single file 'model_deposito_all_in_one.pkl'")
```

*Penting untuk menyimpan juga label encoding agar saat melakukan prediksi di masa depan, model dapat mengonversi data input ke dalam format yang sesuai secara otomatis. Dengan menyertakan encoder target dan urutan encoding, semua langkah yang diperlukan untuk memproses data dapat dilakukan tanpa perlu intervensi manual, sehingga meningkatkan efisiensi dan konsistensi.*

<br>

Setelah model disimpan, model, encoder, dan urutan encoding dapat dimuat kembali menggunakan kode berikut:

```python
# Load the model, encoder, and encoding order from the saved file
with open("model_deposito_all_in_one.pkl", "rb") as file:
    loaded_objects = pickle.load(file)

# Extract the model, target encoder, and encoding order
model = loaded_objects['model']
target_encoder = loaded_objects['target_encoder']
encoding_order = loaded_objects['encoding_order']
```

**Struktur Proyek Deployment**

Setelah mempersiapkan model, struktur proyek untuk deployment menggunakan Flask dilakukan pada app VSCode yang dapat diorganisasikan sebagai berikut:

```
Your project name/
│
├── Deployment
│   ├── .venv
│   ├── app.py
│   ├── model_deposito_all_in_one.pkl
│   ├── templates/
│   │   ├── index.html
│   │   └── predict.html
│   └── static/
│       └── style.css
```

- **app.py**: File utama yang berisi kode Flask untuk menjalankan aplikasi web.
- **model_deposito_all_in_one.pkl**: File pickle yang menyimpan model, target encoder, dan urutan encoding, yang memungkinkan aplikasi untuk melakukan prediksi berdasarkan input pengguna.
- **templates/**: Folder yang menyimpan file HTML untuk antarmuka pengguna.
  - **index.html**: Halaman utama untuk pengguna.
  - **predict.html**: Halaman untuk menampilkan hasil prediksi.
- **static/**: Folder yang menyimpan file statis seperti CSS untuk styling.
  - **style.css**: File CSS untuk mengatur tampilan antarmuka pengguna.


Ini adalah gambaran dari web yang telah dibuat. Meskipun ini tidak dapat ditampilkan melalui link karena belum dihosting, Anda bisa mencoba semua kode yang tersedia untuk menjalankannya di lingkungan lokal Anda.

**Gambar 3. Tampilan Web**

<p align="center">
  <img src="https://drive.google.com/uc?export=view&id=1jah-UkzulTLss4gnhCrwH925Coq6zBr7" alt="Deskripsi Gambar">
</p>

<br>

**Gambar 4. Tampilan web untuk prediction Result**

<p align="center">
  <img src="https://drive.google.com/uc?export=view&id=1W5mukAVkk164SC-0yvxyOnf4zruYXKwW" alt="Deskripsi Gambar" >
</p>


Web ini memungkinkan pengguna untuk melakukan prediksi dengan cara mengisi variabel secara manual. Setelah variabel diisi, data akan otomatis melalui proses encoding karena model dan pengaturan encoding telah disimpan sebelumnya. Untuk mempermudah, juga disediakan opsi untuk mengunggah file CSV. Setelah proses prediksi selesai, hasilnya akan ditampilkan dengan label "Yes" atau "No". Jika pengguna mengunggah file CSV, hasil prediksi akan ditampilkan dalam bentuk tabel yang berisi variabel input beserta hasil prediksinya.

---

# **Limitation**
---

Meskipun semua langkah telah dilakukan dan aplikasi berjalan di lokal, hosting di server masih menjadi tantangan yang perlu diatasi agar aplikasi dapat diakses oleh pengguna secara luas. Selain itu, untuk mendukung latensi proses batch, penggunaan Airflow sebagai orkestrator juga menjadi sebuah limitasi yang perlu dilanjutkan pada project selanjutnya.

---

References
---

Link berupa paper ilmiah sebagai penunjang argumentasi yang dikemukakan dapat diakses **[di sini](https://drive.google.com/drive/folders/1WTW2cw4IhWioQx2NVF49ariBLobvS-4-?usp=sharing)**

