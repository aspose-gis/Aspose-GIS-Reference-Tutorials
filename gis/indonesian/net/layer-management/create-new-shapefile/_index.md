---
date: 2026-01-13
description: Pelajari cara membuat shapefile baru dengan Aspose.GIS untuk .NET. Panduan
  langkah demi langkah ini menunjukkan cara mendefinisikan lapisan vektor, menambahkan
  atribut tanggal, dan mengelola data spasial.
linktitle: Create New Shapefile
second_title: Aspose.GIS .NET API
title: Buat Shapefile Baru
url: /id/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Shapefile Baru

## Pendahuluan
Jika Anda sedang mendalami pengembangan sistem informasi geografis (GIS) dengan .NET, Aspose.GIS adalah solusi pilihan Anda. Perpustakaan yang kuat ini memungkinkan pengembang bekerja secara mulus dengan data spasial, dan dalam tutorial ini, kami akan memandu Anda cara **membuat shapefile baru** menggunakan Aspose.GIS untuk .NET. Anda akan melihat mengapa mendefinisikan lapisan vektor dan menambahkan atribut tanggal merupakan langkah penting untuk proyek GIS yang handal.

## Jawaban Cepat
- **Apa yang diajarkan tutorial ini?** Cara membuat shapefile baru, mendefinisikan lapisan vektor, dan menambahkan atribut (termasuk bidang tanggal).  
- **Perpustakaan apa yang dibutuhkan?** Aspose.GIS untuk .NET.  
- **Apakah saya memerlukan lisensi?** Versi trial gratis cukup untuk belajar; lisensi komersial diperlukan untuk produksi.  
- **IDE apa yang harus saya gunakan?** Visual Studio (versi terbaru apa pun).  
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk contoh dasar.

## Prasyarat
Sebelum memulai tutorial, pastikan Anda telah menyiapkan hal‑hal berikut:
- Pemahaman dasar tentang bahasa pemrograman C#.
- Visual Studio terpasang di mesin Anda.
- Perpustakaan Aspose.GIS untuk .NET. Anda dapat mengunduhnya [di sini](https://releases.aspose.com/gis/net/).

## Impor Namespace
Mulailah dengan mengimpor namespace yang diperlukan untuk memanfaatkan fungsionalitas Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Langkah 1: Siapkan Proyek Anda
Mulailah dengan membuat proyek C# baru di Visual Studio dan sertakan perpustakaan Aspose.GIS.

## Langkah 2: Tentukan Direktori Dokumen
```csharp
string dataDir = "Your Document Directory";
```
Ganti *Your Document Directory* dengan jalur sebenarnya tempat Anda ingin menyimpan shapefile baru Anda.

## Langkah 3: Buat VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
Segmen kode ini **mendefinisikan lapisan vektor** dan mendeklarasikan tiga atribut: bidang teks (`name`), bidang integer (`age`), dan bidang tanggal‑waktu (`dob`). Menambahkan atribut tanggal sangat penting untuk analisis GIS temporal.

## Langkah 4: Tambahkan Fitur
### Kasus 1: Mengatur Nilai Secara Individual
```csharp
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
firstFeature.SetValue("dob", new DateTime(1982, 2, 5, 16, 30, 0));
layer.Add(firstFeature);
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
secondFeature.SetValue("dob", new DateTime(1984, 12, 15, 15, 30, 0));
layer.Add(secondFeature);
```
Di sini kami membuat dua titik, mengatur setiap atribut secara terpisah, dan menambahkan fitur‑fitur ke lapisan.

### Kasus 2: Mengatur Nilai Baru untuk Semua Atribut
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
Dengan pendekatan ini kami mengisi semua nilai atribut dalam satu pemanggilan menggunakan array objek—praktis ketika Anda memiliki banyak atribut.

## Mengapa Ini Penting
Membuat shapefile secara programatik memungkinkan Anda mengotomatisasi alur data, menghasilkan dataset uji, atau mengintegrasikan output GIS langsung ke layanan web. Dengan menguasai **cara membuat shapefile** menggunakan Aspose.GIS, Anda memperoleh kontrol penuh atas geometri fitur, skema atribut, dan kepatuhan format file.

## Kesalahan Umum & Tips
- **Pemilih jalur:** Gunakan `Path.Combine` untuk kompatibilitas lintas‑platform alih‑alih menggabungkan string secara manual.  
- **Urutan atribut:** Urutan nilai dalam `SetValues` harus sesuai dengan urutan atribut yang Anda tambahkan.  
- **Penanganan tanggal:** Selalu gunakan `DateTimeKind.Utc` jika data GIS Anda akan dibagikan lintas zona waktu.

## Kesimpulan
Selamat! Anda telah berhasil membuat shapefile baru menggunakan Aspose.GIS untuk .NET. Tutorial ini mencakup dasar‑dasar menyiapkan proyek, mendefinisikan lapisan vektor, dan menambahkan fitur—termasuk atribut tanggal. Saat Anda mengeksplorasi lebih jauh, lihat [dokumentasi](https://reference.aspose.com/gis/net/) untuk fitur dan fungsionalitas lanjutan.

## Pertanyaan yang Sering Diajukan
### T: Bisakah saya menggunakan Aspose.GIS dengan bahasa pemrograman lain?
Aspose.GIS terutama mendukung .NET, tetapi ada versi yang tersedia untuk Java juga.  

### T: Apakah ada trial gratis yang tersedia?
Ya, Anda dapat mengakses trial gratis [di sini](https://releases.aspose.com/).  

### T: Di mana saya dapat menemukan dukungan untuk Aspose.GIS?
Kunjungi [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) untuk dukungan komunitas dan diskusi.  

### T: Bagaimana cara mendapatkan lisensi sementara?
Dapatkan lisensi sementara Anda [di sini](https://purchase.aspose.com/temporary-license/).  

### T: Di mana saya dapat membeli Aspose.GIS untuk .NET?
Anda dapat membeli perpustakaan tersebut [di sini](https://purchase.aspose.com/buy).

---

**Terakhir Diperbarui:** 2026-01-13  
**Diuji Dengan:** Aspose.GIS 24.11 for .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}