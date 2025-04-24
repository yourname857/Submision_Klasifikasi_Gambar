# Klasifikasi Gambar Sayuran Menggunakan CNN

Proyek ini merupakan implementasi klasifikasi gambar menggunakan model Convolutional Neural Network (CNN) untuk mengenali jenis-jenis sayuran. Dataset yang digunakan berisi gambar-gambar sayuran dengan label yang berasal dari nama folder masing-masing.

---

## Struktur Direktori

```
VegetableClassifier/
│
├── hasil_split/            # File CSV hasil pembagian data
├── saved_model/            # Model dalam format SavedModel
├── tfjs_model/             # Model dalam format TensorFlow.js
├── model.tflite            # Model dalam format TensorFlow Lite
├── best_model.h5           # Model terbaik disimpan sebagai HDF5
├── requirements.txt        # Daftar pustaka yang dibutuhkan
├── notebook.ipynb          # Notebook utama proyek
└── README.md               # Penjelasan proyek ini
```

---

## Tools

- Python 3
- TensorFlow dan Keras
- Pandas, NumPy, Matplotlib
- Google Colab

---

## Alur Kerja

1. **Persiapan Data**

   - Membaca gambar dari direktori
   - Membuat DataFrame berisi path, nama file, dan label
   - Memisahkan data menjadi Train, Validasi, dan Test

2. **Augmentasi Data**

   - Normalisasi (rescale)
   - Rotasi, zoom, dan flipping horizontal

3. **Pembangunan Model CNN**

   - Terdiri dari 3 blok Conv2D dan MaxPooling
   - Fully connected layer dengan dropout
   - Softmax untuk klasifikasi multi-kelas

4. **Pelatihan dan Validasi**

   - Menggunakan optimizer Adam
   - Loss function: categorical crossentropy
   - EarlyStopping dan ModelCheckpoint untuk mencegah overfitting

5. **Evaluasi & Visualisasi**

   - Grafik akurasi dan loss untuk data pelatihan dan validasi

6. **Penyimpanan Model**
   - Disimpan dalam format: `.h5`, `SavedModel`, `.tflite`, dan `tfjs`

---

## Hasil Pelatihan

Model berhasil mencapai akurasi validasi dan pengujian lebih dari 85%, tergantung pada konfigurasi pelatihan dan jumlah data.

---

## Cara Menjalankan

1. Upload seluruh folder ke Google Colab
2. Jalankan setiap sel pada `notebook.ipynb`
3. Pastikan struktur folder dataset sesuai: `dataset/nama_kelas/nama_gambar.jpg`
4. Model yang sudah dilatih akan otomatis tersimpan di berbagai format

---

## Output Akhir

- `best_model.h5`: Model terbaik selama pelatihan
- `saved_model/`: Direktori model untuk deployment
- `model.tflite`: Model ringan untuk mobile
- `tfjs_model/`: Model siap pakai di web browser

---
