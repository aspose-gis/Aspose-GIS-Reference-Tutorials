---
date: 2025-12-06
description: Pelajari cara mengonversi GeoJSON ke TopoJSON dengan pengelompokan, mengatur
  atribut nama objek, dan mengelompokkan fitur GeoJSON menggunakan Aspose.GIS untuk
  .NET.
linktitle: How to Convert GeoJSON to TopoJSON with Grouping using Aspose.GIS
second_title: Aspose.GIS .NET API
title: Cara Mengonversi GeoJSON ke TopoJSON dengan Pengelompokan menggunakan Aspose.GIS
url: /id/net/geo-data-conversion/convert-geojson-to-topojson-with-grouping/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengonversi GeoJSON ke TopoJSON dengan Pengelompokan menggunakan Aspose.GIS

## Pendahuluan

Dalam tutorial langkah‑demi‑langkah ini Anda akan belajar **cara mengonversi GeoJSON** menjadi TopoJSON sambil mengelompokkan fitur berdasarkan atribut yang dipilih. Menggunakan Aspose.GIS .NET API membuat konversi menjadi cepat, andal, dan sepenuhnya dapat dikendalikan dari kode C# Anda. Baik Anda membangun layanan konversi GeoJSON ASP.NET atau alat GIS desktop, panduan ini menunjukkan secara tepat apa yang perlu Anda lakukan.

## Jawaban Cepat
- **Perpustakaan apa yang menangani konversi?** Aspose.GIS untuk .NET  
- **Berapa lama implementasinya?** Biasanya 5‑10 menit untuk pengaturan dasar  
- **Apakah saya memerlukan lisensi untuk produksi?** Ya, lisensi komersial diperlukan (tersedia percobaan gratis)  
- **Bisakah saya mengelompokkan fitur berdasarkan atribut apa pun?** Ya – atur `ObjectNameAttribute` ke bidang yang ingin Anda gunakan untuk pengelompokan  
- **Apakah .NET Core didukung?** Tentu – API bekerja dengan .NET Core, .NET 5/6, dan .NET Framework klasik  

## Apa itu GeoJSON dan TopoJSON?

GeoJSON adalah format JSON yang banyak digunakan untuk mengkodekan fitur geografis seperti titik, garis, dan poligon. TopoJSON memperluas GeoJSON dengan menyimpan topologi (segmen garis yang berbagi) yang mengurangi ukuran file dan meningkatkan kinerja rendering untuk peta kompleks. Mengonversi di antara keduanya merupakan langkah umum ketika Anda memerlukan data peta yang ringkas untuk visualisasi web.

## Mengapa Mengelompokkan Fitur GeoJSON?

Pengelompokan (`group geojson features`) memungkinkan Anda mengatur geometri terkait di bawah satu objek bernama dalam TopoJSON yang dihasilkan. Ini sangat berguna ketika:
- Anda ingin membuat lapisan terpisah untuk wilayah administratif yang berbeda.  
- Perpustakaan pemetaan front‑end Anda mengharapkan objek bernama untuk penataan atau interaksi.  
- Anda perlu mengurangi duplikasi dengan berbagi batas antara fitur yang berdekatan.

## Prasyarat

Sebagai langkah awal, pastikan Anda memiliki prasyarat berikut:

1. **Aspose.GIS untuk .NET** – unduh dan pasang dari situs resmi [di sini](https://releases.aspose.com/gis/net/).  
2. **Lingkungan Pengembangan** – Visual Studio, Visual Studio Code, atau IDE apa pun yang mendukung C#.  
3. **File GeoJSON Contoh** – file yang berisi fitur yang ingin Anda konversi.  

## Impor Namespace

Pertama, sertakan namespace yang diperlukan dalam proyek Anda:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
```

## Panduan Langkah‑demi‑Langkah

### Langkah 1: Tentukan Jalur File

Tentukan di mana GeoJSON sumber berada dan ke mana TopoJSON harus ditulis:

```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithGrouping_out.topojson";
```

> **Tip Pro:** Gunakan `Path.Combine` untuk membangun jalur lintas‑platform jika Anda menargetkan .NET Core.

### Langkah 2: Konfigurasikan Opsi Konversi (Atur Atribut Nama Objek)

Buat instance `ConversionOptions` dan beri tahu Aspose.GIS cara mengelompokkan fitur:

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

Ganti `"group"` dengan nama properti sebenarnya dalam GeoJSON Anda yang ingin Anda gunakan untuk **pengelompokan fitur geojson**. `DefaultObjectName` memastikan setiap fitur masuk ke dalam objek TopoJSON, bahkan jika atribut tersebut tidak ada.

### Langkah 3: Lakukan Konversi (Konversi GeoJSON ke TopoJSON)

Jalankan konversi dengan satu panggilan API:

```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```

Setelah eksekusi, `convertedSampleWithGrouping_out.topojson` akan berisi representasi TopoJSON, dengan fitur-fitur yang dikelompokkan sesuai atribut yang Anda tentukan.

## Masalah Umum dan Pemecahan Masalah

| Gejala | Penyebab Kemungkinan | Solusi |
|---------|----------------------|--------|
| **Semua fitur berakhir di “unnamed”** | `ObjectNameAttribute` tidak cocok dengan properti apa pun dalam GeoJSON | Verifikasi nama properti yang tepat (case‑sensitive) dan perbarui opsi |
| **File output kosong** | Jalur file tidak benar atau izin baca yang hilang | Gunakan jalur absolut atau pastikan aplikasi memiliki akses sistem file |
| **Konversi melempar `NotSupportedException`** | Mencoba mengonversi GeoJSON dengan tipe geometri yang tidak didukung (mis., GeometryCollection) | Sederhanakan data sumber atau tingkatkan ke versi Aspose.GIS terbaru |

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya mengelompokkan fitur berdasarkan beberapa atribut?**  
A: Ya, Anda dapat menggabungkan beberapa bidang menjadi satu atribut virtual atau menjalankan beberapa proses konversi dengan nilai `ObjectNameAttribute` yang berbeda.

**Q: Apakah Aspose.GIS kompatibel dengan ASP.NET Core?**  
A: Tentu – perpustakaan ini bekerja dengan ASP.NET Core, .NET 5, .NET 6, dan .NET Framework klasik.

**Q: Bisakah saya mengonversi format geografis lain selain GeoJSON?**  
A: Ya, Aspose.GIS mendukung Shapefile, KML, GML, CSV, dan banyak format lainnya untuk impor dan ekspor.

**Q: Apakah Aspose.GIS menawarkan percobaan gratis?**  
A: Ya, Anda dapat memperoleh percobaan gratis Aspose.GIS dari [di sini](https://releases.aspose.com/).

**Q: Di mana saya dapat mendapatkan dukungan untuk Aspose.GIS?**  
A: Anda dapat mendapatkan dukungan dari forum komunitas Aspose.GIS [di sini](https://forum.aspose.com/c/gis/33).

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**Last Updated:** 2025-12-06  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose