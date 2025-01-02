# Spotify Genre Data Analysis

## 📖 Pendahuluan  
Spotify menghadapi tantangan dalam mempertahankan engagement pengguna akibat kesulitan memberikan rekomendasi musik yang tepat sesuai preferensi individu. Masalah ini penting karena pengalaman mendengarkan yang personal dan relevan dapat meningkatkan loyalitas pengguna serta memaksimalkan waktu yang dihabiskan di platform. Dengan demikian, analisis data ini bertujuan untuk memberikan wawasan yang mendalam terkait preferensi musik pengguna.

## 🛠️ Rencana dan Pendekatan  
Kami menggunakan dataset open source dari [Github](https://github.com/rfordatascience/tidytuesday/blob/main/data/2020/2020-01-21/readme.md) yang mencakup metadata lagu Spotify, seperti:  
- **Karakteristik audio** (*danceability*, *energy*, *tempo*, *valence*).  
- **Genre playlist** dan tingkat popularitas.  
- **Durasi lagu** dan struktur tonal (*key* dan *mode*).  

### **Metodologi**  
- **Pembersihan Data**: Mengatasi kekosongan data dengan nilai default.  
- **Eksplorasi Data Awal (EDA)**: Menggali pola perilaku pengguna dengan statistik deskriptif.  
- **Visualisasi Data**: Membantu memahami hubungan antar variabel secara intuitif.

## 🔍 Teknik Analisis yang Digunakan
**!!Kami Belum Melakukan Evaluasi Model maupun Eksperimen Model, Projek ini dilakukan sebagai bentuk tanjung jawab terhadap kami sebagai mahasiswa informatika mata kuliah analisis bigdata!!**  
1. **Penambahan Fitur Baru**:  
   - *Energy Acoustic Ratio*: Rasio dominasi energi terhadap elemen akustik.  
   - *Energy Efficiency*: Efisiensi energi berdasarkan karakteristik musikal.  
   - *TEMPO CATEGORY*: Kategori berdasarkan tempo musik.  
2. **Klasifikasi Tempo Lagu**:  
   Lagu dikategorikan berdasarkan kecepatan menjadi *Fast*, *Moderate*, dan *Slow*.  
3. **Analisis Popularitas**:  
   Hubungan antara genre playlist dan skor popularitas disajikan melalui heatmap, scatter plot, dan boxplot.  

## 🌟 Manfaat Analisis  
Hasil analisis ini diharapkan dapat:  
- Mengoptimalkan algoritma rekomendasi musik Spotify.  
- Memberikan pengalaman mendengarkan yang lebih personal dan relevan bagi pengguna.  
- Membantu tim produk Spotify meningkatkan engagement platform.  

Dengan analisis ini, Spotify dapat lebih memahami kebutuhan pengguna dan menciptakan pengalaman mendengarkan yang menarik dan memuaskan.

## 📂 Struktur Proyek  
- **Dataset**: `spotify_songs.csv` (Metadata lagu Spotify).  
- **Kode Analisis**: `spotify.ipynb`.  
- **Visualisasi**: Disimpan di folder `asset/`.  

## 📂 Library
1. **gdown**:  
   *Mengunduh data dari Google Drive.*
2. **pandas (pd)**: *Library utama yang digunakan untuk manipulasi dan analisis data dalam bentuk tabel (DataFrame).*
3. **matplotlib (plt)**: *Library visualisasi data yang digunakan untuk membuat grafik dan plot.*
4. **seaborn (sns)**: *Dibangun di atas matplotlib dan menyediakan cara yang lebih mudah dan lebih estetik.*  

## 🧹 Data Preparation  
Sumber dataset berasal dari [Github](https://github.com/rfordatascience/tidytuesday/blob/main/data/2020/2020-01-21/readme.md). Dataset ini berupa data tabular yang berisi metadata lagu-lagu Spotify, dirilis pada 2 Januari 2020. Dataset terdiri dari **32.832 baris** dan **23 kolom** dengan tipe data:  
- **String**: 10 kolom.  
- **Numerik**:  
  - *float64*: 9 kolom.  
  - *int64*: 4 kolom.  

### **Karakteristik Data**  
1. **Karakteristik Audio**: *“danceability”*, *“energy”*, *“tempo”*, dan *“valence”* sebagai metrik numerik.  
2. **Durasi Lagu**: *“duration_ms”*, mengukur panjang lagu.  
3. **Struktur Tonal**: *“key”* (nada dasar) dan *“mode”* (mayor/minor).  
4. **Genre yang Tercakup**: Pop, Latin, Rap, Rock, R&B, dan EDM dengan tingkat popularitas yang seimbang.  

### **Proses Cleaning Data**  
#### 1. Mengatasi Kekosongan Data  
Dataset memiliki kekosongan data pada kolom `track_name`, `track_artist`, dan `track_album_name` (5 baris). Kekosongan diatasi dengan:  
- **String**: Diimput nilai "Unknown".  
- **Numerik**: Diimput nilai `0`.  

#### 2. Membersihkan Angka, Karakter, dan Simbol Khusus  
Pada kolom `track_name`, dilakukan pembersihan angka, karakter, dan simbol khusus untuk memastikan data lebih konsisten dan siap dianalisis. Proses ini menggunakan pendekatan regex (*regular expressions*), seperti:  
- Menghapus angka: `\d+`  
- Menghapus simbol khusus: `[^\w\s]`  
- Menjaga huruf dan spasi saja: `[a-zA-Z\s]`  

#### Tabel Before dan After Cleaning  
| **ID** | **Track ID**          | **Track Name** | **Track Artist** | **Track Album Name** | **Duration_Ms** | **DateAdded** |  
|--------|------------------------|----------------|------------------|----------------------|--------------|----------------|  
| 8151   | 69gRFGOWY9OMpFJgFol1u0 | NaN            | NaN              | NaN                  | 0            | 2012-01-05     |  
| ...    | ...                    | NaN            | NaN              | NaN                  | ...          | ...            |  

*Setelah Cleaning*:  

| **ID** | **Track ID**          | **Track Name** | **Track Artist** | **Track Album Name** | **Duration_Ms** | **DateAdded** |  
|--------|------------------------|----------------|------------------|----------------------|--------------|----------------|  
| 8151   | 69gRFGOWY9OMpFJgFol1u0 | Unknown        | Unknown          | Unknown              | 0            | 2012-01-05     |  
| ...    | ...                    | Unknown        | Unknown          | Unknown              | ...          | ...            |

Selain itu, dilakukan pembersihan terhadap simbol atau karakter tertentu yang memengaruhi kualitas data. Proses ini memastikan data siap untuk analisis lebih lanjut.


## 🤝 Kontribusi  
Kami selalu terbuka untuk saran dan kolaborasi. Jangan ragu untuk membuka *issue* atau *pull request*.  

---

**Dibuat oleh Tim Spotify Genre Analysis**  
**Dosen Pengampu: Yuda Munarko, S.Kom., M.Sc.**  
**Anggota Kelompok**:  
   - *Muhammad Wahyudi - 202110370311234*
   - *Abd. Baasithur Rizqu - 202110370311234*
   - *Alji Afrian - 202110370311234*