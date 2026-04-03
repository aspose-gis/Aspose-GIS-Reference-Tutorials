---
date: 2026-04-03
description: Pelajari cara membuat poligon dengan geometri lubang menggunakan Aspose.GIS
  untuk .NET. Panduan ini menunjukkan cara membuat lubang dalam poligon dan bekerja
  dengan data geospasial.
keywords:
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
linktitle: Buat Poligon dengan Geometri Lubang
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
Dalam tutorial ini, Anda akan **create polygon with hole** geometri menggunakan Aspose.GIS untuk .NET. Baik Anda sedang membangun aplikasi pemetaan, melakukan analisis spasial, atau menyiapkan data untuk layanan GIS, mengetahui cara menyisipkan lubang di dalam poligon sangat penting. Kami akan membimbing Anda melalui seluruh proses langkah demi langkah, mulai dari menyiapkan lingkungan hingga menghasilkan objek poligon akhir.

## Jawaban Cepat
- **What does “create polygon with hole” mean?** Artinya membangun sebuah poligon yang berisi satu atau lebih cincin interior (lubang) yang dikecualikan dari area.  
- **Which library handles this?** Aspose.GIS untuk .NET menyediakan dukungan penuh untuk cincin eksternal dan interior.  
- **Do I need a license?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **How long does it take?** Biasanya kurang dari 10 menit untuk mengimplementasikan dan menguji.

## Cara menambahkan lubang ke poligon menggunakan Aspose.GIS
Menambahkan lubang hanyalah soal mendefinisikan **interior ring** dan melampirkannya ke poligon. Library mengurus orientasi dan validitas, sehingga Anda dapat fokus pada koordinat yang mewakili ruang kosong yang dibutuhkan.

## Apa itu “create polygon with hole”?
Membuat poligon dengan lubang melibatkan definisi **exterior ring** yang menggambarkan batas luar dan satu atau lebih **interior rings** yang mengukir ruang kosong. Cincin interior sering disebut *lubang* karena mereka mewakili area yang bukan bagian dari permukaan poligon.

## Mengapa membuat lubang dalam poligon menggunakan Aspose.GIS?
- **Accurate spatial modeling:** Fitur dunia nyata seperti danau di dalam bidang tanah atau halaman dalam bangunan memerlukan lubang.  
- **Interoperability:** Format seperti Shapefile, GeoJSON, dan GML secara native mendukung interior rings; Aspose.GIS mempertahankannya.  
- **Performance:** Library mengelola validitas geometri, sehingga Anda tidak perlu menulis kode validasi khusus.

## Skenario Dunia Nyata untuk Poligon dengan Lubang
1. **Land parcel with an internal lake** – danau dimodelkan sebagai lubang sehingga tidak dihitung dalam area bidang tanah.  
2. **Building footprints with courtyards** – halaman dikecualikan dari jejak bangunan.  
3. **Protected zones inside a larger conservation area** – Anda dapat mengecualikan bagian yang dibatasi tanpa membuat lapisan terpisah.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. Aspose.GIS for .NET Library: Anda dapat mengunduhnya dari [here](https://releases.aspose.com/gis/net/).  
2. Development Environment: Pastikan Anda memiliki lingkungan pengembangan yang terpasang dengan Visual Studio atau IDE .NET lainnya.

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
Kita mulai dengan membuat instance objek `Polygon` kosong yang nantinya akan menampung cincin eksternal dan interior.

```csharp
Polygon polygon = new Polygon();
```

## Langkah 2: Definisikan Exterior Ring
Exterior ring mendefinisikan batas luar poligon. Tambahkan titik secara berurutan searah jarum jam untuk membentuk bentuk tertutup.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## Langkah 3: Definisikan Interior Ring (Lubang)
Selanjutnya, kita membuat interior ring—ini adalah **hole** yang akan dikecualikan dari area poligon. Titik biasanya ditambahkan secara berlawanan arah jarum jam, namun Aspose.GIS menangani orientasi secara otomatis.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## Langkah 4: Tetapkan Exterior Ring dan Tambahkan Interior Ring ke Polygon
Akhirnya, lampirkan exterior ring ke poligon dan kemudian tambahkan interior ring (lubang). Metode `AddInteriorRing` dapat dipanggil berkali‑kali jika Anda membutuhkan beberapa lubang.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## Tips dan Praktik Terbaik
- **Orientation matters for readability** – meskipun Aspose.GIS secara otomatis memperbaiki orientasi, menjaga exterior rings searah jarum jam dan interior rings berlawanan arah jarum jam membuat geometri lebih mudah diperiksa di penampil GIS.  
- **Close each ring** – selalu ulangi koordinat pertama sebagai titik terakhir; ini menjamin bentuk tertutup yang valid.  
- **Validate after creation** – Anda dapat memanggil `polygon.IsValid` untuk memastikan geometri mematuhi standar OGC sebelum disimpan.

## Masalah Umum dan Solusinya
| Masalah | Alasan | Solusi |
|-------|--------|-----|
| Lubang tidak muncul di penampil GIS | Orientasi interior ring terbalik | Pastikan titik ditambahkan dalam arah berlawanan dengan exterior ring (berlawanan arah jarum jam). |
| Kesalahan poligon tidak valid | Cincin tidak tertutup (pertama ≠ titik terakhir) | Ulangi titik pertama sebagai titik terakhir di setiap cincin (seperti yang ditunjukkan di atas). |
| Geometri kosong yang tidak terduga | Lupa menetapkan `ExteriorRing` sebelum menambahkan interior rings | Set `polygon.ExteriorRing` terlebih dahulu, kemudian panggil `AddInteriorRing`. |

## Pertanyaan yang Sering Diajukan
### 1. Apa itu Aspose.GIS?
Aspose.GIS adalah library .NET yang memungkinkan pengembang bekerja dengan data geospasial, memungkinkan mereka membuat, membaca, dan memanipulasi berbagai format file geospasial.

### 2. Bisakah saya menggunakan Aspose.GIS untuk proyek komersial?
Ya, Anda dapat menggunakan Aspose.GIS untuk proyek pribadi maupun komersial dengan membeli lisensi. Kunjungi [here](https://purchase.aspose.com/buy) untuk detail lebih lanjut.

### 3. Apakah ada percobaan gratis untuk Aspose.GIS?
Ya, Anda dapat memanfaatkan percobaan gratis Aspose.GIS dari [here](https://releases.aspose.com/).

### 4. Di mana saya dapat menemukan dukungan untuk Aspose.GIS?
Anda dapat menemukan dukungan untuk Aspose.GIS di [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).

### 5. Bagaimana saya dapat memperoleh lisensi sementara untuk Aspose.GIS?
Anda dapat memperoleh lisensi sementara untuk Aspose.GIS dari [here](https://purchase.aspose.com/temporary-license/).

**Terakhir Diperbarui:** 2026-04-03  
**Diuji dengan:** Aspose.GIS 24.11 for .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}