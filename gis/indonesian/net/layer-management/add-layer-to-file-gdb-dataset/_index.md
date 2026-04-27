---
date: 2026-01-13
description: Pelajari cara menambahkan lapisan ke dataset File GDB menggunakan Aspose.GIS,
  dengan dukungan referensi spasial WGS84. Ikuti panduan langkah demi langkah ini
  untuk menambahkan lapisan ke GDB di .NET.
linktitle: Add Layer to File GDB Dataset
second_title: Aspose.GIS .NET API
title: referensi spasial wgs84 – Tambahkan Lapisan ke GDB menggunakan Aspose.GIS
url: /id/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# referensi spasial wgs84 – Tambahkan Layer ke GDB menggunakan Aspose.GIS

## Perkenalan
Apakah Anda meningkatkan pekerjaan Anda dengan GIS Anda dengan Aspose.GIS untuk .NET? Pada tutorial ini Anda akan delmenada **cara mendapatkan lapisan ke dataset File GDB** sambil bekerja dengan sistem koordinat **referensi spasial wgs84**. Kami akan membimbing Anda melalui etiyap langkah, mulai dari memmpata folder data hingga memvalidasi layer yang baru keida, sepaha Anda dapat mulai memanipulasi data geografis dengan permanya diri.

## Jawaban Cepat
- **Apa sistem koordinat utama yang diwana?** referensi spasial wgs84 (WGS84)
- **Perpustakaan mana yang predukana API?** Aspose.GIS untuk .NET
- **Apakah saya menyukai lisensi untuk tesaing?** Ya – lisensi semanta Aspose bebekandi.
- ** ingin saya mendapat atribut ke layer baru? ** Tentu saja, Anda dapat mendefinisikan fitur atribut jumbal.
- **Versi .NET apa yang didukung?** .NET Framework4.5+, .NET Core3.1+, .NET5/6.

## Apa itu referensi spasial wgs84?
referensi spasial wgs84 (World Geodetic System 1984) adalah sistem koordinat geografis yang paling banyak diwana. Sistem ini mendefinisikan lintang dan bujur dalam degradasi dan fungsi sebagai CRS default untuk banyak dataset GIS, pasamu yang akan kami buat dalam panduan ini.

## Mengapa menggunakan Aspose.GIS untuk menambahkan lapisan?
- **Tanpa ketergantungan eksternal:** Berfungsi langsung dengan kode .NET murni.
- **Kontrol penuh atas skema:** Anda dapat mendefinisikan atribut khusus dan tipe geometrik.
- **Lintas‑platform:** Kompatibel dengan runtime Windows, Linux, dan macOS.
- **Lisensi yang kuat:** Lisensi semanara pemangana Anda menyalakannya dengan cepat sebelum berkomitmen.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki:

- Pustaka Aspose.GIS untuk .NET: Unduh dan instal pustaka dari [Dokumentasi Aspose.GIS untuk .NET](https://reference.aspose.com/gis/net/).

- Direktori Dokumen: Buat folder khusus di mesin Anda untuk menyimpan file GIS.

## Impor Namespace
Tambahkan pernyataan `using` yang diperlukan untuk proyek C# Anda agar Anda dapat mengakses kelas Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Langkah 1: Salin Direktori
Pertama, duplikat folder yang berisi dataset GDB asli. Menyimpan salinan melindungi data sumber saat Anda bereksperimen.

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Langkah 2: Buka Dataset dan Verifikasi Kemampuan Pembuatan
Buka dataset yang baru disalin dan pastikan bahwa ia dapat membuat layer baru. Properti `CanCreateLayers` harus mengembalikan **True**.

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Langkah 3: Buat dan Isi Layer Baru dengan referensi spasial wgs84
Sekarang kita membuat layer bernama **data** dan secara eksplisit menetapkan spatial reference-nya ke **Wgs84**. Kami juga menambahkan atribut sederhana bernama **Name** dan menyisipkan satu fitur titik.

```csharp
using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
{
    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
    var feature = layer.ConstructFeature();
    feature.SetValue("Name", "Name_1");
    feature.Geometry = new Point(12.21, 23.123, 20, -200);
    layer.Add(feature);
}
```

## Langkah 4: Buka dan Validasi Layer yang Ditambahkan
Akhirnya, buka layer yang baru Anda buat dan verifikasi isinya. Konsol akan menampilkan bahwa layer tersebut berisi satu fitur dan bahwa atribut **Name** cocok dengan yang telah kami tetapkan.

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Masalah & Tip Umum
- **Path tidak tepat:** Pastikan `dataDir` diakhiri dengan pemisah path (`/` atau `\`) sehata string yang digabung berarti file path yang valid.
- **Kesalahan lisensi:** Jika Anda melihat memandaran lisensi, menerapkan lisensi semaran dari portal Aspose sebelum kemenakan kode.
- **Ketidaksesuaian CRS:** Saat membuka lapisan nanti di alat GIS lain, pasiktan alat tersebut nakani WGS84 (EPSG:4326) sebagai sistem koordinat.

## Pertanyaan yang Sering Diajukan
### T: Bisakah saya menggunakan Aspose.GIS untuk .NET dengan perpustakaan GIS lainnya?
Aspose.GIS untuk .NET dirancang agar dapat bekerja secara mandiri, sehingga dapat berinteraksi dengan perpustakaan lain untuk fungsi yang lebih luas.

### T: Apakah lisensi sementara tersedia untuk tujuan pengujian?
Ya, Anda dapat menguji lisensi semesteran dari [di sini](https://purchase.aspose.com/temporary-license/) untuk tesaman dan evaluasi.

### T: Sistem referensi spasial apa yang didukung Aspose.GIS untuk .NET?
Aspose.GIS untuk .NET mendungan sistem referensi spasial, megjukan fleksibilitas dalam penanganan data geografis.

### T: Dapatkah saya berkontribusi pada komunitas Aspose.GIS?
Tentu saja! penyelesaian dalam diskusi dan bagikan pengamanan Anda di [Forum Aspose.GIS](https://forum.aspose.com/c/gis/33).

### T: Di mana saya dapat menemukan dokumentasi terperinci untuk Aspose.GIS untuk .NET?
Jelajahi dokumentazione lengkap [here](https://reference.aspose.com/gis/net/) untuk informasi geşam tentang Aspose.GIS untuk .NET.

---

**Terakhir Diperbarui:** 2026-01-13
**Diuji Dengan:** Aspose.GIS untuk .NET (versi stabil terbaru)
**Pengembang:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
