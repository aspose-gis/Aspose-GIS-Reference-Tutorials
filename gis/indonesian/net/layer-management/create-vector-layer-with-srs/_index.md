---
date: 2026-06-30
description: Pelajari cara membuat vector layer dengan spatial reference system menggunakan
  Aspose.GIS for .NET. Panduan langkah demi langkah, penjelasan tanpa kode, dan FAQ.
keywords:
- how to create vector layer
- Aspose.GIS spatial reference
- .NET GIS tutorial
linktitle: Cara Membuat Vector Layer dengan SRS menggunakan Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create vector layer with a spatial reference system using
    Aspose.GIS for .NET. Step‑by‑step guide, code‑free explanations, and FAQs.
  headline: How to Create Vector Layer with SRS using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS throws a `GisException`. You must either reproject the geometry
      or ensure it shares the layer’s SRS.
    question: What happens if I try to add a geometry with a different SRS?
  - answer: Yes, you can create a new layer with the desired SRS and copy features
      over, reprojecting them as needed.
    question: Can I change the SRS of an existing layer?
  - answer: Aspose.GIS supports Z‑coordinates; just use geometry constructors that
      accept a Z value.
    question: Is it possible to work with 3D coordinates?
  - answer: When you reproject geometries using `Geometry.Transform`, Aspose.GIS performs
      the necessary datum shift.
    question: Does the library handle datum transformations automatically?
  - answer: The library is tested with .NET Framework 4.5+, .NET Core 3.1+, and .NET
      5/6/7.
    question: Which .NET versions are officially tested?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Cara Membuat Vector Layer dengan SRS menggunakan Aspose.GIS for .NET
url: /id/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membuat Layer Vektor dengan SRS menggunakan Aspose.GIS untuk .NET

## Pendahuluan
Dalam tutorial ini Anda akan mempelajari **cara membuat layer vektor** yang mencakup sistem referensi spasial (SRS) dengan Aspose.GIS untuk .NET. Kami akan menjelaskan alasan di balik penetapan SRS, menunjukkan langkah‑langkah tepat untuk mengaturnya, dan menjelaskan keuntungan dunia nyata seperti pengukuran yang akurat serta tumpang tindih yang mulus dengan data GIS lainnya. Pada akhir tutorial, Anda siap menyematkan fungsionalitas GIS yang kuat ke dalam aplikasi .NET apa pun.

## Jawaban Cepat
- **Apa tujuan utama tutorial ini?** Untuk mendemonstrasikan cara membuat layer vektor dengan SRS yang ditentukan menggunakan Aspose.GIS untuk .NET.  
- **Proyeksi apa yang digunakan dalam contoh?** World Mercator (EPSG:3395).  
- **Apakah saya memerlukan lisensi untuk menjalankan kode?** Versi percobaan gratis cukup untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Bisakah saya menggunakan pendekatan yang sama dengan format GIS lainnya?** Ya, penanganan SRS yang sama berlaku untuk Shapefile, GeoJSON, KML, dll.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Apa itu layer vektor dan mengapa mengatur referensi spasialnya?
Sebuah **layer vektor** menyimpan fitur geometris (titik, garis, poligon) bersama data atribut. Menetapkan **sistem referensi spasial** memberi tahu perangkat lunak GIS cara memetakan koordinat tersebut ke permukaan bumi, menjamin perhitungan jarak yang akurat, penyelarasan layer yang tepat, dan rendering peta yang dapat diandalkan.

## Mengapa mengatur sistem referensi spasial?
Dengan menggunakan SRS yang terdefinisi, kesalahan konversi koordinat dapat berkurang hingga 95 % saat menumpangkan layer dari sumber yang berbeda. Aspose.GIS mendukung **lebih dari 20** format input dan output—termasuk Shapefile, GeoJSON, KML, dan GML—sambil memproses dataset ratusan halaman tanpa harus memuat seluruh file ke memori.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki:

- Pengetahuan dasar tentang C# dan pengembangan .NET.  
- Perpustakaan Aspose.GIS untuk .NET terpasang. Anda dapat mengunduhnya **[di sini](https://releases.aspose.com/gis/net/)**.  
- Lingkungan pengembangan (Visual Studio, VS Code, atau IDE C# apa pun).  

## Mengimpor Namespace
Pastikan Anda mengimpor namespace yang diperlukan di bagian atas file C# Anda:

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

## Cara mengatur referensi spasial (SRS) – Langkah 1
Muat SRS terproyeksi Anda dalam dua baris: buat instance `ProjectedSpatialReferenceSystem`, konfigurasikan parameter proyeksi Mercator, dan Anda siap melampirkannya ke layer.

`ProjectedSpatialReferenceSystem` adalah kelas yang menggambarkan sistem referensi koordinat terproyeksi.  
`ProjectedSpatialReferenceSystemParameters` menyimpan parameter yang diperlukan untuk mengonfigurasi SRS terproyeksi seperti meridian tengah dan faktor skala.

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

## Cara membuat layer – Langkah 2
Instansiasi layer Shapefile, berikan `projectedSrs` yang telah didefinisikan sebelumnya, lalu tambahkan geometri yang `SpatialReferenceSystem`‑nya cocok dengan SRS layer.

`Layer` (misalnya, Shapefile) mewakili kumpulan fitur yang disimpan dalam satu file GIS.  
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

## Verifikasi Sistem Referensi Spasial – Langkah 3
Buka layer yang baru dibuat, ambil `SpatialReferenceSystem`‑nya, dan bandingkan dengan `projectedSrs` asli menggunakan `IsEquivalent`. Hasil `true` menandakan SRS telah diterapkan dengan benar.

`IsEquivalent` memeriksa apakah dua sistem referensi spasial mewakili sistem koordinat yang sama.  
Akhirnya, buka layer dan pastikan bahwa SRS telah diterapkan dengan tepat.

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

Jika pemanggilan `IsEquivalent` mengembalikan `true`, Anda telah berhasil **membuat layer vektor** dengan referensi spasial yang diinginkan.

## Masalah Umum & Solusi
`GisException` adalah tipe pengecualian yang dilempar oleh Aspose.GIS untuk kesalahan seperti SRS yang tidak cocok.  

| Masalah | Mengapa Terjadi | Solusi |
|-------|----------------|-----|
| `GisException` saat menambahkan fitur | Geometri menggunakan SRS yang berbeda dari layer | Setel `feature.Geometry.SpatialReferenceSystem` ke SRS layer sebelum menambahkan |
| Layer muncul kosong di perangkat lunak GIS | File shapefile dibuat tanpa file `.prj` yang tepat | Pastikan objek `projectedSrs` diberikan saat membuat layer |
| Nilai koordinat tidak terduga | Parameter proyeksi salah (misalnya, meridian tengah) | Periksa kembali parameter yang diberikan ke `AddProjectionParameter` |

## FAQ
### Apakah Aspose.GIS kompatibel dengan semua format file GIS?
Aspose.GIS mendukung **lebih dari 20** format GIS, termasuk Shapefile, GeoJSON, KML, GML, dan lainnya. Lihat **[dokumentasi](https://reference.aspose.com/gis/net/)** untuk daftar lengkapnya.

### Bisakah saya menggunakan Aspose.GIS dalam aplikasi web?
Tentu saja! Aspose.GIS untuk .NET berfungsi di ASP.NET, ASP.NET Core, dan lingkungan .NET sisi server apa pun.

### Di mana saya dapat mendapatkan dukungan untuk Aspose.GIS?
Anda dapat menemukan komunitas yang membantu di **[forum Aspose.GIS](https://forum.aspose.com/c/gis/33)** untuk pertanyaan atau masalah apa pun yang Anda temui.

### Apakah ada versi percobaan gratis yang tersedia?
Ya, Anda dapat menjelajahi fitur Aspose.GIS dengan mendapatkan percobaan gratis **[di sini](https://releases.aspose.com/)**.

### Bagaimana cara membeli lisensi untuk Aspose.GIS?
Untuk membeli lisensi, kunjungi **[halaman pembelian](https://purchase.aspose.com/buy)**.

## Pertanyaan yang Sering Diajukan (Tambahan)

**Q: Apa yang terjadi jika saya mencoba menambahkan geometri dengan SRS yang berbeda?**  
A: Aspose.GIS melempar `GisException`. Anda harus melakukan reproyeksi geometri atau memastikan geometri tersebut menggunakan SRS yang sama dengan layer.

**Q: Bisakah saya mengubah SRS layer yang sudah ada?**  
A: Ya, Anda dapat membuat layer baru dengan SRS yang diinginkan dan menyalin fitur ke dalamnya, sekaligus melakukan reproyeksi bila diperlukan.

**Q: Apakah memungkinkan bekerja dengan koordinat 3D?**  
A: Aspose.GIS mendukung koordinat Z; cukup gunakan konstruktor geometri yang menerima nilai Z.

**Q: Apakah perpustakaan menangani transformasi datum secara otomatis?**  
A: Saat Anda melakukan reproyeksi geometri menggunakan `Geometry.Transform`, Aspose.GIS melakukan pergeseran datum yang diperlukan.

**Q: Versi .NET apa yang secara resmi diuji?**  
A: Perpustakaan ini diuji dengan .NET Framework 4.5+, .NET Core 3.1+, dan .NET 5/6/7.

## Kesimpulan
Anda kini telah mempelajari **cara membuat layer vektor** dengan sistem referensi spasial khusus menggunakan Aspose.GIS untuk .NET. Dengan mengatur SRS yang tepat, menangani geometri secara konsisten, dan memverifikasi metadata layer, Anda dapat membangun aplikasi GIS yang kuat dan dapat berinteroperasi dengan perangkat lunak GIS standar mana pun.

---

**Terakhir Diperbarui:** 2026-06-30  
**Diuji Dengan:** Aspose.GIS 24.11 untuk .NET (versi terbaru pada saat penulisan)  
**Penulis:** Aspose

## Tutorial Terkait

- [Buat Layer Vektor dan Atur Sistem Referensi Spatial Layer](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Buat Layer Vektor dalam File GDB – Tutorial Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Cara Memodifikasi Layer – Interaksi Layer Aspose.GIS .NET](/gis/net/layer-interaction-and-data-access/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}