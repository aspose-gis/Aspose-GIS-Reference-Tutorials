---
date: 2026-03-29
description: Pelajari cara membuat geometri multipolygon dan menambahkan poligon ke
  multipolygon menggunakan Aspose.GIS untuk .NET. Panduan langkah demi langkah dengan
  percobaan gratis.
linktitle: Create MultiPolygon Geometry
second_title: Aspose.GIS .NET API
title: Cara Membuat Geometri MultiPolygon dengan Aspose.GIS
url: /id/net/geometry-creation/create-multipolygon-geometry/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membuat Geometri MultiPolygon dengan Aspose.GIS

## Pendahuluan
Jika Anda mencari **cara membuat multipolygon** dalam lingkungan .NET, Anda berada di tempat yang tepat. Aspose.GIS untuk .NET memberi Anda API bersih yang berorientasi objek untuk membangun objek geospasial yang kompleks, dan tutorial ini memandu Anda melalui setiap langkah—dari menginstal perpustakaan hingga menggabungkan poligon individu menjadi satu MultiPolygon. Pada akhir tutorial, Anda akan dapat **menambahkan poligon ke multipolygon** dengan percaya diri.

## Jawaban Cepat
- **Apa itu MultiPolygon?** Geometri yang mengelompokkan dua atau lebih objek Polygon menjadi satu koleksi.  
- **Mengapa menggunakan Aspose.GIS?** Mendukung banyak format GIS, bekerja pada .NET Framework dan .NET Core, dan tidak memerlukan pustaka native eksternal.  
- **Berapa lama contoh ini memakan waktu?** Sekitar 5 menit untuk mengetik dan menjalankannya.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Versi .NET mana yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Apa itu Geometri MultiPolygon?
MultiPolygon adalah geometri komposit yang berisi beberapa objek Polygon, masing‑masing mungkin memiliki cincin interior (lubang) sendiri. Struktur ini ideal untuk merepresentasikan bidang tanah yang terpisah, pulau, atau kumpulan area terpisah yang memiliki atribut bersama.

## Mengapa Menambahkan Poligon ke MultiPolygon?
Menambahkan poligon ke MultiPolygon memungkinkan Anda memperlakukan beberapa bentuk independen sebagai satu entitas. Ini menyederhanakan kueri spasial, rendering, dan pertukaran data karena Anda dapat menyimpan, mentransfer, dan memanipulasi seluruh koleksi dengan satu objek alih‑alih menangani setiap poligon secara terpisah.

## Prasyarat
Sebelum menyelam ke kode, pastikan Anda memiliki hal‑hal berikut:

- **Aspose.GIS untuk .NET** terinstal (lihat langkah‑langkah di bawah).  
- Lingkungan pengembangan .NET (Visual Studio, VS Code, atau IDE apa pun yang Anda sukai).  
- Familiaritas dasar dengan sintaks C#.

### Menginstal Aspose.GIS untuk .NET
1. Download Aspose.GIS: Kunjungi [download page](https://releases.aspose.com/gis/net/) dan pilih versi yang sesuai untuk lingkungan pengembangan Anda.  
2. Install Aspose.GIS: Ikuti petunjuk instalasi yang disediakan dalam dokumentasi untuk menginstal Aspose.GIS untuk .NET di mesin Anda.

## Mengimpor Namespace
Untuk mulai bekerja dengan Aspose.GIS dalam proyek .NET Anda, impor namespace yang diperlukan:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Langkah 1: Membuat Linear Ring
Pertama, kita perlu membuat objek **LinearRing** untuk setiap poligon. LinearRing adalah rangkaian garis tertutup yang mendefinisikan batas luar (dan secara opsional lubang dalam) sebuah poligon.

```csharp
LinearRing firstRing = new LinearRing();
firstRing.AddPoint(8.5, -2.5);
firstRing.AddPoint(-8.5, 2.5);
firstRing.AddPoint(8.5, -2.5);
LinearRing secondRing = new LinearRing();
secondRing.AddPoint(7.6, -3.6);
secondRing.AddPoint(-9.6, 1.5);
secondRing.AddPoint(7.6, -3.6);
```

## Langkah 2: Membuat Poligon
Selanjutnya, kita mengubah setiap LinearRing menjadi objek **Polygon**. Poligon‑poligon ini nantinya akan ditambahkan ke MultiPolygon.

```csharp
Polygon firstPolygon = new Polygon(firstRing);
Polygon secondPolygon = new Polygon(secondRing);
```

## Langkah 3: Membuat MultiPolygon
Sekarang, mari gabungkan poligon‑poligon menjadi satu geometri **MultiPolygon**. Di sinilah kita **menambahkan poligon ke multipolygon**.

```csharp
MultiPolygon multiPolygon = new MultiPolygon();
multiPolygon.Add(firstPolygon);
multiPolygon.Add(secondPolygon);
```

Selamat! Anda telah berhasil membuat geometri MultiPolygon menggunakan Aspose.GIS untuk .NET.

## Masalah Umum dan Solusinya
| Masalah | Penyebab | Solusi |
|-------|-------|-----|
| **Titik tidak menutup cincin** | Titik pertama dan terakhir berbeda. | Pastikan koordinat pertama dan terakhir identik; Aspose.GIS secara otomatis menutup cincin, tetapi penutupan eksplisit menghindari kebingungan. |
| **Urutan koordinat tidak tepat (X, Y vs. Lon, Lat)** | Mencampur longitude dan latitude. | Gunakan urutan (X, Y) yang dipakai oleh Aspose.GIS; X = longitude, Y = latitude. |
| **Perpustakaan tidak ditemukan saat runtime** | Referensi NuGet atau DLL yang hilang. | Pastikan paket Aspose.GIS direferensikan dalam file proyek Anda dan DLL disalin ke folder output. |

## Pertanyaan yang Sering Diajukan

**Q: Apakah Aspose.GIS untuk .NET cocok untuk pemula?**  
A: Tentu saja! Aspose.GIS menawarkan dokumentasi lengkap dan tutorial untuk membantu pengembang dari semua tingkat keahlian memulai.

**Q: Bisakah saya mencoba Aspose.GIS sebelum membeli?**  
A: Ya, Anda dapat mengunduh percobaan gratis dari [sini](https://releases.aspose.com/) untuk menjelajahi fiturnya sebelum melakukan pembelian.

**Q: Di mana saya dapat menemukan dukungan untuk Aspose.GIS?**  
A: Anda dapat mengunjungi forum Aspose.GIS [di sini](https://forum.aspose.com/c/gis/33) untuk mengajukan pertanyaan dan mendapatkan bantuan dari komunitas.

**Q: Apakah ada lisensi sementara yang tersedia untuk Aspose.GIS?**  
A: Ya, Anda dapat memperoleh lisensi sementara dari [sini](https://purchase.aspose.com/temporary-license/) untuk tujuan evaluasi.

**Q: Bisakah saya membeli Aspose.GIS secara langsung?**  
A: Ya, Anda dapat membeli Aspose.GIS dari situs web [sini](https://purchase.aspose.com/buy).

---

**Terakhir Diperbarui:** 2026-03-29  
**Diuji Dengan:** Aspose.GIS 24.12 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}