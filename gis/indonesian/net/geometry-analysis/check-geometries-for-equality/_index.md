---
title: Periksa Geometri untuk Kesetaraan
linktitle: Periksa Geometri untuk Kesetaraan
second_title: Aspose.GIS .NET API
description: Pelajari cara menggunakan Aspose.GIS untuk .NET guna memeriksa geometri untuk kesetaraan dalam aplikasi .NET Anda dengan tutorial komprehensif ini.
type: docs
weight: 10
url: /id/net/geometry-analysis/check-geometries-for-equality/
---
## Perkenalan
Aspose.GIS untuk .NET adalah perpustakaan canggih yang memungkinkan pengembang bekerja dengan data geospasial secara efisien dalam aplikasi .NET mereka. Baik Anda membuat aplikasi pemetaan, alat analisis spasial, atau mengintegrasikan fungsi geospasial ke dalam perangkat lunak yang ada, Aspose.GIS menyediakan alat yang Anda perlukan untuk menyelesaikan pekerjaan.
## Prasyarat
Sebelum mulai menggunakan Aspose.GIS untuk .NET, pastikan Anda memiliki prasyarat berikut:
### .NET Framework Terpasang
Pastikan Anda telah menginstal .NET Framework di sistem Anda. Anda dapat mengunduhnya dari situs web Microsoft.
### Aspose.GIS untuk Perpustakaan .NET
 Unduh dan instal perpustakaan Aspose.GIS untuk .NET dari[Unduh Halaman](https://releases.aspose.com/gis/net/). Ikuti petunjuk instalasi yang disediakan dalam dokumentasi.
### Pengembangan lingkungan
Siapkan lingkungan pengembangan pilihan Anda, seperti Visual Studio, untuk pengembangan .NET.

## Impor Namespace
Di aplikasi .NET Anda, impor namespace yang diperlukan untuk menggunakan fungsionalitas Aspose.GIS:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Langkah 1: Tentukan Geometri
Pertama, tentukan geometri yang ingin Anda bandingkan. Dalam contoh ini, kita memiliki dua geometri:`geometry1` Dan`geometry2`.
```csharp
var geometry1 = new MultiLineString
{
    new LineString(new [] { new Point(0, 0), new Point(1, 1) }),
    new LineString(new [] { new Point(1, 1), new Point(2, 2) }),
};
var geometry2 = new LineString(new[]
{
    new Point(0, 0), new Point(2, 2),
});
```
## Langkah 2: Periksa Geometri untuk Kesetaraan
 Sekarang, periksa apakah geometrinya sama secara spasial menggunakan`SpatiallyEquals` metode yang disediakan oleh Aspose.GIS.
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // BENAR
```
 Ini akan mencetak`True` ke konsol sejak itu`geometry1` Dan`geometry2` secara spasial setara.
## Langkah 3: Ubah Geometri
 Selanjutnya mari kita modifikasi`geometry2` dengan menambahkan poin baru.
```csharp
geometry2.AddPoint(3, 3);
```
## Langkah 4: Periksa Kembali Kesetaraan
Sekarang, periksa kembali persamaan geometri setelah modifikasi.
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // PALSU
```
 Kali ini, hasilnya adalah`False` karena geometrinya tidak lagi sama secara spasial akibat modifikasi yang dilakukan`geometry2`.

## Kesimpulan
Kesimpulannya, Aspose.GIS untuk .NET menyediakan alat canggih untuk bekerja dengan data geospasial dalam aplikasi .NET. Dengan mengikuti panduan langkah demi langkah ini, Anda dapat dengan mudah memeriksa kesetaraan geometri menggunakan metode Aspose.GIS.
## FAQ
### Bisakah saya menggunakan Aspose.GIS untuk .NET dengan kerangka .NET lainnya?
Ya, Aspose.GIS untuk .NET kompatibel dengan berbagai kerangka .NET, termasuk .NET Core dan .NET Standard.
### Apakah ada uji coba gratis yang tersedia untuk Aspose.GIS untuk .NET?
 Ya, Anda dapat mengunduh uji coba gratis dari[halaman rilis](https://releases.aspose.com/).
### Di mana saya dapat menemukan dokumentasi Aspose.GIS untuk .NET?
 Anda dapat menemukan dokumentasi terperinci di[Halaman dokumentasi Aspose.GIS](https://reference.aspose.com/gis/net/).
### Bagaimana saya bisa mendapatkan dukungan untuk Aspose.GIS untuk .NET?
 Anda bisa mendapatkan dukungan dari forum komunitas Aspose.GIS[Di Sini](https://forum.aspose.com/c/gis/33).
### Bisakah saya membeli lisensi sementara Aspose.GIS untuk .NET?
 Ya, Anda dapat membeli lisensi sementara dari[halaman pembelian](https://purchase.aspose.com/temporary-license/).