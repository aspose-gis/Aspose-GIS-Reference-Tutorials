---
title: Buat Geometri MultiPoligon dengan Aspose.GIS
linktitle: Buat Geometri MultiPoligon
second_title: Aspose.GIS .NET API
description: Pelajari cara membuat geometri MultiPolygon menggunakan Aspose.GIS untuk .NET. Panduan langkah demi langkah untuk pemula. Uji coba gratis tersedia.
weight: 16
url: /id/net/geometry-creation/create-multipolygon-geometry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Geometri MultiPoligon dengan Aspose.GIS

## Perkenalan
Dalam dunia pengembangan Sistem Informasi Geografis (GIS), Aspose.GIS untuk .NET menonjol sebagai alat yang ampuh untuk membuat, mengedit, dan menganalisis data geospasial. Baik Anda seorang pengembang berpengalaman atau baru memulai, menguasai Aspose.GIS dapat membuka banyak kemungkinan untuk proyek Anda.
## Prasyarat
Sebelum mulai menggunakan Aspose.GIS untuk .NET, ada beberapa prasyarat yang harus Anda miliki:
### Menginstal Aspose.GIS untuk .NET
1.  Unduh Aspose.GIS: Kunjungi[Unduh Halaman](https://releases.aspose.com/gis/net/)dan pilih versi yang sesuai untuk lingkungan pengembangan Anda.
2. Instal Aspose.GIS: Ikuti petunjuk instalasi yang disediakan dalam dokumentasi untuk menginstal Aspose.GIS untuk .NET di mesin Anda.

## Mengimpor Namespace
Untuk mulai bekerja dengan Aspose.GIS di proyek .NET, Anda harus mengimpor namespace yang diperlukan:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Langkah 1: Buat Cincin Linier
Pertama, kita perlu membuat LinearRings untuk setiap poligon. Setiap LinearRing mewakili string garis tertutup yang membentuk batas poligon.
```csharp
LinearRing firstRing = new LinearRing();
firstRing.AddPoint(8.5, -2.5);
firstRing.AddPoint(-8.5, 2.5);
firstRing.AddPoint(8.5, -2.5);
LinearRing secondRing = new LinearRing();
secondRing.AddPoint(7.6, -3.6);
secondRing.AddPoint(-9.6, 1.5);
secondRing.AddPoint(7.6, -3.6);
```
## Langkah 2: Buat Poligon
Selanjutnya, kita akan membuat objek Poligon menggunakan LinearRings yang telah kita definisikan.
```csharp
Polygon firstPolygon = new Polygon(firstRing);
Polygon secondPolygon = new Polygon(secondRing);
```
## Langkah 3: Buat MultiPoligon
Sekarang, mari gabungkan poligon-poligon ini menjadi geometri MultiPoligon.
```csharp
MultiPolygon multiPolygon = new MultiPolygon();
multiPolygon.Add(firstPolygon);
multiPolygon.Add(secondPolygon);
```
Selamat! Anda telah berhasil membuat geometri MultiPolygon menggunakan Aspose.GIS untuk .NET.

## Kesimpulan
Menguasai Aspose.GIS untuk .NET membuka banyak kemungkinan bagi pengembang yang bekerja dengan data geospasial. Dengan mengikuti panduan langkah demi langkah ini, Anda telah mempelajari cara membuat geometri MultiPoligon, yang meletakkan dasar untuk aplikasi GIS yang lebih kompleks.
## FAQ
### Apakah Aspose.GIS untuk .NET cocok untuk pemula?
Sangat! Aspose.GIS menawarkan dokumentasi dan tutorial komprehensif untuk membantu pengembang dari semua tingkat keahlian memulai.
### Bisakah saya mencoba Aspose.GIS sebelum membeli?
 Ya, Anda dapat mengunduh uji coba gratis dari[Di Sini](https://releases.aspose.com/) untuk menjelajahi fitur-fiturnya sebelum melakukan pembelian.
### Di mana saya dapat menemukan dukungan untuk Aspose.GIS?
 Anda dapat mengunjungi forum Aspose.GIS[Di Sini](https://forum.aspose.com/c/gis/33) untuk bertanya dan mendapatkan bantuan dari masyarakat.
### Apakah ada lisensi sementara yang tersedia untuk Aspose.GIS?
 Ya, Anda bisa mendapatkan lisensi sementara dari[Di Sini](https://purchase.aspose.com/temporary-license/) untuk tujuan evaluasi.
### Bisakah saya membeli Aspose.GIS secara langsung?
 Ya, Anda dapat membeli Aspose.GIS dari situs web[Di Sini](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
