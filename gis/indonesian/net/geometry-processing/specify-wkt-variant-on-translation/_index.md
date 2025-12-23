---
date: 2025-12-23
description: Pelajari cara mengonversi geometri ke WKT dengan berbagai opsi, mengatur
  format numerik, dan menyesuaikan presisi desimal menggunakan Aspose.GIS untuk .NET.
linktitle: Convert Geometry to WKT
second_title: Aspose.GIS .NET API
title: Mengonversi Geometri ke Opsi Varian WKT menggunakan Aspose.GIS
url: /id/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mengonversi Geometri ke Opsi Varian WKT menggunakan Aspose.GIS

## Introduction
Dalam aplikasi .NET modern, **mengonversi geometri ke WKT** adalah langkah umum ketika Anda perlu bertukar data spasial dengan sistem lain atau menyimpannya dalam format berbasis teks. Aspose.GIS untuk .NET membuat konversi ini menjadi mudah sambil memberi Anda kontrol penuh atas varian WKT, format numerik, dan presisi desimal. Dalam tutorial ini Anda akan belajar cara mengonversi geometri ke WKT, memilih varian yang tepat, dan menyesuaikan output agar memenuhi persyaratan proyek Anda secara tepat.

## Quick Answers
- **Apa arti “convert geometry to WKT”?** Itu mengubah objek geometrik (titik, garis, poligon) menjadi representasi Well‑Known Text.  
- **Varian WKT apa yang didukung?** `Iso`, `SimpleFeatureAccessOutdated`, dan `ExtendedPostGis`.  
- **Bagaimana saya dapat mengontrol presisi desimal?** Gunakan opsi `NumericFormat` seperti `General`, `RoundTrip`, atau `Flat`.  
- **Apakah saya memerlukan lisensi untuk produksi?** Ya, lisensi komersial diperlukan untuk penggunaan selain percobaan.  
- **Versi .NET apa yang kompatibel?** .NET Framework 4.0+ dan .NET 5/6/7.

## What is “convert geometry to WKT”?
Mengonversi geometri ke WKT menghasilkan string yang dapat dibaca manusia yang menggambarkan objek spasial. Format ini diterima secara luas oleh alat GIS, basis data, dan layanan web, menjadikannya ideal untuk pertukaran data.

## Why use Aspose.GIS for this conversion?
- **Kontrol presisi** – Pilih berapa banyak tempat desimal yang dikeluarkan.  
- **Fleksibilitas varian** – Sesuaikan dialek WKT yang tepat yang dibutuhkan oleh sistem hilir Anda.  
- **Tanpa ketergantungan eksternal** – Perpustakaan .NET murni, tanpa binari native.

## Prerequisites
Sebelum kita mulai, pastikan Anda memiliki:

1. **Aspose.GIS untuk .NET** – Unduh dan instal dari [halaman unduhan](https://releases.aspose.com/gis/net/).  
2. **Lingkungan Pengembangan** – Versi terbaru Visual Studio atau VS Code dengan .NET SDK.  
3. **Pengetahuan dasar C#** – Familiaritas dengan kelas, objek, dan kerangka kerja .NET.

## Import Namespaces
First, bring the required namespaces into scope:

```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```

## Step 1: Create a Point Object
Create a `Point` that you will later **convert geometry to WKT**. The point includes latitude, longitude, and an optional measure (M) value:

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Step 2: Set Spatial Reference System (SRS)
Assign a spatial reference system so the WKT output knows which coordinate system to reference. Here we use the common WGS84 system:

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Step 3: Specify WKT Variant
Choose the appropriate WKT variant when you **convert geometry to WKT**. Each variant formats the output slightly differently:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Step 4: Control Numeric Format (Set Numeric Format & Adjust Decimal Precision)
Fine‑tune the numeric representation of coordinates. The `NumericFormat` class lets you **set numeric format** and **adjust decimal precision** to suit your needs:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

## Common Issues & Tips
- **Nilai M hilang** – Jika Anda tidak memerlukan ukuran, hapus properti `M`; varian ISO akan mengabaikannya secara otomatis.  
- **Presisi tidak terduga** – Periksa kembali bahwa Anda menggunakan `NumericFormat` yang tepat; `General` mempertahankan presisi double penuh, sementara `Flat` membulatkan ke jumlah desimal yang ditentukan.  
- **SRID tidak ditampilkan** – Hanya varian `ExtendedPostGis` yang menambahkan awalan `SRID=` pada output. Pilih varian ini ketika sistem target Anda mengharapkan SRID.

## Conclusion
Dengan mengikuti langkah‑langkah ini Anda kini tahu cara **mengonversi geometri ke WKT**, memilih varian yang tepat, dan mengontrol output numerik dengan presisi. Ini memberi Anda fleksibilitas untuk mengintegrasikan Aspose.GIS dengan alur kerja GIS, basis data, atau layanan web apa pun yang mengonsumsi WKT.

## FAQ's
### Apakah Aspose.GIS kompatibel dengan semua versi .NET?
Ya, Aspose.GIS mendukung .NET Framework 4.0 ke atas.

### Apakah saya dapat menggunakan Aspose.GIS untuk proyek komersial?
Ya, Aspose.GIS dapat digunakan untuk proyek pribadi maupun komersial.

### Apakah Aspose.GIS menyediakan dukungan untuk format data spasial lainnya?
Ya, Aspose.GIS mendukung berbagai format data spasial, termasuk ESRI Shapefile, GeoJSON, dan KML.

### Apakah ada versi percobaan gratis untuk Aspose.GIS?
Ya, Anda dapat mengunduh versi percobaan gratis Aspose.GIS dari [sini](https://releases.aspose.com/).

### Di mana saya dapat mendapatkan bantuan atau dukungan untuk Aspose.GIS?
Anda dapat mengirim pertanyaan atau meminta bantuan dari komunitas Aspose.GIS di [forum](https://forum.aspose.com/c/gis/33).

## Frequently Asked Questions
**Q: Bagaimana cara mengekspor koleksi Geometry menjadi satu string WKT?**  
A: Iterasi setiap geometry dalam koleksi dan gabungkan hasil `AsText` mereka, opsional dipisahkan dengan koma atau baris baru.

**Q: Bisakah saya mengubah SRID tanpa mengubah koordinat?**  
A: Ya, atur properti `SpatialReferenceSystem` ke SRID yang diinginkan; nilai koordinat tetap tidak berubah.

**Q: Apa yang terjadi jika saya menggunakan varian WKT yang tidak didukung?**  
A: Aspose.GIS akan melempar `ArgumentException`. Selalu validasi varian terhadap nilai enum `WktVariant`.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}