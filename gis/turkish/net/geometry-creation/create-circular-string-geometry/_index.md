---
date: 2026-02-15
description: Aspose.GIS for .NET kullanarak vektör katmanı oluşturmayı ve dairesel
  çizgi geometrisi eklemeyi öğrenin – GIS uygulamaları oluşturmanın hızlı bir yolu.
linktitle: Create Circular String Geometry
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET'te Vektör Katmanı ve Dairesel Dize Oluşturma
url: /tr/net/geometry-creation/create-circular-string-geometry/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET ile Vektör Katmanı ve Dairesel Dize Geometrisi Oluşturma

## Giriş
.NET platformunda bir GIS uygulaması geliştiriyorsanız, ilk adım genellikle **vektör katmanı oluşturmak** için uzamsal özelliklerinizi depolayan nesneler yaratmaktır. Aspose.GIS for .NET bu süreci basitleştirir ve bu katmanları dairesel dize gibi gelişmiş geometrilerle zenginleştirmenizi sağlar. Bu öğreticide tam olarak **vektör katmanı oluşturmayı**, **dairesel dize** geometrisini eklemeyi ve sonucu bir Shapefile olarak kaydetmeyi öğreneceksiniz — temiz, üretim‑hazır C# kodu ile.

## Hızlı Yanıtlar
- **“create vector layer” ne anlama geliyor?** Yeni bir konteyner (katman) oluşturur ve bu konteyner nokta, çizgi veya çokgen gibi uzamsal özellikleri tutabilir.  
- **Hangi sınıf dairesel dizeyi temsil eder?** `CircularString` from `Aspose.Gis.Geometries`.  
- **Katmanı Shapefile olarak kaydedebilir miyim?** Evet – katmanı oluştururken `Drivers.Shapefile` kullanın.  
- **Geliştirme için lisansa ihtiyacım var mı?** Değerlendirme için geçici bir lisans yeterlidir; üretim için tam lisans gereklidir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## “create vector layer” nedir?
Bir vektör katmanı, tek bir veri kaynağında saklanan vektör özelliklerinin (nokta, çizgi, çokgen) mantıksal bir gruplamasıdır. Aspose.GIS'te bir katmanı `VectorLayer.Create` çağırarak, hedef dosya yolu ve istenen sürücü (ör. Shapefile) belirterek örnekleyebilirsiniz. Katman oluşturulduktan sonra özellik ekleyebilir, geometriler atayabilir ve uzamsal işlemler gerçekleştirebilirsiniz.

## Neden dairesel dize ekleyelim?
Dairesel dizeler, bir dizi nokta kullanarak yayları yaklaşık olarak temsil eden bir **linear geometry** (doğrusal geometri) türüdür. Eğri yollar, nehir kıvrımları veya çok sayıda küçük çizgi segmentine başvurmadan pürüzsüz bir eğri gerektiren herhangi bir özelliği temsil etmek için kullanışlıdır.

## Önkoşullar
- **.NET Framework veya .NET Core** makinenizde yüklü olmalıdır.  
- **Aspose.GIS for .NET** kütüphanesi – resmi siteden **[buradan](https://releases.aspose.com/gis/net/)** indirebilirsiniz.  
- **Visual Studio** veya **JetBrains Rider** gibi bir IDE.  
- **C#** programlamaya temel aşinalık.

## Ad Alanlarını İçe Aktarma
C# dosyanıza gerekli ad alanlarını ekleyin:

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
Shapefile'ın yazılacağı konumu ayarlayın.

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

### Adım 3: Yeni bir özellik oluştur
Bir özellik, katman içinde tek bir uzamsal kaydı temsil eder.

```csharp
    var feature = layer.ConstructFeature();
```

### Adım 4: Dairesel dize geometrisini oluştur
Eğri şekli tanımlayan noktaları ekleyin. Nokta dizisi, aynı konumda başlayan ve biten bir yay oluşturur ve kapalı bir dairesel dize meydana getirir.

```csharp
    var circularString = new CircularString();
    circularString.AddPoint(0, 0);
    circularString.AddPoint(1, 1);
    circularString.AddPoint(2, 0);
    circularString.AddPoint(1, -1);
    circularString.AddPoint(0, 0);
```

### Adım 5: Geometriyi atayın ve özelliği katmana ekleyin
Geometriyi özelliğe bağlayın ve katmanda saklayın.

```csharp
    feature.Geometry = circularString;
    layer.Add(feature);
}
```

`using` bloğu sona erdiğinde, katman otomatik olarak diskteki Shapefile'a yazılır.

## Yaygın Sorunlar ve Çözümler
| Sorun | Çözüm |
|-------|----------|
| **Dosya yolu geçersiz** | Dizinin mevcut olduğundan ve yazma izinlerinizin olduğundan emin olun. |
| **CircularString düz bir çizgi olarak görünüyor** | Noktaların doğru sırayla eklendiğini doğrulayın; kapalı bir şekil için ilk ve son noktalar aynı olmalıdır. |
| **Lisans istisnası** | Geliştirme sırasında geçici bir lisans uygulayın veya üretim kullanımı için tam lisans satın alın. |

## Sıkça Sorulan Sorular

### Aspose.GIS for .NET tüm .NET Framework sürümleriyle uyumlu mu?
**Evet**, Aspose.GIS for .NET geniş bir .NET sürüm yelpazesiyle çalışacak şekilde tasarlanmıştır; Framework 4.5'ten en yeni .NET 8 sürümlerine kadar.

### Aspose.GIS for .NET'i diğer GIS kütüphaneleriyle entegre edebilir miyim?
**Kesinlikle!** Diğer kütüphanelerle veri okuyabilir, Aspose.GIS ile işleyebilir ve ardından tekrar yazabilirsiniz; esnek API sayesinde.

### Aspose.GIS for .NET uzamsal veri görselleştirmeyi destekliyor mu?
**Evet**, kütüphane haritalar ve geometrilerinizin görsel temsillerini oluşturmanıza olanak tanıyan render araçları içerir.

### Aspose.GIS for .NET ile ilgili yardım alabileceğim bir topluluk forumu var mı?
**Evet**, sorular sorabilir ve deneyimlerinizi paylaşabilirsiniz; forum **[burada](https://forum.aspose.com/c/gis/33)** bulunmaktadır.

### Aspose.GIS for .NET'i değerlendirmek için geçici bir lisans alabilir miyim?
**Elbette!** Geçici bir değerlendirme lisansı **[buradan](https://purchase.aspose.com/temporary-license/)** temin edilebilir.

### Aynı katmana daha karmaşık geometriler (ör. MultiLineString) nasıl eklenir?
Uygun geometri nesnesini (ör. `MultiLineString`) oluşturun, bireysel `LineString` nesneleriyle doldurun, `feature.Geometry`'ye atayın ve dairesel dizeyle yaptığımız gibi özelliği ekleyin.

## SSS (Hızlı‑Referans)

**S:** **vektör katmanı oluştur** programmatically nasıl yapılır?  
**C:** `VectorLayer.Create(path, Drivers.Shapefile)` (veya başka bir sürücü) `using` bloğu içinde çağırın.

**S:** Dairesel dizeye nokta ekleyen yöntem nedir?  
**C:** Her koordinat için `circularString.AddPoint(x, y)` kullanın.

**S:** Aynı katmanda birden fazla geometri depolayabilir miyim?  
**C:** Evet, her geometri için yeni bir özellik oluşturup `layer.Add(feature)` ile ekleyin.

**S:** Shapefile oluşturulmazsa ne yapmalıyım?  
**C:** Çıktı dizininin var olduğunu, yazma izinlerinizin olduğunu ve sürücünün (`Drivers.Shapefile`) doğru referanslandığını doğrulayın.

**S:** Değerlendirme sürümü için lisans gerekli mi?  
**C:** Geliştirme ve test için geçici bir lisans yeterlidir; üretim dağıtımları için tam lisans gerekir.

## Sonuç
Bu adımları izleyerek artık Aspose.GIS for .NET kullanarak **vektör katmanı oluştur** nesnelerini nasıl oluşturacağınızı ve **dairesel dize** geometrisiyle nasıl zenginleştireceğinizi biliyorsunuz. Bu temel, ulaşım ağlarını haritalamaktan çevresel verileri görselleştirmeye, özel uzamsal analiz araçları geliştirmeye kadar daha zengin GIS çözümleri oluşturmanızı sağlar.

---

**Son Güncelleme:** 2026-02-15  
**Test Edilen Versiyon:** Aspose.GIS 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}