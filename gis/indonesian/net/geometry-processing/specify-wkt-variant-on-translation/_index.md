---
date: 2026-04-09
description: Pelajari cara menetapkan referensi spasial dan mengatur presisi desimal
  saat membuat titik C# dengan Aspose.GIS untuk .NET dalam aplikasi .NET Anda.
keywords:
- assign spatial reference
- set decimal precision
- create point c#
linktitle: Tentukan Varian WKT pada Terjemahan
second_title: Aspose.GIS .NET API
title: Tetapkan Referensi Spasial & Atur Varian WKT menggunakan Aspose.GIS
url: /id/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tetapkan Referensi Spasial & Atur Variasi WKT menggunakan Aspose.GIS

## Pendahuluan
Dalam tutorial ini Anda akan belajar cara **menetapkan referensi spasial** pada sebuah geometri dan mengontrol format output WKT yang tepat dengan Aspose.GIS untuk .NET. Baik Anda perlu **membuat point C#** untuk pemetaan, analitik, atau pertukaran data, kemampuan memilih variasi WKT yang tepat dan presisi numerik membuat data spasial Anda dapat dipertukarkan dan mudah dibaca. Mari kita jalani prosesnya langkah demi langkah.

## Jawaban Cepat
- **Apa arti “assign spatial reference”?** Itu mengaitkan sebuah geometri dengan sistem koordinat tertentu seperti WGS‑84.  
- **Varian WKT apa yang didukung?** Iso, SimpleFeatureAccessOutdated, dan ExtendedPostGis.  
- **Bagaimana saya dapat mengontrol presisi desimal?** Gunakan opsi `NumericFormat` seperti `General`, `RoundTrip`, atau `Flat`.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis tersedia; lisensi komersial diperlukan untuk produksi.  
- **Versi .NET apa yang kompatibel?** .NET Framework 4.0+ dan .NET Core/5/6+.

## Apa itu “assign spatial reference”?
Menetapkan referensi spasial (atau sistem referensi spasial, SRS) memberi tahu perangkat lunak GIS cara menafsirkan nilai koordinat sebuah geometri. Tanpa SRS, angka lintang‑bujur sebuah titik tidak memiliki arti dunia nyata.

## Mengapa mengontrol variasi WKT dan format numerik?
Berbagai alat GIS mengharapkan sintaks WKT yang sedikit berbeda. Memilih variasi yang tepat memastikan pertukaran data yang mulus, sementara mengatur presisi desimal mencegah kesalahan pembulatan atau angka yang terlalu panjang yang mengacaukan log dan file.

## Prasyarat
1. Aspose.GIS untuk .NET – unduh dari [halaman unduhan](https://releases.aspose.com/gis/net/).  
2. Lingkungan pengembangan .NET (Visual Studio, VS Code, atau Rider).  
3. Familiaritas dasar dengan C# dan kerangka kerja .NET.

## Impor Namespace
Sebelum menggunakan kelas Aspose.GIS apa pun, impor namespace yang diperlukan:

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

## Langkah 1: Buat Objek Point (create point C#)
Kita mulai dengan membuat sebuah `Point` dengan nilai latitude, longitude, dan nilai ukuran (M) opsional:

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Langkah 2: Tetapkan Sistem Referensi Spasial (SRS)
Sekarang kita **menetapkan referensi spasial** pada titik tersebut. Di sini kita menggunakan sistem WGS‑84 yang banyak didukung (SRID 4326):

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Langkah 3: Tentukan Variasi WKT yang Diinginkan
Pilih variasi WKT yang cocok dengan aplikasi hilir Anda:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Langkah 4: Atur Presisi Desimal untuk Output WKT
Kontrol berapa banyak digit yang muncul dalam string akhir menggunakan `NumericFormat`:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### Kesalahan Umum & Tips
- **Kesalahan:** Lupa mengatur SRS sebelum memanggil `AsText` dapat menyebabkan informasi SRID hilang.  
- **Tips:** Gunakan `NumericFormat.RoundTrip` ketika Anda memerlukan perjalanan bolak‑balik koordinat tanpa kehilangan.  
- **Tips:** Variasi `Iso` adalah yang paling portabel; pilih `ExtendedPostGis` hanya ketika Anda memerlukan SRID tersemat.

## Kesimpulan
Anda kini tahu cara **menetapkan referensi spasial**, memilih variasi WKT yang tepat, dan **mengatur presisi desimal** saat Anda **membuat point C#** dengan Aspose.GIS. Kontrol ini memberi Anda fleksibilitas untuk memenuhi persyaratan tepat dari alur kerja GIS apa pun, mulai dari visualisasi sederhana hingga analisis spasial berpresisi tinggi.

## Pertanyaan yang Sering Diajukan

**T:** Apakah Aspose.GIS kompatibel dengan semua versi .NET?  
**J:** Ya, Aspose.GIS mendukung .NET Framework 4.0 ke atas, serta .NET Core/5/6.

**T:** Bisakah saya menggunakan Aspose.GIS untuk proyek komersial?  
**J:** Tentu saja. Lisensi komersial diperlukan untuk penggunaan produksi, namun versi percobaan gratis tersedia untuk evaluasi.

**T:** Apakah Aspose.GIS mendukung format data spasial lain?  
**J:** Ya, ia bekerja dengan ESRI Shapefile, GeoJSON, KML, dan banyak format lainnya.

**T:** Di mana saya dapat mengunduh versi percobaan gratis?  
**J:** Anda dapat mengunduh versi percobaan gratis Aspose.GIS dari [sini](https://releases.aspose.com/).

**T:** Bagaimana saya mendapatkan bantuan jika saya mengalami masalah?  
**J:** Posting pertanyaan Anda di [forum](https://forum.aspose.com/c/gis/33) komunitas Aspose.GIS dimana staf Aspose dan anggota komunitas dapat membantu.

---

**Terakhir Diperbarui:** 2026-04-09  
**Diuji Dengan:** Aspose.GIS untuk .NET (rilis terbaru)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}