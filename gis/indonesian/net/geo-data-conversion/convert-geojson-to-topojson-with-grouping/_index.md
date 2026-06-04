---
date: 2026-02-05
description: Pelajari cara **mengonversi geojson ke topojson** dengan pengelompokan,
  mengatur atribut nama objek, dan mengelompokkan fitur GeoJSON menggunakan Aspose.GIS
  untuk .NET.
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

## Perkenalan

Dalam tutorial langkah‑demi‑langkah ini Anda akan belajar **cara mengubah GeoJSON** menjadi TopoJSON sambil mengelompokkan fitur berdasarkan atribut yang dipilih.Menggunakan Aspose.GIS.NET API membuat konversi menjadi cepat, dapat diandalkan, dan sepenuhnya dapat dikendalikan dari kode C# Anda. Baik Anda sedang membangun layanan konversi GeoJSON ASP.NETatau alat GIS desktop, panduan ini menunjukkan secara tepat apa yang perlu Anda lakukan untuk **mengonversi geojson ke topojson** secara efisien.

## Jawaban Cepat
- **Perpustakaan apa yang menangani konversi?**Aspose.GIS untuk .NET
- **Berapa lama implementasinya?**Biasanya 5‑10menit untuk pengaturan dasar
- **Apakah saya memerlukan lisensi untuk produksi?**Ya, lisensi komersial diperlukan (versi percobaan gratis tersedia)
- ** menyarankan saya mengelompokkan fitur berdasarkan atribut apa pun?**Ya – atur `ObjectNameAttribute` ke bidang yang ingin Anda kelompokkan
- **Apakah .NETCore didukung?**tentu – API bekerja dengan .NETCore, .NET5/6, dan .NET Framework klasik

## Cara mengubah geojson ke topojson dengan pengelompokan di C#
Di bawah ini kami menjelaskan langkah‑langkah tepat yang perlu Anda lakukan. Prosesnya sengaja dibuat sederhana: menemukan file sumber dan tujuan, mengkonfigurasikan opsi pengelompokan, lalu membiarkan Aspose.GIS melakukan pekerjaan berat.

## Apa itu GeoJSON dan TopoJSON?

GeoJSON adalah format JSON yang banyak digunakan untuk mengkodekan fitur geografis seperti titik, garis, dan poligon. TopoJSON memperluas GeoJSON dengan menyimpan topologi (segmen garis yang berbagi) yang mengurangi ukuran file dan meningkatkan kinerja rendering untuk peta yang kompleks. Mengonversi antara keduanya adalah langkah umum ketika Anda memerlukan data peta yang ringkas untuk visualisasi web.

## Mengapa Fitur Grup GeoJSON?

Pengelompokan (`fitur geojson grup`) memungkinkan Anda mengatur geometri yang terkait di bawah satu objek bernama dalam TopoJSON yang dihasilkan. Ini sangat berguna ketika:
- Anda ingin membuat lapisan terpisah untuk wilayah administratif yang berbeda.
- Perpustakaan tata letak front‑end Anda mengharapkan objek bernama untuk pengaturan gaya atau interaksi.
- Anda perlu mengurangi duplikasi dengan berbagi batas antara fitur yang bersebelahan.

## Tetapkan atribut nama objek untuk pengelompokan

`ObjectNameAttribute` memberi tahu Aspose.GIS properti mana dalam GeoJSON sumber yang harus digunakan sebagai nama objek dalam output TopoJSON. Menetapkan atribut ini dengan benar adalah kunci keberhasilan **fitur geojson grup**.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:

1. **Aspose.GIS untuk .NET** – unduh dan instal dari situs resmi[di sini](https://releases.aspose.com/gis/net/).
2. **Lingkungan Pengembangan** – Visual Studio, VisualStudioCode, atau IDE apa pun yang mendukung C#.
3. **Contoh File GeoJSON** – file yang berisi fitur yang ingin Anda konversi.

## Impor Namespace

Pertama, sertakan namespace yang diperlukan dalam proyek Anda:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
```

## Panduan Langkah demi Langkah

### Langkah 1: Tentukan Jalur File

Tentukan di mana GeoJSON sumber berada dan ke mana TopoJSON harus ditulis:

```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithGrouping_out.topojson";
```

> **Pro tip:** Gunakan `Path.Combine` untuk membangun jalur lintas‑platform jika Anda menargetkan .NET Core.

### Langkah 2: Konfigurasi Opsi Konversi (Atur Atribut Nama Objek)

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

Ganti `"group"` dengan nama properti sebenarnya dalam GeoJSON Anda yang ingin Anda gunakan untuk **geojson feature grouping**. `DefaultObjectName` memastikan setiap fitur berakhir dalam objek TopoJSON, bahkan jika atribut tersebut tidak ada.

### Langkah 3: Lakukan Konversi (Konversi GeoJSON ke TopoJSON)

Jalankan konversi dengan satu panggilan API:

```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```

Setelah eksekusi, `convertedSampleWithGrouping_out.topojson` akan berisi representasi TopoJSON, dengan fitur yang dikelompokkan sesuai atribut yang Anda tentukan.

## Masalah Umum dan Pemecahan Masalah

| Gejala | Penyebab Kemungkinan | Perbaikan |
|---------|----------------------|-----------|
| **Semua fitur berakhir di “unnamed”** | `ObjectNameAttribute` tidak cocok dengan properti apa pun dalam GeoJSON | Verifikasi nama properti yang tepat (case‑sensitive) dan perbarui opsi |
| **Keluaran file kosong** | Jalur file tidak tepat atau izin baca tidak ada | Gunakan jalur absolut atau pastikan aplikasi memiliki akses sistem file |
| **Konversi pelemparan `NotSupportedException`** | Mencoba mengonversi GeoJSON dengan tipe geometri yang tidak didukung (mis., GeometryCollection) | Sederhanakan sumber data atau tingkatkan ke versi Aspose.GIS terbaru |

## C# praktik terbaik konversi GeoJSON

- **Validasi sumber GeoJSON** sebelum konversi untuk menangkap atribut yang hilang lebih awal.
- **Gunakan `Path.Combine`** untuk jalur file guna menghindari masalah batasan yang spesifik platform.
- **Bungkus pemanggilan konversi dalam blok try‑catch** untuk menangani kesalahan I/O secara elegan.
- **Kata kejadian `DefaultObjectName`**; ini dapat menunjukkan masalah kualitas data yang mungkin ingin Anda perbaiki di hulu.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya mengelompokkan fitur berdasarkan beberapa atribut?**
A: Ya, Anda dapat menggabungkan beberapa bidang menjadi satu atribut virtual atau menjalankan beberapa proses konversi dengan nilai `ObjectNameAttribute` yang berbeda.

**Q: Apakah Aspose.GIS kompatibel dengan ASP.NET Core?**
A: Tentu – perpustakaan ini bekerja dengan ASP.NETCore, .NET5, .NET6, dan .NET Framework klasik.

**Q: Bisakah saya mengonversi format geografis lain selain GeoJSON?**
A: Ya, Aspose.GIS mendukung Shapefile, KML, GML, CSV, dan banyak format lainnya untuk impor maupun ekspor.

**Q: Apakah Aspose.GIS menawarkan versi percobaan gratis?**
A: Ya, Anda dapat mendapatkan versi percobaan gratis Aspose.GIS dari [di sini](https://releases.aspose.com/).

**Q: Di mana saya bisa mendapatkan dukungan untuk Aspose.GIS?**
A: Anda bisa mendapatkan dukungan dari forum komunitas Aspose.GIS [di sini](https://forum.aspose.com/c/gis/33).

## Kesimpulan

Anda kini memiliki resep lengkap yang siap produksi untuk **mengonversi geojson ke topojson** dengan pengelompokan fitur menggunakan Aspose.GIS untuk .NET. Dengan mengatur `ObjectNameAttribute`, Anda mengontrol cara fitur diorganisir, yang menyederhanakan penataan gaya dan interaksi di peta web. Jangan ragu untuk menjelajahi driver lain, bereksperimen dengan atribut pengelompokan yang berbeda, dan mengintegrasikan konversi ini ke dalam pipeline GIS yang lebih besar.

---

**Terakhir Diperbarui:** 2026-02-05  
**Diuji Dengan:** Aspose.GIS for .NET (rilis terbaru)  
**Penulis:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
