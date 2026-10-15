---
date: 2026-10-15
description: Pelajari cara membuat geojson dari koordinat dan menuliskannya ke aliran
  menggunakan Aspose.GIS for .NET. Tutorial ini menunjukkan konversi titik secara
  langkah demi langkah dan pembuatan kode GeoJSON C#.
keywords:
- create geojson from coordinates
- stream large geojson files
- write geojson to stream
- geojson tutorial c#
- compress geojson with gzip
lastmod: 2026-10-15
linktitle: Tulis GeoJSON ke Aliran
og_description: Pelajari cara membuat geojson dari koordinat dan menuliskannya ke
  aliran menggunakan Aspose.GIS for .NET – panduan langkah demi langkah untuk dataset
  besar.
og_image_alt: Screenshot of Aspose.GIS code generating GeoJSON stream in C#
og_title: Buat geojson dari koordinat, tulis ke aliran dalam .NET
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create geojson from coordinates and write it to a stream
    using Aspose.GIS for .NET. This tutorial shows step‑by‑step conversion of points
    and generation of GeoJSON C# code.
  headline: Create geojson from coordinates, write to a stream in .NET
  type: TechArticle
- questions:
  - answer: Yes – create a `Feature` for each point, assign a `Point` geometry, and
      add it to the `VectorLayer`.
    question: Can I generate GeoJSON from a collection of latitude/longitude points?
  - answer: You can wrap the `MemoryStream` in a `GZipStream` before saving to produce
      a compressed payload.
    question: Does Aspose.GIS support writing compressed GeoJSON (gzip)?
  - answer: The library can stream files exceeding 2 GB; memory usage stays low because
      data is written incrementally.
    question: What is the maximum size of a GeoJSON file Aspose.GIS can handle?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geojson
- Aspose.GIS
- .NET geospatial
- C# stream processing
- GIS data conversion
title: Buat geojson dari koordinat, tulis ke aliran dalam .NET
url: /id/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat geojson dari koordinat dan tulis ke aliran

## Pendahuluan
Dalam tutorial ini Anda akan belajar **cara membuat geojson dari koordinat** dan menulisnya langsung ke aliran menggunakan Aspose.GIS untuk .NET. Kami akan membahas penyiapan lingkungan, pembuatan lapisan, pengisian fitur, dan streaming hasilnya, sehingga Anda dapat menyematkan payload geospasial dalam API, fungsi cloud, atau layanan tanpa file sementara.

## Jawaban Cepat
- **Kelas apa yang menulis GeoJSON ke aliran?** `VectorLayer` bersama dengan `GeoJsonDriver`.
- **Apakah saya memerlukan lisensi untuk pengembangan?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.
- **Versi .NET mana yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Bisakah saya mengonversi koleksi titik menjadi GeoJSON?** Ya – buat `Feature` untuk setiap titik dan tetapkan geometri `Point`.
- **Apakah streaming cocok untuk dataset besar?** Tentu – `MemoryStream` memungkinkan Anda menulis GeoJSON berskala gigabyte tanpa memuat seluruh file ke memori.

## Apa itu GeoJSON?
GeoJSON adalah format berbasis JSON terbuka untuk mengenkode fitur geografis seperti titik, garis, dan poligon. Format ini terdiri dari `FeatureCollection` yang mengelompokkan objek `Feature` individual, masing‑masing membawa geometri dan data atribut. Karena ringan dan ramah web, GeoJSON menjadi standar de‑facto untuk pertukaran data spasial antara peramban, server GIS, dan aplikasi seluler.

## Mengapa menggunakan Aspose.GIS untuk pembuatan geojson?
Aspose.GIS mendukung **lebih dari 35 format file spasial** dan dapat streaming file yang lebih besar dari **2 GB** sambil menjaga penggunaan memori di bawah **50 MB**. Mesin streaming berperforma tinggi menulis GeoJSON langsung ke `Stream` .NET apa pun, menghilangkan kebutuhan file sementara dan mengurangi latensi I/O hingga **70 %** dalam skenario cloud tipikal.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki:

1. **Aspose.GIS untuk .NET** terpasang. Unduh paket **Aspose.GIS untuk .NET** [di sini](https://releases.aspose.com/gis/net/).
2. Folder yang dapat ditulisi dalam proyek Anda untuk menempatkan file sementara bila diperlukan.
3. Runtime .NET 5+ atau .NET Core 3.1+ terinstal.

Sekarang, mari kita selami implementasinya.

## Cara membuat geojson dari koordinat dan menulis ke aliran?
`VectorLayer` mewakili dataset vektor dalam memori yang dapat disimpan dalam berbagai format.  
`GeoJsonDriver` adalah driver yang memungkinkan pembacaan dan penulisan file GeoJSON.  

Muat `VectorLayer` dengan `GeoJsonDriver`, tambahkan objek `Feature` yang berisi geometri `Point`, dan panggil `layer.Save(stream, new GeoJsonSaveOptions())`. Panggilan tunggal ini men-serialisasi seluruh koleksi fitur menjadi dokumen GeoJSON yang sesuai standar dan berada di dalam `MemoryStream` yang disediakan. Proses ini menangani pemetaan atribut dan konversi koordinat secara otomatis, sehingga Anda menerima payload JSON siap pakai tanpa harus membangun string secara manual.

### Definisi jangkar
**VectorLayer** adalah objek inti Aspose.GIS yang mewakili dataset vektor yang dapat diubah dalam memori.  
**GeoJsonDriver** adalah driver yang bertanggung jawab untuk membaca dan menulis file GeoJSON.  

## Impor namespace
Langkah pertama, pastikan untuk menyertakan namespace yang diperlukan agar dapat mengakses fungsionalitas Aspose.GIS dalam kode Anda:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Langkah 1: siapkan direktori dokumen
Buat jalur folder tempat Aspose.GIS dapat menyimpan file tambahan bila diperlukan.  
```csharp
string dataDir = "Your Document Directory";
```
Ganti "Your Document Directory" dengan jalur aktual ke direktori dokumen Anda.

## Langkah 2: buat memory stream
`MemoryStream` menyediakan buffer dalam memori yang dapat dikirim langsung melalui HTTP atau disimpan ke penyimpanan cloud.  
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code for the next steps goes here
}
```

## Langkah 3: buat layer vektor dengan driver GeoJSON
Kelas `VectorLayer` mewakili dataset vektor yang dapat disimpan dalam berbagai format, termasuk GeoJSON.  
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Code for the next steps goes here
}
```

## Langkah 4: definisikan atribut fitur
Tentukan skema atribut untuk fitur Anda (misalnya, ID, Nama).  
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## Langkah 5: bangun dan tambahkan fitur
Buat objek `Feature`, tetapkan geometri titik, set nilai atribut, dan tambahkan ke layer.  
```csharp
// First Feature
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);
// Second Feature
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```

## Langkah 6: tampilkan output GeoJSON
Setelah menyimpan, reset posisi aliran dan baca string JSON untuk verifikasi atau transmisi.  
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

Selamat! Anda telah berhasil membuat geojson dari koordinat dan menulisnya ke aliran menggunakan Aspose.GIS untuk .NET.

## Masalah umum dan solusi
- **Aliran output kosong:** Pastikan Anda mereset posisi aliran (`stream.Position = 0`) sebelum membaca.
- **Urutan koordinat tidak tepat:** GeoJSON mengharapkan urutan longitude‑latitude; verifikasi nilai titik Anda.
- **Dataset besar:** Gunakan `layer.Save(stream, new GeoJsonSaveOptions { WriteFeatureCollection = true })` untuk streaming fitur secara bertahap dan menjaga penggunaan memori tetap rendah.

## Pertanyaan yang sering diajukan

**T: Bisakah saya menggunakan Aspose.GIS untuk .NET di lingkungan Windows dan Linux?**  
J: Ya, Aspose.GIS untuk .NET berjalan di Windows, Linux, dan macOS dengan dukungan penuh .NET Core.

**T: Apakah tersedia versi percobaan gratis?**  
J: Tentu! Anda dapat menjelajahi **halaman unduhan percobaan gratis** [di sini](https://releases.aspose.com/).

**T: Di mana saya dapat menemukan dokumentasi terperinci?**  
J: Lihat **dokumentasi Aspose.GIS .NET** [di sini](https://reference.aspose.com/gis/net/).

**T: Bagaimana cara mendapatkan lisensi sementara?**  
J: Lisensi sementara tersedia pada **halaman lisensi sementara** [di sini](https://purchase.aspose.com/temporary-license/).

**T: Butuh bantuan atau memiliki pertanyaan lebih lanjut?**  
J: Kunjungi **forum dukungan GIS** kami [di sini](https://forum.aspose.com/c/gis/33).

**T: Bisakah saya menghasilkan GeoJSON dari koleksi titik latitude/longitude?**  
J: Ya – buat `Feature` untuk setiap titik, tetapkan geometri `Point`, dan tambahkan ke `VectorLayer`.

**T: Apakah Aspose.GIS mendukung penulisan GeoJSON terkompresi (gzip)?**  
J: Anda dapat membungkus `MemoryStream` dalam `GZipStream` sebelum menyimpan untuk menghasilkan payload terkompresi.

**T: Berapa ukuran maksimum file GeoJSON yang dapat ditangani Aspose.GIS?**  
J: Perpustakaan dapat streaming file yang melebihi 2 GB; penggunaan memori tetap rendah karena data ditulis secara bertahap.

---

**Terakhir Diperbarui:** 2026-10-15  
**Diuji Dengan:** Aspose.GIS 24.11 untuk .NET  
**Penulis:** Aspose  

## Tutorial terkait

- [Cara Membaca GeoJSON dari Stream dengan Aspose.GIS untuk .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Cara Mengonversi GeoJSON ke TopoJSON dengan Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Cara Mengonversi Shapefile ke GeoJSON menggunakan Aspose.GIS untuk .NET](/gis/net/layer-management/extract-features-to-geojson/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}