---
date: 2026-02-15
description: Pelajari cara membuat lapisan vektor dan geometri poligon melengkung
  menggunakan Aspose.GIS untuk .NET, termasuk geometri string melingkar untuk cincin
  interior.
linktitle: Create Curve Polygon Geometry
second_title: Aspose.GIS .NET API
title: Buat lapisan vektor dan poligon melengkung dengan Aspose.GIS
url: /id/net/geometry-creation/create-curve-polygon-geometry/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat lapisan vektor dan poligon melengkung dengan Aspose.GIS

## Pendahuluan
Di dunia pengembangan Sistem Informasi Geografis (GIS), **Aspose.GIS for .NET** menonjol sebagai perpustakaan yang kuat untuk membuat, mengedit, dan memanipulasi data spasial. Pada tutorial ini Anda akan belajar cara **membuat lapisan vektor** dan **membuat geometri poligon melengkung** langkah demi langkah, sehingga Anda dapat menyematkan bentuk yang canggih langsung ke dalam aplikasi GIS Anda. Pada akhir panduan Anda akan memiliki Shapefile siap pakai yang berisi poligon melengkung dengan cincin luar dan dalam.

## Jawaban Cepat
- **Perpustakaan apa yang digunakan?** Aspose.GIS for .NET  
- **Tugas utama?** Membuat geometri poligon melengkung, menyimpannya sebagai Shapefile, dan **membuat lapisan vektor** untuk data tersebut  
- **Waktu implementasi tipikal?** 5–10 menit untuk bentuk dasar  
- **Prasyarat?** Lingkungan pengembangan .NET dan paket NuGet Aspose.GIS  
- **Apakah saya dapat melihat hasilnya?** Ya – semua penampil GIS yang mendukung Shapefile (mis., QGIS, ArcGIS)

## Apa itu Poligon Melengkung?
*Poligon melengkung* adalah poligon yang tepinya dapat terdiri dari segmen melengkung (seperti busur melingkar) alih‑alih hanya garis lurus. Ini memungkinkan pemodelan yang lebih realistis dari fitur alami seperti danau, pulau, atau bentuk apa pun yang diuntungkan oleh batas yang halus.

## Mengapa membuat geometri poligon melengkung dengan Aspose.GIS?
- **Presisi** – Tepi melengkung disimpan secara matematis, mempertahankan geometri yang tepat.  
- **Interoperabilitas** – Shapefile yang dihasilkan bekerja dengan semua platform GIS utama.  
- **Produktivitas** – Kode minimal diperlukan untuk mendefinisikan bentuk kompleks, mempercepat siklus pengembangan.  
- **Fleksibilitas** – Anda dapat **membuat lapisan vektor** secara dinamis dan melampirkan geometri apa pun yang Anda butuhkan.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki hal‑hal berikut:

1. **Aspose.GIS for .NET** terpasang. Unduh dari [Aspose.GIS for .NET releases page](https://releases.aspose.com/gis/net/).  
2. Pengetahuan kerja tentang C# dan ekosistem .NET.  
3. IDE seperti Visual Studio (versi terbaru apa pun) atau Visual Studio Code.

## Impor Namespace
Pada langkah ini, kita akan mengimpor namespace yang diperlukan untuk menggunakan fungsionalitas Aspose.GIS dalam kode kita.

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

### Langkah 1: Tentukan Jalur File
Pertama, tentukan di mana Shapefile Poligon Melengkung yang dihasilkan akan disimpan.

```csharp
string path = "Your Document Directory" + "CreateCurvePolygon_out.shp";
```

Ganti `"Your Document Directory"` dengan jalur folder sebenarnya di mesin Anda.

### Langkah 2: Buat Lapisan Vektor
Instansiasi lapisan vektor baru menggunakan driver Shapefile. Ini adalah langkah **membuat lapisan vektor** yang menyiapkan wadah untuk geometri kita.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Your code for creating the Curve Polygon Geometry will go here
}
```

`using` statement menjamin bahwa sumber daya dilepaskan dengan benar.

### Langkah 3: Bangun Fitur
Buat objek fitur yang akan menampung geometri dan data atribut apa pun.

```csharp
var feature = layer.ConstructFeature();
```

### Langkah 4: Buat Geometri Poligon Melengkung
Sekarang kita akan membuat objek `CurvePolygon` kosong.

```csharp
var curvePolygon = new CurvePolygon();
```

### Langkah 5: Tentukan Cincin Eksterior
Tambahkan string melingkar yang membentuk batas luar poligon.

```csharp
var exterior = new CircularString();
exterior.AddPoint(-2, 0);
exterior.AddPoint(0, 2);
exterior.AddPoint(2, 0);
exterior.AddPoint(0, -2);
exterior.AddPoint(-2, 0);
curvePolygon.ExteriorRing = exterior;
```

Koordinat di atas menghasilkan bentuk seperti torus.

### Langkah 6: Tentukan Cincin Interior (Opsional)
Jika Anda memerlukan lubang di dalam poligon, definisikan sebagai string melingkar lainnya. Ini menunjukkan cara menambahkan **poligon cincin interior** menggunakan **geometri string melingkar**.

```csharp
var interior = new CircularString();
interior.AddPoint(-1, 0);
interior.AddPoint(0, 1);
interior.AddPoint(1, 0);
interior.AddPoint(0, -1);
interior.AddPoint(-1, 0);
curvePolygon.AddInteriorRing(interior);
```

### Langkah 7: Tetapkan Geometri ke Fitur
Hubungkan poligon melengkung ke fitur yang Anda buat sebelumnya.

```csharp
feature.Geometry = curvePolygon;
```

### Langkah 8: Tambahkan Fitur ke Lapisan
Akhirnya, tambahkan fitur ke lapisan vektor sehingga menjadi bagian dari dataset.

```csharp
layer.Add(feature);
```

Ketika blok `using` berakhir, Shapefile ditulis ke disk.

## Masalah Umum dan Solusinya
| Masalah | Mengapa Terjadi | Solusi |
|---------|----------------|--------|
| **File tidak dibuat** | Jalur tidak benar atau izin menulis tidak ada | Pastikan direktori ada dan aplikasi memiliki izin menulis. |
| **Tepi melengkung muncul sebagai garis lurus di beberapa penampil** | Penampil tidak mendukung string melingkar | Gunakan aplikasi GIS yang sepenuhnya mendukung spesifikasi Shapefile (mis., QGIS 3.28+). |
| **Exception `ArgumentException` pada `AddPoint`** | Titik berada di luar rentang koordinat yang valid untuk CRS yang dipilih | Pastikan koordinat berada dalam sistem referensi koordinat yang akan Anda gunakan. |

## Pertanyaan yang Sering Diajukan

**T: Apakah Aspose.GIS untuk .NET kompatibel dengan perpustakaan GIS lain?**  
J: Ya, Aspose.GIS untuk .NET mendukung interoperabilitas dengan banyak format GIS populer, memungkinkan Anda menukar data dengan perpustakaan seperti GDAL/OGR atau Proj.NET.

**T: Bisakah saya memvisualisasikan Geometri Poligon Melengkung yang dihasilkan di perangkat lunak GIS?**  
J: Tentu saja! Shapefile yang dihasilkan dapat dibuka di QGIS, ArcGIS, atau alat GIS apa pun yang membaca format Shapefile.

**T: Apakah Aspose.GIS untuk .NET menyediakan kemampuan analisis spasial?**  
J: Ya, ia mencakup fungsi untuk kueri spasial, buffering, interseksi, dan lainnya, memungkinkan analisis lanjutan langsung di .NET.

**T: Di mana saya dapat meminta bantuan atau berdiskusi dengan pengguna lain?**  
J: Bergabunglah dengan forum komunitas Aspose.GIS [di sini](https://forum.aspose.com/c/gis/33) untuk terhubung dengan pengembang lain.

**T: Apakah tersedia percobaan gratis sebelum membeli?**  
J: Tentu! Anda dapat mengunduh percobaan gratis dari [halaman rilis](https://releases.aspose.com/) dan mengevaluasi semua fitur.

## Kesimpulan
Anda kini telah mempelajari cara **membuat lapisan vektor** dan **membuat geometri poligon melengkung** menggunakan Aspose.GIS untuk .NET, menyimpannya sebagai Shapefile, serta menjelajahi jebakan umum dan FAQ. Silakan bereksperimen dengan set koordinat yang berbeda, menambahkan data atribut, atau mengintegrasikan lapisan ke dalam alur kerja GIS yang lebih besar.

---

**Last Updated:** 2026-02-15  
**Tested With:** Aspose.GIS for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}