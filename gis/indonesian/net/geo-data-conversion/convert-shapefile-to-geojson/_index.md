---
date: 2026-07-24
description: Pelajari cara mengonversi Shapefile ke GeoJSON dengan mudah di .NET menggunakan
  Aspose.GIS dan mencapai interoperabilitas data geospasial yang mulus saat membaca
  Shapefile dengan C#.
keywords:
- convert shapefile to geojson
- read shapefile c#
- c# shapefile to geojson
- export geojson c#
- convert shapefile to json
lastmod: 2026-07-24
linktitle: Konversi Shapefile ke GeoJSON
og_description: Konversi shapefile ke geojson dengan cepat menggunakan Aspose.GIS
  untuk .NET. Pelajari kode C# langkah demi langkah, prasyarat, dan pemecahan masalah
  dalam waktu kurang dari 10 menit.
og_image_alt: 'Developer guide: Convert Shapefile to GeoJSON in C# with Aspose.GIS'
og_title: Konversi Shapefile ke GeoJSON – Panduan Cepat C# (50‑60 karakter)
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Learn how to effortlessly convert Shapefile to GeoJSON in .NET using
    Aspose.GIS and achieve seamless geospatial data interoperability while reading
    Shapefile in C#.
  headline: Convert Shapefile to GeoJSON
  type: TechArticle
- questions:
  - answer: Yes. Place the conversion code inside a `foreach` loop that iterates over
      each `.shp` file in a directory, calling `VectorLayer.Convert` for every file.
    question: Can I convert multiple Shapefiles to GeoJSON in one go using Aspose.GIS
      for .NET?
  - answer: It supports .NET Framework 4.5 and higher, as well as .NET Core 3.1+ and
      .NET 5/6/7.
    question: Is Aspose.GIS for .NET compatible with all versions of .NET Framework?
  - answer: Absolutely. The library handles formats such as GeoTIFF, KML, GML, CSV,
      and many more—over 60 in total.
    question: Does Aspose.GIS for .NET provide support for other geospatial formats
      apart from Shapefile and GeoJSON?
  - answer: Yes. The API offers overloads and properties to set target coordinate
      systems, filter attributes, and modify feature geometry during conversion.
    question: Can I customize the conversion process, such as specifying a coordinate
      system or attribute mappings?
  - answer: Yes, you can download a free trial from the [Aspose website](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert shapefile
- Aspose.GIS
- C# geospatial processing
- geojson export
title: Konversi Shapefile ke GeoJSON
url: /id/net/geo-data-conversion/convert-shapefile-to-geojson/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mengonversi Shapefile ke GeoJSON

## Pendahuluan
Dalam Sistem Informasi Geografis (GIS) modern, **interoperabilitas data geospasial** adalah kunci untuk membuka analisis spasial yang kuat. Salah satu tugas konversi yang paling umum adalah **mengonversi shapefile ke geojson**, memungkinkan pertukaran data ringan dengan peta web, aplikasi seluler, dan layanan cloud. Dalam tutorial ini Anda akan melihat cara **membaca shapefile dalam C#** dan mengekspornya sebagai GeoJSON menggunakan perpustakaan Aspose.GIS .NET, sehingga Anda dapat mengintegrasikan konversi langsung ke dalam aplikasi Anda.

## Jawaban Cepat
- **Perpustakaan apa yang menangani konversi?** Aspose.GIS for .NET  
- **Berapa lama implementasinya?** Typically under 10 minutes for a single file  
- **Apakah saya memerlukan lisensi?** A free trial works for development; a license is required for production  
- **Versi .NET yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **Bisakah saya mengonversi beberapa file?** Yes – just loop over the `VectorLayer.Convert` call  

## Apa itu “convert shapefile to geojson”?
Mengonversi Shapefile (tiga berkas `.shp`, `.shx`, `.dbf`) menjadi GeoJSON mengubah data menjadi format tunggal berbasis JSON yang mudah dibaca, diedit, dan dirender di peramban. GeoJSON khususnya cocok untuk perpustakaan pemetaan JavaScript seperti Leaflet atau Mapbox.

## Mengapa menggunakan Aspose.GIS untuk .NET untuk konversi format data GIS?
Aspose.GIS menyediakan solusi komprehensif yang sepenuhnya dikelola, mendukung lebih dari 60 format vektor dan raster, menghilangkan ketergantungan eksternal, dan memberikan konversi berkecepatan tinggi bahkan untuk dataset besar, menjadikannya ideal untuk lingkungan perusahaan dan cloud di mana keandalan serta kinerja sangat penting saat ini.

- **API all‑in‑one** – Mendukung **60+** format vektor dan raster geospasial, termasuk KML, GML, CSV, GeoTIFF, dan lainnya.  
- **Konversi tanpa ketergantungan** – Tidak memerlukan GDAL, Proj4, atau binary native; semuanya berjalan pada kode yang sepenuhnya dikelola.  
- **Kinerja tinggi** – Memproses berkas hingga **500 MB** dalam waktu kurang dari **5 detik** pada VM server tipikal, dan dapat menangani pekerjaan batch tanpa penggunaan memori berlebih.  
- **Kustomisasi kaya** – Anda dapat menentukan sistem koordinat target, menyaring atribut, dan mengubah geometri secara langsung.  

## Prasyarat
Sebelum memulai, pastikan Anda memiliki hal berikut:

1. **Aspose.GIS for .NET installed** – Ikuti petunjuk pada [Aspose.GIS for .NET documentation](https://reference.aspose.com/gis/net/) resmi untuk menambahkan paket NuGet ke proyek Anda.  
2. **A source Shapefile** – Dapatkan satu dari portal data terbuka, lembaga pemerintah, atau buat dengan QGIS/ArcGIS.  
3. **Basic C# knowledge** – Potongan kode menggunakan sintaks C# dan konvensi .NET.  

## Impor Namespace
Namespace `Aspose.GIS` menyediakan kelas yang diperlukan untuk membaca dan menulis data vektor.

Namespace `Aspose.GIS.Geometries` berisi tipe geometri, sementara `Aspose.GIS.VectorLayers` menyimpan kelas `VectorLayer` yang melakukan konversi format. Namespace `Aspose.GIS.VectorLayers` berisi kelas `VectorLayer` yang digunakan untuk konversi format.

## Cara mengonversi shapefile ke GeoJSON dalam C#?
`Metode `VectorLayer.Open` memuat dataset vektor dari sebuah berkas ke dalam objek `VectorLayer`.  
`VectorLayer.Convert` adalah metode statis yang mengubah berkas vektor sumber langsung ke format target seperti GeoJSON.

Muat Shapefile sumber dengan `VectorLayer.Open`, kemudian panggil metode statis `VectorLayer.Convert` untuk menulis berkas GeoJSON dalam satu baris. Pendekatan ini membaca sumber, secara opsional memproyeksikannya kembali, dan menyalurkan hasil langsung ke disk, menghilangkan kebutuhan akan objek perantara.

### Langkah 1: Tentukan Jalur Input dan Output
Tetapkan folder yang berisi Shapefile Anda dan tujuan untuk berkas GeoJSON. Sesuaikan jalur agar cocok dengan lingkungan Anda.

Gunakan `Path.Combine(dataDir, "InputShapeFile.shp")` untuk membangun jalur yang independen platform, dan `Path.Combine(outputDir, "output.geojson")` untuk berkas hasil.

> **Pro tip:** Simpan tiga komponen Shapefile (`.shp`, `.shx`, `.dbf`) dalam folder yang sama; `VectorLayer.Open` secara otomatis menemukan berkas terkait.

### Langkah 2: Lakukan Konversi
Panggil `VectorLayer.Convert(inputPath, outputPath, OutputFormat.GeoJSON)`. Satu baris ini membaca Shapefile, menerjemahkannya, dan menulis FeatureCollection GeoJSON yang valid.

Setelah dijalankan, `output.geojson` akan berisi dokumen GeoJSON yang sepenuhnya sesuai yang dapat Anda muat ke dalam penampil peta web apa pun, server GIS, atau pipeline analitik.

## Mengapa ini penting
Mengonversi shapefile ke GeoJSON memungkinkan integrasi mulus dengan perpustakaan pemetaan web modern, mengurangi ukuran berkas, dan menyederhanakan pertukaran data antar platform, memungkinkan pengembang membangun aplikasi GIS yang responsif tanpa harus berurusan dengan kompleksitas format warisan serta meningkatkan efisiensi alur kerja secara keseluruhan bagi tim yang menangani data spasial.

- **Interoperabilitas:** Mengonversi ke GeoJSON memungkinkan Anda berbagi data dengan berbagai alat GIS berbasis web tanpa khawatir tentang format proprietari.  
- **Kinerja:** Aspose.GIS memproses konversi di memori, yang lebih cepat daripada memanggil utilitas baris perintah eksternal.  
- **Skalabilitas:** Pendekatan yang sama dapat dibungkus dalam loop atau layanan latar belakang untuk menangani konversi massal bagi pipeline data.  

## Masalah Umum & Solusi
| Masalah | Mengapa Terjadi | Solusi |
|-------|----------------|-----|
| **Berkas tidak ditemukan** | `dataDir` salah atau berkas `.shp` hilang | Verifikasi jalur dan pastikan semua tiga komponen Shapefile (`.shp`, `.shx`, `.dbf`) ada. |
| **Ketidaksesuaian sistem koordinat** | Shapefile sumber menggunakan proyeksi yang tidak dikenali oleh konsumen | Gunakan `VectorLayer.Open(...).CoordinateSystem` untuk memproyeksikan ulang sebelum konversi. |
| **Berkas besar menyebabkan tekanan memori** | Seluruh dataset dimuat ke memori | Proses fitur dalam potongan atau gunakan `VectorLayer.Stream` untuk konversi streaming. |

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya mengonversi beberapa Shapefile ke GeoJSON sekaligus menggunakan Aspose.GIS untuk .NET?**  
A: Ya. Tempatkan kode konversi di dalam loop `foreach` yang mengiterasi setiap berkas `.shp` dalam sebuah direktori, memanggil `VectorLayer.Convert` untuk setiap berkas.

**Q: Apakah Aspose.GIS untuk .NET kompatibel dengan semua versi .NET Framework?**  
A: Ia mendukung .NET Framework 4.5 ke atas, serta .NET Core 3.1+ dan .NET 5/6/7.

**Q: Apakah Aspose.GIS untuk .NET menyediakan dukungan untuk format geospasial lain selain Shapefile dan GeoJSON?**  
A: Tentu saja. Perpustakaan ini menangani format seperti GeoTIFF, KML, GML, CSV, dan banyak lagi—lebih dari 60 secara total.

**Q: Bisakah saya menyesuaikan proses konversi, seperti menentukan sistem koordinat atau pemetaan atribut?**  
A: Ya. API menyediakan overload dan properti untuk mengatur sistem koordinat target, menyaring atribut, dan memodifikasi geometri fitur selama konversi.

**Q: Apakah ada versi percobaan yang tersedia untuk Aspose.GIS untuk .NET?**  
A: Ya, Anda dapat mengunduh percobaan gratis dari [Aspose website](https://releases.aspose.com/).

## Kesimpulan
Dengan mengikuti langkah‑langkah ini Anda kini tahu **cara mengonversi shapefile ke geojson** secara efisien menggunakan **Aspose.GIS untuk .NET**. Kemampuan ini membuka **interoperabilitas data geospasial** yang mulus, memungkinkan Anda memasukkan data spasial ke dalam peta web modern, API, dan pipeline analitik. Jelajahi fitur **konversi format data GIS** yang lebih luas dari Aspose.GIS untuk menangani KML, GML, format raster, dan lainnya seiring proyek Anda berkembang.

---

**Terakhir Diperbarui:** 2026-07-24  
**Diuji Dengan:** Aspose.GIS for .NET 24.11  
**Penulis:** Aspose

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

```csharp
string dataDir = "Your Document Directory";
string shapefilePath = dataDir + "InputShapeFile.shp";
string jsonPath = dataDir + "output_out.json";
```

```csharp
VectorLayer.Convert(shapefilePath, Drivers.Shapefile, jsonPath, Drivers.GeoJson);
```

## Tutorial Terkait

- [Cara Membaca GeoJSON dari Stream dengan Aspose.GIS untuk .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Cara Mengonversi GeoJSON ke TopoJSON dengan Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Baca Shapefile C# – Filter Fitur berdasarkan Atribut dengan Aspose.GIS](/gis/net/layer-management/filter-features-by-attribute/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}