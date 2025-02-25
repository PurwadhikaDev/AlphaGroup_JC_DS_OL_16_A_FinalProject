# Saudi Used Car Price Prediction

by Alpha Group:
- Ivanka Larasati
- Kenneth Aleanda
- Mochamad Dandi

**Link Streamlit**
https://finalproject-purwadhika-pcuobfkvrhf3qyffk82cnj.streamlit.app

**Link Tableau**
https://public.tableau.com/app/profile/ivanka.larasati/viz/shared/F2M7T2XTB
![Dashboard 1](https://github.com/user-attachments/assets/85381308-321a-4bc9-93a5-d508416fba8b)

## Domain Knowledge

### Context
Syarah ([syarah.com](https://syarah.com)) adalah online marketplace untuk penjualan mobil bekas di Saudi Arabia. Untuk meningkatkan revenue, platform ini akan menawarkan fitur **price suggestion** kepada seller. Fitur ini akan dapat diakses melalui **subscription** dan memungkinkan seller untuk memasukkan atribut mobil yang ingin dijual. Outputnya adalah **price range** yang direkomendasikan berdasarkan atribut tersebut.

### Stakeholder
Stakeholder utama dalam proyek ini adalah **Syarah Company** (syarah.com), sebagai marketplace online yang memfasilitasi penjualan mobil bekas di Saudi Arabia.

## Business Problem

1. **Menentukan harga kompetitif untuk mobil bekas sulit dilakukan.**
   - Banyak seller tidak memiliki pengetahuan mengenai harga pasar mobil bekas.
   - Mencari informasi harga pasar berdasarkan fitur mobil tertentu membutuhkan waktu lama.
   - Saat ini, kebanyakan orang perlu melakukan riset sendiri dengan mengecek daftar harga online, mengunjungi dealer, dan mempertimbangkan berbagai faktor seperti merk, model, tahun, jarak tempuh, dan kondisi kendaraan.

2. **Mengidentifikasi faktor yang mempengaruhi harga mobil memerlukan banyak waktu jika dilakukan manual.**
   - Mencari tahu faktor utama yang mempengaruhi harga mobil sangat memakan waktu.
   - Tidak semua seller memiliki waktu atau kemauan untuk melakukan riset tersebut.

## Goals
1. **Accurately Predict the Price of Used Cars**
   - Membuat model yang mampu memberikan estimasi harga mobil bekas dengan **MAPE 20-25%**.
2. **Understanding Key Factors**
   - Mengidentifikasi faktor utama yang mempengaruhi harga mobil bekas di marketplace.

## Business Questions
1. **Berapa prediksi harga dari sebuah mobil bekas dengan fitur tertentu?**
2. **Fitur apa yang paling berpengaruh dalam menentukan harga mobil bekas?**
3. **Bagaimana distribusi harga mobil bekas?**
4. **Apa brand mobil populer berdasarkan region?**
5. **Apa jenis mobil yang paling laku berdasarkan region?**
6. **Apa tipe transmisi dan bahan bakar yang paling populer?**
7. **Bagaimana hubungan antara mileage, umur mobil, dan popularitasnya?**

## Evaluation Metrics

### 1. Median Absolute Error (MedAE)
MedAE digunakan karena robust terhadap **outlier**, dengan rumus:
```math
MedAE = \text{median}(| y_i - \hat{y}_i |)
```

### 2. Mean Absolute Error (MAE)
MAE mengukur rata-rata selisih absolut antara nilai aktual dan prediksi, digunakan untuk menentukan range harga:
```math
MAE = \frac{1}{n} \sum_{i=1}^{n} | y_i - \hat{y}_i |
```

### 3. Mean Absolute Percentage Error (MAPE)
MAPE digunakan untuk mengukur **error rate** dalam bentuk persentase:
```math
MAPE = \frac{1}{n} \sum_{i=1}^{n} \left| \frac{y_i - \hat{y}_i}{y_i} \right| \times 100\%
```

## Project Limitations
- Dataset hanya mencakup mobil bekas dari tahun **2003 - 2021**.
- Ukuran mesin mobil yang dianalisis berkisar antara **1.0 - 8.0**.
- Mileage mobil dalam dataset berkisar antara **100 - 432000 km**.
- Harga mobil dalam dataset berkisar antara **4000 - 1150000 SAR**.
- Dataset tidak memiliki informasi populasi untuk kolom region, sehingga perlu sumber eksternal untuk klasifikasinya.
- Menggunakan **hardware machine learning** dengan spesifikasi terbatas.

## Data Features and Description

Dataset: **Saudi Arabia Used Cars Dataset**

Dataset ini terdiri dari **8035 records** yang diambil dari syarah.com. Setiap row merepresentasikan mobil bekas dengan informasi berikut:

| Column       | Data Type | Description |
|-------------|----------|-------------|
| Make        | str      | Brand mobil |
| Type        | str      | Jenis mobil |
| Year        | int      | Tahun produksi |
| Origin      | str      | Asal mobil |
| Color       | str      | Warna mobil |
| Options     | str      | Kelengkapan opsi mobil |
| Engine_Size | float    | Ukuran mesin (L) |
| Fuel_Type   | str      | Tipe bahan bakar |
| Mileage     | int      | Jarak tempuh (km) |
| Region      | str      | Wilayah tempat mobil dijual |
| Price       | int      | Harga mobil (SAR) |
| Negotiable  | bool     | Apakah harga bisa dinegosiasi |

## Summary of Findings

### 1. Accurately Predicting the Price of Used Cars
- Model terbaik untuk prediksi harga mobil bekas adalah **Tuned XGBoost Regression**.
- **MAPE model: 20,87%**.

### 2. Understanding Key Factors
#### *Top 5 Faktor yang Mempengaruhi Harga Mobil:*
1. **Engine_Size**
2. **Year**
3. **Options**
4. **Make: Mercedes**
5. **Mileage**

#### *19 Faktor yang Paling Tidak Berpengaruh:*
- Make: BYD, Cherry, FAW, Iveco, Hummer, Great Wall, GAC, Foton, Mercury, Subaru, Zhengzhou, Škoda, Maserati, Peugeot, Lifan.
- Color: Orange.
- Region: Sakaka, Wadi Dawasir, Arar.

# Car Marketplace Data Analysis

## Domain Knowledge
Understanding the factors influencing car sales, including price, brand popularity, fuel type, and other attributes, is crucial for optimizing a car marketplace platform.

## Business Problem
The goal is to improve user experience, increase engagement, and enhance conversion rates by leveraging data-driven insights to refine car listings, pricing strategies, and customer targeting.

## Goals
- Identify pricing patterns and trends.
- Optimize search filters and recommendation systems.
- Enhance customer engagement through personalized insights.
- Improve sales conversion rates.

## Business Questions
- What are the key factors affecting car pricing?
- How do different brands and car types impact demand?
- What insights can be drawn from mileage and car age?
- How can we improve customer experience through data-driven enhancements?

## Evaluation Metrics
- Click-through rate (CTR) on recommended listings.
- Conversion rate (views to purchases).
- Customer retention rate.
- Average time spent per session.

## Project Limitations
- Data might not account for regional economic factors affecting pricing.
- Limited historical data on certain car brands/models.
- Potential inconsistencies in user-inputted data.

## Data Features
- Car brand
- Model
- Year of manufacture
- Price
- Fuel type
- Mileage
- Transmission type
- Location
- Condition (New/Used)

## Summary of Findings
- Price is significantly influenced by brand reputation and mileage.
- Customers prefer automatic transmission over manual.
- Fuel efficiency is a key deciding factor for many buyers.
- Listings with detailed descriptions and multiple images have higher engagement.

## Recommendation

### **1. Data Analysis Insights**  
#### **Price Segmentation**  
- Membagi harga mobil ke dalam tiga kategori:  
  - **Budget (<60,000)**  
  - **Midrange (60,000 - 185,000)**  
  - **High-end (>185,000)**  

#### **Brand & Type Popularity**  
- Menyediakan penawaran khusus dan menampilkan brand populer berdasarkan akses regional pelanggan.  

#### **Gear Popularity**  
- Menampilkan jenis gear tertentu tergantung pada harga yang dicari pelanggan berdasarkan **price_average**.  

#### **Fuel Popularity**  
- Memberikan **badge/flair/label** pada mobil sesuai dengan jenis bahan bakarnya untuk meningkatkan transparansi bagi pelanggan.  

#### **Mileage & Age**  
- Menyoroti mobil dengan **mileage rendah** jika usianya tua, terutama jika berada di bawah **price_average** untuk meningkatkan daya tariknya.  

---

### **2. Dataset Enhancements**  
#### **Data Tambahan untuk Analisis Lebih Baik**  
- **Menambahkan dataset populasi per region** untuk mengkategorikan area (Urban, Sub-Urban, Rural).  
- **Menambahkan dataset history pencarian/query** pada platform untuk memahami pola pencarian pelanggan.  
- **Menambahkan kolom kesehatan ban** untuk memberikan informasi tambahan mengenai kondisi mobil.  
- **Menambahkan kolom riwayat servis beserta tempatnya** untuk meningkatkan transparansi kendaraan.  
- **Menambahkan kolom kondisi interior dan eksterior** sebagai faktor tambahan dalam penentuan harga.  
- **Menambahkan kolom modifikasi** untuk menampilkan perubahan yang dilakukan pada kendaraan.  

---

### **3. Business Impact & Revenue Opportunities**  
#### **Meningkatkan Revenue dengan Customer Satisfaction**  
- Fitur-fitur tambahan dapat meningkatkan pengalaman pelanggan, mempercepat transaksi, dan meningkatkan kepuasan.  

#### **Targeted Marketing & Conversion Increase**  
- Pemasaran yang lebih spesifik dapat menjangkau lebih banyak **potential customers**, sehingga meningkatkan **conversion rate**.  

#### **Specified Region Advertisement**  
- Menawarkan fitur **iklan regional** untuk penjual yang ingin mempromosikan mobilnya di wilayah tertentu.  

#### **Customer Retention Strategy**  
- **5% peningkatan dalam customer retention** dapat meningkatkan profit sebesar **25%-95%**[^1].  
- Pelanggan yang sudah ada dapat membelanjakan hingga **300% lebih banyak** dibanding pelanggan baru.  
- **Lebih hemat 5x lipat** dalam mempertahankan pelanggan lama dibandingkan mencari pelanggan baru.  

#### **New Revenue Stream - Verified Listing Service**  
- Dengan dataset tambahan, platform dapat menawarkan layanan **vehicle testing** sebelum penjualan.  
- Jika mobil lolos tes, penjual dapat mendapatkan badge seperti **"Trusted Seller"** atau **"Tested"**, meningkatkan kepercayaan pembeli dan mempercepat penjualan. 
---

Thank you.

