---
date: 2026-08-30
description: Aspose.GIS for .NET kullanarak haritaya etiket ekleme ve SLD içe aktarma.
  Bu adım adım kılavuz, Styled Layer Descriptor dosyalarını nasıl içe aktaracağınızı,
  dinamik etiketler eklemenizi ve yüksek kaliteli rasterler oluşturmanızı gösterir.
keywords:
- how to label map
- how to import sld
- Aspose.GIS .NET
- map rendering .NET
- GIS styling
lastmod: 2026-08-30
linktitle: Haritaya etiket ekleme ve SLD içe aktarma
og_description: Aspose.GIS for .NET kullanarak haritaya etiket eklemek hızlı ve esnektir.
  SLD dosyalarını içe aktarın, katmanları stilize edin ve dakikalar içinde yüksek
  kaliteli rasterler oluşturun.
og_image_alt: 'Aspose.GIS tutorial: label map and import SLD in .NET'
og_title: Aspose.GIS for .NET ile haritaya etiket ekleme ve SLD içe aktarma
schemas:
- author: Aspose
  dateModified: '2026-08-30'
  description: How to label map and import SLD using Aspose.GIS for .NET. This step‑by‑step
    guide shows you how to import Styled Layer Descriptor files, add dynamic labels,
    and render high‑quality rasters.
  headline: How to label map and import SLD with Aspose.GIS for .NET
  type: TechArticle
- description: How to label map and import SLD using Aspose.GIS for .NET. This step‑by‑step
    guide shows you how to import Styled Layer Descriptor files, add dynamic labels,
    and render high‑quality rasters.
  name: How to label map and import SLD with Aspose.GIS for .NET
  steps:
  - name: '**Create the map instance.**'
    text: '**Create the map instance.**'
  - name: '**Add your vector data source.**'
    text: '**Add your vector data source.**'
  - name: '**Import the SLD file.**'
    text: '**Import the SLD file.**'
  - name: '**Render or further customize.**'
    text: '**Render or further customize.**'
  type: HowTo
- questions:
  - answer: Yes. Load each SLD separately and assign it to the appropriate layer via
      the `Layer.Style` property.
    question: Can I combine multiple SLD files for different layers?
  - answer: Absolutely. Reference TrueType fonts in your SLD or define symbols programmatically
      with `Symbol.Font = new Font("CustomFont", 12)`.
    question: Does Aspose.GIS support custom symbol fonts?
  - answer: Set `RenderOptions.BackgroundColor = Color.Transparent` before calling
      `Render`.
    question: How do I render a map without a background (transparent PNG)?
  - answer: You can retrieve the `Style` object from a layer, modify its rules, and
      re‑apply it without re‑loading the XML file.
    question: Is it possible to edit an SLD after importing it?
  - answer: Raster size is limited by available memory; for images larger than 10
      000 × 10 000 px, use tiling (`RenderOptions.TileSize`) to stream the output.
    question: What limits are there on the size of the raster output?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- label map
- import sld
- Aspose.GIS
- map rendering
- C# GIS
title: Aspose.GIS for .NET ile haritaya etiket ekleme ve SLD içe aktarma
url: /tr/net/map-rendering/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Harita Etiketleme ve SLD'yi Aspose.GIS for .NET ile İçe Aktarma

## Giriş
Bu öğreticide Aspose.GIS for .NET kullanarak **harita etiketleme** ve Styled Layer Descriptor (SLD) dosyalarını nasıl içe aktaracağınızı keşfedeceksiniz. Konum‑tabanlı bir hizmet, özel bir portal veya veri keşif aracı geliştiriyor olsanız da, bu adımları öğrenmek harita stilizasyonu, etiketleme ve raster çıktısı üzerinde tam kontrol sağlar ve kodunuzu temiz ve sürdürülebilir tutar.

## Hızlı Yanıtlar
- **SLD nedir?** Styled Layer Descriptor (SLD), harita katmanları için görsel stil kurallarını tanımlayan OGC‑standardı XML formatıdır.  
- **Neden Aspose.GIS for .NET?** Saf‑yönetilen bir API sunar, 50+ vektör ve raster formatını destekler ve yerel kütüphanelere ihtiyaç duymaz.  
- **Lisans gerekli mi?** Geliştirme için ücretsiz deneme sürümü çalışır; üretim dağıtımları için ticari lisans gereklidir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **SLD içe aktarımını özel etiketleme ile birleştirebilir miyim?** Evet – bir SLD içe aktarın, ardından etiket kurallarını programlı olarak ekleyin veya geçersiz kılın.

## “SLD nasıl içe aktarılır” nedir?
Styled Layer Descriptor (SLD), bir GIS motoruna bir katmandaki her özelliği nasıl çizeceğini söyleyen OGC‑standardı bir XML dosyasıdır.  
Bir SLD'yi içe aktarmak, bu kuralları bir `Map` nesnesine yükler, böylece görsel görünüm tanıma uyar ve renkler ya da semboller kod içinde sabitlenmez.

## SLD Nasıl İçe Aktarılır
Bir SLD'yi içe aktarmak için stil dosyasını yüklersiniz ve uygun harita katmanına bağlarsınız. Aspose.GIS XML'i ayrıştırır, stil nesneleri oluşturur ve aynı adı paylaşan katmanlarla otomatik olarak eşleştirir, böylece çizim kodu yazmadan vektör verilerini stilize edebilirsiniz. Ayrıntılı bir rehber için [Explore Import SLD Tutorial](./import-styled-layer-descriptor/) adresine bakın.

**Doğrudan cevap:** `Map.LoadStyle("./myStyle.sld")` (veya `layer.Style = Style.FromFile("myStyle.sld")`) kullanarak tanımlayıcıyı anında uygulayın – manuel kural oluşturma gerekmez. Bu tek satırlık işlem XML'i ayrıştırır, iç stil nesnelerini oluşturur ve eşleşen katmanlara bağlar.  
`Map`, Aspose.GIS içinde katmanları ve render ayarlarını tutan merkezi nesnedir.

### Adım‑adım kılavuz
1. **Create the map instance.**  
   ```csharp
   var map = new Map();
   ```
2. **Add your vector data source.**  
   ```csharp
   map.Layers.Add(new ShapefileLayer("roads.shp"));
   ```
3. **Import the SLD file.**  
   ```csharp
   map.LoadStyle("./styles/roadStyle.sld");
   ```
4. **Render or further customize.**  
   ```csharp
   map.Render("output.png", new RenderOptions { Width = 1024, Height = 768 });
   ```

## Harita Nasıl Etiketlenir
Aspose.GIS'te etiketleme, özelliklere öznitelik değerlerine göre metin sembolleri ekler. Motor optimal yerleşimi hesaplar, geometri tipine saygı gösterir ve çakışmaları önleyebilir, böylece manuel konumlandırma olmadan net, okunabilir haritalar elde edersiniz. Her etiket katmanı için yazı tipi, boyut ve stil de özelleştirilebilir. Daha fazla bilgi için [Discover Feature Labeling Tutorial](./label-features-on-map/) adresine bakın.

**Doğrudan cevap:** Katman yüklendikten sonra `layer.Labels.Add(new LabelStyle { Font = new Font("Arial", 10), Placement = LabelPlacement.Point })` çağrısı yapın – Aspose.GIS çakışmaları önleyerek etiketleri otomatik olarak yerleştirir.  
`LabelStyle`, harita etiketlerinin yazı tipi, boyut ve yerleşim gibi görsel özelliklerini tanımlar.

### Ana etiketleme seçenekleri
- **Yazı tipi ve boyut:** Sunucuda yüklü herhangi bir TrueType yazı tipini seçin.  
- **Yerleşim:** Geometri tipine bağlı olarak `LabelPlacement.Point`, `LabelPlacement.Line` veya `LabelPlacement.Polygon`.  
- **Çakışma tespiti:** Yoğun haritalarda metin çakışmasını önlemek için `LabelOptions.CollisionDetection = true` etkinleştirin.

## Haritaları Etiketlemek İçin Neden Aspose.GIS for .NET Kullanılmalı?
Aspose.GIS, tipik bir 2.5 GHz CPU üzerinde saniyede **10 000 özelliğe** kadar etiketleyebilir ve küresel diller için **Unicode‑tam metin render'ı** destekler. API ayrıca yerleşik çakışma yönetimi sağlar, bu da özel etiket‑yerleştirme algoritmalarına ihtiyaç duyulmadığı anlamına gelir.

## Önkoşullar
- Visual Studio 2022 (veya herhangi bir .NET‑uyumlu IDE)  
- Aspose.GIS for .NET NuGet paketi kurulu (`Install-Package Aspose.GIS`)  
- Örnek bir veri seti (Shapefile, GeoJSON, vb.)  
- Uygulamak istediğiniz bir SLD dosyası  

## Harita Render'ı
Stilize edilmiş vektör verilerinden raster görüntü oluşturmak basittir.  

**Doğrudan cevap:** `map.Render("map.png", new RenderOptions { Width = 1200, Height = 800, Dpi = 300 })` çağrısını yapın – bu tek çağrı ek yapılandırma olmadan yüksek çözünürlüklü PNG, JPEG veya GeoTIFF üretir. Harita render'ına başlamak için [Get Started with Map Rendering](./render-a-map/) rehberine bakın.  
`RenderOptions`, görüntü boyutu, DPI, arka plan rengi ve diğer render parametrelerini belirlemenizi sağlar.

## Çeşitli Raster Formatlarını Render Etme
Aspose.GIS **12 raster çıktı formatını** (PNG, JPEG, BMP, TIFF, GeoTIFF, SVG, PDF ve WebP dahil) destekler.  
Farklı bir format render'lamak için dosya uzantısını değiştirin veya seçenek nesnesinde `RenderFormat` belirtin. Format seçeneklerini [Explore Raster Formats Tutorial](./render-various-raster-formats/) adresinde keşfedin.  
`RenderFormat`, PNG, JPEG ve GeoTIFF gibi desteklenen raster çıktı türlerini listeler.

## Yaygın Kullanım Senaryoları
- **Tematik haritalama:** Nüfus yoğunluğu, arazi kullanımı veya çevresel verileri görselleştirmek için bir SLD uygulayın.  
- **Dinamik etiketleme:** Harita görünümü değiştiğinde otomatik olarak güncellenen şehir adları, yol numaraları veya özel POI etiketleri eklemek için “label map” yaklaşımını kullanın.  
- **Çok‑formatlı dışa aktarım:** Web hizmetleri, baskı veya sonraki GIS analizleri için PNG, JPEG veya GeoTIFF çıktıları oluşturun.

## Sorun Giderme İpuçları
- **SLD uygulanmıyor mu?** Her `<FeatureTypeStyle>` öğesinin `Name` özniteliğinin `Map` içindeki ilgili katman adıyla eşleştiğini doğrulayın.  
- **Etiketler çakışıyor mu?** `LabelOptions.CollisionResolutionRadius` değerini artırın veya doğrusal özellikler için `LabelPlacement.Line`'a geçin.  
- **Raster render'ı bulanık mı?** Dışa aktarmadan önce `RenderOptions` içinde daha yüksek DPI (ör. `Dpi = 300`) ayarlayın.

## Sıkça Sorulan Sorular

**Q: Farklı katmanlar için birden fazla SLD dosyasını birleştirebilir miyim?**  
A: Evet. Her SLD'yi ayrı ayrı yükleyin ve `Layer.Style` özelliğiyle uygun katmana atayın.

**Q: Aspose.GIS özel sembol yazı tiplerini destekliyor mu?**  
A: Kesinlikle. SLD'nizde TrueType yazı tiplerine referans verin veya `Symbol.Font = new Font("CustomFont", 12)` ile sembolleri programlı olarak tanımlayın.

**Q: Arka plan olmadan (şeffaf PNG) bir harita nasıl render'lanır?**  
A: `Render` çağrısından önce `RenderOptions.BackgroundColor = Color.Transparent` ayarlayın.

**Q: İçe aktardıktan sonra bir SLD'yi düzenlemek mümkün mü?**  
A: Bir katmandan `Style` nesnesini alabilir, kurallarını değiştirebilir ve XML dosyasını yeniden yüklemeden tekrar uygulayabilirsiniz.

**Q: Raster çıktısının boyutu konusunda hangi sınırlamalar vardır?**  
A: Raster boyutu mevcut bellekle sınırlıdır; 10 000 × 10 000 px'den büyük görüntüler için çıkışı akışa almak amacıyla döşeme (`RenderOptions.TileSize`) kullanın.

## Harita Render'ı Öğreticileri
### [Styled Layer Descriptor (SLD) İçe Aktarma](./import-styled-layer-descriptor/)
Aspose.GIS for .NET ile GIS geliştirmeyi yükseltin. Styled Layer Descriptor (SLD)'yi zahmetsizce içe aktarın. Şimdi özelleştirme olanaklarını keşfedin!
### [Haritada Özellikleri Etiketleme](./label-features-on-map/)
Aspose.GIS for .NET'i keşfedin ve haritalarda özellik etiketleme sanatında uzmanlaşın. Coğrafi görselleştirmelerinizi zahmetsizce geliştirin.
### [Harita Render'ı](./render-a-map/)
Aspose.GIS for .NET ile coğrafi veri görselleştirmenin dünyasını keşfedin. Muhteşem haritalar oluşturun zahmetsizce. Şimdi indirin!
### [Çeşitli Raster Formatlarını Render Etme](./render-various-raster-formats/)
Aspose.GIS for .NET ile raster veri görselleştirmenin dünyasını keşfedin. Çeşitli formatlarda muhteşem haritalar render'lamayı zahmetsizce öğrenin. Şimdi indirin!

---

**Son Güncelleme:** 2026-08-30  
**Test Edilen:** Aspose.GIS for .NET 24.10  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Aspose.GIS for .NET ile SVG Harita Oluşturma ve Şehir Ekleme](/gis/net/map-rendering/render-a-map/)
- [Aspose.GIS kullanarak asp.net ile stilize harita oluşturma](/gis/net/map-rendering/import-styled-layer-descriptor/)
- [Aspose.GIS for .NET ile SLD İçe Aktarma ve Harita Render'ı](/gis/net/map-rendering/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}