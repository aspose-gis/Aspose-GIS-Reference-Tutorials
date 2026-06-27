---
date: 2026-05-05
description: Pelajari cara membuat TopoJSON menggunakan Aspose.GIS untuk .NET. Panduan
  langkah demi langkah untuk menulis fitur ke format TopoJSON.
keywords:
- create topojson aspose
- Aspose.GIS TopoJSON
- .NET GIS tutorial
linktitle: Tulis Fitur ke TopoJSON
second_title: Aspose.GIS .NET API
title: Cara Membuat TopoJSON dengan Aspose.GIS untuk .NET
url: /id/net/layer-data-operations/write-features-to-topojson/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membuat TopoJSON dengan Aspose.GIS untuk .NET

## Pendahuluan
Jika Anda perlu **membuat TopoJSON** secara langsung dari aplikasi .NET Anda, Aspose.GIS menyediakan API yang bersih dan efisien untuk melakukannya. Dalam tutorial ini kami akan membahas seluruh proses menulis fitur ke dokumen TopoJSON, mulai dari menyiapkan lingkungan hingga menambahkan atribut dan geometri. Pada akhir tutorial, Anda akan dapat mengintegrasikan pembuatan TopoJSON ke dalam solusi GIS apa pun yang Anda bangun.

## Jawaban Cepat
- **Apa yang dibahas dalam tutorial ini?** Menulis fitur vektor ke file TopoJSON menggunakan Aspose.GIS untuk .NET.  
- **Berapa lama waktu yang dibutuhkan?** Sekitar 10‑15 menit untuk implementasi dasar.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis cukup untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Versi .NET yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Bisakah saya menambahkan atribut khusus?** Ya – Anda dapat mendefinisikan sejumlah atribut fitur sebelum menambahkan geometri.

## Apa itu TopoJSON dan Mengapa Menggunakan Aspose.GIS?
TopoJSON adalah ekstensi dari GeoJSON yang mengkodekan topologi, menghasilkan ukuran file yang lebih kecil dan segmen garis yang dibagi. Menggunakan Aspose.GIS untuk **membuat TopoJSON** memberi Anda kontrol programatik, kinerja tinggi, dan integrasi mulus dengan alur kerja GIS lainnya dalam ekosistem .NET.

## Prasyarat
Sebelum Anda memulai, pastikan Anda memiliki hal berikut:

- Aspose.GIS untuk .NET terpasang. Anda dapat menemukan dokumentasi dan mengunduh perpustakaan [di sini](https://reference.aspose.com/gis/net/).
- Lingkungan pengembangan .NET (Visual Studio, VS Code, atau IDE apa pun yang Anda sukai).
- Sebuah folder di mesin Anda tempat file output akan disimpan – kami akan menyebutnya `Your Document Directory` dalam contoh kode.

## Impor Namespace
Pertama, tambahkan namespace yang diperlukan agar Anda dapat bekerja dengan kelas GIS.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Panduan Langkah‑per‑Langkah

### Langkah 1: Atur Direktori Dokumen
Tentukan folder yang akan menyimpan file TopoJSON yang dihasilkan.

```csharp
string dataDir = "Your Document Directory";
```

Ganti `"Your Document Directory"` dengan jalur sebenarnya di sistem Anda.

### Langkah 2: Tentukan Jalur Output
Gabungkan direktori dengan nama file yang diinginkan.

```csharp
var outputPath = dataDir + "sample_out.topojson";
```

### Langkah 3: Buat VectorLayer dengan Driver TopoJSON
Instansiasi `VectorLayer` yang menggunakan driver TopoJSON. Layer ini akan berfungsi sebagai wadah untuk semua fitur yang Anda tambahkan.

```csharp
using (VectorLayer layer = VectorLayer.Create(outputPath, Drivers.TopoJson))
```

### Langkah 4: Tambahkan Atribut ke Layer
Sebelum menyisipkan geometri, deklarasikan skema atribut. Atribut-atribut ini akan disimpan bersamaan dengan setiap fitur.

```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("measurement", AttributeDataType.Double));
layer.Attributes.Add(new FeatureAttribute("id", AttributeDataType.Integer));
```

### Langkah 5: Tambahkan Fitur ke Layer
Buat fitur individu, atur nilai atributnya, tetapkan geometri, dan tambahkan ke layer.

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

Ketika blok `using` selesai, Aspose.GIS secara otomatis menulis data ke `sample_out.topojson`.

## Kesalahan Umum & Tips
- **Pemilih jalur:** Gunakan `Path.Combine` jika Anda memerlukan kompatibilitas lintas‑platform.  
- **Tipe atribut:** Pastikan tipe data yang Anda tentukan cocok dengan nilai yang Anda berikan; ketidaksesuaian akan menyebabkan pengecualian runtime.  
- **Dataset besar:** Untuk ribuan fitur, pertimbangkan melakukan batch insert atau menggunakan `layer.BeginTransaction()` / `Commit()` untuk meningkatkan kinerja.

## Kesimpulan
Anda kini telah mempelajari cara **membuat TopoJSON** dengan Aspose.GIS untuk .NET, mulai dari menyiapkan layer hingga mengisinya dengan atribut khusus dan geometri titik. Dasar ini memungkinkan Anda memperluas ke geometri yang lebih kompleks (garis, poligon) dan dataset yang lebih besar seiring pertumbuhan aplikasi GIS Anda.

## Pertanyaan yang Sering Diajukan
**Q: Bisakah saya menggunakan Aspose.GIS untuk .NET dengan perpustakaan GIS lain?**  
A: Aspose.GIS beroperasi secara independen, tetapi Anda dapat menukar data dengan perpustakaan lain dengan membaca atau menulis format umum seperti GeoJSON, Shapefile, atau KML.

**Q: Apakah ada opsi lisensi untuk Aspose.GIS?**  
A: Ya, Anda dapat menjelajahi opsi lisensi dan melakukan pembelian [di sini](https://purchase.aspose.com/buy).

**Q: Apakah tersedia percobaan gratis untuk Aspose.GIS untuk .NET?**  
A: Tentu saja! Anda dapat mengakses percobaan gratis [di sini](https://releases.aspose.com/).

**Q: Di mana saya dapat mencari dukungan atau terhubung dengan komunitas Aspose.GIS?**  
A: Kunjungi [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) untuk dukungan komunitas dan diskusi.

**Q: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.GIS?**  
A: Anda dapat memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

---

**Terakhir Diperbarui:** 2026-05-05  
**Diuji Dengan:** Aspose.GIS untuk .NET (versi terbaru per Mei 2026)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}