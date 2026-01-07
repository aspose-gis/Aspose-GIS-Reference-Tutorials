---
date: 2026-01-07
description: Pelajari cara mendapatkan properti fitur dari TopoJSON dengan Aspose.GIS
  untuk .NET dan mengambil ID fitur secara efisien.
linktitle: Access Features in TopoJSON
second_title: Aspose.GIS .NET API
title: Dapatkan Properti Fitur dari TopoJSON menggunakan Aspose.GIS untuk .NET
url: /id/net/layer-management/access-features-in-topojson/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dapatkan Properti Fitur dari TopoJSON menggunakan Aspose.GIS untuk .NET

## Pendahuluan
Dalam tutorial ini Anda akan menemukan cara **mendapatkan properti fitur** dari file TopoJSON dengan Aspose.GIS untuk .NET. Baik Anda perlu membaca nilai atribut, mengekstrak geometri, atau sekadar *mengambil id fitur* untuk pemrosesan lebih lanjut, langkah‑langkah di bawah ini akan memandu Anda melalui solusi bersih end‑to‑end. Pada akhir tutorial, Anda akan dapat menarik properti apa pun dari data TopoJSON Anda dan menggunakannya dalam aplikasi .NET Anda.

## Jawaban Cepat
- **Apa arti “mendapatkan properti fitur”?** Itu merujuk pada membaca nilai atribut (misalnya, id, name) yang terlampir pada setiap fitur geografis.  
- **Perpustakaan mana yang mendukung ini?** Aspose.GIS untuk .NET menyediakan API sederhana untuk penanganan TopoJSON.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis cukup untuk pengujian; lisensi komersial diperlukan untuk produksi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Seberapa cepat operasi ini?** Memuat dan mengiterasi fitur dilakukan di memori dan cocok untuk sebagian besar dataset berukuran menengah.

## Apa itu “mendapatkan properti fitur”?
Mendapatkan properti fitur berarti mengakses data atribut yang disimpan bersama setiap objek geografis dalam file TopoJSON. Properti ini dapat mencakup pengidentifikasi, nama, klasifikasi, atau metadata khusus apa pun yang menggambarkan fitur tersebut.

## Mengapa mengambil id fitur?
Operasi **mengambil id fitur** sering menjadi langkah pertama dalam alur kerja berbasis data—seperti penyaringan, penggabungan dengan tabel eksternal, atau visualisasi fitur tertentu pada peta. Mengetahui ID memungkinkan Anda menargetkan secara tepat fitur yang sedang dikerjakan.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki hal‑hal berikut:
- Pengetahuan dasar tentang C# dan .NET.  
- Perpustakaan Aspose.GIS untuk .NET terpasang. Anda dapat mengunduhnya [di sini](https://releases.aspose.com/gis/net/).  
- File TopoJSON contoh untuk pengujian. Anda dapat menemukan satu di [dokumentasi](https://reference.aspose.com/gis/net/).

## Impor Namespace
Mulailah dengan mengimpor namespace yang diperlukan ke dalam kode C# Anda:
```csharp
using Aspose.Gis;
using System;
using System.Text;
```

## Langkah 1: Siapkan Proyek Anda
Buat proyek C# baru (Console App, ASP.NET, dll.) dan tambahkan referensi ke DLL Aspose.GIS untuk .NET. Pastikan proyek menargetkan versi .NET yang didukung.

## Langkah 2: Muat Data TopoJSON dan Dapatkan Properti Fitur
```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
string sampleTopoJsonPath = dataDir + "sample.topojson";
StringBuilder builder = new StringBuilder();
// Open the TopoJSON file
using (VectorLayer layer = VectorLayer.Open(sampleTopoJsonPath, Drivers.TopoJson))
{
    // Iterate through each feature in the layer
    foreach (Feature feature in layer)
    {
        // get id property
        int id = feature.GetValue<int>("id");
        // get name of the object that contains this feature
        string objectName = feature.GetValue<string>("topojson_object_name");
        // get name attribute property, located inside 'properties' object
        string name = feature.GetValue<string>("name");
        // get geometry of the feature.
        string geometry = feature.Geometry.AsText();
        // Build the output string
        builder.AppendFormat("Feature with ID {0}:\n", id);
        builder.AppendFormat("Object Name = {0}\n", objectName);
        builder.AppendFormat("Name        = {0}\n", name);
        builder.AppendFormat("Geometry    = {0}\n", geometry);
    }
}
// Display the output
Console.WriteLine("Output:");
Console.WriteLine(builder.ToString());
```

Pada cuplikan di atas kami **mengambil id fitur** (`id`) dan atribut lain (`name`, `topojson_object_name`). Inilah inti dari “mendapatkan properti fitur” dari sumber TopoJSON.

## Masalah Umum dan Solusinya
- **File tidak ditemukan** – Pastikan `sample.topojson` ada di direktori yang ditentukan dan path‑nya benar.  
- **Properti tidak ada** – Jika nama properti salah (misalnya, typo pada `"name"`), `GetValue<T>` akan melempar pengecualian. Gunakan `feature.TryGetValue<T>` untuk menangani properti opsional dengan aman.  
- **File besar** – Untuk file TopoJSON yang sangat besar, pertimbangkan memproses fitur secara batch atau menggunakan API streaming untuk mengurangi konsumsi memori.

## Pertanyaan yang Sering Diajukan

**T: Di mana saya dapat menemukan dokumentasi lebih lanjut?**  
J: Kunjungi [dokumentasi Aspose.GIS untuk .NET](https://reference.aspose.com/gis/net/).

**T: Bagaimana cara mengunduh Aspose.GIS untuk .NET?**  
J: Unduh perpustakaan [di sini](https://releases.aspose.com/gis/net/).

**T: Di mana saya dapat mendapatkan dukungan untuk Aspose.GIS?**  
J: Bergabunglah dengan [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) untuk bantuan.

**T: Apakah ada versi percobaan gratis?**  
J: Ya, Anda dapat mengakses percobaan gratis [di sini](https://releases.aspose.com/).

**T: Bagaimana cara membeli lisensi?**  
J: Beli lisensi [di sini](https://purchase.aspose.com/buy).

**T: Bisakah saya menggunakan kode ini dengan .NET Core?**  
J: Tentu—Aspose.GIS mendukung .NET Core 3.1 dan versi lebih baru.

**T: Bagaimana jika saya perlu menulis properti yang diekstrak ke file CSV?**  
J: Setelah membangun `StringBuilder`, Anda dapat menulis isinya ke file menggunakan `File.WriteAllText("output.csv", builder.ToString());`.

## Kesimpulan
Selamat! Anda telah mempelajari cara **mendapatkan properti fitur** dari file TopoJSON dan **mengambil id fitur** menggunakan Aspose.GIS untuk .NET. Dasar ini memungkinkan Anda membangun aplikasi geospasial yang lebih kaya, melakukan analisis data, atau mengintegrasikan data GIS ke dalam solusi .NET apa pun.

---

**Terakhir Diperbarui:** 2026-01-07  
**Diuji Dengan:** Aspose.GIS untuk .NET 24.11  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}