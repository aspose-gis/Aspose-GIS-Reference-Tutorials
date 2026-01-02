---
date: 2026-01-02
description: Pelajari cara menambahkan fitur titik sambil mengatur nama bidang dan
  membaca ID objek menggunakan Aspose.GIS untuk .NET. Panduan langkah demi langkah
  untuk pengembang.
linktitle: Specify Object ID and Geometry Field Names
second_title: Aspose.GIS .NET API
title: Tambahkan fitur titik dan tentukan Nama ID Objek serta Nama Kolom Geometri
url: /id/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan fitur titik dan tentukan Nama ID Objek serta Nama Field Geometri

## Pendahuluan
Memulai perjalanan ke dalam ranah Sistem Informasi Geografis (GIS) menggunakan Aspose.GIS untuk .NET membuka dunia kemungkinan bagi pengembang dan penggemar. Dalam tutorial ini, **Anda akan belajar cara menambahkan fitur titik** sekaligus **menetapkan nama field** dan **membaca nilai ID objek**, memberi Anda kontrol penuh atas data spasial Anda.

## Jawaban Cepat
- **Apa tujuan utama panduan ini?** Menunjukkan cara menambahkan fitur titik dan mengonfigurasi Nama ID Objek serta Nama Field Geometri.  
- **Perpustakaan apa yang digunakan?** Aspose.GIS untuk .NET.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis tersedia; lisensi diperlukan untuk produksi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Bisakah saya membaca ID Objek setelah penyisipan?** Ya – tutorial ini memperlihatkan cara membaca ID objek dari layer.

## Prasyarat
Sebelum menyelam ke tutorial, pastikan Anda memiliki prasyarat berikut:
- Aspose.GIS untuk .NET: Unduh dan instal perpustakaan dari [sini](https://releases.aspose.com/gis/net/).
- Direktori Dokumen: Siapkan direktori untuk dokumen Anda guna menyimpan geodatabase.
- Lingkungan .NET: Pastikan Anda memiliki lingkungan .NET yang berfungsi.

## Impor Namespace
Untuk memulai, Anda perlu mengimpor namespace yang diperlukan ke dalam proyek Anda. Namespace ini menyediakan kelas dan metode penting untuk berinteraksi dengan Aspose.GIS untuk .NET.

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## Langkah 1: Tambahkan fitur titik dan tentukan Nama ID Objek serta Nama Field Geometri
Pada langkah ini, Anda akan belajar cara mengatur Nama ID Objek dan Nama Field Geometri untuk data GIS Anda. Ini penting untuk manajemen data yang efisien dan untuk dapat **membaca ID objek** nanti.

### Langkah 1.1: Atur Direktori Dokumen
Mulailah dengan mendefinisikan jalur ke direktori dokumen Anda:

```csharp
string dataDir = "Your Document Directory";
```

### Langkah 1.2: Buat GeoDatabase dan Tentukan Opsi
Buat GeoDatabase dengan **menetapkan nama field** yang diinginkan untuk ID Objek dan Geometri:

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

### Langkah 1.3: Buat dan Tambahkan Layer
Buat layer di dalam GeoDatabase dan tambahkan fitur yang mewakili geometri titik:

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

### Langkah 1.4: Buka dan Ambil Data dari Layer
Buka layer dan ambil fitur yang baru saja Anda tambahkan. Ini memperlihatkan cara **membaca ID objek** dari dataset:

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## Mengapa mengatur nama field khusus?
Menyesuaikan Nama ID Objek dan Nama Field Geometri memberi Anda fleksibilitas saat mengintegrasikan dengan basis data yang sudah ada atau saat mematuhi konvensi penamaan yang diperlukan oleh aplikasi hilir. Ini juga membuat data lebih deskriptif, yang menyederhanakan pemeliharaan dan kolaborasi.

## Kesalahan umum dan pemecahan masalah
- **Direktori tidak ada** – Pastikan `dataDir` mengarah ke folder yang ada; jika tidak, `Dataset.Create` akan melempar pengecualian.
- **Konflik nama field** – Jika sebuah field dengan nama yang sama sudah ada di geodatabase, pembuatan akan gagal. Pilih nama yang unik.
- **Ketidaksesuaian referensi spasial** – Selalu sesuaikan sistem referensi spasial (misalnya, WGS84) dengan data yang ingin Anda simpan.

## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara **menambahkan fitur titik**, **menetapkan nama field**, dan **membaca ID objek** menggunakan Aspose.GIS untuk .NET. Dasar ini memberi Anda kemampuan untuk membangun aplikasi GIS yang kuat dan mengelola data spasial dengan percaya diri.

## Pertanyaan yang Sering Diajukan
### Q: Bisakah saya menggunakan Aspose.GIS untuk .NET dalam aplikasi web saya?
A: Ya, Aspose.GIS untuk .NET cocok untuk aplikasi desktop maupun web, menyediakan kemampuan geospasial yang serbaguna.

### Q: Apakah ada versi percobaan yang tersedia sebelum membeli?
A: Ya, Anda dapat menjelajahi fitur Aspose.GIS untuk .NET dengan percobaan gratis yang tersedia [sini](https://releases.aspose.com/).

### Q: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.GIS untuk .NET?
A: Anda dapat memperoleh lisensi sementara [sini](https://purchase.aspose.com/temporary-license/) untuk keperluan evaluasi.

### Q: Sistem referensi spasial apa yang didukung oleh Aspose.GIS untuk .NET?
A: Aspose.GIS untuk .NET mendukung berbagai sistem referensi spasial, memberikan fleksibilitas untuk berbagai dataset geografis.

### Q: Di mana saya dapat mencari bantuan atau berdiskusi tentang pertanyaan terkait Aspose.GIS?
A: Kunjungi forum Aspose.GIS [sini](https://forum.aspose.com/c/gis/33) untuk dukungan dan diskusi.

## Pertanyaan Tambahan yang Sering Diajukan

**Q: Bisakah saya mengubah field ID Objek setelah layer dibuat?**  
A: Tidak. Nama field ditentukan saat layer dibuat; Anda harus membuat ulang layer dengan objek `FileGdbOptions` baru untuk mengubahnya.

**Q: Bagaimana cara mengambil nilai atribut lain selain ID Objek?**  
A: Gunakan `feature.GetValue<T>("FieldName")` dimana `FieldName` adalah nama atribut yang ingin Anda baca.

**Q: Apakah memungkinkan menambahkan beberapa fitur titik dalam satu batch?**  
A: Ya. Lakukan loop pada data Anda, buat fitur untuk setiap titik, tetapkan geometri, dan panggil `layer.Add(feature)` di dalam blok `using` yang sama.

**Q: Apakah Aspose.GIS mendukung tipe geometri lain?**  
A: Tentu saja. Anda dapat bekerja dengan `LineString`, `Polygon`, `MultiPoint`, dan lainnya dengan membuat objek geometri yang sesuai.

**Q: Apa yang terjadi jika saya mencoba membaca ID Objek yang tidak ada?**  
A: Mengakses indeks di luar jangkauan (misalnya, `layer[10]` padahal hanya ada satu fitur) akan melempar `IndexOutOfRangeException`. Selalu periksa `layer.Count` terlebih dahulu.

---

**Terakhir Diperbarui:** 2026-01-02  
**Diuji Dengan:** Aspose.GIS untuk .NET 24.11  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}