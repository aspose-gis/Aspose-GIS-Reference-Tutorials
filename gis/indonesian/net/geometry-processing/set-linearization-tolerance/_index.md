---
date: 2026-05-31
description: Pelajari cara membuat GeoJSON, mengonfigurasi opsi GeoJSON, dan menambahkan
  fitur ke lapisan menggunakan Aspose.GIS untuk .NET. Ikuti panduan langkah demi langkah
  ini.
keywords:
- how to create geojson
- add feature to layer
- configure geojson options
linktitle: Atur Toleransi Linearization
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  headline: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  name: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  steps:
  - name: Configure GeoJSON Options (how to set tolerance)
    text: '`GeoJsonOptions` specifies the serialization settings used when writing
      GeoJSON files. `GeoJsonOptions` defines how Aspose.GIS serializes GeoJSON, including
      linearization tolerance, coordinate precision, and other output settings. We’ll
      create a `GeoJsonOptions` object and tell Aspose.GIS how close '
  - name: Define the Output Path (how to export GeoJSON)
    text: Specify the full file path where the resulting GeoJSON will be saved. Ensure
      the folder exists and the application has write permissions.
  - name: '**Create Vector Layer** with the configured options'
    text: The `VectorLayer` class represents a GIS container that can read and write
      spatial data. `Drivers.GeoJson` is the driver identifier for writing GeoJSON
      format files. Using `VectorLayer.Create` together with the `Drivers.GeoJson`
      driver and the previously configured `GeoJsonOptions` creates a new Geo
  - name: Construct a Geometry (e.g., a circular string)
    text: '`CircularString` is a curved line geometry that Aspose.GIS can linearize
      based on the tolerance you set. You can replace this with any valid WKT representation
      such as `POINT`, `LINESTRING`, or `POLYGON`.'
  - name: '**Add Feature to Layer** and save'
    text: '`Feature` is the object that couples a geometry with attribute data. After
      creating a `Feature` instance, assign the geometry, optionally add attribute
      values, and call `layer.Add(feature)` to persist it. When the `using` block
      ends, the layer is automatically written to the file defined in `path`. '
  type: HowTo
- questions:
  - answer: Yes, it works with .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6/7.
    question: Is Aspose.GIS for .NET compatible with other .NET frameworks?
  - answer: Absolutely. A commercial license removes all evaluation restrictions and
      provides full technical support.
    question: Can I use Aspose.GIS in commercial projects?
  - answer: Yes, it supports over 30 formats—including Shapefile, KML, GML, and CSV—allowing
      seamless conversion between them.
    question: Does Aspose.GIS support other GIS formats besides GeoJSON?
  - answer: You can download a free 30‑day trial from the Aspose website; it includes
      all features.
    question: Is there a trial version available?
  - answer: Use the Aspose forums, the dedicated support portal, or the “Contact Support”
      link in the product dashboard.
    question: Where can I get support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Cara Membuat GeoJSON dengan Toleransi Aspose.GIS untuk .NET
url: /id/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membuat GeoJSON dengan Toleransi Aspose.GIS untuk .NET

## Pendahuluan
Jika Anda ingin **belajar cara membuat GeoJSON** file, mengontrol presisi kurva, dan mengekspor hasilnya sebagai dokumen siap‑pakai, Aspose.GIS untuk .NET mempermudahnya. Dalam tutorial ini Anda akan menemukan cara mengonfigurasi opsi GeoJSON, mengatur toleransi linearitas, dan **menambahkan fitur ke lapisan** objek sambil menjaga kode tetap bersih dan siap produksi.

## Jawaban Cepat
- **Apa arti “create vector layer”?** Itu membuat dataset vektor GIS baru (misalnya, file GeoJSON) yang dapat menyimpan geometri dan atribut.  
- **Bagaimana cara mengatur toleransi linearitas?** Atur properti `LinearizationTolerance` pada instance `GeoJsonOptions` sebelum membuat lapisan.  
- **Bisakah saya mengekspor file GeoJSON secara langsung?** Ya—gunakan `VectorLayer.Create` dengan driver `Drivers.GeoJson` dan opsi yang telah dikonfigurasi.  
- **Apakah saya memerlukan lisensi?** Lisensi Aspose.GIS yang valid membuka semua fitur; kunci evaluasi sementara dapat digunakan untuk pengujian.  
- **Versi .NET mana yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Apa itu “create vector layer”?
Membuat lapisan vektor berarti menginisialisasi kontainer GIS baru (seperti file GeoJSON) yang dapat menampung titik, garis, poligon, dan data atribut terkait. Lapisan ini menjadi target untuk setiap geometri yang Anda buat dan setiap atribut yang Anda lampirkan.

## Mengapa mengonfigurasi opsi GeoJSON?
Mengonfigurasi opsi GeoJSON—terutama **toleransi linearitas**—memastikan bahwa geometri melengkung (misalnya, `CircularString`) diaproksimasi dengan presisi yang memenuhi persyaratan akurasi aplikasi Anda. Konfigurasi yang tepat mengurangi ukuran file sambil mempertahankan kesetiaan visual, yang penting ketika GeoJSON digunakan oleh peta web atau alat analitik spasial.

## Prasyarat
1. **Visual Studio** (versi terbaru apa pun).  
2. **Lisensi Aspose.GIS** (atau kunci evaluasi sementara).  
3. **Pustaka Aspose.GIS untuk .NET** yang direferensikan dalam proyek Anda.  
4. Familiaritas dasar dengan **C#**.

## Impor Namespace
Pertama, impor namespace yang diperlukan sehingga compiler mengetahui di mana menemukan kelas GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Panduan Langkah‑per‑Langkah

### Langkah 1: Konfigurasikan Opsi GeoJSON (cara mengatur toleransi)
`GeoJsonOptions` menentukan pengaturan serialisasi yang digunakan saat menulis file GeoJSON.  
`GeoJsonOptions` mendefinisikan cara Aspose.GIS men-serialize GeoJSON, termasuk toleransi linearitas, presisi koordinat, dan pengaturan output lainnya.  
Kami akan membuat objek `GeoJsonOptions` dan memberi tahu Aspose.GIS seberapa dekat geometri yang dilineariskan harus dengan kurva asli.

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### Langkah 2: Tentukan Jalur Output (cara mengekspor GeoJSON)
Tentukan jalur file lengkap tempat GeoJSON yang dihasilkan akan disimpan. Pastikan folder tersebut ada dan aplikasi memiliki izin menulis.

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### Langkah 3: **Create Vector Layer** dengan opsi yang dikonfigurasi
Kelas `VectorLayer` mewakili kontainer GIS yang dapat membaca dan menulis data spasial.  
`Drivers.GeoJson` adalah pengidentifikasi driver untuk menulis file format GeoJSON.  
Menggunakan `VectorLayer.Create` bersama dengan driver `Drivers.GeoJson` dan `GeoJsonOptions` yang telah dikonfigurasi sebelumnya membuat file GeoJSON baru yang siap untuk penyisipan fitur.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### Langkah 4: Bangun Geometri (mis., circular string)
`CircularString` adalah geometri garis melengkung yang dapat dilineariskan oleh Aspose.GIS berdasarkan toleransi yang Anda tetapkan. Anda dapat menggantinya dengan representasi WKT yang valid seperti `POINT`, `LINESTRING`, atau `POLYGON`.

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### Langkah 5: **Add Feature to Layer** dan simpan
`Feature` adalah objek yang menggabungkan geometri dengan data atribut. Setelah membuat instance `Feature`, tetapkan geometri, opsional tambahkan nilai atribut, dan panggil `layer.Add(feature)` untuk menyimpannya. Ketika blok `using` selesai, lapisan secara otomatis ditulis ke file yang didefinisikan dalam `path`.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

Ketika blok `using` selesai, lapisan secara otomatis ditulis ke file yang didefinisikan dalam `path`, memberikan Anda file GeoJSON siap‑pakai.

## Masalah Umum & Tips
- **Path tidak benar** – Verifikasi direktori ada dan Anda memiliki izin menulis.  
- **Toleransi terlalu rendah** – Menetapkan `LinearizationTolerance` ke nilai yang sangat kecil dapat meningkatkan ukuran file secara dramatis; toleransi 0.001 biasanya menyeimbangkan presisi dan ukuran.  
- **Kesalahan lisensi** – Jika Anda melihat peringatan lisensi, pastikan file lisensi dimuat sebelum panggilan Aspose.GIS apa pun.  
- **Catatan kinerja** – Aspose.GIS mendukung pemrosesan file hingga 2 GB tanpa memuat seluruh dokumen ke memori, berkat arsitektur streaming-nya.

## Pertanyaan yang Sering Diajukan

**Q: Apakah Aspose.GIS untuk .NET kompatibel dengan kerangka .NET lainnya?**  
A: Ya, ia bekerja dengan .NET Framework 4.5+, .NET Core 3.1+, dan .NET 5/6/7.

**Q: Bisakah saya menggunakan Aspose.GIS dalam proyek komersial?**  
A: Tentu saja. Lisensi komersial menghapus semua pembatasan evaluasi dan menyediakan dukungan teknis penuh.

**Q: Apakah Aspose.GIS mendukung format GIS lain selain GeoJSON?**  
A: Ya, ia mendukung lebih dari 30 format—termasuk Shapefile, KML, GML, dan CSV—memungkinkan konversi mulus di antara mereka.

**Q: Apakah ada versi percobaan yang tersedia?**  
A: Anda dapat mengunduh percobaan gratis 30‑hari dari situs web Aspose; itu mencakup semua fitur.

**Q: Di mana saya dapat mendapatkan dukungan?**  
A: Gunakan forum Aspose, portal dukungan khusus, atau tautan “Contact Support” di dasbor produk.

## Kesimpulan
Dengan mengikuti langkah‑langkah ini Anda kini tahu **cara membuat GeoJSON**, mengonfigurasi toleransi linearitas, dan **menambahkan fitur ke lapisan** untuk ekspor GeoJSON yang mulus. Jelajahi tipe geometri tambahan, penanganan atribut, dan skenario pemrosesan massal untuk memanfaatkan Aspose.GIS secara penuh dalam proyek GIS .NET Anda.

---

**Last Updated:** 2026-05-31  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Cara Mengonversi GeoJSON – Aspose.GIS untuk .NET](/gis/net/geo-data-conversion/)
- [Buat Vector Layer, Batasi Presisi dengan Aspose.GIS untuk .NET](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [Buat Vector Layer di File GDB – Tutorial Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}