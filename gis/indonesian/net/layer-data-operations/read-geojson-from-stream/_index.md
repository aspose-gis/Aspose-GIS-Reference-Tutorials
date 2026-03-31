---
date: 2025-12-28
description: Pelajari cara membaca GeoJSON dari aliran menggunakan Aspose.GIS untuk
  .NET. Panduan membaca GeoJSON C# ini menyediakan contoh langkah demi langkah untuk
  mengintegrasikan data geospasial.
linktitle: Read GeoJSON from Stream
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
Jika Anda bertanya-tanya **cara membaca geojson** dalam aplikasi .NET, Anda berada di tempat yang tepat. Dalam tutorial ini kami akan membahas contoh **c# geojson example** lengkap yang menunjukkan cara mengonversi string GeoJSON, membuka lapisan GeoJSON dari memory stream, dan mengekstrak properti GeoJSON menggunakan Aspose.GIS. Pada akhir tutorial Anda akan memiliki pola yang dapat digunakan kembali dan dapat disisipkan ke proyek apa pun yang membutuhkan pengolahan data geospasial.

## Jawaban Cepat
- **Pustaka apa yang harus saya gunakan?** Aspose.GIS untuk .NET  
- **Apakah saya dapat membaca GeoJSON langsung dari stream?** Ya – gunakan `VectorLayer.Open` dengan `AbstractPath.FromStream`.  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Versi trial gratis cukup untuk pengujian; lisensi diperlukan untuk produksi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Apakah mengekstrak properti itu sederhana?** Ya – panggil `GetValue<T>(columnName)` pada sebuah feature.

## Apa itu “cara membaca geojson”?
Membaca GeoJSON berarti mem-parsing format berbasis JSON yang menggambarkan fitur geografis (titik, garis, poligon) dan membuat fitur-fitur tersebut tersedia sebagai objek yang dapat Anda query, edit, atau render dalam aplikasi Anda.

## Mengapa menggunakan Aspose.GIS untuk **membuka lapisan geojson**?
Aspose.GIS mengabstraksi detail parsing tingkat rendah dan memberikan API yang konsisten untuk banyak format GIS. Ini memungkinkan Anda **membuka lapisan geojson** langsung dari stream, menangani file besar secara efisien, dan mengakses atribut fitur tanpa menulis parser JSON khusus.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki:

1. **Pengetahuan dasar C#** – Anda harus nyaman dengan sintaks .NET dan IDE Visual Studio.  
2. **Aspose.GIS terinstal** – unduh pustaka dari [here](https://releases.aspose.com/gis/net/).  
3. **Lingkungan pengembangan** – Visual Studio, Visual Studio Code, atau JetBrains Rider dapat digunakan dengan baik.  

## Impor Namespace
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## Langkah Mengonversi string GeoJSON** – sebuah **c# geojson example**
Pertama kami membuat string JSON yang mewakili sebuah `FeatureCollection` sederhana. Ini adalah bagian **convert geojson string** dari alur kerja.

```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```

## Langkah 2: **Membuka lapisan GeoJSON** dari stream dan **mengekstrak properti geojson**
Sekarang kami memasukkan string ke dalam `MemoryStream`, membukanya sebagai lapisan GIS, dan mendemonstrasikan cara membaca nilai atribut (langkah **extract geojson properties**).

```csharp
using (var memoryStream = new MemoryStream(Encoding.UTF8.GetBytes(geoJson)))
using (var layer = VectorLayer.Open(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    Console.WriteLine(layer.Count); // Output: 2
    Console.WriteLine(layer[1].GetValue<string>("name")); // Output: Mary
}
```

> **Tips profesional:** `VectorLayer.Open` secara otomatis mendeteksi format GeoJSON ketika Anda memberikan `Drivers.GeoJson`. Anda juga dapat membuka file secara langsung dengan menyediakan jalur file alih-alih stream.

## Masalah Umum & Solusi
| Masalah | Solusi |
|-------|----------|
| **Format JSON tidak valid** | Verifikasi bahwa string GeoJSON terbentuk dengan baik; gunakan validator JSON. |
| **Masalah enkoding** | Pastikan stream menggunakan UTF-8 (`Encoding.UTF8.GetBytes`). |
| **Properti tidak ditemukan** | Periksa apakah nama properti ditulis dengan benar (`"name"` pada contoh). |
| **Pengecualian lisensi** | Gunakan lisensi trial untuk pengujian; terapkan lisensi permanen untuk produksi. |

## Pertanyaan yang Sering Diajukan
### Apakah Aspose.GIS kompatibel dengan format GIS lain?
Ya, Aspose.GIS mendukung GeoJSON, Shapefile, KML, GML, dan banyak format lainnya.

### Bisakah saya mencoba Aspose.GIS sebelum membeli?
Ya, Anda dapat mengunduh trial gratis Aspose.GIS dari [here](https://releases.aspose.com/).

### Di mana saya dapat menemukan dokumentasi untuk Aspose.GIS?
Anda dapat menemukan dokumentasi Aspose.GIS [here](https://reference.aspose.com/gis/net/).

### Bagaimana cara mendapatkan dukungan untuk Aspose.GIS?
Anda dapat memperoleh dukungan untuk Aspose.GIS di forum Aspose [here](https://forum.aspose.com/c/gis/33).

### Apakah saya memerlukan lisensi sementara untuk menggunakan Aspose.GIS?
Anda dapat memperoleh lisensi sementara untuk Aspose.GIS dari [here](https://purchase.aspose.com/temporary-license/).

## Kesimpulan
Dalam panduan ini kami membahas **cara membaca geojson** dari memory stream menggunakan Aspose.GIS untuk .NET, mendemonstrasikan alur kerja **c# read geojson**, dan menunjukkan cara **mengekstrak properti geojson** dari lapisan yang dibuka. Dengan langkah‑langkah ini Anda dapat mengintegrasikan penanganan data geospasial secara mulus ke dalam aplikasi .NET apa pun.

---

**Terakhir Diperbarui:** 2025-12-28  
**Diuji Dengan:** Aspose.GIS 24.11 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}