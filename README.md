# Tugas Analisis Statistik: Deskriptif, Korelasi, dan Regresi

## 1. Informasi Penyusun

- **Nama:** IYAD IMANULLAH
- **NIM:** 2515091090
- **Program Studi:** `SISTEM INFORMASI
- **Mata Kuliah:** Statistika dan Probabilitas

---

## 2. Deskripsi Proyek

Pada bagian ini, jelaskan secara singkat dataset yang Anda gunakan. Apa saja variabel di dalamnya? Apa tujuan dari analisis yang Anda lakukan?

*Contoh:*
> Dataset yang digunakan adalah data `data_startup_saas.csv` yang berisi informasi tentang `berbagai startup SaaS yang meliputi identitas startup, jenis layanan yang disediakan, besaran pendapatan tahunan dalam miliar rupiah, biaya berlangganan dalam satuan juta rupiah, nilai pelanggan selama masa penggunaan layanan, serta persentase churn pelanggan, yang secara keseluruhan dapat dimanfaatkan untuk menilai performa bisnis dan perilaku pelanggan.`. Variabel kunci dalam dataset ini meliputi `Pendapatan_Tahunan_Miliar_IDR`, `Biaya_Akuisisi_Pelanggan_Juta_IDR`, dan `NIlai_Pelanggan_Juta_IDR`. Tujuan dari proyek ini adalah untuk memahami karakteristik data melalui statistik deskriptif, menguji hubungan antara `Pendapatan_Tahunan_Miliar_IDR` dan `Biaya_Akuisisi_Pelanggan_Juta_IDR` melalui analisis korelasi, serta memprediksi `NIlai_Pelanggan_Juta_IDR` menggunakan `Pendapatan_Tahunan_Miliar_IDR` sebagai prediktor melalui analisis regresi.

---

## 3. Struktur Proyek

Proyek ini diorganisir ke dalam beberapa folder:
- `/data`: Berisi dataset mentah yang digunakan untuk analisis.
- `/scripts`: Berisi semua skrip R yang digunakan dalam analisis, diurutkan berdasarkan alur kerja.
- `/results`: Berisi output dari analisis, seperti plot, gambar, atau tabel ringkasan.

---

## 4. Cara Menjalankan Analisis

Untuk mereproduksi hasil analisis ini, ikuti langkah-langkah berikut:
1. Pastikan Anda memiliki R dan RStudio terinstal.
2. Buka proyek R ini di RStudio.
3. Instal paket yang diperlukan dengan menjalankan perintah berikut di konsol R:
   ```R
   # install.packages(c("tidyverse", "corrplot", "knitr"))
   ```
4. Jalankan skrip di dalam folder `/scripts` secara berurutan, mulai dari `01_data_preparation.R` hingga `05_analisis_regresi.R`.

---

## 5. Hasil dan Interpretasi

Di bagian ini, mahasiswa diharapkan untuk menyajikan dan menginterpretasikan hasil dari setiap tahap analisis.

### 5.1. Statistik Deskriptif
- **Ukuran Pemusatan (Mean, Median, Modus):**
  - *Tabel atau ringkasan...*
  - dari variable yang saya analisa yaitu Biaya_Akuisisi_Pelanggan_Juta_IDR saya mendapatkan :
    1. Mean = 33.4985230769231
    2. Median = 33.075
    3. modus = 3.21
  - *Interpretasi:* Jelaskan apa arti dari nilai-nilai tersebut terkait dengan data Anda.
  - mean sebesar 33,50 juta rupiah menunjukkan bahwa biaya yang dikeluarkan startup untuk memperoleh pelanggan umumnya berada di sekitar angka tersebut. Median yang bernilai 33,08 juta rupiah dan hampir sama dengan mean menandakan bahwa distribusi data cukup seimbang dan tidak terlalu dipengaruhi oleh nilai yang sangat tinggi atau rendah. Sementara itu, modus sebesar 3,21 juta rupiah menunjukkan bahwa biaya akuisisi pelanggan yang paling sering muncul justru relatif kecil, sehingga dapat disimpulkan bahwa ada sebagian startup yang mampu mendapatkan pelanggan dengan biaya rendah, namun keberadaan startup dengan biaya akuisisi tinggi ikut mendorong nilai rata-rata menjadi lebih besar.
- **Ukuran Sebaran (Standar Deviasi, Range, Kuartil):**
  - *Tabel atau ringkasan...*
  - dari variable yang saya analisa yaitu Biaya_Akuisisi_Pelanggan_Juta_IDR saya mendapatkan :
  - Standar Deviasi = 20.0276791663993
  - Range = 2.56 - 68.77
  - Kuartil =  Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
               2.56   15.23   33.08   33.50   50.92   68.77 
  - *Interpretasi:* Jelaskan seberapa menyebar data Anda berdasarkan nilai-nilai ini.
  - Nilai standar deviasi sebesar 20,03 juta rupiah menandakan bahwa biaya akuisisi pelanggan antar startup sangat bervariasi dan cukup jauh menyimpang dari nilai rata-ratanya. Rentang data yang luas, yaitu dari 2,56 hingga 68,77 juta rupiah, menunjukkan adanya kesenjangan yang besar antara startup dengan biaya akuisisi paling rendah dan paling tinggi. Dilihat dari kuartil, seperempat data berada di bawah 15,23 juta rupiah, setengah data terpusat di sekitar median 33,08 juta rupiah, dan tiga perempat data berada di bawah 50,92 juta rupiah. Secara keseluruhan, hal ini menggambarkan bahwa sebaran data tidak merata, dengan perbedaan biaya akuisisi yang cukup signifikan di antara startup.
- **Visualisasi (Histogram/Boxplot):**
  - *Sematkan gambar plot dari folder /results...*
  - *Interpretasi:* Jelaskan wawasan apa yang Anda dapatkan dari bentuk distribusi data.

### 5.2. Uji Normalitas
- **Hasil Uji Shapiro-Wilk:**
  - *Nilai p-value...*
  - *Interpretasi:* Apakah data Anda terdistribusi normal berdasarkan hasil uji? Apa implikasinya?
- **Plot Q-Q:**
  - *Sematkan gambar plot dari folder /results...*
    ![alt text]
  - *Interpretasi:* Apakah titik-titik data mengikuti garis lurus? Apa artinya?

### 5.3. Analisis Korelasi
- **Nilai Koefisien Korelasi:**
  - *Nilai r...*
  - *Interpretasi:* Seberapa kuat dan apa arah hubungan antara dua variabel yang Anda uji? (misalnya, korelasi positif kuat, negatif lemah, atau tidak ada korelasi).
- **Visualisasi (Scatter Plot):**
  - *Sematkan gambar plot dari folder /results...*
  - *Interpretasi:* Apakah pola pada scatter plot mendukung hasil koefisien korelasi?

### 5.4. Analisis Regresi
- **Model Regresi:**
  - *Persamaan regresi: Y = b0 + b1*X*
  - *Interpretasi:* Jelaskan arti dari koefisien intercept (b0) dan slope (b1) dalam konteks data Anda.
- **Evaluasi Model (R-squared):**
  - *Nilai R-squared...*
  - *Interpretasi:* Berapa persen variasi dari variabel dependen yang dapat dijelaskan oleh model regresi Anda?
- **Visualisasi (Garis Regresi pada Scatter Plot):**
  - *Sematkan gambar plot dari folder /results...*
  - *Interpretasi:* Jelaskan bagaimana garis regresi merepresentasikan hubungan antara variabel.

---

## 6. Kesimpulan

Rangkum temuan utama dari analisis Anda dalam beberapa kalimat. Apa wawasan paling penting yang Anda peroleh?
