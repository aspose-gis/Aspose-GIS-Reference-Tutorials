---
title: Buat Shapefile Baru
linktitle: Buat Shapefile Baru
second_title: Aspose.GIS .NET API
description: Pelajari cara membuat shapefile baru menggunakan Aspose.GIS untuk .NET. Ikuti panduan langkah demi langkah kami dan temukan kekuatan manipulasi data spasial.
type: docs
weight: 12
url: /id/net/layer-management/create-new-shapefile/
---
## Perkenalan
Jika Anda mempelajari pengembangan sistem informasi geografis (GIS) dengan .NET, Aspose.GIS adalah solusi tepat Anda. Pustaka canggih ini memberdayakan pengembang untuk bekerja secara lancar dengan data spasial, dan dalam tutorial ini, kami akan memandu Anda melalui proses pembuatan shapefile baru menggunakan Aspose.GIS untuk .NET.
## Prasyarat
Sebelum kita masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
- Pemahaman dasar bahasa pemrograman C#.
- Visual Studio diinstal pada mesin Anda.
-  Aspose.GIS untuk perpustakaan .NET. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/gis/net/).
## Impor Namespace
Mulailah dengan mengimpor namespace yang diperlukan untuk memanfaatkan fungsionalitas Aspose.GIS:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Langkah 1: Siapkan Proyek Anda
Mulailah dengan membuat proyek C# baru di Visual Studio dan sertakan perpustakaan Aspose.GIS.
## Langkah 2: Tentukan Direktori Dokumen
```csharp
string dataDir = "Your Document Directory";
```
Ganti "Direktori Dokumen Anda" dengan jalur sebenarnya tempat Anda ingin menyimpan shapefile baru Anda.
## Langkah 3: Buat Lapisan Vektor
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    //menambahkan atribut sebelum menambahkan fitur
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
Segmen kode ini menyiapkan lapisan vektor dan mendefinisikan atribut untuk fitur Anda.
## Langkah 4: Tambahkan Fitur
### Kasus 1: Menetapkan Nilai Secara Individual
```csharp
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
firstFeature.SetValue("dob", new DateTime(1982, 2, 5, 16, 30, 0));
layer.Add(firstFeature);
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
secondFeature.SetValue("dob", new DateTime(1984, 12, 15, 15, 30, 0));
layer.Add(secondFeature);
```
### Kasus 2: Menetapkan Nilai Baru untuk Semua Atribut
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
## Kesimpulan
 Selamat! Anda telah berhasil membuat shapefile baru menggunakan Aspose.GIS untuk .NET. Tutorial ini membahas dasar-dasar menyiapkan proyek Anda, menentukan atribut, dan menambahkan fitur. Saat Anda menjelajah lebih jauh, lihat[dokumentasi](https://reference.aspose.com/gis/net/) untuk fitur dan fungsi lanjutan.
## Pertanyaan yang Sering Diajukan
### T: Dapatkah saya menggunakan Aspose.GIS dengan bahasa pemrograman lain?
Aspose.GIS pada dasarnya mendukung .NET, tetapi ada juga versi yang tersedia untuk Java.
### T: Apakah tersedia uji coba gratis?
 Ya, Anda dapat mengakses uji coba gratis[Di Sini](https://releases.aspose.com/).
### T: Di mana saya bisa mendapatkan dukungan untuk Aspose.GIS?
 Mengunjungi[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33) untuk dukungan dan diskusi komunitas.
### Q: Bagaimana cara mendapatkan lisensi sementara?
 Dapatkan lisensi sementara Anda[Di Sini](https://purchase.aspose.com/temporary-license/).
### T: Di mana saya bisa membeli Aspose.GIS untuk .NET?
 Anda dapat membeli perpustakaan[Di Sini](https://purchase.aspose.com/buy).