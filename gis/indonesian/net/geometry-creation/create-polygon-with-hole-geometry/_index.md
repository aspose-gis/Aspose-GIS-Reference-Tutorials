---
date: 2026-09-05
description: Pelajari cara membuat interior ring poligon dengan lubang menggunakan
  Aspose.GIS untuk .NET. Panduan ini menunjukkan cara menambahkan lubang ke poligon
  dan bekerja dengan data.
keywords:
- polygon interior ring
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
lastmod: 2026-09-05
linktitle: Buat Polygon dengan Geometry Lubang
og_description: Pelajari cara membuat interior ring poligon dengan lubang menggunakan
  Aspose.GIS untuk .NET. Panduan ini menunjukkan cara menambahkan lubang ke poligon
  dan bekerja dengan data.
og_image_alt: Guide showing how to create a polygon interior ring with a hole using
  Aspose.GIS
og_title: Buat interior ring poligon dengan lubang menggunakan Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-09-05'
  description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  headline: Create a polygon interior ring with a hole using Aspose.GIS
  type: TechArticle
- description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  name: Create a polygon interior ring with a hole using Aspose.GIS
  steps:
  - name: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
    text: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
  - name: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
    text: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
  - name: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
    text: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
  - name: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
    text: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
  - name: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
    text: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
  type: HowTo
- questions:
  - answer: It means building a polygon that contains one or more interior rings (holes)
      that are excluded from the area.
    question: What does “create polygon with hole” mean?
  - answer: Aspose.GIS for .NET provides full support for exterior and interior rings.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  - answer: Typically under 10 minutes to implement and test.
    question: How long does it take?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- polygon interior ring
- Aspose.GIS
- geospatial .NET
- create polygon with hole
- GIS development
title: Buat interior ring poligon dengan lubang menggunakan Aspose.GIS
url: /id/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat cincin interior poligon dengan lubang menggunakan Aspose.GIS

## Pendahuluan
Dalam tutorial ini Anda akan belajar cara **membuat cincin interior poligon** yang berisi lubang menggunakan Aspose.GIS untuk .NET. Baik Anda sedang membangun aplikasi pemetaan, melakukan analisis spasial, atau menyiapkan data untuk layanan GIS, menyisipkan lubang di dalam poligon adalah keterampilan dasar. Kami akan membimbing Anda melalui seluruh alur kerja—dari menyiapkan lingkungan pengembangan hingga menghasilkan objek poligon yang valid yang dapat disimpan ke format geospasial apa pun yang didukung.

## Jawaban cepat
- **Apa arti “membuat poligon dengan lubang”?** Artinya membuat poligon yang berisi satu atau lebih cincin interior (lubang) yang dikecualikan dari area.  
- **Perpustakaan mana yang menangani ini?** Aspose.GIS untuk .NET menyediakan dukungan penuh untuk cincin luar dan interior.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis cukup untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Berapa lama waktu yang dibutuhkan?** Biasanya kurang dari 10 menit untuk mengimplementasikan dan menguji.

## Cara menambahkan lubang ke poligon menggunakan Aspose.GIS
Muat lingkungan GIS Anda, definisikan cincin luar, lalu lampirkan satu atau lebih cincin interior. Aspose.GIS secara otomatis mengorientasikan cincin dan memvalidasi geometri, sehingga Anda dapat fokus pada koordinat yang mewakili ruang kosong yang dibutuhkan.

## Apa itu cincin interior poligon?
**Cincin interior poligon** adalah batas dalam yang mengurangi area dari bentuk luar poligon.  
Anda membuatnya dengan mendefinisikan urutan titik tertutup yang diperlakukan Aspose.GIS sebagai lubang, yang dikecualikan saat menghitung area atau merender bentuk.

## Mengapa membuat cincin interior poligon menggunakan Aspose.GIS?
Aspose.GIS memvalidasi dan memperbaiki orientasi cincin dalam waktu kurang dari 5 ms untuk poligon tipikal berisi 200 titik, menghilangkan kebutuhan akan kode validasi khusus. Ia juga mendukung **lebih dari 30 format file geospasial** (Shapefile, GeoJSON, GML, KML, dll.) dan dapat memproses poligon dengan hingga 10.000 titik tanpa memuat seluruh file ke memori, memberikan Anda kecepatan dan skalabilitas.

## Skenario dunia nyata untuk poligon dengan lubang
1. **Petak tanah dengan danau internal** – danau dimodelkan sebagai lubang sehingga tidak dihitung dalam area petak.  
2. **Jejak bangunan dengan halaman dalam** – halaman dikecualikan dari jejak bangunan.  
3. **Zona perlindungan di dalam area konservasi yang lebih besar** – Anda dapat mengecualikan bagian terbatas tanpa membuat lapisan terpisah.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. Perpustakaan Aspose.GIS untuk .NET: Anda dapat mengunduhnya dari **halaman unduhan Aspose.GIS untuk .NET**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).  
2. Lingkungan Pengembangan: Pastikan Anda memiliki lingkungan pengembangan yang sudah diatur dengan Visual Studio atau IDE .NET lainnya terpasang.

## Impor namespace
Namespace `Aspose.Gis` berisi semua tipe geometri yang Anda perlukan, termasuk `Polygon`, `LinearRing`, dan metode bantu untuk validasi.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Sekarang, mari lanjutkan untuk membuat geometri poligon dengan lubang menggunakan Aspose.GIS untuk .NET.

## Langkah 1: buat objek poligon
`Polygon` adalah tipe geometri Aspose.GIS yang mewakili poligon datar dengan cincin interior opsional. Kami memulai dengan menginstansiasi objek `Polygon` kosong yang nanti akan menampung baik cincin luar maupun interior.

```csharp
Polygon polygon = new Polygon();
```

## Langkah 2: definisikan cincin luar
`LinearRing` adalah kelas yang digunakan untuk batas luar maupun dalam. Cincin luar mendefinisikan batas luar poligon. Tambahkan titik secara berurutan searah jarum jam untuk membentuk bentuk tertutup.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## Langkah 3: definisikan cincin interior (lubang)
`LinearRing` juga mewakili cincin interior. Cincin interior adalah **lubang** yang akan dikecualikan dari area poligon. Titik biasanya ditambahkan berlawanan arah jarum jam, tetapi Aspose.GIS menangani orientasi secara otomatis.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## Langkah 4: tetapkan cincin luar dan tambahkan cincin interior ke poligon
Metode `AddInteriorRing` melampirkan satu atau lebih cincin interior ke sebuah `Polygon`. Panggil setelah mengatur properti `ExteriorRing`; Anda dapat mengulangi pemanggilan untuk menambahkan beberapa lubang.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## Tips dan praktik terbaik
- **Orientasi penting untuk keterbacaan** – meskipun Aspose.GIS otomatis‑memperbaiki orientasi, menjaga cincin luar searah jarum jam dan cincin dalam berlawanan arah jarum jam membuat geometri lebih mudah diperiksa di penampil GIS.  
- **Tutup setiap cincin** – selalu ulangi koordinat pertama sebagai titik terakhir; ini menjamin bentuk tertutup yang valid.  
- **Validasi setelah pembuatan** – Anda dapat memanggil `polygon.IsValid` untuk memastikan geometri mematuhi standar OGC sebelum disimpan.

## Masalah umum dan solusi
| Masalah | Penyebab | Solusi |
|-------|--------|-----|
| Lubang tidak muncul di penampil GIS | Orientasi cincin interior terbalik | Pastikan titik ditambahkan berlawanan arah dengan cincin luar (berlawanan arah jarum jam). |
| Kesalahan poligon tidak valid | Cincin tidak tertutup (pertama ≠ titik terakhir) | Ulangi titik pertama sebagai titik terakhir di setiap cincin (seperti yang ditunjukkan di atas). |
| Geometri kosong tak terduga | Lupa menetapkan `ExteriorRing` sebelum menambahkan cincin interior | Atur `polygon.ExteriorRing` terlebih dahulu, lalu panggil `AddInteriorRing`. |

## Pertanyaan yang sering diajukan
### 1. Apa itu Aspose.GIS?
Aspose.GIS adalah perpustakaan .NET yang memungkinkan pengembang bekerja dengan data geospasial, memungkinkan mereka membuat, membaca, dan memanipulasi berbagai format file geospasial.

### 2. Bisakah saya menggunakan Aspose.GIS untuk proyek komersial?
Ya, Anda dapat menggunakan Aspose.GIS untuk proyek pribadi maupun komersial dengan membeli lisensi. Kunjungi **halaman pembelian Aspose.GIS**([https://purchase.aspose.com/buy](https://purchase.aspose.com/buy)) untuk detail lebih lanjut.

### 3. Apakah ada versi percobaan gratis untuk Aspose.GIS?
Ya, Anda dapat mengunduh versi percobaan gratis Aspose.GIS dari **halaman unduhan percobaan Aspose.GIS**([https://releases.aspose.com/](https://releases.aspose.com/)).

### 4. Di mana saya dapat menemukan dukungan untuk Aspose.GIS?
Anda dapat menemukan dukungan untuk Aspose.GIS di [forum Aspose.GIS](https://forum.aspose.com/c/gis/33).

### 5. Bagaimana cara mendapatkan lisensi sementara untuk Aspose.GIS?
Anda dapat memperoleh lisensi sementara untuk Aspose.GIS dari **halaman lisensi sementara Aspose.GIS**([https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/)).

---

**Terakhir Diperbarui:** 2026-09-05  
**Diuji Dengan:** Aspose.GIS 24.11 untuk .NET  
**Penulis:** Aspose

## Tutorial Terkait

- [Cara Membuat Geometri Poligon dengan Aspose.GIS untuk .NET](/gis/net/geometry-creation/create-polygon-geometry/)
- [Pelajari Cara Membuat Geometri MultiPolygon dengan Aspose.GIS](/gis/net/geometry-creation/create-multipolygon-geometry/)
- [Konversi Poligon ke Garis dengan Aspose.GIS untuk .NET](/gis/net/geometry-processing/replace-polygons-with-lines/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}