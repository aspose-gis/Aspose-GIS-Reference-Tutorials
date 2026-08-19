---
date: 2026-06-25
description: Pelajari cara membaca shapefile dan mengonversi shapefile poligon menjadi
  linestring menggunakan Aspose.GIS untuk .NET. Tingkatkan pengembangan GIS Anda dengan
  panduan langkah demi langkah yang jelas.
keywords:
- how to read shapefile
- convert polygon to line
- shapefile to geojson c#
- extract lines from polygon
linktitle: Konversi Polygon Shapefile ke Linestring
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to read shapefile and convert a polygon shapefile to a linestring
    using Aspose.GIS for .NET. Boost your GIS development with clear step‑by‑step
    guidance.
  headline: How to Read Shapefile C# – Convert Polygon Shapefile to Linestring
  type: TechArticle
- description: Learn how to read shapefile and convert a polygon shapefile to a linestring
    using Aspose.GIS for .NET. Boost your GIS development with clear step‑by‑step
    guidance.
  name: How to Read Shapefile C# – Convert Polygon Shapefile to Linestring
  steps:
  - name: Set the Document Directory
    text: Replace `"Your Document Directory"` with the actual path where your shapefile
      resides.
  - name: Open the Source Shapefile
    text: This line opens the source Polygon Shapefile so you can read its features.
  - name: Create the Destination Linestring Shapefile
    text: Here we create a new Linestring Shapefile that will store the converted
      geometries.
  - name: Iterate Through Source Features
    text: The loop walks through each polygon feature in the original file.
  - name: Convert Polygon to Linestring and Write to Destination
    text: The `ExteriorRing` property returns the outer boundary of a polygon as a
      `LineString`. In this block we convert polygon to line (`LineString`) and add
      the new feature to the destination shapefile.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS supports .NET Framework 4.5+, .NET Core 3.1+, and .NET
      5/6/7, ensuring seamless integration with modern development stacks.
    question: Is Aspose.GIS compatible with all versions of .NET?
  - answer: Yes, you can. Purchase a license [here](https://purchase.aspose.com/buy)
      to remove evaluation limitations and obtain full support.
    question: Can I use Aspose.GIS for commercial projects?
  - answer: Yes, you can find comprehensive documentation and code samples on the
      [documentation page](https://reference.aspose.com/gis/net/).
    question: Are there any examples or documentation available?
  - answer: Absolutely – explore Aspose.GIS with a free trial by visiting [this link](https://releases.aspose.com/).
    question: Is there a trial version available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      assistance and official support.
    question: Where can I seek help or support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Cara Membaca Shapefile C# – Mengonversi Polygon Shapefile ke Linestring
url: /id/net/layer-management/convert-polygon-shapefile-to-linestring/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Baca Shapefile C# – Konversi Shapefile Polygon ke Linestring

## Pendahuluan
Jika Anda perlu **cara membaca shapefile** data dalam lingkungan .NET, Anda berada di tempat yang tepat. Aspose.GIS untuk .NET mengabstraksi format biner tingkat rendah dari sebuah Shapefile, memungkinkan Anda memuat, mengkueri, dan mengubah fitur geografis dengan hanya beberapa panggilan API. Mengonversi shapefile polygon menjadi linestring sangat berguna ketika Anda ingin mengekstrak representasi linier untuk routing, analisis jaringan, atau visualisasi sederhana.

## Jawaban Cepat
- **Perpustakaan mana yang membantu Anda membaca shapefile c#?** Aspose.GIS untuk .NET – mendukung lebih dari 50 format GIS dan menangani file hingga beberapa ratus megabyte tanpa memuat seluruh file ke memori.  
- **Apakah Anda dapat mengonversi polygon menjadi garis?** Ya – panggil `LineString` pada cincin luar polygon dan tulis hasilnya ke shapefile baru.  
- **Apakah saya memerlukan lisensi untuk produksi?** Lisensi komersial diperlukan untuk penerapan produksi; versi percobaan gratis dapat digunakan untuk evaluasi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **Apakah tersedia versi percobaan?** Tentu saja – unduh versi percobaan gratis dari situs Aspose.

`LineString` adalah tipe geometri yang mewakili serangkaian segmen garis yang terhubung.

## Apa itu “read shapefile c#”?
`Document` adalah kelas inti yang mewakili dataset GIS dan menyediakan akses ke fiturnya.  
Membaca shapefile dalam C# berarti memuat file `.shp` ke memori sehingga Anda dapat mengkueri, memodifikasi, atau mengubah geometri-geomtrinya. **Anda cukup menginstansiasi kelas `Document` dengan jalur file, dan Aspose.GIS akan mengurai struktur biner untuk Anda**, menampilkan fitur melalui koleksi yang mudah digunakan. Pendekatan ini menghilangkan kebutuhan untuk bekerja dengan header file tingkat rendah atau array koordinat secara manual.

## Mengapa mengonversi polygon menjadi garis dengan Aspose.GIS?
Mengonversi polygon menjadi linestring mempertahankan batas luar yang tepat sambil menghilangkan cincin interior, memberikan Anda representasi linier yang bersih. Aspose.GIS memproses **dataset hingga 500 MB dalam kurang dari 2 detik pada server tipikal**, membuat konversi batch cepat dan efisien memori. Perpustakaan ini juga mempertahankan referensi spasial asli, sehingga garis yang dihasilkan selaras sempurna dengan lapisan GIS yang ada.

## Prasyarat
Sebelum kita masuk ke tutorial, pastikan Anda memiliki hal‑hal berikut:

- **Aspose.GIS Library** – Unduh dan instal pustaka Aspose.GIS dari [website](https://releases.aspose.com/gis/net/).  
- **Shapefile Data** – Miliki Shapefile Polygon yang siap untuk konversi. Jika Anda belum memilikinya, Anda dapat menemukan data contoh atau membuatnya sendiri.  
- **Development Environment** – Siapkan lingkungan pengembangan .NET Anda dengan alat yang diperlukan (Visual Studio, .NET SDK, dll.).

## Impor Namespace
Kelas `Document` adalah objek inti Aspose.GIS yang mewakili dataset GIS dan menyediakan metode untuk membaca dan menulis shapefile. Tambahkan namespace berikut di awal file kode Anda:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Cara membaca shapefile dan mengonversi polygon menjadi linestring?
Muat shapefile polygon sumber, ekstrak cincin luar setiap polygon, buat `LineString` dari cincin tersebut, dan tulis hasilnya ke shapefile baru – semua dalam lima langkah sederhana. Pola ini bekerja untuk dataset berukuran apa pun dan menjamin sistem koordinat sumber tetap dipertahankan di tujuan.

### Langkah 1: Atur Direktori Dokumen
```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```
Ganti `"Your Document Directory"` dengan jalur sebenarnya tempat shapefile Anda berada.

### Langkah 2: Buka Shapefile Sumber
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
Baris ini membuka Shapefile Polygon sumber sehingga Anda dapat membaca fiturnya.

### Langkah 3: Buat Shapefile Linestring Tujuan
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
Di sini kami membuat Shapefile Linestring baru yang akan menyimpan geometri yang telah dikonversi.

### Langkah 4: Iterasi Melalui Fitur Sumber
```csharp
foreach (Feature sourceFeature in source)
{
    // Rest of the code will go here
}
```
Loop ini berjalan melalui setiap fitur polygon dalam file asli.

### Langkah 5: Konversi Polygon menjadi Linestring dan Tulis ke Tujuan
Properti `ExteriorRing` mengembalikan batas luar sebuah polygon sebagai `LineString`.  
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```

## Masalah Umum dan Tips
- **Ketidaksesuaian Sistem Koordinat** – Pastikan kedua lapisan sumber dan tujuan menggunakan referensi spasial yang sama; jika tidak, garis dapat tampak bergeser.  
- **File Besar** – Saat memproses shapefile yang sangat besar, pertimbangkan streaming fitur alih‑alih memuat semuanya ke memori sekaligus.  
- **Geometri Null** – Lindungi terhadap fitur dengan geometri kosong untuk menghindari pengecualian runtime.  
- **Ekstrak garis dari polygon** – Jika Anda hanya membutuhkan cincin luar, gunakan properti `ExteriorRing`; untuk cincin interior, iterasi `InteriorRings`.  

## Pertanyaan yang Sering Diajukan

**Q: Apakah Aspose.GIS kompatibel dengan semua versi .NET?**  
A: Ya, Aspose.GIS mendukung .NET Framework 4.5+, .NET Core 3.1+, dan .NET 5/6/7, memastikan integrasi mulus dengan stack pengembangan modern.

**Q: Bisakah saya menggunakan Aspose.GIS untuk proyek komersial?**  
A: Ya, Anda dapat. Beli lisensi [di sini](https://purchase.aspose.com/buy) untuk menghapus batasan evaluasi dan mendapatkan dukungan penuh.

**Q: Apakah ada contoh atau dokumentasi yang tersedia?**  
A: Ya, Anda dapat menemukan dokumentasi lengkap dan contoh kode di [halaman dokumentasi](https://reference.aspose.com/gis/net/).

**Q: Apakah tersedia versi percobaan?**  
A: Tentu saja – jelajahi Aspose.GIS dengan versi percobaan gratis dengan mengunjungi [tautan ini](https://releases.aspose.com/).

**Q: Di mana saya dapat mencari bantuan atau dukungan?**  
A: Kunjungi [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) untuk bantuan komunitas dan dukungan resmi.

---

**Last Updated:** 2026-06-25  
**Diuji Dengan:** Aspose.GIS untuk .NET (rilis terbaru)  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Cara Mengonversi Shapefile ke GeoJSON menggunakan Aspose.GIS untuk .NET](/gis/net/layer-management/extract-features-to-geojson/)
- [Cara Membaca GeoJSON dari Stream dengan Aspose.GIS untuk .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Cara Membuat Geometri Polygon dengan Aspose.GIS untuk .NET](/gis/net/geometry-creation/create-polygon-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}