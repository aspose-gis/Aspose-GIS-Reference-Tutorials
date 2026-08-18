---
date: 2026-06-10
description: Pelajari cara membuat geometri linestring di .NET dan mengonversi geometri
  ke WKB menggunakan Aspose.GIS untuk .NET dengan varian ExtendedPostGis.
keywords:
- create linestring geometry .net
- WKB variant Aspose GIS
- EWKB conversion .NET
linktitle: Tentukan Varian WKB pada Translasi
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  headline: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  name: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  steps:
  - name: Creating a Geometry Object
    text: The `Geometry` class is Aspose.GIS's base type that represents any spatial
      object in memory. Linestring represents a series of connected points forming
      a linear geometry. In this step we instantiate a `Linestring` with a collection
      of coordinate pairs that model a simple road segment.
  - name: Generating WKB Representation
    text: '`WkbVariant.ExtendedPostGis` is the enum value that tells Aspose.GIS to
      include SRID in the output binary. Here we call the `AsBinary` method, passing
      the EWKB variant, which returns a `byte[]` containing the full binary representation.'
  - name: Writing to File
    text: '`File.WriteAllBytes` writes the binary array to disk. The resulting file
      (`EWkbFile.ewkb`) can be imported directly into a PostGIS table using the `ST_GeomFromEWKB`
      function.'
  type: HowTo
- questions:
  - answer: Yes, the `ExtendedPostGis` variant produces EWKB that includes SRID, which
      PostGIS reads directly via `ST_GeomFromEWKB`.
    question: Can I use the EWKB file with PostGIS?
  - answer: Absolutely. Use `Geometry.FromBinary(byteArray)` to reconstruct the geometry
      from its binary form.
    question: Is it possible to read a WKB file back into a geometry object?
  - answer: Yes, Aspose.GIS handles points, linestrings, polygons, multipolygons,
      and many more spatial types.
    question: Does the library support other geometry types like polygons?
  - answer: Set the `SRID` property on the geometry object before calling `AsBinary`,
      e.g., `linestring.SRID = 4326;`.
    question: How do I specify a different SRID when creating the geometry?
  - answer: Yes, the same API works across .NET Framework, .NET Core, and .NET 5/6
      without modification.
    question: Will this code work on .NET Core?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Buat Geometri Linestring & Varian WKB di Aspose.GIS untuk .NET
url: /id/net/geometry-processing/specify-wkb-variant-on-translation/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Geometri Linestring & Varian WKB di Aspose.GIS untuk .NET

## Pendahuluan
Jika Anda perlu **membuat geometri linestring .NET** dan kemudian mengubah geometri tersebut menjadi bentuk biner, Aspose.GIS untuk .NET memberikan API yang bersih dan berperforma tinggi yang bekerja di .NET Framework, .NET Core, dan .NET 5/6+. Dalam tutorial ini kami akan membahas setiap langkah—dari mengimpor namespace hingga menulis file EWKB—sehingga Anda dapat mempertahankan informasi SRID dan mengintegrasikan data GIS ke PostgreSQL/PostGIS atau alur kerja berbasis biner apa pun tanpa kesulitan.

## Jawaban Cepat
- **What does WKB stand for?** Well‑Known Binary, a compact binary representation of geometric objects.  
- **Which WKB variant stores SRID?** The `ExtendedPostGis` (EWKB) variant embeds SRID directly in the binary.  
- **Do I need a license?** A temporary or full Aspose.GIS license is required for production deployments.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6+.  
- **How long does the implementation take?** Typically under 10 minutes for a basic example.

## Apa itu Geometri Linestring?
Geometri linestring adalah bentuk sederhana yang terdiri dari daftar terurut titik‑titik yang dihubungkan oleh segmen garis lurus. Ini merupakan representasi utama untuk fitur linear seperti jalan, pipa, atau jalur sungai dalam basis data spasial.

## Mengapa Menentukan Varian WKB?
Menggunakan varian WKB yang tepat menjamin bahwa metadata penting—terutama Spatial Reference System Identifier (SRID)—menyertai geometri Anda. Varian `ExtendedPostGis` (EWKB) menyimpan SRID di dalam payload biner, memungkinkan pertukaran data yang mulus dengan PostGIS, Oracle Spatial, atau sistem apa pun yang mengharapkan biner yang menyadari SRID.

## Prasyarat
Sebelum Anda memulai, pastikan Anda memiliki hal‑hal berikut:

### Menginstal Aspose.GIS untuk .NET
1. Unduh Aspose.GIS: Kunjungi [download link](https://releases.aspose.com/gis/net/) untuk mendapatkan paket terbaru.  
2. Tambahkan paket NuGet ke proyek Anda (misalnya, `Install-Package Aspose.GIS`).  

### Familiaritas dengan Pemrograman C#
- Pemahaman dasar tentang sintaks C# dan struktur proyek.  
- Kemampuan menjalankan proyek konsol .NET atau perpustakaan kelas.

## Impor Namespace
Namespace `Aspose.GIS` memberi Anda akses ke semua kelas terkait geometri.  

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Namespace ini menyediakan fungsionalitas GIS inti, termasuk pembuatan geometri, transformasi, dan serialisasi biner.

## Cara membuat geometri linestring?
Untuk membuat linestring, buat objek `Linestring` dengan daftar terurut pasangan koordinat, atur SRID‑nya jika diperlukan, lalu serialisasikan ke varian WKB yang diinginkan. Proses ini melibatkan tiga langkah: membangun geometri, memilih varian `ExtendedPostGis` untuk mempertahankan SRID, dan menulis array byte yang dihasilkan ke sebuah file.

### Langkah 1: Membuat Objek Geometri
Kelas `Geometry` adalah tipe dasar Aspose.GIS yang mewakili setiap objek spasial dalam memori.  
Linestring mewakili serangkaian titik yang terhubung membentuk geometri linear.  

```csharp
IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
```
Pada langkah ini kami menginstansiasi `Linestring` dengan kumpulan pasangan koordinat yang menggambarkan segmen jalan sederhana.

### Langkah 2: Menghasilkan Representasi WKB
`WkbVariant.ExtendedPostGis` adalah nilai enum yang memberi tahu Aspose.GIS untuk menyertakan SRID dalam biner output.  

```csharp
byte[] wkb = geometry.AsBinary(WkbVariant.ExtendedPostGis);
```
Di sini kami memanggil metode `AsBinary`, dengan memberikan varian EWKB, yang mengembalikan `byte[]` berisi representasi biner lengkap.

### Langkah 3: Menulis ke File
`File.WriteAllBytes` menulis array biner ke disk.  

```csharp
File.WriteAllBytes(Path.Combine("Your Document Directory", "EWkbFile.ewkb"), wkb);
```
File yang dihasilkan (`EWkbFile.ewkb`) dapat diimpor langsung ke tabel PostGIS menggunakan fungsi `ST_GeomFromEWKB`.

## Masalah Umum dan Solusinya
| Masalah | Alasan | Solusi |
|-------|--------|----------|
| **Empty file** | `Path.Combine` points to a non‑existent directory. | Ensure the target directory exists or create it with `Directory.CreateDirectory`. |
| **Incorrect SRID** | Using the default `WkbVariant.Standard` drops SRID. | Always use `WkbVariant.ExtendedPostGis` when SRID preservation is required. |
| **License exception** | Running without a valid license in production. | Apply a temporary or full license before executing the code in a production environment. |

## Pertanyaan yang Sering Diajukan
**Q: Can I use the EWKB file with PostGIS?**  
A: Yes, the `ExtendedPostGis` variant produces EWKB that includes SRID, which PostGIS reads directly via `ST_GeomFromEWKB`.  

**Q: Is it possible to read a WKB file back into a geometry object?**  
A: Absolutely. Use `Geometry.FromBinary(byteArray)` to reconstruct the geometry from its binary form.  

**Q: Does the library support other geometry types like polygons?**  
A: Yes, Aspose.GIS handles points, linestrings, polygons, multipolygons, and many more spatial types.  

**Q: How do I specify a different SRID when creating the geometry?**  
A: Set the `SRID` property on the geometry object before calling `AsBinary`, e.g., `linestring.SRID = 4326;`.  

**Q: Will this code work on .NET Core?**  
A: Yes, the same API works across .NET Framework, .NET Core, and .NET 5/6 without modification.

---

**Terakhir Diperbarui:** 2026-06-10  
**Diuji Dengan:** Aspose.GIS for .NET 23.9 (latest at time of writing)  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Menerjemahkan Geometri ke Format WKB dengan Aspose.GIS untuk .NET](/gis/net/geometry-processing/translate-geometry-to-wkb/)
- [Menentukan Varian WKT pada Translasi menggunakan Aspose.GIS](/gis/net/geometry-processing/specify-wkt-variant-on-translation/)
- [Membuat Geometri MultiLineString menggunakan Aspose.GIS untuk .NET](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}