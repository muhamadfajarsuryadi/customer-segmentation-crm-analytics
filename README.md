# CRM Customer Lifecycle & Marketing Performance Analysis

Proyek ini berfokus pada pengolahan data pelanggan (*CRM Data*) menggunakan Python dan Power BI untuk membangun sistem segmentasi otomatis. Hasil analisis digunakan untuk menentukan prioritas tim tim *Sales*, memetakan *Customer Lifecycle*, mengidentifikasi *Churn Risk*, serta memberikan rekomendasi kampanye pemasaran dan produk yang terpersonalisasi.

---

## 🎯 Business Problem & Objectives

Pengelolaan pelanggan skala besar sering kali mengalami kendala dalam menentukan prioritas tindak lanjut dan personalisasi penawaran. Tanpa segmentasi yang terstruktur, strategi *marketing* dan *sales* menjadi tidak efisien. 

Proyek ini bertujuan untuk:
1. **Prioritisasi Lead**: Menghitung *Lead Score* untuk memilah calon pembeli potensial (*Hot Leads*) bagi tim Sales.
2. **Pemetaan Lifecycle & Churn Risk**: Mengelompokkan pelanggan berdasarkan tingkat aktivitas dan mendeteksi risiko *churn*.
3. **Personalisasi Campaign & Produk**: Menyusun aturan rekomendasi otomatis untuk kampanye *marketing* dan tawaran produk yang relevan (*upselling/cross-selling*).
4. **Monitoring End-to-End**: Menyediakan *executive dashboard* interaktif di Power BI untuk pemantauan performa harian.

---

## 🛠️ Data Sources & Feature Engineering

Dataset mencakup empat dimensi utama data pelanggan:
* **Demografis**: *Age, Gender, Income*
* **Perilaku (Behavioral)**: *Product Viewed, Add To Cart, Active Time*
* **Riwayat Transaksi**: *Purchase Frequency, Transaction Value, Last Purchase*
* **Interaksi (Engagement)**: *Email Opened, WhatsApp Clicked, Chat Replied*

melalui skrip Python (`notebooks/crm_customer_segmentation.ipynb`), dikembangkan **7 kolom segmentasi baru**:

| Kolom Hasil Enrichment | Deskripsi / Fungsi Utama |
|---|---|
| **Lead Score** | Skor komposit berbasis aktivitas (*Add to Cart, WA Click, Chat Reply, Email Open*). |
| **Lead Status** | Pengelompokan status kualitatif (*Hot, Warm, Cold Leads*). |
| **Sales Priority** | Skala prioritas tindakan untuk tim *Sales*. |
| **Customer Stage** | Tahapan pelanggan dalam *funnel/lifecycle*. |
| **Churn Risk** | Tingkat risiko kepindahan pelanggan (*Low, Medium, High Risk*). |
| **Campaign Recommendation** | Jenis kampanye terarah (*Sales Follow Up, Promo Reactivation, Loyalty, dll.*). |
| **Product Recommendation** | Logika penawaran produk (*Similar Product, Bundling, Premium, Discount*). |

---

## 📊 Key Findings & Business Impact

Berdasarkan hasil pemrosesan dan analisis data:

1. **Efisiensi Kerja Tim Sales**:
   * **9 Hot Leads** teridentifikasi sebagai prioritas utama yang harus segera di-*follow up* oleh tim Sales.
   * **118 Cold Leads** dialokasikan ke dalam *nurturing campaign* berbasis edukasi produk.

2. **Retensi Pelanggan & Mitigasi Churn**:
   * **91 Pelanggan Medium Risk** menjadi target program retensi untuk mencegah *churn*.
   * **144 Pelanggan Retention** difokuskan untuk peluang *upselling* dan program *loyalty*.

3. **Distribusi Rekomendasi Kampanye**:
   * *Sales Follow Up*: 57 pelanggan
   * *Promo Reactivation*: 57 pelanggan
   * *Loyalty Program*: 43 pelanggan
   * *WhatsApp Reminder*: 16 pelanggan
   * *Testimonial Customer*: 13 pelanggan
   * *Product Bundling*: 10 pelanggan

---

## 💡 Strategic Recommendations

* **High-Value & Loyal Customers**: Tawarkan produk kategori *Premium* serta akses awal program *loyalty* untuk mempertahankan *Customer Lifetime Value* (CLV).
* **At-Risk / Inactive Customers**: Eksekusi kampanye *Promo Reactivation* dengan memberikan penawaran diskon khusus pada produk yang sering dilihat.
* **Prospek Baru (Hot Leads)**: Dorong respons cepat dari tim Sales untuk meningkatkan angka konversi sebelum minat pembeli menurun.

---

## 🗂️ Repository Structure

```text
├── README.md                           <- Dokumentasi utama proyek
├── requirements.txt                    <- Daftar library Python
├── .gitignore                          <- File pengabaian sistem
│
├── data/
│   └── processed/
│       └── crm_data_final.xlsx         <- Dataset olahan dengan 7 kolom segmentasi
│
├── notebooks/
│   └── crm_customer_segmentation.ipynb <- Jupyter Notebook (Data Cleaning, Scoring, & Enrichment)
│
├── dashboards/
│   ├── crm_customer_dashboard.pbix     <- File Power BI Dashboard
│   └── screenshots/
│       └── dashboard_overview.png      <- Tampilan visual dashboard
│
├── assets/
│   ├── data_processing_flow.png        <- Diagram alur pemrosesan data
│   └── customer_lifecycle_flow.png     <- Diagram alur lifecycle pelanggan
│
└── Report & Presentation/
    └── crm_customer_analytics_report.pdf <- Slide laporan presentasi eksekutif
