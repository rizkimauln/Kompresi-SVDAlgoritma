# Praktikum Kompresi Gambar Lossy (SVD) & Lossless (WebP)

Repositori ini memuat implementasi tugas praktikum kelompok mengenai kompresi citra digital menggunakan pendekatan *Lossy* dan *Lossless*. Algoritma ini ditulis menggunakan bahasa pemrograman Python dalam format Jupyter Notebook.

## Deskripsi Tugas
1. **Algoritma yang Digunakan**: 
   - **Lossy**: Singular Value Decomposition (SVD).
   - **Lossless**: WebP Lossless Encoding.
2. **Data Uji**: Minimal 20 gambar dengan format ekstensi `.webp`.
3. **Luaran (Output)**: Evaluasi performa kompresi menggunakan metrik *Mean Squared Error* (MSE), *Peak Signal-to-Noise Ratio* (PSNR), perbandingan ukuran file, serta visualisasi perbandingan citra.

## Prasyarat (Dependencies)
Pastikan *environment* Python Anda telah terinstal *library* berikut sebelum menjalankan kode:
- `numpy` (Komputasi matriks SVD)
- `Pillow` / `PIL` (Pemrosesan file citra)
- `matplotlib` (Visualisasi data dan gambar)
- `pandas` (Pembuatan tabel laporan evaluasi)

Jika belum, Anda dapat menginstalnya menggunakan *Command Prompt* atau Terminal dengan perintah:
```bash
pip install numpy Pillow matplotlib pandas
```

## Struktur Direktori
Pastikan struktur folder pada *workspace* Anda menyerupai format berikut agar program berjalan lancar:
```text
Compresi/
├── Kompresi_SVD_WebP.ipynb   # File utama kode Python
├── data_uji/                 # Direktori untuk meletakkan 20+ gambar asli (.webp)
├── hasil_kompresi/           # Direktori keluaran gambar setelah dikompresi (Otomatis dibuat)
└── README.md                 # Dokumentasi panduan proyek
```

## Panduan Penggunaan
1. Buat folder baru bernama `data_uji` pada folder yang sama dengan file `Kompresi_SVD_WebP.ipynb`.
2. Masukkan minimal 20 buah file gambar berekstensi `.webp` ke dalam folder `data_uji` tersebut.
3. Buka file `Kompresi_SVD_WebP.ipynb` menggunakan Jupyter Notebook, JupyterLab, atau Visual Studio Code.
4. Jalankan (*Run All*) seluruh sel kode dari atas hingga bawah.
5. Hasil proses akan secara otomatis tersimpan di dalam folder `hasil_kompresi`. 
6. Tabel evaluasi metrik (MSE, PSNR, ukuran file) akan muncul di sel bagian akhir evaluasi beserta sampel perbandingan visualnya.

## Tinjauan Metodologi
- **Singular Value Decomposition (Lossy)**: Memecah matriks setiap *channel* warna citra RGB dan membuang sebagian nilai komponen matriks yang kurang dominan. Bertujuan untuk mereduksi ukuran file secara signifikan dengan menukarkan sedikit penurunan kualitas pada ketajaman visual.
- **WebP (Lossless)**: Mengemas ulang struktur data citra (*encoding*) secara efisien sehingga menghemat alokasi *byte* file gambar, namun memastikan detail susunan piksel tetap dipertahankan 100% identik dengan orisinalnya (selalu menghasilkan nilai MSE = 0).
