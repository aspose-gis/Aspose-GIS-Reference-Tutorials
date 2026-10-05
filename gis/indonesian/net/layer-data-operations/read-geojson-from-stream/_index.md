---
date: 2026-10-05
description: Pelajari cara membaca geojson dari stream menggunakan Aspose.GIS for
  .NET. Panduan langkah‑demi‑langkah ini menunjukkan cara memuat stream geojson, mengurai,
  dan mengekstrak properti dalam C#.
keywords:
- how to read geojson
- load geojson stream
- parse geojson c#
- open geojson layer
- extract geojson properties
lastmod: 2026-10-05
linktitle: Baca GeoJSON dari Stream
og_description: Pelajari cara membaca geojson dari stream menggunakan Aspose.GIS for
  .NET, termasuk mengurai, membuka lapisan geojson, dan mengekstrak properti dalam
  C#.
og_image_alt: Tutorial guide showing how to read geojson from a stream with Aspose.GIS
  in C#
og_title: Cara membaca geojson dari stream dengan Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to read geojson from a stream using Aspose.GIS for .NET.
    This step‑by‑step guide shows you how to load geojson stream, parse it, and extract
    properties in C#.
  headline: How to read geojson from a stream with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to read geojson from a stream using Aspose.GIS for .NET.
    This step‑by‑step guide shows you how to load geojson stream, parse it, and extract
    properties in C#.
  name: How to read geojson from a stream with Aspose.GIS for .NET
  steps:
  - name: '**Basic knowledge of C#** – you should be comfortable with .NET syntax
      and the Visual Studio IDE.'
    text: '**Basic knowledge of C#** – you should be comfortable with .NET syntax
      and the Visual Studio IDE.'
  - name: '**Aspose.GIS installed** – download the library from [Aspose.GIS .NET download
      page](https://releases.aspose.com/gis/net/).'
    text: '**Aspose.GIS installed** – download the library from [Aspose.GIS .NET download
      page](https://releases.aspose.com/gis/net/).'
  - name: '**A development environment** – Visual Studio, Visual Studio Code, or JetBrains
      Rider will work fine.'
    text: '**A development environment** – Visual Studio, Visual Studio Code, or JetBrains
      Rider will work fine.'
  type: HowTo
- questions:
  - answer: Aspose.GIS for .NET – it handles 30+ GIS formats out of the box.
    question: What library should I use?
  - answer: Yes – call `VectorLayer.Open` with `AbstractPath.FromStream`.
    question: Can I read GeoJSON directly from a stream?
  - answer: A free trial works for testing; a full license is required for production.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.
    question: Which .NET versions are supported?
  - answer: Absolutely – use `GetValue<T>(columnName)` on a feature.
    question: Is extracting properties simple?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geojson
- Aspose.GIS
- .NET GIS
- C# geospatial
title: Cara membaca geojson dari stream dengan Aspose.GIS for .NET
url: /id/net/layer-data-operations/read-geojson-from-stream/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membaca geojson dari stream dengan Aspose.GIS untuk .NET

## Pendahuluan
Jika Anda bertanya-tanya **cara membaca geojson** dalam aplikasi .NET, Anda berada di tempat yang tepat. Dalam tutorial ini kami akan membahas contoh **contoh C# GeoJSON** lengkap yang menunjukkan cara mengonversi string GeoJSON, **memuat stream geojson** ke dalam memory stream, membuka lapisan GeoJSON, dan mengekstrak properti GeoJSON menggunakan Aspose.GIS. Pada akhir tutorial Anda akan memiliki pola yang dapat digunakan kembali dan dapat dimasukkan ke dalam proyek apa pun yang membutuhkan data geospasial.

## Jawaban Cepat
- **Library apa yang harus saya gunakan?** Aspose.GIS untuk .NET – menangani lebih dari 30 format GIS secara langsung.  
- **Bisakah saya membaca GeoJSON langsung dari stream?** Ya – panggil `VectorLayer.Open` dengan `AbstractPath.FromStream`.  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Versi percobaan gratis dapat digunakan untuk pengujian; lisensi penuh diperlukan untuk produksi.  
- **Versi .NET mana yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Apakah mengekstrak properti itu sederhana?** Tentu – gunakan `GetValue<T>(columnName)` pada sebuah feature.

**VectorLayer.Open** membuka lapisan GIS dari sumber data seperti file atau stream. **AbstractPath.FromStream** membuat objek abstract path yang mewakili stream yang diberikan untuk driver GIS. **GetValue<T>(columnName)** membaca nilai atribut yang ditentukan dari sebuah feature dan mengembalikannya sebagai tipe T.

## Apa itu cara membaca geojson?
Membaca geojson adalah proses mengonversi string atau stream berformat GeoJSON menjadi objek fitur geografis dalam memori. Format ini mengkodekan titik, garis, dan poligon menggunakan JSON, sehingga memudahkan pertukaran data spasial antara layanan web, basis data, dan aplikasi klien. Setelah diparsing, Anda dapat melakukan query, mengedit, atau merender fitur-fitur tersebut dengan library .NET yang mendukung GIS, seperti Aspose.GIS.

## Mengapa menggunakan Aspose.GIS untuk membuka lapisan geojson?
Aspose.GIS memungkinkan Anda membuka lapisan GeoJSON langsung dari stream, menghilangkan kebutuhan akan file sementara dan mengurangi beban I/O. Library ini mendukung lebih dari 30 format GIS dan dapat memproses file hingga 2 GB tanpa memuat seluruh dokumen ke dalam memori, yang ideal untuk dataset besar. Ia juga menormalkan sistem referensi koordinat secara otomatis, sehingga Anda dapat fokus pada logika bisnis alih-alih parsing tingkat rendah.

## Kapan Anda akan memuat stream geojson?
Anda akan memuat stream GeoJSON ketika menerima data spasial dari API, perlu menangani file yang diunggah pengguna tanpa menyimpannya ke disk, atau menghasilkan GeoJSON secara langsung dari query basis data. Streaming menghindari penulisan disk yang tidak perlu, meningkatkan kinerja dalam skenario throughput tinggi, dan menjaga aplikasi Anda tetap stateless, yang sangat berharga dalam microservices berbasis cloud.

## Prasyarat
1. **Pengetahuan dasar C#** – Anda harus nyaman dengan sintaks .NET dan IDE Visual Studio.  
2. **Aspose.GIS terpasang** – unduh library dari [Aspose.GIS .NET download page](https://releases.aspose.com/gis/net/).  
3. **Lingkungan pengembangan** – Visual Studio, Visual Studio Code, atau JetBrains Rider akan berfungsi dengan baik.  

## Impor namespace
Namespace `Aspose.GIS` menyediakan kelas GIS inti. `System.IO` memberikan `MemoryStream`, dan `System.Text` menyediakan utilitas enkoding UTF‑8. Mengimpor namespace ini membuat kode selanjutnya menjadi ringkas dan mudah dibaca.

```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## Langkah 1: mengonversi string geojson – contoh C# GeoJSON
Pertama kami membuat string JSON yang mewakili `FeatureCollection` sederhana. Ini adalah bagian **mengonversi string geojson** dari alur kerja.

```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```

## Langkah 2: memuat stream geojson dan mengekstrak properti geojson
Sekarang kami memasukkan string ke dalam `MemoryStream`, membukanya sebagai lapisan GIS, dan mendemonstrasikan cara membaca nilai atribut (langkah **mengekstrak properti geojson**).

```csharp
using (var memoryStream = new MemoryStream(Encoding.UTF8.GetBytes(geoJson)))
using (var layer = VectorLayer.Open(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    Console.WriteLine(layer.Count); // Output: 2
    Console.WriteLine(layer[1].GetValue<string>("name")); // Output: Mary
}
```

> **Pro tip:** `VectorLayer.Open` secara otomatis mendeteksi format GeoJSON ketika Anda memberikan `Drivers.GeoJson`. Anda juga dapat membuka file secara langsung dengan menyediakan path file alih-alih stream.

## Masalah umum & solusi
| Masalah | Solusi |
|-------|----------|
| **Format JSON tidak valid** | Verifikasi bahwa string GeoJSON terbentuk dengan baik; gunakan validator JSON. |
| **Masalah enkoding** | Pastikan stream menggunakan UTF‑8 (`Encoding.UTF8.GetBytes`). |
| **Properti hilang** | Periksa nama properti sudah dieja dengan benar (`"name"` dalam contoh). |
| **Pengecualian lisensi** | Gunakan lisensi percobaan untuk pengujian; terapkan lisensi permanen untuk produksi. |

## Pertanyaan yang sering diajukan
### Apakah Aspose.GIS kompatibel dengan format GIS lainnya?
Ya, Aspose.GIS mendukung GeoJSON, Shapefile, KML, GML, dan lebih dari 20 format tambahan, memungkinkan Anda beralih antar sumber data tanpa mengubah kode.

### Bisakah saya mencoba Aspose.GIS sebelum membeli?
Anda dapat mengunduh versi percobaan gratis Aspose.GIS dari [Aspose.GIS free trial download page](https://releases.aspose.com/).

### Di mana saya dapat menemukan dokumentasi untuk Aspose.GIS?
Anda dapat menemukan dokumentasi untuk Aspose.GIS di [Aspose.GIS .NET API reference](https://reference.aspose.com/gis/net/).

### Bagaimana saya dapat mendapatkan dukungan untuk Aspose.GIS?
Anda dapat mendapatkan dukungan untuk Aspose.GIS di forum Aspose GIS [Aspose GIS forum](https://forum.aspose.com/c/gis/33).

### Apakah saya memerlukan lisensi sementara untuk menggunakan Aspose.GIS?
Anda dapat memperoleh lisensi sementara untuk Aspose.GIS dari [temporary license request page](https://purchase.aspose.com/temporary-license/).

## Kesimpulan
Dalam panduan ini kami membahas **cara membaca geojson** dari memory stream menggunakan Aspose.GIS untuk .NET, mendemonstrasikan alur kerja **C# read geojson**, dan menunjukkan cara **mengekstrak properti geojson** dari lapisan yang dibuka. Dengan langkah-langkah ini Anda dapat mengintegrasikan penanganan data geospasial secara mulus ke dalam aplikasi .NET apa pun.

---

**Terakhir Diperbarui:** 2026-10-05  
**Diuji Dengan:** Aspose.GIS 24.11 untuk .NET  
**Penulis:** Aspose

## Tutorial Terkait

- [Cara Menulis GeoJSON ke Stream dengan Aspose.GIS untuk .NET](/gis/net/layer-data-operations/write-geojson-to-stream/)
- [Cara Mengonversi GeoJSON ke GDB Menggunakan Aspose.GIS untuk .NET](/gis/net/layer-management/convert-geojson-layer-to-file-gdb/)
- [Mengonversi Shapefile ke GeoJSON dengan Aspose.GIS untuk .NET](/gis/net/layer-management/extract-features-to-geojson/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}