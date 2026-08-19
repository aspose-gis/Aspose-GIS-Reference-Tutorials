---
date: 2026-06-15
description: Pelajari cara membuat vector layer dan set layer spatial reference system
  dengan Aspose.GIS untuk .NET. Kuasai mendefinisikan spatial reference, menambahkan
  point feature, dan mengambil EPSG code.
keywords:
- create vector layer
- add point feature
- set layer coordinate system
- define epsg code
- how to set crs
linktitle: Set Layer Spatial Reference System
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  headline: Create Vector Layer and Set Layer Spatial Reference System
  type: TechArticle
- description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  name: Create Vector Layer and Set Layer Spatial Reference System
  steps:
  - name: Specify the Document Directory
    text: Begin by specifying the path to your document directory. This will be the
      location where your spatial data files are stored.
  - name: Define Spatial Reference and Set Shapefile Coordinate System
    text: SpatialReferenceSystem represents the CRS of a layer, identified by an EPSG
      code. Define the path for the Shapefile, and **define spatial reference** using
      the EPSG code (26918 in this example). This step **sets the shapefile coordinate
      system** for the layer.
  - name: Create Vector Layer
    text: '`ConstructFeature` creates a new feature object that can hold geometry
      and attribute data. Now **create vector layer** with the specified Shapefile
      path, driver type (Shapefile), and the spatial reference system you just defined.'
  - name: Add Point Feature to the Layer
    text: Construct a new feature and **add point feature** by setting its geometry
      (a `Point` with coordinates 60, 24). Then add the feature to the vector layer.
  - name: Retrieve Spatial Reference System Information (Retrieve EPSG Code)
    text: Open the Vector Layer and retrieve information about the spatial reference
      system, such as the EPSG code and the human‑readable name. This demonstrates
      how to **retrieve EPSG code** and **set layer CRS**.
  type: HowTo
- questions:
  - answer: Open the layer, create a new `SpatialReferenceSystem` with the desired
      EPSG code, assign it to `layer.SpatialReferenceSystem`, then save the layer.
    question: How do I change the CRS of an existing Shapefile?
  - answer: Yes—replace `new Point(x, y)` with `new Polygon(...)` or `new LineString(...)`
      as needed.
    question: Can I add other geometry types (e.g., polygons) using the same approach?
  - answer: Use streaming APIs (`VectorLayer.Create` with `FeatureCollection`) and
      dispose layers promptly to free resources.
    question: Is it possible to work with large datasets efficiently?
  - answer: Yes—use `Geometry.Transform(targetSrs)` to reproject geometries between
      different spatial references.
    question: Does Aspose.GIS support coordinate transformation?
  - answer: Aspose.GIS works with .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Buat Vector Layer dan Set Layer Spatial Reference System
url: /id/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Lapisan Vektor dan Atur Sistem Referensi Spasial Lapisan

## Pendahuluan
Di dalam lanskap luas Sistem Informasi Geografis (GIS), **Aspose.GIS for .NET** menonjol sebagai perpustakaan yang kuat dan berperforma tinggi yang mendukung lebih dari **70+** format vektor dan raster serta dapat memproses file yang lebih besar dari **10 GB** tanpa harus memuat seluruh dataset ke dalam memori. Dalam tutorial ini Anda akan **membuat lapisan vektor**, menentukan referensi spasialnya, **menambahkan fitur titik**, dan mengambil kode EPSG—semua dengan panduan langkah demi langkah yang jelas. Baik Anda membangun layanan pemetaan, pipeline konversi data, atau mesin analitik spasial, menguasai dasar‑dasar ini akan menjaga sistem koordinat shapefile Anda tetap akurat dan alur kerja GIS Anda dapat diandalkan.

## Jawaban Cepat
- **Apa arti “create vector layer”?** Ini membuat lapisan GIS baru (misalnya, Shapefile) yang dapat menyimpan geometri seperti titik, garis, atau poligon.  
- **Kode EPSG mana yang digunakan dalam contoh?** EPSG 26918 (NAD83 / UTM zone 18N).  
- **Bisakah saya menambahkan fitur titik setelah membuat lapisan?** Ya—gunakan `ConstructFeature()` dan tetapkan geometri `Point`.  
- **Bagaimana cara saya mengambil CRS lapisan?** Baca `layer.SpatialReferenceSystem.EpsgCode` atau `.Name`.  
- **Apakah saya memerlukan lisensi untuk Aspose.GIS?** Versi percobaan gratis tersedia; lisensi diperlukan untuk penggunaan produksi.

## Apa itu create vector layer?
Operasi **create vector layer** membuat dataset vektor baru (seperti Shapefile) yang dapat menyimpan fitur geometris dan data atribut. Di Aspose.GIS, hal ini dilakukan dengan menginstansiasi objek `VectorLayer` dengan driver dan sistem referensi spasial.

## Mengapa mengatur sistem koordinat lapisan (CRS) dengan benar?
Menetapkan sistem referensi koordinat (CRS) yang tepat memastikan setiap geometri yang Anda simpan selaras dengan dataset spasial lainnya. Dengan Aspose.GIS Anda dapat mendefinisikan CRS menggunakan kode EPSG standar, yang menjamin interoperabilitas dengan perangkat lunak GIS di seluruh dunia. Misalnya, EPSG 26918 mendefinisikan NAD83 / UTM zona 18N, proyeksi umum untuk data di bagian timur Amerika Serikat.

## Prasyarat
- Pengalaman pengembangan .NET (C# atau VB.NET).  
- Visual Studio 2022 atau yang lebih baru.  
- Perpustakaan Aspose.GIS untuk .NET – unduh **[di sini](https://releases.aspose.com/gis/net/)**.  
- Familiaritas dasar dengan sistem referensi spasial (CRS/EPSG).

## Impor Namespace
Namespace `Aspose.Gis` menyediakan kelas GIS inti, sementara `Aspose.Gis.Geometries` memberikan tipe geometri seperti `Point`.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## Bagaimana cara membuat lapisan vektor di Aspose.GIS untuk .NET?
VectorLayer mewakili dataset vektor seperti Shapefile dan menyediakan metode untuk membuat, membaca, dan mengedit fitur.  
SpatialReferenceSystem mendefinisikan sistem referensi koordinat menggunakan kode EPSG.  

Muat folder target, definisikan `SpatialReferenceSystem` dengan kode EPSG, dan panggil `VectorLayer.Create` dengan driver Shapefile. Panggilan tunggal ini membuat file `.shp` baru, menulis file `.shx` dan `.dbf` yang menyertainya, serta menyematkan metadata CRS, siap untuk penyisipan fitur secara efisien.

### Langkah 1: Tentukan Direktori Dokumen
Mulailah dengan menentukan jalur ke direktori dokumen Anda. Ini akan menjadi lokasi tempat file data spasial Anda disimpan.

```csharp
string dataDir = "Your Document Directory";
```

### Langkah 2: Definisikan Referensi Spasial dan Atur Sistem Koordinat Shapefile
SpatialReferenceSystem mewakili CRS sebuah lapisan, diidentifikasi oleh kode EPSG.  

Tentukan jalur untuk Shapefile, dan **definisikan referensi spasial** menggunakan kode EPSG (26918 dalam contoh ini). Langkah ini **mengatur sistem koordinat shapefile** untuk lapisan.

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## Bagaimana cara menambahkan fitur titik ke lapisan vektor?
`Point` adalah tipe geometri yang mewakili satu pasang koordinat X/Y.  

Buat fitur baru, tetapkan geometri `Point` dengan koordinat X/Y yang diinginkan, dan tambahkan fitur tersebut ke `VectorLayer` yang terbuka. Operasi ini menulis geometri ke dalam file `.shp` dan catatan atribut ke dalam file `.dbf` dalam satu transaksi.

### Langkah 3: Buat Lapisan Vektor
`ConstructFeature` membuat objek fitur baru yang dapat menyimpan data geometri dan atribut.  

Sekarang **buat lapisan vektor** dengan jalur Shapefile yang ditentukan, tipe driver (Shapefile), dan sistem referensi spasial yang baru saja Anda definisikan.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

### Langkah 4: Tambahkan Fitur Titik ke Lapisan
Buat fitur baru dan **tambahkan fitur titik** dengan mengatur geometri (sebuah `Point` dengan koordinat 60, 24). Kemudian tambahkan fitur tersebut ke lapisan vektor.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

### Langkah 5: Ambil Informasi Sistem Referensi Spasial (Ambil Kode EPSG)
Buka Vector Layer dan ambil informasi tentang sistem referensi spasial, seperti kode EPSG dan nama yang dapat dibaca manusia. Ini menunjukkan cara **mengambil kode EPSG** dan **mengatur CRS lapisan**.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

## Masalah Umum dan Solusinya
| Masalah | Mengapa Terjadi | Solusi |
|-------|----------------|-----|
| **Lapisan gagal dibuka** | Driver salah atau jalur file rusak | Verifikasi `Drivers.Shapefile` dan pastikan `path` mengarah ke file `.shp` yang ada. |
| **CRS yang ditampilkan tidak tepat** | Menggunakan kode EPSG yang salah | Periksa kembali kode EPSG dengan sumber yang berwenang (mis., EPSG.io). |
| **Fitur tidak tersimpan** | Tidak memanggil `layer.Add(feature)` di dalam blok `using` | Pastikan metode `Add` dijalankan sebelum lapisan dibuang. |

## Pertanyaan yang Sering Diajukan
**Q: Bagaimana cara mengubah CRS dari Shapefile yang ada?**  
A: Buka lapisan, buat `SpatialReferenceSystem` baru dengan kode EPSG yang diinginkan, tetapkan ke `layer.SpatialReferenceSystem`, kemudian simpan lapisan.

**Q: Bisakah saya menambahkan tipe geometri lain (mis., poligon) menggunakan pendekatan yang sama?**  
A: Ya—ganti `new Point(x, y)` dengan `new Polygon(...)` atau `new LineString(...)` sesuai kebutuhan.

**Q: Apakah memungkinkan bekerja dengan dataset besar secara efisien?**  
A: Gunakan API streaming (`VectorLayer.Create` dengan `FeatureCollection`) dan segera buang lapisan untuk membebaskan sumber daya.

**Q: Apakah Aspose.GIS mendukung transformasi koordinat?**  
A: Ya—gunakan `Geometry.Transform(targetSrs)` untuk memproyeksikan ulang geometri antara referensi spasial yang berbeda.

**Q: Versi .NET apa yang didukung?**  
A: Aspose.GIS bekerja dengan .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.

**Terakhir Diperbarui:** 2026-06-15  
**Diuji Dengan:** Aspose.GIS 24.11 for .NET  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Buat Lapisan Vektor dan Atur Toleransi Linearization menggunakan Aspose.GIS untuk .NET](/gis/net/geometry-processing/set-linearization-tolerance/)
- [Buat Lapisan Vektor di File GDB – Tutorial Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [referensi spasial wgs84 – Tambahkan Lapisan ke GDB menggunakan Aspose.GIS](/gis/net/layer-management/add-layer-to-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}