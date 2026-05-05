---
date: 2026-01-18
description: Aspose.GIS for .NET kullanarak haritaya şehir eklemeyi ve SVG harita
  oluşturmayı öğrenin. Çarpıcı görselleştirmeleri hızlıca oluşturun.
linktitle: Render a Map
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET ile Haritaya Şehir Ekleme
url: /tr/net/map-rendering/render-a-map/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET ile Haritaya Şehir Nasıl Eklenir

## Giriş
Aspose.GIS for .NET’in heyecan verici dünyasına hoş geldiniz! Bu adım‑adım kılavuzda **haritaya şehir eklemeyi** ve yüksek kaliteli bir SVG çıktısı üretmeyi öğreneceksiniz. İster bir masaüstü kontrol paneli ister web tabanlı bir GIS portalı oluşturuyor olun, bu öğretici size vektör katmanları çizmeyi, harita boyutlarını ayarlamayı ve bir GeoJSON haritasını sorunsuz bir şekilde yüklemeyi gösterir.

## Hızlı Yanıtlar
- **Bu öğretici neyi kapsıyor?** Haritaya şehir eklemek ve bunu bir SVG dosyası olarak dışa aktarmak.  
- **Hangi kütüphane gerekiyor?** Aspose.GIS for .NET.  
- **Lisans gerekli mi?** Ücretsiz bir deneme sürümü mevcuttur; üretim ortamı için lisans gereklidir.  
- **Web uygulamalarında kullanabilir miyim?** Evet – aynı kod ASP.NET, Blazor ve diğer .NET web çerçevelerinde çalışır.  
- **Hangi çıktı formatı üretiliyor?** Tarayıcılarda görüntülenebilen veya daha sonra düzenlenebilen bir SVG harita.

## Ön Koşullar
Bu öğreticiye başlamadan önce aşağıdaki ön koşulların sağlandığından emin olun:
- Aspose.GIS for .NET Kütüphanesi: Aspose.GIS for .NET kütüphanesinin yüklü olduğundan emin olun. **[buradan](https://releases.aspose.com/gis/net/)** indirebilirsiniz.  
- Veri Dosyaları: Öğretici için gerekli shapefile ve GeoJSON verilerini hazırlayın. Örnek verileri belgelerde bulabilir veya kendi dosyalarınızı kullanabilirsiniz.  
- Geliştirme Ortamı: Visual Studio gibi bir kod editörü içeren .NET geliştirme ortamınızın kurulu olduğundan emin olun.

## Namespace'leri İçe Aktarın
Başlamak için gerekli namespace'leri .NET projenize ekleyin. Bu namespace'ler Aspose.GIS işlevselliğiyle çalışmak için gereklidir.

```csharp
using Aspose.Gis;
using Aspose.Gis.Rendering;
using Aspose.Gis.Rendering.Symbolizers;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.Drawing.Text;
using System.IO;
using System.Linq;
```

## Adım 1: Haritayı Kur (harita boyutlarını ayarla)
```csharp
string dataDir = "Your Document Directory";
using (var map = new Map(800, 476))
{
    // Additional code for map setup can be added here.
}
```
Bu adımda, genişliği 800 piksel ve yüksekliği 476 piksel olan yeni bir harita başlatıyoruz. Tasarım gereksinimlerinize göre boyutları ayarlayabilirsiniz.

## Adım 2: Temel Harita Ekle (vektör katmanı çiz)
```csharp
var baseMapSymbolizer = new SimpleFill { FillColor = Color.Salmon, StrokeWidth = 0.75 };
map.Add(VectorLayer.Open(dataDir + "basemap.shp", Drivers.Shapefile), baseMapSymbolizer);
```
Burada, shapefile kullanarak temel harita için **bir vektör katmanı çizeriz**. Görsel stilinize uyması için `SimpleFill` özelliklerini istediğiniz gibi değiştirebilirsiniz.

## Adım 3: Haritaya Şehirleri Ekle (şehirleri haritaya ekle, GeoJSON haritasını yükle)
```csharp
var citiesSymbolizer = new SimpleMarker() { FillColor = Color.LightBlue };
citiesSymbolizer.FeatureBasedConfiguration = (feature, symbolizer) =>
{
    // Additional configuration logic can be added here.
};
map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), citiesSymbolizer);
```
Bu adım, şehir nokta verilerini içeren bir GeoJSON dosyasını yükler ve **şehirleri haritaya ekler**. `FeatureBasedConfiguration` temsilcisini, nüfus gibi özniteliklere göre şehirleri biçimlendirecek şekilde geliştirebilirsiniz.

## Adım 4: Haritayı Oluştur (haritayı SVG olarak dışa aktar, SVG harita oluştur)
```csharp
map.Render(dataDir + "cities_out.svg", Renderers.Svg);
```
Son olarak, **haritayı bir SVG dosyası olarak dışa aktarırız**. Oluşan `cities_out.svg` dosyası, modern bir tarayıcıda açılabilir veya bir vektör‑grafik editöründe düzenlenebilir.

## Sonuç
Tebrikler! Aspose.GIS for .NET kullanarak **haritaya şehir eklemeyi** ve bir SVG harita üretmeyi başarıyla tamamladınız. Bu öğreticide harita boyutlarını ayarlamayı, vektör katmanları çizmeyi, GeoJSON verilerini yüklemeyi ve sonucu ölçeklenebilir bir SVG olarak dışa aktarmayı gösterdik—hem web hem de baskı senaryoları için mükemmel.

## SSS
### Aspose.GIS for .NET'i web uygulamalarımda kullanabilir miyim?
Evet, Aspose.GIS for .NET hem masaüstü hem de web uygulamaları için uygundur.

### Deneme sürümü mevcut mu?
Evet, ücretsiz deneme sürümünü **[buradan](https://releases.aspose.com/)** keşfedebilirsiniz.

### Aspose.GIS for .NET için destek nereden alınabilir?
Herhangi bir yardım veya soru için **[Aspose.GIS forumunu](https://forum.aspose.com/c/gis/33)** ziyaret edin.

### Kısa vadeli projeler için geçici lisans satın alabilir miyim?
Evet, geçici lisans **[buradan](https://purchase.aspose.com/temporary-license/)** temin edilebilir.

### Aspose.GIS for .NET için ek öğreticiler var mı?
Evet, kapsamlı öğreticiler ve kılavuzlar için **[belgelere](https://reference.aspose.com/gis/net/)** göz atın.

---

**Son Güncelleme:** 2026-01-18  
**Test Edilen Sürüm:** Aspose.GIS 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}