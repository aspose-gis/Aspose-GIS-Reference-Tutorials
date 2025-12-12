---
date: 2025-12-12
description: Pelajari cara membuat lapisan vektor dan menambahkan geometri string
  melingkar menggunakan Aspose.GIS untuk .NET – cara cepat membangun aplikasi GIS.
linktitle: Create Circular String Geometry
second_title: Aspose.GIS .NET API
title: Buat Layer Vektor & String Lingkaran di Aspose.GIS untuk .NET
url: /id/net/geometry-creation/create-circular-string-geometry/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Layer Vektor dan Geometri Circular String dengan Aspose.GIS untuk .NET

## Pendahuluan
Jika Anda sedang membangun aplikasi GIS di platform .NET, langkah pertama biasanya **membuat objek layer vektor** yang menyimpan fitur spasial Anda. Aspose.GIS untuk .NET membuat proses ini sederhana dan memungkinkan Anda memperkaya layer tersebut dengan geometri lanjutan seperti circular string. Pada tutorial ini Anda akan belajar cara membuat layer vektor, menambahkan geometri circular string, dan menyimpan hasilnya sebagai Shapefile—semua dengan kode C# yang bersih dan siap produksi.

## Jawaban Cepat
- **Apa arti “membuat layer vektor”?** Itu membuat sebuah kontainer (layer) baru yang dapat menampung fitur spasial seperti titik, garis, atau poligon.  
- **Kelas mana yang mewakili circular string?** `CircularString` dari `Aspose.Gis.Geometries`.  
- **Bisakah saya menyimpan layer sebagai Shapefile?** Ya – gunakan `Drivers.Shapefile` saat membuat layer.  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Lisensi sementara dapat digunakan untuk evaluasi; lisensi penuh diperlukan untuk produksi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Apa itu “membuat layer vektor”?
Layer vektor adalah pengelompokan logis dari fitur vektor (titik, garis, poligon) yang disimpan dalam satu sumber data. Di Aspose.GIS Anda menginstansiasi sebuah layer dengan memanggil `VectorLayer.Create`, memberikan jalur file target dan driver yang diinginkan (misalnya, Shapefile). Setelah layer ada, Anda dapat menambahkan fitur, menetapkan geometri, dan melakukan operasi spasial.

## Mengapa menambahkan circular string?
Circular string adalah jenis **geometri** yang mendekati busur menggunakan urutan titik. Ini berguna untuk merepresentasikan jalan melengkung, tikungan sungai, atau fitur apa pun yang memerlukan kurva halus tanpa harus menggunakan banyak segmen garis kecil.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki:

- **.NET Framework atau .NET Core** yang terpasang di mesin Anda.  
- **Pustaka Aspose.GIS untuk .NET** – unduh dari situs resmi **[di sini](https://releases.aspose.com/gis/net/)**.  
- Sebuah IDE seperti **Visual Studio** atau **JetBrains Rider**.  
- Familiaritas dasar dengan pemrograman **C#**.

## Impor Namespace
Tambahkan namespace yang diperlukan ke file C# Anda:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Panduan Langkah‑per‑Langkah

### Langkah 1: Tentukan jalur file output
Atur lokasi di mana Shapefile akan ditulis.

```csharp
string path = "Your Document Directory" + "CreateCircularString_out.shp";
```

Ganti `"Your Document Directory"` dengan jalur folder sebenarnya di sistem Anda.

### Langkah 2: **Buat layer vektor**
Buka sebuah `VectorLayer` menggunakan metode `Create`. Inilah inti dari operasi **membuat layer vektor**.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
```

### Langkah 3: Buat fitur baru
Sebuah fitur mewakili satu catatan spasial di dalam layer.

```csharp
    var feature = layer.ConstructFeature();
```

### Langkah 4: Bangun geometri circular string
Tambahkan titik‑titik yang mendefinisikan bentuk melengkung. Urutan titik menciptakan sebuah busur yang mulai dan berakhir pada lokasi yang sama, membentuk circular string tertutup.

```csharp
    var circularString = new CircularString();
    circularString.AddPoint(0, 0);
    circularString.AddPoint(1, 1);
    circularString.AddPoint(2, 0);
    circularString.AddPoint(1, -1);
    circularString.AddPoint(0, 0);
```

### Langkah 5: Tetapkan geometri dan tambahkan fitur ke layer
Hubungkan geometri ke fitur dan simpan di dalam layer.

```csharp
    feature.Geometry = circularString;
    layer.Add(feature);
}
```

Saat blok `using` berakhir, layer secara otomatis di‑flush ke Shapefile di disk.

## Masalah Umum & Solusi
| Masalah | Solusi |
|-------|----------|
| **Jalur file tidak valid** | Pastikan direktori ada dan Anda memiliki izin menulis. |
| **CircularString muncul sebagai garis lurus** | Verifikasi bahwa titik‑titik ditambahkan dalam urutan yang benar; titik pertama dan terakhir harus identik untuk bentuk tertutup. |
| **Pengecualian lisensi** | Terapkan lisensi sementara selama pengembangan atau beli lisensi penuh untuk penggunaan produksi. |

## Pertanyaan yang Sering Diajukan

### Apakah Aspose.GIS untuk .NET kompatibel dengan semua versi .NET Framework?
Ya, Aspose.GIS untuk .NET dirancang untuk bekerja dengan berbagai versi .NET, mulai dari Framework 4.5 hingga rilis .NET 8 terbaru.

### Bisakah saya mengintegrasikan Aspose.GIS untuk .NET dengan pustaka GIS lain?
Tentu! Anda dapat membaca data dengan pustaka lain, memanipulasinya dengan Aspose.GIS, lalu menulis kembali, berkat API yang fleksibel.

### Apakah Aspose.GIS untuk .NET mendukung visualisasi data spasial?
Ya, pustaka ini menyertakan utilitas rendering yang memungkinkan Anda menghasilkan peta dan representasi visual dari geometri Anda.

### Apakah ada forum komunitas tempat saya dapat meminta bantuan tentang Aspose.GIS untuk .NET?
Ya, Anda dapat mengunjungi forum Aspose.GIS **[di sini](https://forum.aspose.com/c/gis/33)** untuk mengajukan pertanyaan dan berbagi pengalaman.

### Bisakah saya memperoleh lisensi sementara untuk mengevaluasi Aspose.GIS untuk .NET?
Tentu! Lisensi evaluasi sementara tersedia **[di sini](https://purchase.aspose.com/temporary-license/)**.

### Bagaimana cara menambahkan geometri yang lebih kompleks (misalnya, MultiLineString) ke layer yang sama?
Buat objek geometri yang sesuai (misalnya, `MultiLineString`), isi dengan objek `LineString` individual, tetapkan ke `feature.Geometry`, dan tambahkan fitur seperti yang kita lakukan dengan circular string.

## Kesimpulan
Dengan mengikuti langkah‑langkah ini Anda kini tahu cara **membuat layer vektor** dan memperkaya mereka dengan geometri circular string menggunakan Aspose.GIS untuk .NET. Dasar ini memungkinkan Anda membangun solusi GIS yang lebih kaya—baik untuk memetakan jaringan transportasi, memvisualisasikan data lingkungan, atau mengembangkan alat analitik spasial khusus.

---

**Terakhir Diperbarui:** 2025-12-12  
**Diuji Dengan:** Aspose.GIS 24.11 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}