---
date: 2026-06-10
description: Pelajari cara menambahkan titik dan menambahkan koordinat ke bentuk saat
  mengiterasi geometri menggunakan Aspose.GIS untuk .NET, toolkit GIS yang kuat untuk
  pengembang .NET.
keywords:
- how to add points
- add coordinates to shape
- Aspose.GIS geometry
linktitle: Cara Menambahkan Titik dan Mengiterasi Geometri di .NET
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to add points and add coordinates to shape while iterating
    over geometry using Aspose.GIS for .NET, the powerful GIS toolkit for .NET developers.
  headline: How to Add Points and Iterate Over Geometry in .NET
  type: TechArticle
- description: Learn how to add points and add coordinates to shape while iterating
    over geometry using Aspose.GIS for .NET, the powerful GIS toolkit for .NET developers.
  name: How to Add Points and Iterate Over Geometry in .NET
  steps:
  - name: Create a `LineString` object
    text: '`LineString` is Aspose.GIS''s geometry type that represents an ordered
      collection of points forming a polyline.'
  - name: Add points to the `LineString`
    text: The `AddPoint` method inserts a new vertex (longitude, latitude) at the
      end of the line. Call it repeatedly to **add coordinates to shape** objects.
  - name: Iterate over the points
    text: '`LineString` implements `IEnumerable<IPoint>`, allowing you to loop through
      each point with a `foreach` statement. This makes extracting X (longitude) and
      Y (latitude) values trivial. The loop prints each point’s X (longitude) and
      Y (latitude) values to the console, allowing you to verify that the p'
  type: HowTo
- questions:
  - answer: '`LineString`'
    question: What is the primary class for point collections?
  - answer: Use `AddPoint(longitude, latitude)`
    question: How do you add a point?
  - answer: Yes, `LineString` implements `IEnumerable<IPoint>`
    question: Can you iterate with a foreach loop?
  - answer: .NET 6+ (or .NET Core 3.1/Framework 4.6+) and Aspose.GIS for .NET library
    question: Prerequisites?
  - answer: Building routes, visualizing tracks, or preprocessing data for spatial
      analysis
    question: Typical use case?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Cara Menambahkan Titik dan Mengiterasi Geometri di .NET
url: /id/net/geometry-processing/iterate-over-points-in-geometry/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menambahkan Titik dan Mengiterasi Geometri di .NET

## Pendahuluan

Jika Anda bekerja dengan data GIS dalam lingkungan .NET, salah satu hal pertama yang perlu Anda ketahui adalah **cara menambahkan titik** ke sebuah geometri dan kemudian bekerja dengan titik‑titik tersebut. Aspose.GIS untuk .NET menyediakan API yang bersih dan berorientasi‑objek yang membuat proses ini menjadi mudah. Dalam tutorial ini kami akan menunjukkan cara membuat sebuah `LineString`, menambahkan titik ke dalamnya, dan mengiterasi titik‑titik tersebut sehingga Anda dapat mengekstrak koordinat atau melakukan analisis lebih lanjut. Anda juga akan melihat cara **menambahkan koordinat ke shape** secara efisien.

## Jawaban Cepat
- **Apa kelas utama untuk koleksi titik?** `LineString`
- **Bagaimana cara menambahkan sebuah titik?** Gunakan `AddPoint(longitude, latitude)`
- **Apakah dapat diiterasi dengan loop foreach?** Ya, `LineString` mengimplementasikan `IEnumerable<IPoint>`
- **Prasyarat?** .NET 6+ (atau .NET Core 3.1/Framework 4.6+) dan pustaka Aspose.GIS untuk .NET
- **Kasus penggunaan tipikal?** Membangun rute, memvisualisasikan trek, atau memproses data untuk analisis spasial  
- **IPoint** mewakili sebuah geometri titik tunggal dengan koordinat X (longitude) dan Y (latitude).

## Apa itu “menambahkan titik” dalam GIS?

Menambahkan titik berarti memasukkan pasangan koordinat individu (longitude, latitude) ke dalam sebuah wadah geometris seperti `LineString`, `Polygon`, atau `MultiPoint`. Setiap titik menjadi sebuah vertex yang mendefinisikan bentuk atau jalur yang Anda modelkan, memungkinkan operasi spasial dan visualisasi. Vertex‑vertex ini kemudian dapat diakses untuk analisis, diekspor ke berbagai format GIS, atau digunakan dalam perhitungan spasial seperti pengukuran jarak atau pengujian interseksi.

## Mengapa menambahkan titik dengan Aspose.GIS?

Anda menambahkan titik dengan Aspose.GIS karena pustaka ini menjamin **penanganan geometri yang type‑safe**, mendukung **lebih dari 30 format vektor dan raster**, serta dapat memproses **dataset ratusan halaman** tanpa harus memuat seluruh file ke memori. API‑nya juga menyediakan iterasi bawaan, operasi spasial, dan konversi format (Shapefile, GeoJSON, KML, dll.) pada setiap platform yang didukung.

## Prasyarat

- Visual Studio 2022 (atau IDE C# apa pun)  
- Paket NuGet Aspose.GIS untuk .NET terpasang  
- Pemahaman dasar tentang sintaks C#  

## Impor Namespace

Mulailah dengan mengimpor namespace yang diperlukan untuk mengakses fungsionalitas Aspose.GIS dalam aplikasi .NET Anda:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Cara Menambahkan Titik ke Geometri?

Anda menambahkan titik dengan membuat sebuah instance `LineString`, memanggil metode `AddPoint` untuk setiap pasangan koordinat, dan kemudian mengiterasi koleksi tersebut bila diperlukan. Pola tiga langkah ini mencakup pembuatan, pengisian, dan penelusuran secara ringkas dan mudah dibaca. **LineString adalah tipe geometri yang mewakili koleksi terurut titik‑titik yang membentuk sebuah polyline.** Pendekatan ini memastikan geometri tetap valid dan siap untuk operasi spasial lebih lanjut seperti perhitungan panjang atau ekspor.

### Langkah 1: Buat objek `LineString`  

`LineString` adalah tipe geometri Aspose.GIS yang mewakili koleksi terurut titik‑titik yang membentuk sebuah polyline.

```csharp
LineString line = new LineString();
```

### Langkah 2: Tambahkan titik ke `LineString`  

Metode `AddPoint` menyisipkan sebuah vertex baru (longitude, latitude) di akhir garis. Panggil metode ini berulang kali untuk **menambahkan koordinat ke shape**.

```csharp
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```

### Langkah 3: Iterasi titik-titik  

`LineString` mengimplementasikan `IEnumerable<IPoint>`, memungkinkan Anda melakukan loop melalui setiap titik dengan pernyataan `foreach`. Hal ini memudahkan ekstraksi nilai X (longitude) dan Y (latitude).

```csharp
foreach (IPoint point in line)
{
    Console.WriteLine(point.X + "," + point.Y);
}
```

Loop tersebut mencetak nilai X (longitude) dan Y (latitude) setiap titik ke konsol, sehingga Anda dapat memverifikasi bahwa titik‑titik telah ditambahkan dengan benar.

## Kasus Penggunaan Umum

- **Perencanaan rute** – Bangun jalur dari log GPS dan kemudian analisis jarak antar waypoint.  
- **Validasi data** – Iterasi titik untuk memastikan mereka berada dalam batas yang diharapkan (misalnya, dalam batas negara).  
- **Visualisasi** – Ekspor `LineString` ke GeoJSON atau Shapefile untuk digunakan dalam alat pemetaan.

## Pertanyaan yang Sering Diajukan

**Q1: Dapatkah Aspose.GIS untuk .NET menangani bentuk geometris lain selain `LineString`?**  
A: Ya, Aspose.GIS mendukung `Point`, `Polygon`, `MultiLineString`, `MultiPolygon`, dan banyak tipe geometri lainnya.

**Q2: Apakah Aspose.GIS cocok untuk proyek komersial maupun pribadi?**  
A: Tentu saja. Opsi lisensi mencakup penggunaan komersial, pribadi, dan edukasi.

**Q3: Apakah Aspose.GIS untuk .NET menawarkan dokumentasi lengkap untuk pemula?**  
A: Ya, produk ini menyertakan dokumentasi ekstensif, referensi API, dan puluhan contoh kode untuk membantu Anda memulai dengan cepat.

**Q4: Dapatkah saya memperluas fungsionalitas Aspose.GIS untuk .NET melalui pengembangan khusus?**  
A: Anda dapat membuat metode ekstensi atau membungkus kelas Aspose.GIS untuk menyesuaikan alur kerja tertentu, memberikan kontrol penuh atas solusi geospasial khusus.

**Q5: Apakah dukungan teknis tersedia untuk pengguna Aspose.GIS?**  
A: Dukungan teknis khusus disediakan melalui forum Aspose dan sistem tiket, memastikan Anda mendapatkan bantuan dengan cepat.

---

**Last Updated:** 2026-06-10  
**Tested With:** Aspose.GIS for .NET 24.5 (latest at time of writing)  
**Author:** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [How to Count Points in Geometry with Aspose.GIS for .NET](/gis/net/geometry-creation/count-points-in-geometry/)
- [How to Add Point to LineString and Convert Geometry to Editable Format with Aspose.GIS](/gis/net/geometry-creation/convert-geometry-to-editable/)
- [Create MultiPoint Geometry with Aspose.GIS for .NET](/gis/net/geometry-creation/create-multipoint-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}