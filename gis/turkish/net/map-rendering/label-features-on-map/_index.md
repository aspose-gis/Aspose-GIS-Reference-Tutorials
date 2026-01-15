---
date: 2026-01-15
description: Aspose.GIS for .NET kullanarak harita öğelerini nasıl etiketleyeceğinizi
  öğrenin; büyük veri seti etiketlemesi için özelleştirilebilir etiket stil seçenekleriyle.
linktitle: Label Features on Map
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET ile Harita Özelliklerini Etiketleyin
url: /tr/net/map-rendering/label-features-on-map/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET ile Harita Özelliklerine Etiketleme

## Giriş
Harita özelliklerine etiket eklemek, ham coğrafi verileri net, kullanıcı dostu görselleştirmelere dönüştürmek için esastır. Bu öğreticide Aspose.GIS for .NET kullanarak **harita özelliklerine nasıl etiket ekleneceğini** (ana anahtar kelime) keşfedecek, özel etiket stillerini inceleyecek ve büyük veri setleriyle bile çalışan teknikleri göreceksiniz. Sonunda haritalarınıza doğrudan bilgilendirici metin ekleyebilecek ve bunları analistler ile son kullanıcılar için daha anlamlı hâle getirebileceksiniz.

## Hızlı Yanıtlar
- **Renderleme için ana sınıf nedir?** `Map` (Aspose.Gis.Rendering)
- **Basit metin ekleyen etiketleme sınıfı hangisidir?** `SimpleLabeling`
- **Etiketleri (halo, yazı tipi, dönüş) biçimlendirebilir miyim?** Evet – `HaloSize`, `FontStyle` ve `Placement` gibi özellikler aracılığıyla
- **Büyük veri setleri nasıl yönetilir?** Etiketleri öznitelik değerlerine göre önceliklendirmek için `FeatureBasedConfiguration` kullanın
- **Lisans gerekli mi?** Geliştirme için deneme sürümü çalışır; üretim için ticari lisans gerekir

## Harita Özelliklerine Etiket Nedir?
`label map features` (harita özelliklerine etiket) okunabilir metin (şehir isimleri, nüfus rakamları veya özel tanımlayıcılar gibi) geometrik nesnelere—noktalara, çizgilere veya çokgenlere—eklemeyi ifade eder; böylece harita bir bakışta hem mekânsal hem de öznitelik bilgilerini iletir.

## Harita Özelliklerine Etiket İçin Neden Aspose.GIS Kullanmalı?
- **Sıfır dış bağımlılık** – saf .NET kütüphanesi, yerel GIS ikili dosyaları gerekmez.  
- **Zengin stil seçenekleri** – halo, özel yazı tipleri, dönüş ve ankraj noktaları görünümü ince ayarlamanıza olanak tanır.  
- **Performans odaklı** – yerleşik özellik‑tabanlı etiketleme, büyük veri setlerini render ederken en önemli etiketleri önceliklendirmenizi sağlar.  
- **Çoklu çıktı formatları** – SVG, PNG, PDF vb., tutarlı etiketleme sonuçlarıyla.  

## Ön Koşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- C# ve .NET çerçevesi hakkında temel bilgi.  
- Aspose.GIS for .NET yüklü. **[buradan](https://releases.aspose.com/gis/net/)** indirebilirsiniz.  
- Nokta verisi içeren bir GeoJSON dosyası (veya desteklenen herhangi bir vektör formatı).  

## Ad Alanlarını İçe Aktarma
C# kodunuzda gerekli ad alanlarını içe aktarın:

```csharp
using System;
using System.Drawing;
using Aspose.Gis;
using Aspose.Gis.Rendering;
using Aspose.Gis.Rendering.Labelings;
using Aspose.Gis.Rendering.Symbolizers;
using Aspose.GIS.Examples.CSharp;
using FontStyle = Aspose.Gis.Rendering.Labelings.FontStyle;
```

Şimdi, önceki örnek üzerine inşa edilen birkaç etiketleme senaryosunu adım adım inceleyeceğiz.

## Nokta Etiketleme – Noktaları Nasıl Etiketlersiniz
### Adım 1: Belgeler dizininizin yolunu ayarlayın
```csharp
string dataDir = "Your Document Directory";
```

### Adım 2: Basit bir işaretçi sembolü ile harita oluşturun
```csharp
using (var map = new Map(500, 200))
{
    var symbol = new SimpleMarker
    {
        FillColor = Color.LightGray,
        StrokeStyle = StrokeStyle.None
    };
    var labeling = new SimpleLabeling(labelAttribute: "name");
    // 3. Add a vector layer and apply labeling
    map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), symbol, labeling);
    map.Padding = 50;
    // 4. Render the map to an SVG file
    map.Render(dataDir + "points_labeling_out.svg", Renderers.Svg);
}
```

Bu temel örnekte, GeoJSON dosyasındaki `name` özniteliğini kullanarak **noktalara nasıl etiket ekleneceğini** gösteriyoruz.

## Nokta Etiketleme Stilize – Özel Etiket Stili
Önceki örnekten adım 1 ve 2'yi izleyin, ardından etiketleme stilini özelleştirin:

```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 2,
    HaloColor = Color.LightGray,
    FontSize = 15,
    FontStyle = FontStyle.Italic,
};
// Rest of the steps remain the same
```

Eklenen halo ve italik yazı tipi, etiketlere yoğun arka planlarda bile öne çıkan bir **özel etiket stili** kazandırır.

## Nokta Etiketleme Yerleşim – Gelişmiş Yerleştirme Seçenekleri
Yine ilk örnekten adım 1 ve 2'yi başlatın, ardından yerleşimi ayarlayın:

```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 1,
    Placement = new PointLabelPlacement
    {
        VerticalAnchorPoint = VerticalAnchor.Bottom,
        HorizontalAnchorPoint = HorizontalAnchor.Left,
        HorizontalOffset = 2,
        VerticalOffset = 2,
        Rotation = 10,
    }
};
// Rest of the steps remain the same
```

Burada ankraj noktalarını, ofsetleri ve dönüşü kontrol ederek, kalabalık harita bölgelerinde **noktalara nasıl etiket ekleneceği** konusunda ayrıntılı kontrol sağlıyorsunuz.

## Nokta Etiketleme Özellik‑Tabanlı – Büyük Veri Seti Etiketleme
Birçok nokta ile çalışırken, nüfus gibi bir özniteliğe göre etiketleri önceliklendirmek isteyebilirsiniz. İlk örnekten adım 1 ve 2'yi izleyin, ardından özellik‑tabanlı etiketlemeyi uygulayın:

```csharp
var pointLabeling = new SimpleLabeling("name")
{
    HaloSize = 1,
    Placement = new PointLabelPlacement
    {
        VerticalAnchorPoint = VerticalAnchor.Bottom,
        HorizontalAnchorPoint = HorizontalAnchor.Left,
        VerticalOffset = 4,
        HorizontalOffset = 4,
    },
    FeatureBasedConfiguration = (feature, labeling) =>
    {
        // Retrieve population from the feature.
        var population = feature.GetValue<int>("population");
        // Font size is computed and is based on the population.
        labeling.FontSize = Math.Min(20, 5 * population / 1000);
        // Priority of the label is also based on the population.
        // The greater the priority is, the more likely label will appear on the output image.
        labeling.Priority = population;
    }
};
// Rest of the steps remain the same
```

Bu **büyük veri seti etiketleme** stratejisi, en önemli şehirlerin (nüfusa göre) önce gösterilmesini sağlar; sınırlı alan olduğunda daha az kritik noktalar atlanabilir.

## Sonuç
Tebrikler! Artık Aspose.GIS for .NET ile **harita özelliklerine etiket eklemenin** birden fazla yolunu biliyorsunuz—basit nokta etiketlemeden büyük veri setleri için gelişmiş, özellik‑tabanlı stilize etmeye kadar. Halo, dönüş ve öncelik kurallarıyla deneyler yaparak izleyicinizin görmesi gerekenleri tam olarak ileten haritalar oluşturabilirsiniz.

## Sıkça Sorulan Sorular

**Q: Özellikleri özel yazı tipleriyle etiketleyebilir miyim?**  
A: Evet. `SimpleLabeling` yapılandırmasında `FontFamily` ve `FontStyle` ayarlarını yaparak yüklü herhangi bir yazı tipini kullanabilirsiniz.

**Q: Aspose.GIS diğer GIS veri formatlarıyla uyumlu mu?**  
A: Kesinlikle. GeoJSON, Shapefile, KML, GML ve daha birçok formatı destekler.

**Q: Etiketleme için büyük veri setlerini nasıl yönetebilirim?**  
A: `FeatureBasedConfiguration` kullanarak öncelikler atayın ve öznitelik değerlerine göre yazı tipi boyutlarını dinamik olarak ayarlayın; bu, özellik‑tabanlı örnekte gösterildiği gibi.

**Q: Gelişmiş etiket yerleştirme seçenekleri mevcut mu?**  
A: Evet. `PointLabelPlacement` ile ankraj noktalarını, ofsetleri ve dönüşü ayarlayarak yerleşimi ince ayarlayabilirsiniz.

**Q: Etiket oluşturmayı toplu bir işlemde otomatikleştirebilir miyim?**  
A: Kesinlikle. Harita render kodunu bir döngüye veya arka plan servisine sararak birden fazla katmanı veya dosyayı otomatik olarak işleyebilirsiniz.

---

**Son Güncelleme:** 2026-01-15  
**Test Edilen Versiyon:** Aspose.GIS 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}