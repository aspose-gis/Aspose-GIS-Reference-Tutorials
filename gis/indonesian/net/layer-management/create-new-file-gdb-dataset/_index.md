---
title: Buat Kumpulan Data GDB File Baru
linktitle: Buat Kumpulan Data GDB File Baru
second_title: Aspose.GIS .NET API
description: Jelajahi Aspose.GIS untuk .NET untuk membuat dan mengelola kumpulan data GIS dengan mudah. Unduh sekarang untuk pengembangan geospasial yang lancar. #Asumsikan #GIS
weight: 10
url: /id/net/layer-management/create-new-file-gdb-dataset/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Kumpulan Data GDB File Baru

## Perkenalan
Dalam bidang pengembangan geospasial, Aspose.GIS untuk .NET menonjol sebagai perangkat yang ampuh untuk mengelola dan memanipulasi data Sistem Informasi Geografis (GIS). Baik Anda seorang pengembang berpengalaman atau baru memulai perjalanan Anda ke GIS, tutorial ini akan memandu Anda melalui proses pembuatan kumpulan data File Geodatabase (GDB) baru menggunakan Aspose.GIS untuk .NET.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
-  Aspose.GIS untuk .NET: Pastikan Anda telah menginstal perpustakaan Aspose.GIS untuk .NET. Anda dapat mengunduhnya dari[Halaman unduh Aspose.GIS untuk .NET](https://releases.aspose.com/gis/net/).
- Lingkungan Pengembangan: Siapkan lingkungan pengembangan Anda dengan IDE yang kompatibel, seperti Visual Studio, dan miliki pemahaman dasar tentang pemrograman .NET.
- Direktori Dokumen: Ganti "Direktori Dokumen Anda" di cuplikan kode dengan jalur yang sesuai di mana Anda ingin menyimpan kumpulan data GDB Anda.
- Keakraban dengan C#: Tutorial ini mengasumsikan Anda sudah familiar dengan bahasa pemrograman C#.
## Impor Namespace
Pada langkah awal, impor namespace yang diperlukan untuk memanfaatkan fungsionalitas Aspose.GIS di aplikasi .NET Anda:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Langkah 1: Buat Kumpulan Data GDB File Baru
```csharp
string dataDir = "Your Document Directory";
using (var dataset = Dataset.Create(dataDir, Drivers.FileGdb))
{
    Console.WriteLine(dataset.LayersCount); // Keluaran: 0
    // Lanjutkan dengan langkah selanjutnya...
}
```
 Penjelasan: Pada langkah ini, kita membuat dataset GDB baru menggunakan`Dataset.Create` metode. Kami menentukan jalur dan driver (FileGdb) untuk membuat File Geodatabase. Output konsol menampilkan jumlah lapisan awal, yang saat ini adalah nol.
## Langkah 2: Buat dan Isi Layer_1
```csharp
using (var layer = dataset.CreateLayer("layer_1"))
{
    layer.Attributes.Add(new FeatureAttribute("value", AttributeDataType.Integer));
    for (int i = 0; i < 10; ++i)
    {
        var feature = layer.ConstructFeature();
        feature.SetValue("value", i);
        feature.Geometry = new Point(i, i);
        layer.Add(feature);
    }
}
```
Penjelasan: Langkah ini melibatkan pembuatan lapisan bernama "layer_1" di dalam kumpulan data. Ini mendefinisikan atribut bernama "nilai" bertipe integer dan mengisi lapisan dengan sepuluh fitur, masing-masing memiliki geometri titik.
## Langkah 3: Buat dan Isi Layer_2
```csharp
using (var layer = dataset.CreateLayer("layer_2"))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```
Penjelasan: Di sini, kita membuat layer kedua bernama "layer_2" dan menambahkan satu fitur dengan geometri string garis.
## Langkah 4: Periksa Jumlah Lapisan yang Diperbarui
```csharp
Console.WriteLine(dataset.LayersCount); // Keluaran: 2
```
Penjelasan: Terakhir, kami memeriksa jumlah lapisan yang diperbarui setelah menambahkan dua lapisan. Dalam hal ini, outputnya harus 2.
## Kesimpulan
Selamat! Anda telah berhasil membuat kumpulan data File GDB baru dan mengisinya dengan lapisan menggunakan Aspose.GIS untuk .NET. Tutorial ini memberikan pemahaman dasar tentang bekerja dengan data geospasial di lingkungan .NET.
## Pertanyaan yang Sering Diajukan
### T: Dapatkah saya menggunakan Aspose.GIS untuk .NET dengan pustaka GIS lainnya?
Aspose.GIS untuk .NET adalah perangkat mandiri; namun, Anda dapat mengintegrasikannya dengan perpustakaan .NET lainnya untuk meningkatkan fungsionalitas.
### T: Apakah ada forum komunitas untuk dukungan Aspose.GIS?
 Ya, Anda dapat menemukan dukungan dan diskusi di[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33).
### T: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.GIS?
 Mengunjungi[Lisensi Sementara](https://purchase.aspose.com/temporary-license/) halaman untuk informasi tentang cara mendapatkan lisensi sementara.
### T: Apakah tersedia contoh dan dokumentasi tambahan?
 Jelajahi[Dokumentasi Aspose.GIS](https://reference.aspose.com/gis/net/) untuk lebih banyak contoh dan informasi rinci.
### T: Di mana saya bisa membeli Aspose.GIS untuk .NET?
 Anda dapat membeli Aspose.GIS untuk .NET di[halaman pembelian](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
