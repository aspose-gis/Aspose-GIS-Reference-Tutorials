---
date: 2025-12-12
description: Aspose.GIS for .NET kullanarak vektör katmanı oluşturmayı ve dairesel
  dize geometrisi eklemeyi öğrenin – GIS uygulamaları oluşturmanın hızlı bir yolu.
linktitle: Create Circular String Geometry
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET'te Vektör Katmanı ve Dairesel Dize Oluştur
url: /tr/net/geometry-creation/create-circular-string-geometry/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET ile Vektör Katmanı ve Dairesel Dize Geometrisi Oluşturma

## Giriş
Eğer .NET platformunda bir GIS uygulaması geliştiriyorsanız, genellikle ilk adım **vektör katmanı oluşturmak** nesneleridir ve uzamsal özelliklerinizi depolar. Aspose.GIS for .NET bu süreci basitleştirir ve bu katmanları dairesel dize gibi gelişmiş geometrilerle zenginleştirmenizi sağlar. Bu öğreticide, bir vektör katmanı nasıl oluşturulur, dairesel dize geometrisi nasıl eklenir ve sonucun Shapefile olarak nasıl kaydedileceği tam olarak öğrenilecek—hepsi temiz, üretim‑hazır C# kodu ile.

## Hızlı Yanıtlar
- **“create vector layer” ne anlama geliyor?** Yeni bir konteyner (katman) oluşturur ve nokta, çizgi veya çokgen gibi uzamsal özellikleri tutabilir.  
- **Hangi sınıf dairesel dizeyi temsil eder?** `CircularString` sınıfı `Aspose.Gis.Geometries` içinde.  
- **Katmanı Shapefile olarak kaydedebilir miyim?** Evet – katmanı oluştururken `Drivers.Shapefile` kullanın.  
- **Geliştirme için lisansa ihtiyacım var mı?** Değerlendirme için geçici bir lisans yeterlidir; üretim için tam lisans gereklidir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## “create vector layer” nedir?
Vektör katmanı, tek bir veri kaynağında saklanan vektör özelliklerinin (nokta, çizgi, çokgen) mantıksal bir gruplamasıdır. Aspose.GIS'te bir katmanı `VectorLayer.Create` çağırarak, hedef dosya yolunu ve istenen sürücüyü (ör. Shapefile) belirterek örnekleyebilirsiniz. Katman oluşturulduktan sonra özellik ekleyebilir, geometriler atayabilir ve uzamsal işlemler gerçekleştirebilirsiniz.

## Neden dairesel dize ekleyelim?
Dairesel dizeler, **lineer geometri** tipinin bir çeşididir ve bir dizi nokta kullanarak yayları yaklaşık olarak temsil eder. Eğri yollar, nehir kıvrımları veya çok sayıda küçük çizgi segmentine ihtiyaç duymadan pürüzsüz bir eğri gerektiren herhangi bir özellik için kullanışlıdır.

## Önkoşullar
- **.NET Framework veya .NET Core** makinenizde kurulu olmalıdır.  
- **Aspose.GIS for .NET** kütüphanesi – resmi siteden **[buradan](https://releases.aspose.com/gis/net/)** indirin.  
- **Visual Studio** veya **JetBrains Rider** gibi bir IDE.  
- **C#** programlamaya temel aşinalık.

## Ad Alanlarını İçe Aktarın
Gerekli ad alanlarını C# dosyanıza ekleyin:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Adım‑Adım Kılavuz

### Adım 1: Çıktı dosya yolunu tanımlayın
Shapefile'in yazılacağı konumu ayarlayın.

```csharp
string path = "Your Document Directory" + "CreateCircularString_out.shp";
```

`"Your Document Directory"` ifadesini sisteminizdeki gerçek klasör yolu ile değiştirin.

### Adım 2: **Vektör katmanı oluştur**
`Create` metodunu kullanarak bir `VectorLayer` açın. Bu, **vektör katmanı oluşturma** işleminin çekirdeğidir.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
```

### Adım 3: Yeni bir özellik oluşturun
Bir özellik, katman içindeki tek bir uzamsal kaydı temsil eder.

```csharp
    var feature = layer.ConstructFeature();
```

### Adım 4: Dairesel dize geometrisini oluşturun
Eğri şekli tanımlayan noktaları ekleyin. Nokta dizisi, aynı konumda başlayıp biten bir yay oluşturur ve kapalı bir dairesel dize meydana getirir.

```csharp
    var circularString = new CircularString();
    circularString.AddPoint(0, 0);
    circularString.AddPoint(1, 1);
    circularString.AddPoint(2, 0);
    circularString.AddPoint(1, -1);
    circularString.AddPoint(0, 0);
```

### Adım 5: Geometriyi atayın ve özelliği katmana ekleyin
Geometriyi özelliğe bağlayın ve katmanda depolayın.

```csharp
    feature.Geometry = circularString;
    layer.Add(feature);
}
```

`using` bloğu sona erdiğinde, katman otomatik olarak diskteki Shapefile'e yazılır.

## Yaygın Sorunlar ve Çözümler
| Sorun | Çözüm |
|-------|----------|
| **Dosya yolu geçersiz** | Dizin mevcut olduğundan ve yazma izniniz olduğundan emin olun. |
| **CircularString düz bir çizgi olarak görünüyor** | Noktaların doğru sırayla eklendiğini doğrulayın; kapalı bir şekil için ilk ve son noktalar aynı olmalıdır. |
| **Lisans istisnası** | Geliştirme sırasında geçici bir lisans uygulayın veya üretim için tam lisans satın alın. |

## Sıkça Sorulan Sorular

### Aspose.GIS for .NET tüm .NET Framework sürümleriyle uyumlu mu?
Evet, Aspose.GIS for .NET, Framework 4.5'ten en yeni .NET 8 sürümlerine kadar geniş bir .NET sürüm yelpazesinde çalışacak şekilde tasarlanmıştır.

### Aspose.GIS for .NET'i diğer GIS kütüphaneleriyle entegre edebilir miyim?
Kesin Diğer kütüphanelerle verileri okuyabilir, Aspose.GIS ile işleyebilir ve ardından geri yazabilirsiniz; esnek API'si sayesinde.

### Aspose.GIS for .NET uzamsal veri görselleştirmeyi destekliyor mu?
Evet, kütüphane, geometrilerinizi haritalar ve görsel temsiller olarak oluşturmanızı sağlayan render araçları içerir.

### Aspose.GIS for .NET ile ilgili yardım alabileceğim bir topluluk forumu var mı?
Evet, sorular sorup deneyimlerinizi paylaşabileceğiniz Aspose.GIS forumunu **[buradan](https://forum.aspose.com/c/gis/33)** ziyaret edebilirsiniz.

### Aspose.GIS for .NET'i değerlendirmek için geçici bir lisans alabilir miyim?
Elbette! Geçici bir değerlendirme lisansı **[buradan](https://purchase.aspose.com/temporary-license/)** temin edilebilir.

### Aynı katmana daha karmaşık geometriler (ör. MultiLineString) nasıl eklenir?
Uygun geometri nesnesini (ör. `MultiLineString`) oluşturun, onu bireysel `LineString` nesneleriyle doldurun, `feature.Geometry`'ye atayın ve dairesel dizeyle yaptığımız gibi özelliği ekleyin.

## Sonuç
Bu adımları izleyerek artık Aspose.GIS for .NET kullanarak **vektör katmanı** nesnelerini nasıl oluşturacağınızı ve bunları dairesel dize geometrisiyle nasıl zenginleştireceğinizi biliyorsunuz. Bu temel, ulaşım ağlarını haritalamaktan çevresel verileri görselleştirmeye, özel uzamsal analiz araçları geliştirmeye kadar daha zengin GIS çözümleri oluşturmanızı sağlar.

---

**Son Güncelleme:** 2025-12-12  
**Test Edilen Sürüm:** Aspose.GIS 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}