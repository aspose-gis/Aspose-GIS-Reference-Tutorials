---
date: 2026-01-10
description: Pelajari cara mengonversi GeoJSON ke File GDB dengan Aspose.GIS untuk
  .NET. Panduan langkah demi langkah ini mencakup konversi data geospasial dan konversi
  Aspose GIS.
linktitle: Convert GeoJSON Layer to File GDB
second_title: Aspose.GIS .NET API
title: Cara Mengonversi GeoJSON ke File GDB Menggunakan Aspose.GIS untuk .NET
url: /id/net/layer-management/convert-geojson-layer-to-file-gdb/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengonversi GeoJSON ke File GDB Menggunakan Aspose.GIS untuk .NET

## Pendahuluan
Jika Anda bertanya-tanya **cara mengonversi GeoJSON** menjadi File Geodatabase (File GDB) untuk alur kerja GIS yang kuat, Anda berada di tempat yang tepat. Dalam tutorial ini kami akan memandu Anda melalui seluruh proses dengan Aspose.GIS untuk .NET, menunjukkan mengapa perpustakaan ini menjadi pilihan utama untuk konversi data geospasial dan bagaimana Anda dapat dengan cepat membuat file geodatabase dari lapisan GeoJSON.

## Jawaban Cepat
- **Apa yang dibahas dalam tutorial ini?** Mengonversi lapisan GeoJSON ke File GDB menggunakan Aspose.GIS untuk .NET.  
- **Kata kunci utama apa yang ditargetkan?** *how to convert geojson*.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengujian; lisensi komersial diperlukan untuk produksi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk konversi dasar.

## Apa itu GeoJSON dan File GDB?
GeoJSON adalah format ringan berbasis teks untuk mengenkode berbagai struktur data geografis. File Geodatabase (File GDB) adalah format berbasis folder dengan kinerja tinggi yang digunakan oleh banyak aplikasi GIS desktop. Mengonversi di antara keduanya memungkinkan Anda memanfaatkan keunggulan kedua format dalam proyek Anda.

## Mengapa menggunakan Aspose.GIS untuk konversi data geospasial?
Aspose.GIS menawarkan API terpadu yang menyederhanakan kompleksitas penanganan format. Dengan dukungan bawaan untuk **geojson to file gdb**, Anda dapat:

- Membaca GeoJSON dalam C# tanpa parser pihak ketiga.  
- Membuat file geodatabase secara programatis.  
- Mempertahankan data atribut dan informasi referensi spasial secara otomatis.  

## Prasyarat
Sebelum Anda memulai, pastikan Anda memiliki:

- Pengetahuan kerja tentang pemrograman .NET.  
- Aspose.GIS untuk .NET terpasang. Jika belum, unduh dari [here](https://releases.aspose.com/gis/net/) dan ikuti petunjuk instalasi.

## Impor Namespace
Langkah pertama adalah memasukkan namespace yang diperlukan ke dalam ruang lingkup.

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

## Langkah 1: Siapkan Lapisan GeoJSON
Buat file GeoJSON sementara yang berisi atribut dan fitur yang ingin Anda konversi. Contoh ini menambahkan dua fitur titik sederhana.

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

## Langkah 2: Salin Dataset Uji
Untuk menjaga data uji asli tetap tidak tersentuh, gandakan dataset File GDB yang ada. Ini memastikan lingkungan bersih untuk konversi.

```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```

## Langkah 3: Konversi GeoJSON ke File GDB
Buka lapisan GeoJSON, buat lapisan baru di dalam File GDB yang disalin, salin atribut, dan transfer setiap fitur. Ini adalah inti dari proses **aspose gis conversion**.

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

## Masalah Umum dan Solusinya
- **Referensi spasial hilang:** Pastikan GeoJSON sumber menyertakan definisi CRS atau secara eksplisit tetapkan `SpatialReferenceSystem.Wgs84` saat membuat lapisan File GDB.  
- **Ketidaksesuaian tipe atribut:** Tipe data atribut dalam GeoJSON harus cocok dengan skema target; jika tidak, Aspose.GIS akan melemparkan pengecualian.  
- **Kesalahan akses file:** Verifikasi bahwa folder tujuan memiliki izin menulis dan tidak ada proses lain yang mengunci file GDB.  

## Pertanyaan yang Sering Diajukan
### Apakah Aspose.GIS kompatibel dengan .NET framework terbaru?
Ya, Aspose.GIS kompatibel dengan versi .NET framework terbaru.  

### Apakah saya dapat mengonversi format geospasial lain menggunakan Aspose.GIS?
Tentu saja! Aspose.GIS mendukung berbagai format geospasial untuk manipulasi data yang fleksibel.  

### Apakah ada versi percobaan yang tersedia untuk Aspose.GIS?
Ya, Anda dapat menjelajahi fungsionalitas Aspose.GIS dengan mengunduh versi percobaan [here](https://releases.aspose.com/).  

### Bagaimana saya dapat mendapatkan dukungan untuk pertanyaan terkait Aspose.GIS?
Kunjungi [forum](https://forum.aspose.com/c/gis/33) Aspose.GIS untuk dukungan khusus.  

### Apakah saya dapat memperoleh lisensi sementara untuk Aspose.GIS?
Ya, Anda dapat memperoleh lisensi sementara [here](https://purchase.aspose.com/temporary-license/).  

---

**Terakhir Diperbarui:** 2026-01-10  
**Diuji Dengan:** Aspose.GIS 24.11 for .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}