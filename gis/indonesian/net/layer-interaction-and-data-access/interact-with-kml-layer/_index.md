---
date: 2026-01-07
description: Pelajari cara menulis file KML menggunakan Aspose.GIS untuk .NET, cara
  membuat KML, menambahkan atribut boolean, dan membuat line string dalam aplikasi
  Anda.
linktitle: Interact with KML Layer
second_title: Aspose.GIS .NET API
title: Cara Menulis File KML dengan Aspose.GIS untuk .NET
url: /id/net/layer-interaction-and-data-access/interact-with-kml-layer/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menulis File KML dengan Aspose.GIS untuk .NET

## Pendahuluan
Di dunia yang didorong oleh data saat ini, kemampuan untuk **menulis file KML** secara programatik memberi Anda kekuatan untuk berbagi informasi geografis lintas platform, memvisualisasikan rute pada peta, dan mengintegrasikan data lokasi ke dalam aplikasi web atau seluler. Aspose.GIS untuk .NET membuat proses ini sederhana, memungkinkan Anda fokus pada logika daripada kerumitan format file. Dalam tutorial ini kami akan menjelaskan cara membuat lapisan KML, menambahkan atribut (termasuk atribut boolean), dan membangun geometri line string—semua dengan kode langkah demi langkah yang jelas.

## Jawaban Cepat
- **Apa arti “menulis file KML”?** Menghasilkan dokumen KML (Keyhole Markup Language) yang menggambarkan fitur geografis seperti titik, garis, dan poligon.  
- **Perpustakaan mana yang terbaik untuk .NET?** Aspose.GIS untuk .NET menyediakan API fluent untuk membuat dan mengedit file KML.  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Versi percobaan gratis dapat digunakan untuk evaluasi; lisensi diperlukan untuk penggunaan produksi.  
- **Bisakah saya menambahkan atribut khusus?** Ya – Anda dapat menambahkan atribut string, integer, boolean, dan double ke setiap fitur.  
- **Apakah pembuatan geometri didukung?** Tentu – Anda dapat membuat titik, line string, poligon, dan lainnya.

## Prasyarat
- Aspose.GIS untuk .NET: Unduh dan instal perpustakaan dari [halaman unduhan Aspose.GIS untuk .NET](https://releases.aspose.com/gis/net/).
- Lingkungan Pengembangan: Siapkan lingkungan pengembangan yang sesuai, seperti Visual Studio, untuk mengintegrasikan Aspose.GIS dengan mulus ke dalam proyek .NET Anda.

## Impor Namespace
Sebelum kita mulai berinteraksi dengan lapisan KML, pastikan untuk menyertakan namespace yang diperlukan dalam proyek Anda. Langkah ini memastikan Anda memiliki akses ke kelas dan metode yang dibutuhkan untuk manipulasi data geospasial.

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Drawing;
using System.Threading;
using Aspose.Gis.Formats.Kml;
using Aspose.Gis.Formats.Kml.Styles;
using Aspose.Gis.Geometries;
using Point = Aspose.Gis.Geometries.Point;
```

## Langkah 1: Atur Direktori Dokumen
Tentukan jalur ke direktori dokumen Anda di mana file KML akan disimpan.

```csharp
string dataDir = "Your Document Directory";
```

## Langkah 2: Buat Lapisan KML
Inisialisasi lapisan KML menggunakan Aspose.GIS, dengan menentukan jalur untuk file KML.

```csharp
using (var layer = Drivers.Kml.CreateLayer(dataDir + "Kml_File_out.kml"))
{
```

## Langkah 3: Definisikan Atribut (tambahkan atribut boolean)
Tambahkan atribut ke lapisan KML untuk mewakili berbagai tipe data seperti string, integer, **boolean**, dan double. Di sinilah Anda “menambahkan atribut boolean” ke setiap fitur.

```csharp
layer.Attributes.Add(new FeatureAttribute("string_data", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("int_data", AttributeDataType.Integer));
layer.Attributes.Add(new FeatureAttribute("bool_data", AttributeDataType.Boolean));
layer.Attributes.Add(new FeatureAttribute("float_data", AttributeDataType.Double));
```

## Langkah 4: Bangun dan Isi Fitur (buat line string)
Bangun fitur yang mewakili entitas geospasial dan tetapkan nilai untuk atribut yang telah didefinisikan. Di sini kami **membuat line string** geometry untuk menggambarkan jalur sederhana.

```csharp
Feature feature = layer.ConstructFeature();
feature.SetValue("string_data", "string value");
feature.SetValue("int_data", 10);
feature.SetValue("bool_data", true);
feature.SetValue("float_data", 3.14);
feature.Geometry = new LineString(new[] { new Point(0, 0), new Point(1, 1) });
layer.Add(feature);
```

## Langkah 5: Tambahkan Fitur Lain
Ulangi proses untuk menambahkan fitur kedua dengan nilai atribut yang berbeda dan geometri null.

```csharp
Feature feature2 = layer.ConstructFeature();
feature2.SetValue("string_data", "string value2");
feature2.SetValue("int_data", 100);
feature2.SetValue("bool_data", false);
feature2.SetValue("float_data", 3.1415);
feature2.Geometry = Geometry.Null;
layer.Add(feature2);
```

## Cara Menulis File KML – Menggabungkan Semua Langkah
Dengan mengikuti langkah-langkah di atas, Anda kini memiliki file KML yang berfungsi penuh yang berisi atribut khusus (termasuk flag boolean) dan geometri line string. Anda dapat membuka `Kml_File_out.kml` yang dihasilkan di Google Earth, ArcGIS, atau penampil GIS apa pun yang mendukung KML.

## Masalah Umum & Pemecahan Masalah
- **Kesalahan jalur file** – Pastikan `dataDir` diakhiri dengan pemisah jalur (`\` atau `/`) yang sesuai untuk OS Anda.  
- **Lisensi hilang** – Versi percobaan dapat digunakan untuk evaluasi, tetapi versi berlisensi diperlukan untuk menulis file KML tanpa batas.  
- **Geometri null** – Menetapkan `Geometry.Null` memang disengaja untuk fitur tanpa data spasial; hapus jika Anda selalu memerlukan geometri.

## Pertanyaan yang Sering Diajukan
### Apakah Aspose.GIS kompatibel dengan format GIS lainnya?
Ya, Aspose.GIS mendukung berbagai format GIS, termasuk shapefile, GeoJSON, dan KML.

### Bisakah saya memvisualisasikan data geospasial yang dibuat menggunakan Aspose.GIS?
Tentu! Aspose.GIS terintegrasi mulus dengan pustaka pemetaan, memungkinkan Anda memvisualisasikan data geospasial Anda.

### Apakah ada versi percobaan yang tersedia untuk Aspose.GIS?
Ya, Anda dapat menjelajahi fitur Aspose.GIS dengan mengunduh [versi percobaan gratis](https://releases.aspose.com/).

### Bagaimana saya dapat mendapatkan dukungan untuk Aspose.GIS?
Kunjungi [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) untuk dukungan komunitas atau jelajahi opsi dukungan premium [di sini](https://purchase.aspose.com/buy).

### Apakah lisensi sementara tersedia untuk Aspose.GIS?
Ya, Anda dapat memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

## Pertanyaan Tambahan yang Sering Diajukan

**Q: Bagaimana cara **membuat KML** dengan gaya khusus?**  
A: Gunakan namespace `Aspose.Gis.Formats.Kml.Styles` untuk mendefinisikan ikon, warna garis, dan gaya label sebelum menambahkan fitur.

**Q: Bisakah saya menulis file KML besar secara efisien?**  
A: Tulis fitur dalam batch dan flush lapisan secara berkala untuk menjaga penggunaan memori tetap rendah.

**Q: Apakah Aspose.GIS mendukung .NET Core dan .NET 6+?**  
A: Ya, perpustakaan ini sepenuhnya kompatibel dengan .NET Core, .NET 5, dan .NET 6.

---

**Terakhir Diperbarui:** 2026-01-07  
**Diuji Dengan:** Aspose.GIS 24.10 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}