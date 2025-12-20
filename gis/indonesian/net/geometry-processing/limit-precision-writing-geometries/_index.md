---
date: 2025-12-20
description: Pelajari cara membatasi presisi saat menulis geometri menggunakan Aspose.GIS
  untuk .NET. Panduan langkah demi langkah ini membantu Anda mengelola data spasial
  dengan kontrol koordinat yang tepat.
linktitle: Limit Precision Writing Geometries
second_title: Aspose.GIS .NET API
title: Cara Membatasi Presisi Penulisan Geometri dengan Aspose.GIS
url: /id/net/geometry-processing/limit-precision-writing-geometries/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membatasi Presisi Saat Menulis Geometri dengan Aspose.GIS

Jika Anda bertanya-tanya **cara membatasi presisi** saat menulis geometri dalam aplikasi GIS .NET, Aspose.GIS untuk .NET menyediakan cara yang sederhana dan berperforma tinggi untuk mengontrol pembulatan koordinat. Dalam tutorial ini kami akan membahas seluruh proses—dari menyiapkan lingkungan hingga memverifikasi bahwa output mematuhi aturan presisi yang Anda tentukan.

## Jawaban Cepat
- **Apa arti “membatasi presisi”?** Itu membulatkan nilai koordinat ke sejumlah digit pecahan yang ditentukan saat menulis file spasial.  
- **Format apa yang digunakan dalam contoh?** GeoJSON, tetapi opsi yang sama berlaku untuk format lain yang didukung.  
- **Apakah saya memerlukan lisensi untuk mencoba ini?** Versi percobaan gratis dapat digunakan untuk pengembangan dan pengujian; lisensi komersial diperlukan untuk produksi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Bisakah saya mengontrol presisi koordinat Z secara terpisah?** Ya—gunakan `ZPrecisionModel` untuk menetapkan nilai tepat atau dibulatkan.

## Cara Membatasi Presisi Saat Menulis Geometri
Membatasi presisi penting ketika Anda memerlukan representasi koordinat yang konsisten di berbagai alat GIS, mengurangi ukuran file, atau mematuhi standar pertukaran data. Di bawah ini kami akan mendefinisikan opsi presisi, menulis sebuah geometri, dan kemudian membacanya kembali untuk mengonfirmasi pembulatan.

## Prasyarat

### 1. Unduh dan Instalasi
Unduh paket Aspose.GIS untuk .NET terbaru dari situs resmi: [tautan unduhan](https://releases.aspose.com/gis/net/). Ikuti panduan instalasi untuk menambahkan paket NuGet ke proyek Anda.

### 2. Impor Namespace
Tambahkan namespace yang diperlukan sehingga Anda dapat mengakses kelas GIS dan utilitas pembantu.

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Panduan Langkah‑ demi‑Langkah

### Langkah 1: Definisikan Opsi Presisi
Buat instance `GeoJsonOptions` dan beri tahu Aspose.GIS berapa banyak digit pecahan yang Anda inginkan untuk koordinat X/Y dan Z.

```csharp
var options = new GeoJsonOptions
{
    // Limit X and Y coordinates to 3 fractional digits.
    XYPrecisionModel = PrecisionModel.Rounding(3),

    // Write all fractional digits of the Z coordinate.
    ZPrecisionModel = PrecisionModel.Exact
};
```

### Langkah 2: Tentukan Jalur Output
Tentukan lokasi di mana file GeoJSON yang dihasilkan akan disimpan.

```csharp
var path = "Your Document Directory" + "LimitPrecisionWhenWritingGeometries_out.json";
```

### Langkah 3: Buat dan Isi Geometri
Buka `VectorLayer` baru dengan opsi yang telah didefinisikan di atas, buat geometri `Point`, dan tambahkan ke layer.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    var point = new Point();
    point.X = 1.8888888;
    point.Y = 1.00123;
    point.Z = 1.123456789;

    Feature feature = layer.ConstructFeature();
    feature.Geometry = point;
    layer.Add(feature);
}
```

### Langkah 4: Baca dan Verifikasi Presisi
Buka file yang baru saja Anda buat dan cetak koordinatnya. Anda akan melihat nilai X/Y dibulatkan ke tiga tempat desimal sementara nilai Z tetap tepat.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.GeoJson))
{
    var point = (IPoint)layer[0].Geometry;

    // Output: 1.889, 1.001, 1.123456789
    Console.WriteLine("{0}, {1}, {2}", point.X, point.Y, point.Z);
}
```

## Masalah Umum & Tips

- **Kesalahan Jalur:** Pastikan direktori dalam `path` ada atau gunakan `Path.Combine` dengan `Environment.CurrentDirectory` untuk membangun jalur file yang aman.  
- **Presisi Tidak Diterapkan:** Pastikan Anda mengirimkan objek `GeoJsonOptions` saat membuat layer; jika tidak, presisi default (double penuh) yang digunakan.  
- **Dataset Besar:** Untuk operasi massal, pertimbangkan untuk menggunakan kembali satu instance `VectorLayer` dan menambahkan fitur secara batch untuk meningkatkan kinerja.

## Pertanyaan yang Sering Diajukan

**T: Apakah Aspose.GIS untuk .NET kompatibel dengan format GIS lain?**  
J: Ya, ia mendukung Shapefile, GeoJSON, KML, GML, dan banyak lagi, memungkinkan konversi mulus antar format.

**T: Bisakah saya mencoba Aspose.GIS untuk .NET sebelum membeli?**  
J: Tentu saja. Versi percobaan gratis tersedia di halaman unduhan, memberi Anda akses penuh ke semua fitur untuk evaluasi.

**T: Bagaimana cara mendapatkan lisensi sementara untuk pengujian?**  
J: Lisensi evaluasi sementara dapat dibuat melalui portal lisensi Aspose; lisensi tersebut berlaku selama 30 hari.

**T: Di mana saya dapat mendapatkan bantuan jika mengalami masalah?**  
J: Forum Aspose.GIS dan tag Stack Overflow `aspose-gis` adalah tempat yang bagus untuk mengajukan pertanyaan dan menemukan solusi komunitas.

**T: Apakah perpustakaan ini bekerja untuk skrip kecil maupun aplikasi skala perusahaan?**  
J: Ya, Aspose.GIS dirancang untuk menangani segala hal mulai dari prototipe cepat hingga aplikasi server dengan throughput tinggi.

## Kesimpulan
Dengan mengikuti langkah-langkah di atas, Anda kini tahu **cara membatasi presisi** saat menulis geometri dengan Aspose.GIS untuk .NET. Mengontrol pembulatan koordinat membantu menjaga data spasial Anda tetap bersih, dapat dipertukarkan, dan efisien dalam penyimpanan—manfaat utama untuk proyek yang berfokus pada GIS.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose