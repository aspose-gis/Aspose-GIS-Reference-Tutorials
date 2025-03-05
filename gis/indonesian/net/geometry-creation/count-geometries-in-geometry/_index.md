---
title: Hitung Geometri dalam Geometri dengan Aspose.GIS
linktitle: Hitung Geometri dalam Geometri
second_title: Aspose.GIS .NET API
description: Pelajari cara menghitung geometri dalam geometri menggunakan Aspose.GIS untuk .NET. Tutorial langkah demi langkah dengan contoh kode untuk pengembang.
type: docs
weight: 23
url: /id/net/geometry-creation/count-geometries-in-geometry/
---
## Perkenalan
Aspose.GIS untuk .NET adalah alat yang ampuh bagi pengembang yang ingin menggabungkan fungsionalitas geospasial ke dalam aplikasi .NET mereka. Baik Anda membuat perangkat lunak pemetaan, layanan berbasis lokasi, atau alat analisis spasial, Aspose.GIS menyediakan serangkaian fitur lengkap untuk memenuhi kebutuhan Anda. Dalam tutorial ini, kita akan mempelajari cara menghitung geometri dalam geometri menggunakan Aspose.GIS untuk .NET.
## Prasyarat
Sebelum mendalami tutorial ini, pastikan Anda memiliki prasyarat berikut:
1. Visual Studio: Pastikan Anda telah menginstal Visual Studio di sistem Anda.
2. Aspose.GIS untuk .NET: Unduh dan instal Aspose.GIS untuk .NET dari[Unduh Halaman](https://releases.aspose.com/gis/net/).
3. Pengetahuan Dasar C#: Biasakan diri Anda dengan dasar-dasar bahasa pemrograman C#.

## Impor Namespace
Sebelum memulai pengkodean, Anda perlu mengimpor namespace yang diperlukan untuk mengakses fungsionalitas Aspose.GIS.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Langkah 2: Buat Geometri Titik
```csharp
Point point = new Point(40.7128, -74.006);
```
 Di sini, kami membuat a`Point` geometri dengan garis lintang 40.7128 dan garis bujur -74.006.
## Langkah 3: Buat Geometri LineString
```csharp
LineString line = new LineString();
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```
 Langkah ini menciptakan a`LineString` geometri dan menambahkan dua titik padanya.
## Langkah 4: Buat Koleksi Geometri
```csharp
GeometryCollection geometryCollection = new GeometryCollection();
geometryCollection.Add(point);
geometryCollection.Add(line);
```
 Kami kemudian membuat a`GeometryCollection` dan tambahkan geometri titik dan garis yang dibuat sebelumnya ke dalamnya.
## Langkah 5: Hitung Geometri
```csharp
int geometriesCount = geometryCollection.Count;
```
 Langkah ini menghitung jumlah geometri di dalamnya`GeometryCollection`.
## Langkah 6: Tampilkan Hitungannya
```csharp
Console.WriteLine(geometriesCount); // 2
```
 Terakhir, kami mencetak hitungan geometri, yang dalam hal ini adalah`2`.

## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara menghitung geometri dalam geometri menggunakan Aspose.GIS untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat memasukkan fungsionalitas geospasial ke dalam aplikasi .NET Anda dengan mudah.
## FAQ
### Apakah Aspose.GIS untuk .NET cocok untuk aplikasi desktop dan web?
Ya, Aspose.GIS untuk .NET dapat digunakan di aplikasi desktop dan web dengan lancar.
### Bisakah saya melakukan kueri spasial menggunakan Aspose.GIS untuk .NET?
Tentu saja, Aspose.GIS untuk .NET memberikan dukungan yang kuat untuk melakukan kueri spasial pada geometri.
### Apakah Aspose.GIS untuk .NET mendukung berbagai format file GIS?
Ya, Aspose.GIS untuk .NET mendukung berbagai format file GIS termasuk SHP, KML, dan GeoJSON.
### Apakah ada uji coba gratis yang tersedia untuk Aspose.GIS untuk .NET?
 Ya, Anda dapat mengunduh uji coba gratis dari[situs web](https://releases.aspose.com/).
### Di mana saya dapat menemukan dukungan untuk Aspose.GIS untuk .NET?
 Anda dapat menemukan dukungan di[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33).