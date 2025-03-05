---
title: Ubah Bentuk Poligon menjadi Linestring
linktitle: Ubah Bentuk Poligon menjadi Linestring
second_title: Aspose.GIS .NET API
description: Jelajahi kekuatan Aspose.GIS untuk .NET dan konversikan Polygon Shapefiles ke Linestrings dengan mudah. Tingkatkan pengembangan GIS Anda hari ini!
type: docs
weight: 18
url: /id/net/layer-management/convert-polygon-shapefile-to-linestring/
---
## Perkenalan
Jika Anda bekerja dengan sistem informasi geografis (GIS) di .NET, Aspose.GIS adalah perpustakaan canggih yang dapat menyederhanakan tugas Anda. Dalam tutorial ini, kami akan memandu Anda melalui proses konversi Polygon Shapefile menjadi Linestring menggunakan Aspose.GIS. Hal ini sangat berguna ketika Anda perlu mengekstrak fitur linier dari data poligonal untuk berbagai aplikasi seperti perencanaan rute atau analisis jaringan.
## Prasyarat
Sebelum kita masuk ke tutorialnya, pastikan Anda memiliki yang berikut ini:
-  Perpustakaan Aspose.GIS: Unduh dan instal perpustakaan Aspose.GIS dari[situs web](https://releases.aspose.com/gis/net/).
- Data Shapefile: Siapkan Polygon Shapefile untuk dikonversi. Jika tidak memilikinya, Anda dapat mencari data sampel atau membuatnya sendiri.
- Lingkungan Pengembangan: Siapkan lingkungan pengembangan .NET Anda dengan alat yang diperlukan.
## Impor Namespace
Dalam kode C#, Anda perlu mengimpor namespace Aspose.GIS untuk mengakses kelas dan metode yang diperlukan. Tambahkan namespace berikut di awal file kode Anda:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Langkah 1: Atur Direktori Dokumen
```csharp
// Jalur ke direktori dokumen.
string dataDir = "Your Document Directory";
```
Ganti "Direktori Dokumen Anda" dengan jalur ke direktori tempat Shapefile Anda berada.
## Langkah 2: Buka Sumber Shapefile
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Kode lainnya akan ditempatkan di sini
}
```
Langkah ini membuka sumber Polygon Shapefile untuk dibaca.
## Langkah 3: Buat Shapefile Linestring Tujuan
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Kode lainnya akan ditempatkan di sini
}
```
Di sini, kita membuat Linestring Shapefile baru untuk menulis data yang dikonversi.
## Langkah 4: Iterasi Melalui Fitur Sumber
```csharp
foreach (Feature sourceFeature in source)
{
    // Kode lainnya akan ditempatkan di sini
}
```
Perulangan ini mengulangi setiap fitur di Polygon Shapefile sumber.
## Langkah 5: Ubah Poligon menjadi Linestring dan Tulis ke Tujuan
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
Pada langkah ini, setiap fitur Poligon diubah menjadi Linestring, dan fitur Linestring yang dihasilkan ditulis ke Shapefile tujuan.
## Kesimpulan
Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah mengonversi Polygon Shapefile menjadi Linestring menggunakan Aspose.GIS untuk .NET. Proses ini membuka kemungkinan baru untuk analisis dan visualisasi data dalam aplikasi GIS.

## FAQ
### Apakah Aspose.GIS kompatibel dengan semua versi .NET?
Ya, Aspose.GIS mendukung berbagai versi .NET, memastikan kompatibilitas dengan lingkungan pengembangan Anda.
### Bisakah saya menggunakan Aspose.GIS untuk proyek komersial?
 Ya kamu bisa. Untuk menggunakan Aspose.GIS dalam proyek komersial, pertimbangkan untuk membeli lisensi[Di Sini](https://purchase.aspose.com/buy).
### Apakah ada contoh atau dokumentasi yang tersedia?
 Ya, Anda dapat menemukan dokumentasi dan contoh lengkap di[halaman dokumentasi](https://reference.aspose.com/gis/net/).
### Apakah ada versi uji coba yang tersedia?
 Ya, Anda dapat menjelajahi Aspose.GIS dengan uji coba gratis dengan mengunjungi[Link ini](https://releases.aspose.com/).
### Di mana saya dapat mencari bantuan atau dukungan?
 Mengunjungi[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33) untuk bantuan atau pertanyaan terkait dukungan apa pun.