---
date: 2026-07-05
description: Pelajari cara mengonversi shapefile ke geojson menggunakan Aspose.GIS
  untuk .NET. Panduan ini juga mencakup menyalin atribut antar lapisan dan menghasilkan
  file geojson dengan c#.
keywords:
- convert shapefile to geojson
- export shapefile as geojson
- aspose gis conversion
- read shapefile c#
- write geojson c#
linktitle: Ekstrak Fitur ke GeoJSON
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  headline: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  name: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  steps:
  - name: Open Input Shapefile
    text: The `VectorLayer.Open` method reads a Shapefile and returns an enumerable
      collection of `Feature` objects that you can iterate over.
  - name: Create Output GeoJSON
    text: '`VectorLayer.Create` with the `Drivers.GeoJson` driver creates an empty
      GeoJSON file ready to receive features.'
  - name: Copy Attributes Between Layers
    text: '`CopyAttributes` copies the attribute schema (field names and data types)
      from the source Shapefile to the new GeoJSON layer in a single call.'
  - name: Process Features
    text: Iterate through each feature in the Shapefile so you can apply any custom
      logic before writing it out.
  - name: Filter Features by Date
    text: In this example we skip records whose `dob` (date of birth) field is missing
      or earlier than 1 Jan 1982. Adjust the filter to match your own data requirements.
  - name: Construct a New Feature (C# Generate GeoJSON File)
    text: A `Feature` represents a single spatial element containing geometry and
      attribute data. Here we build a new `Feature` for the GeoJSON layer, copy the
      geometry and attribute values, and add it to the output. This is the core of
      *c# generate geojson file*. Congratulations! You’ve successfully **conver
  type: HowTo
- questions:
  - answer: Visit the [Aspose.GIS documentation](https://reference.aspose.com/gis/net/)
      for in‑depth information.
    question: Where can I find more documentation?
  - answer: You can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I get a temporary license?
  - answer: Join the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I seek support?
  - answer: Yes, you can find the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: You can buy the product [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Konversi Shapefile ke GeoJSON dengan Aspose.GIS untuk .NET
url: /id/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mengonversi Shapefile ke GeoJSON dengan Aspose.GIS untuk .NET

## Pendahuluan
Dalam tutorial komprehensif langkah‑demi‑langkah ini Anda akan belajar **cara mengonversi shapefile ke geojson** menggunakan pustaka Aspose.GIS yang kuat untuk .NET. Baik Anda membangun layanan web pemetaan, menyiapkan data untuk aplikasi GIS seluler, atau sekadar perlu menukar data antar format, panduan ini menunjukkan secara tepat apa yang harus dilakukan, mengapa setiap langkah penting, dan bagaimana menghindari jebakan umum.

## Jawaban Cepat
- **Apa yang dibahas tutorial ini?** Mengonversi Shapefile ke file GeoJSON, menyalin atribut antara layer, dan menghasilkan output dengan C#.
- **Perpustakaan apa yang diperlukan?** Aspose.GIS untuk .NET.
- **Apakah saya memerlukan lisensi?** Lisensi sementara atau penuh diperlukan untuk produksi; percobaan gratis dapat digunakan untuk evaluasi.
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk konversi dasar.
- **Apakah saya dapat menjalankannya di .NET Core/.NET 6?** Ya – kode berfungsi pada semua versi .NET yang didukung.

## Apa itu mengonversi shapefile ke geojson?
Mengonversi Shapefile ke GeoJSON berarti membaca fitur vektor dari format Shapefile klasik ESRI dan menuliskannya sebagai dokumen GeoJSON modern yang ramah web. Transformasi ini memungkinkan Anda memasukkan data GIS langsung ke perpustakaan pemetaan JavaScript seperti Leaflet atau Mapbox GL, serta menyederhanakan pertukaran data antara alat GIS desktop dan API web.

## Mengapa menggunakan Aspose.GIS untuk konversi ini?
Aspose.GIS mengabstraksi parsing biner tingkat rendah, mendukung lebih dari 50 format input dan output, serta dapat memproses dataset ratusan halaman tanpa memuat seluruh file ke memori. Perpustakaan ini juga menyediakan API berorientasi objek yang bersih yang bekerja di .NET Framework, .NET Core, dan .NET 5/6, sehingga Anda dapat fokus pada logika bisnis bukan keanehan format.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal‑hal berikut:

- Aspose.GIS untuk .NET: Pastikan Anda telah menginstal perpustakaan tersebut. Jika belum, Anda dapat mengunduhnya dari [halaman Aspose.GIS untuk .NET](https://releases.aspose.com/gis/net/).
- Data Shapefile: Siapkan Shapefile untuk input. Jika Anda memerlukan data contoh, Anda dapat menemukannya di [dokumentasi Aspose.GIS](https://reference.aspose.com/gis/net/).
- Lingkungan .NET: Siapkan lingkungan .NET untuk menjalankan kode yang disediakan.
- Direktori Dokumen: Tentukan jalur ke direktori dokumen Anda dalam potongan kode.

Setelah semua siap, mari mulai mengonversi shapefile ke geojson!

## Cara Mengonversi Shapefile ke GeoJSON
Muat Shapefile sumber, buat layer GeoJSON target, salin skema atribut, filter catatan, dan tulis hasilnya—semua dalam beberapa langkah singkat. Alur kerja lengkap muat dengan nyaman dalam satu blok `using`, memastikan sumber daya dilepaskan secara otomatis.

### Langkah 1: Buka Shapefile Input
Metode `VectorLayer.Open` membaca Shapefile dan mengembalikan koleksi enumerable dari objek `Feature` yang dapat Anda iterasi.

```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```

### Langkah 2: Buat GeoJSON Output
`VectorLayer.Create` dengan driver `Drivers.GeoJson` membuat file GeoJSON kosong yang siap menerima fitur.

```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```

### Langkah 3: Salin Atribut Antara Layer
`CopyAttributes` menyalin skema atribut (nama bidang dan tipe data) dari Shapefile sumber ke layer GeoJSON baru dalam satu panggilan.

```csharp
outputLayer.CopyAttributes(inputLayer);
```

### Langkah 4: Proses Fitur
Iterasi setiap fitur dalam Shapefile sehingga Anda dapat menerapkan logika khusus sebelum menuliskannya.

```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```

### Langkah 5: Filter Fitur Berdasarkan Tanggal
Dalam contoh ini kami melewatkan catatan yang bidang `dob` (tanggal lahir)nya hilang atau lebih awal dari 1 Jan 1982. Sesuaikan filter sesuai kebutuhan data Anda.

```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```

### Langkah 6: Buat Fitur Baru (C# Generate GeoJSON File)
Sebuah `Feature` mewakili elemen spasial tunggal yang berisi geometri dan data atribut.  
Di sini kami membuat `Feature` baru untuk layer GeoJSON, menyalin geometri dan nilai atribut, dan menambahkannya ke output. Ini adalah inti dari *c# generate geojson file*.

```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```

Selamat! Anda telah berhasil **mengonversi shapefile ke geojson** dan mempelajari cara **menyalin atribut antara layer** sepanjang proses.

## Masalah Umum dan Solusinya
| Masalah | Mengapa Terjadi | Solusi |
|-------|----------------|-----|
| File output kosong | `CopyAttributes` dipanggil setelah layer output ditutup | Pastikan blok `using` untuk `outputLayer` tetap terbuka sampai semua fitur ditambahkan. |
| Filter tanggal menghapus semua catatan | Nama bidang salah atau format tanggal tidak terduga | Verifikasi nama atribut (`dob`) dan gunakan `GetValue<string>` jika tanggal disimpan sebagai string. |
| Pengecualian lisensi | Menjalankan tanpa lisensi Aspose.GIS yang valid di produksi | Terapkan lisensi sementara atau penuh seperti yang dijelaskan dalam dokumentasi Aspose. |

## Pertanyaan yang Sering Diajukan
**Q: Di mana saya dapat menemukan dokumentasi lebih lanjut?**  
A: Kunjungi [dokumentasi Aspose.GIS](https://reference.aspose.com/gis/net/) untuk informasi mendalam.

**Q: Bagaimana saya dapat memperoleh lisensi sementara?**  
A: Anda dapat memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

**Q: Di mana saya dapat mencari dukungan?**  
A: Bergabunglah dengan [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) untuk dukungan komunitas dan diskusi.

**Q: Apakah tersedia percobaan gratis?**  
A: Ya, Anda dapat menemukan percobaan gratis [di sini](https://releases.aspose.com/).

**Q: Di mana saya dapat membeli Aspose.GIS untuk .NET?**  
A: Anda dapat membeli produk [di sini](https://purchase.aspose.com/buy).

## Kesimpulan
Dalam tutorial ini kami menjelajahi proses lengkap **mengonversi shapefile ke geojson** menggunakan Aspose.GIS untuk .NET, menunjukkan cara **menyalin atribut antara layer**, dan memperlihatkan cara bersih untuk *c# generate geojson file*. Bereksperimenlah dengan filter yang berbeda, dataset yang lebih besar, atau transformasi geometri tambahan untuk memanfaatkan sepenuhnya kemampuan perpustakaan.

---

**Terakhir Diperbarui:** 2026-07-05  
**Diuji Dengan:** Aspose.GIS untuk .NET (rilis stabil terbaru)  
**Penulis:** Aspose

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Tutorial Terkait

- [How to Convert GeoJSON to File GDB Using Aspose.GIS for .NET](/gis/net/layer-management/convert-geojson-layer-to-file-gdb/)
- [How to Read GeoJSON from Stream with Aspose.GIS for .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [How to Convert GeoJSON to TopoJSON with Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}