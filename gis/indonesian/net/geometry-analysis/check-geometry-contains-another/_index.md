---
title: Periksa Geometri Berisi Yang Lain
linktitle: Periksa Geometri Berisi Yang Lain
second_title: Aspose.GIS .NET API
description: Jelajahi Aspose.GIS untuk .NET, perpustakaan tangguh untuk integrasi data geospasial yang lancar dalam aplikasi .NET Anda.
weight: 14
url: /id/net/geometry-analysis/check-geometry-contains-another/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Periksa Geometri Berisi Yang Lain

## Perkenalan
Aspose.GIS untuk .NET adalah perpustakaan canggih yang memungkinkan pengembang bekerja dengan data geospasial secara lancar dalam aplikasi .NET mereka. Baik Anda sedang membangun aplikasi pemetaan, melakukan analisis geospasial, atau mengintegrasikan fitur berbasis lokasi ke dalam perangkat lunak Anda, Aspose.GIS menyederhanakan proses dengan menyediakan API intuitif dan fungsionalitas yang kuat.
## Prasyarat
Sebelum mulai menggunakan Aspose.GIS untuk .NET, pastikan Anda memiliki prasyarat berikut:
### 1. Pengaturan Lingkungan Pengembangan .NET
Pastikan Anda memiliki lingkungan pengembangan .NET yang berfungsi di mesin Anda. Ini termasuk menginstal dan mengkonfigurasi .NET SDK dengan benar.
### 2. Instalasi Aspose.GIS
 Instal Aspose.GIS untuk .NET dengan mengunduh perpustakaan dari halaman rilis[Di Sini](https://releases.aspose.com/gis/net/) . Ikuti petunjuk instalasi yang disediakan dalam dokumentasi[Di Sini](https://reference.aspose.com/gis/net/)untuk mengintegrasikan Aspose.GIS ke dalam proyek Anda.
### 3. Pemahaman Dasar C#
Biasakan diri Anda dengan bahasa pemrograman C# karena Aspose.GIS untuk .NET terutama digunakan dengan C#.

## Impor Namespace
Dalam proyek C# Anda, impor namespace yang diperlukan untuk memanfaatkan fungsi Aspose.GIS:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Langkah 1: Tentukan Objek Geometri
Pertama, tentukan objek geometri menggunakan kelas Aspose.GIS:
```csharp
var geometry1 = new Polygon();
geometry1.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 4),
    new Point(4, 4),
    new Point(4, 0),
    new Point(0, 0),
});
geometry1.AddInteriorRing(new LinearRing(new[]
{
    new Point(1, 1),
    new Point(1, 3),
    new Point(3, 3),
    new Point(3, 1),
    new Point(1, 1),
}));
var geometry2 = new Point(2, 2);
```
## Langkah 2: Periksa Penahanan Spasial
Selanjutnya, periksa apakah satu geometri berisi geometri lainnya:
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry2)); // PALSU
```
## Langkah 3: Tentukan Geometri Lain
Tentukan objek geometri lain:
```csharp
var geometry3 = new Point(0.5, 0.5);
```
## Langkah 4: Periksa Kembali Penahanan Spasial
Periksa apakah geometri yang baru didefinisikan terkandung dalam geometri pertama:
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry3)); // BENAR
```
## Langkah 5: Fungsi Setara
 Pahami itu`a.SpatiallyContains(b)` setara dengan`b.Within(a)`:
```csharp
Console.WriteLine(geometry3.Within(geometry1)); // BENAR
```

## Kesimpulan
Kesimpulannya, Aspose.GIS untuk .NET menyediakan alat canggih untuk menangani data geospasial dalam aplikasi .NET. Dengan mengikuti panduan ini dan memanfaatkan contoh yang diberikan, Anda dapat melakukan pemeriksaan pengendalian spasial secara efisien dan memanfaatkan fungsi geospasial lainnya dalam proyek Anda.
## FAQ
### Q1: Apakah Aspose.GIS kompatibel dengan .NET Core?
J: Ya, Aspose.GIS sepenuhnya mendukung .NET Core, memungkinkan Anda mengembangkan aplikasi geospasial di berbagai platform.
### Q2: Bisakah saya melakukan analisis geospasial menggunakan Aspose.GIS?
J: Tentu saja, Aspose.GIS menawarkan berbagai fungsi untuk analisis geospasial, termasuk kueri spasial, penghitungan jarak, dan manipulasi geometri.
### Q3: Seberapa sering pembaruan dirilis untuk Aspose.GIS?
J: Aspose.GIS secara rutin merilis pembaruan untuk meningkatkan kinerja, menambahkan fitur baru, dan mengatasi masalah apa pun yang dilaporkan. Anda dapat terus mendapatkan informasi terbaru dengan mengunjungi halaman rilis.
### Q4: Apakah ada forum komunitas untuk pengguna Aspose.GIS?
A: Ya, Anda dapat bergabung di forum komunitas Aspose.GIS[Di Sini](https://forum.aspose.com/c/gis/33) untuk terhubung dengan pengguna lain, mengajukan pertanyaan, dan berbagi pengalaman Anda.
### Q5: Dapatkah saya mencoba Aspose.GIS sebelum membeli?
 A: Tentu saja, Anda dapat menjelajahi Aspose.GIS dengan mengunduh uji coba gratisnya[Di Sini](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
