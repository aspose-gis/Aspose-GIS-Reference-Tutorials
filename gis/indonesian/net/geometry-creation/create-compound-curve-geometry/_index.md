---
date: 2026-02-15
description: Pelajari cara menambahkan kurva dan membuat geometri kurva gabungan di
  .NET menggunakan Aspose.GIS untuk pemrosesan data geospasial yang mulus.
linktitle: How to Add Curves – Compound Curve Geometry
second_title: Aspose.GIS .NET API
title: Cara Menambahkan Kurva - Geometri Kurva Majemuk dengan Aspose.GIS
url: /id/net/geometry-creation/create-compound-curve-geometry/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menambahkan Kurva: Geometri Kurva Gabungan dengan Aspose.GIS

## Pendahuluan
Dalam dunia pengembangan .NET, mempelajari **cara menambahkan kurva** dengan Aspose.GIS sangat penting untuk membangun aplikasi geospasial yang canggih. Baik Anda membuat peta interaktif, melakukan analisis spasial, atau menghasilkan dataset GIS yang kompleks, Aspose.GIS memberikan alat yang Anda perlukan untuk bekerja dengan geometri lanjutan secara cepat dan dapat diandalkan. Panduan ini akan membawa Anda melalui proses lengkap **cara menambahkan kurva** dan menyusunnya menjadi satu geometri kurva gabungan yang dapat digunakan kembali.

## Jawaban Cepat
- **Apa tujuan utama?** Menambahkan kurva dan membangun geometri kurva gabungan dalam sebuah Shapefile.  
- **Perpustakaan mana yang digunakan?** Aspose.GIS untuk .NET.  
- **Prasyarat?** Visual Studio, Aspose.GIS terpasang, dan proyek C# dasar.  
- **Waktu implementasi tipikal?** Sekitar 10‑15 menit untuk contoh yang berfungsi.  
- **Format output yang didukung?** Shapefile (tetapi pendekatan yang sama berlaku untuk GeoJSON, KML, dll.).

## Apa itu Kurva Gabungan?
Sebuah **kurva gabungan** adalah satu geometri yang terdiri dari beberapa komponen kurva yang terhubung—garis lurus (line strings) dan busur melingkar (circular arcs)—yang digabungkan menjadi bentuk yang lebih kompleks. Struktur ini berguna ketika satu garis sederhana tidak dapat merepresentasikan jalur yang diinginkan secara akurat, seperti jalan dengan tikungan atau belokan sungai.

## Mengapa Menggunakan Aspose.GIS untuk Menambahkan Kurva?
- **API geometri yang kaya:** Menangani line strings, circular strings, dan compound curves secara langsung.  
- **Cross‑platform:** Berfungsi dengan .NET Framework, .NET Core, dan .NET 5/6+.  
- **Tanpa dependensi eksternal:** Tidak memerlukan perpustakaan GIS native atau COM interop.  
- **Mudah diekspor:** Langsung menulis ke Shapefile, GeoJSON, KML, dan banyak format lainnya.

## Mengapa Ini Penting
Menambahkan kurva memungkinkan Anda memodelkan fitur dunia nyata dengan lebih akurat, yang meningkatkan kualitas visual pada render peta dan meningkatkan presisi dalam analisis spasial seperti pencarian kedekatan atau routing jaringan. Dengan menguasai **cara menambahkan kurva**, Anda dapat meningkatkan fidelitas solusi .NET berbasis GIS apa pun.

## Kasus Penggunaan Umum
- **Jaringan transportasi:** Memodelkan jalan raya, rel kereta, atau jalur sepeda yang memiliki tikungan halus.  
- **Hidrologi:** Merepresentasikan alur sungai yang mengikuti busur alami.  
- **Perencanaan kota:** Menggambar batas properti dengan bagian melengkung.  
- **Simbol khusus:** Membuat bentuk dekoratif atau skematik untuk legenda peta.

## Prasyarat
- **Visual Studio** terpasang di workstation Anda.  
- **Aspose.GIS untuk .NET** diunduh dari [halaman unduhan](https://releases.aspose.com/gis/net/).  
- Proyek C# yang menargetkan .NET 6 (atau versi yang didukung lainnya).

## Impor Namespace
Untuk mulai bekerja dengan Aspose.GIS, impor namespace yang diperlukan di bagian atas file C# Anda:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Panduan Langkah‑per‑Langkah untuk Membuat Geometri Kurva Gabungan

### Langkah 1: Tentukan Jalur Output
Pertama, beri tahu perpustakaan ke mana menulis hasilnya. Ganti placeholder dengan folder nyata di mesin Anda.

```csharp
string path = "Your Document Directory" + "CreateCompoundCurve_out.shp";
```

### Langkah 2: Buat Layer Vektor
`VectorLayer` berfungsi sebagai wadah untuk fitur spasial. Semua pekerjaan geometri terjadi di dalam blok `using` ini, yang juga menjamin bahwa sumber daya dibebaskan dengan benar.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Code block for creating the compound curve geometry will be inserted here.
}
```

### Langkah 3: Bangun Fitur Kurva Gabungan
Di dalam layer, kita membuat fitur baru dan objek `CompoundCurve` kosong yang akan menampung bagian‑bagian kurva individual.

```csharp
var feature = layer.ConstructFeature();
var compoundCurve = new CompoundCurve();
```

### Langkah 4: Definisikan Kurva Komponen
Di sini kita menyiapkan lima potongan terpisah—dua `LineString` lurus, dua busur `CircularString`, dan satu `LineString` akhir. Potongan‑potongan ini akan dijahit bersama untuk membentuk kurva gabungan lengkap.

```csharp
var bottom = (ILineString)Geometry.FromText("LineString (0 0, 3 0)");
var firstArc = (ICircularString)Geometry.FromText("CircularString (3 0, 4 1, 3 2)");
var middle = (ILineString)Geometry.FromText("LineString (3 2, 1 2)");
var secondArc = (ICircularString)Geometry.FromText("CircularString (1 2, 0 3, 1 4)");
var top = (ILineString)Geometry.FromText("LineString (1 4, 4 4)");
```

### Langkah 5: Tambahkan Kurva Komponen ke Kurva Gabungan
Setiap komponen ditambahkan secara berurutan, memastikan geometri tetap kontinu dan berorientasi dengan benar.

```csharp
compoundCurve.AddCurve(bottom);
compoundCurve.AddCurve(firstArc);
compoundCurve.AddCurve(middle);
compoundCurve.AddCurve(secondArc);
compoundCurve.AddCurve(top);
```

### Langkah 6: Tetapkan Geometri ke Fitur
Sekarang `CompoundCurve` yang telah dirakit menjadi geometri fitur yang akan kita simpan.

```csharp
feature.Geometry = compoundCurve;
```

### Langkah 7: Tambahkan Fitur ke Layer
Akhirnya, kami menulis fitur ke dalam Shapefile. Ketika blok `using` berakhir, file ditutup dan siap digunakan di aplikasi GIS mana pun.

```csharp
layer.Add(feature);
```

## Masalah Umum & Tips
- **Urutan koordinat:** Aspose.GIS mengharapkan koordinat dalam urutan `X Y` (longitude, latitude). Membalik urutan dapat menghasilkan geometri terbalik.  
- **Sintaks CircularString:** Pastikan titik tengah `CircularString` berada pada busur yang dimaksud; jika tidak, kurva dapat menjadi datar.  
- **Timpa file:** Jika Shapefile target sudah ada, `VectorLayer.Create` akan menimpanya tanpa peringatan—gunakan nama file unik selama pengembangan.  
- **Kinerja:** Untuk dataset besar, tambahkan fitur secara batch daripada satu‑per‑satu di dalam blok `using`.  
- **Tip pro:** Gunakan kembali objek `CompoundCurve` yang sama saat membuat beberapa fitur serupa; cukup bersihkan kurvanya dengan `compoundCurve.Clear()` sebelum mengisi kembali.

## Pertanyaan yang Sering Diajukan

**T: Bisakah saya menggunakan Aspose.GIS untuk .NET dengan kerangka .NET lain?**  
J: Ya, Aspose.GIS untuk .NET bekerja dengan .NET Framework, .NET Core, dan .NET Standard.

**T: Apakah Aspose.GIS mendukung membaca dan menulis berbagai format file geospasial?**  
J: Tentu saja! Ia mendukung Shapefile, GeoJSON, KML, GML, dan banyak format lainnya.

**T: Apakah Aspose.GIS cocok untuk aplikasi desktop maupun web?**  
J: Ya, perpustakaan ini dapat digunakan di aplikasi desktop, web, dan layanan cloud.

**T: Bisakah saya melakukan analisis spasial dengan Aspose.GIS untuk .NET?**  
J: Ya, Anda dapat menghitung jarak, melakukan operasi geometrik, dan mengeksekusi kueri spasial.

**T: Di mana saya dapat mendapatkan bantuan komunitas untuk Aspose.GIS?**  
J: Kunjungi [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) untuk mengajukan pertanyaan dan berbagi ide.

---

**Terakhir Diperbarui:** 2026-02-15  
**Diuji Dengan:** Aspose.GIS untuk .NET (rilis stabil terbaru)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}