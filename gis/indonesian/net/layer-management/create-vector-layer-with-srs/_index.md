---
date: 2026-01-15
description: Jelajahi Aspose.GIS untuk .NET untuk membuat lapisan vektor dengan sistem
  referensi spasial. Pelajari cara mengatur SRS, membuat lapisan, dan mengelola data
  GIS. Unduh sekarang!
linktitle: Create Vector Layer with SRS
second_title: Aspose.GIS .NET API
title: Buat Lapisan Vektor dengan SRS
url: /id/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create Vector Layer with SRS

## Introduction
Aspose.GIS for .NET adalah perpustakaan kuat yang memungkinkan pengembang untuk **membuat objek layer vektor** dan bekerja dengan data sistem informasi geografis (GIS) secara mulus dalam aplikasi .NET. Dalam tutorial ini, kami akan menjelaskan cara membuat layer vektor dengan sistem referensi spasial (SRS), mengapa Anda perlu mengatur referensi spasial, dan manfaat apa yang diberikan pada proyek dunia nyata. Pada akhir panduan ini, Anda akan dapat mengintegrasikan kemampuan GIS ke dalam solusi .NET Anda dengan percaya diri.

## Quick Answers
- **Apa tujuan utama tutorial ini?** Menunjukkan cara membuat layer vektor dengan SRS yang ditentukan menggunakan Aspose.GIS for .NET.  
- **Proyeksi apa yang digunakan dalam contoh?** World Mercator (EPSG:3395).  
- **Apakah saya memerlukan lisensi untuk menjalankan kode?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Bisakah saya menggunakan pendekatan yang sama dengan format GIS lain?** Ya, penanganan SRS yang sama berlaku untuk Shapefile, GeoJSON, KML, dll.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## What is a vector layer and why set its spatial reference?
Sebuah **layer vektor** menyimpan fitur geometris (titik, garis, poligon) bersama dengan data atribut. Menetapkan **referensi spasial** (SRS) memberi tahu perangkat lunak GIS cara menafsirkan koordinat tersebut pada permukaan bumi. Mengatur SRS yang tepat memastikan pengukuran yang akurat, overlay yang benar dengan layer lain, dan visualisasi peta yang dapat diandalkan.

## Prerequisites
Sebelum kita mulai, pastikan Anda memiliki:

- Pengetahuan dasar tentang C# dan pengembangan .NET.  
- Perpustakaan Aspose.GIS for .NET terpasang. Anda dapat mengunduhnya **[di sini](https://releases.aspose.com/gis/net/)**.  
- Lingkungan pengembangan (Visual Studio, VS Code, atau IDE C# apa pun).  

## Import Namespaces
Pastikan Anda telah mengimpor namespace yang diperlukan di bagian atas file C# Anda:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## How to set spatial reference (SRS) – Step 1
Mari buat **sistem referensi spasial terproyeksi** menggunakan proyeksi World Mercator sebagai contoh. Ini menunjukkan **cara mengatur srs** untuk sebuah layer.

```csharp
var parameters = new ProjectedSpatialReferenceSystemParameters
{
    Name = "WGS 84 / World Mercator",
    Base = SpatialReferenceSystem.Wgs84,
    ProjectionMethodName = "Mercator_1SP",
    LinearUnit = Unit.Meter,
    XAxis = new Axis("Easting", AxisDirection.East),
    YAxis = new Axis("Northing", AxisDirection.North),
    AxisesOrder = ProjectedAxisesOrder.XY,
};
parameters.AddProjectionParameter("central_meridian", 0);
parameters.AddProjectionParameter("scale_factor", 1);
parameters.AddProjectionParameter("false_easting", 0);
parameters.AddProjectionParameter("false_northing", 0);
var projectedSrs = SpatialReferenceSystem.CreateProjected(parameters, Identifier.Epsg(3395));
```

## How to create layer – Step 2
Sekarang kita akan **membuat layer vektor** (Shapefile) dan menambahkan fitur yang menggunakan SRS yang baru saja kita definisikan. Bagian ini menjawab **cara membuat layer** dengan Aspose.GIS.

```csharp
using (var layer = Drivers.Shapefile.CreateLayer(dataDir + "filepath_out.shp", new ShapefileOptions(), projectedSrs))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2);
    layer.Add(feature);
    feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2) { SpatialReferenceSystem = SpatialReferenceSystem.Nad83 };
    try
    {
        layer.Add(feature); // This will throw an exception as the geometry has a different SRS
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```

> **Tip pro:** Selalu pastikan bahwa `SpatialReferenceSystem` pada geometri cocok dengan SRS layer sebelum menambahkannya. Nilai SRS yang tidak cocok akan memicu `GisException`, seperti yang ditunjukkan di atas.

## Verify Spatial Reference System – Step 3
Akhirnya, buka layer dan konfirmasi bahwa SRS telah diterapkan dengan benar.

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

Jika pemanggilan `IsEquivalent` mengembalikan `true`, Anda telah berhasil **membuat layer vektor** dengan referensi spasial yang diinginkan.

## Common Issues & Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| `GisException` saat menambahkan fitur | Geometri menggunakan SRS yang berbeda dari layer | Atur `feature.Geometry.SpatialReferenceSystem` ke SRS layer sebelum menambahkannya |
| Layer muncul kosong di perangkat lunak GIS | Shapefile dibuat tanpa file `.prj` yang tepat | Pastikan objek `projectedSrs` diberikan saat membuat layer |
| Nilai koordinat tidak terduga | Parameter proyeksi salah (misalnya, meridian tengah) | Periksa kembali parameter yang diberikan ke `AddProjectionParameter` |

## FAQs
### Apakah Aspose.GIS kompatibel dengan semua format file GIS?
Aspose.GIS mendukung berbagai format GIS, termasuk Shapefile, GeoJSON, KML, dan lainnya. Lihat **[dokumentasi](https://reference.aspose.com/gis/net/)** untuk daftar lengkapnya.

### Bisakah saya menggunakan Aspose.GIS dalam aplikasi web?
Tentu saja! Aspose.GIS for .NET bersifat serbaguna dan dapat digunakan dalam aplikasi web, aplikasi desktop, bahkan aplikasi seluler.

### Di mana saya dapat mendapatkan dukungan untuk Aspose.GIS?
Anda dapat menemukan komunitas yang membantu di **[forum Aspose.GIS](https://forum.aspose.com/c/gis/33)** untuk pertanyaan atau masalah apa pun yang Anda temui.

### Apakah ada versi percobaan gratis yang tersedia?
Ya, Anda dapat menjelajahi fitur Aspose.GIS dengan mendapatkan percobaan gratis **[di sini](https://releases.aspose.com/)**.

### Bagaimana cara membeli lisensi untuk Aspose.GIS?
Untuk membeli lisensi, kunjungi **[halaman pembelian](https://purchase.aspose.com/buy)**.

## Frequently Asked Questions (Additional)

**Q: Apa yang terjadi jika saya mencoba menambahkan geometri dengan SRS yang berbeda?**  
A: Aspose.GIS akan melempar `GisException`. Anda harus melakukan reproyeksi geometri atau memastikan geometri tersebut menggunakan SRS yang sama dengan layer.

**Q: Bisakah saya mengubah SRS layer yang sudah ada?**  
A: Ya, Anda dapat membuat layer baru dengan SRS yang diinginkan dan menyalin fitur ke dalamnya, sambil melakukan reproyeksi bila diperlukan.

**Q: Apakah memungkinkan bekerja dengan koordinat 3D?**  
A: Aspose.GIS mendukung koordinat Z; cukup gunakan konstruktor geometri yang menerima nilai Z.

**Q: Apakah perpustakaan ini menangani transformasi datum secara otomatis?**  
A: Saat Anda melakukan reproyeksi geometri menggunakan `Geometry.Transform`, Aspose.GIS melakukan pergeseran datum yang diperlukan.

**Q: Versi .NET mana yang secara resmi diuji?**  
A: Perpustakaan ini diuji dengan .NET Framework 4.5+, .NET Core 3.1+, dan .NET 5/6/7.

## Conclusion
Anda kini telah mempelajari cara **membuat layer vektor** dengan sistem referensi spasial khusus menggunakan Aspose.GIS for .NET. Dengan mengatur SRS yang tepat, menangani geometri secara konsisten, dan memverifikasi metadata layer, Anda dapat membangun aplikasi yang didukung GIS secara kuat dan dapat berinteroperasi dengan perangkat lunak GIS standar mana pun.

---

**Last Updated:** 2026-01-15  
**Tested With:** Aspose.GIS 24.11 for .NET (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}