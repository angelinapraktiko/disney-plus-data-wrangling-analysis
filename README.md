# disney-plus-data-wrangling-analysis
Proses data wrangling dan eksplorasi data (EDA) pada dataset Disney+ menggunakan Python.

---

## Deskripsi
Project ini merupakan proses end-to-end data wrangling pada dataset Disney+ yang mencakup tahap eksplorasi data (EDA), pembersihan data, transformasi, feature engineering, hingga analisis tren.

---

## Tujuan
- Memahami karakteristik dataset Disney+
- Membersihkan dan mempersiapkan data untuk analisis
- Menghasilkan insight terkait distribusi konten

---

## Tahapan Analisis

### 1. Exploratory Data Analysis (EDA)
- Dataset terdiri dari 1450 data dan 12 kolom
- Tidak ditemukan data duplikat
- Ditemukan missing values pada kolom:
  - director (~32%)
  - cast (~13%)
  - country (~15%)

**Insight:**
- Konten didominasi oleh **Movie (~72%)**
- Mayoritas konten berasal dari **United States (~69%)**
- Genre dominan: **Animation, Family, Comedy**
- Rating didominasi konten **ramah keluarga**


### 2. Data Cleaning
- Missing value pada `director`, `cast`, `country` diisi dengan label khusus
- `date_added` dikonversi ke datetime dan diisi dengan forward/backward fill
- `duration_minutes` diisi menggunakan median
- `rating` dikonversi ke numerik



### 3. Data Transformation
- Standardisasi (Z-score) pada rating
- Normalisasi Min-Max pada:
  - rating
  - release_year
- Encoding:
  - Label Encoding (`type`, `rating`)
  - One-hot encoding (`country`, `genre`)



### 4. Feature Engineering
Membuat fitur baru:
- `is_kids` → mengidentifikasi konten untuk anak berdasarkan genre & rating



### 5. Data Joining
- Self-join berdasarkan `director`
- Menghubungkan film dengan sutradara yang sama



### 6. Resampling Analysis
- Analisis jumlah konten per bulan
- Ditemukan lonjakan besar pada **November 2019**
- Film menjadi kontributor utama



## Insight Keseluruhan
- Disney+ sangat fokus pada konten film dibandingkan serial
- Konten didominasi oleh produksi Amerika Serikat
- Strategi rilis menunjukkan adanya penambahan massal konten di waktu tertentu
- Konten cenderung family-friendly

---

## Tools yang Digunakan
- Python
- Pandas
- NumPy
- Matplotlib & Seaborn
- Scikit-learn

