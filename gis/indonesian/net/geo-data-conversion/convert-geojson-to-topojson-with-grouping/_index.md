---
date: 2026-08-03
description: Pelajari cara mengonversi geojson ke topojson dengan pengelompokan, mengatur
  atribut nama objek, dan mengelompokkan fitur GeoJSON menggunakan Aspose.GIS untuk
  .NET.
keywords:
- convert geojson to topojson
- group features by attribute
- asp.net core geojson
- set object name attribute
- asp.net geojson conversion
lastmod: 2026-08-03
linktitle: Cara Mengonversi GeoJSON ke TopoJSON dengan Pengelompokan menggunakan Aspose.GIS
og_description: Pelajari cara mengonversi geojson ke topojson dengan pengelompokan,
  mengatur atribut nama objek, dan mengelompokkan fitur GeoJSON secara efisien menggunakan
  Aspose.GIS untuk .NET.
og_image_alt: Screenshot of Aspose.GIS conversion code showing GeoJSON to TopoJSON
  with grouping
og_title: Konversi geojson ke topojson dengan pengelompokan menggunakan Aspose.GIS
  untuk .NET
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to convert geojson to topojson with grouping, set object
    name attribute, and group GeoJSON features using Aspose.GIS for .NET.
  headline: How to convert geojson to topojson with grouping using Aspose.GIS
  type: TechArticle
- description: Learn how to convert geojson to topojson with grouping, set object
    name attribute, and group GeoJSON features using Aspose.GIS for .NET.
  name: How to convert geojson to topojson with grouping using Aspose.GIS
  steps:
  - name: Define file paths
    text: 'Specify where the source GeoJSON lives and where the TopoJSON should be
      written: > **Pro tip:** Use `Path.Combine` for cross‑platform path building
      if you target .NET Core.'
  - name: Configure conversion options (set object name attribute)
    text: '`ConversionOptions` is the configuration object that controls how Aspose.GIS
      performs the conversion. It lets you set the grouping attribute, define a default
      object name, and tweak topology precision. The `ObjectNameAttribute` property
      (string) defines the GeoJSON field used for grouping, while `De'
  - name: Perform the conversion (convert GeoJSON to TopoJSON)
    text: '`Conversion.Convert` is a single‑line API call that reads the source file,
      applies the options, and writes the TopoJSON output. It internally builds a
      topology graph, deduplicates shared edges, and writes the result in the compact
      TopoJSON format. After execution, `convertedSampleWithGrouping_out.to'
  type: HowTo
- questions:
  - answer: Yes, you can concatenate several fields into a single virtual attribute
      or run multiple conversion passes with different `ObjectNameAttribute` values.
    question: Can I group features based on multiple attributes?
  - answer: Absolutely – the library works with ASP.NET Core, .NET 5, .NET 6, and
      the classic .NET Framework.
    question: Is Aspose.GIS compatible with ASP.NET Core?
  - answer: Yes, Aspose.GIS supports more than 30 input and output formats—including
      Shapefile, KML, GML, CSV, and DXF—for both import and export.
    question: Can I convert other geographic formats besides GeoJSON?
  - answer: Yes, you can get a free trial of Aspose.GIS from the [Aspose.GIS free
      trial page](https://releases.aspose.com/).
    question: Does Aspose.GIS offer a free trial?
  - answer: You can get support from the Aspose.GIS community forum [Aspose.GIS community
      forum](https://forum.aspose.com/c/gis/33).
    question: Where can I get support for Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert geojson
- Aspose.GIS
- C# GIS processing
- geojson conversion
- topojson grouping
title: Cara mengonversi geojson ke topojson dengan pengelompokan menggunakan Aspose.GIS
url: /id/net/geo-data-conversion/convert-geojson-to-topojson-with-grouping/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Bagaimana cara mengonversi geojson ke topojson dengan pengelompokan menggunakan Aspose.GIS

## Pendahuluan

Pada tutorial langkah‑demi‑langkah ini Anda akan belajar **cara mengonversi geojson ke topojson** sambil mengelompokkan fitur berdasarkan atribut yang dipilih. Menggunakan Aspose.GIS .NET API membuat konversi menjadi cepat (memproses hingga 2 000 fitur per detik) dan sepenuhnya dapat dikendalikan dari kode C# Anda. Baik Anda membangun layanan konversi geojson ASP.NET Core, alat GIS desktop, atau pipeline data otomatis, panduan ini menunjukkan secara tepat apa yang perlu Anda lakukan untuk **mengonversi geojson ke topojson** secara efisien dan dapat diandalkan.

## Jawaban Cepat
- **Perpustakaan apa yang menangani konversi?** Aspose.GIS for .NET  
- **Berapa lama implementasinya?** Biasanya 5‑10 menit untuk pengaturan dasar  
- **Apakah saya memerlukan lisensi untuk produksi?** Ya, lisensi komersial diperlukan (tersedia percobaan gratis)  
- **Bisakah saya mengelompokkan fitur berdasarkan atribut apa pun?** Ya – atur `ObjectNameAttribute` ke bidang yang ingin Anda kelompokkan  
- **Apakah .NET Core didukung?** Tentu – API bekerja dengan .NET Core, .NET 5/6, dan .NET Framework klasik  

## Cara mengonversi geojson ke topojson dengan pengelompokan di C#

Muat GeoJSON sumber Anda, konfigurasikan `ConversionOptions` dengan `ObjectNameAttribute` yang diinginkan, dan panggil `Conversion.Convert` – panggilan tunggal itu menghasilkan file TopoJSON yang sepenuhnya dikelompokkan dalam kurang dari satu detik untuk dataset skala kota yang tipikal.

Anda dapat menyematkan pola ini dalam aplikasi konsol, layanan latar belakang, atau endpoint konversi geojson ASP.NET Core. API mengabstraksi semua perhitungan topologi tingkat rendah, sehingga Anda dapat fokus pada logika bisnis alih‑alih matematika geometri.

## Apa itu GeoJSON dan TopoJSON?

GeoJSON adalah format JSON ringan yang mewakili fitur geografis seperti titik, garis, dan poligon. TopoJSON memperluas GeoJSON dengan menyimpan segmen garis yang dibagi (topologi), yang mengurangi ukuran file hingga 80 % untuk peta kompleks dan meningkatkan kecepatan rendering dalam visualisasi web.

## Mengapa mengelompokkan fitur GeoJSON?

Mengelompokkan fitur GeoJSON memungkinkan Anda menggabungkan geometri terkait di bawah satu objek bernama dalam output TopoJSON, yang menyederhanakan styling dan interaksi di tahap selanjutnya. Ini berguna ketika Anda memerlukan lapisan terpisah untuk wilayah administratif, ketika perpustakaan pemetaan mengharapkan objek bernama untuk penanganan klik, atau ketika Anda ingin menghilangkan data batas duplikat antara fitur yang bersebelahan.

## Atur atribut nama objek untuk pengelompokan

`ObjectNameAttribute` memberi tahu Aspose.GIS properti mana dalam GeoJSON sumber yang harus digunakan sebagai nama objek dalam output TopoJSON. Menetapkan atribut ini dengan benar adalah kunci untuk berhasil **mengelompokkan fitur geojson**.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:

1. **Aspose.GIS untuk .NET** – unduh dan instal dari [halaman rilis Aspose.GIS untuk .NET](https://releases.aspose.com/gis/net/).  
2. **Lingkungan pengembangan** – Visual Studio, Visual Studio Code, atau IDE apa pun yang mendukung C#.  
3. **File GeoJSON contoh** – file yang berisi fitur yang ingin Anda konversi.  

## Impor namespace

Pertama, sertakan namespace yang diperlukan dalam proyek Anda:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
```

## Panduan langkah‑demi‑langkah

### Langkah 1: Tentukan jalur file

Tentukan di mana GeoJSON sumber berada dan di mana TopoJSON harus ditulis:

```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithGrouping_out.topojson";
```

> **Tip profesional:** Gunakan `Path.Combine` untuk membangun jalur lintas‑platform jika Anda menargetkan .NET Core.

### Langkah 2: Konfigurasikan opsi konversi (atur atribut nama objek)

`ConversionOptions` adalah objek konfigurasi yang mengontrol bagaimana Aspose.GIS melakukan konversi. Ini memungkinkan Anda mengatur atribut pengelompokan, mendefinisikan nama objek default, dan menyesuaikan presisi topologi.

Properti `ObjectNameAttribute` (string) menentukan bidang GeoJSON yang digunakan untuk pengelompokan, sementara `DefaultObjectName` (string) menyediakan nama cadangan untuk fitur yang tidak memiliki atribut tersebut.

```csharp
var options = new ConversionOptions
{
    DestinationDriverOptions = new TopoJsonOptions
    {
        // Specify the attribute in GeoJSON layer by which we are going to group into objects
        ObjectNameAttribute = "group",
        // Specify the default object name for features with unknown attribute values
        DefaultObjectName = "unnamed",
    }
};
```

Ganti `"group"` dengan nama properti sebenarnya dalam GeoJSON Anda yang ingin Anda gunakan untuk **pengelompokan fitur geojson**. `DefaultObjectName` memastikan setiap fitur masuk ke dalam objek TopoJSON, bahkan jika atributnya tidak ada.

### Langkah 3: Lakukan konversi (konversi GeoJSON ke TopoJSON)

`Conversion.Convert` adalah panggilan API satu baris yang membaca file sumber, menerapkan opsi, dan menulis output TopoJSON. Secara internal ia membangun grafik topologi, menghilangkan duplikasi tepi yang dibagi, dan menulis hasil dalam format TopoJSON yang kompak.

```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```

Setelah eksekusi, `convertedSampleWithGrouping_out.topojson` akan berisi representasi TopoJSON, dengan fitur-fitur yang dikelompokkan sesuai atribut yang Anda tentukan.

## Masalah umum dan pemecahan masalah

| Gejala | Penyebab kemungkinan | Perbaikan |
|---------|--------------|-----|
| **Semua fitur berakhir di “unnamed”** | `ObjectNameAttribute` tidak cocok dengan properti apa pun di GeoJSON | Verifikasi nama properti yang tepat (case‑sensitive) dan perbarui opsi |
| **File output kosong** | Jalur file tidak tepat atau izin baca yang hilang | Gunakan jalur absolut atau pastikan aplikasi memiliki akses sistem file |
| **Konversi melempar `NotSupportedException`** | Mencoba mengonversi GeoJSON dengan tipe geometri yang tidak didukung (mis., GeometryCollection) | Sederhanakan data sumber atau tingkatkan ke versi Aspose.GIS terbaru |

## Praktik terbaik konversi GeoJSON C#

- **Validasi GeoJSON sumber** sebelum konversi untuk menangkap atribut yang hilang lebih awal.  
- **Gunakan `Path.Combine`** untuk jalur file guna menghindari masalah pemisah khusus platform.  
- **Bungkus panggilan konversi dalam blok try‑catch** untuk menangani kesalahan I/O secara elegan.  
- **Catat kejadian `DefaultObjectName`**; ini dapat menunjukkan masalah kualitas data yang mungkin ingin Anda perbaiki di hulu.  

## Pertanyaan yang sering diajukan

**T: Bisakah saya mengelompokkan fitur berdasarkan beberapa atribut?**  
J: Ya, Anda dapat menggabungkan beberapa bidang menjadi satu atribut virtual atau menjalankan beberapa proses konversi dengan nilai `ObjectNameAttribute` yang berbeda.

**T: Apakah Aspose.GIS kompatibel dengan ASP.NET Core?**  
J: Tentu – perpustakaan ini bekerja dengan ASP.NET Core, .NET 5, .NET 6, dan .NET Framework klasik.

**T: Bisakah saya mengonversi format geografis lain selain GeoJSON?**  
J: Ya, Aspose.GIS mendukung lebih dari 30 format input dan output—termasuk Shapefile, KML, GML, CSV, dan DXF—untuk impor maupun ekspor.

**T: Apakah Aspose.GIS menawarkan percobaan gratis?**  
J: Ya, Anda dapat memperoleh percobaan gratis Aspose.GIS dari [halaman percobaan gratis Aspose.GIS](https://releases.aspose.com/).

**T: Di mana saya dapat mendapatkan dukungan untuk Aspose.GIS?**  
J: Anda dapat mendapatkan dukungan dari forum komunitas Aspose.GIS [forum komunitas Aspose.GIS](https://forum.aspose.com/c/gis/33).

## Kesimpulan

Anda kini memiliki resep lengkap yang siap produksi untuk **mengonversi geojson ke topojson** dengan pengelompokan fitur menggunakan Aspose.GIS untuk .NET. Dengan mengatur `ObjectNameAttribute`, Anda mengontrol cara fitur diorganisir, yang menyederhanakan styling dan interaksi di tahap selanjutnya pada peta web. Jangan ragu untuk menjelajahi driver lain, bereksperimen dengan atribut pengelompokan yang berbeda, dan mengintegrasikan konversi ini ke dalam pipeline GIS yang lebih besar.

---

**Terakhir Diperbarui:** 2026-08-03  
**Diuji dengan:** Aspose.GIS untuk .NET (rilis terbaru)  
**Penulis:** Aspose  

---

## Tutorial Terkait

- [Cara Mengonversi GeoJSON ke TopoJSON dengan Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Cara Mengonversi GeoJSON ke TopoJSON dengan Nama Objek Spesifik](/gis/net/geo-data-conversion/convert-geojson-to-topojson-with-specific-object-name/)
- [Membuka Fitur TopoJSON dengan Aspose.GIS untuk .NET](/gis/net/layer-management/access-features-in-topojson/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}