---
date: 2026-06-30
description: Pelajari cara membuat shapefile menggunakan Aspose.GIS untuk .NET. Panduan
  langkah demi langkah ini menunjukkan cara mendefinisikan lapisan vektor, menambahkan
  atribut tanggal, dan mengelola data spasial secara efisien.
keywords:
- how to create shapefile
- temporal gis shapefile
- Aspose.GIS vector layer
- GIS data automation
linktitle: Buat Shapefile Baru
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create shapefile using Aspose.GIS for .NET. This step‑by‑step
    guide shows you how to define a vector layer, add a date attribute, and manage
    spatial data efficiently.
  headline: How to Create Shapefile with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS primarily supports .NET, but there are versions available for
      Java as well.
    question: Can I use Aspose.GIS with other programming languages?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I find support for Aspose.GIS?
  - answer: Get your temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license?
  - answer: You can buy the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Cara Membuat Shapefile dengan Aspose.GIS untuk .NET
url: /id/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Shapefile Baru

## Pendahuluan
Jika Anda menyelami pengembangan sistem informasi geografis (GIS) dengan .NET, Aspose.GIS adalah solusi utama Anda untuk **cara membuat shapefile** secara programatis. Perpustakaan ini memberi Anda kontrol penuh atas lapisan vektor, skema atribut, dan kepatuhan format file, sehingga Anda dapat mengotomatisasi alur data atau menghasilkan dataset uji dalam hitungan menit.

## Jawaban Cepat
- **Apa yang diajarkan tutorial ini?** Cara membuat shapefile baru, mendefinisikan lapisan vektor, dan menambahkan atribut (termasuk bidang tanggal).  
- **Perpustakaan mana yang diperlukan?** Aspose.GIS for .NET.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis cukup untuk belajar; lisensi komersial diperlukan untuk produksi.  
- **IDE apa yang harus saya gunakan?** Visual Studio (any recent version).  
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk contoh dasar.

## Cara membuat shapefile dengan Aspose.GIS untuk .NET?
Muat perpustakaan Aspose.GIS, atur folder output, buat `VectorLayer`, definisikan atribut, dan tambahkan fitur—seluruh alur kerja ini dapat ditulis dalam kurang dari 30 baris C#. Perpustakaan ini menangani pembuatan geometri, pengetikan atribut, dan penulisan file secara otomatis, sehingga Anda tidak perlu mengelola spesifikasi Shapefile tingkat rendah secara manual.

## Prasyarat
Sebelum kita melompat ke tutorial, pastikan Anda memiliki prasyarat berikut:
- Pemahaman dasar tentang bahasa pemrograman C#.  
- Visual Studio terpasang di mesin Anda.  
- Perpustakaan Aspose.GIS untuk .NET. Anda dapat mengunduhnya [di sini](https://releases.aspose.com/gis/net/).

## Impor Namespace
Start by importing the necessary namespaces to leverage the functionality of Aspose.GIS:

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
Kelas `VectorLayer` mewakili satu lapisan shapefile yang menyimpan data geometri dan atribut.  
Pada langkah ini kami mendefinisikan lapisan vektor dan mendeklarasikan tiga atribut: bidang teks (`name`), bidang integer (`age`), dan bidang tanggal‑waktu (`dob`). Menambahkan atribut tanggal sangat penting untuk analisis **shapefile GIS temporal**.

```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```

## Langkah 4: Tambahkan Fitur
### Kasus 1: Mengatur Nilai Secara Individual
Metode `SetValues` menetapkan nilai atribut ke sebuah fitur dalam urutan yang telah didefinisikan.  
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
Di sini kami membuat dua titik, mengatur setiap atribut secara terpisah, dan menambahkan fitur ke lapisan.

### Kasus 2: Mengatur Nilai Baru untuk Semua Atribut
Sebagai alternatif, Anda dapat memberikan semua nilai atribut sekaligus menggunakan `SetValues` dengan array objek.  
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
Dalam pendekatan ini kami mengisi semua nilai atribut dalam satu panggilan menggunakan array objek—praktis ketika Anda memiliki banyak atribut.

## Mengapa Ini Penting?
Membuat shapefile secara programatis memungkinkan Anda mengotomatisasi alur data, menghasilkan dataset uji, atau menyematkan output GIS langsung ke layanan web. Aspose.GIS mendukung **lebih dari 30 format vektor dan raster** dan dapat menulis shapefile berukuran ratusan halaman tanpa memuat seluruh file ke memori, memberikan kecepatan dan skalabilitas.

## Kesalahan Umum & Tips
- **Pemisah jalur:** Gunakan `Path.Combine` untuk kompatibilitas lintas‑platform alih-alih menggabungkan string.  
- **Urutan atribut:** Urutan nilai dalam `SetValues` harus sesuai dengan urutan atribut yang Anda tambahkan.  
- **Penanganan tanggal:** Selalu gunakan `DateTimeKind.Utc` jika data GIS Anda akan dibagikan lintas zona waktu.

## Kesimpulan
Selamat! Anda telah berhasil membuat shapefile baru menggunakan Aspose.GIS untuk .NET. Tutorial ini mencakup dasar-dasar menyiapkan proyek Anda, mendefinisikan lapisan vektor, dan menambahkan fitur—termasuk atribut tanggal. Saat Anda menjelajah lebih jauh, lihat [dokumentasi](https://reference.aspose.com/gis/net/) untuk fitur dan fungsionalitas lanjutan.

## Pertanyaan yang Sering Diajukan
**Q: Bisakah saya menggunakan Aspose.GIS dengan bahasa pemrograman lain?**  
A: Aspose.GIS terutama mendukung .NET, tetapi ada versi yang tersedia untuk Java juga.  

**Q: Apakah tersedia percobaan gratis?**  
A: Ya, Anda dapat mengakses percobaan gratis [di sini](https://releases.aspose.com/).  

**Q: Di mana saya dapat menemukan dukungan untuk Aspose.GIS?**  
A: Kunjungi [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) untuk dukungan komunitas dan diskusi.  

**Q: Bagaimana saya dapat memperoleh lisensi sementara?**  
A: Dapatkan lisensi sementara Anda [di sini](https://purchase.aspose.com/temporary-license/).  

**Q: Di mana saya dapat membeli Aspose.GIS untuk .NET?**  
A: Anda dapat membeli perpustakaan tersebut [di sini](https://purchase.aspose.com/buy).  

---

**Terakhir Diperbarui:** 2026-06-30  
**Diuji Dengan:** Aspose.GIS 24.11 untuk .NET  
**Penulis:** Aspose

## Tutorial Terkait

- [Dapatkan Atribut Lapisan – Ambil Informasi Atribut Lapisan dengan Aspose.GIS untuk .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Buat Lapisan Vektor dan Atur Sistem Referensi Spasial Lapisan](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Buat Lapisan Vektor dalam File GDB – Tutorial Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}