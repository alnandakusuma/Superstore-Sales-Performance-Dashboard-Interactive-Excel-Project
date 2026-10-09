**Bahasa:** [English](README.md) | Bahasa Indonesia

# Dashboard Sales & Performance Superstore (Excel)

Dashboard Excel interaktif yang menganalisis penjualan, profitabilitas, dan tren pesanan sebuah perusahaan ritel (Superstore, 2014-2017). Proyek ini memakai Power Query untuk impor data, PivotTable dan PivotChart untuk analisis, serta slicer dan timeline untuk penyaringan interaktif.

## Tampilan Dashboard
![Dashboard](screenshots/dashboard.png)

## Pertanyaan Bisnis
1. Berapa penjualan dan keuntungan bisnis, dan berapa margin keuntungan keseluruhan?
2. Bagaimana tren penjualan dan profit dari waktu ke waktu, dan kapan musim puncaknya?
3. Kategori dan produk mana yang mendorong penjualan dan profit?
4. Bagaimana perbedaan hasil menurut wilayah dan segmen pelanggan?

## Dataset
- **Sumber:** dataset Sample - Superstore
- **Ukuran:** 9.994 baris, 21 kolom, tanggal pesanan Januari 2014 sampai Desember 2017
- **Pesanan:** 5.009 pesanan unik (dataset berisi satu baris per item pesanan)
- File CSV mentah tidak disertakan di repositori ini.

## Metrik Utama
| Metrik | Nilai |
|---|---|
| Total Sales | $2,30 juta |
| Total Profit | $286 ribu |
| Profit Margin | 12,5% |
| Total Orders (unik) | 5.009 |

## Alur Pengerjaan
1. **Impor (Power Query):** memuat CSV ke tabel Excel bernama `Dataset`.
2. **Validasi data:** memeriksa jumlah baris, duplikat, nilai kosong, rentang tanggal, dan total (lihat catatan kualitas data di bawah).
3. **Analisis:** membuat lima PivotTable (KPI, tren bulanan, kategori, produk teratas, wilayah) di sheet `Pivot`.
4. **Dashboard:** tiga PivotChart, kartu KPI yang terhubung ke sel PivotTable, slicer (Region, Segment, Bulan), dan timeline Order Date, semuanya tersambung ke setiap PivotTable.
5. **Penyajian:** skema warna konsisten, tata letak sejajar, dan legenda chart yang jelas.

## Catatan Kualitas Data
Pada versi awal, kartu KPI menampilkan profit yang lebih besar dari penjualan (margin 159%). Penyebabnya ada di proses impor: karena pengaturan regional Indonesia, titik desimal terbaca sebagai pemisah ribuan, sehingga kolom `Sales`, `Discount`, dan `Profit` tersimpan sebagai bilangan bulat (misalnya `261.96` menjadi `26196`).

**Perbaikan:** memuat ulang data di Power Query dan mengubah tipe data memakai locale English (United States). Setelah itu saya memvalidasi ulang total (penjualan, profit, margin, dan pesanan unik) serta memeriksa bahwa baris-baris awal sama dengan file sumber.

## Temuan Utama
- Penjualan naik setiap September dan kembali pada November-Desember; bulan tertinggi adalah November 2017 (sekitar $118 ribu).
- Technology adalah kategori terkuat dalam penjualan maupun profit.
- Furniture penjualannya besar tetapi profitnya paling kecil, sehingga penjualan tinggi belum tentu berarti keuntungan tinggi.
- Produk terlaris adalah Canon imageCLASS 2200 Advanced Copier (sekitar $62 ribu).

## Saran Tindak Lanjut
- Selidiki penyebab profit Furniture yang rendah (misalnya diskon atau biaya produk).
- Siapkan stok dan promosi menjelang puncak September dan November-Desember.
- Bandingkan margin per wilayah dan segmen memakai slicer.

## Keterbatasan
- Dataset contoh, sehingga temuan menggambarkan pendekatan analisis dan bukan perusahaan nyata.
- Sumber Power Query mengarah ke jalur file lokal; menyegarkan data di komputer lain memerlukan perubahan sumber data.
- Slicer dan timeline bekerja paling baik di Excel desktop (2013 atau lebih baru).

## Cara Memakai
1. Unduh `Superstore_Sales_Dashboard.xlsx` dan buka di Excel.
2. Buka sheet `Dashboard`, lalu gunakan slicer (Region, Segment, Bulan) dan timeline Order Date.
3. Klik ikon corong dengan tanda silang pada slicer untuk menghapus filter.

## Tools
Microsoft Excel · Power Query · PivotTable dan PivotChart · Slicer dan Timeline

## Penulis
**Alnanda**
www.linkedin.com/in/alnandakusuma
https://github.com/alnandakusuma
