---
date: 2026-01-13
description: Pelajari cara mengonversi shapefile ke geojson menggunakan Aspose.GIS
  untuk .NET. Panduan ini juga mencakup penyalinan atribut antar lapisan dan pembuatan
  file geojson dengan C#.
linktitle: Extract Features to GeoJSON
second_title: Aspose.GIS .NET API
title: Cara Mengonversi Shapefile ke GeoJSON menggunakan Aspose.GIS untuk .NET
url: /id/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mengonversi Shapefile ke GeoJSON dengan Aspose.GIS untuk .NET

## Perkenalan
Dalam tutorial komprehensif langkah‑demi‑langkah ini Anda akan belajar **bagaimana mengkonversi shapefile ke geojson** menggunakan pustaka Aspose.GIS yang kuat untuk .NET. Baik Anda segang membujang serviceanan web pemetan, mempapata data untuk aplikasi GIS selular, atau sekadaar peru menjakan data antar format, panduan ini sekaran sekara tepat apa yang harus dikanta, penbanga patiap langkah pentang, dan cara megujaran jebakan umum.

## Jawaban Cepat
- **Apa yang tercakup dalam tutorial ini?** Mengonversi Shapefile ke file GeoJSON, kabina atribut antar legasan, dan prodatsa output dengan C#.
- **Perpustakaan mana yang diperlukan?** Aspose.GIS untuk .NET.
**Apakah saya memerlukan lisensi?** uji coba gratis dapat digunakan untuk evaluasi.
- **Berapa lama waktu implementasi?** Sekitar 10‑15 menit untuk konversi dasar.
**Dapatkah saya menjalankan ini di .NET Core/.NET 6?**

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal‑hal beringen:

- Aspose.GIS for .NET: Pastikan Anda telah menginstal pustaka tersebut. Jika belum, Anda dapat nadukumnya dari [Aspose.GIS untuk halaman .NET](https://releases.aspose.com/gis/net/).
- Data Shapefile: Miliki Shapefile siap untuk input. Jika Anda memerlukan data, Anda dapat menemukannya di [dokumentasi Aspose.GIS](https://reference.aspose.com/gis/net/).
- .NET Environment: Siapkan lingungan .NET untuk mendapatkan kode yang sukuna.
- Direktori Dokumen: Tentukan jalar ke direktori dokumen Anda dalam cuplikan kode.

Sekarang semua sudah siap, mari mulai mengubah shapefile ke geojson!

## Apa itu “konversi shapefile ke geojson”?
Mengonversi Shapefile ke GeoJSON berarti membaka fitur vektor dari format Shapefile klasik ESRI dan menuliskannya sebagai dokumen GeoJSON modern yang ramah web. GeoJSON dapat digunakan dalam penggunaan JavaScript (Leaflet, Mapbox GL) dan API, dan sering digunakan dalam pengembangan GIS.

## Mengapa menggunakan Aspose.GIS untuk konversi ini?
Aspose.GIS menyembunyikan detail file berformat tingkat‑rendah, memungkinkan Anda menyalin atribut tabel dengan mudah, dan menyediakan objek berorientasi API yang berfungsi dengan baik dengan .NET Framework, .NET Core, dan .NET 5/6. Ini berarti Anda dapat fokus pada logika bisnis alih-alih memparsing file biner.

## Impor Namespace
Pertama, sertakan namespace yang bahasanya dalam kode Anda:

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Namespace ini penting untuk bekerja dengan fungsionalitas Aspose.GIS.

## Cara Mengonversi Shapefile ke GeoJSON
Berikut adalah alur kerja lengkap yang dibagi menjadi langkah‑langkah jelas. Setiap langkah mencakup penjelasan singkat diikuti oleh blok kode tepat yang perlu Anda salin ke dalam proyek.

### Langkah 1: Buka Input Shapefile
```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```
Buka Shapefile input menggunakan metode `VectorLayer.Open`. Ini memberi Anda koleksi enumerable dari objek `Feature`.

### Langkah 2: Buat Keluaran GeoJSON
```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```
Buat file output dengan metode `VectorLayer.Create`, dengan menentukan driver `Drivers.GeoJson`.

### Langkah 3: Salin Atribut Antar Lapisan
```csharp
outputLayer.CopyAttributes(inputLayer);
```
Baris tunggal ini menyalin skema atribut (nama bidang, tipe) dari Shapefile sumber ke lapisan GeoJSON baru—tepat seperti yang dijelaskan oleh kata kunci sekunder *copy attributes between layers*.

### Langkah 4: Fitur Proses
```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```
Iterasi setiap fitur dalam Shapefile sehingga Anda dapat menerapkan logika khusus sebelum menuliskannya.

### Langkah 5: Filter Fitur berdasarkan Tanggal
```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```
Dalam contoh ini kami melewatkan catatan yang bidang `dob` (tanggal lahir)nya hilang atau lebih awal dari 1 Jan 1982. Silakan sesuaikan filter sesuai kebutuhan data Anda.

### Langkah 6: Membuat Fitur Baru (C# Hasilkan File GeoJSON)
```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```
Di sini kami membangun `Feature` baru untuk lapisan GeoJSON, menyalin geometri dan nilai atribut, dan menambahkannya ke output. Ini adalah inti dari *c# generate geojson file*.

Selamat! Anda telah berhasil **converted shapefile to geojson** dan mempelajari cara menyalin atribut antar lapisan selama proses.

## Masalah Umum dan Solusinya
| Masalah | Mengapa Terjadi | Solusi |
|-------|----------------|-----|
| File keluaran kosong | `CopyAttributes` dipanggil setelah lapisan output ditutup | Pastikan blok `using` untuk `outputLayer` tetap terbuka hingga semua fitur ditambahkan. |
| Filter tanggal menghapus semua catatan | Nama bidang salah atau format tanggal tidak terduga | Verifikasi nama atribut (`dob`) dan gunakan `GetValue<string>` jika tanggal disimpan sebagai string. |
| Pengecualian lisensi | Garis tanpa lisensi Aspose.GIS yang valid di produksi | Terapkan lisensi sementara atau penuh seperti yang dijelaskan dalam dokumentasi Aspose. |

## Pertanyaan yang Sering Diajukan
**Q: Bagaimana saya dapat menemukan dokumentasi lebih lanjut?**
A: Kunjungi [dokumentasi Aspose.GIS](https://reference.aspose.com/gis/net/) untuk informasi mendalam.

**Q: Bagaimana cara mendapatkan lisensi sementara?**
A: Anda dapat memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

**Q: Di mana saya dapat mencari dukungan?**
A: bersinggungan dengan [Forum Aspose.GIS](https://forum.aspose.com/c/gis/33) untuk dukungan komunitas dan diskusi.

**Q: Apakah ada percobaan gratis yang tersedia?**
A: Ya, Anda dapat menemukan percobaan gratis [di sini](https://releases.aspose.com/).

**Q: Di mana saya dapat membeli Aspose.GIS untuk .NET?**
A: Anda dapat membeli produk tersebut [di sini](https://purchase.aspose.com/buy).

## Kesimpulan
Dalam tutorial ini kami menjelajahi proses lengkap **convert shapefile to geojson** menggunakan Aspose.GIS untuk .NET, menunjukkan cara menyalin atribut antar lapisan, dan menampilkan cara bersih untuk *c# generate geojson file*. Bereksperimenlah dengan filter yang berbeda, dataset yang lebih besar, atau transformasi geometri tambahan untuk memanfaatkan kemampuan perpustakaan secara maksimal.

---

**Terakhir Diperbarui:** 13-01-2026
**Diuji Dengan:** Aspose.GIS untuk .NET (rilis stabil terbaru)
**Penulis:** Berasumsi  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}