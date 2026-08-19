---
date: 2026-06-15
description: Pelajari cara membaca nilai atribut shapefile di C# menggunakan Aspose.GIS
  untuk .NET, mengambil setiap atribut fitur, dan mengekspor atribut secara efisien.
keywords:
- read shapefile attribute values
- Aspose.GIS attribute extraction
- C# GIS tutorial
linktitle: Dapatkan Semua Nilai Atribut Fitur
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to read shapefile attribute values in C# using Aspose.GIS
    for .NET, retrieve every feature attribute, and dump attributes efficiently.
  headline: Read Shapefile Attribute Values in C# – Get All Feature Attribute Values
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS fully supports .NET Core, enabling cross‑platform GIS
      solutions on Windows, Linux, and macOS.
    question: Is Aspose.GIS compatible with .NET Core?
  - answer: Absolutely. The library handles Shapefile, GeoJSON, KML, GML, CSV, and
      over 30 other formats without additional plugins.
    question: Can I work with different GIS file formats using Aspose.GIS?
  - answer: You can acquire a temporary license for evaluation [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for testing?
  - answer: The comprehensive reference is available [here](https://reference.aspose.com/gis/net/).
    question: Where is the official documentation for Aspose.GIS?
  - answer: Use `GetValues` with a single‑element array and pass the column index
      of “Name”, or simply call `feature["Name"]` for direct access.
    question: How do I retrieve only the “Name” attribute from each feature?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Baca Nilai Atribut Shapefile di C# – Dapatkan Semua Nilai Atribut Fitur
url: /id/net/layer-interaction-and-data-access/get-all-feature-attribute-values/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dapatkan Semua Nilai Atribut Fitur

## Pendahuluan
Pada tutorial ini Anda akan menemukan **cara membaca nilai atribut shapefile** di C# dengan Aspose.GIS untuk .NET. Baik Anda sedang membangun aplikasi pemetaan langsung, melakukan analisis spasial massal, atau hanya perlu mengekspor tabel atribut, mengekstrak setiap field dari Shapefile adalah keterampilan dasar. Kami akan membahas alur kerja lengkap, mulai dari mengatur direktori data hingga membuang koleksi atribut, serta menyoroti tips praktik terbaik yang menjaga kode Anda tetap bersih dan berperforma.

## Jawaban Cepat
- **Apa yang dilakukan kode ini?** Kode ini membuka Shapefile, mengiterasi setiap fitur, dan mengambil setiap nilai atribut atau subset yang dipilih.  
- **Perpustakaan mana yang diperlukan?** Aspose.GIS untuk .NET (berfungsi dengan .NET Framework, .NET Core, .NET 5/6).  
- **Apakah saya memerlukan lisensi?** Lisensi sementara cukup untuk pengujian; lisensi penuh wajib untuk penerapan produksi.  
- **Bisakah saya membaca format lain?** Ya – API yang sama dapat membaca GeoJSON, KML, GML, CSV, dan lebih dari 30 format GIS lainnya.  
- **Bagaimana cara membuang (dump) atribut?** Panggil `feature.GetValuesDump()` untuk mendapatkan array objek yang dapat diserialisasi atau diperiksa secara langsung.

## Apa itu “read shapefile C#”?
Membaca Shapefile di C# berarti membuka file `.shp` dengan perpustakaan GIS, mengiterasi fitur vektornya, dan mengakses data atribut yang disimpan dalam file `.dbf` yang menyertainya. Aspose.GIS mengabstraksi penanganan file tingkat rendah, memungkinkan Anda mengekstrak nilai atribut hanya dengan beberapa baris kode.

## Mengapa menggunakan Aspose.GIS untuk membaca atribut?
Aspose.GIS menyediakan API berperforma tinggi, lintas platform yang menyederhanakan ekstraksi atribut dari Shapefile. Ia mendukung **lebih dari 30 format GIS**, memproses hingga **500 000 fitur per detik** pada server standar 4‑core, dan menawarkan metode intuitif seperti `GetValues` dan `GetValuesDump` yang menghilangkan kebutuhan parsing DBF manual. Gunakan ketika Anda memerlukan kode yang andal, bebas lisensi (untuk pengujian) yang berfungsi di Windows, Linux, dan macOS tanpa plugin tambahan.

## Prasyarat
- **Aspose.GIS untuk .NET** – unduh dari [halaman unduhan Aspose.GIS untuk .NET](https://releases.aspose.com/gis/net/).  
- **Lingkungan pengembangan** – Visual Studio 2022, Rider, atau IDE apa pun yang mendukung .NET 6+.  
- **Shapefile contoh** – letakkan file seperti `InputShapeFile.shp` di folder yang diketahui pada mesin Anda.  

## Impor Namespace
Namespace `Aspose.Gis` berisi tipe GIS inti seperti `VectorLayer` dan `Feature`.  
`VectorLayer` mewakili dataset vektor seperti Shapefile, sementara `Feature` mewakili catatan spasial individual.  
```csharp
using System;
using Aspose.Gis;
```

## Langkah 1: Atur Direktori Dokumen
Tentukan folder yang menyimpan Shapefile Anda sehingga API dapat menemukan file `.shp`, `.shx`, dan `.dbf`.  
```csharp
string dataDir = "Your Document Directory";
```
Ganti “Your Document Directory” dengan jalur sebenarnya tempat Shapefile Anda berada.

## Langkah 2: Buka VectorLayer
`VectorLayer` mewakili dataset vektor (Shapefile, GeoJSON, dll.). Membukanya memuat skema tanpa membaca semua data geometrik, sehingga penggunaan memori tetap rendah.  
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for further steps goes here
}
```
Langkah ini menentukan jalur file dan format (Shapefile).

## Langkah 3: Ambil Semua Nilai Atribut Fitur
`GetValues` mengisi array yang telah dialokasikan sebelumnya dengan nilai atribut mentah dari sebuah fitur. Pendekatan ini ideal ketika Anda memerlukan set hasil yang deterministik dan berukuran tetap.  
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
Potongan kode ini menunjukkan cara membaca atribut untuk **setiap** fitur ke dalam array berukuran tetap.

## Langkah 4: Ambil Beberapa Nilai Atribut Fitur
Ketika hanya sebagian bidang yang diperlukan, Anda dapat memberikan array yang lebih kecil atau menggunakan indeks kolom untuk membatasi data yang ditransfer. Ini mengurangi beban memori dan mempercepat pemrosesan.  
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
Di sini kami mendemonstrasikan pembacaan nilai atribut spesifik (misalnya, “Name” dan “Population”).

## Langkah 5: Ambil Nilai Atribut sebagai Dump Objek
`GetValuesDump` mengembalikan `object[]` yang berisi semua nilai atribut dari sebuah fitur, sesuai dengan skema fitur tersebut. Ini memungkinkan Anda mengenumerasi bidang tanpa pengetahuan sebelumnya tentang urutan atau tipe mereka.  
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
Langkah akhir ini menampilkan cara yang fleksibel dan tidak tergantung skema untuk membuang (dump) atribut untuk debugging atau serialisasi.

## Masalah Umum dan Solusinya
- **Ketidaksesuaian ukuran array** – Pastikan array yang Anda berikan ke `GetValues` cocok dengan jumlah atribut yang diharapkan; jika tidak, Anda akan menerima entri `null`.  
- **File tidak ditemukan** – Verifikasi bahwa `dataDir` mengarah ke folder yang benar dan nama Shapefile ditulis tepat, termasuk ekstensi `.shp`.  
- **Pengecualian lisensi** – Jika muncul kesalahan lisensi, terapkan lisensi sementara atau penuh sebelum memanggil metode API apa pun.

## Pertanyaan yang Sering Diajukan
**Q: Apakah Aspose.GIS kompatibel dengan .NET Core?**  
A: Ya, Aspose.GIS sepenuhnya mendukung .NET Core, memungkinkan solusi GIS lintas platform di Windows, Linux, dan macOS.  

**Q: Bisakah saya bekerja dengan format file GIS berbeda menggunakan Aspose.GIS?**  
A: Tentu saja. Perpustakaan ini menangani Shapefile, GeoJSON, KML, GML, CSV, dan lebih dari 30 format lain tanpa plugin tambahan.  

**Q: Bagaimana cara memperoleh lisensi sementara untuk pengujian?**  
A: Anda dapat memperoleh lisensi sementara untuk evaluasi [di sini](https://purchase.aspose.com/temporary-license/).  

**Q: Di mana dokumentasi resmi untuk Aspose.GIS?**  
A: Referensi lengkap tersedia [di sini](https://reference.aspose.com/gis/net/).  

**Q: Bagaimana cara mengambil hanya atribut “Name” dari setiap fitur?**  
A: Gunakan `GetValues` dengan array satu elemen dan berikan indeks kolom “Name”, atau cukup panggil `feature["Name"]` untuk akses langsung.  

**Q: Apa perbedaan antara `GetValues` dan `GetValuesDump`?**  
A: `GetValues` mengisi array yang telah dialokasikan sebelumnya dengan nilai mentah, sementara `GetValuesDump` mengembalikan `object[]` yang dapat dienumerasi tanpa mengetahui skema sebelumnya.  

**Q: Di mana saya dapat mendapatkan bantuan jika mengalami masalah?**  
A: Kunjungi forum dukungan Aspose GIS [di sini](https://forum.aspose.com/c/gis/33) untuk bantuan komunitas dan dukungan resmi.  

---

**Last Updated:** 2026-06-15  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose

## Tutorial Terkait

- [Dapatkan Atribut Layer – Ambil Informasi Atribut Layer dengan Aspose.GIS untuk .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Cara Mendapatkan Nilai Atribut (Default) dengan Aspose.GIS untuk .NET](/gis/net/layer-interaction-and-data-access/get-feature-attribute-value-default/)
- [Baca Shapefile C# – Filter Fitur berdasarkan Atribut dengan Aspose.GIS](/gis/net/layer-management/filter-features-by-attribute/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}