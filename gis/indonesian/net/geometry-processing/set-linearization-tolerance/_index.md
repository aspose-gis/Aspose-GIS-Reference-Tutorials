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

# Buat Vector Layer dan Atur Linearization Tolerance menggunakan Aspose.GIS untuk .NET

## Introduction
Jika Anda perlu **create vector layer** file, mengontrol presisi kurva, dan mengekspor hasil sebagai dokumen GeoJSON, Aspose.GIS untuk .NET mempermudahnya. Dalam tutorial ini Anda akan belajar cara mengonfigurasi opsi GeoJSON, mengatur toleransi linearization, dan **add feature to layer** objek—semua sambil menjaga kode tetap bersih dan siap produksi.

## Quick Answers
- **What does “create vector layer” mean?** Itu membuat dataset vektor GIS baru (misalnya file GeoJSON) yang dapat menyimpan geometri dan atribut.  
- **How to set tolerance?** Gunakan properti `LinearizationTolerance` dari `GeoJsonOptions`.  
- **Can I export a GeoJSON file?** Ya—cukup buat `VectorLayer` dengan driver `Drivers.GeoJson`.  
- **Do I need a license?** Lisensi Aspose.GIS yang valid membuka semua fitur; lisensi sementara dapat digunakan untuk evaluasi.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## What is “create vector layer”?
Membuat vector layer berarti menginisialisasi kontainer GIS baru (seperti file GeoJSON) yang dapat menampung fitur geometris seperti titik, garis, dan poligon. Layer ini menjadi target untuk setiap geometri yang Anda buat dan setiap atribut yang Anda lampirkan.

## Why configure GeoJSON options?
Mengonfigurasi opsi GeoJSON—terutama **linearization tolerance**—memastikan bahwa geometri melengkung (misalnya `CircularString`) diaproksimasi dengan presisi yang memenuhi kebutuhan akurasi aplikasi Anda. Langkah ini penting ketika Anda kemudian **export GeoJSON file** untuk digunakan dalam peta web atau analisis spasial.

## Prerequisites
Sebelum memulai, pastikan Anda memiliki:

1. **Visual Studio** terinstal (versi terbaru apa pun).  
2. **Lisensi Aspose.GIS** (atau kunci evaluasi sementara).  
3. Pustaka **Aspose.GIS for .NET** diunduh dan direferensikan dalam proyek Anda.  
4. Pemahaman dasar tentang **C#**.

## Import Namespaces
First, import the required namespaces so the compiler knows where to find the GIS classes:

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

## Step‑by‑Step Guide

### Step 1: Configure GeoJSON Options (how to set tolerance)
Kita akan membuat objek `GeoJsonOptions` dan memberi tahu Aspose.GIS seberapa dekat geometri yang dilineariskan harus dengan kurva asli.

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### Step 2: Define the Output Path (how to export GeoJSON)
Tentukan di mana file hasil akan disimpan. Ganti placeholder dengan folder Anda yang sebenarnya.

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### Step 3: **Create Vector Layer** with the configured options
Sekarang kita benar-benar **create vector layer** menggunakan metode `VectorLayer.Create`. Blok `using` menjamin pembuangan sumber daya yang tepat.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### Step 4: Construct a Geometry (e.g., a circular string)
Di sini kami membangun contoh geometri—sebuah `CircularString`. Anda dapat menggantinya dengan WKT yang valid apa pun.

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### Step 5: **Add Feature to Layer** and save
Akhirnya, kami membuat fitur, menetapkan geometri, dan menambahkannya ke layer. Ini adalah inti dari operasi **add feature to layer**.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

Saat blok `using` berakhir, layer secara otomatis ditulis ke file yang ditentukan dalam `path`, memberikan Anda file GeoJSON siap pakai.

## Common Issues & Tips
- **Path tidak benar** – Pastikan direktori ada dan Anda memiliki izin menulis.  
- **Toleransi terlalu rendah** – Menetapkan `LinearizationTolerance` ke nilai sangat kecil dapat meningkatkan ukuran file secara dramatis. Sesuaikan berdasarkan kebutuhan akurasi Anda.  
- **Kesalahan lisensi** – Jika Anda melihat peringatan lisensi, pastikan file lisensi dimuat dengan benar sebelum panggilan Aspose.GIS apa pun.

## Frequently Asked Questions

**Q: Apakah Aspose.GIS untuk .NET kompatibel dengan kerangka kerja .NET lainnya?**  
A: Ya, ia bekerja dengan .NET Framework, .NET Core, dan .NET 5/6/7.

**Q: Bisakah saya menggunakan Aspose.GIS dalam proyek komersial?**  
A: Tentu saja. Lisensi komersial menghapus semua pembatasan evaluasi.

**Q: Apakah Aspose.GIS mendukung format GIS lain selain GeoJSON?**  
A: Ya, ia mendukung Shapefile, KML, GML, dan banyak lagi.

**Q: Apakah ada versi percobaan yang tersedia?**  
A: Anda dapat mengunduh percobaan gratis dari situs web Aspose.

**Q: Di mana saya dapat mendapatkan dukungan?**  
A: Gunakan forum Aspose atau tautan dukungan di bagian sumber daya.

## Conclusion
Dengan mengikuti langkah‑langkah ini Anda kini tahu cara **create vector layer**, mengonfigurasi linearization tolerance, dan **add feature to layer** untuk pembuatan **export GeoJSON file** yang mulus. Jelajahi tipe geometri tambahan dan penanganan atribut untuk memanfaatkan sepenuhnya Aspose.GIS dalam proyek .NET GIS Anda.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose