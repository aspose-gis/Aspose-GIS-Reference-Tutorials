---
date: 2026-08-18
description: Konversi decimal degrees ke dms menggunakan Aspose.GIS for .NET. Panduan
  langkah demi langkah C# ini menunjukkan cara mengonversi latitude/longitude, decimal
  degrees ke dms, dan lainnya.
keywords:
- decimal degrees to dms
- convert coordinates dms
- gis coordinate conversion
- convert lat long dms
- c# convert lat long
lastmod: 2026-08-18
linktitle: Konversi Koordinat
og_description: Konversi decimal degrees ke dms menjadi mudah dengan Aspose.GIS for
  .NET. Pelajari cara mengubah nilai latitude‑longitude menjadi format DMS dalam menit.
og_image_alt: Guide showing decimal degrees to DMS conversion using Aspose.GIS in
  C#
og_title: Konversi decimal degrees ke dms dengan Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  headline: How to convert decimal degrees to dms with Aspose.GIS for .NET
  type: TechArticle
- description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  name: How to convert decimal degrees to dms with Aspose.GIS for .NET
  steps:
  - name: start the conversion process
    text: We print a friendly message so you know the demo has begun.
  - name: convert to decimal degrees
    text: Even though the final goal is DMS, we start by showing the original decimal
      representation. This also demonstrates the **decimal degrees to dms** path you’ll
      later follow.
  - name: convert to degree decimal minutes
    text: This format (`DD°MM.m'`) is a common intermediate step when you need to
      **convert lat long degree minutes**.
  - name: convert to degree minutes seconds (dms)
    text: Here’s the core of our tutorial—**convert coordinates to dms**.
  - name: convert to GeoRef
    text: For completeness, we also demonstrate the `GeoRef` format, useful in remote‑sensing
      workflows.
  type: HowTo
- questions:
  - answer: Aspose.GIS primarily targets .NET developers, but a Java version is also
      available.
    question: Is Aspose.GIS compatible with other programming languages?
  - answer: Yes, you can access a free trial of Aspose.GIS from the [website](https://releases.aspose.com/).
    question: Can I try Aspose.GIS before purchasing?
  - answer: You can seek assistance from the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How can I get support for Aspose.GIS?
  - answer: Yes, temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses available for Aspose.GIS?
  - answer: You can purchase Aspose.GIS from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert coordinates
- Aspose.GIS
- .NET GIS processing
title: Cara mengonversi decimal degrees ke dms dengan Aspose.GIS for .NET
url: /id/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mengonversi derajat desimal ke dms dengan Aspose.GIS

## Pendahuluan
Dalam tutorial ini Anda akan belajar **cara mengonversi derajat desimal ke dms** menggunakan pustaka Aspose.GIS yang kuat untuk .NET. Baik Anda perlu **c# convert lat long**, menghasilkan string lokasi yang dapat dibaca manusia untuk laporan, atau sekadar menjelajahi format koordinat yang berbeda, panduan ini akan memandu Anda melalui setiap langkah dengan penjelasan yang jelas dan potongan kode C# yang siap dijalankan.

## Jawaban Cepat
- **Apa arti “convert coordinates to dms”?** Itu mengubah nilai numerik lintang/bujur menjadi notasi tradisional derajat‑menit‑detik.  
- **Pustaka mana yang menangani konversi?** Aspose.GIS untuk .NET menyediakan kelas `GeoConvert` dengan dukungan format bawaan.  
- **Apakah saya memerlukan lisensi untuk mencobanya?** Versi percobaan gratis tersedia; lisensi komersial diperlukan untuk penggunaan produksi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, dan .NET 5/6+.  
- **Bisakah saya menggunakan kode yang sama untuk format lain?** Ya—cukup ubah nilai enum `PointFormats` (misalnya, `DecimalDegrees`, `GeoRef`).  

## Apa itu konversi koordinat ke dms?
Konversi koordinat ke DMS mengubah nilai lintang dan bujur desimal menjadi format seperti `25°30'00"N 45°30'00"E`. Proses ini membagi setiap derajat desimal menjadi derajat penuh, menit (satu enam puluh derajat), dan detik (satu enam puluh menit), kemudian menambahkan indikator belahan bumi yang sesuai (N, S, E, W). Bentuk yang dapat dibaca manusia ini penting untuk banyak dataset warisan dan untuk mengkomunikasikan lokasi yang tepat tanpa bergantung pada notasi desimal.

## Mengapa menggunakan Aspose.GIS untuk konversi koordinat?
Aspose.GIS mendukung **lebih dari 50 format input dan output** dan dapat memproses file GIS berukuran ratusan halaman tanpa memuat seluruh dataset ke memori. API memberikan akurasi sub‑milimeter untuk kasus tepi seperti nilai negatif dan penanda belahan bumi, serta berjalan secara konsisten pada runtime .NET Windows, Linux, dan macOS.

## Prasyarat
Sebelum Anda memulai, pastikan Anda memiliki:

1. **Pengetahuan dasar tentang C#** – familiaritas dengan variabel, pemanggilan metode, dan output konsol.  
2. **Aspose.GIS terpasang** – unduh paket terbaru dari [Aspose.GIS website](https://releases.aspose.com/gis/net/). Anda juga dapat menjelajahi situs rilis utama Aspose di [Aspose releases website](https://releases.aspose.com/).  

## Impor namespace
Pertama, impor namespace yang diperlukan untuk operasi GIS:
Placeholder Import Namespaces tetap tidak berubah.

## Panduan langkah demi langkah

### Apa itu kelas GeoConvert?
Kelas `GeoConvert` menyediakan metode statis untuk mengonversi antara format koordinat seperti derajat desimal, DMS, dan GeoRef. Ini mencakup overload yang menerima nilai numerik mentah atau objek `Point` dan mengembalikan string terformat atau instance `Point` baru. Dengan menangani kasus tepi seperti koordinat negatif dan pembulatan, kelas ini menjamin bahwa output mematuhi spesifikasi GIS standar, menyederhanakan integrasi ke dalam aplikasi pemetaan .NET apa pun.

### Langkah 1: mulai proses konversi
Kita mencetak pesan ramah sehingga Anda tahu demo telah dimulai.

```csharp
using System;
using Aspose.Gis;
```

### Langkah 2: konversi ke derajat desimal
Meskipun tujuan akhir adalah DMS, kami mulai dengan menampilkan representasi desimal asli. Ini juga memperlihatkan jalur **decimal degrees to dms** yang akan Anda ikuti nanti.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### Langkah 3: konversi ke menit desimal derajat
Format ini (`DD°MM.m'`) adalah langkah menengah yang umum ketika Anda perlu **convert lat long degree minutes**.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Langkah 4: konversi ke derajat menit detik (dms)
Inilah inti tutorial kami—**convert coordinates to dms**.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Langkah 5: konversi ke GeoRef
Untuk melengkapi, kami juga memperlihatkan format `GeoRef`, yang berguna dalam alur kerja penginderaan jauh.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

## Masalah umum dan solusi
- **Huruf belahan bumi yang salah** – Pastikan Anda memberikan nilai positif untuk utara/timur dan negatif untuk selatan/barat; API secara otomatis menambahkan sufiks yang tepat.  
- **Output kosong yang tidak terduga** – Verifikasi bahwa assembly `Aspose.Gis` direferensikan dengan benar dan proyek menargetkan versi .NET yang didukung.  
- **Lisensi tidak ditemukan** – Tempatkan file lisensi Anda di root aplikasi atau atur secara programatis dengan `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.

## Pertanyaan yang sering diajukan

**Q: Apakah Aspose.GIS kompatibel dengan bahasa pemrograman lain?**  
A: Aspose.GIS terutama ditujukan untuk pengembang .NET, tetapi versi Java juga tersedia.

**Q: Bisakah saya mencoba Aspose.GIS sebelum membeli?**  
A: Ya, Anda dapat mengakses percobaan gratis Aspose.GIS dari [website](https://releases.aspose.com/).

**Q: Bagaimana saya dapat mendapatkan dukungan untuk Aspose.GIS?**  
A: Anda dapat mencari bantuan di forum komunitas Aspose.GIS [di sini](https://forum.aspose.com/c/gis/33).

**Q: Apakah lisensi sementara tersedia untuk Aspose.GIS?**  
A: Ya, lisensi sementara dapat diperoleh dari [halaman lisensi sementara](https://purchase.aspose.com/temporary-license/).

**Q: Di mana saya dapat membeli Aspose.GIS?**  
A: Anda dapat membeli Aspose.GIS dari [halaman pembelian](https://purchase.aspose.com/buy).

## Kesimpulan
Dengan mengikuti langkah‑langkah ini, Anda kini tahu cara **convert decimal degrees to dms** dan format GIS umum lainnya menggunakan Aspose.GIS untuk .NET. Kemampuan ini memungkinkan Anda mengintegrasikan string lokasi yang dapat dibaca manusia secara mulus ke dalam aplikasi pemetaan, laporan, atau alur kerja data spasial apa pun. Jangan ragu untuk bereksperimen dengan nilai lintang/bujur yang berbeda dan menjelajahi format lain yang ditawarkan oleh kelas `GeoConvert`.

---

**Terakhir Diperbarui:** 2026-08-18  
**Diuji Dengan:** Aspose.GIS 24.11 for .NET  
**Penulis:** Aspose  

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## Tutorial Terkait

- [Cara Membuat Geometri Titik dan Mendapatkan Tipe Geometri dengan Aspose.GIS untuk .NET](/gis/net/geometry-analysis/get-geometry-type/)
- [Cara Mengonversi GeoJSON – Aspose.GIS untuk .NET](/gis/net/geo-data-conversion/)
- [Buat Geometri MultiPoint .NET dengan Aspose.GIS](/gis/net/geometry-creation/create-multipoint-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}