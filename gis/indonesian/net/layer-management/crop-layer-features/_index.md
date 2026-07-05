---
date: 2026-07-05
description: Pelajari cara memotong fitur lapisan dengan Aspose.GIS untuk .NET, termasuk
  cara memotong raster dengan poligon, mengekstrak ukuran sel raster, dan mengambil
  rentang raster. Unduh percobaan gratis Anda sekarang.
keywords:
- how to crop layer
- extract raster extent
- get raster cell size
- crop raster layer
- crop raster with polygon
linktitle: Cara Memotong Fitur Lapisan
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to crop layer features with Aspose.GIS for .NET, including
    how to crop raster with polygon, extract raster cell size, and retrieve raster
    extent. Download your free trial now.
  headline: How to Crop Layer Features with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Is a temporary license available for Aspose.GIS for .NET?
  - answer: The documentation is available [here](https://reference.aspose.com/gis/net/).
    question: Where can I find comprehensive documentation for Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for support
      and community engagement.
    question: How can I seek support or connect with the community for Aspose.GIS
      for .NET?
  - answer: Yes, you can download a free trial [here](https://releases.aspose.com/).
    question: Can I download a free trial of Aspose.GIS for .NET?
  - answer: You can purchase the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Cara Memotong Fitur Lapisan dengan Aspose.GIS untuk .NET
url: /id/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Memotong Fitur Lapisan

## Pendahuluan
Dalam tutorial ini Anda akan belajar **how to crop layer** fitur menggunakan Aspose.GIS untuk .NET, sebuah perpustakaan kuat yang memungkinkan Anda **crop raster with polygon**, **extract raster cell size**, dan **retrieve raster extent** untuk analisis geospasial yang tepat. Baik Anda menyiapkan data untuk peta web, memangkas citra satelit, atau mengisolasi wilayah yang diminati, panduan langkah‑demi‑langkah ini menunjukkan cara menyelesaikan pekerjaan dengan cepat dan dapat diandalkan.

## Jawaban Cepat
- **What does “crop layer” mean?** Itu memotong lapisan raster atau vektor ke batas geometri yang diberikan, mengabaikan semua yang berada di luar.  
- **Which geometry is used in this example?** Sebuah poligon yang didefinisikan dalam format WKT (Well‑Known Text).  
- **Can I extract cell size after cropping?** Ya – properti `CellSize` mengembalikan lebar dan tinggi sel raster.  
- **Do I need a license to run the code?** Lisensi sementara dapat digunakan untuk evaluasi; lisensi penuh diperlukan untuk penggunaan produksi.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Apa itu “how to crop layer”?
**Cropping a layer means restricting the dataset to a specific geographic area, discarding everything outside.** Operasi ini mengurangi ukuran file, mempercepat pemrosesan selanjutnya, dan memfokuskan analisis pada wilayah yang Anda pedulikan. Dengan membatasi data ke area yang diminati, Anda juga menyederhanakan alur kerja downstream seperti styling, analisis, dan publikasi, sambil mempertahankan sistem referensi koordinat dan metadata asli.

## Mengapa menggunakan Aspose.GIS untuk pemotongan?
**Aspose.GIS processes raster files up to 2 GB without loading the entire image into memory and supports more than 30 raster formats, including GeoTIFF, JPEG2000, and PNG.** Perpustakaan ini menawarkan pemanggilan `Crop` satu baris, penanganan CRS otomatis, dan kinerja multi‑threaded yang dapat memangkas GeoTIFF berukuran 500 MB dalam kurang dari satu detik pada server tipikal.

## Prasyarat
Sebelum menyelami keajaiban manipulasi geospasial, pastikan Anda memiliki prasyarat berikut:

- Aspose.GIS for .NET Library: Pastikan Anda telah menginstal perpustakaan Aspose.GIS dalam proyek .NET Anda. Anda dapat mengunduhnya dari [di sini](https://releases.aspose.com/gis/net/).  
- Document Directory: Siapkan sebuah direktori untuk menyimpan dokumen Anda. Ganti `"Your Document Directory"` dalam kode yang disediakan dengan jalur sebenarnya ke direktori dokumen Anda.

Sekarang, mari kita selami panduan langkah‑demi‑langkah.

## Impor Namespace
Namespace `Aspose.Gis` berisi semua tipe inti untuk penanganan raster dan vektor. Impor namespace ini untuk mendapatkan akses ke kelas `Layer`, `Geometry`, dan kelas terkait.

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Bagaimana cara memotong lapisan dengan poligon?
`Crop` adalah metode dari kelas `Layer` yang mengekstrak subset raster yang didefinisikan oleh sebuah geometri.  
Muat raster sumber, definisikan geometri poligon, dan panggil metode `Crop` – seluruh operasi dilakukan dalam satu baris kode. Metode ini mengembalikan raster baru yang hanya berisi piksel di dalam poligon, secara otomatis mempertahankan referensi spasial asli.

## Langkah 1: Buka dan Potong Lapisan (crop raster with polygon)
`Layer` mewakili dataset raster yang dapat dibuka, diquery, dan diedit.  
Kelas `Layer` mewakili dataset raster yang dapat dibuka, diquery, dan diedit. Membuka sebuah GeoTIFF dan memotongnya dengan poligon mengisolasi area yang diminati hanya dalam beberapa pernyataan.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## Langkah 2: Dapatkan Informasi Raster (extract raster cell size & retrieve raster extent)
`CellSize` memberikan lebar dan tinggi setiap sel raster dalam satuan koordinat.  
`Extent` mengembalikan kotak pembatas geografis raster.  
Properti `CellSize` memberikan lebar dan tinggi setiap sel raster dalam satuan koordinat, sementara properti `Extent` mengembalikan kotak pembatas geografis raster yang dipotong. Kedua informasi ini penting untuk perhitungan downstream seperti pengukuran area atau re‑projection.

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
| **Orientasi poligon tidak benar** | Pastikan poligon WKT mengikuti aturan tangan kanan (berlawanan arah jarum jam untuk cincin luar). |
| **Referensi spasial hilang** | Verifikasi bahwa GeoTiff sumber memiliki CRS; jika tidak, atur secara manual sebelum pemotongan. |
| **Penurunan kinerja pada raster besar** | Gunakan `layer.Crop` pada salinan yang di‑down‑sample atau proses raster dalam ubin. |

## Pertanyaan yang Sering Diajukan
**Q: Apakah lisensi sementara tersedia untuk Aspose.GIS untuk .NET?**  
A: Ya, Anda dapat memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

**Q: Di mana saya dapat menemukan dokumentasi komprehensif untuk Aspose.GIS untuk .NET?**  
A: Dokumentasi tersedia [di sini](https://reference.aspose.com/gis/net/).

**Q: Bagaimana saya dapat mencari dukungan atau terhubung dengan komunitas untuk Aspose.GIS untuk .NET?**  
A: Kunjungi [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) untuk dukungan dan keterlibatan komunitas.

**Q: Apakah saya dapat mengunduh trial gratis Aspose.GIS untuk .NET?**  
A: Ya, Anda dapat mengunduh trial gratis [di sini](https://releases.aspose.com/).

**Q: Di mana saya dapat membeli Aspose.GIS untuk .NET?**  
A: Anda dapat membeli perpustakaan tersebut [di sini](https://purchase.aspose.com/buy).

**Q: Apakah saya dapat memotong beberapa lapisan dalam satu kali jalankan?**  
A: Ya—lakukan loop pada setiap lapisan dan terapkan pemanggilan `Crop` yang sama dengan geometri yang diinginkan.

**Q: Apakah API mendukung format raster lain (misalnya, JPEG2000)?**  
A: Aspose.GIS mendukung semua format yang disediakan oleh driver GDAL yang mendasarinya, termasuk JPEG2000, PNG, dan lainnya.

## Kesimpulan
Dengan mengikuti panduan ini Anda kini mengetahui **how to crop layer** fitur secara efisien dengan Aspose.GIS untuk .NET. Anda dapat dengan mudah **crop raster with polygon**, **extract raster cell size**, dan **retrieve raster extent** untuk memenuhi kebutuhan proyek apa pun. Jelajahi API lebih lanjut untuk re‑projection, styling raster, dan analisis vektor untuk membuka potensi penuh alur kerja geospasial Anda.

---

**Last Updated:** 2026-07-05  
**Tested With:** Aspose.GIS 24.10 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Cara Membuat Geometri Poligon dengan Aspose.GIS untuk .NET](/gis/net/geometry-creation/create-polygon-geometry/)
- [Dapatkan Atribut Lapisan – Ambil Informasi Atribut Lapisan dengan Aspose.GIS untuk .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Buat Geometri Poligon C# dan Periksa Interseksi dengan Aspose.GIS untuk .NET](/gis/net/geometry-analysis/check-geometries-intersection/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}