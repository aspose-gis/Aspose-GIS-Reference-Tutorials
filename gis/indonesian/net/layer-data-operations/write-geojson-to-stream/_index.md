---
date: 2026-01-02
description: Pelajari cara menulis GeoJSON ke stream di C# menggunakan Aspose.GIS
  untuk .NET. Tampilkan contoh GeoJSON C# dan tingkatkan aplikasi geospasial Anda.
linktitle: Write GeoJSON to Stream
second_title: Aspose.GIS .NET API
title: Cara Menulis GeoJSON ke Stream dengan Aspose.GIS untuk .NET
url: /id/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menulis GeoJSON ke Stream

## Pendahuluan
Jika Anda perlu **how to write geojson** langsung ke memori atau aliran file dalam aplikasi .NET, Anda berada di tempat yang tepat. Dalam tutorial ini kami akan menjelaskan langkah‑langkah tepat untuk menulis GeoJSON ke aliran menggunakan pustaka Aspose.GIS untuk .NET, dan kami juga akan menunjukkan cara **display GeoJSON C#** output di konsol. Pada akhir, Anda akan memiliki pola yang dapat digunakan kembali yang dapat Anda masukkan ke proyek geospasial mana pun.

## Jawaban Cepat
- **What does “write GeoJSON to stream” mean?** Itu berarti menserialisasi lapisan vektor ke dalam format GeoJSON dan mengirimkan byte‑nya ke objek `Stream` (misalnya, `MemoryStream`).  
- **Which library handles this?** Aspose.GIS untuk .NET menyediakan driver GeoJSON bawaan.  
- **Do I need a license for development?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Can I run this on Linux?** Ya – Aspose.GIS bersifat lintas‑platform dan berfungsi di Windows, Linux, serta macOS.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Apa itu “how to write geojson” di .NET?
Aspose.GIS memungkinkan Anda membuat `VectorLayer`, menambahkan fitur, dan kemudian menserialisasi lapisan menggunakan driver `Drivers.GeoJson`. Driver tersebut menulis teks GeoJSON langsung ke dalam `Stream` apa pun, memberi Anda kontrol penuh tentang ke mana data tersebut pergi (memori, file, jaringan, dll.).

## Mengapa menggunakan Aspose.GIS untuk tugas ini?
- **Zero‑dependency serialization** – tidak memerlukan pustaka JSON eksternal.  
- **Full GeoJSON spec compliance** – mendukung FeatureCollections, properti, dan presisi koordinat.  
- **Cross‑platform** – berfungsi sama pada Windows, Linux, dan macOS.  
- **Performance‑optimized** – menulis langsung ke aliran tanpa string perantara.

## Prasyarat
1. **Aspose.GIS for .NET** – unduh di [sini](https://releases.aspose.com/gis/net/).  
2. **Document directory** – tentukan di mana Anda ingin menyimpan file sementara atau aliran output.

Sekarang, mari kita selami kode.

## Impor Namespace
Pertama, sertakan namespace yang memberi Anda akses ke kelas Aspose.GIS dan utilitas I/O standar .NET:

```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Langkah 1: Siapkan Direktori Dokumen
Tentukan folder yang akan menjadi tempat file sementara yang mungkin Anda perlukan.

```csharp
string dataDir = "Your Document Directory";
```

Ganti `"Your Document Directory"` dengan jalur sebenarnya di mesin Anda.

## Langkah 2: Buat Memory Stream
`MemoryStream` memungkinkan Anda menyimpan GeoJSON di memori, yang sempurna untuk API atau ketika Anda ingin mengembalikan data langsung ke klien.

```csharp
using (var memoryStream = new MemoryStream())
{
    // Subsequent steps will be placed inside this block
}
```

## Langkah 3: Buat Vector Layer dengan Driver GeoJSON
Di dalam blok memory‑stream, buat `VectorLayer` yang menggunakan driver GeoJSON. Ini memberi tahu Aspose.GIS untuk menserialisasi lapisan sebagai GeoJSON.

```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Feature creation goes here
}
```

## Langkah 4: Definisikan Atribut Fitur
Tambahkan definisi atribut yang akan muncul sebagai properti dalam output GeoJSON akhir.

```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## Langkah 5: Buat dan Tambahkan Fitur
Buat dua titik contoh, tetapkan nilai atribut, dan tambahkan ke lapisan.

```csharp
// First Feature
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);

// Second Feature
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```

## Langkah 6: Tampilkan Output GeoJSON C#
Setelah lapisan terisi, konversi byte aliran menjadi string UTF‑8 dan tulis ke konsol. Ini menunjukkan cara **display GeoJSON C#** hasil.

```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

Anda akan melihat FeatureCollection GeoJSON yang valid dicetak ke terminal.

## Masalah Umum dan Solusinya
| Masalah | Mengapa Terjadi | Solusi |
|---------|----------------|--------|
| Empty output | Posisi stream berada di akhir saat membaca | Panggil `memoryStream.Position = 0;` sebelum mengonversi ke string. |
| Invalid geometry | Koordinat berada di luar rentang yang valid | Verifikasi bahwa lintang berada antara -90 dan 90, bujur antara -180 dan 180. |
| License exception | Menjalankan tanpa lisensi yang valid di produksi | Terapkan lisensi sementara atau penuh menggunakan `License license = new License(); license.SetLicense("Aspose.GIS.lic");` |

## Pertanyaan yang Sering Diajukan
### Bisakah saya menggunakan Aspose.GIS untuk .NET di lingkungan Windows dan Linux?
Ya, Aspose.GIS untuk .NET kompatibel dengan sistem Windows dan Linux.

### Apakah tersedia versi percobaan gratis?
Tentu saja! Anda dapat menjelajahi versi percobaan gratis [di sini](https://releases.aspose.com/).

### Di mana saya dapat menemukan dokumentasi terperinci?
Lihat dokumentasi [di sini](https://reference.aspose.com/gis/net/).

### Bagaimana saya dapat memperoleh lisensi sementara?
Lisensi sementara tersedia [di sini](https://purchase.aspose.com/temporary-license/).

### Butuh bantuan atau memiliki pertanyaan lebih lanjut?
Kunjungi forum dukungan kami [di sini](https://forum.aspose.com/c/gis/33).

## FAQ
**Q: Bisakah saya menulis GeoJSON langsung ke file alih-alih memory stream?**  
A: Ya—ganti `MemoryStream` dengan `FileStream` dan berikan jalur file. Driver yang sama tetap berfungsi.

**Q: Bagaimana saya mengontrol indentasi atau format GeoJSON yang dihasilkan?**  
A: Aspose.GIS menulis JSON yang kompak secara default. Untuk output yang diformat rapi, proses string tersebut dengan `JsonSerializerOptions { WriteIndented = true }`.

**Q: Apakah memungkinkan menambahkan geometri yang lebih kompleks (mis., poligon) ke lapisan?**  
A: Tentu saja. Buat objek `Polygon` atau `LineString`, tetapkan ke `Feature.Geometry`, dan tambahkan fitur seperti yang ditunjukkan di atas.

**Q: Apakah dataset besar dapat muat dalam `MemoryStream`?**  
A: Untuk koleksi yang sangat besar, pertimbangkan untuk streaming langsung ke file atau menggunakan `BufferedStream` untuk menghindari konsumsi memori yang tinggi.

**Q: Apakah driver GeoJSON mendukung definisi CRS (Coordinate Reference System)?**  
A: Ya—atur properti `SpatialReferenceSystem` lapisan sebelum menambahkan fitur jika Anda memerlukan CRS non‑WGS84.

## Kesimpulan
Anda kini memiliki pola lengkap yang siap produksi untuk **how to write geojson** ke aliran .NET apa pun menggunakan Aspose.GIS. Baik Anda perlu mengembalikan GeoJSON dari API web, menyimpannya ke file, atau sekadar menampilkannya di konsol, langkah‑langkah di atas mencakup seluruh alur kerja. Jelajahi pustaka lebih lanjut untuk bekerja dengan format lain seperti Shapefile, KML, atau GML, dan terus membangun aplikasi geospasial yang lebih kaya.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Terakhir Diperbarui:** 2026-01-02  
**Diuji Dengan:** Aspose.GIS 24.11 untuk .NET  
**Penulis:** Aspose