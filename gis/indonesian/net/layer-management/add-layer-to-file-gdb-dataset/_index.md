---
date: 2026-06-30
description: Pelajari cara menambahkan layer ke dataset File GDB menggunakan Aspose.GIS
  dengan referensi spasial WGS84. Ikuti panduan langkah demi langkah ini untuk menambahkan
  layer di .NET.
keywords:
- how to add layer
- spatial reference wgs84
- Aspose.GIS .NET
- File GDB dataset
linktitle: Tambahkan Layer ke Dataset File GDB
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to add layer to a File GDB dataset using Aspose.GIS with
    spatial reference WGS84. Follow this step‑by‑step guide to add a layer in .NET.
  headline: How to Add Layer to File GDB Dataset with spatial reference WGS84 using
    Aspose.GIS
  type: TechArticle
- questions:
  - answer: spatial reference wgs84 (WGS 84)
    question: What is the primary coordinate system used?
  - answer: Aspose.GIS for .NET
    question: Which library provides the API?
  - answer: Yes – a temporary Aspose license is available.
    question: Do I need a license for testing?
  - answer: Absolutely, you can define any number of feature attributes.
    question: Can I add attributes to the new layer?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Cara Menambahkan Layer ke Dataset File GDB dengan referensi spasial WGS84 menggunakan
  Aspose.GIS
url: /id/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# cara menambahkan layer – referensi spasial wgs84 dengan Aspose.GIS

## Pendahuluan
Siap meningkatkan alur kerja GIS Anda dengan Aspose.GIS untuk .NET? Dalam tutorial ini Anda akan belajar **cara menambahkan layer** ke dataset File GDB sambil bekerja dengan sistem koordinat **spatial reference WGS84**. Kami akan memandu Anda melalui setiap langkah, mulai dari menyiapkan folder data Anda hingga memvalidasi layer yang baru dibuat, sehingga Anda dapat mulai memanipulasi data geografis dengan percaya diri dan efisien.

## Jawaban Cepat
- **Apa sistem koordinat utama yang digunakan?** spatial reference wgs84 (WGS 84)  
- **Perpustakaan mana yang menyediakan API?** Aspose.GIS for .NET  
- **Apakah saya memerlukan lisensi untuk pengujian?** Ya – lisensi sementara Aspose tersedia.  
- **Bisakah saya menambahkan atribut ke layer baru?** Tentu saja, Anda dapat mendefinisikan sejumlah atribut fitur.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## Apa itu spatial reference wgs84?
Spatial reference wgs84 (World Geodetic System 1984) adalah sistem koordinat geografis yang paling banyak digunakan. Sistem ini mendefinisikan lintang dan bujur dalam derajat dan berfungsi sebagai CRS default untuk banyak dataset GIS, termasuk yang akan kami buat dalam panduan ini.

## Mengapa menggunakan Aspose.GIS untuk menambahkan layer?
Muatan data GIS Anda tanpa binari pihak ketiga dan tetap memiliki kontrol penuh atas definisi skema. Aspose.GIS mendukung **40+ sistem referensi spasial**, dapat memproses file lebih besar dari **2 GB** tanpa memuat seluruh dataset ke memori, dan berjalan di Windows, Linux, serta macOS. Ini menjadikannya solusi yang handal dan lintas‑platform untuk otomatisasi GIS tingkat perusahaan.

## Prasyarat
- Perpustakaan Aspose.GIS untuk .NET: Unduh dan instal perpustakaan dari [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/).  
- Direktori Dokumen: Buat folder khusus di mesin Anda untuk menyimpan file GIS.  
- Lisensi Aspose sementara (opsional untuk evaluasi) – lihat FAQ di bawah untuk tautan unduhan.

## Impor Namespace
Tambahkan pernyataan `using` yang diperlukan ke proyek C# Anda sehingga Anda dapat mengakses kelas Aspose.GIS:

*Tidak diperlukan blok kode di sini; cukup tambahkan baris berikut di bagian atas file Anda:*

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.Geometries.Collections;
using Aspose.Gis.SpatialReference;
```

## Langkah 1: Salin Direktori
**Definition anchor:** Dataset File GDB adalah geodatabase ESRI berbasis folder yang menyimpan data spasial dalam sekumpulan file.  
Pertama, gandakan folder yang berisi dataset GDB asli. Menyimpan salinan melindungi data sumber saat Anda bereksperimen.

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

## Langkah 2: Buka Dataset dan Verifikasi Kemampuan Pembuatan
`Dataset` mewakili kumpulan layer GIS yang disimpan dalam File GDB. Buka dataset yang baru disalin dan pastikan bahwa ia dapat membuat layer baru. Properti `CanCreateLayers` harus mengembalikan **True**. **`CanCreateLayers` adalah properti boolean yang menunjukkan apakah dataset mendukung pembuatan layer baru.**

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Langkah 3: Buat dan Isi Layer Baru dengan spatial reference wgs84
Sekarang kami membuat layer bernama **data** dan secara eksplisit menetapkan spatial reference-nya ke **Wgs84**. Kami juga menambahkan atribut sederhana bernama **Name** dan menyisipkan satu fitur titik. **`CreateLayer` membuat layer baru dalam dataset dengan nama dan spatial reference yang ditentukan.** **`SpatialReference` mewakili sistem koordinat yang digunakan oleh sebuah layer.** **`Feature` adalah objek geografis individu (titik, garis, atau poligon) yang disimpan dalam sebuah layer.**

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Langkah 4: Buka dan Validasi Layer yang Ditambahkan
Akhirnya, buka layer yang baru saja Anda buat dan verifikasi isinya. Konsol akan menunjukkan bahwa layer tersebut berisi satu fitur dan bahwa atribut **Name** cocok dengan yang kami tetapkan. **`Layer.Open` membuka layer yang ada untuk membaca atau mengedit.** Ini mengonfirmasi bahwa layer telah ditambahkan dengan benar dan bahwa spatial reference adalah WGS84.

```csharp
using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
{
    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
    var feature = layer.ConstructFeature();
    feature.SetValue("Name", "Name_1");
    feature.Geometry = new Point(12.21, 23.123, 20, -200);
    layer.Add(feature);
}
```

## Cara menambahkan layer ke dataset File GDB?
Muat dataset, panggil `CreateLayer` dengan nama dan spatial reference yang diinginkan, definisikan skema atribut, lalu sisipkan fitur. Semua ini dapat dilakukan dengan beberapa pemanggilan metode Aspose.GIS, dan API secara otomatis menangani penguncian file serta validasi skema. Proses ini memastikan bahwa layer baru sesuai dengan spatial reference dataset, bahwa definisi atribut disimpan dalam skema layer, dan bahwa data dapat diakses oleh perangkat lunak GIS mana pun yang mendukung File GDB.

## Masalah Umum & Tips
- **Path tidak benar:** Pastikan `dataDir` diakhiri dengan pemisah path (`/` atau `\`) sehingga string yang digabung membentuk jalur file yang valid.  
- **Kesalahan lisensi:** Jika Anda melihat peringatan lisensi, terapkan lisensi sementara dari portal Aspose sebelum menjalankan kode.  
- **Tidak cocoknya CRS:** Saat membuka layer nanti di alat GIS lain, pastikan alat tersebut mengenali WGS 84 (EPSG:4326) sebagai sistem koordinat.  
- **Dataset besar:** Untuk dataset yang melebihi 1 GB, pertimbangkan menggunakan `Dataset.OpenReadOnly` untuk mengurangi konsumsi memori.

## Pertanyaan yang Sering Diajukan
### Q: Bisakah saya menggunakan Aspose.GIS untuk .NET dengan perpustakaan GIS lain?
A: Ya, Aspose.GIS berfungsi secara independen tetapi dapat digabungkan dengan perpustakaan seperti GDAL atau NetTopologySuite untuk pemrosesan lanjutan.

### Q: Apakah lisensi sementara tersedia untuk tujuan pengujian?
A: Ya, Anda dapat memperoleh lisensi sementara dari [di sini](https://purchase.aspose.com/temporary-license/) untuk pengujian dan evaluasi.

### Q: Sistem referensi spasial apa yang didukung oleh Aspose.GIS untuk .NET?
A: Aspose.GIS mendukung lebih dari **40 kode EPSG**, termasuk sistem populer seperti WGS84 (EPSG:4326), Web Mercator (EPSG:3857), dan NAD83 (EPSG:4269). Jelajahi dokumentasi lengkap [di sini](https://reference.aspose.com/gis/net/).

### Q: Bisakah saya berkontribusi ke komunitas Aspose.GIS?
A: Tentu saja! Bergabunglah dalam diskusi dan bagikan pengalaman Anda di [forum Aspose.GIS](https://forum.aspose.com/c/gis/33).

### Q: Di mana saya dapat menemukan dokumentasi terperinci untuk Aspose.GIS untuk .NET?
A: Jelajahi dokumentasi lengkap [di sini](https://reference.aspose.com/gis/net/) untuk informasi mendalam tentang semua kelas, metode, dan praktik terbaik.

---

**Terakhir Diperbarui:** 2026-06-30  
**Diuji Dengan:** Aspose.GIS for .NET (latest stable version)  
**Penulis:** Aspose

{{< blocks/products/products-backtop-button >}}

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Tutorial Terkait

- [Buat Dataset File Geodatabase .NET dengan Aspose.GIS](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Buat Layer Vektor di File GDB – Tutorial Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Buat Dataset File GDB dan Atur Toleransi untuk Layer](/gis/net/layer-data-operations/set-tolerances-for-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}