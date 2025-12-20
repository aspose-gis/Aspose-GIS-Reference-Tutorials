---
date: 2025-12-20
description: Pelajari cara membuat poligon dengan geometri lubang menggunakan Aspose.GIS
  untuk .NET. Panduan ini menunjukkan cara membuat lubang pada poligon dan bekerja
  dengan data geospasial.
linktitle: Create Polygon with Hole Geometry
second_title: Aspose.GIS .NET API
title: Buat Poligon dengan Geometri Lubang menggunakan Aspose.GIS
url: /id/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Geometri Poligon dengan Lubang menggunakan Aspose.GIS

## Pendahuluan
Dalam tutorial ini, Anda akan **create polygon with hole** geometry menggunakan Aspose.GIS untuk .NET. Baik Anda sedang membangun aplikasi pemetaan, melakukan analisis spasial, atau menyiapkan data untuk layanan GIS, mengetahui cara menyisipkan lubang di dalam poligon sangat penting. Kami akan memandu Anda melalui seluruh proses langkah demi langkah, mulai dari menyiapkan lingkungan hingga menghasilkan objek poligon akhir.

## Jawaban Cepat
- **Apa arti “create polygon with hole”?** Artinya membuat poligon yang berisi satu atau lebih cincin interior (lubang) yang dikecualikan dari area.  
- **Perpustakaan mana yang menangani ini?** Aspose.GIS for .NET provides full support for exterior and interior rings.  
- **Apakah saya memerlukan lisensi?** A free trial works for development; a commercial license is required for production.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Berapa lama waktu yang dibutuhkan?** Typically under 10 minutes to implement and test.  

## Apa itu “create polygon with hole”?
Membuat poligon dengan lubang melibatkan definisi **exterior ring** yang menggambarkan batas luar dan satu atau lebih **interior rings** yang mengukir ruang kosong. Cincin interior sering disebut *lubang* karena mereka mewakili area yang bukan bagian dari permukaan poligon.

## Mengapa membuat lubang dalam poligon menggunakan Aspose.GIS?
- **Pemodelan spasial yang akurat:** Fitur dunia nyata seperti danau di dalam bidang tanah atau halaman dalam bangunan memerlukan lubang.  
- **Interoperabilitas:** Format seperti Shapefile, GeoJSON, dan GML secara native mendukung cincin interior; Aspose.GIS mempertahankannya.  
- **Kinerja:** Perpustakaan mengelola validitas geometri, sehingga Anda tidak perlu menulis kode validasi khusus.  

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. Aspose.GIS for .NET Library: Anda dapat mengunduhnya dari [here](https://releases.aspose.com/gis/net/).
2. Lingkungan Pengembangan: Pastikan Anda memiliki lingkungan pengembangan yang terpasang dengan Visual Studio atau IDE .NET lainnya.

## Impor Namespace
Pertama, Anda perlu mengimpor namespace yang diperlukan untuk bekerja dengan fungsionalitas Aspose.GIS. Berikut cara melakukannya:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Sekarang, mari kita lanjutkan untuk membuat geometri poligon dengan lubang menggunakan Aspose.GIS untuk .NET.

## Langkah 1: Buat Objek Polygon
Kita mulai dengan membuat instance objek `Polygon` kosong yang nantinya akan menampung baik cincin luar maupun cincin dalam.

```csharp
Polygon polygon = new Polygon();
```

## Langkah 2: Definisikan Cincin Luar
Cincin luar mendefinisikan batas luar poligon. Tambahkan titik secara berurutan searah jarum jam untuk membentuk bentuk tertutup.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## Langkah 3: Definisikan Cincin Dalam (Lubang)
Selanjutnya, kita membuat cincin dalam—ini adalah **lubang** yang akan dikecualikan dari area poligon. Titik biasanya ditambahkan secara berlawanan arah jarum jam, tetapi Aspose.GIS menangani orientasi secara otomatis.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## Langkah 4: Tetapkan Cincin Luar dan Tambahkan Cincin Dalam ke Polygon
Akhirnya, lampirkan cincin luar ke poligon dan kemudian tambahkan cincin dalam (lubang). Metode `AddInteriorRing` dapat dipanggil berkali‑kali jika Anda memerlukan beberapa lubang.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## Masalah Umum dan Solusinya
| Masalah | Alasan | Solusi |
|-------|--------|-----|
| Lubang tidak muncul di penampil GIS | Orientasi cincin dalam terbalik | Pastikan titik ditambahkan dalam arah berlawanan dengan cincin luar (berlawanan arah jarum jam). |
| Kesalahan poligon tidak valid | Cincin tidak tertutup (titik pertama ≠ titik terakhir) | Ulangi titik pertama sebagai titik terakhir pada setiap cincin (seperti yang ditunjukkan di atas). |
| Geometri kosong yang tidak terduga | Lupa menetapkan `ExteriorRing` sebelum menambahkan cincin dalam | Setel `polygon.ExteriorRing` terlebih dahulu, kemudian panggil `AddInteriorRing`. |

## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara **create polygon with hole** geometry menggunakan Aspose.GIS untuk .NET. Teknik ini penting untuk banyak skenario geospasial di mana Anda perlu merepresentasikan bentuk kompleks dengan ruang kosong di dalamnya.

## Pertanyaan yang Sering Diajukan
### 1. Apa itu Aspose.GIS?
Aspose.GIS adalah perpustakaan .NET yang memungkinkan pengembang bekerja dengan data geospasial, memungkinkan mereka membuat, membaca, dan memanipulasi berbagai format file geospasial.

### 2. Apakah saya dapat menggunakan Aspose.GIS untuk proyek komersial?
Ya, Anda dapat menggunakan Aspose.GIS untuk proyek pribadi maupun komersial dengan membeli lisensi. Kunjungi [here](https://purchase.aspose.com/buy) untuk detail lebih lanjut.

### 3. Apakah tersedia trial gratis untuk Aspose.GIS?
Ya, Anda dapat mengakses trial gratis Aspose.GIS dari [here](https://releases.aspose.com/).

### 4. Di mana saya dapat menemukan dukungan untuk Aspose.GIS?
Anda dapat menemukan dukungan untuk Aspose.GIS di [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).

### 5. Bagaimana saya dapat memperoleh lisensi sementara untuk Aspose.GIS?
Anda dapat memperoleh lisensi sementara untuk Aspose.GIS dari [here](https://purchase.aspose.com/temporary-license/).

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}