---
date: 2026-01-10
description: Pelajari cara membaca shapefile C# dan mengonversi shapefile poligon
  menjadi linestring menggunakan Aspose.GIS untuk .NET. Tingkatkan pengembangan GIS
  Anda dengan panduan langkah demi langkah yang jelas.
linktitle: Convert Polygon Shapefile to Linestring
second_title: Aspose.GIS .NET API
title: Baca Shapefile C# – Konversi Shapefile Poligon menjadi Linestring
url: /id/net/layer-management/convert-polygon-shapefile-to-linestring/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Baca Shapefile C# – Mengonversi Shapefile Poligon menjadi Linestring

## Pendahuluan
Jika Anda bekerja dengan sistem informasi geografis (GIS) di .NET, **read shapefile c#** adalah langkah pertama yang umum sebelum Anda dapat memanipulasi data. Aspose.GIS membuat proses ini sederhana, memungkinkan Anda mengonversi Shapefile Poligon menjadi Linestring dengan hanya beberapa baris kode. Kemampuan ini sangat berguna ketika Anda perlu mengekstrak fitur linier dari dataset poligon untuk tugas seperti perencanaan rute, analisis jaringan, atau visualisasi data.

## Jawaban Cepat
- **Perpustakaan mana yang membantu Anda membaca shapefile c#?** Aspose.GIS for .NET  
- **Apakah Anda dapat mengonversi poligon menjadi garis?** Yes – use `LineString` with the polygon’s exterior ring.  
- **Apakah saya memerlukan lisensi untuk produksi?** A commercial license is required for production use.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Apakah tersedia versi percobaan?** Absolutely – download a free trial from the Aspose site.

## Apa itu “read shapefile c#”?
Membaca shapefile di C# berarti memuat file `.shp` ke dalam memori sehingga Anda dapat melakukan query, memodifikasi, atau mengubah geometri-geomtrinya. Aspose.GIS menyediakan API sederhana yang mengabstraksi detail level rendah dan memungkinkan Anda fokus pada logika GIS.

## Mengapa mengonversi poligon menjadi garis dengan Aspose.GIS?
- **Pertahankan topologi** – konversi mempertahankan batas luar yang tepat dari setiap poligon.  
- **Kinerja** – perpustakaan dioptimalkan untuk dataset besar, membuat konversi batch menjadi cepat.  
- **Fleksibilitas** – Anda dapat kemudian menulis linestring ke shapefile lain, GeoJSON, atau format lain yang didukung.

## Prasyarat
Sebelum kita masuk ke tutorial, pastikan Anda memiliki hal-hal berikut:

- **Aspose.GIS Library** – Unduh dan instal perpustakaan Aspose.GIS dari [website](https://releases.aspose.com/gis/net/).  
- **Shapefile Data** – Miliki Shapefile Poligon yang siap untuk konversi. Jika Anda belum memiliki, Anda dapat menemukan data contoh atau membuatnya sendiri.  
- **Development Environment** – Siapkan lingkungan pengembangan .NET Anda dengan alat yang diperlukan (Visual Studio, .NET SDK, dll.).

## Impor Namespace
Dalam kode C# Anda, Anda perlu mengimpor namespace Aspose.GIS untuk mengakses kelas dan metode yang diperlukan. Tambahkan namespace berikut di awal file kode Anda:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Cara mengonversi shapefile dari poligon menjadi garis?
Berikut adalah panduan langkah demi langkah yang menunjukkan **cara mengonversi shapefile** data dari poligon menjadi garis menggunakan Aspose.GIS.

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
Baris ini **membuka Shapefile Poligon sumber** sehingga Anda dapat membaca fiturnya.

### Langkah 3: Buat Shapefile Linestring Tujuan
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
Di sini kami **membuat Shapefile Linestring baru** yang akan menyimpan geometri yang telah dikonversi.

### Langkah 4: Iterasi Melalui Fitur Sumber
```csharp
foreach (Feature sourceFeature in source)
{
    // Rest of the code will go here
}
```
Loop ini melintasi setiap fitur poligon dalam file asli.

### Langkah 5: Konversi Poligon menjadi Linestring dan Tulis ke Tujuan
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
Dalam blok ini kami **mengonversi poligon menjadi garis** (`LineString`) dan menambahkan fitur baru ke shapefile tujuan.

## Masalah Umum dan Tips
- **Coordinate System Mismatch** – Pastikan kedua lapisan sumber dan tujuan menggunakan referensi spasial yang sama; jika tidak, garis dapat tampak bergeser.  
- **Large Files** – Saat memproses shapefile yang sangat besar, pertimbangkan untuk streaming fitur alih-alih memuat semuanya ke memori sekaligus.  
- **Null Geometries** – Lindungi terhadap fitur dengan geometri kosong untuk menghindari pengecualian runtime.

## Pertanyaan yang Sering Diajukan

**Q: Apakah Aspose.GIS kompatibel dengan semua versi .NET?**  
A: Ya, Aspose.GIS mendukung berbagai versi .NET, memastikan kompatibilitas dengan lingkungan pengembangan Anda.

**Q: Bisakah saya menggunakan Aspose.GIS untuk proyek komersial?**  
A: Ya, Anda dapat. Untuk menggunakan Aspose.GIS dalam proyek komersial, pertimbangkan membeli lisensi [di sini](https://purchase.aspose.com/buy).

**Q: Apakah ada contoh atau dokumentasi yang tersedia?**  
A: Ya, Anda dapat menemukan dokumentasi lengkap dan contoh pada [halaman dokumentasi](https://reference.aspose.com/gis/net/).

**Q: Apakah tersedia versi percobaan?**  
A: Ya, Anda dapat menjelajahi Aspose.GIS dengan percobaan gratis dengan mengunjungi [tautan ini](https://releases.aspose.com/).

**Q: Di mana saya dapat mencari bantuan atau dukungan?**  
A: Kunjungi [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) untuk pertanyaan bantuan atau dukungan apa pun.

---

**Terakhir Diperbarui:** 2026-01-10  
**Diuji Dengan:** Aspose.GIS for .NET (latest release)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}