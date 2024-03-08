---
title: Tulis GeoJSON ke Streaming
linktitle: Tulis GeoJSON ke Streaming
second_title: Aspose.GIS .NET API
description: Jelajahi kekuatan Aspose.GIS untuk .NET! Tulis GeoJSON untuk melakukan streaming dengan mudah. Unduh sekarang untuk integrasi geospasial yang lancar.
type: docs
weight: 25
url: /id/net/layer-data-operations/write-geojson-to-stream/
---
## Perkenalan
Apakah Anda ingin memanfaatkan kekuatan GeoJSON dalam aplikasi .NET Anda menggunakan Aspose.GIS? Nah, Anda berada di tempat yang tepat! Panduan langkah demi langkah ini akan memandu Anda melalui proses penulisan GeoJSON ke aliran, memanfaatkan kemampuan kuat Aspose.GIS untuk .NET.
## Prasyarat
Sebelum kita mendalami tutorialnya, pastikan Anda memiliki prasyarat berikut:
1. Perpustakaan Aspose.GIS untuk .NET: Pastikan Anda telah menginstal perpustakaan Aspose.GIS untuk .NET. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/gis/net/).
2. Direktori Dokumen: Siapkan direktori dokumen di proyek Anda, dan catat jalurnya.
Sekarang, mari kita mulai tutorialnya!
## Impor Namespace
Hal pertama yang pertama, pastikan untuk menyertakan namespace yang diperlukan untuk mengakses fungsi Aspose.GIS dalam kode Anda:
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
Ganti "Direktori Dokumen Anda" dengan jalur sebenarnya ke direktori dokumen Anda.
## Langkah 2: Buat Aliran Memori
```csharp
using (var memoryStream = new MemoryStream())
{
    // Kode untuk langkah selanjutnya ada di sini
}
```
## Langkah 3: Buat Layer Vektor dengan Driver GeoJSON
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Kode untuk langkah selanjutnya ada di sini
}
```
## Langkah 4: Tentukan Atribut Fitur
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```
## Langkah 5: Bangun dan Tambahkan Fitur
```csharp
// Fitur Pertama
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);
// Fitur Kedua
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```
## Langkah 6: Tampilkan Keluaran GeoJSON
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```
Selamat! Anda telah berhasil menulis GeoJSON ke aliran menggunakan Aspose.GIS untuk .NET.
## Kesimpulan
Dalam tutorial ini, kami membahas langkah-langkah mendasar untuk mengintegrasikan Aspose.GIS untuk .NET ke dalam proyek Anda, khususnya berfokus pada penulisan GeoJSON ke aliran. Dengan langkah sederhana namun ampuh ini, Anda dapat meningkatkan kemampuan geospasial aplikasi Anda.
## Pertanyaan yang Sering Diajukan
### Bisakah saya menggunakan Aspose.GIS untuk .NET di lingkungan Windows dan Linux?
Ya, Aspose.GIS untuk .NET kompatibel dengan sistem Windows dan Linux.
### Apakah ada uji coba gratis yang tersedia?
 Sangat! Anda dapat menjelajahi uji coba gratis[Di Sini](https://releases.aspose.com/).
### Di mana saya dapat menemukan dokumentasi terperinci?
 Lihat dokumentasinya[Di Sini](https://reference.aspose.com/gis/net/).
### Bagaimana saya bisa mendapatkan lisensi sementara?
 Lisensi sementara tersedia[Di Sini](https://purchase.aspose.com/temporary-license/).
### Butuh bantuan atau memiliki pertanyaan lebih lanjut?
 Kunjungi forum dukungan kami[Di Sini](https://forum.aspose.com/c/gis/33).