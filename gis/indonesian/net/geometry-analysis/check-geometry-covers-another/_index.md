---
title: Periksa Geometri Meliputi Yang Lain
linktitle: Periksa Geometri Meliputi Yang Lain
second_title: Aspose.GIS .NET API
description: Pelajari cara memanfaatkan Aspose.GIS untuk .NET agar dapat bekerja secara efisien dengan data geografis, menganalisis informasi spasial, dan mengintegrasikan fitur pemetaan ke dalam aplikasi .NET Anda.
type: docs
weight: 15
url: /id/net/geometry-analysis/check-geometry-covers-another/
---
## Perkenalan
Aspose.GIS untuk .NET adalah perpustakaan canggih yang menyediakan alat bagi pengembang untuk bekerja secara efisien dengan data geografis dalam aplikasi .NET mereka. Baik Anda membuat aplikasi pemetaan, menganalisis data spasial, atau mengintegrasikan fitur geografis ke dalam perangkat lunak Anda, Aspose.GIS menawarkan serangkaian fungsi komprehensif untuk menyederhanakan proses pengembangan Anda.
## Prasyarat
Sebelum mulai menggunakan Aspose.GIS untuk .NET, pastikan Anda telah menyiapkan prasyarat berikut:
### 1. Instal Visual Studio
Pastikan Anda telah menginstal Visual Studio di sistem Anda. Aspose.GIS untuk .NET terintegrasi secara mulus dengan Visual Studio, memberikan pengalaman pengembangan yang lancar.
### 2. Dapatkan Aspose.GIS untuk .NET
 Unduh perpustakaan Aspose.GIS untuk .NET dari[situs web](https://releases.aspose.com/gis/net/). Anda dapat mengunduh perpustakaan secara langsung atau menggunakan manajer paket seperti NuGet untuk menginstalnya ke dalam proyek Anda.
### 3. Keakraban dengan .NET Framework
Pengetahuan dasar tentang kerangka .NET dan bahasa pemrograman C# sangat penting untuk memanfaatkan Aspose.GIS untuk .NET secara efektif.
### 4. Akses terhadap Dokumentasi dan Dukungan
 Mengacu kepada[dokumentasi](https://reference.aspose.com/gis/net/) untuk informasi mendetail tentang API dan fungsi Aspose.GIS. Jika Anda mengalami masalah atau memiliki pertanyaan, gunakan[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33) untuk bantuan.
### 5. Opsional: Lisensi Sementara
 Jika Anda menjelajahi Aspose.GIS untuk .NET, Anda dapat memperoleh lisensi sementara dari[Di Sini](https://purchase.aspose.com/temporary-license/) untuk mengevaluasi fitur perpustakaan.

## Impor Namespace
Sebelum menggunakan Aspose.GIS untuk .NET di proyek Anda, Anda perlu mengimpor namespace yang diperlukan:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Sekarang, mari kita bagi contoh yang diberikan menjadi beberapa langkah untuk memahami cara memeriksa apakah satu geometri menutupi geometri lainnya menggunakan Aspose.GIS untuk .NET.
## Langkah 1: Buat Objek LineString
```csharp
var line = new LineString();
```
 Di sini, kami membuat instance yang baru`LineString` objek, yang mewakili urutan segmen garis yang terhubung dalam ruang dua dimensi.
## Langkah 2: Tambahkan Poin ke LineString
```csharp
line.AddPoint(0, 0);
line.AddPoint(1, 1);
```
 Kami menambahkan poin ke`LineString` menggunakan`AddPoint` metode. Dalam contoh ini, kita menambahkan dua titik: (0, 0) dan (1, 1), membentuk ruas garis.
## Langkah 3: Buat Objek Titik
```csharp
var point = new Point(0, 0);
```
 Buat contoh a`Point` objek yang mewakili satu titik dalam ruang dua dimensi. Di sini kita membuat titik pada koordinat (0, 0).
## Langkah 4: Periksa apakah Garis Menutupi Titik
```csharp
Console.WriteLine(line.Covers(point));    // BENAR
```
 Menggunakan`Covers` metode untuk memeriksa apakah garis menutupi titik tersebut. Dalam hal ini, ia kembali`True` karena titik (0,0) terletak pada garis.
## Langkah 5: Periksa apakah Titik Tercakup oleh Garis
```csharp
Console.WriteLine(point.CoveredBy(line)); // BENAR
```
Demikian pula, gunakan`CoveredBy` metode untuk memeriksa apakah titik tersebut tertutup oleh garis. Karena titik (0, 0) terletak pada garis, maka titik tersebut kembali`True`.

## Kesimpulan
Kesimpulannya, Aspose.GIS untuk .NET menyediakan alat canggih untuk bekerja dengan data geografis dalam aplikasi .NET. Dengan mengikuti langkah-langkah yang diuraikan di atas, Anda dapat memanfaatkan fungsi Aspose.GIS secara efisien untuk memeriksa apakah satu geometri menutupi geometri lainnya, sehingga meningkatkan kemampuan analisis spasial perangkat lunak Anda.
## FAQ
### Bisakah saya menggunakan Aspose.GIS untuk .NET dalam proyek komersial saya?
Ya, Anda dapat menggunakan Aspose.GIS untuk .NET di proyek komersial dan non-komersial setelah mendapatkan lisensi yang sesuai.
### Apakah Aspose.GIS untuk .NET kompatibel dengan .NET Core?
Ya, Aspose.GIS untuk .NET kompatibel dengan lingkungan .NET Framework dan .NET Core.
### Apakah Aspose.GIS untuk .NET mendukung berbagai format GIS?
Ya, Aspose.GIS untuk .NET mendukung berbagai format GIS termasuk Shapefile, GeoJSON, KML, dan banyak lagi.
### Bisakah saya berkontribusi pada pengembangan Aspose.GIS untuk .NET?
Aspose.GIS untuk .NET adalah perpustakaan berpemilik yang dikembangkan oleh Aspose, sehingga kontribusi dari pengembang eksternal tidak diterima. Namun, Anda dapat memberikan masukan dan saran untuk perbaikan perpustakaan.
### Seberapa sering pembaruan dirilis untuk Aspose.GIS untuk .NET?
 Pembaruan Aspose.GIS untuk .NET dirilis secara berkala untuk memperkenalkan fitur baru, penyempurnaan, dan perbaikan bug. Periksalah[situs web](https://releases.aspose.com/gis/net/) untuk rilis terbaru.