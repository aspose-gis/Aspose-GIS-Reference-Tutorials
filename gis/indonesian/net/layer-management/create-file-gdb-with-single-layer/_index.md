---
date: 2026-01-10
description: Pelajari cara membuat lapisan vektor dalam File Geodatabase menggunakan
  Aspose.GIS untuk .NET. Kelola data geospasial dengan referensi spasial WGS84 dan
  opsi file gdb.
linktitle: Create File GDB with Single Layer
second_title: Aspose.GIS .NET API
title: Buat Lapisan Vektor di File GDB – Tutorial Aspose.GIS .NET
url: /id/net/layer-management/create-file-gdb-with-single-layer/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Membuat Layer Vektor di File GDB

## Pendahuluan
Jika Anda perlu **membuat layer vektor** di dalam File Geodatabase (GDB) dan mengelola data geospasial secara efisien, Aspose.GIS untuk .NET memberikan pendekatan bersih berbasis kode. Dalam panduan langkah‑demi‑langkah ini kami akan menunjukkan cara menulis fitur garis, mengonfigurasi opsi file gdb, dan bekerja dengan referensi spasial WGS84—semua dalam beberapa baris C#. Pada akhir tutorial Anda akan dapat menghitung fitur dalam sebuah layer dan mengintegrasikan GDB yang dihasilkan ke dalam alur kerja pemetaan atau analisis .NET apa pun.

## Jawaban Cepat
- **Apa arti “membuat layer vektor”?** Itu berarti menambahkan dataset vektor baru (titik, garis, atau poligon) ke dalam file geodatabase.  
- **Perpustakaan mana yang harus saya gunakan?** Aspose.GIS untuk .NET menyediakan dukungan penuh untuk pembuatan dan penyuntingan File GDB.  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Versi percobaan gratis cukup untuk pengujian; lisensi komersial diperlukan untuk produksi.  
- **Bisakah saya mengatur referensi spasial?** Ya – gunakan `SpatialReferenceSystem.Wgs84` untuk datum WGS84 yang umum.  
- **Berapa banyak baris kode?** Kurang dari 30 baris untuk membuat GDB, menambahkan fitur garis, dan membaca kembali jumlah fitur.

## Apa itu operasi “membuat layer vektor”?
Membuat layer vektor berarti mendefinisikan tabel baru di dalam geodatabase yang menyimpan objek geometris (titik, garis, poligon) beserta atributnya. Operasi ini menjadi dasar bagi setiap aplikasi GIS yang perlu **mengelola data geospasial**.

## Mengapa menggunakan Aspose.GIS untuk membuat layer vektor?
- **Tanpa ketergantungan eksternal** – API berfungsi langsung pada .NET Framework, .NET Core, dan .NET 5/6.  
- **Dukungan penuh untuk File GDB** – Anda dapat mengonfigurasi `FileGdbOptions` untuk mengendalikan kompresi, pengindeksan spasial, dan lainnya.  
- **Penanganan referensi spasial bawaan** – cukup berikan `SpatialReferenceSystem.Wgs84` untuk bekerja pada sistem koordinat global.  
- **API yang sederhana** – tulis fitur garis, tambahkan ke layer, dan dapatkan jumlah fitur hanya dengan beberapa pemanggilan metode.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki:

1. **Aspose.GIS untuk .NET** – unduh dari [halaman unduhan Aspose.GIS untuk .NET](https://releases.aspose.com/gis/net/).  
2. **Lingkungan pengembangan .NET** – Visual Studio, Rider, atau `dotnet` CLI.  
3. **Folder** tempat File GDB akan dibuat (kami akan menyebutnya *Your Document Directory*).

## Impor Namespace
Tambahkan pernyataan `using` yang diperlukan di bagian atas file C# Anda:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```

## Langkah 1: Siapkan Direktori Dokumen Anda
```csharp
string dataDir = "Your Document Directory";
```
Ganti `"Your Document Directory"` dengan jalur absolut tempat Anda ingin File GDB berada.

## Langkah 2: Buat File Geodatabase dengan Satu Layer
```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```
Potongan kode ini **membuat layer vektor** menggunakan `FileGdbOptions`, menulis fitur garis sederhana, dan menyimpannya dalam File GDB yang menggunakan **referensi spasial WGS84**.

## Langkah 3: Buka File Geodatabase dan Dapatkan Informasi Layer
```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Output: Features count: 1
}
```
Di sini kami **menghitung fitur layer** dengan membuka dataset dan mencetak jumlah fitur – dalam contoh ini, `1`.

## Masalah Umum dan Solusinya
| Masalah | Alasan | Solusi |
|-------|--------|-----|
| **`File not found`** | Variable `path` tidak tepat | Pastikan `dataDir` mengarah ke folder yang ada dan `path` menggabungkannya dengan nama file, misalnya `Path.Combine(dataDir, "MyData.gdb")`. |
| **`Unsupported geometry`** | Menggunakan tipe geometri yang tidak didukung di File GDB | Gunakan `Point`, `LineString`, atau `Polygon` untuk layer dasar. |
| **`License not set`** | Menjalankan tanpa lisensi yang valid di produksi | Daftarkan lisensi Anda dengan `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Pertanyaan yang Sering Diajukan
### Bisakah saya menggunakan Aspose.GIS untuk .NET dalam proyek .NET yang sudah ada?
Ya, Aspose.GIS untuk .NET dapat diintegrasikan secara mulus ke dalam proyek .NET Anda yang sudah ada.

### Apakah tersedia versi percobaan untuk Aspose.GIS untuk .NET?
Ya, Anda dapat menjelajahi fitur Aspose.GIS untuk .NET dengan mengunduh [versi percobaan gratis](https://releases.aspose.com/).

### Di mana saya dapat menemukan dokumentasi lengkap untuk Aspose.GIS untuk .NET?
Lihat [dokumentasi](https://reference.aspose.com/gis/net/) untuk informasi komprehensif tentang Aspose.GIS untuk .NET.

### Bagaimana cara mendapatkan dukungan untuk Aspose.GIS untuk .NET?
Kunjungi [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) untuk dukungan komunitas dan bantuan.

### Apakah lisensi sementara tersedia untuk Aspose.GIS untuk .NET?
Ya, Anda dapat memperoleh [lisensi sementara](https://purchase.aspose.com/temporary-license/) untuk Aspose.GIS untuk .NET.

---

**Terakhir Diperbarui:** 2026-01-10  
**Diuji Dengan:** Aspose.GIS 24.11 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}