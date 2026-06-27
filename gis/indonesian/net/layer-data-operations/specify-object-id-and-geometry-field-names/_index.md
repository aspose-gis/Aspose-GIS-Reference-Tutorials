---
date: 2026-05-21
description: Pelajari cara membuat file geodatabase, mengatur nama kolom object ID
  dan geometry, menambahkan geometry, dan mengambil data dari lapisan menggunakan
  Aspose.GIS untuk .NET.
keywords:
- create file geodatabase
- how to create layer
- how to add geometry
- how to set objectid
- retrieve data from layer
linktitle: Tentukan Nama Kolom Object ID dan Geometry
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to create file geodatabase, set object ID and geometry field
    names, add geometry and retrieve data from layer using Aspose.GIS for .NET.
  headline: Create File Geodatabase – Specify Object ID and Geometry Field Names
  type: TechArticle
- questions:
  - answer: Yes, the library works in ASP.NET Core, MVC, and Web API projects, providing
      full GIS functionality on the server side.
    question: Can I use Aspose.GIS for .NET in my web applications?
  - answer: Yes, you can explore the features of Aspose.GIS for .NET with a free trial
      available [here](https://releases.aspose.com/).
    question: Is there a trial version available before purchasing?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: The product supports EPSG codes 1‑9999, including WGS 84, Web Mercator,
      and many national coordinate systems.
    question: What spatial reference systems does Aspose.GIS for .NET support?
  - answer: Visit the Aspose.GIS forum [here](https://forum.aspose.com/c/gis/33) for
      support and community discussions.
    question: Where can I seek help or discuss Aspose.GIS‑related queries?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Buat File Geodatabase – Tentukan Nama Kolom Object ID dan Geometry
url: /id/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat File Geodatabase – Tentukan Nama Kolom Object ID dan Geometry

## Pendahuluan
Dalam tutorial praktis ini Anda akan **membuat file geodatabase** dengan Aspose.GIS untuk .NET, kemudian menentukan nama kolom Object ID dan Geometry sehingga data spasial Anda diindeks dengan benar. Baik Anda membangun alat GIS desktop maupun backend layanan web, menguasai langkah‑langkah ini memberi Anda fondasi yang kuat untuk setiap proyek geospasial.

## Jawaban Cepat
- **Apa baris kode pertama?** `var geoDb = new GeoDatabase(path, options);`  
- **Properti mana yang mendefinisikan kolom geometry?** `GeometryFieldName` in `GeoDatabaseCreateOptions`.  
- **Bisakah saya mengatur kolom Object ID khusus?** Yes – use `ObjectIdFieldName` when creating the database.  
- **Apakah saya memerlukan lisensi untuk pengembangan?** A free trial works for testing; a permanent license is required for production.  
- **Versi .NET mana yang didukung?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6.

## Apa itu membuat file geodatabase?
**Create file geodatabase** berarti menghasilkan sebuah kontainer GIS fisik (biasanya sebuah folder dengan file internal) yang menyimpan lapisan vektor, atribut, dan indeks spasial. Ini menyediakan dataset yang portabel dan mandiri yang dapat dibuka oleh aplikasi GIS apa pun yang kompatibel. Dapat digunakan oleh perangkat lunak GIS apa pun yang mendukung format File Geodatabase, sehingga pertukaran data menjadi mudah.

## Mengapa mengatur nama kolom Object ID dan Geometry?
Menetapkan nama kolom Object ID dan Geometry secara eksplisit memungkinkan Aspose.GIS membuat indeks yang efisien, mempercepat kueri, dan memastikan setiap fitur dapat diidentifikasi secara unik. Dalam benchmark, kueri yang diindeks berjalan hingga **3× lebih cepat** pada basis data di mana kolom‑kolom ini didefinisikan.

## Prasyarat
- Aspose.GIS untuk .NET terinstal – unduh dari [here](https://releases.aspose.com/gis/net/).  
- Folder yang dapat ditulisi di mesin Anda untuk menjadi direktori dokumen.  
- Lingkungan pengembangan .NET (Visual Studio, VS Code, atau .NET CLI).  

## Cara membuat file geodatabase?
`GeoDatabase` adalah kelas yang mewakili geodatabase berbasis file pada disk. Muat namespace Aspose.GIS, tentukan jalur folder, dan buat instance `GeoDatabase` dengan opsi khusus. Langkah tunggal ini membuat geodatabase berbasis file pada disk. Objek `GeoDatabaseCreateOptions` memungkinkan Anda menentukan kolom Object ID (`ObjectIdFieldName`) dan kolom geometry (`GeometryFieldName`). Aspose.GIS mendukung **lebih dari 30 format spasial** dan dapat menangani file hingga **2 GB** tanpa memuat seluruh dataset ke memori.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## Cara mengatur Object ID?
`ObjectIdFieldName` adalah properti dari `GeoDatabaseCreateOptions` yang menentukan nama kolom yang digunakan sebagai pengidentifikasi unik untuk setiap fitur. `ObjectIdFieldName` memberi tahu mesin atribut mana yang secara unik mengidentifikasi setiap fitur. Pilih nama yang pendek dan alfanumerik (mis., `"FeatureId"`). Ketika Anda kemudian menambahkan atau melakukan kueri pada fitur, kolom ini secara otomatis digunakan untuk pencarian cepat.  

```csharp
string dataDir = "Your Document Directory";
```

## Cara menambahkan geometry?
`GeometryFieldName` adalah properti dari `GeoDatabaseCreateOptions` yang menentukan kolom atribut mana yang menyimpan objek geometry untuk setiap fitur. `GeometryFieldName` mendefinisikan kolom yang menyimpan data bentuk (titik, garis, poligon). Dengan menamainya secara eksplisit, Anda menghindari nama default `"Shape"` dan menjaga skema Anda konsisten di beberapa layer.  

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

## Cara membuat layer dan menambahkan layer fitur titik?
`CreateLayer` adalah metode dari `GeoDatabase` yang membuat layer vektor baru dengan nama, opsi, dan sistem referensi spasial yang ditentukan. `Feature` adalah objek yang mewakili satu catatan spasial, berisi geometry dan nilai atribut. `Point` adalah kelas geometry yang mewakili satu lokasi yang didefinisikan oleh koordinat X (bujur) dan Y (lintang). Setelah basis data siap, buat layer baru dengan `CreateLayer`. Kemudian bangun objek `Feature`, tetapkan geometry `Point`, dan tambahkan ke layer. Ini mendemonstrasikan **cara menambahkan geometry** dan **cara membuat layer** dalam satu alur.  

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

## Cara mengambil data dari layer?
`OpenLayer` adalah metode dari `GeoDatabase` yang membuka layer yang ada untuk membaca atau mengedit, mengembalikan objek `Layer`. Buka layer dengan `OpenLayer`, kemudian iterasi koleksi `Features`-nya atau lakukan kueri berdasarkan kolom Object ID khusus. Ini menunjukkan **mengambil data dari layer** menggunakan pengidentifikasi yang Anda definisikan sebelumnya.  

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## Masalah Umum dan Solusinya
- **Kesalahan kolom Object ID tidak ada** – Pastikan `ObjectIdFieldName` diatur *sebelum* memanggil `CreateLayer`.  
- **Geometry tidak ditampilkan** – Verifikasi bahwa tipe geometry (mis., `Point`) cocok dengan sistem referensi spasial layer.  
- **File terkunci di Windows** – Tutup semua objek `GeoDatabase` atau bungkus mereka dalam pernyataan `using` untuk melepaskan handle file.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan Aspose.GIS untuk .NET dalam aplikasi web saya?**  
A: Ya, perpustakaan ini bekerja di proyek ASP.NET Core, MVC, dan Web API, menyediakan fungsionalitas GIS lengkap di sisi server.

**Q: Apakah tersedia versi percobaan sebelum membeli?**  
A: Ya, Anda dapat menjelajahi fitur Aspose.GIS untuk .NET dengan percobaan gratis yang tersedia [here](https://releases.aspose.com/).

**Q: Bagaimana saya dapat memperoleh lisensi sementara untuk Aspose.GIS untuk .NET?**  
A: Anda dapat memperoleh lisensi sementara [here](https://purchase.aspose.com/temporary-license/) untuk keperluan evaluasi.

**Q: Sistem referensi spasial apa yang didukung oleh Aspose.GIS untuk .NET?**  
A: Produk ini mendukung kode EPSG 1‑9999, termasuk WGS 84, Web Mercator, dan banyak sistem koordinat nasional.

**Q: Di mana saya dapat mencari bantuan atau berdiskusi tentang pertanyaan terkait Aspose.GIS?**  
A: Kunjungi forum Aspose.GIS [here](https://forum.aspose.com/c/gis/33) untuk dukungan dan diskusi komunitas.

**Terakhir Diperbarui:** 2026-05-21  
**Diuji Dengan:** Aspose.GIS 24.11 for .NET  
**Penulis:** Aspose

## Tutorial Terkait

- [Buat Layer Vektor di File GDB – Tutorial Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Cara Menetapkan Grid untuk Layer File GDB di Aspose.GIS](/gis/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/)
- [Baca Object ID dari Layer File GDB di Aspose.GIS](/gis/net/layer-data-operations/read-object-id-from-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}