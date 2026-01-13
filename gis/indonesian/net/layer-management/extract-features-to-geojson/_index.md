---
date: 2026-01-13
description: Pelajari cara mengonversi shapefile ke geojson menggunakan Aspose.GIS
  untuk .NET. Panduan ini juga mencakup penyalinan atribut antar lapisan dan pembuatan
  file geojson dengan C#.
linktitle: Extract Features to GeoJSON
second_title: Aspose.GIS .NET API
title: Cara Mengonversi Shapefile ke GeoJSON menggunakan Aspose.GIS untuk .NET
url: /id/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mengonversi Shapefile ke GeoJSON dengan Aspose.GIS untuk .NET

## Introduction
Dalam tutorial komprehensif langkah‑demi‑langkah ini Anda akan belajar **how to convert shapefile to geojson** menggunakan pustaka Aspose.GIS yang kuat untuk .NET. Baik Anda sedang membangun layanan web pemetaan, menyiapkan data untuk aplikasi GIS seluler, atau sekadar perlu menukar data antar format, panduan ini menunjukkan secara tepat apa yang harus dilakukan, mengapa setiap langkah penting, dan cara menghindari jebakan umum.

## Quick Answers
- **What does this tutorial cover?** Mengonversi Shapefile ke file GeoJSON, menyalin atribut antar lapisan, dan menghasilkan output dengan C#.
- **Which library is required?** Aspose.GIS untuk .NET.
- **Do I need a license?** Lisensi sementara atau penuh diperlukan untuk produksi; percobaan gratis dapat digunakan untuk evaluasi.
- **How long does implementation take?** Sekitar 10‑15 menit untuk konversi dasar.
- **Can I run this on .NET Core/.NET 6?** Ya – kode berfungsi pada semua versi .NET yang didukung.

## Prerequisites
Sebelum kita mulai, pastikan Anda memiliki hal‑hal berikut:

- Aspose.GIS for .NET: Pastikan Anda telah menginstal pustaka tersebut. Jika belum, Anda dapat mengunduhnya dari [Aspose.GIS for .NET page](https://releases.aspose.com/gis/net/).
- Shapefile Data: Miliki Shapefile siap untuk input. Jika Anda membutuhkan data contoh, Anda dapat menemukannya di [Aspose.GIS documentation](https://reference.aspose.com/gis/net/).
- .NET Environment: Siapkan lingkungan .NET untuk menjalankan kode yang disediakan.
- Document Directory: Tentukan jalur ke direktori dokumen Anda dalam cuplikan kode.

Sekarang semua sudah siap, mari mulai mengonversi shapefile ke geojson!

## What is “convert shapefile to geojson”?
Mengonversi Shapefile ke GeoJSON berarti membaca fitur vektor dari format Shapefile klasik ESRI dan menuliskannya sebagai dokumen GeoJSON modern yang ramah web. GeoJSON banyak digunakan dalam pustaka pemetaan JavaScript (Leaflet, Mapbox GL) dan API, menjadikan konversi ini tugas yang sering dalam pengembangan GIS.

## Why use Aspose.GIS for this conversion?
Aspose.GIS menyembunyikan detail tingkat‑rendah format file, memungkinkan Anda menyalin tabel atribut dengan mudah, dan menyediakan API berorientasi‑objek yang bersih yang bekerja di .NET Framework, .NET Core, dan .NET 5/6. Ini berarti Anda dapat fokus pada logika bisnis alih‑alih memparsing file biner.

## Import Namespaces
Pertama, sertakan namespace yang diperlukan dalam kode Anda:

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Namespace ini penting untuk bekerja dengan fungsionalitas Aspose.GIS.

## How to Convert Shapefile to GeoJSON
Berikut adalah alur kerja lengkap yang dibagi menjadi langkah‑langkah jelas. Setiap langkah mencakup penjelasan singkat diikuti oleh blok kode tepat yang perlu Anda salin ke dalam proyek.

### Step 1: Open Input Shapefile
```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```
Buka Shapefile input menggunakan metode `VectorLayer.Open`. Ini memberi Anda koleksi enumerable dari objek `Feature`.

### Step 2: Create Output GeoJSON
```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```
Buat file output dengan metode `VectorLayer.Create`, dengan menentukan driver `Drivers.GeoJson`.

### Step 3: Copy Attributes Between Layers
```csharp
outputLayer.CopyAttributes(inputLayer);
```
Baris tunggal ini menyalin skema atribut (nama bidang, tipe) dari Shapefile sumber ke lapisan GeoJSON baru—tepat seperti yang dijelaskan oleh kata kunci sekunder *copy attributes between layers*.

### Step 4: Process Features
```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```
Iterasi setiap fitur dalam Shapefile sehingga Anda dapat menerapkan logika khusus sebelum menuliskannya.

### Step 5: Filter Features by Date
```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```
Dalam contoh ini kami melewatkan catatan yang bidang `dob` (tanggal lahir)nya hilang atau lebih awal dari 1 Jan 1982. Silakan sesuaikan filter sesuai kebutuhan data Anda.

### Step 6: Construct a New Feature (C# Generate GeoJSON File)
```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```
Di sini kami membangun `Feature` baru untuk lapisan GeoJSON, menyalin geometri dan nilai atribut, dan menambahkannya ke output. Ini adalah inti dari *c# generate geojson file*.

Selamat! Anda telah berhasil **converted shapefile to geojson** dan mempelajari cara menyalin atribut antar lapisan selama proses.

## Common Issues and Solutions
| Masalah | Mengapa Terjadi | Solusi |
|-------|----------------|-----|
| Output file is empty | `CopyAttributes` dipanggil setelah lapisan output ditutup | Pastikan blok `using` untuk `outputLayer` tetap terbuka hingga semua fitur ditambahkan. |
| Date filter removes all records | Nama bidang salah atau format tanggal tidak terduga | Verifikasi nama atribut (`dob`) dan gunakan `GetValue<string>` jika tanggal disimpan sebagai string. |
| License exception | Menjalankan tanpa lisensi Aspose.GIS yang valid di produksi | Terapkan lisensi sementara atau penuh seperti yang dijelaskan dalam dokumentasi Aspose. |

## Frequently Asked Questions
**Q: Di mana saya dapat menemukan dokumentasi lebih lanjut?**  
A: Kunjungi [Aspose.GIS documentation](https://reference.aspose.com/gis/net/) untuk informasi mendalam.

**Q: Bagaimana cara mendapatkan lisensi sementara?**  
A: Anda dapat memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

**Q: Di mana saya dapat mencari dukungan?**  
A: Bergabunglah dengan [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) untuk dukungan komunitas dan diskusi.

**Q: Apakah ada percobaan gratis yang tersedia?**  
A: Ya, Anda dapat menemukan percobaan gratis [di sini](https://releases.aspose.com/).

**Q: Di mana saya dapat membeli Aspose.GIS untuk .NET?**  
A: Anda dapat membeli produk tersebut [di sini](https://purchase.aspose.com/buy).

## Conclusion
Dalam tutorial ini kami menjelajahi proses lengkap **convert shapefile to geojson** menggunakan Aspose.GIS untuk .NET, menunjukkan cara menyalin atribut antar lapisan, dan memperlihatkan cara bersih untuk *c# generate geojson file*. Bereksperimenlah dengan filter yang berbeda, dataset yang lebih besar, atau transformasi geometri tambahan untuk memanfaatkan kemampuan pustaka secara maksimal.

---

**Terakhir Diperbarui:** 2026-01-13  
**Diuji Dengan:** Aspose.GIS for .NET (latest stable release)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}