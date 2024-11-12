# Project Klasifikasi Dogs vs Cats

Project ini bertujuan untuk mengklasifikasikan gambar kucing dan anjing menggunakan teknik deep learning menggunakan model yang dibangun sendiri dan juga pre-trained model. Dataset yang digunakan berasal dari Kaggle.

## Daftar Isi
1. [Pendahuluan](#pendahuluan)  
2. [Gambaran Dataset](#gambaran-dataset)  
3. [Arsitektur Model](#arsitektur-model)  
4. [Pelatihan dan Validasi](#pelatihan-dan-validasi)  
5. [Hasil](#hasil)  
6. [Cara Penggunaan](#cara-penggunaan)  
7. [Kesimpulan](#kesimpulan)  

## Pendahuluan
Project ini menunjukkan bagaimana menggunakan *Convolutional Neural Networks* (CNN) untuk menyelesaikan masalah klasifikasi biner: membedakan gambar kucing dan anjing.

## Gambaran Dataset
- **Sumber**: Dataset *Cat vs Dog* dari Kaggle  
- **Struktur**:
  - Dataset pelatihan: Gambar yang diberi label sebagai kucing atau anjing.
  - Dataset validasi: Subset terpisah untuk evaluasi kinerja model.

## Arsitektur Model
Proyek ini menggunakan dua arsitektur model yang berbeda:

1. **Model Kustom**: Model pertama dibangun dari awal menggunakan lapisan-lapisan dasar CNN, seperti:
   - Beberapa lapisan konvolusi dan pooling untuk ekstraksi fitur.
   - Lapisan *fully connected* untuk klasifikasi.
   
   Model ini dirancang untuk memahami pola dasar dalam data tanpa menggunakan bobot yang telah dilatih sebelumnya.

2. **Model VGG16**: Model kedua menggunakan arsitektur *pre-trained* VGG16 dengan transfer learning. VGG16 merupakan model yang telah dilatih sebelumnya pada dataset ImageNet dan mampu mengenali pola yang kompleks dalam gambar. Dalam proyek ini:
   - Lapisan awal VGG16 digunakan untuk ekstraksi fitur.
   - Lapisan akhir disesuaikan (*fine-tuning*) untuk tugas klasifikasi biner (kucing vs anjing).
   
Pendekatan ini memungkinkan model untuk memanfaatkan fitur yang telah dipelajari oleh VGG16, sehingga mempercepat proses pelatihan dan meningkatkan akurasi.
biner.

### Komponen Utama:
- Input: Gambar yang diubah ukurannya menjadi \(224 \times 224\).
- Transfer Learning: Memanfaatkan bobot yang telah dilatih sebelumnya.
- Lapisan Fully Connected: Lapisan khusus untuk output biner.

## Pelatihan dan Validasi
- **Optimizer**: Adam dengan laju pembelajaran tertentu.
- **Fungsi Loss**: *Binary cross-entropy*.
- **Metrik Kinerja**: Akurasi dan loss selama pelatihan dan validasi.

## Hasil
- **Matriks Kebingungan**: Memberikan gambaran tentang *true positives*, *false positives*, *true negatives*, dan *false negatives*.
- **Kurva Akurasi dan Loss**: Visualisasi kinerja model selama beberapa epoch.

## Cara Penggunaan
Untuk mereplikasi analisis ini:
1. Clone repositori ini.
2. Unduh dataset dari [Kaggle](https://www.kaggle.com/competitions/dogs-vs-cats/rules).
3. Jalankan Jupyter Notebook: `Dogs vs Cats.ipynb`.

## Kesimpulan
Project ini menunjukkan bagaimana transfer learning dapat digunakan untuk mengklasifikasikan gambar dengan akurasi tinggi dalam membedakan kucing dan anjing.
