---
date: 2026-05-16
description: Contoh layer vektor yang menunjukkan cara mengatur field width, mendefinisikan
  attribute width, dan menambahkan attribute length di Aspose.GIS for .NET – panduan
  langkah demi langkah yang lengkap.
keywords:
- vector layer example
- how to set width
- set field width
- define attribute width
- add attribute length
linktitle: Cara Mengatur Field Width
schemas:
- author: Aspose
  dateModified: '2026-05-16'
  description: Vector layer example showing how to set field width, define attribute
    width, and add attribute length in Aspose.GIS for .NET – a complete step‑by‑step
    guide.
  headline: Vector Layer Example – How to Set Field Width in Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for peer‑to‑peer
      help and official responses.
    question: Where can I find community support for Aspose.GIS for .NET?
  - answer: Yes, explore the [free trial](https://releases.aspose.com/) to experience
      the full feature set without cost.
    question: Is there a free trial available for Aspose.GIS for .NET?
  - answer: Purchase your license [here](https://purchase.aspose.com/buy).
    question: How do I purchase a license for Aspose.GIS for .NET?
  - answer: Refer to the [documentation](https://reference.aspose.com/gis/net/) for
      comprehensive API details.
    question: Where can I access the documentation for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Contoh Layer Vektor – Cara Mengatur Field Width di Aspose.GIS for .NET
url: /id/net/layer-data-operations/specify-attribute-value-length/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Contoh Lapisan Vektor – Cara Mengatur Lebar Kolom di Aspose.GIS untuk .NET

Dalam **contoh lapisan vektor** ini Anda akan belajar cara mengatur lebar kolom untuk sebuah atribut saat membuat Shapefile dengan Aspose.GIS untuk .NET. Kami akan membahas setiap langkah, mulai dari mengimpor namespace hingga menambahkan fitur, dan menjelaskan mengapa mengontrol panjang atribut penting untuk integritas data dan interoperabilitas dengan alat GIS lainnya.

## Jawaban Cepat
- **Apa tujuan utama panduan ini?** Menunjukkan cara mengatur lebar kolom untuk sebuah atribut dalam shapefile menggunakan Aspose.GIS untuk .NET.  
- **Kelas mana yang mendefinisikan lebar kolom?** `FeatureAttribute.Width`.  
- **Apakah saya memerlukan lisensi untuk menjalankan kode?** Lisensi sementara dapat digunakan untuk evaluasi; lisensi penuh diperlukan untuk produksi.  
- **Format file apa yang digunakan dalam contoh ini?** ESRI Shapefile (`.shp`).  
- **Bisakah saya mengubah lebar setelah lapisan dibuat?** Tidak – lebar harus didefinisikan sebelum menambahkan fitur.

## Apa Itu Lebar Kolom dan Mengapa Penting?
Lebar kolom (juga disebut panjang atribut) adalah jumlah maksimum karakter yang dapat disimpan oleh sebuah field string dalam komponen DBF Shapefile. Menetapkan lebar yang tepat mencegah pemotongan diam-diam, memastikan bahwa aplikasi GIS lain membaca data persis seperti yang Anda masukkan, dan menjaga ukuran file tetap dapat diprediksi—setiap karakter tambahan menambah satu byte per record.

## Prasyarat
- **Aspose.GIS for .NET Library** – unduh dari [download link](https://releases.aspose.com/gis/net/).  
- **Lingkungan Pengembangan** – Visual Studio 2022, Visual Studio Code, atau IDE apa pun yang mendukung .NET 6+.  
- **Akses Tulis** – folder di disk tempat shapefile yang dihasilkan akan disimpan.

## Mengapa Menggunakan Contoh Lapisan Vektor dengan Lebar yang Ditentukan?
Aspose.GIS mendukung **lebih dari 30 format file GIS**, termasuk Shapefile, GeoJSON, KML, dan GML. Ketika Anda secara eksplisit mengatur lebar kolom, Anda menghindari batas default 255 karakter, yang dapat secara tidak perlu memperbesar file `.dbf` hingga 255 × recordCount byte. Pada dataset besar, hal ini berarti penghematan penyimpanan yang signifikan.

## Cara Mengatur Lebar Kolom untuk Sebuah Atribut?
Pada bagian ini kami memuat atau membuat `VectorLayer` yang menunjuk ke file `.shp` target, mendefinisikan atribut string dengan lebar yang tepat, dan kemudian menambahkan fitur—semua dalam beberapa pernyataan singkat. `VectorLayer` mewakili dataset vektor seperti Shapefile dan menyediakan akses ke geometri serta tabel atributnya. Berikut adalah resep langsung yang dapat Anda ikuti langkah demi langkah:

Muat atau buat `VectorLayer` yang menunjuk ke file `.shp` target, deklarasikan atribut string bernama **wide** dengan `Width = 120`, kemudian tambahkan fitur yang nilainya mematuhi batas 120 karakter tersebut. Aspose.GIS secara otomatis akan memotong string yang lebih panjang ke lebar yang ditentukan, menjaga konsistensi data tanpa melempar pengecualian.

### Impor Namespace
`FeatureAttribute`, `VectorLayer`, dan tipe terkait berada di namespace `Aspose.Gis`. Impor mereka di bagian atas file Anda:

The `Aspose.Gis` namespace provides the core GIS objects you’ll work with, such as `VectorLayer`, `Feature`, and `FeatureAttribute`. Importing it makes the classes available without fully‑qualified names.

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Buat VectorLayer
Kelas `VectorLayer` mewakili sumber data vektor (mis., Shapefile). Ini adalah kontainer yang menyimpan fitur dan atributnya.

Kelas `VectorLayer` adalah representasi Aspose.GIS untuk dataset vektor, mengelola geometri dan tabel atribut dalam memori. Buat sebuah instance yang menunjuk ke file `.shp` baru atau yang sudah ada.

```csharp
string dataDir = "Your Document Directory";
using (VectorLayer layer = VectorLayer.Create(dataDir + "SpecifyAttributeValueLength_out.shp", Drivers.Shapefile))
{
    // Your code for the next steps will go here.
}
```

### Tambahkan Atribut dengan Panjang Spesifik
Definisikan atribut string bernama **wide** dan atur properti `Width`-nya menjadi 120 karakter. Ini adalah langkah inti dari **contoh lapisan vektor**.

Objek `FeatureAttribute` menggambarkan sebuah kolom dalam tabel atribut; mengatur `Width = 120` memberi tahu penulis Shapefile untuk mengalokasikan tepat 120 byte untuk setiap record pada field ini.

```csharp
FeatureAttribute attribute = new FeatureAttribute("wide", AttributeDataType.String);
attribute.Width = 120;
layer.Attributes.Add(attribute);
```

> **Tip Pro:** Properti `Width` hanya berlaku untuk atribut string. Field numerik, tanggal, atau Boolean mengabaikan `Width` karena ukuran mereka ditentukan oleh tipe data.

### Buat dan Tambahkan Fitur
Buat sebuah `Feature`, tetapkan nilai yang sesuai dengan batas 120 karakter, dan tambahkan ke lapisan. Jika string melebihi batas, Aspose.GIS secara diam-diam memotongnya ke lebar yang ditentukan, menjaga integritas data.

Kelas `Feature` mengenkapsulasi geometri dan nilai atribut; setelah mengatur atribut, memanggil `layer.Add(feature)` menulis record ke Shapefile.

```csharp
Feature feature = layer.ConstructFeature();
feature.SetValue("wide", "this string can be up to 120 characters long now.");
layer.Add(feature);
```

Jika Anda mencoba menetapkan string yang lebih panjang, Aspose.GIS akan memotongnya ke lebar yang ditentukan, menjaga integritas data.

## Kesalahan Umum & Pemecahan Masalah
- **Lupa mengatur `Width` sebelum menambahkan atribut?** Lebar default adalah 255 karakter; mengubahnya kemudian tidak memengaruhi field yang sudah dibuat. Selalu definisikan lebar terlebih dahulu.  
- **Menggunakan tipe data non‑string?** `Width` diabaikan untuk field numerik atau tanggal; pastikan `AttributeDataType` atribut adalah `String`.  
- **Error “Field not found”?** Nama atribut bersifat case‑sensitive. Pastikan nama yang digunakan dalam `SetValue` persis sama dengan nama yang didefinisikan dalam skema.  
- **Peningkatan ukuran file yang tidak terduga?** Lebar yang lebih besar meningkatkan ukuran `.dbf` secara linier. Untuk 10 000 record, peningkatan lebar dari 50 ke 120 menambah sekitar 700 KB.

## Pertanyaan yang Sering Diajukan
**Q: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.GIS untuk .NET?**  
A: Anda dapat memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

**Q: Di mana saya dapat menemukan dukungan komunitas untuk Aspose.GIS untuk .NET?**  
A: Kunjungi [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) untuk bantuan sesama pengguna dan respons resmi.

**Q: Apakah ada percobaan gratis untuk Aspose.GIS untuk .NET?**  
A: Ya, jelajahi [percobaan gratis](https://releases.aspose.com/) untuk merasakan semua fitur tanpa biaya.

**Q: Bagaimana cara membeli lisensi untuk Aspose.GIS untuk .NET?**  
A: Beli lisensi Anda [di sini](https://purchase.aspose.com/buy).

**Q: Di mana saya dapat mengakses dokumentasi untuk Aspose.GIS untuk .NET?**  
A: Lihat [dokumentasi](https://reference.aspose.com/gis/net/) untuk detail API yang komprehensif.

**Q: Bisakah saya mengubah lebar kolom setelah lapisan dibuat?**  
A: Tidak. Lebar kolom harus didefinisikan sebelum atribut ditambahkan; untuk mengubahnya Anda harus membuat ulang lapisan dengan skema baru.

**Q: Apakah mengatur lebar yang lebih besar memengaruhi ukuran file?**  
A: Shapefile menyimpan field string dengan panjang tetap, sehingga meningkatkan lebar secara langsung menambah ukuran file `.dbf` secara proporsional dengan jumlah record.

## Kesimpulan
**contoh lapisan vektor** ini menunjukkan cara mengatur lebar kolom untuk sebuah atribut dalam Shapefile menggunakan Aspose.GIS untuk .NET, dan memperlihatkan cara menambahkan atribut dengan panjang tertentu secara efisien. Dengan mengontrol lebar atribut, Anda menghindari pemotongan data, menjaga ukuran file tetap optimal, dan memastikan interoperabilitas yang mulus dengan platform GIS lainnya. Bereksperimenlah dengan lebar yang berbeda, jelajahi [dokumentasi](https://reference.aspose.com/gis/net/), dan buka potensi penuh pengembangan geospasial dengan Aspose.GIS.

---

**Terakhir Diperbarui:** 2026-05-16  
**Diuji Dengan:** Aspose.GIS 24.11 for .NET  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Dapatkan Atribut Lapisan – Mengambil Informasi Atribut Lapisan dengan Aspose.GIS untuk .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Cara Mendapatkan Nilai Atribut (Default) dengan Aspose.GIS untuk .NET](/gis/net/layer-interaction-and-data-access/get-feature-attribute-value-default/)
- [Buat Lapisan Vektor di File GDB – Tutorial Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}