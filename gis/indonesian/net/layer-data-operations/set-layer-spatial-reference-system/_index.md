---
date: 2025-12-31
description: Pelajari cara membuat lapisan vektor dan mengatur sistem referensi spasial
  lapisan dengan Aspose.GIS untuk .NET. Kuasai mendefinisikan referensi spasial, menambahkan
  fitur titik, dan mengambil kode EPSG.
linktitle: Set Layer Spatial Reference System
second_title: Aspose.GIS .NET API
title: Buat Lapisan Vektor dan Atur Sistem Referensi Spasial Lapisan
url: /id/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Layer Vektor dan Atur Sistem Referensi Spasial Layer

## Pendahuluan
Dalam lanskap luas Sistem Informasi Geografis (GIS), **Aspose.GIS for .NET** menonjol sebagai alat yang kuat dan serbaguna bagi pengembang. Dalam tutorial ini Anda akan **create vector layer**, mendefinisikan referensi spasialnya, menambahkan fitur titik, dan mengambil kode EPSG—semua dengan panduan langkah demi langkah yang jelas. Baik Anda seorang insinyur GIS berpengalaman maupun yang baru memulai, teknik ini akan membantu Anda mengatur sistem koordinat shapefile dengan benar dan meningkatkan keandalan alur kerja data spasial Anda.

## Jawaban Cepat
- **Apa arti “create vector layer”?** Membuat layer GIS baru (misalnya, Shapefile) yang dapat menyimpan geometri seperti titik, garis, atau poligon.  
- **Kode EPSG apa yang digunakan dalam contoh?** EPSG 26918 (NAD83 / UTM zone 18N).  
- **Bisakah saya menambahkan fitur titik setelah membuat layer?** Ya—gunakan `ConstructFeature()` dan tetapkan geometri `Point`.  
- **Bagaimana cara mengambil CRS layer?** Baca `layer.SpatialReferenceSystem.EpsgCode` atau `.Name`.  
- **Apakah saya memerlukan lisensi untuk Aspose.GIS?** Versi percobaan gratis tersedia; lisensi diperlukan untuk penggunaan produksi.

## Prasyarat
- Pengetahuan kerja tentang pemrograman .NET.  
- Visual Studio terpasang di sistem Anda.  
- Perpustakaan Aspose.GIS for .NET, yang dapat Anda unduh [di sini](https://releases.aspose.com/gis/net/).  
- Pemahaman dasar tentang sistem referensi spasial dalam GIS.

## Impor Namespace
Di proyek .NET Anda, mulailah dengan mengimpor namespace yang diperlukan untuk mengakses fungsionalitas yang disediakan oleh Aspose.GIS. Gunakan cuplikan kode berikut:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## Langkah 1: Tentukan Direktori Dokumen
Mulailah dengan menentukan path ke direktori dokumen Anda. Ini akan menjadi lokasi tempat file data spasial Anda disimpan.

```csharp
string dataDir = "Your Document Directory";
```

## Langkah 2: Definisikan Referensi Spasial dan Atur Sistem Koordinat Shapefile
Tentukan path untuk Shapefile, dan **definisikan referensi spasial** menggunakan kode EPSG (26918 dalam contoh ini). Langkah ini **mengatur sistem koordinat shapefile** untuk layer.

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## Langkah 3: Buat Layer Vektor
Sekarang **buat layer vektor** dengan path Shapefile yang telah ditentukan, tipe driver (Shapefile), dan sistem referensi spasial yang baru saja Anda definisikan.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

## Langkah 4: Tambahkan Fitur Titik ke Layer
Buat fitur baru dan **tambahkan fitur titik** dengan mengatur geometri nya (sebuah `Point` dengan koordinat 60, 24). Kemudian tambahkan fitur tersebut ke layer vektor.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

## Langkah 5: Ambil Informasi Sistem Referensi Spasial (Ambil Kode EPSG)
Buka Vector Layer dan ambil informasi tentang sistem referensi spasial, seperti kode EPSG dan nama yang dapat dibaca manusia. Ini menunjukkan cara **mengambil kode EPSG** dan **mengatur CRS layer**.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

Ulangi langkah-langkah ini sesuai dengan kasus penggunaan Anda, dan Anda akan berada di jalur yang tepat untuk menguasai seni **create vector layer** dan mengelola referensi spasial dengan Aspose.GIS untuk .NET.

## Masalah Umum dan Solusinya
| Masalah | Mengapa Terjadi | Solusi |
|-------|----------------|-----|
| **Layer gagal dibuka** | Driver salah atau path file rusak | Verifikasi `Drivers.Shapefile` dan pastikan `path` mengarah ke file `.shp` yang ada. |
| **CRS yang ditampilkan tidak tepat** | Menggunakan kode EPSG yang salah | Periksa kembali kode EPSG dengan sumber yang terpercaya (mis., EPSG.io). |
| **Fitur tidak tersimpan** | Tidak memanggil `layer.Add(feature)` di dalam blok `using` | Pastikan metode `Add` dijalankan sebelum layer dibuang. |

## Pertanyaan yang Sering Diajukan
### Apakah Aspose.GIS kompatibel dengan perpustakaan GIS lain?
Ya, Aspose.GIS terintegrasi dengan baik dengan perpustakaan GIS lain dan dapat digunakan bersamaan dengan mereka.

### Bisakah saya menggunakan Aspose.GIS untuk aplikasi desktop dan web?
Tentu saja! Aspose.GIS serbaguna dan dapat digunakan baik pada aplikasi desktop maupun berbasis web.

### Apakah ada opsi lisensi yang tersedia untuk Aspose.GIS?
Ya, Anda dapat menjelajahi opsi lisensi dan melakukan pembelian [di sini](https://purchase.aspose.com/buy).

### Apakah ada versi percobaan gratis untuk Aspose.GIS?
Tentu! Anda dapat mengunduh versi percobaan gratis [di sini](https://releases.aspose.com/).

### Di mana saya dapat mencari dukungan untuk pertanyaan terkait Aspose.GIS?
Untuk dukungan atau pertanyaan, kunjungi [forum Aspose.GIS](https://forum.aspose.com/c/gis/33).

## Pertanyaan Tambahan yang Sering Diajukan
**Q: Bagaimana cara mengubah CRS dari Shapefile yang ada?**  
A: Buka layer, buat `SpatialReferenceSystem` baru dengan kode EPSG yang diinginkan, dan tetapkan ke `layer.SpatialReferenceSystem` sebelum menyimpan.

**Q: Bisakah saya menambahkan tipe geometri lain (mis., poligon) dengan pendekatan yang sama?**  
A: Ya—ganti `new Point(x, y)` dengan `new Polygon(...)` atau `new LineString(...)` sesuai kebutuhan.

**Q: Apakah memungkinkan bekerja dengan dataset besar secara efisien?**  
A: Gunakan API streaming (`VectorLayer.Create` dengan `FeatureCollection`) dan segera buang layer untuk membebaskan sumber daya.

**Q: Apakah Aspose.GIS mendukung transformasi koordinat?**  
A: Ya—gunakan `Geometry.Transform(targetSrs)` untuk memproyeksikan ulang geometri antara referensi spasial yang berbeda.

**Q: Versi .NET apa yang didukung?**  
A: Aspose.GIS bekerja dengan .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.

## Kesimpulan
Dalam tutorial ini kami mengeksplorasi cara **create vector layer**, mendefinisikan referensi spasialnya, **menambahkan fitur titik**, dan **mengambil kode EPSG** menggunakan Aspose.GIS untuk .NET. Dengan menguasai langkah-langkah ini Anda dapat dengan yakin mengatur sistem koordinat shapefile, mengelola CRS layer, dan membangun aplikasi GIS yang handal.

---

**Last Updated:** 2025-12-31  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}