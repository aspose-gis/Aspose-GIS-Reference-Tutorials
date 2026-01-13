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

# spatial reference wgs84 – Add Layer to GDB using Aspose.GIS

## Introduction
Siap meningkatkan alur kerja GIS Anda dengan Aspose.GIS untuk .NET? Pada tutorial ini Anda akan mempelajari **cara menambahkan layer ke dataset File GDB** sambil bekerja dengan sistem koordinat **spatial reference wgs84**. Kami akan membimbing Anda melalui setiap langkah, mulai dari menyiapkan folder data hingga memvalidasi layer yang baru dibuat, sehingga Anda dapat mulai memanipulasi data geografis dengan percaya diri.

## Quick Answers
- **Apa sistem koordinat utama yang digunakan?** spatial reference wgs84 (WGS 84)  
- **Perpustakaan mana yang menyediakan API?** Aspose.GIS untuk .NET  
- **Apakah saya memerlukan lisensi untuk pengujian?** Ya – lisensi sementara Aspose tersedia.  
- **Bisakah saya menambahkan atribut ke layer baru?** Tentu saja, Anda dapat mendefinisikan sejumlah atribut fitur.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## What is spatial reference wgs84?
spatial reference wgs84 (World Geodetic System 1984) adalah sistem koordinat geografis yang paling banyak digunakan. Sistem ini mendefinisikan lintang dan bujur dalam derajat dan berfungsi sebagai CRS default untuk banyak dataset GIS, termasuk yang akan kami buat dalam panduan ini.

## Why use Aspose.GIS to add a layer?
- **Tanpa ketergantungan eksternal:** Berfungsi langsung dengan kode .NET murni.  
- **Kontrol penuh atas skema:** Anda dapat mendefinisikan atribut khusus dan tipe geometri.  
- **Lintas‑platform:** Kompatibel dengan runtime Windows, Linux, dan macOS.  
- **Lisensi yang kuat:** Lisensi sementara memungkinkan Anda mengevaluasi dengan cepat sebelum berkomitmen.

## Prerequisites
Sebelum memulai, pastikan Anda memiliki:

- Aspose.GIS untuk .NET Library: Unduh dan instal perpustakaan dari [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/).  
- Document Directory: Buat folder khusus di mesin Anda untuk menyimpan file GIS.

## Import Namespaces
Tambahkan pernyataan `using` yang diperlukan ke proyek C# Anda sehingga Anda dapat mengakses kelas Aspose.GIS:

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

## Step 1: Copy Directory
Pertama, duplikat folder yang berisi dataset GDB asli. Menyimpan salinan melindungi data sumber saat Anda bereksperimen.

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Step 2: Open Dataset and Verify Creation Capability
Buka dataset yang baru disalin dan pastikan bahwa ia dapat membuat layer baru. Properti `CanCreateLayers` harus mengembalikan **True**.

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Step 3: Create and Populate a New Layer with spatial reference wgs84
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

## Step 4: Open and Validate the Added Layer
Akhirnya, buka layer yang baru Anda buat dan verifikasi isinya. Konsol akan menampilkan bahwa layer tersebut berisi satu fitur dan bahwa atribut **Name** cocok dengan yang telah kami tetapkan.

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Common Issues & Tips
- **Path tidak tepat:** Pastikan `dataDir` diakhiri dengan pemisah path (`/` atau `\`) sehingga string yang digabung membentuk path file yang valid.  
- **Kesalahan lisensi:** Jika Anda melihat peringatan lisensi, terapkan lisensi sementara dari portal Aspose sebelum menjalankan kode.  
- **Ketidaksesuaian CRS:** Saat membuka layer nanti di alat GIS lain, pastikan alat tersebut mengenali WGS 84 (EPSG:4326) sebagai sistem koordinat.

## Frequently Asked Questions
### Q: Can I use Aspose.GIS for .NET with other GIS libraries?
Aspose.GIS untuk .NET dirancang agar dapat bekerja secara mandiri, tetapi dapat diintegrasikan dengan perpustakaan lain untuk fungsionalitas yang lebih luas.  

### Q: Is a temporary license available for testing purposes?
Ya, Anda dapat memperoleh lisensi sementara dari [here](https://purchase.aspose.com/temporary-license/) untuk pengujian dan evaluasi.  

### Q: What spatial reference systems does Aspose.GIS for .NET support?
Aspose.GIS untuk .NET mendukung berbagai sistem referensi spasial, memberikan fleksibilitas dalam penanganan data geografis.  

### Q: Can I contribute to the Aspose.GIS community?
Tentu saja! Bergabunglah dalam diskusi dan bagikan pengalaman Anda di [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).  

### Q: Where can I find detailed documentation for Aspose.GIS for .NET?
Jelajahi dokumentasi lengkap [here](https://reference.aspose.com/gis/net/) untuk informasi mendalam tentang Aspose.GIS untuk .NET.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-13  
**Tested With:** Aspose.GIS for .NET (latest stable version)  
**Author:** Aspose