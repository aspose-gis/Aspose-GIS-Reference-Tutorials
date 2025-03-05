---
title: Aspose.GIS for .NET ile Özellik Etiketlemede Uzmanlaşma
linktitle: Haritadaki Etiket Özellikleri
second_title: Aspose.GIS .NET API'si
description: Aspose.GIS for .NET'i keşfedin ve haritalarda özellik etiketleme sanatında ustalaşın. Jeo-uzaysal görselleştirmelerinizi zahmetsizce geliştirin. #Aspose #GIS
type: docs
weight: 11
url: /tr/net/map-rendering/label-features-on-map/
---
## giriiş
Jeo-uzamsal veri görselleştirme dünyasında, harita üzerindeki özelliklerin etiketlenmesi, bilginin etkili bir şekilde iletilmesinde çok önemli bir rol oynar. Aspose.GIS for .NET, bunu sorunsuz bir şekilde gerçekleştirmek için güçlü bir araç seti sağlar. Bu derste, Aspose.GIS kullanarak bir haritadaki noktaları etiketlemenin çeşitli yöntemlerini inceleyeceğiz ve harita görselleştirmelerinizi bilgilendirici etiketlerle zenginleştireceğiz.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
- C# ve .NET çerçevesi hakkında çalışma bilgisi.
-  Aspose.GIS for .NET kuruldu. İndirebilirsin[Burada](https://releases.aspose.com/gis/net/).
- Nokta verilerini içeren bir GeoJSON dosyası. Eğer elinizde yoksa test için örnek bir dosya kullanabilirsiniz.
## Ad Alanlarını İçe Aktar
Aspose.GIS ile çalışmak için C# kodunuzda gerekli ad alanlarını içe aktardığınızdan emin olun:
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
Şimdi, adım adım kılavuz formatında her örneği birden çok adıma ayıralım.
##  Puan Etiketleme

### Adım 1: Belgeler dizininizin yolunu ayarlayın:
```csharp
string dataDir = "Your Document Directory";
```
### Adım 2: Basit bir işaretçi sembolüyle bir harita oluşturun:
```csharp
using (var map = new Map(500, 200))
{
    var symbol = new SimpleMarker
    {
        FillColor = Color.LightGray,
        StrokeStyle = StrokeStyle.None
    };
    var labeling = new SimpleLabeling(labelAttribute: "name");
    // 3. Bir vektör katmanı ekleyin ve etiketlemeyi uygulayın
    map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), symbol, labeling);
    map.Padding = 50;
    // 4. Haritayı bir SVG dosyasına dönüştürün
    map.Render(dataDir + "points_labeling_out.svg", Renderers.Svg);
}
```
## Puan Etiketleme Stili

Önceki örnekteki 1. ve 2. adımları izleyin.

### 1. Adım: Etiketleme stilini özelleştirin:
```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 2,
    HaloColor = Color.LightGray,
    FontSize = 15,
    FontStyle = FontStyle.Italic,
};
// Adımların geri kalanı aynı kalıyor
```
## Nokta Etiketlemesi Yerleştirildi

İlk örnekteki 1. ve 2. adımları izleyin.
### 2. Adım: Etiket yerleşimini özelleştirin:
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
// Adımların geri kalanı aynı kalıyor
```
## Nokta Etiketleme Özelliğine Dayalı

İlk örnekteki 1. ve 2. adımları izleyin.

### 1. Adım: Özellik tabanlı etiketlemeyi uygulayın:
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
        // Özellikten popülasyonu alın.
        var population = feature.GetValue<int>("population");
        // Yazı tipi boyutu hesaplanır ve popülasyona dayalıdır.
        labeling.FontSize = Math.Min(20, 5 * population / 1000);
        // Etiketin önceliği de popülasyona bağlıdır.
        // Öncelik ne kadar büyükse, çıktı görüntüsünde etiketin görünme olasılığı da o kadar yüksektir.
        labeling.Priority = population;
    }
};
// Adımların geri kalanı aynı kalıyor
```
## Çözüm
Tebrikler! Aspose.GIS for .NET kullanarak özellikleri etiketleyerek harita görselleştirmelerinizi nasıl geliştireceğinizi öğrendiniz. Verilerinize göre uyarlanmış ilgi çekici haritalar oluşturmak için farklı stiller ve yerleşimlerle denemeler yapın.
## SSS
### Özel yazı tiplerini kullanarak özellikleri etiketleyebilir miyim?
Evet, etiketleme yapılandırmasında yazı tipi stilini ve boyutunu özelleştirebilirsiniz.
### Aspose.GIS diğer GIS veri formatlarıyla uyumlu mu?
Aspose.GIS, GeoJSON, Shapefile ve daha fazlası dahil olmak üzere çeşitli coğrafi formatları destekler.
### Etiketleme için büyük veri kümelerini nasıl işleyebilirim?
Aspose.GIS performans için optimize edilmiştir ancak veri özelliklerine göre etiketlere öncelik vermek için özellik bazlı konfigürasyonlar kullanmayı düşünün.
### Gelişmiş etiket yerleştirme seçenekleri mevcut mu?
Evet, döndürme, bağlantı noktaları ve uzaklıklar gibi seçenekleri kullanarak etiket yerleşiminde ince ayar yapabilirsiniz.
### Toplu işlemde etiket oluşturmayı otomatikleştirebilir miyim?
Toplu etiket üretimi için Aspose.GIS'i kesinlikle otomatik iş akışlarınıza entegre edebilirsiniz.