# Credit Default Prediction - Rakamin x Home Credit Indonesia

**Final Task - Home Credit Scorecard Model**
Repositori ini berisi proyek machine learning prediktif yang bertujuan untuk memprediksi risiko gagal bayar nasabah Home Credit. Fokusnya adalah menganalisis data alternatif seperti data demografi, riwayat pinjaman, dan pola pembayaran untuk mengidentifikasi calon peminjam yang berpotensi mengalami kesulitan pembayaran.

Tahapan umum pada project ini mencakup beberapa bagian utama, yaitu sebagai berikut.
1. Pemrosesan data: proses pembersihan, penggabungan, dan transformasi data mentah agar siap digunakan untuk pemodelan.
2. Eksplorasi dan visualisasi: analisis statistik dan visual untuk memahami distribusi data serta hubungan antar fitur.
3. Pelatihan model: eksperimen dengan algoritma machine learning berupa logistic regression, random forest, dan gradient boosting untuk memprediksi risiko gagal bayar.
4. Prediksi: proses akhir untuk menghasilkan skor risiko atau credit scorecard dari data baru.

## Data
Data yang digunakan dalam proyek ini berasal dari Program Virtual Internship Rakamin x Home Credit Indonesia. Dataset disediakan untuk tujuan pembelajaran dalam analisis data dan pengembangan model machine learning untuk prediksi risiko gagal bayar pada nasabah.
Dataset terdiri dari beberapa file yang merepresentasikan berbagai aspek profil dan perilaku pelanggan, yaitu sebagai berikut.
1. `application_train.csv`
2. `application_test.csv`
3. `bureau.csv`
4. `bureau_balance.csv`
5. `previous_application.csv`
6. `POS_CASH_balance.csv`
7. `credit_card_balance.csv`
8. `installments_payments.csv`
9. `HomeCredit_columns_description.csv`
10. `sample_submission.csv`

## Alur Project dan Penjelasan Notebook
Proyek ini bertujuan untuk membangun model machine learning prediktif yang dapat memprediksi potensi nasabah mengalami kesulitan pembayaran pinjaman (credit risk prediction). Seluruh proses dilakukan melalui empat notebook utama yang dijalankan secara berurutan.


**`data_processing.ipynb` (Pemrosesan Data)**
Notebook ini merupakan tahap awal untuk menyiapkan data agar siap digunakan dalam proses analisis dan pelatihan model. Beberapa langkah penting yang dilakukan di sini meliputi:
1. Membaca berbagai file data dari program Virtual Internship Rakamin x Home Credit Indonesia.
2. Melakukan data cleaning seperti menghapus nilai kosong, menyesuaikan tipe data, dan menggabungkan beberapa tabel penting (misalnya data nasabah, riwayat pinjaman, dan pembayaran).
3. Melakukan feature engineering sederhana, seperti pembuatan fitur baru berdasarkan rasio pendapatan dan pinjaman.
4. Menyimpan hasil pemrosesan dalam bentuk dataset bersih yang siap digunakan pada tahap pelatihan model.
Melalui proses ini akan dihasilkan data dalam format csv yang akan disimpan ke dalam folder `data/dataset_hasil_data_processing/`.


**`data_visualitation.ipynb` (Eksplorasi dan Visualisasi Data)**
Notebook ini digunakan untuk memahami pola dan karakteristik data melalui proses visualisasi. Langkah-langkah utamanya antara lain sebagai berikut:
1. Analisis distribusi variabel utama seperti pendapatan, umur, dan jumlah pinjaman.
2. Pembuatan grafik hubungan antara variabel independen dan target.
3. Visualisasi korelasi antar fitur untuk menemukan hubungan penting dalam prediksi risiko.
Output utama dari proses ini meliputi grafik dan visualisasi yang menunjukkan tren dan insight dari data yang disimpan dalam folder `outputs/hasil_visualisasi/`


**`trains.ipynb` (Pelatihan Model)**
Notebook ini berisi proses membangun model machine learning yang terdiri dari model Logistic Regression, Random Forest, dan Gradient Boosting. Tahapan utamanya meliputi hal seperti berikut.
1. Memuat data yang telah diproses dari tahap sebelumnya.
2. Membagi data menjadi train dan test set.
3. Melatih model prediktif
4. Mengevaluasi kinerja model menggunakan metrik seperti akurasi, AUC-ROC, dan F1-score.
5. Menyimpan model terbaik untuk digunakan di tahap prediksi.
Melalui Tahapan ini dihasilkan model terlatih dan file laporan evaluasi model yang disimpan di folder `outputs/models/`


**`prediksi.ipynb` (Prediksi)**
Notebook terakhir digunakan untuk menghasilkan prediksi berdasarkan model yang sudah dilatih, prosesnya meliputi:
1. Memuat model terlatih dari tahap sebelumnya.
2. Menggunakan data uji `application_test.csv` untuk menghasilkan prediksi probabilitas terkait risiko gagal bayar.
3. Menyimpan hasil prediksi pada folder `outputs/hasil_prediksi/`
4. Menyimpan rekapan dan grafik dari hasil prediksi

## Struktur Project yang Disarankan
```
home_credit_scorecard_model/
├─ data/
│  ├─ dataset_awal/                  
│  └─ dataset_hasil_data_processing/
│
├─ data_processing_dan_visualitation/
│  ├─ data_processing.ipynb
│  └─ data_visualitation.ipynb
│
├─ trains.ipynb                                          
│
├─ outputs/
│  ├─ hasil_visualisasi/
│  ├─ preprocessing/
│  ├─ models/
│  │   ├─ logistic_regression/
│  │   ├─ random_forest/
│  │   └─ gradient_boosting/
│  └─ hasil_prediksi/
│
└─ prediksi.ipynb
```

## Hasil Evaluasi
Berikut hasil evaluasi yang telah dilakukan pada model dengan menggunakan metrik Recall, Precision, F1-Score, ROC-AUC, dan Average Precision.

| Model                   |   Recall  | Precision | F1-score |  ROC-AUC  | Avg. Precision | Threshold |
| ----------------------- | :-------: | :-------: | :------: | :-------: | :------------: | :-------: |
| **Logistic Regression** |   0.687   |   0.148   |**0.244** | **0.727** |    **0.203**   |   0.489   |
| **Random Forest**       | **0.726** |   0.136   |   0.229  |   0.714   |      0.185     |   0.441   |
| **Gradient Boosting**   |   0.676   | **0.147** |   0.241  |   0.722   |      0.196     |   0.440   |
