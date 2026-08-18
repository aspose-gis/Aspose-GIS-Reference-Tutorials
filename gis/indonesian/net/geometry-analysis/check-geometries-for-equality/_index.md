---
date: 2026-06-05
description: Pelajari cara membandingkan geometries di .NET menggunakan Aspose.GIS,
  mendeteksi duplicate geometries, dan memeriksa geometry equality dalam aplikasi
  Anda.
keywords:
- how to compare geometries
- detect duplicate geometries
- Aspose.GIS geometry equality
linktitle: Cara Membandingkan Geometries untuk Equality
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to compare geometries in .NET using Aspose.GIS, detect duplicate
    geometries, and check geometry equality in your applications.
  headline: How to Compare Geometries for Equality using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS works with .NET Framework, .NET Core, and .NET Standard
      projects.
    question: Can I use Aspose.GIS for .NET with other .NET frameworks?
  - answer: Absolutely. Download a trial from the [Aspose.GIS releases page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Detailed docs are on the [Aspose.GIS documentation page](https://reference.aspose.com/gis/net/).
    question: Where can I find the full API documentation?
  - answer: Post your question on the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How do I get help if I run into an issue?
  - answer: Yes, temporary licenses are available on the [purchase page](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Cara Membandingkan Geometries untuk Equality menggunakan Aspose.GIS untuk .NET
url: /id/net/geometry-analysis/check-geometries-for-equality/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membandingkan Geometri untuk Kesetaraan menggunakan Aspose.GIS untuk .NET

## Pendahuluan
Dalam tutorial ini Anda akan belajar **cara membandingkan geometri** dengan Aspose.GIS untuk .NET, sebuah tugas yang penting ketika Anda perlu mendeteksi geometri duplikat, memvalidasi data spasial, atau menegakkan aturan topologi. Baik Anda sedang membangun layanan pemetaan, menjalankan analisis spasial batch, atau sekadar memverifikasi bahwa dua bentuk berada di lokasi yang sama, panduan ini akan memandu Anda melalui pembuatan, modifikasi, dan pengujian kesetaraan geometri dengan kode C# yang bersih dan siap produksi.

## Jawaban Cepat
- **Apa arti “compare geometries”?** Ini memeriksa apakah dua objek geometrik menempati ruang yang sama, terlepas dari bagaimana mereka dibangun.  
- **Metode apa yang digunakan?** `SpatiallyEquals` from the Aspose.GIS API.  
- **Apakah saya membutuhkan lisensi untuk pengembangan?** A free trial works for testing; a commercial license is required for production.  
- **Versi .NET yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Waktu implementasi tipikal?** About 5‑10 minutes for a basic equality check.

## Apa itu Kesetaraan Geometri?
Kesetaraan geometri, juga disebut kesetaraan spasial, berarti bahwa dua geometri mewakili kumpulan titik yang persis sama pada permukaan bumi. Bahkan jika satu geometri dibangun sebagai `MultiLineString` dan yang lainnya sebagai `LineString` tunggal, mereka dianggap sama ketika setiap koordinat cocok dalam toleransi yang ditentukan. Definisi ini memungkinkan pengembang mendeteksi geometri duplikat secara andal di berbagai sumber data yang heterogen.

## Mengapa Menggunakan Aspose.GIS untuk Membandingkan Geometri?
Aspose.GIS menawarkan mesin geometri offline dengan kinerja tinggi yang menghilangkan kebutuhan akan layanan eksternal. Ia **mendukung lebih dari 30 format vektor dan raster** (termasuk WKT, GeoJSON, Shapefile, KML, GML) dan dapat memproses file dengan **ratusan ribu simpul** sambil menjaga penggunaan memori di bawah 50 MB. Metode `SpatiallyEquals` dalam pustaka ini sadar akan presisi, memberikan hasil deterministik bahkan dengan koordinat floating‑point.

### Mengapa ini penting bagi pengembang
Ketika Anda perlu **mendeteksi geometri duplikat** dalam proses batch, pipeline validasi waktu nyata, atau migrasi data GIS, sebuah pustaka yang terbukti menghilangkan tebakan dan menjamin hasil yang konsisten di berbagai penyedia data.

## Prasyarat
- **.NET Framework atau .NET Core terinstal** – versi apa pun yang didukung oleh Aspose.GIS.  
- **Pustaka Aspose.GIS untuk .NET** – unduh dari [Aspose.GIS download page](https://releases.aspose.com/gis/net/).  
- **IDE pengembangan** – Visual Studio, Rider, atau VS Code dengan ekstensi C#.

## Impor Namespace
Dalam proyek .NET Anda, tambahkan pernyataan `using` yang diperlukan sehingga kompilator tahu di mana menemukan kelas GIS:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Langkah 1: Definisikan Geometri
`MultiLineString` mewakili kumpulan komponen garis, sementara `LineString` mendefinisikan satu garis kontinu. Kedua kelas mewarisi dari tipe dasar `Geometry`.

Pertama, kita membuat dua geometri yang akan dibandingkan. Dalam contoh ini `geometry1` adalah `MultiLineString` yang terdiri dari dua segmen garis, sementara `geometry2` adalah `LineString` tunggal yang mencakup titik awal dan akhir yang sama.

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
`SpatiallyEquals` mengevaluasi apakah dua geometri menempati kumpulan titik yang sama, secara opsional menerima nilai toleransi untuk ketidakakuratan floating‑point.

Sekarang kita menggunakan metode `SpatiallyEquals` untuk melihat apakah dua bentuk dianggap sama oleh mesin GIS.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // True
```

Konsol mencetak `True` karena, meskipun konstruksi berbeda, kedua geometri menutupi garis yang sama dari (0,0) ke (2,2).

## Langkah 3: Modifikasi Salah Satu Geometri
Untuk menggambarkan bagaimana perubahan memengaruhi kesetaraan, kami menambahkan satu titik ekstra ke `geometry2`.

```csharp
geometry2.AddPoint(3, 3);
```

## Langkah 4: Periksa Kembali Kesetaraan Setelah Modifikasi
Setelah modifikasi, geometri tidak lagi sama, sehingga `SpatiallyEquals` mengembalikan `False`.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // False
```

Output `False` mengkonfirmasi bahwa titik tambahan memutuskan kesetaraan spasial.

## Bagaimana Mendeteksi Geometri Duplikat?
Muat setiap geometri, panggil `SpatiallyEquals` dengan toleransi yang sesuai, dan saring yang mengembalikan `True`. Pola ini skalabel dengan baik menggunakan LINQ, memungkinkan Anda mengidentifikasi bentuk duplikat dalam koleksi besar dengan hanya beberapa baris kode. Anda juga dapat menggabungkannya dengan `GroupBy` untuk mengagregasi geometri yang identik dan mengurangi biaya penyimpanan.

## Masalah Umum & Tips
- **Masalah presisi** – Jika Anda bekerja dengan koordinat yang sangat presisi, pertimbangkan pembulatan atau menggunakan overload toleransi dari `SpatiallyEquals`.  
- **SRID yang berbeda** – Pastikan kedua geometri memiliki Spatial Reference System Identifier (SRID) yang sama sebelum dibandingkan.  
- **Kinerja** – Untuk koleksi besar, perbandingan batch menggunakan LINQ atau loop paralel dapat mengurangi beban secara dramatis.

## Pertanyaan yang Sering Diajukan
**Q: Bisakah saya menggunakan Aspose.GIS untuk .NET dengan kerangka kerja .NET lainnya?**  
A: Ya, Aspose.GIS bekerja dengan proyek .NET Framework, .NET Core, dan .NET Standard.

**Q: Apakah tersedia versi percobaan gratis?**  
A: Tentu saja. Unduh percobaan dari [Aspose.GIS releases page](https://releases.aspose.com/).

**Q: Di mana saya dapat menemukan dokumentasi API lengkap?**  
A: Dokumentasi detail ada di [Aspose.GIS documentation page](https://reference.aspose.com/gis/net/).

**Q: Bagaimana saya mendapatkan bantuan jika saya mengalami masalah?**  
A: Posting pertanyaan Anda di forum komunitas Aspose.GIS [di sini](https://forum.aspose.com/c/gis/33).

**Q: Bisakah saya membeli lisensi sementara untuk evaluasi?**  
A: Ya, lisensi sementara tersedia di [purchase page](https://purchase.aspose.com/temporary-license/).

## Kesimpulan
Anda kini tahu **cara membandingkan geometri** menggunakan Aspose.GIS untuk .NET, mulai dari membuat objek hingga memeriksa kesetaraan spasial dan menangani modifikasi. Kemampuan ini merupakan blok bangunan untuk analisis spasial yang lebih maju seperti validasi topologi, deteksi duplikat, dan penyaringan berbasis geometri.

---

**Terakhir Diperbarui:** 2026-06-05  
**Diuji Dengan:** Aspose.GIS for .NET 24.11  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Buat Geometri Poligon C# dan Periksa Interseksi dengan Aspose.GIS untuk .NET](/gis/net/geometry-analysis/check-geometries-intersection/)
- [Cara Melakukan Analisis Overlap Spasial Geometri dengan Aspose.GIS untuk .NET](/gis/net/geometry-analysis/check-geometries-overlap/)
- [Pemeriksaan Routing Jaringan: Geometri yang Menyentuh dengan Aspose.GIS](/gis/net/geometry-analysis/check-geometries-touching/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}