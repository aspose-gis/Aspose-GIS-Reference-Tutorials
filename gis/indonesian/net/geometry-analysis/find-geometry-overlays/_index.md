---
title: Menguasai Overlay Geometri dengan Aspose.GIS untuk .NET
linktitle: Temukan Hamparan Geometri
second_title: Aspose.GIS .NET API
description: Pelajari cara melakukan operasi overlay geometris menggunakan Aspose.GIS untuk .NET. Kuasai operasi perpotongan, penyatuan, selisih, dan selisih simetris.
type: docs
weight: 16
url: /id/net/geometry-analysis/find-geometry-overlays/
---
## Perkenalan
Dalam bidang Sistem Informasi Geografis (GIS), operasi overlay merupakan hal mendasar untuk analisis spasial. Mereka memungkinkan perbandingan dan kombinasi kumpulan data spasial yang berbeda untuk memperoleh wawasan yang berharga. Aspose.GIS untuk .NET menyediakan fungsionalitas yang kuat untuk melakukan overlay geometris secara efisien. Dalam tutorial ini, kita akan mempelajari berbagai operasi overlay seperti Intersection, Union, Difference, dan Symmetric Difference menggunakan Aspose.GIS untuk .NET.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
### 1. Lingkungan Pengembangan .NET
Pastikan Anda telah menyiapkan lingkungan pengembangan .NET di mesin Anda. Anda dapat mengunduh dan menginstal .NET SDK dari situs web .NET.
### 2. Aspose.GIS untuk Perpustakaan .NET
 Unduh dan instal perpustakaan Aspose.GIS untuk .NET dari[situs web](https://releases.aspose.com/gis/net/).
## Impor Namespace
Sebelum Anda dapat mulai menggunakan Aspose.GIS untuk .NET, Anda perlu mengimpor namespace yang diperlukan ke dalam proyek Anda.
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Langkah 1: Buat Objek Poligon
Pertama, kita akan mendefinisikan dua objek poligon yang mewakili wilayah spasial.
```csharp
var polygon1 = new Polygon();
polygon1.ExteriorRing = new LinearRing(new[]
{
	 new Point(0, 0),
	 new Point(0, 2),
	 new Point(2, 2),
	 new Point(2, 0),
	 new Point(0, 0),
 });
var polygon2 = new Polygon();
polygon2.ExteriorRing = new LinearRing(new[]
{
	new Point(1, 1),
	new Point(1, 3),
	new Point(3, 3),
	new Point(3, 1),
	new Point(1, 1),
});
```
## Langkah 2: Lakukan Operasi Persimpangan
Selanjutnya, carilah perpotongan kedua poligon tersebut.
```csharp
var intersection = polygon1.Intersection(polygon2);
Console.WriteLine("Intersection type is {0}", intersection.GeometryType); // Poligon
```
## Langkah 3: Cetak Titik Persimpangan
Kami akan mencetak titik-titik poligon perpotongan.
```csharp
PrintRing(((IPolygon)intersection).ExteriorRing);
```
## Langkah 4: Lakukan Operasi Serikat
Sekarang, mari kita cari gabungan kedua poligon tersebut.
```csharp
var union = polygon1.Union(polygon2);
Console.WriteLine("Union type is {0}", union.GeometryType); // Poligon
```
## Langkah 5: Cetak Union Point
Cetak titik-titik poligon gabungan.
```csharp
PrintRing(((IPolygon)union).ExteriorRing);
```
## Langkah 6: Lakukan Operasi Perbedaan
Selanjutnya, mari kita cari perbedaan antara kedua poligon tersebut.
```csharp
var difference = polygon1.Difference(polygon2);
Console.WriteLine("Difference type is {0}", difference.GeometryType); // Poligon
```
## Langkah 7: Cetak Poin Perbedaan
Cetak titik-titik poligon perbedaan.
```csharp
PrintRing(((IPolygon)difference).ExteriorRing);
```
## Langkah 8: Lakukan Operasi Perbedaan Simetris
Terakhir, mari kita cari perbedaan simetris antara kedua poligon.
```csharp
var symDifference = polygon1.SymDifference(polygon2);
Console.WriteLine("Symmetric Difference type is {0}", symDifference.GeometryType); // MultiPoligon
```
## Langkah 9: Cetak Poligon Beda Simetris
Cetak titik-titik setiap poligon dalam perbedaan simetris.
```csharp
var multiPolygon = (IMultiPolygon)symDifference;
Console.WriteLine("Polygons count is {0}", multiPolygon.Count); // 2
PrintRing(((IPolygon)multiPolygon[0]).ExteriorRing);
PrintRing(((IPolygon)multiPolygon[1]).ExteriorRing);
```
## Kesimpulan
Menguasai overlay geometri sangat penting dalam analisis spasial dan Aspose.GIS untuk .NET menyediakan seperangkat alat komprehensif untuk melakukan operasi ini secara efisien. Dengan mengikuti tutorial ini, Anda telah mempelajari cara memanfaatkan Aspose.GIS untuk .NET untuk melakukan operasi perpotongan, penyatuan, selisih, dan selisih simetris pada bentuk geometris.
## FAQ
### T: Bisakah saya menggunakan Aspose.GIS untuk .NET di proyek komersial saya?
Ya, Aspose.GIS untuk .NET dapat digunakan dalam proyek komersial dan non-komersial.
### T: Apakah ada versi uji coba yang tersedia untuk Aspose.GIS untuk .NET?
 Ya, Anda dapat mengunduh versi uji coba gratis dari[Di Sini](https://releases.aspose.com/).
### T: Bagaimana cara mendapatkan dukungan Aspose.GIS untuk .NET?
 Anda bisa mendapatkan dukungan dari forum komunitas Aspose.GIS[Di Sini](https://forum.aspose.com/c/gis/33).
### T: Apakah ada lisensi sementara yang tersedia untuk Aspose.GIS untuk .NET?
 Ya, lisensi sementara tersedia untuk tujuan pengujian dan evaluasi. Anda dapat memperolehnya dari[Di Sini](https://purchase.aspose.com/temporary-license/).
### T: Dapatkah saya membeli Aspose.GIS untuk .NET secara langsung?
 Ya, Anda dapat membeli Aspose.GIS untuk .NET dari situs web[Di Sini](https://purchase.aspose.com/buy).