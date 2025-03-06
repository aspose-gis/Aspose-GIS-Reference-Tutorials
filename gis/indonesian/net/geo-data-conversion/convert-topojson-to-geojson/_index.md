---
title: Ubah TopoJSON menjadi GeoJSON
linktitle: Ubah TopoJSON menjadi GeoJSON
second_title: Aspose.GIS .NET API
description: Pelajari cara mengonversi TopoJSON ke GeoJSON dengan lancar menggunakan Aspose.GIS untuk .NET. Ikuti tutorial langkah demi langkah kami untuk penanganan data geografis yang efisien.
weight: 16
url: /id/net/geo-data-conversion/convert-topojson-to-geojson/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ubah TopoJSON menjadi GeoJSON

## Perkenalan
Dalam tutorial ini, kita akan mempelajari proses konversi dari TopoJSON ke GeoJSON menggunakan Aspose.GIS untuk .NET. Aspose.GIS adalah API canggih yang dirancang untuk memfasilitasi pemrosesan informasi geografis dalam aplikasi .NET. TopoJSON dan GeoJSON adalah format yang banyak digunakan untuk merepresentasikan data geografis, dan kemampuan mengonversi keduanya sangat penting untuk berbagai aplikasi GIS.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1.  Aspose.GIS untuk .NET: Pastikan Anda telah mengunduh dan menginstal perpustakaan Aspose.GIS untuk .NET. Anda dapat mengunduhnya dari[Situs web Aspose.GIS](https://releases.aspose.com/gis/net/).
2. Lingkungan Pengembangan: Anda memerlukan lingkungan pengembangan yang berfungsi dengan .NET terinstal.
3. Contoh File TopoJSON: Siapkan contoh file TopoJSON untuk dikonversi. Jika belum memilikinya, Anda bisa membuat atau memperolehnya dari berbagai sumber.

## Impor Namespace
Sebelum melanjutkan konversi, impor namespace yang diperlukan ke proyek Anda. Namespace ini akan memberikan akses ke fungsionalitas yang diperlukan untuk konversi TopoJSON ke GeoJSON.

   ```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Sekarang setelah Anda menyiapkan lingkungan dan mengimpor namespace yang diperlukan, mari kita uraikan proses konversi TopoJSON ke GeoJSON menjadi petunjuk langkah demi langkah.
## Langkah 1: Tentukan Jalur Input dan Output

Tentukan jalur untuk file masukan TopoJSON dan file GeoJSON keluaran.
```csharp
var sampleTopoJsonPath = "Your Document Directory" + "sample.topojson";
var outputFilePath = "Your Document Directory" + "convertedSample_out.geojson";
```
##  Langkah 2: Lakukan Konversi Memanfaatkan`VectorLayer.Convert` method to convert TopoJSON to GeoJSON.
```csharp
VectorLayer.Convert(sampleTopoJsonPath, Drivers.TopoJson, outputFilePath, Drivers.GeoJson);
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara mengonversi TopoJSON ke GeoJSON menggunakan Aspose.GIS untuk .NET. Dengan mengikuti langkah-langkah yang diuraikan dan memanfaatkan perpustakaan Aspose.GIS, Anda dapat menangani konversi data geografis dalam aplikasi .NET Anda dengan lancar.
## FAQ
### Bisakah Aspose.GIS menangani kumpulan data geografis yang besar?
Ya, Aspose.GIS mampu memproses kumpulan data geografis berukuran besar secara efisien, sehingga memastikan kinerja optimal.
### Apakah Aspose.GIS kompatibel dengan format file GIS yang berbeda?
Tentu saja, Aspose.GIS mendukung berbagai format file GIS, termasuk TopoJSON, GeoJSON, Shapefile, dan banyak lagi.
### Apakah Aspose.GIS menyediakan dokumentasi dan dukungan?
 Ya, dokumentasi dan dukungan komprehensif tersedia melalui[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33).
### Bisakah saya mencoba Aspose.GIS sebelum membeli?
 Ya, Anda dapat memanfaatkan uji coba gratis dari[Asumsikan situs web](https://releases.aspose.com/).
### Bagaimana saya bisa mendapatkan lisensi sementara untuk Aspose.GIS?
 Anda dapat memperoleh lisensi sementara dari[Asumsikan halaman pembelian](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
