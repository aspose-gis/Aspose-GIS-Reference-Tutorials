---
date: 2025-12-20
description: Aspose.GIS for .NET kullanarak delikli çokgen geometrisi oluşturmayı
  öğrenin. Bu kılavuz, çokgen içinde delik oluşturmayı ve coğrafi verilerle çalışmayı
  gösterir.
linktitle: Create Polygon with Hole Geometry
second_title: Aspose.GIS .NET API
title: Aspose.GIS kullanarak delikli çokgen oluşturma
url: /tr/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Poligon İçinde Delik Geometrisi Oluşturma Aspose.GIS Kullanarak

## Giriş
Bu öğreticide, Aspose.GIS for .NET kullanarak **delikli poligon** geometrisi oluşturacaksınız. Haritalama uygulaması geliştiriyor, mekansal analiz yapıyor ya da GIS hizmetleri için veri hazırlıyor olun, bir poligonun içine bir delik yerleştirmeyi bilmek önemlidir. Ortamı kurmaktan son poligon nesnesini üretmeye kadar tüm süreci adım adım göstereceğiz.

## Hızlı Yanıtlar
- **“delikli poligon oluşturma” ne anlama gelir?** Bu, bir veya daha fazla iç halka (delik) içeren ve bu alanların poligonun dış alanından çıkarıldığı bir poligon oluşturmak demektir.  
- **Hangi kütüphane bunu yönetir?** Aspose.GIS for .NET dış ve iç halkalar için tam destek sağlar.  
- **Lisans gerekiyor mu?** Geliştirme için ücretsiz deneme yeterlidir; üretim için ticari bir lisans gereklidir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Ne kadar sürer?** Genellikle uygulama ve test için 10 dakikadan az sürer.

## “delikli poligon oluşturma” nedir?
Delikli bir poligon oluşturmak, dış sınırı tanımlayan bir **exterior ring** (dış halka) ve bir veya daha fazla **interior ring** (iç halka) tanımlamayı içerir. İç halkalar genellikle *delik* olarak adlandırılır çünkü poligonun yüzeyine dahil olmayan alanları temsil ederler.

## Aspose.GIS ile poligon içinde neden delik oluşturmalıyız?
- **Doğru mekansal modelleme:** Arazi parçaları içinde göller veya binalar içinde avlular gibi gerçek dünya özellikleri delik gerektirir.  
- **Uyumluluk:** Shapefile, GeoJSON ve GML gibi formatlar iç halkaları doğal olarak destekler; Aspose.GIS bunları korur.  
- **Performans:** Kütüphane geometri geçerliliğini yönetir, böylece özel doğrulama kodu yazmanıza gerek kalmaz.

## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. Aspose.GIS for .NET Kütüphanesi: [buradan](https://releases.aspose.com/gis/net/) indirebilirsiniz.  
2. Geliştirme Ortamı: Visual Studio veya başka bir .NET IDE kurulu olduğundan emin olun.

## Ad Alanlarını İçe Aktarma
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
Dış ve iç halkaları daha sonra tutacak boş bir `Polygon` nesnesi örnekleyerek başlayacağız.

```csharp
Polygon polygon = new Polygon();
```

## Adım 2: Dış Halkayı Tanımlama
Dış halka, poligonun dış sınırını tanımlar. Kapalı bir şekil oluşturmak için saat yönünde noktalar ekleyin.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## Adım 3: İç Halkayı (Delik) Tanımlama
Sonra bir iç halka oluşturacağız—bu, poligonun alanından çıkarılacak **delik** olacaktır. Noktalar genellikle saat yönünün tersine eklenir, ancak Aspose.GIS yönlendirmeyi otomatik olarak yönetir.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## Adım 4: Dış Halkayı Ata ve İç Halkayı Poligona Ekle
Son olarak, dış halkayı poligona bağlayın ve ardından iç halkayı (delik) ekleyin. Birden fazla delik eklemeniz gerekiyorsa `AddInteriorRing` metodunu birden çok kez çağırabilirsiniz.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## Yaygın Sorunlar ve Çözümler
| Sorun | Neden | Çözüm |
|-------|--------|-----|
| Delik GIS görüntüleyicide görünmüyor | İç halkanın yönelimi ters | Noktaların dış halka yönünün tersine (saat yönünün tersine) eklendiğinden emin olun. |
| Poligon geçersiz hatası | Halkalar kapalı değil (ilk ≠ son nokta) | Her halkada ilk noktayı son nokta olarak tekrarlayın (yukarıdaki gibi). |
| Beklenmeyen boş geometri | `ExteriorRing` atamasını iç halkalar eklemeden önce unutmak | Önce `polygon.ExteriorRing`'i ayarlayın, ardından `AddInteriorRing` metodunu çağırın. |

## Sonuç
Tebrikler! Aspose.GIS for .NET kullanarak **delikli poligon** geometrisi oluşturmayı başarıyla öğrendiniz. Bu teknik, iç boşlukları olan karmaşık şekilleri temsil etmeniz gereken birçok coğrafi senaryo için temeldir.

## Sıkça Sorulan Sorular
### 1. Aspose.GIS nedir?
Aspose.GIS, geliştiricilerin coğrafi verilerle çalışmasını sağlayan bir .NET kütüphanesidir; çeşitli coğrafi dosya formatlarını oluşturma, okuma ve manipüle etme imkanı sunar.

### 2. Aspose.GIS'i ticari projelerde kullanabilir miyim?
Evet, bir lisans satın alarak Aspose.GIS'i kişisel ve ticari projelerde kullanabilirsiniz. Daha fazla bilgi için [buraya](https://purchase.aspose.com/buy) bakabilirsiniz.

### 3. Aspose.GIS için ücretsiz deneme mevcut mu?
Evet, [buradan](https://releases.aspose.com/) Aspose.GIS'in ücretsiz denemesinden yararlanabilirsiniz.

### 4. Aspose.GIS için desteği nereden bulabilirim?
Aspose.GIS desteğini [Aspose.GIS forumunda](https://forum.aspose.com/c/gis/33) bulabilirsiniz.

### 5. Aspose.GIS için geçici lisans nasıl alabilirim?
Geçici lisansı [buradan](https://purchase.aspose.com/temporary-license/) temin edebilirsiniz.

---

**Son Güncelleme:** 2025-12-20  
**Test Edilen:** Aspose.GIS 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}