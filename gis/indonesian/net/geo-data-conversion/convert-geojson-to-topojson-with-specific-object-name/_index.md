---
date: 2025-11-29
description: Pelajari cara mengonversi GeoJSON ke TopoJSON dengan nama objek tertentu
  menggunakan Aspose.GIS untuk .NET. Panduan langkah demi langkah ini menunjukkan
  secara tepat cara mengonversi GeoJSON ke TopoJSON secara efisien.
language: id
linktitle: Convert GeoJSON to TopoJSON with Specific Object Name
second_title: Aspose.GIS .NET API
title: Konversi GeoJSON ke TopoJSON dengan Nama Objek Spesifik
url: /net/geo-data-conversion/convert-geojson-to-topojson-with-specific-object-name/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mengonversi GeoJSON ke TopoJSON dengan Nama Objek Spesifik

## Pendahuluan
Jika Anda perlu **mengonversi GeoJSON ke TopoJSON** sambil mengontrol nama objek output, Aspose.GIS untuk .NET mempermudahnya. Dalam tutorial ini Anda akan melihat secara tepat cara mengonversi GeoJSON ke TopoJSON, mengapa Anda mungkin menginginkan nama objek khusus, dan di mana menempatkan kode ke dalam proyek .NET Anda yang sudah ada.

## Jawaban Cepat
- **Apa yang dilakukan konversi?** Itu menulis ulang fitur GeoJSON menjadi topologi TopoJSON, dengan opsi mengganti nama objek root.  
- **Berapa lama implementasinya?** Sekitar 5‑10 menit setelah Aspose.GIS terpasang.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengujian; lisensi komersial diperlukan untuk produksi.  
- **Versi .NET mana yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Bisakah saya menentukan nama objek?** Ya – gunakan `DefaultObjectName` di `TopoJsonOptions`.

## Apa itu “mengonversi GeoJSON ke TopoJSON”?
`convert geojson to topojson` adalah proses menerjemahkan file GeoJSON (representasi JSON polos dari fitur geografis) menjadi TopoJSON, format yang lebih ringkas yang menyimpan segmen garis bersama sebagai busur. Ini mengurangi ukuran file dan meningkatkan kinerja rendering untuk peta web.

## Mengapa menggunakan Aspose.GIS untuk .NET untuk mengonversi GeoJSON ke TopoJSON?
- **Integrasi .NET penuh** – tidak memerlukan alat CLI eksternal.  
- **Kontrol detail** – Anda dapat mengatur nama objek output, presisi koordinat, dan lainnya.  
- **Lintas platform** – bekerja di Windows, Linux, dan macOS dengan .NET Core/.NET 5+.  
- **Penanganan error yang kuat** – validasi bawaan untuk GeoJSON input dan pengecualian yang detail.

## Prasyarat
Sebelum kita memulai konversi, pastikan Anda memiliki hal berikut:

1. **Aspose.GIS untuk .NET** – unduh build terbaru dari [halaman unduhan resmi](https://releases.aspose.com/gis/net/).  
2. **Lingkungan pengembangan .NET** – Visual Studio, Rider, atau VS Code dengan ekstensi C#.  
3. **File GeoJSON sumber** – file GeoJSON valid apa pun yang ingin Anda ubah menjadi TopoJSON.

## Impor Namespace
Pertama, bawa namespace yang diperlukan ke dalam ruang lingkup:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Panduan Langkah‑per‑Langkah

### Langkah 1: Tentukan Jalur File
Beritahu API di mana GeoJSON sumber Anda berada dan di mana TopoJSON yang dikonversi harus disimpan.

```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithObjectName_out.topojson";
```

> **Tip pro:** Gunakan `Path.Combine` untuk konstruksi jalur yang independen platform.

### Langkah 2: Atur Opsi Konversi (Cara mengonversi GeoJSON ke TopoJSON dengan nama objek khusus)
Buat instance `ConversionOptions` dan tentukan nama objek yang diinginkan melalui `TopoJsonOptions.DefaultObjectName`.

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

Ini memberi tahu Aspose.GIS untuk menulis semua fitur di bawah node `"name_of_the_object"` dalam file TopoJSON yang dihasilkan.

### Langkah 3: Lakukan Konversi
Akhirnya, panggil metode statis `Convert` pada `VectorLayer`. Metode ini membaca GeoJSON, menerapkan opsi, dan menulis TopoJSON.

```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```

Jika konversi berhasil, Anda akan menemukan file TopoJSON yang ringkas di `outputFilePath` dengan nama objek khusus yang Anda definisikan.

## Masalah Umum dan Solusinya

| Masalah | Mengapa Terjadi | Solusi |
|-------|----------------|-----|
| **File tidak ditemukan** | Jalur tidak tepat atau ekstensi file hilang. | Verifikasi `sampleGeoJsonPath` dengan `File.Exists`. |
| **GeoJSON tidak valid** | File input tidak sesuai dengan spesifikasi GeoJSON. | Gunakan `GeoJsonReader` untuk memvalidasi sebelum konversi. |
| **Nama objek diabaikan** | Menggunakan versi Aspose.GIS yang lebih lama yang tidak memiliki `DefaultObjectName`. | Tingkatkan ke rilis Aspose.GIS terbaru. |
| **Izin ditolak** | Direktori output bersifat read‑only. | Jalankan aplikasi dengan hak akses sistem file yang sesuai. |

## Kesimpulan
Anda kini tahu **cara mengonversi GeoJSON ke TopoJSON** dengan nama objek spesifik menggunakan Aspose.GIS untuk .NET. Pendekatan ini memberi Anda kontrol penuh atas topologi output, mengurangi ukuran file, dan terintegrasi mulus ke dalam alur kerja GIS berbasis .NET apa pun.

## FAQ

### Bisakah saya menggunakan Aspose.GIS untuk .NET dalam proyek komersial saya?
Ya, Anda dapat menggunakan Aspose.GIS untuk .NET dalam proyek komersial maupun pribadi.  

### Apakah ada percobaan gratis untuk Aspose.GIS untuk .NET?
Ya, Anda dapat memperoleh percobaan gratis dari [sini](https://releases.aspose.com/).  

### Di mana saya dapat menemukan dukungan untuk Aspose.GIS untuk .NET?
Anda dapat mendapatkan dukungan dari [forum Aspose.GIS](https://forum.aspose.com/c/gis/33).  

### Bagaimana cara membeli lisensi untuk Aspose.GIS untuk .NET?
Anda dapat membeli lisensi dari [sini](https://purchase.aspose.com/buy).  

### Apakah saya memerlukan lisensi sementara untuk evaluasi?
Ya, Anda dapat memperoleh lisensi sementara dari [sini](https://purchase.aspose.com/temporary-license/).

## Pertanyaan yang Sering Diajukan

**T: Apa keuntungan terbesar TopoJSON dibanding GeoJSON?**  
J: TopoJSON menyimpan segmen garis bersama hanya sekali, secara dramatis mengurangi ukuran file untuk peta yang kompleks.

**T: Bisakah saya mengonversi file GeoJSON besar (ratusan MB)?**  
J: Ya. Aspose.GIS melakukan streaming data, sehingga penggunaan memori tetap rendah; pastikan Anda memiliki ruang disk yang cukup untuk output.

**T: Apakah memungkinkan mengatur presisi koordinat selama konversi?**  
J: Tentu saja. Gunakan `TopoJsonOptions.Precision` untuk membulatkan koordinat ke jumlah desimal yang diinginkan.

**T: Apakah konversi mempertahankan semua properti GeoJSON?**  
J: Semua properti fitur disalin persis ke dalam output TopoJSON.

**T: Bagaimana cara membaca TopoJSON yang dihasilkan di JavaScript?**  
J: Pustaka seperti `topojson-client` dapat mengurai file, dan Anda dapat merujuk ke nama objek khusus yang Anda tetapkan (`name_of_the_object`).

---

**Last Updated:** 2025-11-29  
**Tested With:** Aspose.GIS for .NET 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}