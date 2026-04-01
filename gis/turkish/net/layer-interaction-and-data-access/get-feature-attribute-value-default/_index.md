---
date: 2026-01-05
description: Aspose.GIS for .NET'te öznitelik değerlerini nasıl alacağınızı ve varsayılanları
  nasıl ayarlayacağınızı öğrenin. Bu adım adım kılavuz, GeoJSON katmanları oluşturmayı
  ve GIS özellikleri oluşturmayı gösterir.
linktitle: How to Get Attribute Value (Default)
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET ile Öznitelik Değerini (Varsayılan) Nasıl Alabilirsiniz
url: /tr/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspise.GIS for .NET ile Öznitelik Değerini (Varsayılan) Alma

## Giriş
Bu kapsamlı öğreticide, Aspose.GIS for .NET kullanarak bir GIS özelliğinden **öznitelik değerlerini nasıl alacağınızı** keşfedecek ve bir öznitelik eksik olduğunda varsayılan değerlerle nasıl çalışılacağını öğreneceksiniz. Uzamsal analiz motoru ya da basit bir harita görüntüleyici geliştiriyor olun, öznitelik alımını ve varsayılanların yönetimini ustalıkla yapmak güvenilir GIS uygulamaları için hayati öneme sahiptir.

## Hızlı Yanıtlar
- **Birincil yöntem nedir?** `Feature.GetValueOrDefault<T>()`  
- **Özel bir varsayılan ayarlayabilir miyim?** Evet, varsayılan değeri kabul eden aşırı yükleme yoluyla veya öznitelikte `DefaultValue` tanımlayarak.  
- **Geliştirme için lisansa ihtiyacım var mı?** Test için ücretsiz deneme sürümü çalışır; üretim için ticari lisans gereklidir.  
- **Desteklenen geometri formatları?** GeoJSON, Shapefile, GML ve Aspose.GIS sürücüleri aracılığıyla birçok başka format.  
- **.NET Core/.NET 6+ ile çalışır mı?** Kesinlikle – kütüphane çapraz platformdur.

## Önkoşullar
İlerlemeye başlamadan önce şunların olduğundan emin olun:

- C# ve .NET ekosistemi hakkında temel bilgi.  
- Aspose.GIS for .NET yüklü. Henüz yüklemediyseniz, [buradan](https://releases.aspose.com/gis/net/) indirin.  
- Visual Studio veya Visual Studio Code gibi bir kod düzenleyici.

## Ad Alanlarını İçe Aktarma
API türlerinin kullanılabilir olması için C# dosyanıza gerekli `using` ifadelerini ekleyin:

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Şimdi her örneği adım adım inceleyelim.

## Öznitelik Değerini (Varsayılan) Alma
### Adım 1: Ortamı Hazırlama
Test belgelerinizin bulunduğu klasörün yolunu tanımlayın:

```csharp
string dataDir = "Your Document Directory";
```

### Adım 2: GeoJSON Katmanı Oluşturma
**geojson katmanı oluşturacağız** — null veya ayarlanmamış olabilecek bir öznitelik tanımladığımız ilk yer:

```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```

### Adım 3: GIS Özelliği Oluşturma
**GIS özelliği oluşturacağız** — bu, az önce tanımladığımız öznitelik şemasına uyan yeni bir özellik örneği sağlar:

```csharp
    Feature feature = layer.ConstructFeature();
```

### Adım 4: Değerleri Almak
Son olarak, varsayılanların nasıl çalıştığını gösteren çeşitli senaryolarla **özellik özniteliği** değerlerini alıyoruz:

```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // value == null
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // value == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // value == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```

## Varsayılan Değerleri Ayarlama
### Adım 1: Başka Bir GeoJSON Katmanı Oluşturma
Bu sefer **öznitelik varsayılanını** doğrudan şemada ayarlayacağız:

```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```

### Adım 2: GIS Özelliği (Tekrar) Oluşturma
```csharp
    Feature feature = layer.ConstructFeature();
```

### Adım 3: Değerleri Al ve Ayarla
Varsayılanı alıyoruz, ardından çalışma zamanında **varsayılanı nasıl ayarlayacağınızı** görmek için değiştiriyoruz:

```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); // value == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); // value == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); // value == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```

## Yaygın Tuzaklar ve İpuçları
- **`using` bloğunu kapatmayı asla unutmayın.** Katman otomatik olarak yok edilir ve dosya tutamaçları serbest bırakılır.  
- **`CanBeNull` false olduğunda, `GetValueOrDefault` her zaman bir değer döndürür** (saklanan ya da tanımlı varsayılan).  
- **Genel aşırı yüklemeyi kullanın** (`GetValueOrDefault<T>`) değer tipleri için kutulama/kutudan çıkarma işlemlerinden kaçınmak için.  
- **Pro ipucu:** Bir özniteliğin gerçekten ayarlanıp ayarlanmadığını kontrol etmeniz gerekiyorsa, `GetValueOrDefault` çağırmadan önce `feature.IsAttributeSet("attribute")` kullanın.

## Sıkça Sorulan Sorular
### Aspose.GIS .NET Core ile uyumlu mu?
Evet, Aspose.GIS .NET Core ile tamamen uyumludur, çapraz‑platform desteği sağlar.

### Aspose.GIS'i ticari projelerde kullanabilir miyim?
Kesinlikle! Aspose.GIS, ticari uygulamalarınızda herhangi bir kısıtlama olmadan kullanmanıza izin veren bir ticari lisansa sahiptir.

### Ek destek ve kaynakları nereden bulabilirim?
Topluluk desteği için [Aspose.GIS forumuna](https://forum.aspose.com/c/gis/33) gidin ve ayrıntılı bilgi için [belgelere](https://reference.aspose.com/gis/net/) göz atın.

### Ücretsiz deneme sürümü mevcut mu?
Evet, Aspose.GIS'i ücretsiz deneme sürümüyle keşfedebilirsiniz. [buradan](https://releases.aspose.com/) indirin.

### Test amaçlı geçici lisans nasıl alabilirim?
Geçici lisanslar için [buraya](https://purchase.aspose.com/temporary-license/) bakın.

## Ek SSS
**S: `GetValueOrDefault` metodunu var olmayan bir öznitelik üzerinde çağırırsam ne olur?**  
C: Metod bir `ArgumentException` fırlatır. Her zaman öznitelik adını doğrulayın veya önce `feature.HasAttribute("name")` kullanın.

**S: Katman oluşturulduktan sonra varsayılan değeri değiştirebilir miyim?**  
C: Evet, `attribute.DefaultValue`'ı değiştirebilir ve ardından değişikliği kalıcı kılmak için `layer.UpdateAttribute(attribute)` çağırabilirsiniz.

**S: Aspose.GIS öznitelik değerlerinin toplu güncellemelerini destekliyor mu?**  
C: Bir özellik koleksiyonunu döngüyle gezebilir ve her özellikte `SetValue` çağırabilirsiniz; büyük veri setleri için daha iyi performans sağlamak amacıyla `FeatureCursor` API'sini kullanmayı düşünün.

## Sonuç
Bu rehberde **öznitelik değerlerini nasıl alacağınızı**, varsayılanları nasıl tanımlayıp geçersiz kılacağınızı ve uygulama ihtiyaçlarınıza uygun **GeoJSON katmanı** şemalarını nasıl **oluşturacağınızı** ele aldık. Bu tekniklerle eksik veya isteğe bağlı verileri sorunsuz bir şekilde yöneten sağlam GIS çözümleri oluşturabilirsiniz.

---

**Last Updated:** 2026-01-05  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}