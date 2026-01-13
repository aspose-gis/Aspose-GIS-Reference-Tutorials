---
date: 2026-01-13
description: Pelajari cara memotong fitur lapisan dengan Aspose.GIS untuk .NET, termasuk
  cara memotong raster dengan poligon, mengekstrak ukuran sel raster, dan mengambil
  batas raster. Unduh percobaan gratis Anda sekarang.
linktitle: How to Crop Layer Features
second_title: Aspose.GIS .NET API
title: Cara Memotong Fitur Lapisan dengan Aspose.GIS untuk .NET
url: /id/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Memotong Fitur Layer

## Pendahuluan
Dalam tutorial ini Anda akan mempelajari **cara memotong layer** fitur menggunakan Aspose.GIS untuk .NET, pendekatan yang kuat yang memungkinkan Anda **memotong raster dengan poligon**, **mengekstrak ukuran sel raster**, dan **mengambil batas raster** untuk analisis geospasial yang tepat. Baik Anda menyiapkan data untuk peta web, memotong citra satelit, atau mengisolasi wilayah yang diminati, panduan langkah demi langkah ini menunjukkan secara tepat cara menyelesaikannya.

## Jawaban Cepat
- **Apa arti “crop layer”?** Itu memotong layer raster atau vektor ke batas geometri yang diberikan.  
- **Geometri apa yang digunakan dalam contoh ini?** Poligon yang didefinisikan dalam format WKT.  
- **Bisakah saya mengekstrak ukuran sel setelah memotong?** Ya – properti `CellSize` menyediakan informasi tersebut.  
- **Apakah saya memerlukan lisensi untuk menjalankan kode?** Lisensi sementara dapat digunakan untuk evaluasi; lisensi penuh diperlukan untuk produksi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Apa itu “cara memotong layer”?
Memotong layer berarti membatasi dataset ke area geografis tertentu, membuang semua yang berada di luar bentuk yang didefinisikan. Hal ini mengurangi ukuran file, mempercepat pemrosesan, dan memfokuskan analisis pada wilayah yang Anda pedulikan.

## Mengapa menggunakan Aspose.GIS untuk memotong?
- **Penanganan raster berperforma tinggi** – ideal untuk file GeoTiff besar.  
- **API sederhana** – pemanggilan `Crop` satu baris dengan geometri apa pun.  
- **Kompatibilitas .NET penuh** – berfungsi di aplikasi desktop, server, dan cloud.  
- **Penanganan referensi spasial yang akurat** – secara otomatis mempertahankan informasi CRS.

## Prasyarat
Sebelum menyelami keajaiban manipulasi geospasial, pastikan Anda telah menyiapkan prasyarat berikut:

- Aspose.GIS for .NET Library: Pastikan Anda telah menginstal library Aspose.GIS dalam proyek .NET Anda. Anda dapat mengunduhnya dari [here](https://releases.aspose.com/gis/net/).  
- Document Directory: Siapkan direktori untuk menyimpan dokumen Anda. Ganti `"Your Document Directory"` dalam kode yang disediakan dengan jalur aktual ke direktori dokumen Anda.

Sekarang, mari kita selami panduan langkah demi langkah.

## Impor Namespace
Mulailah dengan mengimpor namespace yang diperlukan untuk memanfaatkan kekuatan penuh Aspose.GIS:

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Langkah 1: Buka dan Potong Layer (memotong raster dengan poligon)
Mulailah dengan membuka layer GeoTiff dan memotongnya berdasarkan poligon yang didefinisikan. Ini memastikan data geospasial Anda dipersempit ke area minat tertentu.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## Langkah 2: Ambil Informasi Raster (ekstrak ukuran sel raster & ambil batas raster)
Setelah layer dipotong, ekstrak informasi penting tentang data raster, seperti ukuran sel, sistem referensi spasial, dan batasnya.

```csharp
// read and print raster
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
```

## Langkah 3: Tampilkan Informasi
Cetak informasi yang diekstrak untuk memahami dampak proses pemotongan pada data geospasial Anda.

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"source extent: {layer.GetExtent()}");
Console.WriteLine($"target extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
```

Ulangi langkah-langkah ini sesuai kebutuhan untuk menyempurnakan dan menyesuaikan data geospasial Anda agar memenuhi persyaratan proyek tertentu.

## Masalah Umum dan Solusinya
| Masalah | Solusi |
|-------|----------|
| **Orientasi poligon tidak tepat** | Pastikan poligon WKT mengikuti aturan tangan kanan (berlawanan arah jarum jam untuk cincin luar). |
| **Referensi spasial hilang** | Verifikasi bahwa GeoTiff sumber memiliki CRS; jika tidak, tetapkan secara manual sebelum memotong. |
| **Penurunan kinerja pada raster besar** | Gunakan `layer.Crop` pada salinan yang di‑down‑sample atau proses raster dalam ubin. |

## Pertanyaan yang Sering Diajukan
### Q: Apakah lisensi sementara tersedia untuk Aspose.GIS untuk .NET?
A: Ya, Anda dapat memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

### Q: Di mana saya dapat menemukan dokumentasi lengkap untuk Aspose.GIS untuk .NET?
A: Dokumentasi tersedia [di sini](https://reference.aspose.com/gis/net/).

### Q: Bagaimana cara mendapatkan dukungan atau terhubung dengan komunitas untuk Aspose.GIS untuk .NET?
A: Kunjungi [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) untuk dukungan dan interaksi komunitas.

### Q: Bisakah saya mengunduh versi percobaan gratis Aspose.GIS untuk .NET?
A: Ya, Anda dapat mengunduh percobaan gratis [di sini](https://releases.aspose.com/).

### Q: Di mana saya dapat membeli Aspose.GIS untuk .NET?
A: Anda dapat membeli perpustakaan tersebut [di sini](https://purchase.aspose.com/buy).

### Q: Bisakah saya memotong beberapa layer dalam satu kali jalankan?
A: Ya—lakukan loop pada setiap layer dan terapkan pemanggilan `Crop` yang sama dengan geometri yang diinginkan.

### Q: Apakah API mendukung format raster lain (misalnya JPEG2000)?
A: Aspose.GIS mendukung semua format yang diekspos oleh driver GDAL di bawahnya, termasuk JPEG2000, PNG, dan lainnya.

## Kesimpulan
Dengan mengikuti panduan ini Anda kini tahu **cara memotong layer** fitur secara efisien menggunakan Aspose.GIS untuk .NET. Anda dapat dengan mudah **memotong raster dengan poligon**, **mengekstrak ukuran sel raster**, dan **mengambil batas raster** untuk memenuhi kebutuhan proyek apa pun. Jelajahi API lebih lanjut untuk reproyeksi, styling raster, dan analisis vektor guna membuka potensi penuh alur kerja geospasial Anda.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-13  
**Tested With:** Aspose.GIS 24.10 for .NET  
**Author:** Aspose