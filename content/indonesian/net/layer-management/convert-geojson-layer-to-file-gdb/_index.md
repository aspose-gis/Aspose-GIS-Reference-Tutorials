---
title: GeoJSON ke File Konversi GDB Diungkapkan
linktitle: Ubah Lapisan GeoJSON menjadi File GDB
second_title: Aspose.GIS .NET API
description: Temukan keajaiban geospasial dengan Aspose.GIS untuk .NET! Konversi lapisan GeoJSON ke File Geodatabases dengan mudah. Coba sekarang! #Asumsikan #GIS
type: docs
weight: 17
url: /id/net/layer-management/convert-geojson-layer-to-file-gdb/
---
## Perkenalan
Dalam dunia Sistem Informasi Geografis (GIS) yang dinamis, kemampuan untuk mengkonversi data dengan lancar antar format yang berbeda sangatlah penting. Aspose.GIS untuk .NET muncul sebagai sekutu yang kuat, menawarkan serangkaian alat komprehensif untuk menangani data geospasial dengan mudah. Dalam tutorial ini, kita akan mempelajari proses mengubah lapisan GeoJSON menjadi File Geodatabase (File GDB) menggunakan Aspose.GIS untuk .NET.
## Prasyarat
Sebelum memulai perjalanan geospasial ini, pastikan Anda memiliki prasyarat berikut:
- Pengetahuan tentang pemrograman .NET.
-  Aspose.GIS untuk .NET diinstal. Jika tidak, unduh dari[Di Sini](https://releases.aspose.com/gis/net/) dan ikuti petunjuk instalasi.
## Impor Namespace
Untuk memulai proses konversi, mulailah dengan mengimpor namespace yang diperlukan:
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
Sekarang, mari kita bagi prosesnya menjadi panduan langkah demi langkah:
## Langkah 1: Siapkan Lapisan GeoJSON
Mulailah dengan membuat lapisan GeoJSON dengan atribut dan fitur yang relevan. Berikut cuplikan untuk memandu Anda:
```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    // Tambahkan atribut
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    //Membangun dan menambahkan fitur
    Feature firstFeature = layer.ConstructFeature();
    firstFeature.Geometry = new Point(33.97, -118.25);
    firstFeature.SetValue("name", "John");
    firstFeature.SetValue("age", 23);
    layer.Add(firstFeature);
    Feature secondFeature = layer.ConstructFeature();
    secondFeature.Geometry = new Point(35.81, -96.28);
    secondFeature.SetValue("name", "Mary");
    secondFeature.SetValue("age", 54);
    layer.Add(secondFeature);
}
```
## Langkah 2: Salin Kumpulan Data Uji
Untuk menjaga integritas data pengujian Anda, buat salinan himpunan data. Gunakan cuplikan kode berikut:
```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```
## Langkah 3: Konversi GeoJSON ke File GDB
Sekarang saatnya melakukan konversi. Gunakan kode berikut:
```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        // Salin atribut
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        // Tambah Fitur
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```
## Kesimpulan
Dalam tutorial ini, kami menjelajahi medan menarik dalam mengonversi lapisan GeoJSON menjadi File Geodatabase menggunakan Aspose.GIS untuk .NET. Berbekal pengetahuan ini, Anda kini diperlengkapi untuk memanipulasi data geospasial dengan lancar di aplikasi .NET Anda.
## FAQ
### Apakah Aspose.GIS kompatibel dengan kerangka .NET terbaru?
Ya, Aspose.GIS kompatibel dengan versi kerangka .NET terbaru.
### Bisakah saya mengonversi format geospasial lain menggunakan Aspose.GIS?
Sangat! Aspose.GIS mendukung beragam format geospasial untuk manipulasi data serbaguna.
### Apakah ada versi uji coba yang tersedia untuk Aspose.GIS?
 Ya, Anda dapat menjelajahi fungsi Aspose.GIS dengan mengunduh versi uji coba[Di Sini](https://releases.aspose.com/).
### Bagaimana saya bisa mendapatkan dukungan untuk pertanyaan terkait Aspose.GIS?
 Kunjungi Aspose.GIS[forum](https://forum.aspose.com/c/gis/33) untuk dukungan khusus.
### Bisakah saya mendapatkan lisensi sementara untuk Aspose.GIS?
 Ya, Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).