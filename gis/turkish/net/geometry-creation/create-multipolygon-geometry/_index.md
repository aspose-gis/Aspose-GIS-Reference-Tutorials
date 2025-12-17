---
date: 2025-12-17
description: Aspose.GIS for .NET kullanarak ASP.NET'te çokgen geometri oluşturmayı
  öğrenin. Adım adım rehber, ücretsiz deneme ve lisans bilgileri.
linktitle: Create MultiPolygon Geometry
second_title: Aspose.GIS .NET API
title: Aspose.GIS ile ASP.NET'te multipolygon geometrisi nasıl oluşturulur
url: /tr/net/geometry-creation/create-multipolygon-geometry/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS ile MultiPolygon Geometrisi Oluşturma

## Giriş
Eğer **asp.net'te multipolygon geometry oluşturmak** istiyorsanız, Aspose.GIS for .NET size herhangi bir .NET platformunda çalışan temiz, tip‑güvenli bir API sunar. Bu öğreticide, kütüphaneyi kurmaktan MultiPolygon nesnesi oluşturup Shapefile, GeoJSON veya desteklenen diğer formatlara dışa aktarmaya kadar tüm süreci adım adım göstereceğiz. İster bir haritalama web servisi ister masaüstü GIS aracı geliştirin, bu iş akışını öğrenmek zaman kazandırır ve hataları azaltır.

## Hızlı Yanıtlar
- **Bununla ne inşa edebilirim?** Arazi‑kullanım haritaları veya teslimat bölgeleri gibi karmaşık çokgen bölgeleri gerektiren herhangi bir GIS uygulaması.  
- **Lisans gerekli mi?** Geliştirme için ücretsiz deneme sürümü yeterlidir; üretim için kalıcı bir lisans gerekir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Kod yazma süresi ne kadar?** Temel bir MultiPolygon için yaklaşık 5‑10 dakika.  
- **Sonucu dışa aktarabilir miyim?** Evet—yerleşik `Save` metodlarını kullanarak Shapefile, GeoJSON vb. formatlara yazabilirsiniz.

## MultiPolygon Geometrisi Nedir?
Bir **MultiPolygon**, birbirinden ayrı veya delik içerebilen bireysel çokgenlerin bir koleksiyonudur. GIS terminolojisinde aynı niteliği paylaşan ancak geometrik olarak ayrı olan mekânsal özelliklerin bir setini temsil eder—örneğin adalardan oluşan ülkeler veya birden fazla parçaya sahip arsalar için mükemmeldir.

## Neden Aspose.GIS for .NET Kullanmalı?
- **Tam özellikli API** – Harici yerel bağımlılık yok, tamamen yönetilen kod.  
- **Çapraz platform** – Windows, Linux ve macOS'ta çalışır.  
- **Zengin format desteği** – Çıktı kutusundan doğrudan onlarca vektör formatını okur/yazar.  
- **Performans odaklı** – Büyük veri setlerini düşük bellek tüketimiyle işler.

## Ön Koşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. **Visual Studio 2022** (veya herhangi bir C# IDE) ve .NET 6 SDK yüklü.  
2. **Aspose.GIS for .NET** paketi – [indirme sayfasından](https://releases.aspose.com/gis/net/) indirin ve belgelerdeki kurulum rehberini izleyin.

## Ad Alanlarını İçe Aktarma
GIS tiplerinin nerede bulunduğunu derleyicinin bilmesi için projenize gerekli `using` yönergelerini ekleyin:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Adım 1: Linear Ring'ler Oluşturma
Bir **LinearRing**, bir çokgenin dış veya iç sınırını tanımlayan kapalı bir `LineString`'dir. Burada iki basit halka oluşturacağız:

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

> **İpucu:** Halka kapatmak için ilk ve son noktalar aynı olmalıdır; Aspose.GIS son noktayı atlamanız durumunda otomatik olarak kapatır, ancak açıkça belirtmek karışıklığı önler.

## Adım 2: Çokgenler Oluşturma
Her `Polygon`, bir `LinearRing`'den oluşturulur. Gerektiğinde daha sonra iç halkalar (delikler) ekleyebilirsiniz.

```csharp
Polygon firstPolygon = new Polygon(firstRing);
Polygon secondPolygon = new Polygon(secondRing);
```

## Adım 3: MultiPolygon Oluşturma
Şimdi iki çokgeni tek bir `MultiPolygon` nesnesinde birleştiriyoruz—bu, **asp.net'te multipolygon geometry oluşturmak** için tam olarak gereken adımdır.

```csharp
MultiPolygon multiPolygon = new MultiPolygon();
multiPolygon.Add(firstPolygon);
multiPolygon.Add(secondPolygon);
```

Artık manipüle edebileceğiniz, sorgulayabileceğiniz veya serileştirebileceğiniz tam işlevsel bir `MultiPolygon`'a sahipsiniz.

## Yaygın Sorunlar & Çözümler
| Sorun | Neden | Çözüm |
|-------|-------|-------|
| **Halka kapalı değil** | İlk noktanın kopyası eksik | İlk ve son noktaların aynı olduğundan emin olun veya `LinearRing.Close()` metodunu açıkça çağırın. |
| **Koordinat sırası hatalı** | Enlem/boylam yer değiştirmiş | Aspose.GIS **X = boylam**, **Y = enlem** bekler. Veri kaynağınızı kontrol edin. |
| **`Add` sırasında istisna** | Null bir çokgen ekleniyor | `MultiPolygon`'a eklemeden önce her `Polygon` örneğinin oluşturulduğunu doğrulayın. |

## Sonuç
Bu adımları izleyerek Aspose.GIS for .NET kullanarak **asp.net'te multipolygon geometry oluşturmayı** öğrendiniz. Bu temel, daha zengin mekânsal modeller inşa etmenizi, mekânsal sorgular yapmanızı ve verileri desteklenen herhangi bir GIS formatına dışa aktarmanızı sağlar. Sonraki adımda `Contains`, `Intersects` veya `Transform` gibi metodları keşfederek uygulamanıza analitik güç katabilirsiniz.

## SSS
### Aspose.GIS for .NET yeni başlayanlar için uygun mu?
Kesinlikle! Aspose.GIS, her seviyeden geliştiricinin hızlıca başlayabilmesi için kapsamlı dokümantasyon ve öğreticiler sunar.

### Aspose.GIS'i satın almadan denemek mümkün mü?
Evet, özelliklerini keşfetmek için [buradan](https://releases.aspose.com/) ücretsiz deneme sürümünü indirebilirsiniz.

### Aspose.GIS için destek nereden alınır?
Topluluk sorularını sorup yardım alabileceğiniz Aspose.GIS forumuna [buradan](https://forum.aspose.com/c/gis/33) ulaşabilirsiniz.

### Aspose.GIS için geçici bir lisans mevcut mu?
Evet, değerlendirme amaçlı geçici lisansı [buradan](https://purchase.aspose.com/temporary-license/) temin edebilirsiniz.

### Aspose.GIS doğrudan satın alınabilir mi?
Evet, Aspose.GIS'i web sitesinden [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

## Sıkça Sorulan Sorular
**S: MultiPolygon'ı bir dosyaya nasıl kaydederim?**  
C: `Feature` sınıfını kullanarak geometriyi paketleyin ve `feature.Save("output.shp", Drivers.Shapefile);` metodunu çağırın.

**S: Bir çokgene iç halkalar (delikler) ekleyebilir miyim?**  
C: Evet—ikinci bir `LinearRing` oluşturup `Polygon` yapıcısının ikinci parametresi olarak geçirin.

**S: Koordinatları başka bir mekânsal referansa dönüştürmek mümkün mü?**  
C: Kesinlikle. `multiPolygon.Transform(sourceCRS, targetCRS);` metodunu çağırın; CRS nesneleri EPSG kodlarıyla tanımlanır.

---

**Son Güncelleme:** 2025-12-17  
**Test Edilen Versiyon:** Aspose.GIS 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}