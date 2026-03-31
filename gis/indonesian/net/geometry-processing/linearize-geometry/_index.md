---
date: 2025-12-21
description: Pelajari cara melinierkan geometri dengan Aspose.GIS untuk .NET, memungkinkan
  pemrosesan data geospasial yang efisien, analisis spasial, dan manipulasi geometri
  dalam aplikasi .NET Anda.
linktitle: Linearize a Geometry
second_title: Aspose.GIS .NET API
title: Cara Melinierkan Geometri Menggunakan Aspose.GIS untuk .NET
url: /id/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Linearisasikan Geometri

## Perkenalan
Jika Anda memerlukan **cara linierisasi geometri** untuk pemetaan, analisis spasial, atau tugas pertukaran data, Aspose.GIS untuk .NET memberikan cara yang bersih dan terprogram untuk melakukannya. Dalam tutorial ini kami akan membahas contoh dunia nyata yang lengkap yang menunjukkan cara mengambil geometri kompleks—yang berisi kurva dan bentuk majemuk—dan mengubahnya menjadi representasi linier sederhana yang dapat bekerja dengan sistem GIS apa pun.

## Jawaban Cepat
- **Apa arti linierisasi geometri?** Mengonversi kurva dan bentuk kompleks menjadi segmen‑segmen garis lurus.
- **Mengapa menggunakan Aspose.GIS?** Ia mendukung puluhan format GIS dan menangani konversi geometri tanpa alat eksternal.
- **Prasyarat?** .NET Framework atau .NET Core, Visual Studio, dan pustaka Aspose.GIS.
- **Berapa lama contoh ini dijalankan?** Kurang dari lima menit setelah pustaka terpasang.
- ** ingin saya menyimpan ke format lain?** Ya—ganti driver KML dengan Shapefile, GeoJSON, dll.

## Apa itu Geometri Linearisasi?
Linearisasi geometri berarti memecah setiap bentuk lengkung atau komposit menjadi serangkaian garis lurus (sebuah “geometri linier”). Hal ini menunjukkan rendering, analisis, dan interoperabilitas dengan alat yang hanya memahami garis dan titik.

## Mengapa Linearisasi Geometri?
- **Performa:** Geometri linear lebih cepat dirender dan diquery.
- **Kompatibilitas:** Banyak platform GIS (misalnya layanan peta lama) hanya menerima fitur linear.
- **Penyederhanaan:** Berguna untuk membuat thumbnail, memuaskan dengan cepat, atau memberi data ke algoritma yang memerlukan input linier.

## Prasyarat
Sebelum menyelam ke kode, pastikan Anda memiliki:

1. **Aspose.GIS untuk .NET** – unduh dari [situs Aspose.GIS](https://releases.aspose.com/gis/net/).
2. **.NET Framework** (atau .NET Core) terpasang di mesin pengembangan Anda.
3. **Visual Studio** (atau IDE yang kompatibel dengan C# apa pun) untuk menulis dan mengeksekusi contoh.

## Impor Namespace
Untuk mulai menggunakan fungsionalitas Aspose.GIS, impor namespace yang diperlukan.

### Langkah 1: Impor Namespace Inti Aspose.GIS
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Langkah 2: Impor Driver untuk Format Target Anda
Untuk contoh ini kami akan menulis hasil ke file KML:
```csharp
using Aspose.GIS.Kml;
```

## Cara Melinearisasi Geometri – Panduan Langkah demi Langkah
Berikut adalah penjelasan terperinci setiap baris kode, menjelaskan **cara linierisasi geometri** dan mengapa setiap langkah penting.

### Langkah 1: Tentukan Jalur Keluaran
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
Ganti `"Your Document Directory"` dengan folder tempat Anda ingin menyimpan file KML.

### Langkah 2: Buat Layer untuk File Output
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```
*Layer* adalah wadah untuk fitur geografis. Di sini kami membuat layer KML baru yang akan menampung geometri yang telah dilinearize.

### Langkah 3: Buat Fitur Baru
```csharp
var feature = layer.ConstructFeature();
```
*Feature* mewakili satu objek geografis (titik, garis, poligon, dll.). Kami akan melampirkan geometri linear kami ke fitur ini.

### Langkah 4: Definisikan Geometri Kompleks Asli
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```
Kami membuat geometri dari string Well‑Known Text (WKT). Contoh ini mencakup `LineString`, `CompoundCurve`, dan `CircularString`—sempurna untuk mendemonstrasikan linearization.

### Langkah 5: Linearisasi Geometri
```csharp
var linear = geometry.ToLinearGeometry();
```
Metode `ToLinearGeometry()` mengubah semua kurva menjadi segmen garis lurus, menghasilkan versi *linear* dari geometri asli.

### Langkah 6: Tetapkan Geometri Linear ke Fitur
```csharp
feature.Geometry = linear;
```
Sekarang fitur memuat geometri linear yang telah disederhanakan.

### Langkah 7: Tambahkan Fitur ke Layer
```csharp
layer.Add(feature);
```
Akhirnya, kami menambahkan fitur ke layer KML, yang menulis geometri linear ke file output ketika blok `using` selesai.

## Kesalahan & Tip Umum
- **Pemisah jalur:** Gunakan `Path.Combine` untuk membangun jalur lintas‑platform.
- **Geometri besar:** Linearisasi bentuk yang sangat kompleks dapat menghasilkan banyak titik; Fokus menggunakan `Simplify()` setelah linearisasi jika Anda memerlukan titik lebih sedikit.
- **Pilihan driver:** Jika Anda memerlukan format output lain, ganti `Drivers.Kml` dengan `Drivers.Shapefile`, `Drivers.GeoJson`, dll., dan sesuaikan ekstensi file yang bersangkutan.

##Kesimpulan
Dalam tutorial ini kami membahas **cara linierisasi geometri** menggunakan Aspose.GIS untuk .NET, mulai dari menyiapkan lingkungan hingga menulis hasil yang telah dilinearisasi ke file KML.

## FAQ
### T: Apakah Aspose.GIS untuk .NET kompatibel dengan .NET Core?
Ya, Aspose.GIS untuk .NET kompatibel dengan .NET Core, memungkinkan Anda membangun aplikasi lintas‑platform.

### Q: Bisakah saya bekerja dengan format file GIS yang berbeda menggunakan Aspose.GIS untuk .NET?
Tentu saja! Aspose.GIS mendukung berbagai format file GIS, termasuk KML, Shapefile, GeoJSON, dan lainnya.

### Q: Apakah Aspose.GIS menawarkan dukungan untuk operasi spasial dan analisis?
Ya, Aspose.GIS menyediakan beragam operasi spasial dan analisis kemampuan untuk menangani tugas geospasial yang kompleks.

### Q: Apakah ada percobaan gratis untuk Aspose.GIS untuk .NET?
Ya, Anda dapat mengunduh percobaan gratis dari [situs Aspose](https://releases.aspose.com/).

### Q: Di mana saya dapat menemukan bantuan dan dukungan untuk Aspose.GIS?
Anda dapat mengunjungi [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) untuk mendapatkan bantuan dari komunitas dan staf dukungan Aspose.

## Pertanyaan Umum (Tambahan)

**Q: Bisakah saya linierisasi geometri yang mengandung koordinat 3D (Z)?**
A: Ya, `ToLinearGeometry()` bekerja dengan geometri 2D dan 3D; nilai Z dipertahankan dalam segmen garis yang dihasilkan.

**Q: Bagaimana linearisasi mempengaruhi ukuran output file?**
A: Mengonversi kurva menjadi banyak segmen garis pendek dapat meningkatkan ukuran file. Gunakan `Simplify()` setelah linearisasi jika ukuran file menjadi perhatian.

**Q: Apakah memungkinkan mengontrol segmen panjang saat linearisasi?**
A: Metode default menggunakan toleransi internal. Untuk segmentasi khusus, Anda dapat melakukan tessellation kurva secara manual sebelum memanggil `ToLinearGeometry()`.

---

**Terakhir Diperbarui:** 21-12-2025
**Diuji Dengan:** Aspose.GIS 24.11 untuk .NET
**Penulis:** Beranggapan  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}