---
date: 2026-01-15
description: Pelajari cara memberi label pada fitur peta menggunakan Aspose.GIS untuk
  .NET, dengan opsi gaya label khusus untuk pelabelan dataset besar.
linktitle: Label Features on Map
second_title: Aspose.GIS .NET API
title: Label Fitur Peta dengan Aspose.GIS untuk .NET
url: /id/net/map-rendering/label-features-on-map/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Fitur Peta Label dengan Aspose.GIS untuk .NET

## Pendahuluan
Labeling map features is essential for turning raw geospatial data into clear, user‑friendly visualizations. In this tutorial you’ll discover **how to label map features** (the primary keyword) using Aspose.GIS for .NET, explore custom label styles, and see techniques that work even with large datasets. By the end you’ll be able to add informative text directly onto your maps, making them more insightful for analysts and end‑users alike.

## Jawaban Cepat
- **Apa kelas utama untuk rendering?** `Map` (Aspose.Gis.Rendering)
- **Kelas pelabelan mana yang menambahkan teks sederhana?** `SimpleLabeling`
- **Bisakah saya menata label (halo, font, rotasi)?** Ya – melalui properti seperti `HaloSize`, `FontStyle`, dan `Placement`
- **Bagaimana menangani dataset besar?** Gunakan `FeatureBasedConfiguration` untuk memprioritaskan label berdasarkan nilai atribut
- **Apakah saya memerlukan lisensi?** Versi percobaan dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi

## Apa itu label map features?
`label map features` berarti menempelkan teks yang dapat dibaca (seperti nama kota, angka populasi, atau pengidentifikasi khusus) pada objek geometris—titik, garis, atau poligon—sehingga peta menyampaikan informasi spasial dan atribut sekaligus secara sekilas.

## Mengapa menggunakan Aspose.GIS untuk label map features?
- **Tanpa ketergantungan eksternal** – perpustakaan .NET murni, tidak memerlukan binary GIS native.  
- **Opsi penataan yang kaya** – halo, font khusus, rotasi, dan titik jangkar memungkinkan Anda menyesuaikan tampilan secara detail.  
- **Berorientasi kinerja** – pelabelan berbasis fitur bawaan memungkinkan Anda memprioritaskan label terpenting saat merender dataset besar.  
- **Berbagai format output** – SVG, PNG, PDF, dll., dengan hasil pelabelan yang konsisten.

## Prasyarat
Sebelum Anda memulai, pastikan Anda memiliki:

- Pengetahuan dasar tentang C# dan kerangka kerja .NET.  
- Aspose.GIS untuk .NET terpasang. Anda dapat mengunduhnya **[di sini](https://releases.aspose.com/gis/net/)**.  
- File GeoJSON yang berisi data titik (atau format vektor lain yang didukung).  

## Impor Namespace
Dalam kode C# Anda, impor namespace yang diperlukan:

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

Sekarang kita akan membahas beberapa skenario pelabelan, masing‑masing dibangun di atas contoh sebelumnya.

## Pelabelan Titik – Cara melabeli titik
### Langkah 1: Atur jalur ke direktori dokumen Anda
```csharp
string dataDir = "Your Document Directory";
```

### Langkah 2: Buat peta dengan simbol penanda sederhana
```csharp
using (var map = new Map(500, 200))
{
    var symbol = new SimpleMarker
    {
        FillColor = Color.LightGray,
        StrokeStyle = StrokeStyle.None
    };
    var labeling = new SimpleLabeling(labelAttribute: "name");
    // 3. Add a vector layer and apply labeling
    map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), symbol, labeling);
    map.Padding = 50;
    // 4. Render the map to an SVG file
    map.Render(dataDir + "points_labeling_out.svg", Renderers.Svg);
}
```

Dalam contoh dasar ini kami **melabeli titik** menggunakan atribut `name` dari file GeoJSON.

## Pelabelan Titik dengan Gaya – Gaya label khusus
Ikuti langkah 1 dan 2 dari contoh sebelumnya, lalu sesuaikan gaya pelabelan:

```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 2,
    HaloColor = Color.LightGray,
    FontSize = 15,
    FontStyle = FontStyle.Italic,
};
// Rest of the steps remain the same
```

Halo dan font miring yang ditambahkan memberikan label **gaya label khusus** yang menonjol di latar belakang yang ramai.

## Pelabelan Titik dengan Penempatan – Opsi penempatan lanjutan
Sekali lagi mulai dengan langkah 1 dan 2 dari contoh pertama, lalu sesuaikan penempatan:

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
// Rest of the steps remain the same
```

Di sini kami mengontrol titik jangkar, offset, dan rotasi, memberi Anda kontrol detail atas **cara melabeli titik** di area peta yang padat.

## Pelabelan Titik Berbasis Fitur – Pelabelan dataset besar
Saat menangani banyak titik, Anda mungkin ingin memprioritaskan label berdasarkan atribut seperti populasi. Ikuti langkah 1 dan 2 dari contoh pertama, lalu terapkan pelabelan berbasis fitur:

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
        // Retrieve population from the feature.
        var population = feature.GetValue<int>("population");
        // Font size is computed and is based on the population.
        labeling.FontSize = Math.Min(20, 5 * population / 1000);
        // Priority of the label is also based on the population.
        // The greater the priority is, the more likely label will appear on the output image.
        labeling.Priority = population;
    }
};
// Rest of the steps remain the same
```

Strategi **pelabelan dataset besar** ini memastikan bahwa kota terpenting (berdasarkan populasi) ditampilkan terlebih dahulu, sementara titik yang kurang penting dapat dihilangkan ketika ruang terbatas.

## Kesimpulan
Selamat! Anda kini mengetahui berbagai cara untuk **melabeli fitur peta** dengan Aspose.GIS untuk .NET—dari pelabelan titik sederhana hingga penataan berbasis fitur yang canggih untuk dataset besar. Bereksperimenlah dengan halo, rotasi, dan aturan prioritas untuk membuat peta yang menyampaikan tepat apa yang perlu dilihat oleh audiens Anda.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya melabeli fitur menggunakan font khusus?**  
A: Ya. Atur `FontFamily` dan `FontStyle` dalam konfigurasi `SimpleLabeling` untuk menggunakan font apa pun yang terpasang.

**Q: Apakah Aspose.GIS kompatibel dengan format data GIS lainnya?**  
A: Tentu saja. Ia mendukung GeoJSON, Shapefile, KML, GML, dan banyak format lainnya.

**Q: Bagaimana saya dapat menangani dataset besar untuk pelabelan?**  
A: Gunakan `FeatureBasedConfiguration` untuk menetapkan prioritas dan menyesuaikan ukuran font secara dinamis berdasarkan nilai atribut, seperti yang ditunjukkan pada contoh berbasis fitur.

**Q: Apakah ada opsi penempatan label lanjutan yang tersedia?**  
A: Ya. Anda dapat menyesuaikan penempatan dengan `PointLabelPlacement`, mengatur titik jangkar, offset, dan rotasi.

**Q: Bisakah saya mengotomatisasi pembuatan label dalam proses batch?**  
A: Tentu. Bungkus kode rendering peta dalam loop atau layanan latar belakang untuk memproses beberapa lapisan atau file secara otomatis.

---

**Terakhir Diperbarui:** 2026-01-15  
**Diuji Dengan:** Aspose.GIS 24.11 for .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}