---
title: Membaca GeoJSON dari Stream dengan Aspose.GIS untuk .NET
linktitle: Baca GeoJSON dari Stream
second_title: Aspose.GIS .NET API
description: Pelajari cara membaca GeoJSON dari aliran menggunakan Aspose.GIS untuk .NET. Ikuti panduan langkah demi langkah kami untuk integrasi geospasial yang lancar ke dalam aplikasi Anda.
weight: 14
url: /id/net/layer-data-operations/read-geojson-from-stream/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Membaca GeoJSON dari Stream dengan Aspose.GIS untuk .NET

## Perkenalan
Selamat datang di panduan langkah demi langkah kami tentang penggunaan Aspose.GIS untuk .NET untuk membaca GeoJSON dari aliran. Aspose.GIS adalah API canggih yang menyediakan kemampuan geospasial untuk aplikasi .NET, memungkinkan Anda bekerja dengan berbagai format GIS secara lancar. Dalam tutorial ini, kami akan memandu Anda melalui proses membaca data GeoJSON dari aliran menggunakan Aspose.GIS, menguraikan setiap langkah untuk kejelasan dan kemudahan pemahaman.
## Prasyarat
Sebelum kita masuk ke tutorialnya, pastikan Anda memiliki prasyarat berikut:
1. Pengetahuan Dasar C#: Anda harus familiar dengan bahasa pemrograman C# dan sintaksnya.
2.  Instalasi Aspose.GIS: Pastikan Anda telah menginstal Aspose.GIS untuk .NET. Jika tidak, Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/gis/net/).
3. Lingkungan Pengembangan: Siapkan lingkungan pengembangan pilihan Anda, seperti Visual Studio atau JetBrains Rider.

## Impor Namespace
Untuk memulai, mari impor namespace yang diperlukan dalam kode C# Anda:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## Langkah 1: Tentukan Data GeoJSON
Pertama, kita perlu mendefinisikan data GeoJSON sebagai string dalam kode C# kita. Misalnya:
```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```
## Langkah 2: Baca GeoJSON dari Stream
Selanjutnya, kita akan membaca data GeoJSON dari aliran menggunakan Aspose.GIS:
```csharp
using (var memoryStream = new MemoryStream(Encoding.UTF8.GetBytes(geoJson)))
using (var layer = VectorLayer.Open(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    Console.WriteLine(layer.Count); // Keluaran: 2
    Console.WriteLine(layer[1].GetValue<string>("name")); // Keluaran: Maria
}
```

## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara membaca data GeoJSON dari aliran menggunakan Aspose.GIS untuk .NET. Dengan mengikuti langkah-langkah yang diuraikan di atas, Anda dapat mengintegrasikan kemampuan geospasial ke dalam aplikasi .NET Anda dengan mudah.
## FAQ
### Apakah Aspose.GIS kompatibel dengan format GIS lainnya?
Ya, Aspose.GIS mendukung berbagai format GIS seperti GeoJSON, Shapefile, KML, dan lainnya.
### Bisakah saya mencoba Aspose.GIS sebelum membeli?
 Ya, Anda dapat mengunduh uji coba gratis Aspose.GIS dari[Di Sini](https://releases.aspose.com/).
### Di mana saya dapat menemukan dokumentasi untuk Aspose.GIS?
 Anda dapat menemukan dokumentasi untuk Aspose.GIS[Di Sini](https://reference.aspose.com/gis/net/).
### Bagaimana saya bisa mendapatkan dukungan untuk Aspose.GIS?
 Anda bisa mendapatkan dukungan untuk Aspose.GIS di forum Aspose[Di Sini](https://forum.aspose.com/c/gis/33).
### Apakah saya memerlukan lisensi sementara untuk menggunakan Aspose.GIS?
 Anda dapat memperoleh lisensi sementara untuk Aspose.GIS dari[Di Sini](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
