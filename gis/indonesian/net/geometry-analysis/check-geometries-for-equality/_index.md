---
date: 2026-02-05
description: Pelajari cara membandingkan geometri di .NET menggunakan Aspose.GIS dan
  memeriksa kesetaraan geometri dalam aplikasi Anda.
linktitle: How to Compare Geometries for Equality
second_title: Aspose.GIS .NET API
title: Cara Membandingkan Geometri untuk Kesamaan menggunakan Aspose.GIS untuk .NET
url: /id/net/geometry-analysis/check-geometries-for-equality/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membandingkan Geometri untuk Kesetaraan menggunakan Aspose.GIS untuk .NET

## Pendahuluan
Dalam tutorial ini Anda akan menemukan **cara membandingkan geometri** dengan Aspose.GIS untuk .NET. Baik Anda sedang membangun layanan pemetaan, melakukan analisis spasial, atau sekadar perlu memverifikasi bahwa dua bentuk mewakili lokasi yang sama, mengetahui cara membandingkan geometri sangat penting. Kami akan membimbing Anda melalui contoh lengkap, end‑to‑end yang menunjukkan cara membuat, memodifikasi, dan menguji kesetaraan geometri hanya dalam beberapa baris kode C#.

## Jawaban Cepat
- **Apa arti “compare geometries”?** Ini memeriksa apakah dua objek geometrik menempati ruang yang sama, terlepas dari bagaimana mereka dibangun.  
- **Metode apa yang digunakan?** `SpatiallyEquals` dari API Aspose.GIS.  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Versi percobaan gratis dapat digunakan untuk pengujian; lisensi komersial diperlukan untuk produksi.  
- **Versi .NET yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Waktu implementasi tipikal?** Sekitar 5‑10 menit untuk pemeriksaan kesetaraan dasar.

## Apa Itu Kesetaraan Geometri?
Kesetaraan geometri (sering disebut kesetaraan spasial) berarti bahwa dua geometri mewakili kumpulan titik yang persis sama pada permukaan bumi. Dua bentuk dapat dibangun secara berbeda—sebuah MultiLineString dibandingkan dengan sebuah LineString tunggal—tetapi tetap secara spasial sama.

## Mengapa Menggunakan Aspose.GIS untuk Membandingkan Geometri?
Aspose.GIS menyediakan mesin geometri yang kuat dan berperforma tinggi yang:
- Mendukung berbagai format vektor (WKT, GeoJSON, Shapefile, dll.).
- Menawarkan metode perbandingan yang memperhatikan presisi seperti `SpatiallyEquals`.
- Bekerja secara offline, tanpa layanan eksternal, menjadikannya ideal untuk lingkungan yang aman atau terisolasi.

### Mengapa ini penting bagi pengembang
Ketika Anda perlu **cara membandingkan geometri** dalam proses batch, rutinitas deteksi duplikat, atau validasi waktu nyata, sebuah perpustakaan yang dapat diandalkan menghilangkan dugaan dan menjamin hasil yang konsisten di berbagai sumber data.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki hal berikut:

- **.NET Framework atau .NET Core terinstal** – versi apa pun yang didukung oleh Aspose.GIS.
- **Perpustakaan Aspose.GIS untuk .NET** – unduh dari [halaman unduhan Aspose.GIS](https://releases.aspose.com/gis/net/).
- **IDE pengembangan** – Visual Studio, Rider, atau VS Code dengan ekstensi C#.

## Impor Namespace
Dalam proyek .NET Anda, tambahkan pernyataan `using` yang diperlukan agar kompilator mengetahui di mana menemukan kelas GIS:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Langkah 1: Definisikan Geometri
Pertama, kita membuat dua geometri yang akan dibandingkan. Dalam contoh ini `geometry1` adalah sebuah `MultiLineString` yang terdiri dari dua segmen garis, sementara `geometry2` adalah sebuah `LineString` tunggal yang mencakup titik awal dan akhir yang sama.

```csharp
var geometry1 = new MultiLineString
{
    new LineString(new [] { new Point(0, 0), new Point(1, 1) }),
    new LineString(new [] { new Point(1, 1), new Point(2, 2) }),
};
var geometry2 = new LineString(new[]
{
    new Point(0, 0), new Point(2, 2),
});
```

## Langkah 2: Periksa Kesetaraan Geometri
Sekarang kita menggunakan metode `SpatiallyEquals` untuk melihat apakah dua bentuk dianggap sama oleh mesin GIS.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // True
```

Konsol mencetak `True` karena, meskipun konstruksi berbeda, kedua geometri menutupi garis yang sama dari (0,0) hingga (2,2).

## Langkah 3: Modifikasi Salah Satu Geometri
Untuk mengilustrasikan bagaimana perubahan memengaruhi kesetaraan, kami menambahkan satu titik ekstra ke `geometry2`.

```csharp
geometry2.AddPoint(3, 3);
```

## Langkah 4: Periksa Kembali Kesetaraan Setelah Modifikasi
Setelah modifikasi, geometri tidak lagi sama, sehingga `SpatiallyEquals` mengembalikan `False`.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // False
```

Output `False` mengonfirmasi bahwa titik tambahan memutuskan kesetaraan spasial.

## Masalah Umum & Tips
- **Masalah presisi** – Jika Anda bekerja dengan koordinat yang sangat presisi, pertimbangkan untuk membulatkan atau menggunakan overload toleransi dari `SpatiallyEquals`.  
- **SRID yang berbeda** – Pastikan kedua geometri memiliki Spatial Reference System Identifier (SRID) yang sama sebelum dibandingkan.  
- **Kinerja** – Untuk koleksi besar, perbandingan batch menggunakan LINQ dapat mengurangi beban.

## Pertanyaan yang Sering Diajukan
**Q: Bisakah saya menggunakan Aspose.GIS untuk .NET dengan kerangka kerja .NET lainnya?**  
A: Ya, Aspose.GIS bekerja dengan proyek .NET Framework, .NET Core, dan .NET Standard.

**Q: Apakah tersedia versi percobaan gratis?**  
A: Tentu saja. Unduh percobaan dari [halaman rilis Aspose.GIS](https://releases.aspose.com/).

**Q: Di mana saya dapat menemukan dokumentasi API lengkap?**  
A: Dokumentasi detail tersedia di [halaman dokumentasi Aspose.GIS](https://reference.aspose.com/gis/net/).

**Q: Bagaimana cara mendapatkan bantuan jika saya mengalami masalah?**  
A: Ajukan pertanyaan Anda di forum komunitas Aspose.GIS [di sini](https://forum.aspose.com/c/gis/33).

**Q: Bisakah saya membeli lisensi sementara untuk evaluasi?**  
A: Ya, lisensi sementara tersedia di [halaman pembelian](https://purchase.aspose.com/temporary-license/).

## Kesimpulan
Anda kini mengetahui **cara membandingkan geometri** menggunakan Aspose.GIS untuk .NET, mulai dari membuat objek hingga memeriksa kesetaraan spasial dan menangani modifikasi. Kemampuan ini merupakan blok bangunan untuk analisis spasial yang lebih maju seperti validasi topologi, deteksi duplikat, dan penyaringan berbasis geometri.

---

**Last Updated:** 2026-02-05  
**Tested With:** Aspose.GIS for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}