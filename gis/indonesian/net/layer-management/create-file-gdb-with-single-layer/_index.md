---
title: Buat File GDB dengan Lapisan Tunggal
linktitle: Buat File GDB dengan Lapisan Tunggal
second_title: Aspose.GIS .NET API
description: Buka potensi pengelolaan data geospasial di .NET dengan Aspose.GIS. Pelajari cara membuat File Geodatabase dan lapisan langkah demi langkah. Unduh sekarang!
type: docs
weight: 11
url: /id/net/layer-management/create-file-gdb-with-single-layer/
---
## Perkenalan
Apakah Anda siap untuk meningkatkan aplikasi geospasial Anda dengan geodatabase dan lapisan file yang kuat? Kunjungi Aspose.GIS untuk .NET. Dalam tutorial ini, kami akan memandu Anda melalui proses pembuatan File Geodatabase (GDB) dengan satu lapisan menggunakan Aspose.GIS untuk .NET. Manfaatkan kekuatan manajemen dan visualisasi data spasial dalam aplikasi .NET Anda dengan mudah.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
1.  Aspose.GIS untuk .NET: Pastikan Anda telah menginstal perpustakaan Aspose.GIS. Anda dapat mengunduhnya dari[Halaman unduh Aspose.GIS untuk .NET](https://releases.aspose.com/gis/net/).
2. Lingkungan Pengembangan: Siapkan lingkungan pengembangan .NET yang berfungsi di mesin Anda.
3. Direktori Dokumen: Pilih atau buat direktori di sistem Anda tempat Anda akan menyimpan file data geospasial.
## Impor Namespace
Untuk memulai, Anda perlu mengimpor namespace yang diperlukan dalam proyek .NET Anda. Namespace ini akan memberikan akses ke fungsionalitas Aspose.GIS. Tambahkan baris berikut di awal file kode Anda:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```
## Langkah 1: Siapkan Direktori Dokumen Anda
```csharp
string dataDir = "Your Document Directory";
```
Ganti "Direktori Dokumen Anda" dengan jalur ke direktori tempat Anda ingin menyimpan file data geospasial.
## Langkah 2: Buat File Geodatabase dengan Satu Lapisan
```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
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
Cuplikan kode ini membuat File Geodatabase dengan satu lapisan dan menambahkan fitur garis ke dalamnya.
## Langkah 3: Buka File Geodatabase dan Ambil Informasi Lapisan
```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Keluaran: Jumlah fitur: 1
}
```
Pada langkah ini, kita membuka File Geodatabase yang dibuat, mengambil layer bernama "layer", dan mencetak jumlah fitur di layer tersebut.
## Kesimpulan
Selamat! Anda telah berhasil membuat File Geodatabase dengan satu lapisan menggunakan Aspose.GIS untuk .NET. Jelajahi kemampuan manajemen data spasial yang luas dalam aplikasi Anda dengan mudah.
## Pertanyaan yang Sering Diajukan
### Bisakah saya menggunakan Aspose.GIS untuk .NET di proyek .NET saya yang sudah ada?
Ya, Aspose.GIS untuk .NET dapat diintegrasikan dengan lancar ke dalam proyek .NET Anda yang sudah ada.
### Apakah ada versi uji coba yang tersedia untuk Aspose.GIS untuk .NET?
 Ya, Anda dapat menjelajahi fitur Aspose.GIS untuk .NET dengan mengunduh[versi percobaan gratis](https://releases.aspose.com/).
### Di mana saya dapat menemukan dokumentasi terperinci untuk Aspose.GIS untuk .NET?
 Mengacu kepada[dokumentasi](https://reference.aspose.com/gis/net/) untuk informasi komprehensif tentang Aspose.GIS untuk .NET.
### Bagaimana saya bisa mendapatkan dukungan untuk Aspose.GIS untuk .NET?
 Mengunjungi[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33) untuk dukungan dan bantuan masyarakat.
### Apakah lisensi sementara tersedia untuk Aspose.GIS untuk .NET?
 Ya, Anda bisa mendapatkan a[izin sementara](https://purchase.aspose.com/temporary-license/) untuk Aspose.GIS untuk .NET.