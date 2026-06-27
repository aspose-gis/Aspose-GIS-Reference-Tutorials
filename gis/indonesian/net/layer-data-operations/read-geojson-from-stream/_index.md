---
date: 2026-04-24
description: Pelajari **cara membaca geojson** dari aliran menggunakan Aspose.GIS
  untuk .NET. Panduan langkah demi langkah ini menunjukkan cara **memuat aliran geojson**,
  mengurai nya, dan mengekstrak properti dalam C#.
keywords:
- how to read geojson
- load geojson stream
- Aspose GIS GeoJSON
linktitle: Baca GeoJSON dari Stream
second_title: Aspose.GIS .NET API
title: Cara Membaca GeoJSON dari Stream dengan Aspose.GIS untuk .NET
url: /id/net/layer-data-operations/read-geojson-from-stream/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membaca GeoJSON dari Stream dengan Aspose.GIS untuk .NET

## Pendahuluan
Jika Anda bertanya-tanya **how to read geojson** dalam aplikasi .NET, Anda berada di tempat yang tepat. Dalam tutorial ini kami akan membahas contoh **C# GeoJSON example** lengkap yang menunjukkan cara mengonversi string GeoJSON, **load geojson stream** ke dalam memory stream, membuka lapisan GeoJSON, dan mengekstrak properti GeoJSON menggunakan Aspose.GIS. Pada akhir tutorial Anda akan memiliki pola yang dapat digunakan kembali dan dapat diterapkan pada proyek apa pun yang perlu bekerja dengan data geospasial.

## Jawaban Cepat
- **What library should I use?** Aspose.GIS for .NET – menangani banyak format GIS secara langsung.  
- **Can I read GeoJSON directly from a stream?** Ya – gunakan `VectorLayer.Open` dengan `AbstractPath.FromStream`.  
- **Do I need a license for development?** Lisensi percobaan gratis dapat digunakan untuk pengujian; lisensi penuh diperlukan untuk produksi.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Is extracting properties simple?** Sangat mudah – panggil `GetValue<T>(columnName)` pada sebuah feature.

## Apa itu “how to read geojson”?
Membaca GeoJSON berarti mem‑parsing format berbasis JSON yang menggambarkan fitur geografis (titik, garis, poligon) dan mengubah fitur‑fitur tersebut menjadi objek yang dapat Anda query, edit, atau render dalam aplikasi Anda.

## Mengapa menggunakan Aspose.GIS untuk **open geojson layer**?
Aspose.GIS menyembunyikan detail parsing tingkat rendah dan memberi Anda API yang konsisten untuk banyak format GIS. Ini memungkinkan Anda **open geojson layer** langsung dari stream, menangani file besar secara efisien, dan mengakses atribut fitur tanpa menulis parser JSON khusus.

## Kapan Anda akan **load geojson stream**?
- Mengimpor data dari layanan web yang mengembalikan GeoJSON dalam body respons.  
- Memproses file GeoJSON yang diunggah pengguna tanpa menulisnya ke disk terlebih dahulu.  
- Bekerja dengan data dalam memori yang dihasilkan secara dinamis (mis., dari basis data atau API lain).  

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki:

1. **Basic knowledge of C#** – Anda harus nyaman dengan sintaks .NET dan IDE Visual Studio.  
2. **Aspose.GIS installed** – unduh perpustakaan dari [here](https://releases.aspose.com/gis/net/).  
3. **A development environment** – Visual Studio, Visual Studio Code, atau JetBrains Rider akan berfungsi dengan baik.  

## Impor Namespace
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## Langkah 1: **Convert GeoJSON string** – a **C# GeoJSON example**
Pertama kami membuat string JSON yang mewakili `FeatureCollection` sederhana. Ini adalah bagian **convert geojson string** dari alur kerja.

```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```

## Langkah 2: **Load GeoJSON stream** and **extract geojson properties**
Sekarang kami memasukkan string ke dalam `MemoryStream`, membukanya sebagai lapisan GIS, dan mendemonstrasikan cara membaca nilai atribut (langkah **extract geojson properties**).

```csharp
using (var memoryStream = new MemoryStream(Encoding.UTF8.GetBytes(geoJson)))
using (var layer = VectorLayer.Open(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    Console.WriteLine(layer.Count); // Output: 2
    Console.WriteLine(layer[1].GetValue<string>("name")); // Output: Mary
}
```

> **Pro tip:** `VectorLayer.Open` secara otomatis mendeteksi format GeoJSON ketika Anda memberikan `Drivers.GeoJson`. Anda juga dapat membuka file secara langsung dengan menyediakan jalur file alih-alih stream.

## Masalah Umum & Solusi
| Masalah | Solusi |
|-------|----------|
| **Invalid JSON format** | Verifikasi bahwa string GeoJSON terbentuk dengan baik; gunakan validator JSON. |
| **Encoding problems** | Pastikan stream menggunakan UTF‑8 (`Encoding.UTF8.GetBytes`). |
| **Missing properties** | Periksa nama properti ditulis dengan benar (`"name"` dalam contoh). |
| **License exception** | Gunakan lisensi percobaan untuk pengujian; terapkan lisensi permanen untuk produksi. |

## Pertanyaan yang Sering Diajukan
### Apakah Aspose.GIS kompatibel dengan format GIS lain?
Ya, Aspose.GIS mendukung GeoJSON, Shapefile, KML, GML, dan banyak format lainnya.

### Bisakah saya mencoba Aspose.GIS sebelum membeli?
Ya, Anda dapat mengunduh percobaan gratis Aspose.GIS dari [here](https://releases.aspose.com/).

### Di mana saya dapat menemukan dokumentasi untuk Aspose.GIS?
Anda dapat menemukan dokumentasi Aspose.GIS [here](https://reference.aspose.com/gis/net/).

### Bagaimana saya dapat mendapatkan dukungan untuk Aspose.GIS?
Anda dapat mendapatkan dukungan untuk Aspose.GIS di forum Aspose [here](https://forum.aspose.com/c/gis/33).

### Apakah saya memerlukan lisensi sementara untuk menggunakan Aspose.GIS?
Anda dapat memperoleh lisensi sementara untuk Aspose.GIS dari [here](https://purchase.aspose.com/temporary-license/).

## Kesimpulan
Dalam panduan ini kami membahas **how to read geojson** dari memory stream menggunakan Aspose.GIS untuk .NET, mendemonstrasikan alur kerja **C# read geojson**, dan menunjukkan cara **extract geojson properties** dari lapisan yang dibuka. Dengan langkah-langkah ini Anda dapat mengintegrasikan penanganan data geospasial secara mulus ke dalam aplikasi .NET apa pun.

---

**Terakhir Diperbarui:** 2026-04-24  
**Diuji Dengan:** Aspose.GIS 24.11 for .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}