
# Penjelasan UTS

## Tahapan Penyelesaian Projek

### 1. Import Library
Pertama tama kita mengimport library yang perlu kita gunakan, yaitu cv2, matplotlib, dan numpy.
> CV2 adalah library yang digunakan untuk menganalisis dan memanipulasi citra. Matplotlib adalah library python yang digunakan untuk pembuatan plot dan visualisasi data. Numpy library dasar untuk komputasi numerik dan manipulasi array di Python.

### 2. Memanggil gambar
Menggunakan fungsi imread untuk mengimport  gambar 
### 3. Convert gambar ke rgb
Dengan menggunakan fungsi cvtColor kita mengubah format gambar dari bgr menjadi rgb. 
### 4. Mencari bentuk gambar
Dengan menggunakan shape kita akan mendapatkan nilai panjang, lebar, dan dimensi. Karena gambar ini berformat RGB, maka nilai dimensinya adalah 3. 
### 5. Menentukan baris dan kolom
    (baris, kolom) = img.shape [:2]
Mengekstrak panjang dan lebar dari gambar menjadi baris dan kolom
### 6. Memurnikan Warna

Kita melakukan segmentasi warna berdasarkan perbedaan intensitas antar kanal/channel warna. Pixel yang memiliki perbedaan intensitas yang cukup besar dengan kanal lainnya akan menjadi warna dominan, sedangkan kanal lainnya ditekan menjadi hitam (nilai 0).

Efek yang dihasilkan kode ini bergantung pada nilai ambang batas perbedaan (pada kode ini niali ambang batasnya adalah 10) dan karakteristik gambar asli.
### 7. Menampilkan Histogram
Kita akan menampilkan histogram dari kanal merah, hijau, dan biru. Ketika kita mengambil kanal merah, maka warna merah yang ada di citra menjadi hilang. Untuk mengambilnya kita mengubah nilai dimensi yang didapat dari shape. 
>Nilai indeks:
>* 0 = merah
>* 1 = hijau
>* 2 = biru

untuk mengekstraksi kanal warna kita menggunakan slicing [:,:,0]. Ini berarti kita mengambil semua baris dan kolom, tetapi hanya saluran warna merah(indeks 0). nilai indeks dapat diubah dengan ketentuan diatas.


dari tiga histogram yang kita miliki kita dapat melihat bahwa ada peningkatan bertahap dalam frekuensi dari awal sumbu x hingga sekitar nilai 150, di mana frekuensi mulai meningkat tajam. Frekuensi tertinggi terjadi pada sekitar nilai 200 di sumbu x, setelah itu frekuensi turun tajam.

### 8. Menentukan nilai ambang batas
kita akan mengkonvert gambar dari RGB to GRAY. setelah menyiapkan plotnya, kita akan melakukan thresholding pada gambar grayscale. Kemudian hasil gambarnya ditampilan pada sublot yang berbeda

## Teori Pendukung 
### Pendeteksian warna pada citra
Pendeteksian warna di citra merupakan suatu proses komputasional yang penting dalam pengolahan gambar dan pengenalan pola. Ada beberapa teori dan metode yang mendukung pendeteksian warna di citra, di antaranya:

>*  Model Warna: Model warna seperti RGB (Red, Green, Blue), HSV (Hue, Saturation, Value), atau Lab (Luminance, a and b color opponents) digunakan untuk merepresentasikan warna dalam citra. Pada model-model ini, setiap warna direpresentasikan sebagai kombinasi dari komponen warna dasar atau dimensi yang berbeda.

>* Segmentasi Warna: Metode segmentasi digunakan untuk memisahkan wilayah-wilayah dengan warna yang berbeda dalam citra. Salah satu pendekatan yang umum adalah menggunakan kriteria pada ruang warna tertentu (misalnya, HSV) untuk mengidentifikasi dan memisahkan piksel-piksel dengan warna yang serupa ke dalam kelompok atau wilayah yang berbeda.

>* Histogram Warna: Histogram warna dapat digunakan untuk menganalisis distribusi warna dalam citra. Histogram warna memperlihatkan sebaran intensitas piksel berdasarkan nilai warna tertentu. Analisis histogram warna dapat membantu dalam mengidentifikasi warna dominan atau pola warna tertentu dalam citra.
