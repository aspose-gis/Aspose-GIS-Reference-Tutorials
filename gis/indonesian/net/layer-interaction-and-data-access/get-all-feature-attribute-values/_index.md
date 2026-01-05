---
date: 2026-01-05
description: Pelajari cara membaca shapefile C# menggunakan Aspose.GIS untuk .NET,
  mengambil semua nilai atribut fitur, dan mengekspor atribut secara efisien.
linktitle: Get All Feature Attribute Values
second_title: Aspose.GIS .NET API
title: Baca Shapefile C# – Dapatkan Semua Nilai Atribut Fitur
url: /id/net/layer-interaction-and-data-access/get-all-feature-attribute-values/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dapatkan Semua Nilai Atribut Fitur

## Introduction
Selamat datang di dunia pengembangan geospasial dengan Aspose.GIS untuk .NET! Dalam tutorial ini Anda akan belajar **cara membaca shapefile C#** dan mengambil setiap nilai atribut dari fitur‑fiturnya. Baik Anda membangun aplikasi pemetaan atau memproses data spasial secara batch, menguasai ekstraksi atribut sangat penting. Mari kita selami dan lihat kode yang beraksi.

## Quick Answers
- **Apa yang dilakukan kode ini?** Kode ini membuka sebuah Shapefile dan membaca semua, beberapa, atau nilai atribut yang di‑dump dari setiap fitur.  
- **Perpustakaan mana yang diperlukan?** Aspose.GIS untuk .NET (kompatibel dengan .NET Framework dan .NET Core).  
- **Apakah saya memerlukan lisensi?** Lisensi sementara dapat digunakan untuk pengujian; lisensi penuh diperlukan untuk produksi.  
- **Bisakah saya membaca format lain?** Ya – API yang sama mendukung GeoJSON, KML, dan banyak lagi.  
- **Bagaimana cara meng‑dump atribut?** Gunakan `feature.GetValuesDump()` untuk memperoleh array objek yang fleksibel.

## What is “read shapefile C#”?
Membaca Shapefile dalam C# berarti membuka file .shp dengan perpustakaan GIS, mengiterasi fitur‑fitur vektornya, dan mengakses data atribut yang disimpan dalam file .dbf yang menyertainya. Aspose.GIS mengabstraksi penanganan file tingkat rendah, memungkinkan Anda fokus pada nilai atribut yang dibutuhkan.

## Why use Aspose.GIS to read attributes?
- **API sederhana** – metode intuitif seperti `GetValues` dan `GetValuesDump`.  
- **Lintas‑platform** – berfungsi di Windows, Linux, dan macOS dengan .NET Core.  
- **Dukungan format kaya** – menangani Shapefile, GeoJSON, GML, dan lainnya tanpa plugin tambahan.  
- **Dioptimalkan untuk kinerja** – iterasi cepat pada dataset besar.

## Prerequisites
Sebelum memulai perjalanan menarik ini, pastikan Anda telah menyiapkan hal‑hal berikut:
- Aspose.GIS untuk .NET: Unduh dan instal perpustakaan dari [halaman unduhan Aspose.GIS untuk .NET](https://releases.aspose.com/gis/net/).
- Lingkungan Pengembangan: Siapkan lingkungan pengembangan .NET, seperti Visual Studio.
- Shapefile: Miliki contoh Shapefile (misalnya "InputShapeFile.shp") yang siap di direktori dokumen Anda.

## Import Namespaces
Dalam kode C# Anda, mulailah dengan mengimpor namespace yang diperlukan untuk mem fungsionalitas Aspose.GIS:
```csharp
using System;
using Aspose.Gis;
```

## Step 1: Set the Document Directory
```csharp
string dataDir = "Your Document Directory";
```
Ganti "Your Document Directory" dengan jalur sebenarnya tempat Shapefile Anda berada.

## Step 2: Open the VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for further steps goes here
}
```
Langkah ini melibatkan pembukaan Shapefile menggunakan Aspose.GIS, dengan menentukanur dan format (dalam kasus ini, Shapefile).

## Step 3: Retrieve All Feature Attribute Values
```csharp
foreach (var feature in layer)
{
    // reads all the attributes into an array.
    object[] all = new object[3];
    feature.GetValues(all);
    Console.WriteLine("all    : {0}, {1}, {2}", all);
    // Your code for handling all attribute values goes here
    Console.WriteLine();
}
```
Potongan kode ini menunjukkan **cara membaca atribut** untuk setiap fitur dengan memuatnya ke dalam array berukuran tetap.

## Step 4: Retrieve Several Feature Attribute Values
```csharp
foreach (var feature in layer)
{
    // reads several attributes into an array.
    object[] several = new object[2];
    feature.GetValues(several);
    Console.WriteLine("several: {0}, {1}", several);
    // Your code for handling several attribute values goes here
    Console.WriteLine();
}
```
Di sini kami mendemonstrasikan **cara membaca nilai atribut tertentu** ketika Anda hanya membutuhkan sebagian bidang.

## Step 5: Retrieve Attribute Values as Objects Dump
```csharp
foreach (var feature in layer)
{
    // reads attributes as a dump of objects.
    var dump = feature.GetValuesDump();
    Console.WriteLine("dump   : {0}, {1}, {2}", dump);
    // Your code for handling dumped attribute values goes here
    Console.WriteLine();
}
```
Langkah akhir ini menampilkan **cara meng‑dump atribut** menggunakan `GetValuesDump()`, yang mengembalikan koleksi fleksibel yang dapat Anda inspeksi atau serialisasi.

## Common Issues and Solutions
- **Ukuran array tidak cocok** – Pastikan array yang Anda berikan ke `GetValues` sesuai dengan jumlah atribut yang diharapkan; jika tidak, Anda akan mendapatkan entri `null`.  
- **File tidak ditemukan** – Verifikasi bahwa `dataDir` mengarah ke folder yang tepat dan nama Shapefile dieja persis.  
- **Pengecualian lisensi** – Jika Anda melihat kesalahan lisensi, terapkan lisensi sementara atau penuh sebelum memanggil metode API apa pun.

## Frequently Asked Questions
### Apakah Aspose.GIS kompatibel dengan .NET Core?
Ya, Aspose.GIS sepenuhnya kompatibel dengan .NET Core, memungkinkan Anda membangun aplikasi lintas‑platform.

### Bisakah saya bekerja dengan format file GIS yang berbeda menggunakan Aspose.GIS?
Tentu saja! Aspose.GIS mendukung berbagai format, termasuk Shapefile, GeoJSON, dan lainnya.

### Apakah ada forum komunitas untuk dukungan Aspose.GIS?
Ya, Anda dapat menemukan bantuan dan berinteraksi dengan komunitas Aspose.GIS di [forum dukungan](https://forum.aspose.com/c/gis/33).

### Bagaimana cara mendapatkan lisensi sementara untuk Aspose.GIS?
Anda dapat memperoleh lisensi sementara untuk keperluan pengujian [di sini](https://purchase.aspose.com/temporary-license/).

### Di mana saya dapat menemukan dokumentasi detail untuk Aspose.GIS?
Dokumentasi lengkap tersedia [di sini](https://reference.aspose.com/gis/net/).

### Bagaimana cara mengambil hanya atribut “Name” dari setiap fitur?
Gunakan `GetValues` dengan array berukuran satu elemen dan berikan indeks bidang “Name”, atau panggil `feature["Name"]` secara langsung.

### Apa perbedaan antara `GetValues` dan `GetValuesDump`?
`GetValues` mengisi array yang telah dialokasikan sebelumnya dengan nilai mentah, sedangkan `GetValuesDump` mengembalikan array objek yang dapat di‑enumerasi tanpa harus mengetahui skema sebelumnya.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Terakhir Diperbarui:** 2026-01-05  
**Diuji Dengan:** Aspose.GIS untuk .NET (rilis terbaru)  
**Penulis:** Aspose