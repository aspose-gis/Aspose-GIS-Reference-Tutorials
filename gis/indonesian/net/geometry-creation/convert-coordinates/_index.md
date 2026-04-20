---
date: 2026-02-13
description: Pelajari cara mengonversi koordinat ke DMS dengan Aspose.GIS untuk .NET.
  Panduan C# langkah demi langkah ini menunjukkan cara mengonversi lintang dan bujur,
  derajat desimal ke DMS, dan lainnya.
linktitle: Convert Coordinates
second_title: Aspose.GIS .NET API
title: Cara Mengonversi Koordinat ke DMS dengan Aspose.GIS untuk .NET
url: /id/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengonversi Koordinat ke DMS dengan Aspose.GIS

## Pendahuluan
Dalam tutorial ini, Anda akan belajar **cara mengonversi koordinat** ke DMS (derajat, menit, detik) menggunakan pustaka Aspose.GIS yang kuat untuk .NET. Baik Anda perlu **c# convert lat long**, menghasilkan string lokasi yang dapat dibaca manusia, atau sekadar menjelajahi berbagai format koordinat, panduan ini akan membawa Anda melalui setiap langkah dengan penjelasan yang jelas dan kode C# yang siap dijalankan.

## Jawaban Cepat
- **Apa arti “convert coordinates to DMS”?** Itu mengubah nilai numerik latitude/longitude menjadi notasi tradisional derajat‑menit‑detik.  
- **Perpustakaan mana yang menangani konversi?** Aspose.GIS untuk .NET menyediakan kelas `GeoConvert` dengan dukungan format bawaan.  
- **Apakah saya memerlukan lisensi untuk mencobanya?** Versi percobaan gratis tersedia; lisensi komersial diperlukan untuk penggunaan produksi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, dan .NET 5/6+.  
- **Bisakah saya menggunakan kode yang sama untuk format lain?** Ya—cukup ubah nilai enum `PointFormats` (mis., `DecimalDegrees`, `GeoRef`).  

## Cara Mengonversi Koordinat ke DMS
Sebelum menyelam ke kode, mari kita jelaskan mengapa DMS masih berharga. Kartografer, pilot, dan banyak penyedia data GIS mengandalkan DMS karena bersahabat dengan manusia dan selaras dengan peta tradisional. Aspose.GIS menghilangkan kebutuhan akan perhitungan manual, memungkinkan Anda fokus pada logika aplikasi Anda.

## Apa itu konversi koordinat ke DMS?
Mengonversi koordinat ke DMS menulis ulang nilai latitude dan longitude desimal ke dalam format seperti `25°30'00"N 45°30'00"E`. Representasi ini banyak digunakan dalam kartografi, navigasi, dan pertukaran data GIS.

## Mengapa menggunakan Aspose.GIS untuk konversi koordinat?
- **API all‑in‑one** – Tanpa pustaka eksternal atau matematika kompleks; Aspose.GIS menangani parsing dan pemformatan secara internal.  
- **Akurasi tinggi** – Penanganan presisi untuk kasus tepi seperti nilai negatif dan penanda belahan bumi.  
- **Cross‑platform** – Berfungsi sama pada runtime .NET Windows, Linux, dan macOS.  
- **Ekstensibel** – Mudah beralih antara format DMS, decimal degrees, degree‑decimal‑minutes, dan GeoRef.  

## Prasyarat
Sebelum Anda memulai, pastikan Anda memiliki:

1. **Pengetahuan dasar tentang C#** – Familiaritas dengan variabel, pemanggilan metode, dan output konsol.  
2. **Aspose.GIS terpasang** – Unduh paket terbaru dari [situs web Aspose.GIS](https://releases.aspose.com/gis/net/).  

## Impor Namespace
Pertama, impor namespace yang diperlukan untuk operasi GIS:

```csharp
using System;
using Aspose.Gis;
```

## Panduan langkah‑demi‑langkah

### Langkah 1: Mulai proses konversi
Kami mencetak pesan ramah sehingga Anda tahu demo telah dimulai.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### Langkah 2: Konversi ke Decimal Degrees  
Meskipun tujuan akhir adalah DMS, kami mulai dengan menampilkan representasi desimal asli. Ini juga menunjukkan jalur **decimal degrees to dms** yang akan Anda ikuti nanti.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Langkah 3: Konversi ke Degree Decimal Minutes  
Format ini (`DD°MM.m'`) adalah langkah menengah yang umum ketika Anda perlu *convert lat long degree minutes*.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Langkah 4: Konversi ke Degree Minutes Seconds (DMS)  
Berikut inti tutorial kami—**convert coordinates to DMS**.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

### Langkah 5: Konversi ke GeoRef  
Untuk melengkapi, kami juga mendemonstrasikan format `GeoRef`, yang berguna dalam alur kerja remote‑sensing.

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## Masalah Umum dan Solusinya
- **Huruf belahan bumi yang salah** – Pastikan Anda memberikan nilai positif untuk utara/timur dan negatif untuk selatan/barat; API secara otomatis menambahkan sufiks yang tepat.  
- **Output kosong yang tidak terduga** – Verifikasi bahwa assembly `Aspose.Gis` direferensikan dengan benar dan proyek menargetkan versi .NET yang didukung.  
- **Lisensi tidak ditemukan** – Tempatkan file lisensi Anda di root aplikasi atau atur secara programatis dengan `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.  

## Pertanyaan yang Sering Diajukan

**Q: Apakah Aspose.GIS kompatibel dengan bahasa pemrograman lain?**  
A: Aspose.GIS terutama menargetkan pengembang .NET, tetapi versi Java juga tersedia.

**Q: Bisakah saya mencoba Aspose.GIS sebelum membeli?**  
A: Ya, Anda dapat mengakses percobaan gratis Aspose.GIS dari [situs web](https://releases.aspose.com/).

**Q: Bagaimana saya dapat mendapatkan dukungan untuk Aspose.GIS?**  
A: Anda dapat mencari bantuan di forum komunitas Aspose.GIS [di sini](https://forum.aspose.com/c/gis/33).

**Q: Apakah lisensi sementara tersedia untuk Aspose.GIS?**  
A: Ya, lisensi sementara dapat diperoleh dari [halaman lisensi sementara](https://purchase.aspose.com/temporary-license/).

**Q: Di mana saya dapat membeli Aspose.GIS?**  
A: Anda dapat membeli Aspose.GIS dari [halaman pembelian](https://purchase.aspose.com/buy).

## Kesimpulan
Dengan mengikuti langkah‑langkah ini, Anda kini tahu cara **convert coordinates to DMS** dan format GIS umum lainnya menggunakan Aspose.GIS untuk .NET. Kemampuan ini memungkinkan Anda mengintegrasikan string lokasi yang dapat dibaca manusia secara mulus ke dalam aplikasi pemetaan, laporan, atau alur kerja data spasial apa pun. Jangan ragu untuk bereksperimen dengan nilai latitude/longitude yang berbeda dan menjelajahi format lain yang ditawarkan oleh kelas `GeoConvert`.

---

**Terakhir Diperbarui:** 2026-02-13  
**Diuji Dengan:** Aspose.GIS 24.11 for .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}