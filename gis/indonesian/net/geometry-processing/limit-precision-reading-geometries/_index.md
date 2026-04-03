---
date: 2026-04-03
description: Pelajari cara membuat lapisan vektor dan membatasi presisi saat membaca
  geometri menggunakan Aspose.GIS untuk .NET. Panduan langkah demi langkah untuk penanganan
  data geospasial yang optimal.
keywords:
- create vector layer
- reduce shapefile size
- set precision model
linktitle: Batasi Presisi Membaca Geometri
second_title: Aspose.GIS .NET API
title: Buat Lapisan Vektor, Batasi Presisi dengan Aspose.GIS untuk .NET
url: /id/net/geometry-processing/limit-precision-reading-geometries/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Layer Vektor, Batasi Presisi dengan Aspose.GIS untuk .NET

## Pendahuluan
Ketika bekerja dengan data geospasial, Anda sering perlu **create vector layer** objects dan memutuskan berapa banyak tempat desimal detail koordinat yang benar‑benar Anda butuhkan. Membatasi presisi tidak hanya mempercepat pemrosesan tetapi juga dapat **reduce shapefile size**, membuat penyimpanan dan transfer menjadi lebih efisien. Dalam tutorial ini kami akan membahas cara membuat layer vektor, menulis geometri titik sederhana, dan kemudian membacanya kembali menggunakan model presisi tepat dan dibulatkan. Pada akhir Anda akan memahami cara **set precision model** opsi yang sesuai dengan kebutuhan akurasi aplikasi Anda.

## Jawaban Cepat
- **Apa arti “limit precision”?** Ia membulatkan nilai koordinat ke sejumlah tempat desimal yang ditentukan.  
- **Mengapa membuat layer vektor terlebih dahulu?** Layer vektor adalah wadah yang menyimpan geometri seperti titik, garis, dan poligon.  
- **Model presisi apa yang tersedia?** `PrecisionModel.Exact` (tanpa pembulatan) dan `PrecisionModel.Rounding(n)` (membulatkan ke *n* desimal).  
- **Apakah saya memerlukan lisensi untuk mencoba ini?** Versi percobaan gratis tersedia di halaman rilis.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core, dan .NET 5/6+.

## Mengapa membatasi presisi dan bagaimana membantu?
- **Peningkatan kinerja** – Lebih sedikit digit berarti lebih sedikit data yang harus diparse dan diserialisasi.  
- **File lebih kecil** – Membulatkan koordinat dapat secara signifikan mengecilkan shapefile, terutama untuk dataset besar.  
- **Akurasi yang cukup** – Banyak analisis GIS tidak memerlukan presisi sub‑milimeter, sehingga pembulatan ke 2‑3 desimal biasanya sudah cukup.

## Prasyarat
Sebelum kita memulai perjalanan ini, pastikan Anda memiliki prasyarat berikut:
1. **Instalasi** – Pustaka Aspose.GIS untuk .NET harus diinstal di lingkungan pengembangan Anda. Jika belum, Anda dapat mengunduhnya dari [releases page](https://releases.aspose.com/gis/net/).
2. **Kefahaman tentang .NET** – Pengetahuan dasar tentang C# dan kerangka kerja .NET diperlukan untuk memahami dan mengimplementasikan contoh kode yang disediakan.
3. **Lingkungan Pengembangan** – Lingkungan pengembangan .NET yang berfungsi, seperti Visual Studio, diperlukan.
4. **Direktori Dokumen** – Miliki direktori yang sudah disiapkan untuk menyimpan dan mengakses shapefile yang dihasilkan selama proses.

## Impor Namespace
Sebelum kita mulai mengimplementasikan fungsionalitas untuk membatasi presisi saat membaca geometri, mari pastikan kita mengimpor namespace yang diperlukan:
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Cara Membuat Layer Vektor
Langkah pertama adalah **create vector layer** yang akan menampung geometri kami. Layer ini akan disimpan sebagai Shapefile sehingga kami dapat membukanya kembali nanti dengan pengaturan presisi yang berbeda.
```csharp
string path = "Your Document Directory" + "LimitPrecisionWhenReadingGeometries_out.shp";
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
	var feature = layer.ConstructFeature();
	feature.Geometry = new Point(1.10234, 2.09743);
	layer.Add(feature);
}
```

## Mengatur Opsi Presisi
Selanjutnya, kita perlu mendefinisikan opsi untuk membaca geometri, menentukan model presisi yang diinginkan. Kita dapat memulai dengan presisi tepat:
```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## Membaca Geometri dengan Presisi Tepat
Sekarang, mari buka layer vektor dengan opsi yang ditentukan untuk membaca geometri dengan presisi tepat:
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Memotong Presisi
Jika kita ingin memotong presisi ke sejumlah tempat desimal tertentu, kita dapat menyesuaikan model presisi sesuai:
```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Cara Mengatur Model Presisi untuk Berbagai Skenario
Anda mungkin bertanya kapan harus menggunakan `Exact` versus `Rounding`. Berikut dua skenario umum:

| Skenario | Model yang Direkomendasikan | Alasan |
|----------|-----------------------------|--------|
| Analisis ilmiah berpresisi tinggi | `PrecisionModel.Exact` | Tidak kehilangan detail koordinat |
| Peta web atau aplikasi seluler | `PrecisionModel.Rounding(2)` | Mengurangi ukuran file dan mempercepat rendering |

## Masalah Umum dan Solusinya
- **Nilai koordinat tidak terduga** – Pastikan Anda mengatur `options.XYPrecisionModel` *sebelum* membuka layer. Mengubahnya setelah membuka tidak berpengaruh.  
- **File tidak ditemukan** – Verifikasi bahwa variabel `path` mengarah ke direktori yang valid dan bahwa Shapefile berhasil dibuat pada langkah sebelumnya.  
- **Tipe geometri tidak tepat** – Contoh ini menggunakan `Point`. Untuk tipe geometri lain (misalnya, `LineString`), casting harus sesuai dengan tipe sebenarnya.  

## Tips untuk Mengurangi Ukuran Shapefile
- Gunakan `PrecisionModel.Rounding` dengan jumlah desimal terkecil yang masih memenuhi kebutuhan akurasi Anda.  
- Hapus field atribut yang tidak diperlukan sebelum menulis layer.  
- Kompres file `.shp`, `.shx`, dan `.dbf` yang dihasilkan menggunakan utilitas ZIP standar jika Anda perlu mentransfernya.

## Kesimpulan
Sebagai kesimpulan, mengelola presisi saat membaca geometri adalah aspek penting dalam manipulasi data geospasial. Aspose.GIS untuk .NET menyediakan fungsionalitas yang kuat untuk mencapai hal ini secara efisien. Dengan mengikuti langkah-langkah di atas Anda dapat dengan mulus **create vector layer** objek, **set precision model**, dan bahkan **reduce shapefile size** bila tepat, memastikan penanganan data yang optimal dalam aplikasi Anda.

## FAQ
### Bisakah saya menggunakan Aspose.GIS untuk .NET dengan kerangka .NET lain seperti .NET Core atau .NET Standard?
Ya, Aspose.GIS untuk .NET kompatibel dengan berbagai kerangka .NET, termasuk .NET Core dan .NET Standard.

### Apakah ada versi percobaan tersedia untuk Aspose.GIS untuk .NET?
Ya, Anda dapat memperoleh versi percobaan gratis dari [releases page](https://releases.aspose.com/).

### Di mana saya dapat menemukan dokumentasi lengkap untuk Aspose.GIS untuk .NET?
Anda dapat merujuk ke [documentation](https://reference.aspose.com/gis/net/) untuk informasi detail dan contoh.

### Bagaimana cara mendapatkan lisensi sementara untuk Aspose.GIS untuk .NET?
Lisensi sementara dapat diperoleh dari [purchase page](https://purchase.aspose.com/temporary-license/) untuk Aspose.GIS.

### Di mana saya dapat mencari bantuan atau dukungan untuk Aspose.GIS untuk .NET?
Anda dapat mengunjungi [forum](https://forum.aspose.com/c/gis/33) Aspose.GIS untuk pertanyaan, diskusi, atau kebutuhan dukungan.

## Pertanyaan yang Sering Diajukan
**Q: Apakah membatasi presisi memengaruhi shapefile asli?**  
A: Tidak. Presisi hanya diterapkan saat membaca geometri; file sumber tetap tidak berubah.  

**Q: Apakah saya dapat menggunakan model presisi yang berbeda untuk koordinat X dan Y?**  
A: Aspose.GIS saat ini menerapkan `XYPrecisionModel` yang sama untuk kedua sumbu.  

**Q: Apakah memungkinkan untuk mengatur fungsi pembulatan khusus?**  
A: API hanya mendukung metode bawaan `PrecisionModel.Rounding(int)`. Untuk logika khusus, Anda harus memproses koordinat setelah membaca.

---

**Terakhir Diperbarui:** 2026-04-03  
**Diuji Dengan:** Aspose.GIS 24.11 for .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}