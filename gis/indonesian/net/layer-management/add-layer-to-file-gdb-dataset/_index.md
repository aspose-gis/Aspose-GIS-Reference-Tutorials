---
title: Penguasaan GIS - Tambahkan Lapisan ke GDB dengan Aspose.GIS untuk .NET
linktitle: Tambahkan Lapisan ke File Kumpulan Data GDB
second_title: Aspose.GIS .NET API
description: Buka kekuatan GIS dengan Aspose.GIS untuk .NET! Pelajari cara menambahkan lapisan ke kumpulan data File GDB dalam tutorial langkah demi langkah ini. #data geografis #Aspose #GIS
weight: 16
url: /id/net/layer-management/add-layer-to-file-gdb-dataset/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Penguasaan GIS - Tambahkan Lapisan ke GDB dengan Aspose.GIS untuk .NET

## Perkenalan
Apakah Anda siap untuk meningkatkan kemampuan GIS Anda menggunakan Aspose.GIS untuk .NET? Dalam panduan langkah demi langkah ini, kami akan memandu Anda melalui proses menambahkan lapisan ke kumpulan data File Geodatabase (GDB). Aspose.GIS untuk .NET menyediakan fitur canggih untuk memanipulasi informasi geografis, dan dengan tutorial ini, Anda akan dapat mengintegrasikan lapisan tambahan ke dalam kumpulan data Anda dengan lancar.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
-  Aspose.GIS untuk .NET Library: Unduh dan instal perpustakaan dari[Aspose.GIS untuk Dokumentasi .NET](https://reference.aspose.com/gis/net/).
- Direktori Dokumen: Buat direktori dokumen khusus di mesin Anda untuk menyimpan dan mengelola file terkait GIS.
## Impor Namespace
Di proyek .NET Anda, pastikan untuk mengimpor namespace yang diperlukan untuk mengakses fungsionalitas Aspose.GIS. Gunakan cuplikan kode berikut:
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
Sebelum melanjutkan, duplikat direktori yang berisi kumpulan data GDB Anda. Langkah ini memastikan kumpulan data asli tetap utuh. Gunakan cuplikan kode yang disediakan:
```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```
## Langkah 2: Buka Kumpulan Data dan Periksa Kemampuan Pembuatan
 Buka kumpulan data duplikat dan periksa apakah dapat membuat lapisan. Hal ini dibuktikan dengan kehadiran`True` di keluaran konsol.
```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // BENAR
```
## Langkah 3: Buat dan Isi Layer Baru
Buat lapisan baru dalam kumpulan data, tentukan sistem referensi spasial, atribut, dan fitur sampelnya. Cuplikan kode ini menunjukkan prosesnya:
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
## Langkah 4: Buka dan Validasi Lapisan yang Ditambahkan
Buka lapisan yang baru saja Anda buat dan validasi kontennya. Periksa hitungan dan ambil nilai atribut menggunakan kode berikut:
```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Nama_1"
}
```
## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara menambahkan lapisan ke kumpulan data File GDB menggunakan Aspose.GIS untuk .NET. Dengan keterampilan baru ini, Anda dapat memanipulasi data geografis secara efisien dalam proyek GIS Anda.
## Pertanyaan yang Sering Diajukan
### T: Dapatkah saya menggunakan Aspose.GIS untuk .NET dengan pustaka GIS lainnya?
Aspose.GIS untuk .NET dirancang untuk bekerja secara independen, namun dapat diintegrasikan dengan perpustakaan lain untuk meningkatkan fungsionalitas.
### T: Apakah lisensi sementara tersedia untuk tujuan pengujian?
 Ya, Anda bisa mendapatkan lisensi sementara dari[Di Sini](https://purchase.aspose.com/temporary-license/) untuk pengujian dan evaluasi.
### T: Sistem referensi spasial apa yang didukung Aspose.GIS untuk .NET?
Aspose.GIS untuk .NET mendukung berbagai sistem referensi spasial, memberikan fleksibilitas dalam penanganan data geografis.
### T: Bisakah saya berkontribusi pada komunitas Aspose.GIS?
 Sangat! Bergabunglah dalam diskusi dan bagikan pengalaman Anda di[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33).
### T: Di mana saya dapat menemukan dokumentasi terperinci untuk Aspose.GIS untuk .NET?
 Jelajahi dokumentasi komprehensif[Di Sini](https://reference.aspose.com/gis/net/) untuk informasi mendalam tentang Aspose.GIS untuk .NET.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
