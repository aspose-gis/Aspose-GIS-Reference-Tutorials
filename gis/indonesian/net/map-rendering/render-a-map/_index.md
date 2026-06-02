---
date: 2026-01-18
description: Pelajari cara menambahkan kota ke peta dan menghasilkan peta SVG menggunakan
  Aspose.GIS untuk .NET. Buat visualisasi menakjubkan dengan cepat.
linktitle: Render a Map
second_title: Aspose.GIS .NET API
title: Cara Menambahkan Kota ke Peta dengan Aspose.GIS untuk .NET
url: /id/net/map-rendering/render-a-map/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menambahkan Kota ke Peta dengan Aspose.GIS untuk .NET

## Pendahuluan
Selamat datang di dunia menarik Aspose.GIS untuk .NET! Dalam panduan langkah‑demi‑langkah ini, Anda akan belajar **cara menambahkan kota ke peta** dan menghasilkan output SVG berkualitas tinggi. Baik Anda membangun dasbor desktop maupun portal GIS berbasis web, tutorial ini menunjukkan cara menggambar lapisan vektor, mengatur dimensi peta, dan memuat peta GeoJSON dengan mudah.

## Jawaban Cepat
- **Apa yang dibahas dalam tutorial ini?** Menambahkan kota ke peta dan mengekspornya sebagai file SVG.  
- **Perpustakaan apa yang diperlukan?** Aspose.GIS untuk .NET.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis tersedia; lisensi diperlukan untuk produksi.  
- **Bisakah saya menggunakan ini dalam aplikasi web?** Ya – kode yang sama bekerja di ASP.NET, Blazor, dan kerangka kerja web .NET lainnya.  
- **Format output apa yang dihasilkan?** Peta SVG yang dapat ditampilkan di browser atau diedit lebih lanjut.

## Prasyarat
Sebelum memulai tutorial, pastikan Anda memiliki prasyarat berikut:
- **Aspose.GIS untuk .NET Library:** Pastikan perpustakaan Aspose.GIS untuk .NET sudah terpasang. Anda dapat mengunduhnya [di sini](https://releases.aspose.com/gis/net/).
- **File Data:** Siapkan shapefile dan data GeoJSON yang diperlukan untuk tutorial. Anda dapat menemukan contoh data di dokumentasi atau menggunakan file Anda sendiri.
- **Lingkungan Pengembangan:** Miliki lingkungan pengembangan .NET yang sudah disiapkan, termasuk editor kode seperti Visual Studio.

## Impor Namespace
Untuk memulai, impor namespace yang diperlukan ke dalam proyek .NET Anda. Namespace ini penting untuk bekerja dengan fungsionalitas Aspose.GIS.

```csharp
using Aspose.Gis;
using Aspose.Gis.Rendering;
using Aspose.Gis.Rendering.Symbolizers;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.Drawing.Text;
using System.IO;
using System.Linq;
```

## Langkah 1: Menyiapkan Peta (menetapkan dimensi peta)
```csharp
string dataDir = "Your Document Directory";
using (var map = new Map(800, 476))
{
    // Additional code for map setup can be added here.
}
```
Pada langkah ini, kami menginisialisasi peta baru dengan lebar 800 piksel dan tinggi 476 piksel. Sesuaikan dimensi sesuai kebutuhan desain Anda.

## Langkah 2: Menambahkan Peta Dasar (menggambar lapisan vektor)
```csharp
var baseMapSymbolizer = new SimpleFill { FillColor = Color.Salmon, StrokeWidth = 0.75 };
map.Add(VectorLayer.Open(dataDir + "basemap.shp", Drivers.Shapefile), baseMapSymbolizer);
```
Di sini, kami **menggambar lapisan vektor** untuk peta dasar menggunakan shapefile. Silakan ubah properti `SimpleFill` agar sesuai dengan gaya visual Anda.

## Langkah 3: Menambahkan Kota ke Peta (menambahkan kota ke peta, memuat peta GeoJSON)
```csharp
var citiesSymbolizer = new SimpleMarker() { FillColor = Color.LightBlue };
citiesSymbolizer.FeatureBasedConfiguration = (feature, symbolizer) =>
{
    // Additional configuration logic can be added here.
};
map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), citiesSymbolizer);
```
Langkah ini memuat file GeoJSON yang berisi data titik kota dan **menambahkan kota ke peta**. Anda dapat memperluas delegate `FeatureBasedConfiguration` untuk menata kota berdasarkan atribut seperti populasi.

## Langkah 4: Merender Peta (mengekspor peta SVG, menghasilkan peta SVG)
```csharp
map.Render(dataDir + "cities_out.svg", Renderers.Svg);
```
Akhirnya, kami **mengekspor peta sebagai file SVG**. File `cities_out.svg` yang dihasilkan dapat dibuka di browser modern mana pun atau editor grafis vektor.

## Kesimpulan
Selamat! Anda telah berhasil **menambahkan kota ke peta** dan menghasilkan peta SVG menggunakan Aspose.GIS untuk .NET. Tutorial ini menunjukkan cara mengatur dimensi peta, menggambar lapisan vektor, memuat data GeoJSON, dan mengekspor hasilnya sebagai SVG yang dapat diskalakan—sempurna untuk skenario web maupun cetak.

## FAQ
### Bisakah saya menggunakan Aspose.GIS untuk .NET dalam aplikasi web saya?
Ya, Aspose.GIS untuk .NET cocok untuk aplikasi desktop maupun web.

### Apakah ada versi percobaan yang tersedia?
Ya, Anda dapat menjelajahi versi percobaan gratis [di sini](https://releases.aspose.com/).

### Di mana saya dapat menemukan dukungan untuk Aspose.GIS untuk .NET?
Kunjungi [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) untuk bantuan atau pertanyaan apa pun.

### Bisakah saya membeli lisensi sementara untuk proyek jangka pendek?
Ya, lisensi sementara tersedia [di sini](https://purchase.aspose.com/temporary-license/).

### Apakah ada tutorial tambahan untuk Aspose.GIS untuk .NET?
Ya, periksa [dokumentasi](https://reference.aspose.com/gis/net/) untuk tutorial dan panduan lengkap.

---

**Terakhir Diperbarui:** 2026-01-18  
**Diuji Dengan:** Aspose.GIS 24.11 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}