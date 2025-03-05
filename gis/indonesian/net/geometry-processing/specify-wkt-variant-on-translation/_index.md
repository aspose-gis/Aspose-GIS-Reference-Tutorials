---
title: Tentukan Varian WKT pada Terjemahan menggunakan Aspose.GIS
linktitle: Tentukan Varian WKT pada Terjemahan
second_title: Aspose.GIS .NET API
description: Pelajari cara menentukan varian WKT di Aspose.GIS untuk .NET guna mengontrol format dan presisi representasi data spasial secara efektif.
type: docs
weight: 19
url: /id/net/geometry-processing/specify-wkt-variant-on-translation/
---
## Perkenalan
Aspose.GIS untuk .NET adalah perpustakaan canggih yang memungkinkan pengembang bekerja dengan data sistem informasi geografis (GIS) dalam aplikasi .NET mereka dengan mudah. Salah satu fitur penting yang disediakan oleh Aspose.GIS adalah kemampuan untuk menentukan varian Teks Terkenal (WKT) selama penerjemahan, memungkinkan pengguna untuk mengontrol format dan ketepatan representasi data spasial. Dalam tutorial ini, kita akan mempelajari cara menentukan varian WKT langkah demi langkah menggunakan Aspose.GIS untuk .NET.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. Aspose.GIS untuk .NET: Unduh dan instal Aspose.GIS untuk .NET dari[Unduh Halaman](https://releases.aspose.com/gis/net/).
2. Lingkungan Pengembangan: Pastikan Anda telah menyiapkan lingkungan pengembangan .NET.
3. Pengetahuan Dasar: Keakraban dengan bahasa pemrograman C# dan kerangka .NET.

## Impor Namespace
Sebelum menggunakan fungsionalitas Aspose.GIS dalam kode Anda, impor namespace yang diperlukan:
```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```
## Langkah 1: Buat Objek Titik
 Pertama, buat a`Point` objek dengan nilai lintang, bujur, dan ukuran opsional (M):
```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```
## Langkah 2: Tetapkan Sistem Referensi Spasial (SRS)
Tetapkan sistem referensi spasial (SRS) ke objek titik. Dalam contoh ini, kami menggunakan sistem referensi spasial WGS84:
```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```
## Langkah 3: Tentukan Varian WKT
 Sekarang, tentukan varian WKT untuk terjemahan. Aspose.GIS mendukung berbagai varian WKT, termasuk`Iso`, `SimpleFeatureAccessOutdated` , Dan`ExtendedPostGis`. Pilih varian yang sesuai berdasarkan kebutuhan Anda:
```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // TITIK M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // TITIK (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTTM (23.5732, 25.3421, 40.3)
```
## Langkah 4: Kontrol Format Numerik
Anda dapat mengontrol format numerik koordinat dalam representasi WKT. Aspose.GIS menyediakan opsi untuk menentukan presisi desimal:
```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // TITIK M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // TITIK M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // TITIK M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // TITIK M (23.573 25.342 40.3)
```

## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara menentukan varian WKT pada terjemahan menggunakan Aspose.GIS untuk .NET. Dengan mengikuti langkah-langkah yang diuraikan di atas, pengembang dapat secara efektif mengontrol format dan ketepatan representasi data spasial dalam aplikasi .NET mereka, sehingga meningkatkan fleksibilitas dan kegunaan sistem informasi geografis.
## FAQ
### Apakah Aspose.GIS kompatibel dengan semua versi .NET?
Ya, Aspose.GIS mendukung .NET Framework 4.0 dan lebih tinggi.
### Bisakah saya menggunakan Aspose.GIS untuk proyek komersial?
Ya, Aspose.GIS dapat digunakan untuk proyek pribadi dan komersial.
### Apakah Aspose.GIS menyediakan dukungan untuk format data spasial lainnya?
Ya, Aspose.GIS mendukung berbagai format data spasial, termasuk ESRI Shapefile, GeoJSON, dan KML.
### Apakah ada uji coba gratis yang tersedia untuk Aspose.GIS?
 Ya, Anda dapat mengunduh Aspose.GIS versi uji coba gratis dari[Di Sini](https://releases.aspose.com/).
### Di mana saya bisa mendapatkan bantuan atau dukungan untuk Aspose.GIS?
 Anda dapat mengirimkan pertanyaan Anda atau mencari bantuan dari komunitas Aspose.GIS di[forum](https://forum.aspose.com/c/gis/33).