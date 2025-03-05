---
title: Ekstrak Fitur ke GeoJSON
linktitle: Ekstrak Fitur ke GeoJSON
second_title: Aspose.GIS .NET API
description: Jelajahi panduan langkah demi langkah tentang penggunaan Aspose.GIS untuk .NET guna mengekstrak fitur ke GeoJSON. Manfaatkan kekuatan GIS dengan mudah! #Asumsikan #GIS
type: docs
weight: 23
url: /id/net/layer-management/extract-features-to-geojson/
---
## Perkenalan
Selamat datang di tutorial langkah demi langkah kami tentang mengekstraksi fitur ke GeoJSON menggunakan Aspose.GIS untuk .NET! Baik Anda seorang pengembang berpengalaman atau baru memulai perjalanan Anda dalam pemrograman GIS, panduan ini akan memandu Anda melalui prosesnya, memastikan Anda memanfaatkan kekuatan penuh Aspose.GIS untuk .NET.
## Prasyarat
Sebelum kita masuk ke tutorialnya, pastikan Anda memiliki prasyarat berikut:
-  Aspose.GIS untuk .NET: Pastikan Anda telah menginstal perpustakaan. Jika belum, Anda dapat mendownloadnya dari[Aspose.GIS untuk halaman .NET](https://releases.aspose.com/gis/net/).
-  Data Shapefile: Siapkan Shapefile untuk dimasukkan. Jika Anda memerlukan data sampel, Anda dapat menemukannya di[Dokumentasi Aspose.GIS](https://reference.aspose.com/gis/net/).
- Lingkungan .NET: Siapkan lingkungan .NET untuk menjalankan kode yang disediakan.
- Direktori Dokumen: Tentukan jalur ke direktori dokumen Anda dalam cuplikan kode.
Sekarang setelah semuanya siap, mari mulai mengekstraksi fitur ke GeoJSON!
## Impor Namespace
Pertama, sertakan namespace yang diperlukan dalam kode Anda:
```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
Namespace ini penting untuk bekerja dengan fungsi Aspose.GIS.
## Langkah 1: Buka Masukan Shapefile
```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Kode Anda untuk memproses input shapefile ada di sini
}
```
 Buka masukan Shapefile menggunakan`VectorLayer.Open` metode.
## Langkah 2: Buat Keluaran GeoJSON
```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Kode Anda untuk membuat keluaran GeoJSON ada di sini
}
```
 Buat keluaran GeoJSON menggunakan`VectorLayer.Create` metode.
## Langkah 3: Salin Atribut
```csharp
outputLayer.CopyAttributes(inputLayer);
```
 Salin atribut dari lapisan masukan ke lapisan keluaran menggunakan`CopyAttributes` metode.
## Langkah 4: Fitur Proses
```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Kode Anda untuk memproses setiap fitur masukan ada di sini
}
```
Ulangi setiap fitur di lapisan masukan dan proses satu per satu.
## Langkah 5: Filter Fitur berdasarkan Tanggal
```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```
Filter fitur berdasarkan kondisi tanggal. Dalam contoh ini, fitur dengan tanggal lahir sebelum tahun 1982 dilewati.
## Langkah 6: Buat Fitur Baru
```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```
Buat fitur baru untuk lapisan keluaran, salin geometri dan nilai dari fitur masukan.
Selamat! Anda telah berhasil mengekstraksi fitur ke GeoJSON menggunakan Aspose.GIS untuk .NET.
## Kesimpulan
Dalam tutorial ini, kami menjelajahi proses mengekstraksi fitur ke GeoJSON menggunakan Aspose.GIS untuk .NET. Perpustakaan yang kuat ini membuka banyak kemungkinan untuk pengembangan GIS. Bereksperimenlah dengan kumpulan data dan fungsi yang berbeda untuk membuka potensi penuh Aspose.GIS.
## FAQ
### T: Di mana saya dapat menemukan dokumentasi selengkapnya?
 Mengunjungi[Dokumentasi Aspose.GIS](https://reference.aspose.com/gis/net/) untuk informasi mendalam.
### T: Bagaimana cara mendapatkan lisensi sementara?
 Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
### T: Di mana saya bisa mencari dukungan?
 Bergabunglah dengan[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33) untuk dukungan dan diskusi komunitas.
### T: Apakah tersedia uji coba gratis?
 Ya, Anda dapat menemukan uji coba gratis[Di Sini](https://releases.aspose.com/).
### T: Di mana saya bisa membeli Aspose.GIS untuk .NET?
 Anda dapat membeli produknya[Di Sini](https://purchase.aspose.com/buy).