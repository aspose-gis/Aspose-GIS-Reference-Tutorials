---
title: Membuka Fitur TopoJSON dengan Aspose.GIS untuk .NET
linktitle: Akses Fitur di TopoJSON
second_title: Aspose.GIS .NET API
description: Jelajahi Aspose.GIS untuk .NET dan pelajari cara mengakses fitur TopoJSON selangkah demi selangkah. Selami dokumentasi, dan gunakan kemampuan geospasial dengan mudah.
type: docs
weight: 15
url: /id/net/layer-management/access-features-in-topojson/
---
## Perkenalan
Aspose.GIS untuk .NET adalah perpustakaan canggih yang memungkinkan pengembang bekerja dengan data geospasial dengan mudah. Dalam tutorial ini, kita akan mempelajari cara mengakses fitur di TopoJSON menggunakan Aspose.GIS untuk .NET. TopoJSON adalah format yang mewakili fitur geografis dengan cara yang kompak dan efisien.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
- Pengetahuan kerja tentang C# dan .NET.
-  Aspose.GIS untuk perpustakaan .NET diinstal. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/gis/net/).
-  Contoh file TopoJSON untuk pengujian. Anda dapat menemukannya di[dokumentasi](https://reference.aspose.com/gis/net/).
## Impor Namespace
Mulailah dengan mengimpor namespace yang diperlukan ke dalam kode C# Anda:
```csharp
using Aspose.Gis;
using System;
using System.Text;
```
## Langkah 1: Siapkan Proyek Anda
Mulailah dengan membuat proyek C# baru dan menambahkan Aspose.GIS untuk .NET sebagai referensi. Pastikan proyek Anda dikonfigurasi untuk menggunakan perpustakaan.
## Langkah 2: Muat Data TopoJSON
```csharp
// Jalur ke direktori dokumen.
string dataDir = "Your Document Directory";
string sampleTopoJsonPath = dataDir + "sample.topojson";
StringBuilder builder = new StringBuilder();
// Buka file TopoJSON
using (VectorLayer layer = VectorLayer.Open(sampleTopoJsonPath, Drivers.TopoJson))
{
    // Ulangi setiap fitur di lapisan
    foreach (Feature feature in layer)
    {
        // dapatkan properti id
        int id = feature.GetValue<int>("id");
        // dapatkan nama objek yang berisi fitur ini
        string objectName = feature.GetValue<string>("topojson_object_name");
        // dapatkan properti atribut nama, yang terletak di dalam objek 'properti'
        string name = feature.GetValue<string>("name");
        // mendapatkan geometri fitur.
        string geometry = feature.Geometry.AsText();
        // Bangun string keluaran
        builder.AppendFormat("Feature with ID {0}:\n", id);
        builder.AppendFormat("Object Name = {0}\n", objectName);
        builder.AppendFormat("Name        = {0}\n", name);
        builder.AppendFormat("Geometry    = {0}\n", geometry);
    }
}
// Tampilkan hasilnya
Console.WriteLine("Output:");
Console.WriteLine(builder.ToString());
```
## Kesimpulan
Selamat! Anda berhasil mengakses fitur di TopoJSON menggunakan Aspose.GIS untuk .NET. Tutorial ini mencakup langkah-langkah dasar untuk memulai, namun masih banyak lagi yang dapat Anda jelajahi dengan perpustakaan.
## FAQ
### T: Di mana saya dapat menemukan dokumentasi selengkapnya?
 Mengunjungi[Aspose.GIS untuk dokumentasi .NET](https://reference.aspose.com/gis/net/).
### T: Bagaimana cara mengunduh Aspose.GIS untuk .NET?
 Unduh perpustakaan[Di Sini](https://releases.aspose.com/gis/net/).
### T: Di mana saya bisa mendapatkan dukungan untuk Aspose.GIS?
 Bergabunglah dengan[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33) untuk bantuan.
### T: Apakah tersedia uji coba gratis?
Ya, Anda dapat mengakses uji coba gratis[Di Sini](https://releases.aspose.com/).
### T: Bagaimana cara membeli lisensi?
 Beli lisensi[Di Sini](https://purchase.aspose.com/buy).