---
title: Buat Lapisan Vektor dengan SRS
linktitle: Buat Lapisan Vektor dengan SRS
second_title: Aspose.GIS .NET API
description: Jelajahi Aspose.GIS untuk .NET - kunci Anda untuk integrasi GIS yang lancar. Buat lapisan vektor dengan mudah menggunakan sistem referensi spasial tertentu. Unduh sekarang!
type: docs
weight: 13
url: /id/net/layer-management/create-vector-layer-with-srs/
---
## Perkenalan
Aspose.GIS untuk .NET adalah perpustakaan canggih yang memungkinkan pengembang bekerja dengan data sistem informasi geografis (GIS) secara lancar dalam aplikasi .NET. Dalam tutorial ini, kita akan fokus membuat lapisan vektor dengan sistem referensi spasial (SRS). Di akhir panduan ini, Anda akan dapat dengan mudah mengintegrasikan kemampuan GIS ke dalam proyek .NET Anda.
## Prasyarat
Sebelum kita mendalami tutorialnya, pastikan Anda memiliki prasyarat berikut:
- Pengetahuan dasar tentang pengembangan C# dan .NET.
-  Aspose.GIS untuk perpustakaan .NET diinstal. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/gis/net/).
- Lingkungan pengembangan telah disiapkan dan siap.
## Impor Namespace
Pastikan Anda telah mengimpor namespace yang diperlukan di awal file C# Anda:
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Langkah 1: Menyiapkan Sistem Referensi Spasial yang Diproyeksikan
Mari kita buat proyeksi sistem referensi spasial (SRS) menggunakan proyeksi World Mercator sebagai contoh. Ikuti langkah ini:
```csharp
var parameters = new ProjectedSpatialReferenceSystemParameters
{
    Name = "WGS 84 / World Mercator",
    Base = SpatialReferenceSystem.Wgs84,
    ProjectionMethodName = "Mercator_1SP",
    LinearUnit = Unit.Meter,
    XAxis = new Axis("Easting", AxisDirection.East),
    YAxis = new Axis("Northing", AxisDirection.North),
    AxisesOrder = ProjectedAxisesOrder.XY,
};
parameters.AddProjectionParameter("central_meridian", 0);
parameters.AddProjectionParameter("scale_factor", 1);
parameters.AddProjectionParameter("false_easting", 0);
parameters.AddProjectionParameter("false_northing", 0);
var projectedSrs = SpatialReferenceSystem.CreateProjected(parameters, Identifier.Epsg(3395));
```
## Langkah 2: Buat Layer Vektor dan Tambahkan Fitur
Sekarang, mari buat sebuah shapefile dan tambahkan fitur dengan SRS yang ditentukan:
```csharp
using (var layer = Drivers.Shapefile.CreateLayer(dataDir + "filepath_out.shp", new ShapefileOptions(), projectedSrs))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2);
    layer.Add(feature);
    feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2) { SpatialReferenceSystem = SpatialReferenceSystem.Nad83 };
    try
    {
        layer.Add(feature); // Ini akan menimbulkan pengecualian karena geometri memiliki SRS yang berbeda
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```
## Langkah 3: Verifikasi Sistem Referensi Spasial
Terakhir, mari buka layer dan verifikasi sistem referensi spasialnya:
```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / Mercator Dunia"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Harus kembali benar
}
```
Dengan mengikuti langkah-langkah ini, Anda telah berhasil membuat lapisan vektor dengan sistem referensi spasial tertentu menggunakan Aspose.GIS untuk .NET.
## Kesimpulan
Mengintegrasikan fungsionalitas GIS ke dalam aplikasi .NET Anda tidak pernah semudah ini, berkat Aspose.GIS. Dengan kemampuan membuat lapisan vektor dan mengelola sistem referensi spasial dengan mudah, Anda dapat menyempurnakan proyek Anda dengan kemampuan geospasial yang kuat.
## FAQ
### Apakah Aspose.GIS kompatibel dengan semua format file GIS?
 Aspose.GIS mendukung berbagai format GIS, termasuk Shapefile, GeoJSON, KML, dan banyak lagi. Periksalah[dokumentasi](https://reference.aspose.com/gis/net/) untuk daftar lengkapnya.
### Bisakah saya menggunakan Aspose.GIS dalam aplikasi web?
Sangat! Aspose.GIS untuk .NET serbaguna dan dapat digunakan dalam aplikasi web, aplikasi desktop, dan bahkan aplikasi seluler.
### Di mana saya bisa mendapatkan dukungan untuk Aspose.GIS?
 Anda dapat menemukan komunitas yang membantu di[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33) untuk pertanyaan atau masalah apa pun yang mungkin Anda temui.
### Apakah ada uji coba gratis yang tersedia?
 Ya, Anda dapat menjelajahi fitur Aspose.GIS dengan mendapatkan uji coba gratis[Di Sini](https://releases.aspose.com/).
### Bagaimana cara membeli lisensi Aspose.GIS?
 Untuk membeli lisensi, kunjungi[halaman pembelian](https://purchase.aspose.com/buy).