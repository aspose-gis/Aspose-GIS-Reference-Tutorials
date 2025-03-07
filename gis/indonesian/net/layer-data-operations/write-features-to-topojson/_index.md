---
title: Tulis Fitur ke TopoJSON
linktitle: Tulis Fitur ke TopoJSON
second_title: Aspose.GIS .NET API
description: Kuasai penulisan fitur TopoJSON dengan Aspose.GIS untuk .NET. Ikuti tutorial langkah demi langkah kami. Tingkatkan aplikasi GIS Anda.
weight: 24
url: /id/net/layer-data-operations/write-features-to-topojson/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tulis Fitur ke TopoJSON

## Perkenalan
Dalam bidang pengembangan Sistem Informasi Geografis (GIS), Aspose.GIS untuk .NET menonjol sebagai perangkat canggih yang menawarkan banyak fungsi untuk memanipulasi data spasial. Di antara banyak kemampuannya, tutorial ini berfokus pada tugas tertentu: menulis fitur ke format TopoJSON menggunakan Aspose.GIS untuk .NET. Jika Anda ingin meningkatkan aplikasi GIS Anda dengan dukungan TopoJSON, ikuti panduan langkah demi langkahnya.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
-  Aspose.GIS untuk .NET: Pastikan Anda telah menginstal perpustakaan Aspose.GIS. Anda dapat menemukan dokumentasi dan mengunduh perpustakaan[Di Sini](https://reference.aspose.com/gis/net/).
- Lingkungan .NET: Pastikan Anda telah menyiapkan lingkungan pengembangan .NET.
-  Direktori Dokumen: Pilih direktori untuk dokumen Anda. Ini akan disebut sebagai`Your Document Directory` dalam contoh kode.
## Impor Namespace
Dalam aplikasi .NET Anda, sertakan namespace yang diperlukan untuk bekerja dengan Aspose.GIS dan fungsi lain yang diperlukan.
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
```
Sekarang, mari kita pecahkan contoh kode menjadi beberapa langkah untuk pemahaman yang lebih jelas.
## 1. Atur Direktori Dokumen
```csharp
string dataDir = "Your Document Directory";
```
 Mengganti`"Your Document Directory"` dengan jalur sebenarnya ke direktori dokumen Anda.
## 2. Tentukan Jalur Keluaran
```csharp
var outputPath = dataDir + "sample_out.topojson";
```
Tentukan jalur untuk file TopoJSON keluaran.
## 3. Buat VectorLayer dengan Driver TopoJSON
```csharp
using (VectorLayer layer = VectorLayer.Create(outputPath, Drivers.TopoJson))
```
Inisialisasi VectorLayer menggunakan driver TopoJSON.
## 4. Tambahkan Atribut ke Layer
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("measurement", AttributeDataType.Double));
layer.Attributes.Add(new FeatureAttribute("id", AttributeDataType.Integer));
```
Tentukan atribut untuk fitur yang akan ditambahkan ke lapisan.
## 5. Tambahkan Fitur ke Layer
```csharp
var feature0 = layer.ConstructFeature();
feature0.SetValue("name", "name_0");
feature0.SetValue("measurement", 1.03);
feature0.SetValue("id", 0);
feature0.Geometry = new Point(1.3, 2.3);
layer.Add(feature0);
var feature1 = layer.ConstructFeature();
feature1.SetValue("name", "name_1");
feature1.SetValue("measurement", 10.03);
feature1.SetValue("id", 1);
feature1.Geometry = new Point(241.32, 23.2);
layer.Add(feature1);
```
Bangun fitur dengan atribut dan geometri tertentu, dan tambahkan ke lapisan.
## Kesimpulan
Selamat! Anda telah berhasil menulis fitur ke TopoJSON menggunakan Aspose.GIS untuk .NET. Tutorial ini memberikan pemahaman dasar tentang proses, memungkinkan Anda mengintegrasikan fungsi ini ke dalam aplikasi GIS Anda dengan lancar.
## Pertanyaan yang Sering Diajukan
### T: Dapatkah saya menggunakan Aspose.GIS untuk .NET dengan pustaka GIS lainnya?
J: Aspose.GIS untuk .NET dirancang untuk bekerja secara independen, namun integrasi dengan perpustakaan lain dimungkinkan untuk meningkatkan fungsionalitas.
### T: Apakah ada opsi lisensi untuk Aspose.GIS?
 J: Ya, Anda dapat menjelajahi opsi lisensi dan melakukan pembelian[Di Sini](https://purchase.aspose.com/buy).
### T: Apakah ada uji coba gratis yang tersedia untuk Aspose.GIS untuk .NET?
 J: Tentu saja! Anda dapat mengakses uji coba gratis[Di Sini](https://releases.aspose.com/).
### T: Di mana saya bisa mencari dukungan atau terhubung dengan komunitas Aspose.GIS?
 J: Pergilah ke[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33) untuk dukungan dan diskusi komunitas.
### T: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.GIS?
 A: Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
