---
date: 2025-12-20
description: Pelajari cara membuat lapisan vektor dan membatasi presisi saat membaca
  geometri menggunakan Aspose.GIS untuk .NET. Panduan langkah demi langkah untuk penanganan
  data geospasial yang optimal.
linktitle: Limit Precision Reading Geometries
second_title: Aspose.GIS .NET API
title: Buat Lapisan Vektor, Batasi Presisi dengan Aspose.GIS untuk .NET
url: /id/net/geometry-processing/limit-precision-reading-geometries/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Layer Vektor, Batasi Presisi dengan Aspose.GIS untuk .NET

## Introduction
Saat bekerja dengan data geospasial, Anda sering perlu **membuat objek layer vektor** dan mengontrol berapa banyak detail numerik yang dipertahankan saat membacanya. Aspose.GIS untuk .NET memudahkan membatasi presisi, yang dapat meningkatkan kinerja dan mengurangi ukuran penyimpanan ketika akurasi ultra‑tinggi tidak diperlukan. Dalam tutorial ini Anda akan melihat secara tepat cara membuat layer vektor, menulis geometri titik sederhana, dan kemudian membacanya kembali dengan presisi tepat dan terpotong.

## Quick Answers
- **Apa arti “batasi presisi”?** Itu membulatkan nilai koordinat ke sejumlah tempat desimal yang ditentukan.  
- **Mengapa harus membuat layer vektor terlebih dahulu?** Layer vektor adalah wadah yang menyimpan geometri seperti titik, garis, dan poligon.  
- **Model presisi apa yang tersedia?** `PrecisionModel.Exact` (tanpa pembulatan) dan `PrecisionModel.Rounding(n)` (membulatkan ke *n* desimal).  
- **Apakah saya memerlukan lisensi untuk mencoba ini?** Versi percobaan gratis tersedia di halaman rilis.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core, dan .NET 5/6+.

## Prerequisites
Sebelum memulai perjalanan ini, pastikan Anda memiliki prasyarat berikut:
1. **Instalasi** – Perpustakaan Aspose.GIS untuk .NET harus diinstal di lingkungan pengembangan Anda. Jika belum, Anda dapat mengunduhnya dari [halaman rilis](https://releases.aspose.com/gis/net/).
2. **Familiaritas dengan .NET** – Pengetahuan dasar tentang C# dan kerangka kerja .NET diperlukan untuk memahami dan menerapkan contoh kode yang disediakan.
3. **Lingkungan Pengembangan** – Diperlukan lingkungan pengembangan .NET yang berfungsi, seperti Visual Studio.
4. **Direktori Dokumen** – Siapkan sebuah direktori tempat Anda dapat menyimpan dan mengakses shapefile yang dihasilkan selama proses.

## Import Namespaces
Sebelum kita mulai mengimplementasikan fungsionalitas untuk membatasi presisi saat membaca geometri, pastikan kita mengimpor namespace yang diperlukan:
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## How to Create Vector Layer
Langkah pertama adalah **membuat layer vektor** yang akan menampung geometri kita. Layer ini akan disimpan sebagai Shapefile sehingga kita dapat membukanya kembali nanti dengan pengaturan presisi yang berbeda.
```csharp
string path = "Your Document Directory" + "LimitPrecisionWhenReadingGeometries_out.shp";
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
	var feature = layer.ConstructFeature();
	feature.Geometry = new Point(1.10234, 2.09743);
	layer.Add(feature);
}
```

## Setting Precision Options
Selanjutnya, kita perlu mendefinisikan opsi untuk membaca geometri, menentukan model presisi yang diinginkan. Kita dapat memulai dengan presisi tepat:
```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## Reading Geometries with Exact Precision
Sekarang, mari buka layer vektor dengan opsi yang ditentukan untuk membaca geometri dengan presisi tepat:
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Truncating Precision
Jika kita ingin memotong presisi ke sejumlah tempat desimal tertentu, kita dapat menyesuaikan model presisi sesuai:
```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Common Issues and Solutions
- **Nilai koordinat tidak terduga** – Pastikan Anda mengatur `options.XYPrecisionModel` *sebelum* membuka layer. Mengubahnya setelah membuka tidak berpengaruh.
- **File tidak ditemukan** – Verifikasi bahwa variabel `path` mengarah ke direktori yang valid dan bahwa Shapefile berhasil dibuat pada langkah sebelumnya.
- **Tipe geometri tidak tepat** – Contoh menggunakan `Point`. Untuk tipe geometri lain (mis., `LineString`), casting harus sesuai dengan tipe sebenarnya.

## Conclusion
Sebagai kesimpulan, mengelola presisi saat membaca geometri adalah aspek penting dalam manipulasi data geospasial. Aspose.GIS untuk .NET menyediakan fungsionalitas yang kuat untuk mencapai hal ini secara efisien. Dengan mengikuti langkah-langkah yang dijelaskan dalam tutorial ini, Anda dapat dengan mudah **membuat objek layer vektor** dan membatasi presisi sesuai kebutuhan Anda, memastikan penanganan data yang optimal dalam aplikasi Anda.

## FAQ
### Bisakah saya menggunakan Aspose.GIS untuk .NET dengan kerangka kerja .NET lain seperti .NET Core atau .NET Standard?
Ya, Aspose.GIS untuk .NET kompatibel dengan berbagai kerangka kerja .NET, termasuk .NET Core dan .NET Standard.

### Apakah ada versi percobaan yang tersedia untuk Aspose.GIS untuk .NET?
Ya, Anda dapat memperoleh versi percobaan gratis dari [halaman rilis](https://releases.aspose.com/).

### Di mana saya dapat menemukan dokumentasi lengkap untuk Aspose.GIS untuk .NET?
Anda dapat merujuk ke [dokumentasi](https://reference.aspose.com/gis/net/) untuk informasi detail dan contoh.

### Bagaimana cara mendapatkan lisensi sementara untuk Aspose.GIS untuk .NET?
Lisensi sementara dapat diperoleh dari [halaman pembelian](https://purchase.aspose.com/temporary-license/) untuk Aspose.GIS.

### Di mana saya dapat mencari bantuan atau dukungan untuk Aspose.GIS untuk .NET?
Anda dapat mengunjungi [forum](https://forum.aspose.com/c/gis/33) Aspose.GIS untuk pertanyaan, diskusi, atau kebutuhan dukungan.

## Pertanyaan yang Sering Diajukan
**T: Apakah membatasi presisi memengaruhi shapefile asli?**  
J: Tidak. Presisi hanya diterapkan saat membaca geometri; file sumber tetap tidak berubah.  

**T: Bisakah saya menggunakan model presisi yang berbeda untuk koordinat X dan Y?**  
J: Aspose.GIS saat ini menerapkan `XYPrecisionModel` yang sama untuk kedua sumbu.  

**T: Apakah memungkinkan untuk menetapkan fungsi pembulatan khusus?**  
J: API hanya mendukung metode bawaan `PrecisionModel.Rounding(int)`. Untuk logika khusus, Anda harus memproses koordinat setelah membaca.

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}