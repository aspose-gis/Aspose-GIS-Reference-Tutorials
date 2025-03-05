---
title: Menguasai Pelabelan Fitur dengan Aspose.GIS untuk .NET
linktitle: Fitur Label pada Peta
second_title: Aspose.GIS .NET API
description: Jelajahi Aspose.GIS untuk .NET dan kuasai seni pelabelan fitur pada peta. Tingkatkan visualisasi geospasial Anda dengan mudah. #Asumsikan #GIS
type: docs
weight: 11
url: /id/net/map-rendering/label-features-on-map/
---
## Perkenalan
Dalam dunia visualisasi data geospasial, pelabelan fitur pada peta memainkan peran penting dalam menyampaikan informasi secara efektif. Aspose.GIS untuk .NET menyediakan perangkat canggih untuk mencapai hal ini dengan lancar. Dalam tutorial ini, kita akan menjelajahi berbagai metode pelabelan titik pada peta menggunakan Aspose.GIS, sehingga menyempurnakan visualisasi peta Anda dengan label yang informatif.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
- Pengetahuan tentang C# dan kerangka .NET.
-  Aspose.GIS untuk .NET diinstal. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/gis/net/).
- File GeoJSON yang berisi data titik. Jika Anda tidak memilikinya, Anda dapat menggunakan file sampel untuk pengujian.
## Impor Namespace
Dalam kode C# Anda, pastikan Anda mengimpor namespace yang diperlukan untuk bekerja dengan Aspose.GIS:
```csharp
using System;
using System.Drawing;
using Aspose.Gis;
using Aspose.Gis.Rendering;
using Aspose.Gis.Rendering.Labelings;
using Aspose.Gis.Rendering.Symbolizers;
using Aspose.GIS.Examples.CSharp;
using FontStyle = Aspose.Gis.Rendering.Labelings.FontStyle;
```
Sekarang, mari kita bagi setiap contoh menjadi beberapa langkah dalam format panduan langkah demi langkah.
##  Pelabelan Poin

### Langkah 1: Tetapkan jalur ke direktori dokumen Anda:
```csharp
string dataDir = "Your Document Directory";
```
### Langkah 2: Buat peta dengan simbol penanda sederhana:
```csharp
using (var map = new Map(500, 200))
{
    var symbol = new SimpleMarker
    {
        FillColor = Color.LightGray,
        StrokeStyle = StrokeStyle.None
    };
    var labeling = new SimpleLabeling(labelAttribute: "name");
    // 3. Tambahkan layer vektor dan terapkan pelabelan
    map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), symbol, labeling);
    map.Padding = 50;
    // 4. Render peta ke file SVG
    map.Render(dataDir + "points_labeling_out.svg", Renderers.Svg);
}
```
## Gaya Pelabelan Poin

Ikuti langkah 1 dan 2 dari contoh sebelumnya.

### Langkah 1: Sesuaikan gaya pelabelan:
```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 2,
    HaloColor = Color.LightGray,
    FontSize = 15,
    FontStyle = FontStyle.Italic,
};
// Langkah-langkah lainnya tetap sama
```
## Pelabelan Poin Ditempatkan

Ikuti langkah 1 dan 2 dari contoh pertama.
### Langkah 2: Sesuaikan penempatan label:
```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 1,
    Placement = new PointLabelPlacement
    {
        VerticalAnchorPoint = VerticalAnchor.Bottom,
        HorizontalAnchorPoint = HorizontalAnchor.Left,
        HorizontalOffset = 2,
        VerticalOffset = 2,
        Rotation = 10,
    }
};
// Langkah-langkah lainnya tetap sama
```
## Berbasis Fitur Pelabelan Poin

Ikuti langkah 1 dan 2 dari contoh pertama.

### Langkah 1: Terapkan pelabelan berbasis fitur:
```csharp
var pointLabeling = new SimpleLabeling("name")
{
    HaloSize = 1,
    Placement = new PointLabelPlacement
    {
        VerticalAnchorPoint = VerticalAnchor.Bottom,
        HorizontalAnchorPoint = HorizontalAnchor.Left,
        VerticalOffset = 4,
        HorizontalOffset = 4,
    },
    FeatureBasedConfiguration = (feature, labeling) =>
    {
        // Ambil populasi dari fitur tersebut.
        var population = feature.GetValue<int>("population");
        // Ukuran font dihitung dan didasarkan pada populasi.
        labeling.FontSize = Math.Min(20, 5 * population / 1000);
        // Prioritas label juga didasarkan pada jumlah penduduk.
        // Semakin besar prioritasnya, semakin besar kemungkinan label muncul pada gambar keluaran.
        labeling.Priority = population;
    }
};
// Langkah-langkah lainnya tetap sama
```
## Kesimpulan
Selamat! Anda telah mempelajari cara menyempurnakan visualisasi peta dengan memberi label fitur menggunakan Aspose.GIS untuk .NET. Bereksperimenlah dengan berbagai gaya dan penempatan untuk membuat peta menarik yang disesuaikan dengan data Anda.
## FAQ
### Bisakah saya memberi label fitur menggunakan font khusus?
Ya, Anda dapat menyesuaikan gaya dan ukuran font dalam konfigurasi pelabelan.
### Apakah Aspose.GIS kompatibel dengan format data GIS lainnya?
Aspose.GIS mendukung berbagai format geospasial, termasuk GeoJSON, Shapefile, dan banyak lagi.
### Bagaimana cara menangani kumpulan data besar untuk diberi label?
Aspose.GIS dioptimalkan untuk kinerja, namun pertimbangkan untuk menggunakan konfigurasi berbasis fitur untuk memprioritaskan label berdasarkan atribut data.
### Apakah tersedia opsi penempatan label lanjutan?
Ya, Anda dapat menyempurnakan penempatan label menggunakan opsi seperti rotasi, titik jangkar, dan offset.
### Bisakah saya mengotomatiskan pembuatan label dalam proses batch?
Tentu saja, Anda dapat mengintegrasikan Aspose.GIS ke dalam alur kerja otomatis Anda untuk pembuatan label batch.