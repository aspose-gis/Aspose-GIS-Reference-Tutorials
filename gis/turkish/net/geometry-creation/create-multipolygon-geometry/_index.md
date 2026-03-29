---
date: 2026-03-29
description: Aspose.GIS for .NET kullanarak çoklu çokgen (multipolygon) geometrisi
  oluşturmayı ve çoklu çokgene çokgen eklemeyi öğrenin. Ücretsiz deneme sürümüyle
  adım adım rehber.
linktitle: Create MultiPolygon Geometry
second_title: Aspose.GIS .NET API
title: Aspose.GIS ile MultiPolygon Geometrisi Nasıl Oluşturulur
url: /tr/net/geometry-creation/create-multipolygon-geometry/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS ile MultiPolygon Geometrisi Nasıl Oluşturulur

## Giriş
Eğer bir .NET ortamında **multipolygon nasıl oluşturulur** şeklinde şekiller arıyorsanız, doğru yere geldiniz. Aspose.GIS for .NET, karmaşık coğrafi nesneler oluşturmak için temiz, nesne‑yönelimli bir API sunar ve bu öğretici, kütüphaneyi kurmaktan bireysel poligonları tek bir MultiPolygon içinde birleştirmeye kadar her adımı size gösterir. Sonunda, **poligonları multipolygon yapılarına ekleme** konusunda kendinize güvenerek çalışabileceksiniz.

## Hızlı Yanıtlar
- **MultiPolygon nedir?** İki veya daha fazla Polygon nesnesini tek bir koleksiyonda birleştiren bir geometri.  
- **Neden Aspose.GIS kullanmalı?** Birçok GIS formatını destekler, .NET Framework ve .NET Core üzerinde çalışır ve harici yerel kütüphanelere ihtiyaç duymaz.  
- **Örnek ne kadar sürer?** Yazmak ve çalıştırmak yaklaşık 5 dakika.  
- **Lisans gerekir mi?** Geliştirme için ücretsiz deneme sürümü yeterlidir; üretim için ticari lisans gereklidir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## MultiPolygon Geometrisi Nedir?
MultiPolygon, birden çok Polygon nesnesini içeren birleşik bir geometri olup, her biri kendi iç halkalarına (deliklere) sahip olabilir. Bu yapı, ayrı ayrı arazi parçalarını, adaları veya ortak bir niteliği paylaşan ayrı alan kümelerini temsil etmek için idealdir.

## Neden Poligonları MultiPolygon'a Ekleyelim?
Poligonları bir MultiPolygon içine eklemek, birkaç bağımsız şekli tek bir varlık olarak ele almanızı sağlar. Bu, uzamsal sorguları, görselleştirmeyi ve veri alışverişini basitleştirir; çünkü tüm koleksiyonu tek bir nesneyle depolayabilir, aktarabilir ve manipüle edebilirsiniz, her bir poligonu ayrı ayrı yönetmek zorunda kalmazsınız.

## Önkoşullar
Kodlamaya başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- **Aspose.GIS for .NET** yüklü (aşağıdaki adımlara bakın).  
- .NET geliştirme ortamı (Visual Studio, VS Code veya tercih ettiğiniz herhangi bir IDE).  
- C# sözdizimine temel aşinalık.

### Aspose.GIS for .NET'i Kurma
1. Aspose.GIS'i indirin: Geliştirme ortamınıza uygun sürümü seçmek için [indirme sayfasına](https://releases.aspose.com/gis/net/) gidin.  
2. Aspose.GIS'i kurun: Belgelerdeki kurulum talimatlarını izleyerek Aspose.GIS for .NET'i makinenize kurun.

## Ad Alanlarını İçe Aktarma
Aspose.GIS ile .NET projenizde çalışmaya başlamak için gerekli ad alanlarını içe aktarın:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Adım 1: Linear Ring'ler Oluşturma
İlk olarak, her poligon için **LinearRing** nesneleri oluşturmamız gerekiyor. LinearRing, bir poligonun dış sınırını (ve isteğe bağlı olarak iç delikleri) tanımlayan kapalı bir çizgi dizesidir.

```csharp
LinearRing firstRing = new LinearRing();
firstRing.AddPoint(8.5, -2.5);
firstRing.AddPoint(-8.5, 2.5);
firstRing.AddPoint(8.5, -2.5);
LinearRing secondRing = new LinearRing();
secondRing.AddPoint(7.6, -3.6);
secondRing.AddPoint(-9.6, 1.5);
secondRing.AddPoint(7.6, -3.6);
```

## Adım 2: Poligonlar Oluşturma
Sonra, her LinearRing'i bir **Polygon** nesnesine dönüştürüyoruz. Bu poligonlar daha sonra MultiPolygon'a eklenecek.

```csharp
Polygon firstPolygon = new Polygon(firstRing);
Polygon secondPolygon = new Polygon(secondRing);
```

## Adım 3: MultiPolygon Oluşturma
Şimdi, poligonları tek bir **MultiPolygon** geometrisine birleştirelim. İşte **poligonları multipolygon'a eklediğimiz** yer.

```csharp
MultiPolygon multiPolygon = new MultiPolygon();
multiPolygon.Add(firstPolygon);
multiPolygon.Add(secondPolygon);
```

Tebrikler! Aspose.GIS for .NET kullanarak bir MultiPolygon geometrisi başarıyla oluşturdunuz.

## Yaygın Sorunlar ve Çözümler
| Sorun | Neden | Çözüm |
|-------|-------|-----|
| **Halkalar kapanmıyor** | İlk ve son noktalar farklı. | İlk ve son koordinatların aynı olduğundan emin olun; Aspose.GIS otomatik olarak halkayı kapatır, ancak açıkça kapatmak karışıklığı önler. |
| **Yanlış koordinat sırası (X, Y vs. Lon, Lat)** | Boylam ve enlemi karıştırmak. | (X, Y) sırasına sadık kalın; X = boylam, Y = enlem. |
| **Çalışma zamanında kütüphane bulunamadı** | Eksik NuGet referansı veya DLL. | Aspose.GIS paketinin proje dosyanızda referans alındığını ve DLL'in çıktı klasörüne kopyalandığını doğrulayın. |

## Sıkça Sorulan Sorular

**S: Aspose.GIS for .NET yeni başlayanlar için uygun mu?**  
C: Kesinlikle! Aspose.GIS, tüm beceri seviyelerindeki geliştiricilerin başlamasına yardımcı olacak kapsamlı belgeler ve öğreticiler sunar.

**S: Aspose.GIS'i satın almadan önce deneyebilir miyim?**  
C: Evet, satın almadan önce özelliklerini keşfetmek için [buradan](https://releases.aspose.com/) ücretsiz deneme sürümünü indirebilirsiniz.

**S: Aspose.GIS için desteği nereden bulabilirim?**  
C: Aspose.GIS forumunu [buradan](https://forum.aspose.com/c/gis/33) ziyaret ederek sorular sorabilir ve topluluktan yardım alabilirsiniz.

**S: Aspose.GIS için geçici bir lisans mevcut mu?**  
C: Evet, değerlendirme amaçlı geçici lisansı [buradan](https://purchase.aspose.com/temporary-license/) alabilirsiniz.

**S: Aspose.GIS'i doğrudan satın alabilir miyim?**  
C: Evet, Aspose.GIS'i web sitesinden [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

---

**Son Güncelleme:** 2026-03-29  
**Test Edilen Versiyon:** Aspose.GIS 24.12 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}