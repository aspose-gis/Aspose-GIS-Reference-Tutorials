---
title: Dapatkan Nilai Atribut Fitur (Default)
linktitle: Dapatkan Nilai Atribut Fitur (Default)
second_title: Aspose.GIS .NET API
description: Buka kekuatan Aspose.GIS untuk .NET! Ambil dan manipulasi nilai atribut fitur dengan mudah menggunakan panduan langkah demi langkah ini. Unduh uji coba Anda sekarang!
type: docs
weight: 14
url: /id/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
---
## Perkenalan
Selamat datang di dunia Aspose.GIS untuk .NET! Dalam panduan komprehensif ini, kita akan mendalami seluk-beluk pengambilan nilai atribut fitur menggunakan kemampuan Aspose.GIS yang canggih. Baik Anda seorang pengembang berpengalaman atau baru memulai, tutorial ini akan memberi Anda panduan langkah demi langkah, memastikan Anda memanfaatkan potensi penuh dari alat luar biasa ini.
## Prasyarat
Sebelum kita memulai petualangan coding ini, pastikan Anda memiliki prasyarat berikut:
- Pengetahuan tentang C# dan .NET framework.
-  Aspose.GIS untuk .NET diinstal. Jika tidak, unduh dari[Di Sini](https://releases.aspose.com/gis/net/).
- Editor kode, seperti Visual Studio, dapat diikuti dengan lancar.
## Impor Namespace
Dalam proyek C# Anda, pastikan untuk menyertakan namespace yang diperlukan:
```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
Sekarang, mari kita bagi setiap contoh menjadi serangkaian langkah yang mudah diikuti.
## Dapatkan Nilai Atribut Fitur (Default)
### Langkah 1: Siapkan Lingkungan
Mulailah dengan menentukan jalur ke direktori dokumen Anda:
```csharp
string dataDir = "Your Document Directory";
```
### Langkah 2: Buat Lapisan GeoJson
Buat lapisan GeoJson dan tentukan atribut dengan nilai default:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```
### Langkah 3: Buat Fitur
Bangun fitur menggunakan atribut yang ditentukan:
```csharp
    Feature feature = layer.ConstructFeature();
```
### Langkah 4: Ambil Nilai
Ambil nilai atribut dengan berbagai skenario:
```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // nilai == nol
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // nilai == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // nilai == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```
## Menetapkan Nilai Default
### Langkah 1: Buat Lapisan GeoJson Lainnya
Ulangi proses ini dengan lapisan GeoJson yang berbeda dan atribut double:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```
### Langkah 2: Buat Fitur (Lagi)
```csharp
    Feature feature = layer.ConstructFeature();
```
### Langkah 3: Ambil dan Tetapkan Nilai
Ambil dan tetapkan nilai atribut, yang menampilkan nilai default:
```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); // nilai == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); // nilai == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); // nilai == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```
Selamat! Anda telah berhasil memanfaatkan kekuatan Aspose.GIS untuk .NET dalam mengambil dan memanipulasi nilai atribut fitur.
## Kesimpulan
Dalam tutorial ini, kita telah menjelajahi nuansa pengambilan nilai atribut fitur menggunakan Aspose.GIS untuk .NET. Dengan API intuitif dan kemampuan yang kuat, Aspose.GIS membuka banyak kemungkinan untuk pengembangan GIS di lingkungan .NET.
## Pertanyaan yang Sering Diajukan
### Apakah Aspose.GIS kompatibel dengan .NET Core?
Ya, Aspose.GIS sepenuhnya kompatibel dengan .NET Core, menyediakan dukungan lintas platform.
### Bisakah saya menggunakan Aspose.GIS untuk proyek komersial?
Sangat! Aspose.GIS hadir dengan lisensi komersial yang memungkinkan Anda menggunakannya dalam aplikasi komersial tanpa batasan apa pun.
### Di mana saya dapat menemukan dukungan dan sumber daya tambahan?
 Mengunjungi[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33) untuk dukungan komunitas dan menjelajahi[dokumentasi](https://reference.aspose.com/gis/net/) untuk informasi mendalam.
### Apakah ada uji coba gratis yang tersedia?
 Ya, Anda dapat menjelajahi Aspose.GIS dengan uji coba gratis. Unduh itu[Di Sini](https://releases.aspose.com/).
### Bagaimana cara mendapatkan lisensi sementara untuk tujuan pengujian?
 Untuk lisensi sementara, kunjungi[Di Sini](https://purchase.aspose.com/temporary-license/).