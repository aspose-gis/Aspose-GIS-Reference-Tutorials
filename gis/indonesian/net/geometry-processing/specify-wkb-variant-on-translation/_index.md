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

# Tentukan Varian WKB pada Translasi di Aspose.GIS untuk .NET

## Introduction
Di bidang pengembangan Sistem Informasi Geografis (GIS), Aspose.GIS untuk .NET menonjol sebagai rangkaian alat yang kuat. Jika Anda perlu **membuat geometri linestring** dan kemudian **mengonversi geometri ke WKB**, Anda berada di tempat yang tepat. Fleksibilitas dan efisiensinya menjadikannya pilihan utama bagi pengembang yang ingin mengintegrasikan fungsionalitas GIS ke dalam aplikasi .NET mereka secara mulus. Artikel ini berfungsi sebagai panduan komprehensif untuk memanfaatkan Aspose.GIS untuk .NET, khususnya berfokus pada penentuan varian WKB (Well‑Known Binary) selama proses translasi.

## Quick Answers
- **Apa kepanjangan WKB?** Well‑Known Binary, representasi biner kompak dari objek geometris.  
- **Varian WKB mana yang memungkinkan saya menyimpan informasi SRID?** Varian `ExtendedPostGis` (EWKB).  
- **Apakah saya memerlukan lisensi untuk menjalankan kode?** Lisensi sementara atau penuh diperlukan untuk penggunaan produksi.  
- **Versi .NET mana yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, dan .NET 5/6+.  
- **Berapa lama implementasinya?** Biasanya kurang dari 10 menit untuk contoh dasar.

## What is a Linestring Geometry?
Linestring adalah bentuk geometris sederhana yang terdiri dari urutan titik yang dihubungkan oleh segmen garis lurus. Ini biasanya digunakan untuk merepresentasikan jalan, sungai, atau fitur linear apa pun dalam data GIS.

## Why Specify a WKB Variant?
Memilih varian WKB yang tepat memastikan bahwa metadata penting—seperti Spatial Reference System Identifier (SRID)—tetap terjaga ketika Anda menyimpan atau bertukar data geometri. Varian `ExtendedPostGis` (EWKB) sangat berguna saat bekerja dengan PostgreSQL/PostGIS atau sistem apa pun yang mengharapkan informasi SRID tertanam dalam biner.

## Prerequisites
Sebelum menyelami detail penentuan varian WKB di Aspose.GIS untuk .NET, pastikan Anda telah menyiapkan prasyarat berikut:

### Installing Aspose.GIS for .NET
1. Download Aspose.GIS: Visit the [download link](https://releases.aspose.com/gis/net/) to acquire the Aspose.GIS for .NET package.  
2. Install the Package: Ikuti petunjuk instalasi yang disediakan dalam dokumentasi untuk mengintegrasikan Aspose.GIS ke dalam lingkungan .NET Anda secara mulus.

### Familiarity with C# Programming
1. Basic C# Knowledge: Pastikan Anda memiliki pemahaman dasar tentang sintaks dan konsep bahasa pemrograman C#.

## Import Namespaces
Untuk memulai perjalanan Anda dengan Aspose.GIS untuk .NET dan memanfaatkan fungsionalitasnya secara efektif, Anda perlu mengimpor namespace yang diperlukan ke dalam proyek Anda. Berikut panduan langkah demi langkah:

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

## How to create linestring geometry?
Mari kita uraikan contoh yang diberikan menjadi beberapa langkah untuk memahami proses penentuan varian WKB pada translasi secara menyeluruh.

### Step 1: Creating a Geometry Object
```csharp
IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
```
Pada langkah ini, kami **membuat geometri linestring** yang mewakili fitur linear dengan koordinat yang ditentukan.

### Step 2: Generating WKB Representation
```csharp
byte[] wkb = geometry.AsBinary(WkbVariant.ExtendedPostGis);
```
Di sini, kami **mengonversi geometri ke WKB** menggunakan varian `ExtendedPostGis`, yang menyertakan informasi SRID.

### Step 3: Writing to File
```csharp
File.WriteAllBytes(Path.Combine("Your Document Directory", "EWkbFile.ewkb"), wkb);
```
Akhirnya, kami menulis data biner WKB yang dihasilkan ke file bernama `EWkbFile.ewkb` di direktori pilihan Anda.

## Common Issues and Solutions
| Masalah | Alasan | Solusi |
|-------|--------|----------|
| **File kosong** | `Path.Combine` menunjuk ke direktori yang tidak ada. | Pastikan direktori target ada atau buat dengan `Directory.CreateDirectory`. |
| **SRID tidak tepat** | Menggunakan `WkbVariant.Standard` default menghilangkan SRID. | Selalu gunakan `WkbVariant.ExtendedPostGis` ketika preservasi SRID diperlukan. |
| **Pengecualian lisensi** | Menjalankan tanpa lisensi yang valid di produksi. | Terapkan lisensi sementara atau penuh sebelum mengeksekusi kode di lingkungan produksi. |

## FAQ's
### Is Aspose.GIS for .NET compatible with all versions of .NET?
Aspose.GIS untuk .NET dirancang agar kompatibel dengan berbagai versi .NET, memastikan fleksibilitas dan aksesibilitas bagi pengembang.

### Can I request support or assistance while using Aspose.GIS for .NET?
Ya, Anda dapat meminta dukungan dan bantuan melalui [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) yang didedikasikan, di mana para ahli dan sesama pengembang dapat menjawab pertanyaan Anda.

### Does Aspose.GIS for .NET offer a free trial?
Ya, Anda dapat menjelajahi fitur dan kemampuan Aspose.GIS untuk .NET melalui percobaan gratis yang tersedia di [tautan ini](https://releases.aspose.com/).

### How can I obtain a temporary license for Aspose.GIS for .NET?
Anda dapat memperoleh lisensi sementara dengan mengunjungi [halaman lisensi sementara](https://purchase.aspose.com/temporary-license/) dan mengikuti instruksi yang diberikan.

### Where can I purchase a license for Aspose.GIS for .NET?
Anda dapat membeli lisensi untuk Aspose.GIS untuk .NET dari halaman pembelian di [tautan ini](https://purchase.aspose.com/buy).

## Frequently Asked Questions
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