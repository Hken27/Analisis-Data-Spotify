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

## 🤝 Kontribusi  
Kami selalu terbuka untuk saran dan kolaborasi. Jangan ragu untuk membuka *issue* atau *pull request*.  

---

**Dibuat oleh Tim Spotify Genre Analysis**  
**Dosen Pengampu: Yuda Munarko, S.Kom., M.Sc**  
**1.   [Muhammad Wahyudi - 202110370311234]**
**2.   [Abd. Baasithur Rizqu - 2021103703112–]**
**3.   [Alji Afrian - 2021103703112–]**