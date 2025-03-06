---
title: Buat Poligon dengan Geometri Lubang menggunakan Aspose.GIS
linktitle: Buat Poligon dengan Geometri Lubang
second_title: Aspose.GIS .NET API
description: Pelajari cara membuat poligon dengan geometri lubang menggunakan Aspose.GIS untuk .NET. Tutorial langkah demi langkah dengan contoh kode.
weight: 13
url: /id/net/geometry-creation/create-polygon-with-hole-geometry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Poligon dengan Geometri Lubang menggunakan Aspose.GIS

## Perkenalan
Dalam tutorial ini, kita akan memandu proses pembuatan poligon dengan geometri lubang menggunakan Aspose.GIS untuk .NET. Aspose.GIS adalah perpustakaan canggih yang memungkinkan pengembang bekerja dengan data geospasial dalam aplikasi .NET mereka. 
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. Aspose.GIS untuk .NET Library: Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/gis/net/).
2. Lingkungan Pengembangan: Pastikan Anda memiliki lingkungan pengembangan yang diatur dengan Visual Studio atau .NET IDE lainnya yang diinstal.
## Impor Namespace
Pertama, Anda perlu mengimpor namespace yang diperlukan agar berfungsi dengan fungsi Aspose.GIS. Berikut cara melakukannya:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Sekarang, mari kita lanjutkan membuat poligon dengan geometri lubang menggunakan Aspose.GIS untuk .NET.
## Langkah 1: Buat Objek Poligon
```csharp
Polygon polygon = new Polygon();
```
## Langkah 2: Tentukan Cincin Eksterior
```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```
## Langkah 3: Tentukan Cincin Interior (Lubang)
```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```
## Langkah 4: Tetapkan Cincin Eksterior dan Tambahkan Cincin Interior ke Poligon
```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```
## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara membuat poligon dengan geometri lubang menggunakan Aspose.GIS untuk .NET. Pengetahuan ini akan bermanfaat untuk berbagai aplikasi geospasial dimana geometri tersebut sangat penting.
## FAQ
### 1. Apa itu Aspose.GIS?
Aspose.GIS adalah perpustakaan .NET yang memungkinkan pengembang bekerja dengan data geospasial, memungkinkan mereka membuat, membaca, dan memanipulasi berbagai format file geospasial.
### 2. Bisakah saya menggunakan Aspose.GIS untuk proyek komersial?
 Ya, Anda dapat menggunakan Aspose.GIS untuk proyek pribadi dan komersial dengan membeli lisensi. Mengunjungi[Di Sini](https://purchase.aspose.com/buy) untuk lebih jelasnya.
### 3. Apakah tersedia uji coba gratis untuk Aspose.GIS?
 Ya, Anda dapat memanfaatkan uji coba gratis Aspose.GIS dari[Di Sini](https://releases.aspose.com/).
### 4. Di mana saya bisa mendapatkan dukungan untuk Aspose.GIS?
 Anda dapat menemukan dukungan untuk Aspose.GIS di[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33).
### 5. Bagaimana cara mendapatkan lisensi sementara untuk Aspose.GIS?
 Anda dapat memperoleh lisensi sementara untuk Aspose.GIS dari[Di Sini](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
