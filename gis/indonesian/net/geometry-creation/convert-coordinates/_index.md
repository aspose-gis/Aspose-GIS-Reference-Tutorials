---
title: Koordinasikan Konversi dengan Aspose.GIS
linktitle: Konversi Koordinat
second_title: Aspose.GIS .NET API
description: Pelajari cara mengonversi koordinat dengan Aspose.GIS untuk .NET. Panduan langkah demi langkah, prasyarat, dan FAQ disediakan.
weight: 25
url: /id/net/geometry-creation/convert-coordinates/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Koordinasikan Konversi dengan Aspose.GIS

## Perkenalan
Dalam tutorial ini, kita akan mempelajari dunia sistem informasi geografis (GIS) menggunakan perpustakaan Aspose.GIS yang canggih untuk .NET. Aspose.GIS adalah perangkat komprehensif yang memberdayakan pengembang untuk bekerja dengan data spasial dengan mudah. Baik Anda seorang pengembang berpengalaman atau baru memulai, tutorial ini akan memandu Anda melalui proses penggunaan Aspose.GIS untuk mengonversi koordinat secara efektif.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
1. Pengetahuan Dasar C#: Keakraban dengan bahasa pemrograman C# sangat penting untuk memahami dan mengimplementasikan contoh kode yang diberikan.
  
2.  Instalasi Aspose.GIS: Pastikan Anda telah mengunduh dan menginstal perpustakaan Aspose.GIS untuk .NET. Anda dapat mengunduhnya dari[Situs web Aspose.GIS](https://releases.aspose.com/gis/net/).

## Impor Namespace
Sebelum memulai, mari impor namespace yang diperlukan untuk mengakses fungsi Aspose.GIS:
```csharp
using System;
using Aspose.Gis;
```

Mari kita bagi contoh yang diberikan menjadi beberapa langkah untuk pemahaman yang jelas:
## Langkah 1: Mulai Proses Konversi
```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```
Baris ini hanya menampilkan pesan yang menunjukkan dimulainya proses konversi koordinat.
## Langkah 2: Konversikan ke Derajat Desimal
```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```
 Di sini, kami mengonversi koordinat (25.5, 45.5) ke format derajat desimal menggunakan`AsPointText` metode dengan`PointFormats.DecimalDegrees` parameter. Hasilnya kemudian dicetak ke konsol.
## Langkah 3: Konversikan ke Derajat Menit Desimal
```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```
Langkah ini mengubah koordinat ke format menit desimal derajat dan mencetak hasilnya.
## Langkah 4: Konversikan ke Derajat Menit Detik
```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```
Demikian pula, kami mengonversi koordinat ke format derajat menit detik dan menampilkan hasilnya.
## Langkah 5: Konversikan ke GeoRef
```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```
Terakhir, kita ubah koordinatnya ke format GeoRef dan cetak hasilnya.

## Kesimpulan
Dalam tutorial ini, kita telah menjelajahi proses konversi koordinat menggunakan Aspose.GIS untuk .NET. Dengan mengikuti panduan langkah demi langkah dan memanfaatkan perpustakaan Aspose.GIS, Anda dapat memanipulasi data spasial secara efisien dalam aplikasi .NET Anda.
## FAQ
### Apakah Aspose.GIS kompatibel dengan bahasa pemrograman lain?
Aspose.GIS terutama menargetkan pengembang .NET, namun menawarkan interoperabilitas dengan Java melalui Aspose.GIS untuk Java.
### Bisakah saya mencoba Aspose.GIS sebelum membeli?
 Ya, Anda dapat mengakses uji coba gratis Aspose.GIS dari[situs web](https://releases.aspose.com/).
### Bagaimana saya bisa mendapatkan dukungan untuk Aspose.GIS?
 Anda dapat mencari bantuan dari forum komunitas Aspose.GIS[Di Sini](https://forum.aspose.com/c/gis/33).
### Apakah lisensi sementara tersedia untuk Aspose.GIS?
 Ya, izin sementara dapat diperoleh dari[halaman lisensi sementara](https://purchase.aspose.com/temporary-license/).
### Dimana saya bisa membeli Aspose.GIS?
 Anda dapat membeli Aspose.GIS dari[halaman pembelian](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
