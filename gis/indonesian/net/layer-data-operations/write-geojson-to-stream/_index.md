---
date: 2026-05-21
description: Pelajari cara menulis GeoJSON ke stream menggunakan Aspose.GIS untuk
  .NET. Tutorial geojson .net ini menunjukkan konversi titik langkah demi langkah
  dan pembuatan kode GeoJSON C#.
keywords:
- how to write geojson
- convert points geojson
- geojson tutorial .net
- generate geojson c#
linktitle: Menulis GeoJSON ke Stream
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to write GeoJSON to stream using Aspose.GIS for .NET. This
    geojson tutorial .net shows step‑by‑step conversion of points and generation of
    GeoJSON C# code.
  headline: How to Write GeoJSON to Stream with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes – create a `Feature` for each point, assign a `Point` geometry, and
      add it to the `VectorLayer`.
    question: Can I generate GeoJSON from a collection of latitude/longitude points?
  - answer: You can wrap the `MemoryStream` in a `GZipStream` before saving to produce
      a compressed payload.
    question: Does Aspose.GIS support writing compressed GeoJSON (gzip)?
  - answer: The library can stream files exceeding 2 GB; memory usage stays low because
      data is written incrementally.
    question: What is the maximum size of a GeoJSON file Aspose.GIS can handle?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Cara Menulis GeoJSON ke Stream dengan Aspose.GIS untuk .NET
url: /id/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tulis GeoJSON ke Stream

## Pendahuluan
Dalam tutorial ini Anda akan belajar **cara menulis GeoJSON ke stream** dalam aplikasi .NET menggunakan Aspose.GIS. Kami akan membahas setiap langkah, mulai dari menyiapkan lingkungan hingga menghasilkan dokumen GeoJSON yang valid, sehingga Anda dapat mengintegrasikan data geospasial dengan mulus ke dalam layanan Anda.

## Jawaban Cepat
- **Apa kelas utama untuk output GeoJSON?** `VectorLayer` dengan `GeoJsonDriver`.
- **Apakah saya memerlukan lisensi untuk pengembangan?** Trial gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Bisakah saya mengonversi koleksi titik ke GeoJSON?** Ya – gunakan kelas `Feature` dan definisikan geometri titik.
- **Apakah streaming didukung untuk dataset besar?** Tentu; `MemoryStream` memungkinkan Anda menulis tanpa file perantara.

## Apa itu GeoJSON?
GeoJSON adalah format standar terbuka untuk mengkodekan berbagai struktur data geografis menggunakan JSON. Ini mendefinisikan objek seperti FeatureCollection, Feature, dan tipe geometri (Point, LineString, Polygon). Representasi ringan dan ramah web ini memungkinkan pertukaran dan visualisasi data spasial yang mudah di banyak platform dan bahasa pemrograman.

## Mengapa menggunakan Aspose.GIS untuk pembuatan GeoJSON?
Aspose.GIS mendukung lebih dari 30 format file spasial dan dapat memproses file lebih besar dari 2 GB tanpa memuat seluruh dokumen ke memori. Mesin streaming berperforma tinggi-nya menulis GeoJSON langsung ke stream, mengurangi beban I/O. Hal ini menjadikannya ideal untuk beban kerja geospasial skala perusahaan, layanan cloud, dan aplikasi real‑time.

## Prasyarat
Sebelum kita memulai tutorial, pastikan Anda memiliki prasyarat berikut:
1. Aspose.GIS for .NET Library: Pastikan Anda telah menginstal library Aspose.GIS untuk .NET. Anda dapat mengunduhnya [di sini](https://releases.aspose.com/gis/net/).
2. Direktori Dokumen: Siapkan direktori dokumen dalam proyek Anda, dan catat jalurnya.

Sekarang, mari kita mulai tutorial!

## Bagaimana cara menulis GeoJSON ke stream?
VectorLayer mewakili dataset vektor yang dapat disimpan dalam berbagai format, termasuk GeoJSON.  
GeoJsonDriver adalah driver yang digunakan Aspose.GIS untuk membaca dan menulis file GeoJSON.  
`layer.Save` menulis konten layer ke stream yang diberikan menggunakan opsi penyimpanan yang ditentukan.  

Muat `VectorLayer` dengan `GeoJsonDriver`, tambahkan fitur yang berisi geometri titik, lalu panggil `layer.Save(stream, new GeoJsonSaveOptions())`. Ini menulis dokumen GeoJSON yang lengkap dan sesuai standar langsung ke `MemoryStream` yang disediakan dalam beberapa baris kode saja. Metode ini menyerialisasi koleksi fitur, menangani data atribut dan konversi geometri secara otomatis, sehingga Anda mendapatkan payload JSON siap pakai tanpa manipulasi string manual.

## Impor Namespace
Pertama-tama, pastikan untuk menyertakan namespace yang diperlukan untuk mengakses fungsionalitas Aspose.GIS dalam kode Anda:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Langkah 1: Siapkan Direktori Dokumen
```csharp
string dataDir = "Your Document Directory";
```
Ganti "Your Document Directory" dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 2: Buat Memory Stream
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code for the next steps goes here
}
```

## Langkah 3: Buat Vector Layer dengan GeoJSON Driver
Kelas `VectorLayer` mewakili dataset vektor yang dapat disimpan dalam berbagai format, termasuk GeoJSON.  
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Code for the next steps goes here
}
```

## Langkah 4: Definisikan Atribut Fitur
Definisikan skema atribut untuk fitur Anda (mis., ID, Name).  
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## Langkah 5: Bangun dan Tambahkan Fitur
Buat objek `Feature`, tetapkan geometri titik, atur nilai atribut, dan tambahkan ke layer.  
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

## Langkah 6: Tampilkan Output GeoJSON
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

Selamat! Anda telah berhasil menulis GeoJSON ke stream menggunakan Aspose.GIS untuk .NET.

## Masalah Umum dan Solusinya
- **Stream output kosong:** Pastikan Anda mengatur ulang posisi stream (`stream.Position = 0`) sebelum membaca.
- **Urutan koordinat tidak tepat:** GeoJSON mengharapkan urutan longitude‑latitude; verifikasi nilai titik Anda.
- **Dataset besar:** Gunakan `layer.Save(stream, new GeoJsonSaveOptions { WriteFeatureCollection = true })` untuk streaming fitur secara bertahap.

## Pertanyaan yang Sering Diajukan
### Bisakah saya menggunakan Aspose.GIS untuk .NET di lingkungan Windows dan Linux?
Ya, Aspose.GIS untuk .NET kompatibel dengan sistem Windows dan Linux.  

### Apakah tersedia trial gratis?
Tentu! Anda dapat menjelajahi trial gratis [di sini](https://releases.aspose.com/).  

### Di mana saya dapat menemukan dokumentasi detail?
Lihat dokumentasi [di sini](https://reference.aspose.com/gis/net/).  

### Bagaimana cara mendapatkan lisensi sementara?
Lisensi sementara tersedia [di sini](https://purchase.aspose.com/temporary-license/).  

### Butuh bantuan atau memiliki pertanyaan lain?
Kunjungi forum dukungan kami [di sini](https://forum.aspose.com/c/gis/33).  

**Q: Bisakah saya menghasilkan GeoJSON dari koleksi titik latitude/longitude?**  
A: Ya – buat `Feature` untuk setiap titik, tetapkan geometri `Point`, dan tambahkan ke `VectorLayer`.  

**Q: Apakah Aspose.GIS mendukung penulisan GeoJSON terkompresi (gzip)?**  
A: Anda dapat membungkus `MemoryStream` dengan `GZipStream` sebelum menyimpan untuk menghasilkan payload terkompresi.  

**Q: Berapa ukuran maksimum file GeoJSON yang dapat ditangani oleh Aspose.GIS?**  
A: Library ini dapat streaming file yang melebihi 2 GB; penggunaan memori tetap rendah karena data ditulis secara bertahap.  

---

**Terakhir Diperbarui:** 2026-05-21  
**Diuji Dengan:** Aspose.GIS 24.11 untuk .NET  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Cara Membaca GeoJSON dari Stream dengan Aspose.GIS untuk .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Cara Mengonversi GeoJSON ke TopoJSON dengan Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Cara Mengonversi Shapefile ke GeoJSON menggunakan Aspose.GIS untuk .NET](/gis/net/layer-management/extract-features-to-geojson/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}