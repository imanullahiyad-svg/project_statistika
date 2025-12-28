# Tugas Analisis Statistik: Deskriptif, Korelasi, dan Regresi

## 1. Informasi Penyusun

- **Nama:** IYAD IMANULLAH
- **NIM:** 2515091090
- **Program Studi:** SISTEM INFORMASI
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
    1. Mean = 33.5
    2. Median = 33.08
    3. modus = 3.21
  - *Interpretasi:* Jelaskan apa arti dari nilai-nilai tersebut terkait dengan data Anda.
  - mean sebesar 33,50 juta rupiah menunjukkan bahwa biaya yang dikeluarkan startup untuk memperoleh pelanggan umumnya berada di sekitar angka tersebut. Median yang bernilai 33,08 juta rupiah dan hampir sama dengan mean menandakan bahwa distribusi data cukup seimbang dan tidak terlalu dipengaruhi oleh nilai yang sangat tinggi atau rendah. Sementara itu, modus sebesar 3,21 juta rupiah menunjukkan bahwa biaya akuisisi pelanggan yang paling sering muncul justru relatif kecil, sehingga dapat disimpulkan bahwa ada sebagian startup yang mampu mendapatkan pelanggan dengan biaya rendah, namun keberadaan startup dengan biaya akuisisi tinggi ikut mendorong nilai rata-rata menjadi lebih besar.
- **Ukuran Sebaran (Standar Deviasi, Range, Kuartil):**
  - *Tabel atau ringkasan...*
  - dari variable yang saya analisa yaitu Biaya_Akuisisi_Pelanggan_Juta_IDR saya mendapatkan :
  - Standar Deviasi = 20.03
  - Range = 2.56 - 68.77
  - Kuartil =  Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
               2.56   15.23   33.08   33.50   50.92   68.77 
  - *Interpretasi:* Jelaskan seberapa menyebar data Anda berdasarkan nilai-nilai ini.
  - Nilai standar deviasi sebesar 20,03 juta rupiah menandakan bahwa biaya akuisisi pelanggan antar startup sangat bervariasi dan cukup jauh menyimpang dari nilai rata-ratanya. Rentang data yang luas, yaitu dari 2,56 hingga 68,77 juta rupiah, menunjukkan adanya kesenjangan yang besar antara startup dengan biaya akuisisi paling rendah dan paling tinggi. Dilihat dari kuartil, seperempat data berada di bawah 15,23 juta rupiah, setengah data terpusat di sekitar median 33,08 juta rupiah, dan tiga perempat data berada di bawah 50,92 juta rupiah. Secara keseluruhan, hal ini menggambarkan bahwa sebaran data tidak merata, dengan perbedaan biaya akuisisi yang cukup signifikan di antara startup.
- **Visualisasi (Histogram/Boxplot):**
  - *Sematkan gambar plot dari folder /results...*
    ![alt text](https://github.com/imanullahiyad-svg/project_statistika/blob/main/results/boxplot_Biaya_Akuisisi_Pelanggan_Juta_IDR.png)
  - *Interpretasi:* Jelaskan wawasan apa yang Anda dapatkan dari bentuk distribusi data.
  - Berdasarkan boxplot Biaya_Akuisisi_Pelanggan_Juta_IDR, dapat disimpulkan bahwa sebaran data cukup luas, terlihat dari rentang antar kuartil yang besar. Letak median yang relatif berada di tengah kotak menunjukkan bahwa distribusi data cenderung merata dan tidak condong ke satu arah tertentu. Whisker yang memanjang ke nilai tinggi mengindikasikan adanya startup dengan biaya akuisisi pelanggan yang jauh lebih besar dibandingkan yang lain. Tidak tampak adanya pencilan yang mencolok, sehingga seluruh nilai masih berada dalam batas yang wajar. Secara keseluruhan, visualisasi ini menggambarkan adanya variasi biaya akuisisi pelanggan yang cukup besar antar startup akibat perbedaan strategi dan efisiensi yang diterapkan.

### 5.2. Uji Normalitas
- **Hasil Uji Shapiro-Wilk:**
  - *Nilai p-value...*
  - p-value = 4.138e-15
  - *Interpretasi:* Apakah data Anda terdistribusi normal berdasarkan hasil uji? Apa implikasinya?
  - Hasil uji Shapiro–Wilk pada variabel biaya akuisisi pelanggan menunjukkan p-value sebesar 4,138 × 10⁻¹⁵, yang nilainya jauh lebih kecil dari taraf signifikansi 0,05. Hal ini mengindikasikan bahwa data tidak berdistribusi normal. Dampaknya, teknik analisis statistik yang bergantung pada asumsi normalitas menjadi kurang tepat untuk diterapkan. Oleh karena itu, analisis lanjutan sebaiknya menggunakan metode nonparametrik atau menerapkan transformasi data agar hasil yang diperoleh lebih valid.
- **Plot Q-Q:**
  - *Sematkan gambar plot dari folder /results...*
    ![alt text](https://github.com/imanullahiyad-svg/project_statistika/blob/main/results/qqplot_Biaya_Akuisisi_Pelanggan_Juta_IDR.png)
  - *Interpretasi:* Apakah titik-titik data mengikuti garis lurus? Apa artinya?
  - Dari hasil Q–Q plot, terlihat bahwa titik-titik data tidak membentuk pola garis lurus dan menyimpang dari garis diagonal normal, terutama pada bagian awal dan akhir kuantil. Pola lengkung ini menunjukkan bahwa data tidak berdistribusi normal, yang menandakan adanya ketidaksimetrian atau perbedaan pada sebaran nilai ekstrem. Dengan demikian, visualisasi ini menegaskan bahwa asumsi normalitas tidak terpenuhi dan mendukung hasil pengujian statistik sebelumnya.

### 5.3. Analisis Korelasi
- **Nilai Koefisien Korelasi:**
  - *Nilai r...*
  - Koefisien Korelasi (r) = 0.996
  - *Interpretasi:* Seberapa kuat dan apa arah hubungan antara dua variabel yang Anda uji? (misalnya, korelasi positif kuat, negatif lemah, atau tidak ada korelasi).
  - Koefisien korelasi sebesar 0,996 menandakan adanya korelasi positif yang sangat kuat antara dua variabel yang dianalisis. Hal ini menunjukkan bahwa peningkatan pada satu variabel hampir selalu diikuti oleh peningkatan pada variabel lainnya. Nilai yang sangat mendekati 1 menggambarkan tingkat hubungan yang sangat tinggi, namun hubungan tersebut tidak serta-merta menunjukkan adanya pengaruh sebab dan akibat.
- **Visualisasi (Scatter Plot):**
  - *Sematkan gambar plot dari folder /results...*
    ![alt text](https://github.com/imanullahiyad-svg/project_statistika/blob/main/results/scatterplot_Pendapatan_Tahunan_Miliar_IDR_vs_Biaya_Akuisisi_Pelanggan_Juta_IDR.png)
  - *Interpretasi:* Apakah pola pada scatter plot mendukung hasil koefisien korelasi?
  - Pola yang terlihat pada scatter plot sejalan dengan nilai koefisien korelasi yang sangat tinggi. Sebaran titik data membentuk kecenderungan garis lurus yang meningkat, menandakan adanya hubungan positif yang sangat kuat antara pendapatan tahunan dan biaya akuisisi pelanggan. Garis tren linear yang mengikuti arah titik-titik tersebut menunjukkan bahwa kenaikan pendapatan tahunan umumnya diikuti oleh peningkatan biaya akuisisi pelanggan. Oleh karena itu, tampilan grafik ini memperkuat dan mendukung hasil korelasi sebesar 0,996.

### 5.4. Analisis Regresi
- **Model Regresi:**
  - *Persamaan regresi: Y = b0 + b1*X*
    1.  Intercept (b0) = 1.37
    2.  Slope (b1) = 1.01
    3.  Y = 1.37 + 1.01*X*
  - *Interpretasi:* Jelaskan arti dari koefisien intercept (b0) dan slope (b1) dalam konteks data Anda.
  - Dalam analisis hubungan antara pendapatan tahunan (X) dan biaya akuisisi pelanggan (Y), nilai intercept (b0) sebesar 1,37 menunjukkan perkiraan biaya akuisisi pelanggan sebesar 1,37 juta rupiah ketika pendapatan tahunan berada pada nilai nol. Sementara itu, koefisien slope (b1) sebesar 1,01 mengindikasikan bahwa setiap peningkatan 1 miliar rupiah pendapatan tahunan akan diikuti oleh kenaikan biaya akuisisi pelanggan sekitar 1,01 juta rupiah. Persamaan regresi Y = 1,37 + 1,01X dengan demikian mencerminkan hubungan positif yang sangat kuat antara kedua variabel tersebut.
- **Evaluasi Model (R-squared):**
  - *Nilai R-squared...*
  - R-squared = 0.991 atau 99.1 %
  - *Interpretasi:* Berapa persen variasi dari variabel dependen yang dapat dijelaskan oleh model regresi Anda?
  - Nilai R-squared sebesar 0,991 (99,1%) menunjukkan bahwa sebagian besar variasi pada variabel dependen, yaitu biaya akuisisi pelanggan, dapat diterangkan oleh model regresi yang digunakan. Artinya, model ini mampu menjelaskan sekitar 99,1% perubahan data, sedangkan sekitar 0,9% sisanya dipengaruhi oleh faktor lain yang tidak dimasukkan ke dalam model.
- **Visualisasi (Garis Regresi pada Scatter Plot):**
  - *Sematkan gambar plot dari folder /results...*
    ![alt text](https://github.com/imanullahiyad-svg/project_statistika/blob/main/results/plot_regresi_Pendapatan_Tahunan_Miliar_IDR_vs_Biaya_Akuisisi_Pelanggan_Juta_IDR.png)
  - *Interpretasi:* Jelaskan bagaimana garis regresi merepresentasikan hubungan antara variabel.
  - Garis regresi pada grafik menunjukkan adanya hubungan linear positif yang sangat kuat antara pendapatan tahunan dan biaya akuisisi pelanggan. Kemiringan garis yang meningkat menandakan bahwa kenaikan pendapatan tahunan diikuti oleh peningkatan biaya akuisisi pelanggan. Sebaran titik data yang berada sangat dekat dengan garis regresi mengindikasikan bahwa model mampu menggambarkan hubungan kedua variabel dengan baik, sejalan dengan nilai Adjusted R-squared sebesar 0,991 yang menunjukkan tingkat kecocokan model yang sangat tinggi.
    

---

## 6. Kesimpulan

Rangkum temuan utama dari analisis Anda dalam beberapa kalimat. Apa wawasan paling penting yang Anda peroleh?
Kesimpulan yang saya peroleh ialah hasil analisis ini menunjukkan bahwa biaya untuk mendapatkan pelanggan di startup SaaS sangat beragam dan tidak selalu mengikuti pola yang rapi, karena tiap startup memiliki strategi dan tingkat efisiensi yang berbeda. Meski begitu, terlihat jelas bahwa ada hubungan yang sangat kuat antara pendapatan tahunan dan biaya akuisisi pelanggan. Startup dengan pendapatan yang lebih tinggi cenderung mengeluarkan biaya lebih besar untuk menarik pelanggan baru. Temuan ini diperkuat oleh hasil regresi yang menunjukkan bahwa hampir seluruh perubahan biaya akuisisi dapat dijelaskan oleh pendapatan tahunan, sehingga hubungan keduanya benar-benar erat dan konsisten.
