---
date: 2026-05-31
description: Pelajari cara membatasi presisi saat menulis geometri dengan Aspose.GIS
  untuk .NET, mengurangi ukuran GeoJSON dan menjaga kontrol koordinat.
keywords:
- how to limit precision
- reduce geojson size
- Aspose.GIS precision control
linktitle: Membatasi Presisi Penulisan Geometri
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to limit precision when writing geometries with Aspose.GIS
    for .NET, reducing GeoJSON size and keeping coordinate control.
  headline: How to Limit Precision Writing Geometries with Aspose.GIS
  type: TechArticle
- description: Learn how to limit precision when writing geometries with Aspose.GIS
    for .NET, reducing GeoJSON size and keeping coordinate control.
  name: How to Limit Precision Writing Geometries with Aspose.GIS
  steps:
  - name: Define Precision Options
    text: The `GeoJsonOptions` class lets you specify how many fractional digits to
      keep for X/Y and Z coordinates. `PrecisionModel` defines how coordinate values
      are rounded or kept exact during writing.
  - name: Set Output Path
    text: Specify where the resulting GeoJSON file will be saved. `VectorLayer` is
      Aspose.GIS's container for a collection of features that share the same schema;
      it writes to the path you provide using the options set earlier.
  - name: Create and Populate Geometry
    text: Open a new `VectorLayer` with the options defined above, construct a `Point`
      geometry, and add it to the layer. `Point` represents a single coordinate (X,
      Y, optional Z) in a spatial reference system. It is the simplest geometry type
      and is used here to demonstrate precision rounding.
  - name: Read and Verify Precision
    text: Open the file you just created and print the coordinates. You should see
      the X/Y values rounded to three decimal places while the Z value remains exact.
      When you read the file back, Aspose.GIS parses the rounded values directly,
      so the in‑memory `Point` reflects the precision you defined during writ
  type: HowTo
- questions:
  - answer: Yes, it supports **50+** formats—including Shapefile, GeoJSON, KML, GML,
      and CSV—allowing seamless conversion between them.
    question: Is Aspose.GIS for .NET compatible with other GIS formats?
  - answer: Absolutely. A free trial is available from the download page, giving you
      full access to all features for evaluation.
    question: Can I try Aspose.GIS for .NET before purchasing?
  - answer: Temporary evaluation licenses can be generated via the Aspose license
      portal; they are valid for 30 days.
    question: How do I obtain a temporary license for testing?
  - answer: The Aspose.GIS forum and Stack Overflow tag `aspose-gis` are great places
      to ask questions and find community solutions.
    question: Where can I get help if I run into issues?
  - answer: Yes, Aspose.GIS is designed to handle everything from quick prototypes
      to high‑throughput server workloads, processing multi‑gigabyte datasets with
      low memory overhead.
    question: Does the library work for both small scripts and enterprise‑scale applications?
  type: FAQPage
second_title: Aspise.GIS .NET API
title: Cara Membatasi Presisi Penulisan Geometri dengan Aspose.GIS
url: /id/net/geometry-processing/limit-precision-writing-geometries/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membatasi Presisi Penulisan Geometri dengan Aspose.GIS

Jika Anda bertanya-tanya **bagaimana cara membatasi presisi** saat menulis geometri dalam aplikasi .NET GIS, Aspose.GIS untuk .NET menyediakan cara yang sederhana dan berperforma tinggi untuk mengontrol pembulatan koordinat. Dalam tutorial ini kami akan membahas seluruh proses—dari menyiapkan lingkungan hingga memverifikasi bahwa output mematuhi aturan presisi yang Anda tentukan.

## Jawaban Cepat
- **Apa arti “limit precision”?** Ia membulatkan nilai koordinat ke sejumlah digit pecahan yang ditentukan saat menulis file spasial.  
- **Format apa yang digunakan dalam contoh?** GeoJSON, tetapi opsi yang sama berlaku untuk format lain yang didukung.  
- **Apakah saya memerlukan lisensi untuk mencoba ini?** Versi percobaan gratis dapat digunakan untuk pengembangan dan pengujian; lisensi komersial diperlukan untuk produksi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Bisakah saya mengontrol presisi koordinat Z secara terpisah?** Ya—gunakan `ZPrecisionModel` untuk mengatur nilai tepat atau dibulatkan.

## Cara Membatasi Presisi Saat Menulis Geometri

Muat penulis GeoJSON Anda dengan objek `GeoJsonOptions` yang menentukan presisi X/Y dan Z yang diinginkan, kemudian tulis geometri dan bacalah kembali—seluruh alur kerja ini dapat diselesaikan dalam kurang dari sepuluh baris kode dan menjamin semua koordinat dibulatkan persis seperti yang Anda tentukan.

Membatasi presisi penting ketika Anda memerlukan representasi koordinat yang konsisten di berbagai alat GIS, mengurangi ukuran file, atau mematuhi standar pertukaran data. Di bawah ini kami akan mendefinisikan opsi presisi, menulis sebuah geometri, dan kemudian membacanya kembali untuk mengonfirmasi pembulatan.

## Apa Itu Pembatasan Presisi?

Pembatasan presisi adalah proses membulatkan bagian pecahan nilai koordinat ke sejumlah digit tetap sebelum menyimpan geometri ke dalam format file. Ini memastikan bahwa setiap konsumen file melihat nilai numerik yang sama, yang membantu menghindari ketidaksesuaian kecil yang dapat menyebabkan kesalahan topologi.

## Mengapa Menggunakan Aspose.GIS untuk Kontrol Presisi?

Aspose.GIS mendukung **50+** format input dan output—termasuk GeoJSON, Shapefile, KML, dan GML—dan dapat memproses file dengan **ratusan ribu fitur** tanpa memuat seluruh dataset ke memori. Model presisi bawaan memungkinkan Anda membulatkan koordinat dalam satu panggilan, menghilangkan kebutuhan akan skrip pemrosesan manual.

## Prasyarat

### 1. Unduh dan Instalasi
Unduh paket Aspose.GIS untuk .NET terbaru dari situs resmi: [download link](https://releases.aspose.com/gis/net/). Ikuti panduan instalasi untuk menambahkan paket NuGet ke proyek Anda.

### 2. Impor Namespace
Tambahkan namespace yang diperlukan sehingga Anda dapat mengakses kelas GIS dan utilitas pembantu.

## Panduan Langkah‑per‑Langkah

### Langkah 1: Definisikan Opsi Presisi
Kelas `GeoJsonOptions` memungkinkan Anda menentukan berapa banyak digit pecahan yang akan dipertahankan untuk koordinat X/Y dan Z.

`PrecisionModel` mendefinisikan bagaimana nilai koordinat dibulatkan atau dipertahankan tepat selama penulisan.  

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

### Langkah 2: Tentukan Jalur Output
Tentukan di mana file GeoJSON yang dihasilkan akan disimpan.

`VectorLayer` adalah kontainer Aspose.GIS untuk kumpulan fitur yang berbagi skema yang sama; ia menulis ke jalur yang Anda berikan menggunakan opsi yang telah ditetapkan sebelumnya.  

```csharp
var options = new GeoJsonOptions
{
    // Limit X and Y coordinates to 3 fractional digits.
    XYPrecisionModel = PrecisionModel.Rounding(3),

    // Write all fractional digits of the Z coordinate.
    ZPrecisionModel = PrecisionModel.Exact
};
```

### Langkah 3: Buat dan Isi Geometri
Buka `VectorLayer` baru dengan opsi yang telah didefinisikan di atas, buat geometri `Point`, dan tambahkan ke layer.

`Point` mewakili satu koordinat (X, Y, opsional Z) dalam sistem referensi spasial. Ini adalah tipe geometri paling sederhana dan digunakan di sini untuk mendemonstrasikan pembulatan presisi.  

```csharp
var path = "Your Document Directory" + "LimitPrecisionWhenWritingGeometries_out.json";
```

### Langkah 4: Baca dan Verifikasi Presisi
Buka file yang baru saja Anda buat dan cetak koordinatnya. Anda akan melihat nilai X/Y dibulatkan ke tiga tempat desimal sementara nilai Z tetap tepat.

Saat Anda membaca kembali file tersebut, Aspose.GIS mem-parsing nilai yang telah dibulatkan secara langsung, sehingga `Point` dalam memori mencerminkan presisi yang Anda definisikan saat penulisan.  

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

## Masalah Umum & Tips

- **Kesalahan Jalur:** Pastikan direktori dalam `path` ada atau gunakan `Path.Combine` dengan `Environment.CurrentDirectory` untuk membangun jalur file yang aman.  
- **Presisi Tidak Diterapkan:** Verifikasi bahwa Anda mengirimkan objek `GeoJsonOptions` saat membuat layer; jika tidak, presisi default (double penuh) akan digunakan.  
- **Dataset Besar:** Untuk operasi bulk, pertimbangkan untuk menggunakan kembali satu instance `VectorLayer` dan menambahkan fitur secara batch untuk meningkatkan kinerja.

## Pertanyaan yang Sering Diajukan

**Q: Apakah Aspose.GIS untuk .NET kompatibel dengan format GIS lain?**  
A: Ya, ia mendukung **50+** format—termasuk Shapefile, GeoJSON, KML, GML, dan CSV—memungkinkan konversi yang mulus di antara mereka.

**Q: Bisakah saya mencoba Aspose.GIS untuk .NET sebelum membeli?**  
A: Tentu saja. Versi percobaan gratis tersedia di halaman unduhan, memberi Anda akses penuh ke semua fitur untuk evaluasi.

**Q: Bagaimana cara mendapatkan lisensi sementara untuk pengujian?**  
A: Lisensi evaluasi sementara dapat dibuat melalui portal lisensi Aspose; lisensi tersebut berlaku selama 30 hari.

**Q: Di mana saya dapat mendapatkan bantuan jika mengalami masalah?**  
A: Forum Aspose.GIS dan tag Stack Overflow `aspose-gis` adalah tempat yang bagus untuk mengajukan pertanyaan dan menemukan solusi komunitas.

**Q: Apakah perpustakaan ini bekerja untuk skrip kecil maupun aplikasi skala perusahaan?**  
A: Ya, Aspose.GIS dirancang untuk menangani segala hal mulai dari prototipe cepat hingga beban kerja server dengan throughput tinggi, memproses dataset multi‑gigabyte dengan overhead memori yang rendah.

---

**Terakhir Diperbarui:** 2026-05-31  
**Diuji Dengan:** Aspose.GIS 24.11 for .NET  
**Penulis:** Aspose

## Tutorial Terkait

- [Buat Vector Layer, Batasi Presisi dengan Aspose.GIS untuk .NET](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [Cara Mengonversi GeoJSON – Aspose.GIS untuk .NET](/gis/net/geo-data-conversion/)
- [Cara Memeriksa Geometri dengan Aspose.GIS untuk .NET](/gis/net/geometry-analysis/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.GeoJson))
{
    var point = (IPoint)layer[0].Geometry;

    // Output: 1.889, 1.001, 1.123456789
    Console.WriteLine("{0}, {1}, {2}", point.X, point.Y, point.Z);
}
```

{{< /blocks/products/pf/main-wrap-class >}}