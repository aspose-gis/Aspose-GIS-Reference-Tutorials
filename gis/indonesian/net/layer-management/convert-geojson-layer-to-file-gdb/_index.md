---
date: 2026-06-20
description: Pelajari cara mengonversi geojson ke gdb dengan Aspose.GIS untuk .NET.
  Panduan langkah demi langkah ini mencakup membaca GeoJSON di C#, membuat File Geodatabase,
  dan menangani masalah umum.
keywords:
- convert geojson to gdb
- how to convert geojson
- read geojson c#
- asp.net geojson conversion
linktitle: Konversi Layer GeoJSON ke GDB
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to convert geojson to gdb with Aspose.GIS for .NET. This
    step‑by‑step guide covers reading GeoJSON in C#, creating a File Geodatabase,
    and handling common issues.
  headline: How to Convert GeoJSON to GDB Using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Converting a GeoJSON layer to a GDB with Aspose.GIS for .NET.
    question: What does this guide teach?
  - answer: '*convert geojson to gdb*.'
    question: Which primary keyword is targeted?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.
    question: Supported .NET versions?
  - answer: Roughly 10‑15 minutes for a basic conversion.
    question: Implementation time?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Cara Mengonversi GeoJSON ke GDB Menggunakan Aspose.GIS untuk .NET
url: /id/net/layer-management/convert-geojson-layer-to-file-gdb/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengonversi GeoJSON ke GDB Menggunakan Aspose.GIS untuk .NET

## Pendahuluan
Jika Anda mencari **convert geojson to gdb** dengan cepat dan dapat diandalkan, Anda berada di tempat yang tepat. Tutorial ini memandu Anda melalui setiap langkah—mulai dari membaca file GeoJSON di C# hingga membuat File Geodatabase (GDB) dengan Aspose.GIS. Anda akan melihat mengapa Aspose.GIS menjadi perpustakaan pilihan untuk konversi data geospasial, cara menyiapkan lingkungan, dan cara menjalankan konversi dalam beberapa menit.

## Jawaban Cepat
- **Apa yang diajarkan panduan ini?** Mengonversi lapisan GeoJSON ke GDB dengan Aspose.GIS untuk .NET.  
- **Kata kunci utama apa yang ditargetkan?** *convert geojson to gdb*.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengujian; lisensi komersial diperlukan untuk produksi.  
- **Versi .NET yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Waktu implementasi?** Sekitar 10‑15 menit untuk konversi dasar.

## Apa itu GeoJSON dan File GDB?
GeoJSON adalah format ringan berbasis teks untuk fitur geografis, sementara File GDB adalah basis data geospasial ESRI berbasis folder dengan kinerja tinggi.  
GeoJSON menyimpan titik, garis, dan poligon sebagai teks biasa, memudahkan berbagi dan mengedit, sedangkan File GDB menyimpan data dalam file biner yang memberikan kueri spasial cepat dan penanganan atribut yang kuat. Bersama-sama keduanya mencakup pertukaran yang ramah web dan pemrosesan GIS desktop berkecepatan tinggi.

## Mengapa menggunakan Aspose.GIS untuk konversi data geospasial?
Aspose.GIS menyediakan API tunggal yang konsisten yang menyembunyikan keanehan format‑spesifik. Ia mendukung **30+ format geospasial**, dapat memproses file hingga **2 GB** tanpa memuat seluruh dataset ke memori, dan secara otomatis mempertahankan sistem referensi koordinat. Ini berarti Anda menghabiskan lebih sedikit waktu menulis parser dan lebih banyak waktu membangun logika aplikasi Anda.

## Prasyarat
- Familiaritas dengan C# dan struktur proyek .NET.  
- Aspose.GIS untuk .NET terinstal. Jika Anda belum menginstalnya, unduh dari [here](https://releases.aspose.com/gis/net/) dan ikuti panduan instalasi. Anda juga dapat menjelajahi produk Aspose lainnya di [here](https://releases.aspose.com/).

## Impor Namespace
Langkah pertama adalah membawa namespace yang diperlukan ke dalam ruang lingkup.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Cara membaca GeoJSON di C#?
Muat file GeoJSON dengan kelas `GeoJsonReader`, yang mem‑parsing JSON dan membuat `FeatureCollection` di memori. Pembaca secara otomatis mendeteksi sistem referensi koordinat, sehingga Anda tidak perlu menangani parsing CRS secara manual. Ia juga mendukung streaming file besar, mempertahankan tipe atribut, dan dapat digabungkan dengan transformasi geometri khusus jika diperlukan.

```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    // Add attributes
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    // Construct and add features
    Feature firstFeature = layer.ConstructFeature();
    firstFeature.Geometry = new Point(33.97, -118.25);
    firstFeature.SetValue("name", "John");
    firstFeature.SetValue("age", 23);
    layer.Add(firstFeature);
    Feature secondFeature = layer.ConstructFeature();
    secondFeature.Geometry = new Point(35.81, -96.28);
    secondFeature.SetValue("name", "Mary");
    secondFeature.SetValue("age", 54);
    layer.Add(secondFeature);
}
```

## Langkah 1: Siapkan Lapisan GeoJSON
Buat file GeoJSON sementara yang berisi atribut dan fitur yang ingin Anda konversi. Contoh ini menambahkan dua fitur titik sederhana.

```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```

## Langkah 2: Salin Dataset Uji
Untuk menjaga data uji asli tetap tidak tersentuh, gandakan dataset File GDB yang ada. Ini memastikan lingkungan bersih untuk konversi.

```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        // Copy attributes
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        // Add features
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```

## Langkah 3: Konversi GeoJSON ke GDB
`FileGdb` mewakili kontainer File Geodatabase dan menyediakan metode untuk mengelola lapisan. Buka lapisan GeoJSON, buat lapisan baru di dalam File GDB yang disalin, salin atribut, dan transfer setiap fitur. Ini adalah inti proses **konversi Aspose.GIS**.

CODE_BLOCK_PLACEHOLDER_4_END

## Cara mengonversi GeoJSON ke GDB?
Muat GeoJSON dengan `GeoJsonReader`, buat objek `FileGdb` yang menunjuk ke folder tujuan Anda, buat lapisan fitur baru, lalu iterasi setiap fitur untuk menyisipkannya. Praktiknya adalah alur tiga langkah—baca, buat, salin—yang selesai dalam kurang dari satu menit untuk dataset tipikal.

## Masalah Umum dan Solusinya
- **Referensi spasial hilang:** Pastikan GeoJSON sumber menyertakan definisi CRS atau secara eksplisit set `SpatialReferenceSystem.Wgs84` saat membuat lapisan GDB.  
- **Ketidaksesuaian tipe atribut:** Tipe data atribut di GeoJSON harus cocok dengan skema target; jika tidak, Aspose.GIS akan melemparkan pengecualian.  
- **Kesalahan akses file:** Verifikasi bahwa folder tujuan memiliki izin menulis dan tidak ada proses lain yang mengunci file GDB.

## Pertanyaan yang Sering Diajukan
### Apakah Aspose.GIS kompatibel dengan .NET framework terbaru?
Ya, Aspose.GIS bekerja dengan .NET Framework 4.5+, .NET Core 3.1+, .NET 5, dan .NET 6+.

### Bisakah saya mengonversi format geospasial lain menggunakan Aspose.GIS?
Tentu saja! Aspose.GIS mendukung lebih dari 30 format input dan output, termasuk Shapefile, KML, GML, dan SQLite.

### Apakah ada versi percobaan yang tersedia untuk Aspose.GIS?
Ya, Anda dapat menjelajahi fungsionalitas Aspose.GIS dengan mengunduh versi percobaan [here](https://releases.aspose.com/).

### Bagaimana saya dapat mendapatkan dukungan untuk pertanyaan terkait Aspose.GIS?
Kunjungi forum Aspose.GIS [forum](https://forum.aspose.com/c/gis/33) untuk bantuan khusus dari komunitas dan tim produk.

### Bisakah saya memperoleh lisensi sementara untuk Aspose.GIS?
Ya, Anda dapat mengamankan lisensi sementara [here](https://purchase.aspose.com/temporary-license/).

---

**Last Updated:** 2026-06-20  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose

## Tutorial Terkait

- [Buat Dataset File Geodatabase .NET dengan Aspose.GIS](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Baca Fitur dari File Geodatabase di Aspose.GIS](/gis/net/layer-data-operations/read-features-from-file-geodatabase/)
- [Buat Lapisan Vektor di File GDB – Tutorial Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}