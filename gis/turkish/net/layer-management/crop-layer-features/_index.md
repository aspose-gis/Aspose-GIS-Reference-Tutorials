---
date: 2026-01-13
description: Aspose.GIS for .NET ile katman özelliklerini nasıl kırpacağınızı öğrenin;
  poligonla raster kırpma, raster hücre boyutunu çıkarma ve raster kapsamını alma
  konularını da içerir. Ücretsiz denemenizi şimdi indirin.
linktitle: How to Crop Layer Features
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET ile Katman Özelliklerini Nasıl Kırpılır?
url: /tr/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Katman Özelliklerini Kırpma

## Giriş
Bu öğreticide Aspose.GIS for .NET kullanarak **katman kırpma** özelliklerini öğreneceksiniz; bu güçlü yaklaşım **poligon ile raster kırpma**, **raster hücre boyutunu çıkar** ve **raster kapsamını al** imkanı sağlar ve hassas coğrafi analizler yapmanıza olanak tanır. Web haritası için veri hazırlıyor, uydu görüntülerini kırpıyor ya da ilgi alanı bölgesini izole ediyor olsanız, bu adım‑adım kılavuz tam olarak işi nasıl yapacağınızı gösterir.

## Hızlı Yanıtlar
- **“crop layer” ne anlama geliyor?** Sağlanan bir geometri sınırlarına göre raster veya vektör katmanını kırpar.  
- **Bu örnekte hangi geometri kullanılıyor?** WKT formatında tanımlanmış bir poligon.  
- **Kırptıktan sonra hücre boyutunu çıkarabilir miyim?** Evet – `CellSize` özelliği bu bilgiyi sağlar.  
- **Kodu çalıştırmak için lisansa ihtiyacım var mı?** Değerlendirme için geçici bir lisans yeterlidir; üretim için tam lisans gerekir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## “Katman kırpma” nedir?
Bir katmanı kırpmak, veri kümesini belirli bir coğrafi alana sınırlamak ve tanımlı şeklin dışındaki her şeyi atmak anlamına gelir. Bu, dosya boyutunu azaltır, işlem süresini hızlandırır ve analizleri ilgilendiğiniz bölgeye odaklar.

## Kırpma için neden Aspose.GIS kullanmalı?
- **Yüksek performanslı raster işleme** – büyük GeoTiff dosyaları için idealdir.  
- **Basit API** – herhangi bir geometri ile tek satır `Crop` çağrısı.  
- **Tam .NET uyumluluğu** – masaüstü, sunucu ve bulut uygulamalarında çalışır.  
- **Doğru mekânsal referans yönetimi** – CRS bilgilerini otomatik olarak korur.

## Önkoşullar
Coğrafi veri manipülasyonunun büyüsüne dalmadan önce, aşağıdaki önkoşulların yerine getirildiğinden emin olun:

- Aspose.GIS for .NET Kütüphanesi: Aspose.GIS kütüphanesinin .NET projenize kurulu olduğundan emin olun. [buradan](https://releases.aspose.com/gis/net/) indirebilirsiniz.  
- Belge Dizini: Belgelerinizi saklamak için bir dizin oluşturun. Sağlanan kodda `"Your Document Directory"` ifadesini gerçek belge dizini yolunuzla değiştirin.

Şimdi, adım‑adım kılavuza dalalım.

## Namespace'leri İçe Aktarın
Aspose.GIS'in tam gücünden yararlanmak için gerekli namespace'leri içe aktararak başlayın:

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Adım 1: Katmanı Aç ve Kırp (poligon ile raster kırpma)
GeoTiff katmanını açarak ve tanımlı bir poligon temelinde kırparak başlayın. Bu, coğrafi verilerinizin belirli bir ilgi alanına daraltılmasını sağlar.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## Adım 2: Raster Bilgilerini Al (raster hücre boyutunu çıkar ve raster kapsamını al)
Katman kırpıldıktan sonra, hücre boyutu, mekânsal referans sistemi ve sınırlar gibi raster verisinin temel bilgilerini çıkarın.

```csharp
// read and print raster
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
```

## Adım 3: Bilgileri Görüntüle
Kırpma işleminin coğrafi verileriniz üzerindeki etkisini anlamak için çıkarılan bilgileri yazdırın.

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
| **Eksik mekânsal referans** | Kaynak GeoTiff'in bir CRS içerdiğini doğrulayın; aksi takdirde kırpmadan önce manuel olarak bir CRS ayarlayın. |
| **Büyük raster'larda performans yavaşlaması** | `layer.Crop` yöntemini düşük çözünürlüklü bir kopyada kullanın veya raster'ı döşemeler halinde işleyin. |

## Sıkça Sorulan Sorular
### Q: Aspose.GIS for .NET için geçici bir lisans mevcut mu?
E: Evet, geçici bir lisansı [buradan](https://purchase.aspose.com/temporary-license/) alabilirsiniz.

### Q: Aspose.GIS for .NET için kapsamlı dokümantasyonu nereden bulabilirim?
E: Dokümantasyon [burada](https://reference.aspose.com/gis/net/) mevcuttur.

### Q: Aspose.GIS for .NET için destek alabilir veya toplulukla iletişime geçebilir miyim?
E: Destek ve topluluk etkileşimi için [Aspose.GIS forumunu](https://forum.aspose.com/c/gis/33) ziyaret edin.

### Q: Aspose.GIS for .NET'in ücretsiz deneme sürümünü indirebilir miyim?
E: Evet, ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) indirebilirsiniz.

### Q: Aspose.GIS for .NET'i nereden satın alabilirim?
E: Kütüphaneyi [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

### Q: Tek bir çalıştırmada birden fazla katmanı kırpabilir miyim?
E: Evet—her katman üzerinde döngü yaparak istediğiniz geometriyle aynı `Crop` çağrısını uygulayabilirsiniz.

### Q: API diğer raster formatlarını (ör. JPEG2000) destekliyor mu?
E: Aspose.GIS, temel GDAL sürücülerinin desteklediği tüm formatları, JPEG2000, PNG ve daha fazlasını destekler.

## Sonuç
Bu kılavuzu izleyerek artık Aspose.GIS for .NET ile **katman kırpma** özelliklerini verimli bir şekilde nasıl yapacağınızı biliyorsunuz. **Poligon ile raster kırpma**, **raster hücre boyutunu çıkar** ve **raster kapsamını al** işlemlerini kolayca gerçekleştirebilir ve herhangi bir projenin ihtiyaçlarına uyarlayabilirsiniz. Yeniden projeksiyon, raster stil verme ve vektör analizi için diğer API'ları keşfederek coğrafi iş akışlarınızın tam potansiyelini ortaya çıkarın.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-13  
**Tested With:** Aspose.GIS 24.10 for .NET  
**Author:** Aspose