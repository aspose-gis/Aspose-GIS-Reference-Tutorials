---
date: 2026-04-09
description: Aspose.GIS for .NET kullanarak çokgeni çizgiye nasıl dönüştüreceğinizi
  ve çokgenleri çizgilere nasıl aktaracağınızı öğrenin. GIS geliştiricileri için hızlı
  bir rehber.
keywords:
- convert polygon to line
- how to replace polygons
- transform polygons to lines
linktitle: Poligonları Çizgilerle Değiştir
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET ile Çokgeni Çizgiye Dönüştür
url: /tr/net/geometry-processing/replace-polygons-with-lines/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Poligonları Çizgiye Dönüştürme Aspose.GIS for .NET

## Giriş
Bir .NET GIS projesinde **poligonları çizgiye dönüştür**meniz gerekiyorsa, Aspose.GIS süreci basitleştirir. Harita görselleştirmelerini sadeleştiriyor, yönlendirme algoritmaları için verileri hazırlıyor ya da sadece daha temiz bir geometri temsiline ihtiyacınız varsa, bu öğretici Aspose.GIS API'sını kullanarak poligonları çizgi geometrileriyle değiştirme adımlarını size gösterecek.

## Hızlı Yanıtlar
- **“Poligonları çizgiye dönüştür” ne anlama geliyor?** Kapalı poligon şekillerini sınır çizgi dizilerine dönüştürür.  
- **Neden bu görev için Aspose.GIS kullanmalı?** Tek bir yöntem (`ReplacePolygonsByLines`) sunar; bu yöntem dönüşümü manuel geometri ayrıştırması yapmadan verimli bir şekilde gerçekleştirir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+ ve .NET 5/6+.  
- **Geliştirme için lisansa ihtiyacım var mı?** Test için ücretsiz deneme sürümü çalışır; üretim için ticari lisans gereklidir.  
- **Uygulama ne kadar sürer?** Temel bir dönüşüm için genellikle 10 dakikadan az sürer.

## “Poligonları çizgiye dönüştür” nedir?
Poligonları çizgiye dönüştürmek, poligonun dış halkasını (çevresini) çıkarıp bunu bir `LineString` olarak temsil etmek anlamına gelir. Ortaya çıkan geometri şeklin dış hatlarını korur ancak iç alan bilgisini kaybeder; bu, ağ analizi veya kenar renderleme gibi görevler için faydalıdır.

## Neden Aspose.GIS ile poligonları çizgilere dönüştürmeliyiz?
- **Görselleştirmeleri sadeleştir:** Çizgiler, özellikle web haritalarında, render edilmesi daha hafiftir.  
- **Yönlendirme için veriyi hazırla:** Birçok yönlendirme motoru çizgi geometrileri gerektirir.  
- **Topolojiyi koru:** Çizgi, orijinal poligonun tam sınırını korur ve mekânsal doğruluğu sağlar.  
- **Tek satır çözüm:** `ReplacePolygonsByLines()` yöntemi tüm ağır işi sizin için yapar.

## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

### Aspose.GIS for .NET'i Kurma
1. Aspose.GIS for .NET'i indirin: En son sürümü indirmek için [bu linki](https://releases.aspose.com/gis/net/) ziyaret edin.  
2. Aspose.GIS for .NET'i kurun: Paketteki kurulum talimatlarını izleyin veya ayrıntılı adımlar için [belgelere](https://reference.aspose.com/gis/net/) bakın.

## Ad Alanlarını İçe Aktarma
.NET projenizde, Aspose.GIS sınıflarıyla çalışabilmek için gerekli ad alanlarını içe aktarın.

```csharp
using System;
using Aspose.Gis.Geometries;
```

## Adım‑Adım Kılavuz

### Adım 1: Kaynak geometrisini tanımla
Dönüştürmek istediğiniz bir veya daha fazla poligonu içeren bir geometri koleksiyonu oluşturun. Bu örnekte, poligon olmayan öğelerin değişmeden kaldığını göstermek için bir nokta da ekliyoruz.

```csharp
var srcGeometry = Geometry.FromText(@"GeometryCollection (POLYGON((1 2, 1 4, 3 4, 3 2)), Point (5 1))");
```

### Adım 2: Poligonları çizgilere dönüştür
`ReplacePolygonsByLines()` yöntemini çağırın. Bu tek çağrı koleksiyonu tarar, her poligonu karşılık gelen çizgi temsiliyle değiştirir ve diğer geometri tiplerini dokunulmaz bırakır.

```csharp
var dstGeometry = srcGeometry.ReplacePolygonsByLines();
```

### Adım 3: Orijinal ve dönüştürülmüş geometrileri göster
Dönüşümü doğrulamak için orijinal ve dönüştürülmüş geometrileri konsola yazdırın.

```csharp
Console.WriteLine($"source: {srcGeometry.AsText()}");
Console.WriteLine($"result: {dstGeometry.AsText()}");
```

## Yaygın Sorunlar ve Çözümler
- **Eksik çizgi çıktısı:** Kaynak geometrinin gerçekten poligon içerdiğinden emin olun; noktalar veya çoklu noktalar değişmeden geçirilir.  
- **Koordinat sırası sorunları:** Aspose.GIS koordinatları `X Y` (boylam enlem) sırasında bekler. Değerlerin yer değiştirmesi beklenmedik şekillere neden olabilir.  
- **Büyük koleksiyonlar:** Çok büyük veri setleri için, yüksek bellek tüketimini önlemek amacıyla geometrileri partiler halinde işlemeyi düşünün.

## Sıkça Sorulan Sorular

**S:** Aspose.GIS for .NET çeşitli GIS dosya formatlarıyla çalışabilir mi?  
**C:** Evet, Shapefile, GeoJSON, KML ve birçok diğer yaygın GIS formatını destekler.

**S:** Aspose.GIS for .NET için ücretsiz deneme sürümü mevcut mu?  
**C:** Evet, Aspose.GIS for .NET'in ücretsiz deneme sürümüne [buradan](https://releases.aspose.com/) erişebilirsiniz.

**S:** Aspose.GIS for .NET geliştiricilere destek sunuyor mu?  
**C:** Evet, geliştiriciler Aspose.GIS topluluk forumundan [burada](https://forum.aspose.com/c/gis/33) destek ve yardım alabilirler.

**S:** Aspose.GIS for .NET için geçici bir lisans satın alabilir miyim?  
**C:** Evet, [buradan](https://purchase.aspose.com/temporary-license/) geçici bir lisans edinebilirsiniz.

**S:** Aspose.GIS for .NET hem yeni başlayanlar hem de deneyimli geliştiriciler için uygun mu?  
**C:** Kesinlikle, tüm beceri seviyeleri için kapsamlı belgeler, kod örnekleri ve API referansları sunar.

## Sonuç
Bu adımları izleyerek Aspose.GIS for .NET kullanarak **poligonları çizgiye dönüştürmeyi** ve etkili bir şekilde **poligonları çizgilere dönüştürmeyi** öğrendiniz. Bu yetenek, daha hafif görselleştirmeler, yönlendirme hazırlıkları ve birçok diğer GIS iş akışının kapısını açar. Uygulamanızın yeteneklerini genişletmek için mekânsal sorgular, yeniden projeksiyon ve format dönüşümü gibi ek Aspose.GIS özelliklerini keşfetmekten çekinmeyin.

---

**Last Updated:** 2026-04-09  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}