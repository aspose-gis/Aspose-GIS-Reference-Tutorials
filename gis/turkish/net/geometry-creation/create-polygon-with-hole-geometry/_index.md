---
date: 2026-04-03
description: Aspose.GIS for .NET kullanarak delikli çokgen geometrisi oluşturmayı
  öğrenin. Bu kılavuz, çokgen içinde delik oluşturmayı ve coğrafi verilerle çalışmayı
  gösterir.
keywords:
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
linktitle: Delik İçeren Geometri ile Çokgen Oluştur
second_title: Aspose.GIS .NET API
title: Aspose.GIS Kullanarak Delik İçeren Poligon Oluşturma
url: /tr/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS kullanarak Delikli Poligon Geometrisi Oluşturma

## Giriş
Bu öğreticide, Aspose.GIS for .NET kullanarak **delikli poligon** geometrisi oluşturacaksınız. Haritalama uygulaması geliştiriyor, mekansal analiz yapıyor ya da GIS hizmetleri için veri hazırlıyor olun, bir poligon içinde delik yerleştirmeyi bilmek çok önemlidir. Ortamı kurmaktan son poligon nesnesini oluşturmaya kadar tüm süreci adım adım göstereceğiz.

## Hızlı Yanıtlar
- **“create polygon with hole” ne anlama geliyor?** Bu, alan dışı bırakılan bir veya daha fazla iç halka (delik) içeren bir poligon oluşturmak anlamına gelir.  
- **Bu işlemi hangi kütüphane yönetir?** Aspose.GIS for .NET, dış ve iç halkalar için tam destek sağlar.  
- **Bir lisansa ihtiyacım var mı?** Geliştirme için ücretsiz deneme sürümü çalışır; üretim için ticari lisans gereklidir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Ne kadar sürer?** Genellikle uygulama ve test için 10 dakikadan az sürer.

## Aspose.GIS kullanarak poligona delik ekleme
Delik eklemek sadece bir **interior ring** tanımlamak ve poligona eklemekle ilgilidir. Kütüphane yönelim ve geçerlilik konularını halleder, böylece ihtiyacınız olan boşluğu temsil eden koordinatlara odaklanabilirsiniz.

## “create polygon with hole” nedir?
Delikli bir poligon oluşturmak, dış sınırı belirleyen bir **exterior ring** ve boş alanları oluşturan bir veya daha fazla **interior rings** tanımlamayı içerir. İç halkalar genellikle *delikler* olarak adlandırılır çünkü poligon yüzeyinin bir parçası olmayan alanları temsil ederler.

## Aspose.GIS kullanarak poligon içinde neden delik oluşturulur?
- **Doğru mekansal modelleme:** Arazi parçaları içindeki göller ya da binalar içindeki avlular gibi gerçek dünya özellikleri delik gerektirir.  
- **Uyumluluk:** Shapefile, GeoJSON ve GML gibi formatlar iç halkaları doğal olarak destekler; Aspose.GIS bunları korur.  
- **Performans:** Kütüphane geometri geçerliliğini yönetir, böylece özel doğrulama kodu yazmanıza gerek kalmaz.

## Delikli Poligonlar için Gerçek Dünya Senaryoları
1. **İçinde göl bulunan arazi parçası** – göl, bir delik olarak modellenir, böylece parselin alanına dahil edilmez.  
2. **Avlulu bina ayak izleri** – avlu, binanın ayak izinden çıkarılır.  
3. **Daha büyük bir koruma alanı içindeki korunan bölgeler** – ayrı katmanlar oluşturmadan kısıtlı bölümleri dışarıda bırakabilirsiniz.

## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. Aspose.GIS for .NET Kütüphanesi: [buradan](https://releases.aspose.com/gis/net/) indirebilirsiniz.  
2. Geliştirme Ortamı: Visual Studio ya da başka bir .NET IDE kurulu bir geliştirme ortamınızın olduğundan emin olun.

## Ad Alanlarını İçe Aktarın
İlk olarak, Aspose.GIS işlevselliğiyle çalışmak için gerekli ad alanlarını içe aktarmanız gerekir. İşte nasıl yapılacağı:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Şimdi, Aspose.GIS for .NET kullanarak delikli bir poligon geometrisi oluşturmaya devam edelim.

## Adım 1: Polygon Nesnesi Oluşturma
Daha sonra dış ve iç halkaları tutacak boş bir `Polygon` nesnesi oluşturarak başlıyoruz.

```csharp
Polygon polygon = new Polygon();
```

## Adım 2: Exterior Ring Tanımlama
Exterior ring, poligonun dış sınırını tanımlar. Kapalı bir şekil oluşturmak için noktaları saat yönünde ekleyin.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## Adım 3: Interior Ring Tanımlama (Delik)
Sonra bir interior ring oluşturuyoruz—bu, poligonun alanından çıkarılacak **delik**tir. Noktalar genellikle saat yönünün tersinde eklenir, ancak Aspose.GIS yönelimi otomatik olarak yönetir.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## Adım 4: Exterior Ring'i Atama ve Interior Ring'i Poligona Ekleme
Son olarak, exterior ring'i poligona ekleyin ve ardından interior ring'i (delik) ekleyin. Birden fazla delik ihtiyacınız varsa `AddInteriorRing` yöntemi birden çok kez çağrılabilir.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## İpuçları ve En İyi Uygulamalar
- **Yönlendirme okunabilirlik için önemlidir** – Aspose.GIS yönlendirmeyi otomatik düzeltirken, exterior ring'leri saat yönünde ve interior ring'leri saat yönünün tersinde tutmak, geometrinin GIS görüntüleyicilerinde incelenmesini kolaylaştırır.  
- **Her halkayı kapatın** – her zaman ilk koordinatı son nokta olarak tekrarlayın; bu geçerli bir kapalı şekil garantiler.  
- **Oluşturduktan sonra doğrulayın** – kaydetmeden önce geometrinin OGC standartlarına uygunluğunu kontrol etmek için `polygon.IsValid` metodunu çağırabilirsiniz.

## Yaygın Sorunlar ve Çözümler
| Sorun | Sebep | Çözüm |
|-------|--------|-----|
| Delik GIS görüntüleyicide görünmüyor | Interior ring yönelimi ters | Noktaların exterior ring'in ters yönünde (saat yönünün tersinde) eklendiğinden emin olun. |
| Polygon geçersiz hatası | Halkalar kapalı değil (ilk ≠ son nokta) | Her halkada ilk noktayı son nokta olarak tekrarlayın (yukarıda gösterildiği gibi). |
| Beklenmedik boş geometri | Interior ring eklemeden önce `ExteriorRing` atamayı unutmak | Önce `polygon.ExteriorRing` atayın, ardından `AddInteriorRing` metodunu çağırın. |

## Sıkça Sorulan Sorular
### 1. Aspose.GIS nedir?
Aspose.GIS, geliştiricilerin coğrafi veri ile çalışmasını sağlayan, çeşitli coğrafi dosya formatlarını oluşturma, okuma ve manipüle etme imkanı veren bir .NET kütüphanesidir.

### 2. Aspose.GIS'i ticari projelerde kullanabilir miyim?
Evet, bir lisans satın alarak Aspose.GIS'i kişisel ve ticari projelerde kullanabilirsiniz. Daha fazla detay için [burayı](https://purchase.aspose.com/buy) ziyaret edin.

### 3. Aspose.GIS için ücretsiz deneme sürümü var mı?
Evet, Aspose.GIS'in ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) edinebilirsiniz.

### 4. Aspose.GIS için desteği nereden bulabilirim?
Aspose.GIS desteğini [Aspose.GIS forumunda](https://forum.aspose.com/c/gis/33) bulabilirsiniz.

### 5. Aspose.GIS için geçici bir lisans nasıl alabilirim?
Aspose.GIS için geçici bir lisansı [buradan](https://purchase.aspose.com/temporary-license/) alabilirsiniz.

---

**Son Güncelleme:** 2026-04-03  
**Test Edilen Versiyon:** Aspose.GIS 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}