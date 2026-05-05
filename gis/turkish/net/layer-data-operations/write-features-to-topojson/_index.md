---
date: 2026-05-05
description: Aspose.GIS for .NET kullanarak TopoJSON oluşturmayı öğrenin. Özellikleri
  TopoJSON formatına yazmak için adım adım kılavuz.
keywords:
- create topojson aspose
- Aspose.GIS TopoJSON
- .NET GIS tutorial
linktitle: Özellikleri TopoJSON'e Yaz
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET ile TopoJSON Nasıl Oluşturulur
url: /tr/net/layer-data-operations/write-features-to-topojson/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET ile TopoJSON Nasıl Oluşturulur

## Giriş
Eğer .NET uygulamanızdan doğrudan **TopoJSON oluşturma** dosyaları oluşturmanız gerekiyorsa, Aspose.GIS bunu yapmak için temiz ve verimli bir API sağlar. Bu öğreticide, ortamı kurmaktan özellikleri TopoJSON belgesine yazmaya, öznitelik ve geometri eklemeye kadar tüm süreci adım adım inceleyeceğiz. Sonunda, TopoJSON üretimini oluşturduğunuz herhangi bir GIS çözümüne entegre edebileceksiniz.

## Hızlı Yanıtlar
- **Bu öğretici neyi kapsıyor?** Aspose.GIS for .NET kullanarak bir TopoJSON dosyasına vektör özellikleri yazma.  
- **Bu ne kadar sürer?** Yaklaşık 10‑15 dakika temel bir uygulama için.  
- **Lisans gerekir mi?** Geliştirme için ücretsiz deneme çalışır; üretim için ticari lisans gereklidir.  
- **Desteklenen .NET sürümleri?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Özel öznitelikler ekleyebilir miyim?** Evet – geometri eklemeden önce istediğiniz sayıda özellik özniteliği tanımlayabilirsiniz.

## TopoJSON Nedir ve Neden Aspose.GIS Kullanmalı?
TopoJSON, topolojiyi kodlayan bir GeoJSON uzantısıdır ve daha küçük dosya boyutları ile ortak çizgi segmentleri sağlar. Aspose.GIS ile **TopoJSON oluşturma**, programatik kontrol, yüksek performans ve .NET ekosistemindeki diğer GIS iş akışlarıyla sorunsuz entegrasyon sunar.

## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.GIS for .NET yüklü. Belgeleri bulabilir ve kütüphaneyi [buradan](https://reference.aspose.com/gis/net/) indirebilirsiniz.  
- Bir .NET geliştirme ortamı (Visual Studio, VS Code veya tercih ettiğiniz herhangi bir IDE).  
- Çıktı dosyasının kaydedileceği makinenizde bir klasör – kod örneklerinde buna `Your Document Directory` diye referans vereceğiz.

## Ad Alanlarını İçe Aktarın
İlk olarak, GIS sınıflarıyla çalışabilmek için gerekli ad alanlarını ekleyin.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Adım Adım Kılavuz

### Adım 1: Belge Dizini Ayarla
Oluşturulan TopoJSON dosyasının saklanacağı klasörü tanımlayın.

```csharp
string dataDir = "Your Document Directory";
```

`"Your Document Directory"` ifadesini sisteminizdeki gerçek yol ile değiştirin.

### Adım 2: Çıktı Yolunu Belirleyin
Dizini istediğiniz dosya adıyla birleştirin.

```csharp
var outputPath = dataDir + "sample_out.topojson";
```

### Adım 3: TopoJSON Sürücüsü ile VectorLayer Oluşturun
`VectorLayer` sınıfını TopoJSON sürücüsüyle örnekleyin. Bu katman, eklediğiniz tüm özellikler için bir kapsayıcı görevi görecektir.

```csharp
using (VectorLayer layer = VectorLayer.Create(outputPath, Drivers.TopoJson))
```

### Adım 4: Katmana Öznitelikler Ekle
Geometrileri eklemeden önce, öznitelik şemasını tanımlayın. Bu öznitelikler her özellik ile birlikte saklanacaktır.

```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("measurement", AttributeDataType.Double));
layer.Attributes.Add(new FeatureAttribute("id", AttributeDataType.Integer));
```

### Adım 5: Katmana Özellikler Ekle
Bireysel özellikler oluşturun, öznitelik değerlerini ayarlayın, bir geometri atayın ve katmana ekleyin.

```csharp
var feature0 = layer.ConstructFeature();
feature0.SetValue("name", "name_0");
feature0.SetValue("measurement", 1.03);
feature0.SetValue("id", 0);
feature0.Geometry = new Point(1.3, 2.3);
layer.Add(feature0);
var feature1 = layer.ConstructFeature();
feature1.SetValue("name", "name_1");
feature1.SetValue("measurement", 10.03);
feature1.SetValue("id", 1);
feature1.Geometry = new Point(241.32, 23.2);
layer.Add(feature1);
```

`using` bloğu sona erdiğinde, Aspose.GIS verileri otomatik olarak `sample_out.topojson` dosyasına yazar.

## Yaygın Tuzaklar ve İpuçları
- **Yol ayırıcıları:** Çapraz platform uyumluluğu gerekiyorsa `Path.Combine` kullanın.  
- **Öznitelik tipleri:** Belirttiğiniz veri tipinin atadığınız değerle eşleştiğinden emin olun; eşleşmezse çalışma zamanı istisnası fırlatılır.  
- **Büyük veri setleri:** Binlerce özellik için, toplu eklemeyi düşünün veya performansı artırmak için `layer.BeginTransaction()` / `Commit()` kullanın.

## Sonuç
Artık Aspose.GIS for .NET ile **TopoJSON oluşturma** dosyalarını nasıl oluşturacağınızı, katmanı kurmaktan özel öznitelikler ve nokta geometrileriyle doldurmaya kadar öğrendiniz. Bu temel, GIS uygulamanız büyüdükçe daha karmaşık geometrilere (çizgiler, çokgenler) ve daha büyük veri setlerine genişlemenizi sağlar.

## Sıkça Sorulan Sorular
**Q: Aspose.GIS for .NET'i diğer GIS kütüphaneleriyle kullanabilir miyim?**  
A: Aspose.GIS bağımsız çalışır, ancak GeoJSON, Shapefile veya KML gibi ortak formatları okuyarak veya yazarak diğer kütüphanelerle veri alışverişi yapabilirsiniz.

**Q: Aspose.GIS için lisans seçenekleri var mı?**  
A: Evet, lisans seçeneklerini inceleyebilir ve satın alımlarınızı [buradan](https://purchase.aspose.com/buy) yapabilirsiniz.

**Q: Aspose.GIS for .NET için ücretsiz deneme mevcut mu?**  
A: Kesinlikle! Ücretsiz denemeye [buradan](https://releases.aspose.com/) erişebilirsiniz.

**Q: Destek alabileceğim veya Aspose.GIS topluluğuyla bağlantı kurabileceğim yer neresi?**  
A: Topluluk desteği ve tartışmalar için [Aspose.GIS forumuna](https://forum.aspose.com/c/gis/33) gidin.

**Q: Aspose.GIS için geçici bir lisans nasıl alabilirim?**  
A: Geçici lisansı [buradan](https://purchase.aspose.com/temporary-license/) edinebilirsiniz.

---

**Son Güncelleme:** 2026-05-05  
**Test Edilen:** Aspose.GIS for .NET (May 2026 itibarıyla en son sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}