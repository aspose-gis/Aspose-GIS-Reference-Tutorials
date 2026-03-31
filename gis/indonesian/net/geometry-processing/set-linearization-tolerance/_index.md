---
date: 2025-12-21
description: Pelajari cara membuat lapisan vektor, mengatur toleransi linearitas,
  dan menambahkan fitur ke lapisan menggunakan Aspose.GIS untuk .NET. Ikuti panduan
  langkah demi langkah ini untuk mengekspor file GeoJSON.
linktitle: Set Linearization Tolerance
second_title: Aspose.GIS .NET API
title: Buat Lapisan Vektor dan Atur Toleransi Linearitas menggunakan Aspose.GIS untuk
  .NET
url: /id/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Layer Vektor dan Atur Toleransi Linierisasi menggunakan Aspose.GIS untuk .NET

## Perkenalan
Jika Anda perlu **membuat lapisan vektor** file, mengatur presisi kurva, dan mengekspor hasil sebagai dokumen GeoJSON, Aspose.GIS untuk .NET mempermudahnya. menjaga kode tetap bersih dan siap produksi.

## Jawaban Cepat
- **Apa yang dimaksud dengan “membuat lapisan vektor”?** Itu membuat dataset vektor GIS baru (misalnya file GeoJSON) yang dapat menyimpan geometri dan atribut.
- **Bagaimana cara mengatur toleransi?** Gunakan properti `LinearizationTolerance` dari `GeoJsonOptions`.
- **Dapatkah saya mengekspor file GeoJSON?** Ya—cukup membuat `VectorLayer` dengan driver `Drivers.GeoJson`.
- **Apakah saya memerlukan lisensi?** Lisensi Aspose.GIS yang valid membuka semua fitur; lisensi sementara dapat digunakan untuk evaluasi.
- **Versi .NET manakah yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Apa itu “membuat lapisan vektor”?
Membuat layer vektor berarti menginisialisasi kontainer GIS baru (seperti file GeoJSON) yang dapat menampung fitur geometris seperti titik, garis, dan poligon. Geometri yang Anda buat dan setiap atribut yang Anda lampirkan.

## Mengapa mengonfigurasi opsi GeoJSON?
Mengonfigurasi opsi GeoJSON—terutama **toleransi linierisasi**—memastikan bahwa geometri melengkung (misalnya `CircularString`) diaproksimasi dengan presisi yang memenuhi kebutuhan akurasi aplikasi Anda. Langkah ini penting ketika Anda kemudian **ekspor file GeoJSON** untuk digunakan dalam peta web atau analisis spasial.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki:

1. **Visual Studio** terinstal (versi terbaru apa pun).
2. **Lisensi Aspose.GIS** (atau kunci evaluasi sementara).
3. Pustaka **Aspose.GIS for .NET** diunduh dan direferensikan dalam proyek Anda.
4. Pemahaman dasar tentang **C#**.

## Impor Namespace
Pertama, impor namespace yang diperlukan sehingga compiler mengetahui di mana menemukan kelas GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Panduan Langkah-demi-Langkah

### Langkah 1: Konfigurasikan Opsi GeoJSON (cara mengatur toleransi)
Kita akan membuat objek `GeoJsonOptions` dan memberi tahu Aspose.GIS seberapa dekat geometri yang dilineariskan harus dengan kurva asli.

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### Langkah 2: Tentukan Jalur Output (cara mengekspor GeoJSON)
Tentukan di mana file hasil akan disimpan. Ganti placeholder dengan folder Anda yang sebenarnya.

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### Langkah 3: **Buat Layer Vektor** dengan opsi yang telah dikonfigurasi
Sekarang kita benar-benar **create vector layer** menggunakan metode `VectorLayer.Create`. Blok `using` menjamin pembuangan sumber daya yang tepat.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### Langkah 4: Buat Geometri (misalnya, tali melingkar)
Di sini kami membangun contoh geometri—sebuah `CircularString`. Anda dapat menggantinya dengan WKT yang valid apa pun.

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### Langkah 5: **Tambahkan Fitur ke Layer** dan simpan
Akhirnya, kami membuat fitur, menetapkan geometri, dan menambahkannya ke layer. Ini adalah inti dari operasi **add feature to layer**.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

Saat blok `using` berakhir, layer secara otomatis ditulis ke file yang ditentukan dalam `path`, memberikan Anda file GeoJSON siap pakai.

## Masalah & Tip Umum
- **Jalur tidak benar** – Pastikan direktori ada dan Anda memiliki izin menulis.
- **Toleransi terlalu rendah** – Menetapkan `LinearizationTolerance` ke nilai sangat kecil dapat meningkatkan ukuran file secara dramatis. Sesuaikan berdasarkan kebutuhan akurasi Anda.
- **Kesalahan lisensi** – Jika Anda melihat peringatan lisensi, pastikan file lisensi dimuat dengan benar sebelum panggilan Aspose.GIS apa pun.

## Pertanyaan yang Sering Diajukan

**Q: Apakah Aspose.GIS untuk .NET kompatibel dengan kerangka kerja .NET lainnya?**
A: Ya, saya bekerja dengan .NET Framework, .NET Core, dan .NET 5/6/7.

**Q: Bisakah saya menggunakan Aspose.GIS dalam proyek komersial?**
J: Tentu saja. Lisensi komersial menghapus semua evaluasi.

**Q: Apakah Aspose.GIS mendukung format GIS lain selain GeoJSON?**
A: Ya, ia mendukung Shapefile, KML, GML, dan banyak lagi.

**Q: Apakah ada versi percobaan yang tersedia?**
A: Anda dapat mengunduh percobaan gratis dari situs web Aspose.

**Q: Di mana saya bisa mendapatkan dukungan?**
A: Gunakan forum Aspose atau tautan dukungan di bagian sumber daya.

##Kesimpulan
Dengan mengikuti langkah‑langkah ini Anda kini mengetahui cara **membuat lapisan vektor**, mengonfigurasi toleransi linierisasi, dan **menambahkan fitur ke lapisan** untuk pembuatan **mengekspor file GeoJSON** yang mulus. Penjelajahan tipe geometritambahan dan penanganan atribut untuk memanfaatkan sepenuhnya Aspose.GIS dalam proyek .NET GIS Anda.

---

**Terakhir Diperbarui:** 21-12-2025
**Diuji Dengan:** Aspose.GIS 24.11 untuk .NET
**Penulis:** Beranggapan

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
