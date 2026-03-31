---
date: 2025-12-21
description: Pelajari cara membuat geometri linestring dan mengonversi geometri ke
  WKB dengan Aspose.GIS untuk .NET menggunakan varian ExtendedPostGis.
linktitle: Specify WKB Variant on Translation
second_title: Aspose.GIS .NET API
title: Buat Geometri Linestring & Varian WKB di Aspose.GIS .NET
url: /id/net/geometry-processing/specify-wkb-variant-on-translation/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tentukan Varian WKB pada Terjemahan di Aspose.GIS untuk .NET

## Perkenalan
Di bidang pengembangan Sistem Informasi Geografis (GIS), Aspose.GIS untuk .NET menonjol sebagai alat rangkaian yang kuat. efisiensinya menjadikannya pilihan utama bagi pengembang yang ingin mengintegrasikan fungsionalitas GIS ke dalam aplikasi .NET mereka secara mulus. khususnya fokus pada penentuan varian WKB (Well‑Known Binary) selama proses translasi.

## Jawaban Cepat
- **Apa kepanjangan WKB?** Well‑Known Binary, representasi biner kompak dari objek geometris.
- **Varian WKB mana yang memungkinkan saya menyimpan informasi SRID?** Varian `ExendedPostGis` (EWKB).
- **Apakah saya memerlukan lisensi untuk menjalankan kode?** Lisensi sementara atau penuh diperlukan untuk penggunaan produksi.
- **Versi .NET mana yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, dan .NET 5/6+.
- **Berapa lama implementasinya?** Biasanya kurang dari 10 menit untuk contoh dasar.

## Apa itu Geometri Linestring?
Linestring adalah bentuk geometris sederhana yang terdiri dari urutan titik yang dihubungkan oleh segmen garis lurus. Ini biasanya digunakan untuk merepresentasikan jalan, sungai, atau fitur linear apa pun dalam data GIS.

## Mengapa Menentukan Varian WKB?
Varian `ExendedPostGis` (EWKB) sangat berguna saat bekerja dengan PostgreSQL/PostGIS atau sistem apa pun yang mengharapkan informasi SRID tertanam dalam biner.

## Prasyarat
Sebelum menyelami detail penentuan varian WKB di Aspose.GIS untuk .NET, pastikan Anda telah menyiapkan prasyarat berikut:

### Menginstal Aspose.GIS untuk .NET
1. Unduh Aspose.GIS: Kunjungi [tautan unduh](https://releases.aspose.com/gis/net/) untuk mendapatkan paket Aspose.GIS untuk .NET.
2. Instal Paket: Ikuti instalasi petunjuk yang disediakan dalam dokumentasi untuk mengintegrasikan Aspose.GIS ke dalam lingkungan .NET Anda secara mulus.

### Keakraban dengan Pemrograman C#
1. Pengetahuan Dasar C#: Pastikan Anda memiliki pemahaman dasar tentang sintaks dan konsep bahasa pemrograman C#.

## Impor Namespace
Berikut panduan langkah demi langkah:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Namespace ini memberikan akses ke fungsionalitas Aspose.GIS, memungkinkan Anda bekerja dengan data geografis dengan mudah.

## Bagaimana cara membuat geometri linestring?
Mari kita uraikan contoh yang diberikan menjadi beberapa langkah untuk memahami proses penentuan varian WKB pada terjemahan secara menyeluruh.

### Langkah 1: Membuat Objek Geometri
```csharp
IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
```
Pada langkah ini, kami **membuat geometri linestring** yang mewakili fitur linear dengan koordinat yang ditentukan.

### Langkah 2: Menghasilkan Representasi WKB
```csharp
byte[] wkb = geometry.AsBinary(WkbVariant.ExtendedPostGis);
```
Di sini, kami **mengonversi geometri ke WKB** menggunakan varian `ExtendedPostGis`, yang menyertakan informasi SRID.

### Langkah 3: Menulis ke File
```csharp
File.WriteAllBytes(Path.Combine("Your Document Directory", "EWkbFile.ewkb"), wkb);
```
Akhirnya, kami menulis data biner WKB yang dihasilkan ke file bernama `EWkbFile.ewkb` di direktori pilihan Anda.

## Masalah Umum dan Solusinya
| Masalah | Alasan | Solusi |
|-------|--------|----------|
| **File kosong** | `Path.Combine` menunjuk ke direktori yang tidak ada. | Pastikan direktori target ada atau buat dengan `Directory.CreateDirectory`. |
| **SRID tidak tepat** | Menggunakan `WkbVariant.Standard` default menghilangkan SRID. | Selalu gunakan `WkbVariant.ExtendedPostGis` ketika preservasi SRID diperlukan. |
| **Pengecualian lisensi** | Menjalankan tanpa lisensi yang valid di produksi. | Terapkan lisensi sementara atau penuh sebelum mengeksekusi kode di lingkungan produksi. |


## Pertanyaan yang Sering Diajukan
**Q: Dapatkah saya menggunakan file EWKB dengan PostGIS?**  
A: Ya, varian `ExtendedPostGis` menghasilkan EWKB yang menyertakan SRID, yang dapat dibaca langsung oleh PostGIS.

**Q: Apakah memungkinkan membaca file WKB kembali menjadi objek geometri?**  
A: Tentu saja. Gunakan `Geometry.FromBinary(byteArray)` untuk merekonstruksi geometri.

**Q: Apakah perpustakaan ini mendukung tipe geometri lain seperti poligon?**  
A: Ya, Aspose.GIS menangani titik, linestring, poligon, multipoligon, dan lainnya.

**Q: Bagaimana cara menentukan SRID yang berbeda saat membuat geometri?**  
A: Atur SRID pada objek geometri sebelum memanggil `AsBinary`, misalnya, `geometry.SRID = 4326;`.

**Q: Apakah kode ini akan berfungsi di .NET Core?**  
A: Ya, API yang sama berfungsi di .NET Framework, .NET Core, dan .NET 5/6.

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.GIS for .NET 23.9 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}