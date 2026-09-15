---
date: 2026-09-15
description: Pelajari cara menetapkan sistem koordinat, mengatur varian WKT, dan mengontrol
  presisi desimal saat membuat geometri titik dalam C# dengan Aspose.GIS untuk .NET.
keywords:
- assign coordinate system
- assign spatial reference
- set decimal precision
- create point geometry
- set numeric format
lastmod: 2026-09-15
linktitle: Tentukan Varian WKT pada Translasi
og_description: Pelajari cara menetapkan sistem koordinat, mengatur varian WKT, dan
  mengontrol presisi desimal saat membuat geometri titik dalam C# dengan Aspose.GIS
  untuk .NET.
og_image_alt: Developer guide showing C# code to assign coordinate system and configure
  WKT output with Aspose.GIS
og_title: Tetapkan sistem koordinat, atur varian WKT menggunakan Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-09-15'
  description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  headline: Assign coordinate system, set WKT variant using Aspose.GIS
  type: TechArticle
- description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  name: Assign coordinate system, set WKT variant using Aspose.GIS
  steps:
  - name: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
    text: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
  - name: A .NET development environment (Visual Studio, VS Code, or Rider).
    text: A .NET development environment (Visual Studio, VS Code, or Rider).
  - name: Basic familiarity with C# and the .NET framework.
    text: Basic familiarity with C# and the .NET framework.
  type: HowTo
- questions:
  - answer: It binds a geometry to a specific coordinate reference system such as
      WGS‑84.
    question: What does “assign coordinate system” mean?
  - answer: Iso, SimpleFeatureAccessOutdated, and ExtendedPostGis.
    question: Which WKT variants are supported?
  - answer: Use the `NumericFormat` enum (`General`, `RoundTrip`, `Flat`).
    question: How can I control decimal precision?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license for Aspose.GIS?
  - answer: .NET Framework 4.0+ and .NET Core/5/6+.
    question: What .NET versions are compatible?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- assign coordinate system
- Aspose.GIS
- C# geometry
- WKT variant
title: Tetapkan sistem koordinat, atur varian WKT menggunakan Aspose.GIS
url: /id/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tetapkan sistem koordinat, atur varian WKT menggunakan Aspose.GIS

## Pendahuluan
Dalam tutorial ini Anda akan belajar cara **assign coordinate system**, memilih varian WKT yang tepat, dan mengontrol presisi desimal saat Anda **create point geometry** dalam C# dengan Aspose.GIS untuk .NET. Baik Anda membangun layanan pemetaan, melakukan analisis spasial, atau menukar data antar platform GIS, pengaturan ini menjamin bahwa output Anda dapat berinteroperasi dan mudah dibaca. Mari kita jalani prosesnya langkah demi langkah.

## Jawaban cepat
- **Apa arti “assign coordinate system”?** Itu mengikat sebuah geometri ke sistem referensi koordinat tertentu seperti WGS‑84.  
- **Varian WKT mana yang didukung?** Iso, SimpleFeatureAccessOutdated, dan ExtendedPostGis.  
- **Bagaimana saya dapat mengontrol presisi desimal?** Gunakan enum `NumericFormat` (`General`, `RoundTrip`, `Flat`).  
- **Apakah saya memerlukan lisensi untuk Aspose.GIS?** Versi percobaan gratis tersedia; lisensi komersial diperlukan untuk penggunaan produksi.  
- **Versi .NET apa yang kompatibel?** .NET Framework 4.0+ dan .NET Core/5/6+.

## Apa itu “assign coordinate system”?
Menetapkan referensi spasial (atau sistem referensi spasial, SRS) memberi tahu perangkat lunak GIS cara menafsirkan nilai koordinat sebuah geometri, menghubungkan angka-angka tersebut ke sistem koordinat dunia nyata seperti WGS‑84. Tanpa SRS, angka lintang‑bujur sebuah titik tidak memiliki makna dunia nyata.

## Mengapa mengontrol varian WKT dan format numerik?
Lebih dari 30 alat GIS mengharapkan sintaks WKT tertentu, sehingga memilih varian yang tepat mencegah kesalahan impor. Menetapkan format numerik mengurangi noise pembulatan dan menjaga output tetap ringkas, yang terutama penting ketika log atau file diproses secara programatik.

## Prasyarat
1. Aspose.GIS untuk .NET – unduh dari [halaman unduhan](https://releases.aspose.com/gis/net/).  
2. Lingkungan pengembangan .NET (Visual Studio, VS Code, atau Rider).  
3. Pemahaman dasar tentang C# dan kerangka kerja .NET.

## Impor namespace
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

## Cara menetapkan sistem koordinat ke sebuah titik?
Muat sebuah instance `Point`, lalu lampirkan sistem referensi spasial (SRS) menggunakan kelas `SpatialReference`. Pola dua langkah ini memastikan geometri membawa metadata sistem koordinatnya saat diekspor, memungkinkan alat hilir untuk menafsirkan koordinat dengan benar. Kelas `Point` mewakili satu lokasi tunggal yang didefinisikan oleh koordinat X (longitude) dan Y (latitude).

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Langkah 2: tetapkan sistem referensi spasial (SRS)
Sekarang kita **assign spatial reference** ke titik tersebut. `SpatialReference` mewakili sistem referensi koordinat yang diidentifikasi oleh SRID. Di sini kita menggunakan sistem WGS‑84 yang banyak didukung (SRID 4326):

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Langkah 3: tentukan varian WKT yang diinginkan
Pilih varian WKT yang sesuai dengan aplikasi hilir Anda:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Cara mengatur presisi desimal untuk output WKT?
Kontrol berapa banyak digit yang muncul dalam string akhir menggunakan enum `NumericFormat`, yang mendefinisikan aturan pemformatan seperti `General`, `RoundTrip`, atau `Flat`. Memilih `RoundTrip` mempertahankan fidelitas koordinat penuh untuk skenario round‑tripping, sementara `General` memberikan representasi ringkas yang cocok untuk kebanyakan tugas visualisasi. Enum `NumericFormat` mengontrol bagaimana angka koordinat diformat dalam output WKT.

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### Jebakan umum & tips
- **Pitfall:** Lupa menetapkan SRS sebelum memanggil `AsText` dapat menyebabkan informasi SRID hilang.  
- **Tip:** Gunakan `NumericFormat.RoundTrip` ketika Anda membutuhkan round‑tripping koordinat tanpa kehilangan.  
- **Tip:** Varian `Iso` adalah yang paling portabel; pilih `ExtendedPostGis` hanya ketika Anda memerlukan SRID tersemat.

## Kesimpulan
Anda kini tahu cara **assign coordinate system**, memilih varian WKT yang tepat, dan **set decimal precision** saat Anda **create point geometry** dengan Aspose.GIS. Kontrol ini memberi Anda fleksibilitas untuk memenuhi persyaratan tepat dari setiap alur kerja GIS, mulai dari visualisasi sederhana hingga analisis spasial berpresisi tinggi.

## Pertanyaan yang sering diajukan

**Q:** Apakah Aspose.GIS kompatibel dengan semua versi .NET?  
**A:** Ya, Aspose.GIS mendukung .NET Framework 4.0 ke atas, serta .NET Core/5/6.

**Q:** Bisakah saya menggunakan Aspose.GIS untuk proyek komersial?  
**A:** Tentu saja. Lisensi komersial diperlukan untuk penggunaan produksi, tetapi versi percobaan gratis tersedia untuk evaluasi.

**Q:** Apakah Aspose.GIS mendukung format data spasial lainnya?  
**A:** Ya, ia bekerja dengan lebih dari 30 format, termasuk ESRI Shapefile, GeoJSON, KML, CSV, dan banyak lagi.

**Q:** Di mana saya dapat mengunduh versi percobaan gratis?  
**A:** Anda dapat mengunduh versi percobaan gratis Aspose.GIS dari [halaman unduhan percobaan gratis Aspose.GIS](https://releases.aspose.com/).

**Q:** Bagaimana saya mendapatkan bantuan jika mengalami masalah?  
**A:** Posting pertanyaan Anda di [forum](https://forum.aspose.com/c/gis/33) komunitas Aspose.GIS dimana staf Aspose dan anggota komunitas dapat membantu.

---

**Terakhir Diperbarui:** 2026-09-15  
**Diuji Dengan:** Aspose.GIS for .NET (latest release)  
**Penulis:** Aspose

## Tutorial Terkait

- [Buat Layer Vektor dan Atur Sistem Referensi Spasialnya](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Cara Menerjemahkan Geometri ke WKT dengan Aspose.GIS untuk .NET](/gis/net/geometry-processing/translate-geometry-to-wkt/)
- [Cara Membatasi Presisi Penulisan Geometri dengan Aspose.GIS](/gis/net/geometry-processing/limit-precision-writing-geometries/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}