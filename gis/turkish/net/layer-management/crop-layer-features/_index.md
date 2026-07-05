---
date: 2026-07-05
description: Aspose.GIS for .NET ile katman özelliklerini nasıl kırpacağınızı öğrenin;
  poligonla raster kırpma, raster hücre boyutunu çıkarma ve raster kapsamını alma
  gibi konuları içerir. Şimdi ücretsiz denemenizi indirin.
keywords:
- how to crop layer
- extract raster extent
- get raster cell size
- crop raster layer
- crop raster with polygon
linktitle: Katman Özelliklerini Kırpma
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to crop layer features with Aspose.GIS for .NET, including
    how to crop raster with polygon, extract raster cell size, and retrieve raster
    extent. Download your free trial now.
  headline: How to Crop Layer Features with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Is a temporary license available for Aspose.GIS for .NET?
  - answer: The documentation is available [here](https://reference.aspose.com/gis/net/).
    question: Where can I find comprehensive documentation for Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for support
      and community engagement.
    question: How can I seek support or connect with the community for Aspose.GIS
      for .NET?
  - answer: Yes, you can download a free trial [here](https://releases.aspose.com/).
    question: Can I download a free trial of Aspose.GIS for .NET?
  - answer: You can purchase the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET ile Katman Özelliklerini Nasıl Kırpılır
url: /tr/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Katman Özelliklerini Kırpma

## Giriş
Bu öğreticide Aspose.GIS for .NET kullanarak **katman kırpma** özelliklerini öğreneceksiniz, bu güçlü kütüphane **poligon ile raster kırpma**, **raster hücre boyutunu çıkarma** ve **raster kapsamını alma** imkanı sağlar ve hassas coğrafi analiz yapmanıza olanak tanır. Web haritası için veri hazırlıyor, uydu görüntülerini kırpıyor ya da ilgi alanı bölgesini izole ediyor olun, bu adım‑adım kılavuz işinizi hızlı ve güvenilir bir şekilde nasıl tamamlayacağınızı gösterir.

## Hızlı Yanıtlar
- **“crop layer” ne anlama geliyor?** Bir raster veya vektör katmanını sağlanan geometrinin sınırlarına kadar kırpar, dışındaki her şeyi atar.  
- **Bu örnekte hangi geometri kullanılıyor?** WKT (Well‑Known Text) formatında tanımlanmış bir poligon.  
- **Kırpmadan sonra hücre boyutunu çıkarabilir miyim?** Evet – `CellSize` özelliği bir raster hücresinin genişliğini ve yüksekliğini döndürür.  
- **Kodu çalıştırmak için lisansa ihtiyacım var mı?** Değerlendirme için geçici bir lisans yeterlidir; üretim kullanımı için tam lisans gereklidir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## “Katman kırpma” nedir?
**Bir katmanı kırpmak, veri kümesini belirli bir coğrafi alana sınırlamak ve dışındaki her şeyi atmak anlamına gelir.** Bu işlem dosya boyutunu azaltır, sonraki işlemleri hızlandırır ve analizinizin odaklandığı bölgeye yönelir. Veriyi ilgi alanına sınırlayarak stil verme, analiz ve yayınlama gibi sonraki iş akışlarını da basitleştirir, aynı zamanda orijinal koordinat referans sistemi ve meta verileri korur.

## Neden Aspose.GIS Kırpmada Kullanılır?
**Aspose.GIS, tüm görüntüyü belleğe yüklemeden 2 GB'a kadar raster dosyalarını işleyebilir ve GeoTIFF, JPEG2000 ve PNG dahil olmak üzere 30'dan fazla raster formatını destekler.** Kütüphane tek satırlık `Crop` çağrısı, otomatik CRS yönetimi ve çok iş parçacıklı performans sunar; tipik bir sunucuda 500 MB'lık GeoTIFF'i bir saniyeden kısa sürede kırpabilir.

## Ön Koşullar
Geospatial manipülasyonunun büyüsüne dalmadan önce aşağıdaki ön koşulların yerine getirildiğinden emin olun:

- Aspose.GIS for .NET Kütüphanesi: Aspose.GIS kütüphanesinin .NET projenize kurulu olduğundan emin olun. [buradan](https://releases.aspose.com/gis/net/) indirebilirsiniz.  
- Belge Dizini: Belgelerinizi saklamak için bir dizin oluşturun. Sağlanan kodda `"Your Document Directory"` ifadesini gerçek belge dizini yolunuzla değiştirin.

Şimdi, adım‑adım kılavuza dalalım.

## Ad Alanlarını İçe Aktarma
`Aspose.Gis` ad alanı raster ve vektör işleme için tüm temel tipleri içerir. `Layer`, `Geometry` ve ilgili sınıflara erişmek için bu ad alanını içe aktarın.

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Bir Poligon ile Katmanı Nasıl Kırparım?
`Crop`, bir geometri tarafından tanımlanan raster alt kümesini çıkaran `Layer` sınıfının bir yöntemidir.  
Kaynak rasterı yükleyin, bir poligon geometrisi tanımlayın ve `Crop` yöntemini çağırın – tüm işlem tek bir kod satırıyla gerçekleştirilir. Yöntem, yalnızca poligon içindeki pikselleri içeren yeni bir raster döndürür ve orijinal uzamsal referansı otomatik olarak korur.

## Adım 1: Katmanı Aç ve Kırp (poligon ile raster kırpma)
`Layer`, açılabilen, sorgulanabilen ve düzenlenebilen bir raster veri kümesini temsil eder.  
`Layer` sınıfı, açılabilen, sorgulanabilen ve düzenlenebilen bir raster veri kümesini temsil eder. Bir GeoTIFF'i açıp poligon ile kırpmak, ilgi alanını sadece birkaç satırla izole eder.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## Adım 2: Raster Bilgilerini Al (raster hücre boyutunu çıkar ve raster kapsamını al)
`CellSize`, her raster hücresinin koordinat birimlerindeki genişlik ve yüksekliğini sağlar.  
`Extent`, rasterin coğrafi sınırlama kutusunu döndürür.  
`CellSize` özelliği her raster hücresinin koordinat birimlerindeki genişlik ve yüksekliğini sağlarken, `Extent` özelliği kırpılmış rasterin coğrafi sınırlama kutusunu döndürür. Bu iki bilgi, alan ölçümü veya yeniden projeksiyon gibi sonraki hesaplamalar için esastır.

```csharp
// read and print raster
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
```

## Adım 3: Bilgileri Görüntüle
Çıkarılan bilgileri yazdırarak kırpma işleminin coğrafi verileriniz üzerindeki etkisini anlayın.

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"source extent: {layer.GetExtent()}");
Console.WriteLine($"target extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
```

Bu adımları gerektiği gibi tekrarlayarak coğrafi verilerinizi belirli proje gereksinimlerine göre iyileştirin ve özelleştirin.

## Yaygın Sorunlar ve Çözümler
| Sorun | Çözüm |
|-------|----------|
| **Yanlış poligon yönelimi** | WKT poligonunun sağ el kuralına (dış halkalar için saat yönünün tersine) uygun olduğundan emin olun. |
| **Eksik uzamsal referans** | Kaynak GeoTiff'in bir CRS içerdiğini doğrulayın; aksi takdirde kırpmadan önce manuel olarak bir CRS ayarlayın. |
| **Büyük rasterlerde performans yavaşlaması** | `layer.Crop` yöntemini düşük çözünürlüklü bir kopyada kullanın veya rasteri döşemeler halinde işleyin. |

## Sıkça Sorulan Sorular
**S: Aspose.GIS for .NET için geçici bir lisans mevcut mu?**  
C: Evet, geçici bir lisansı [buradan](https://purchase.aspose.com/temporary-license/) alabilirsiniz.

**S: Aspose.GIS for .NET için kapsamlı belgeleri nerede bulabilirim?**  
C: Belgeler [burada](https://reference.aspose.com/gis/net/) mevcuttur.

**S: Aspose.GIS for .NET için destek alabilir veya toplulukla nasıl iletişime geçebilirim?**  
C: Destek ve topluluk etkileşimi için [Aspose.GIS forumunu](https://forum.aspose.com/c/gis/33) ziyaret edin.

**S: Aspose.GIS for .NET'in ücretsiz deneme sürümünü indirebilir miyim?**  
C: Evet, ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) indirebilirsiniz.

**S: Aspose.GIS for .NET'i nereden satın alabilirim?**  
C: Kütüphaneyi [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

**S: Tek bir çalıştırmada birden fazla katmanı kırpabilir miyim?**  
C: Evet—her katman üzerinde döngü yaparak istediğiniz geometriyle aynı `Crop` çağrısını uygulayabilirsiniz.

**S: API diğer raster formatlarını (ör. JPEG2000) destekliyor mu?**  
C: Aspose.GIS, temel GDAL sürücüleri tarafından sunulan tüm formatları, JPEG2000, PNG ve daha fazlasını destekler.

## Sonuç
Bu kılavuzu izleyerek artık Aspose.GIS for .NET ile **katman kırpma** özelliklerini verimli bir şekilde nasıl yapacağınızı biliyorsunuz. Herhangi bir projenin ihtiyacına göre **poligon ile raster kırpma**, **raster hücre boyutunu çıkarma** ve **raster kapsamını alma** işlemlerini kolayca yapabilirsiniz. Yeniden projeksiyon, raster stil verme ve vektör analiz için diğer API'ları keşfederek coğrafi iş akışlarınızın tam potansiyelini ortaya çıkarın.

---

**Last Updated:** 2026-07-05  
**Tested With:** Aspose.GIS 24.10 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [Aspose.GIS for .NET ile Poligon Geometrisi Oluşturma](/gis/net/geometry-creation/create-polygon-geometry/)
- [Katman Özelliklerini Al – Aspose.GIS for .NET ile Katman Özellik Bilgilerini Getirme](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [C# ile Poligon Geometrisi Oluşturma ve Aspose.GIS for .NET ile Kesişimi Kontrol Etme](/gis/net/geometry-analysis/check-geometries-intersection/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}