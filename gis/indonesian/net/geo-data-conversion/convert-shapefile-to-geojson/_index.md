---
date: 2025-11-30
description: Pelajari cara mengonversi Shapefile ke GeoJSON dengan mudah di .NET menggunakan
  Aspose.GIS. Ikuti panduan langkah demi langkah kami untuk interoperabilitas data
  geospasial yang mulus.
language: id
linktitle: Convert Shapefile to GeoJSON
second_title: Aspose.GIS .NET API
title: Konversi Shapefile ke GeoJSON
url: /net/geo-data-conversion/convert-shapefile-to-geojson/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mengonversi Shapefile ke GeoJSON

## Pendahuluan
Dalam Sistem Informasi Geografis (GIS) modern, **interoperabilitas data geospasial** adalah kunci untuk membuka analisis spasial yang kuat. Salah satu tugas konversi yang paling umum adalah **mengonversi shapefile ke geojson**, memungkinkan pertukaran data ringan dengan peta web, aplikasi seluler, dan layanan cloud. Tutorial ini memandu Anda melalui seluruh proses menggunakan perpustakaan **Aspose.GIS .NET**, sehingga Anda dapat mengintegrasikan konversi langsung ke dalam aplikasi C# Anda.

## Jawaban Cepat
- **Perpustakaan apa yang menangani konversi?** Aspose.GIS for .NET  
- **Berapa lama implementasinya?** Typically under 10 minutes for a single file  
- **Apakah saya memerlukan lisensi?** A free trial works for development; a license is required for production  
- **Versi .NET yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **Bisakah saya mengonversi banyak file?** Yes – just loop over the `VectorLayer.Convert` call  

## Apa itu “convert shapefile to geojson”?
Mengonversi Shapefile (sekumpulan file `.shp`, `.shx`, `.dbf`) menjadi GeoJSON mengubah data menjadi format berbasis JSON tunggal yang mudah dibaca, diedit, dan ditampilkan di browser web. GeoJSON sangat cocok untuk perpustakaan pemetaan JavaScript seperti Leaflet atau Mapbox.

## Mengapa menggunakan Aspose.GIS untuk .NET untuk konversi format data GIS?
- **API All‑in‑one** – Menangani puluhan format (GeoTIFF, KML, GML, dll.) tanpa alat eksternal.  
- **Konversi tanpa ketergantungan** – Tidak memerlukan GDAL atau pustaka native lainnya.  
- **Kinerja tinggi** – Dioptimalkan untuk dataset besar dan pemrosesan batch.  
- **Kustomisasi kaya** – Anda dapat menentukan sistem koordinat, filter atribut, dan lainnya.  

## Prasyarat
Sebelum Anda memulai, pastikan Anda memiliki hal‑hal berikut:

1. **Aspose.GIS untuk .NET terpasang** – Ikuti petunjuk pada [dokumentasi resmi Aspose.GIS untuk .NET](https://reference.aspose.com/gis/net/) untuk menambahkan paket NuGet ke proyek Anda.  
2. **Shapefile sumber** – Dapatkan satu dari portal data terbuka, lembaga pemerintah, atau buat dengan QGIS/ArcGIS.  
3. **Pengetahuan dasar C#** – Potongan kode menggunakan sintaks C# dan konvensi .NET.  

## Impor Namespace
Pertama, impor namespace yang memberi Anda akses ke kelas Aspose.GIS dan utilitas .NET standar:

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Panduan Langkah demi Langkah

### Langkah 1: Tentukan Jalur Input dan Output
Tetapkan folder yang berisi Shapefile Anda dan tujuan untuk file GeoJSON. Sesuaikan jalur agar cocok dengan lingkungan Anda.

```csharp
string dataDir = "Your Document Directory";
string shapefilePath = dataDir + "InputShapeFile.shp";
string jsonPath = dataDir + "output_out.json";
```

> **Tip Pro:** Gunakan `Path.Combine(dataDir, "InputShapeFile.shp")` untuk membangun jalur yang independen platform.

### Langkah 2: Lakukan Konversi
Panggil metode statis `VectorLayer.Convert`. Baris tunggal ini membaca Shapefile, menerjemahkannya, dan menulis file GeoJSON.

```csharp
VectorLayer.Convert(shapefilePath, Drivers.Shapefile, jsonPath, Drivers.GeoJson);
```

Setelah eksekusi, `output_out.json` akan berisi FeatureCollection GeoJSON yang valid yang dapat Anda muat ke dalam penampil peta web apa pun.

## Masalah Umum & Solusi
| Masalah | Mengapa Terjadi | Solusi |
|---------|----------------|--------|
| **File tidak ditemukan** | `dataDir` salah atau file `.shp` tidak ada | Verifikasi jalur dan pastikan semua tiga komponen Shapefile (`.shp`, `.shx`, `.dbf`) ada. |
| **Tidak cocok sistem koordinat** | Shapefile sumber menggunakan proyeksi yang tidak dikenali oleh konsumen | Gunakan `VectorLayer.Open(...).CoordinateSystem` untuk mereproyeksi sebelum konversi. |
| **File besar menyebabkan tekanan memori** | Seluruh dataset dimuat ke memori | Proses fitur dalam potongan atau gunakan `VectorLayer.Stream` untuk konversi streaming. |

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya mengonversi banyak Shapefile ke GeoJSON sekaligus menggunakan Aspose.GIS untuk .NET?**  
A: Ya. Letakkan kode konversi di dalam loop `foreach` yang mengiterasi setiap file `.shp` dalam sebuah direktori.

**Q: Apakah Aspose.GIS untuk .NET kompatibel dengan semua versi .NET Framework?**  
A: Itu mendukung .NET Framework 4.5 ke atas, serta .NET Core 3.1+ dan .NET 5/6/7.

**Q: Apakah Aspose.GIS untuk .NET menyediakan dukungan untuk format geospasial lain selain Shapefile dan GeoJSON?**  
A: Tentu saja. Perpustakaan ini menangani format seperti GeoTIFF, KML, GML, CSV, dan banyak lagi.

**Q: Bisakah saya menyesuaikan proses konversi, seperti menentukan sistem koordinat atau pemetaan atribut?**  
A: Ya. API menyediakan overload dan properti untuk mengatur sistem koordinat target, memfilter atribut, dan memodifikasi geometri fitur selama konversi.

**Q: Apakah ada versi percobaan yang tersedia untuk Aspose.GIS untuk .NET?**  
A: Ya, Anda dapat mengunduh versi percobaan gratis dari [situs Aspose](https://releases.aspose.com/).

## Kesimpulan
Dengan mengikuti langkah‑langkah ini Anda kini tahu **cara mengonversi shapefile ke geojson** secara efisien menggunakan **Aspose.GIS untuk .NET**. Kemampuan ini membuka **interoperabilitas data geospasial** yang mulus, memungkinkan Anda memasukkan data spasial ke dalam peta web modern, API, dan alur analitik. Jelajahi fitur **konversi format data GIS** yang lebih luas dari Aspose.GIS untuk menangani KML, GML, dan format raster seiring proyek Anda berkembang.

---

**Terakhir Diperbarui:** 2025-11-30  
**Diuji Dengan:** Aspose.GIS for .NET 24.11  
**Penulis:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
