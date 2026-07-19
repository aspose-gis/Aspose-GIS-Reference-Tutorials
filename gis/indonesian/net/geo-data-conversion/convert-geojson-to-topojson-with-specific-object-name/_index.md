---
date: 2026-07-19
description: Pelajari cara mengonversi GeoJSON ke TopoJSON dengan nama objek tertentu
  menggunakan Aspose.GIS untuk .NET – panduan lengkap untuk konversi Aspose GIS.
keywords:
- convert geojson to topojson
- reduce geojson file size
- aspose gis conversion
- how to convert geojson
lastmod: 2026-07-19
linktitle: Cara Mengonversi GeoJSON ke TopoJSON dengan Nama Objek Khusus
og_description: konversi geojson ke topojson dengan nama objek khusus menggunakan
  Aspose.GIS untuk .NET. Kurangi ukuran file, kelola dataset besar, dan permudah persiapan
  peta web.
og_image_alt: 'Tutorial: Convert GeoJSON to TopoJSON with Aspose.GIS for .NET'
og_title: konversi geojson ke topojson – Panduan Detail dengan Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to convert GeoJSON to TopoJSON with a specific object name
    using Aspose.GIS for .NET – a complete guide for Aspose GIS conversion.
  headline: How to Convert GeoJSON to TopoJSON with Specific Object Name
  type: TechArticle
- description: Learn how to convert GeoJSON to TopoJSON with a specific object name
    using Aspose.GIS for .NET – a complete guide for Aspose GIS conversion.
  name: How to Convert GeoJSON to TopoJSON with Specific Object Name
  steps:
  - name: Define File Paths
    text: Replace `"Your Document Directory"` with the actual folder where your input
      GeoJSON lives and where you want the TopoJSON result saved.
  - name: Set Conversion Options (Aspose GIS conversion)
    text: The `ConversionOptions` class lets you fine‑tune the conversion process.
      **Definition anchor:** `ConversionOptions` is a configuration object that controls
      output format, precision, and object naming for Aspose.GIS conversions. Here
      we create a `ConversionOptions` instance and set `DefaultObjectName
  - name: Perform the Conversion (convert geojson to topojson)
    text: The `VectorLayer.Convert` method does the heavy lifting. **Definition anchor:**
      `VectorLayer.Convert` is a static method that reads a source vector file, applies
      the supplied `ConversionOptions`, and writes the target format. The method reads
      the source GeoJSON, applies the options defined above, an
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS for .NET can be used in both commercial and personal applications
      with a valid license.
    question: Can I use Aspose.GIS for .NET in commercial projects?
  - answer: Yes, you can get a free trial from [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.GIS for .NET?
  - answer: Support is available through the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).
    question: Where can I find support for Aspose.GIS for .NET?
  - answer: Licenses can be purchased from [here](https://purchase.aspose.com/buy).
    question: How do I purchase a license for Aspose.GIS for .NET?
  - answer: Yes, a temporary evaluation license is available from [here](https://purchase.aspose.com/temporary-license/).
    question: Do I need a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert geojson
- Aspose.GIS
- .NET data conversion
- TopoJSON
title: Cara Mengonversi GeoJSON ke TopoJSON dengan Nama Objek Khusus
url: /id/net/geo-data-conversion/convert-geojson-to-topojson-with-specific-object-name/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengonversi GeoJSON ke TopoJSON dengan Nama Objek Khusus

## Pendahuluan
Dalam tutorial ini Anda akan menemukan **cara mengonversi GeoJSON** menjadi TopoJSON sambil menetapkan nama objek khusus, menggunakan **Aspose.GIS untuk .NET**. Baik Anda sedang membangun layanan pemetaan, menyiapkan data untuk visualisasi web, atau hanya membutuhkan cara bersih untuk mengganti nama objek output, panduan langkah‑demi‑langkah ini menunjukkan secara tepat apa yang harus dilakukan. Konversi tidak hanya mengubah format tetapi juga **mengurangi ukuran file GeoJSON hingga 70 %** berkat enkoding tepi‑berbagi pada TopoJSON.

## Jawaban Cepat
- **Apa yang dilakukan konversi?** Itu mengubah koleksi fitur GeoJSON menjadi topologi TopoJSON dan memungkinkan Anda mengatur nama objek root.  
- **Perpustakaan mana yang menangani konversi?** Aspose.GIS untuk .NET (bagian dari suite konversi Aspose GIS).  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengujian; lisensi komersial diperlukan untuk produksi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Berapa lama implementasinya?** Sekitar 5‑10 menit setelah lingkungan siap.  

## Apa itu mengonversi geojson ke topojson?
Muat GeoJSON sumber Anda dan panggil API konversi Aspose.GIS – perpustakaan membaca fitur-fitur, membangun topologi tepi‑berbagi, dan menulis file TopoJSON dengan nama yang Anda tentukan. Operasi satu‑panggilan ini mempertahankan presisi geometri sambil secara dramatis memperkecil ukuran payload.

## Mengapa Menggunakan Aspose.GIS .NET untuk Konversi Ini?
Aspose.GIS memproses file hingga **2 GB** tanpa memuat seluruh dokumen ke memori, dan mendukung **lebih dari 50** format input dan output—termasuk Shapefile, KML, CSV, dan GeoPackage. API menyediakan opsi bawaan untuk presisi koordinat, penamaan objek, dan penyederhanaan topologi, menjadikannya pilihan paling dapat diandalkan untuk pipeline geospasial tingkat perusahaan.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal‑hal berikut:

### 1. Instal Aspose.GIS untuk .NET
Kunjungi [halaman unduhan](https://releases.aspose.com/gis/net/) dan dapatkan versi terbaru Aspose.GIS untuk .NET.

### 2. Siapkan Lingkungan Pengembangan Anda
Visual Studio, Rider, atau IDE kompatibel .NET apa pun akan berfungsi. Pastikan proyek Anda menargetkan .NET Framework 4.5+ atau .NET Core 3.1+.

### 3. Siapkan File GeoJSON
Miliki file GeoJSON yang siap untuk dikonversi. Jika belum, Anda dapat membuat yang sederhana atau menggunakan file GeoJSON contoh apa pun untuk tutorial ini.

## Impor Namespace
Sebelum memulai proses konversi, mari impor namespace yang diperlukan:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Cara Mengonversi GeoJSON ke TopoJSON
Mengonversi GeoJSON ke TopoJSON berarti mengambil koleksi fitur GeoJSON standar dan mengenkodenya sebagai topologi TopoJSON. TopoJSON mengurangi ukuran file dengan berbagi tepi geometri dan, dengan Aspose.GIS, memungkinkan Anda menentukan **DefaultObjectName** sehingga file output berisi objek bernama sesuai pilihan Anda.

## Panduan Langkah‑demi‑Langkah

### Langkah 1: Tentukan Jalur File
```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithObjectName_out.topojson";
```  
Ganti `"Your Document Directory"` dengan folder sebenarnya tempat GeoJSON input Anda berada dan tempat Anda ingin menyimpan hasil TopoJSON.

### Langkah 2: Atur Opsi Konversi (konversi Aspose GIS)
Kelas `ConversionOptions` memungkinkan Anda menyesuaikan proses konversi secara detail.  
**Definisi anchor:** `ConversionOptions` adalah objek konfigurasi yang mengontrol format output, presisi, dan penamaan objek untuk konversi Aspose.GIS.  
```csharp
var options = new ConversionOptions
{
    DestinationDriverOptions = new TopoJsonOptions
    {
        // specify the name of the object where features should be written
        DefaultObjectName = "name_of_the_object",
    }
};
```  
Di sini kami membuat instance `ConversionOptions` dan mengatur `DefaultObjectName`. Ini memberi tahu Aspose.GIS untuk menulis semua fitur di bawah objek bernama **name_of_the_object** dalam file TopoJSON yang dihasilkan.

### Langkah 3: Lakukan Konversi (konversi geojson ke topojson)
Metode `VectorLayer.Convert` melakukan pekerjaan berat.  
**Definisi anchor:** `VectorLayer.Convert` adalah metode statis yang membaca file vektor sumber, menerapkan `ConversionOptions` yang diberikan, dan menulis format target.  
```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```  
Metode ini membaca GeoJSON sumber, menerapkan opsi yang didefinisikan di atas, dan menulis file TopoJSON dengan nama objek khusus.

## Cara Menangani File GeoJSON Besar
Muat dataset besar secara efisien dengan streaming file sumber dan meningkatkan batas memori proses. Aspose.GIS dapat memproses file lebih besar dari 1 GB dengan membacanya dalam potongan, yang mencegah pengecualian out‑of‑memory pada konfigurasi server tipikal.

## Masalah Umum & Tips
- **Kesalahan Jalur** – Gunakan `Path.Combine` untuk membangun jalur file secara aman dan menghindari pemisah yang hilang.  
- **Manajemen Memori** – Untuk file GeoJSON yang sangat besar, tingkatkan batas memori proses atau streaming data alih-alih memuat semuanya sekaligus.  
- **Konflik Nama Objek** – Pastikan `DefaultObjectName` unik dalam file TopoJSON; nama duplikat dapat menyebabkan penimpaan.  

Praktik ini membantu Anda **menangani file GeoJSON besar** secara efisien sambil mengonversinya ke TopoJSON.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan Aspose.GIS untuk .NET dalam proyek komersial?**  
A: Ya, Aspose.GIS untuk .NET dapat digunakan dalam aplikasi komersial maupun pribadi dengan lisensi yang valid.

**Q: Apakah tersedia percobaan gratis untuk Aspose.GIS untuk .NET?**  
A: Ya, Anda dapat memperoleh percobaan gratis dari [di sini](https://releases.aspose.com/).

**Q: Di mana saya dapat menemukan dukungan untuk Aspose.GIS untuk .NET?**  
A: Dukungan tersedia melalui [forum Aspose.GIS](https://forum.aspose.com/c/gis/33).

**Q: Bagaimana cara membeli lisensi untuk Aspose.GIS untuk .NET?**  
A: Lisensi dapat dibeli dari [di sini](https://purchase.aspose.com/buy).

**Q: Apakah saya memerlukan lisensi sementara untuk evaluasi?**  
A: Ya, lisensi evaluasi sementara tersedia dari [di sini](https://purchase.aspose.com/temporary-license/).

**Q: Bisakah saya mengonversi dataset GeoJSON yang sangat besar tanpa kehabisan memori?**  
A: Ya—dengan streaming sumber atau meningkatkan alokasi memori aplikasi, Anda dapat menangani file besar secara efisien.

---

**Terakhir Diperbarui:** 2026-07-19  
**Diuji Dengan:** Aspose.GIS untuk .NET (rilis terbaru)  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Cara Mengonversi GeoJSON ke TopoJSON dengan Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Cara Mengonversi GeoJSON ke TopoJSON dengan Pengelompokan menggunakan Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson-with-grouping/)
- [Mengonversi TopoJSON ke GeoJSON](/gis/net/geo-data-conversion/convert-topojson-to-geojson/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}