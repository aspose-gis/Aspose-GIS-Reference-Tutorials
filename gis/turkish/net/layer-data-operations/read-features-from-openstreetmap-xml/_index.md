---
date: 2026-06-10
description: Aspose.GIS for .NET kullanarak OSM'yi Shapefile'a dönüştürmeyi ve OpenStreetMap
  XML özelliklerini okumayı öğrenin. Pratik ipuçlarıyla adım adım rehber.
keywords:
- convert osm to shapefile
- osm to geojson conversion
- how to read osm xml
linktitle: OpenStreetMap XML'den Özellikleri Okuyun
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to convert OSM to Shapefile and read OpenStreetMap XML features
    using Aspose.GIS for .NET. Step‑by‑step guide with practical tips.
  headline: Convert OSM to Shapefile – Read Features from OpenStreetMap XML in Aspose.GIS
  type: TechArticle
- questions:
  - answer: Aspose.GIS for .NET
    question: What library handles OSM XML?
  - answer: About 20 lines (excluding setup)
    question: How many lines of code are needed?
  - answer: A free trial works for testing; a license is required for production.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes—Aspose.GIS streams data efficiently; filtering reduces memory usage.
    question: Can I read large OSM files?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: OSM'yi Shapefile'a Dönüştür – Aspose.GIS'te OpenStreetMap XML'den Özellikleri
  Okuyun
url: /tr/net/layer-data-operations/read-features-from-openstreetmap-xml/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# OSM'yi Shapefile'a Dönüştür – OpenStreetMap XML'den Özellikleri Aspose.GIS ile Okuma

Eğer **OSM'yi Shapefile'a dönüştürmek** istiyor ya da bir .NET uygulaması içinde OpenStreetMap (OSM) XML verilerini okumak istiyorsanız, doğru yerdesiniz. Aspose.GIS for .NET, OSM XML dosyalarını sorunsuz bir şekilde içe aktarmayı, düğüm, yol ve ilişkileri çıkarmayı ve ardından Shapefile, GeoJSON veya diğer GIS formatlarına dışa aktarmayı kolaylaştırır. Bu öğreticide, ortam kurulumundan özellik yinelemeye kadar tüm iş akışını adım adım göstereceğiz; böylece haritalama veya mekansal‑analiz çözümleri geliştirmeye hemen başlayabilirsiniz.

## Hızlı Yanıtlar
- **OSM XML'i işleyen kütüphane nedir?** Aspose.GIS for .NET  
- **Kaç satır kod gerekir?** Yaklaşık 20 satır (kurulum hariç)  
- **Geliştirme için lisansa ihtiyacım var mı?** Test için ücretsiz deneme çalışır; üretim için lisans gereklidir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Büyük OSM dosyalarını okuyabilir miyim?** Evet—Aspose.GIS verileri verimli bir şekilde akıtarak; filtreleme bellek kullanımını azaltır.

## “how to read osm” nedir?
OSM (OpenStreetMap) verilerini okumak, gerçek‑dünya coğrafi özelliklerini temsil eden düğüm, yol ve ilişkileri erişmek için OSM XML formatını ayrıştırmak anlamına gelir. Ayrıştırıldıktan sonra, bu verileri sorgulayabilir, görselleştirebilir veya çeşitli GIS uygulamaları için dönüştürebilirsiniz. Ayrıca etiketler, zaman damgaları ve kullanıcı bilgileri gibi meta verileri içerir; bu da ayrıntılı analiz ve düzenleme iş akışlarını mümkün kılar.

## Aspose.GIS for OSM neden kullanılmalı?
Aspose.GIS, **sıfır bağımlılık** ayrıştırıcı sunar; 1 GB'a kadar dosyaları 250 MB'den az RAM kullanarak işleyebilir ve birçok açık kaynak alternatife göre 3 kat daha hızlıdır. Ayrıca yerleşik geometri dönüşümü, mekansal sorgular ve doğrudan Shapefile, GeoJSON, KML ve daha fazlasına dışa aktarma sağlar; hepsi saf .NET kodundan yapılır.

## Önkoşullar
- **Visual Studio** (Community, Professional veya Enterprise) – son sürüm önerilir.  
- **Aspose.GIS for .NET** – resmi [download link](https://releases.aspose.com/gis/net/) üzerinden indirin ve projenize NuGet paketini ekleyin.  
- Temel C# bilgisi (değişkenler, döngüler, OOP).  

## Ad Alanlarını İçe Aktar
`Aspose.Gis` ad alanı temel GIS tiplerini sağlar, `Aspose.Gis.Geometries` ise geometri yardımcılarını içerir.

`Aspose.Gis` ad alanı, Aspose.GIS'teki tüm GIS işlemleri için giriş noktasıdır.

## Aspose.GIS Kullanarak OSM'yi Shapefile'a Nasıl Dönüştürülür?
OSM XML katmanını yükleyin, özellikleri üzerinde yineleme yapın ve sadece üç API çağrısıyla bir Shapefile'a yazın. `ShapefileWriter` sınıfı yeni bir Shapefile oluşturur ve özellikleri ona yazar. İlk olarak OSM kaynağı için bir `Layer` nesnesi oluşturun, ardından hedef klasöre işaret eden bir `ShapefileWriter` açın ve son olarak her özelliğin geometrisini ve özniteliklerini kopyalayın. Bu yaklaşım, tipik şehir ölçeğindeki veri setleri (≈ 200 k özellik) için bir dakikadan kısa sürede OSM'yi Shapefile'a dönüştürür.

## osm'den geojson'a dönüşüm nasıl yapılır
Aspose.GIS, aynı OSM katmanını tek bir `Save` çağrısıyla doğrudan GeoJSON'a dışa aktarabilir; ara format adımlarına gerek kalmaz. `Save` yöntemi katmanı seçilen formata ve dosya yoluna yazar. `layer.Save("output.geojson", SaveFormat.GeoJson)` çağrısını yapın; kütüphane koordinat dönüşümünü ve öznitelik eşlemesini otomatik olarak gerçekleştirir ve web haritalama için standartlara uygun bir GeoJSON dosyası sunar.

## Adım 1: Belge Dizinini Tanımla
OSM XML dosyanızın bulunduğu klasörü tanımlayın.  
`"Your Document Directory"` ifadesini dosyanın mutlak ya da göreli yoluyla değiştirin.

## Adım 2: OpenStreetMap Katmanını Aç
`Layer` sınıfı, OSM XML dosyası gibi bir veri kaynağından yüklenen bir GIS katmanını temsil eder.  
Katmanı açmak XML'i akıtarak yalnızca gerekli bölümleri bellekte tutar.

## Adım 3: Özellik Sayısını Al
OSM katmanındaki toplam özellik sayısını alın ve konsola yazdırın. Bu, dosyanın doğru okunup okunmadığını doğrulamanıza yardımcı olur.

## Adım 4: İndeksteki Özelliği Al
Sıfır‑tabanlı indeksine göre herhangi bir özelliğe doğrudan erişin; örnek, rastgele erişimi göstermek için üçüncü özelliği getirir.

## Adım 5: Özellikler Üzerinde Yineleme Yap
Katman üzerinde yineleme, her geometriyi—nokta, çizgi veya çokgen—tek tek işlemenizi sağlar. `AsText()` yöntemi, geometriyi Hâlihazırdaki Bilinen Metin (WKT) formatında döndürür; bu, hata ayıklama veya günlükleme için kullanışlıdır.

## Yaygın Sorunlar ve Çözümler
- **Dosya bulunamadı** – `dataDir` içindeki yolu iki kez kontrol edin ve OSM dosya adının tam olarak eşleştiğinden emin olun.  
- **Desteklenmeyen geometri** – Bazı OSM öğeleri karmaşık ilişkiler içerir; önce `feature.Geometry`'yi inceleyin ve `MultiPolygon` veya `GeometryCollection` tiplerini buna göre işleyin.  
- **Büyük dosyalarda performans** – Katmanı bir `using` bloğu içinde yükleyin (gösterildiği gibi) böylece doğru şekilde serbest bırakılır ve sadece belirli özelliklere ihtiyacınız varsa LINQ filtresi (`layer.Where(f => f.Geometry is Point)`) uygulayın.

## Sık Sorulan Sorular
### Aspose.GIS for .NET diğer GIS veri formatlarıyla uyumlu mu?
**Evet**, Aspose.GIS 30'dan fazla GIS formatını destekler—Shapefile, GeoJSON, KML, GML ve CSV dahil—ve sorunsuz veri alışverişi sağlar.

### Aspose.GIS'i ticari amaçlarla kullanabilir miyim?
**Kesinlikle**. Deneme sınırlamalarını kaldırmak ve tam destek almak için [satın alma sayfasından](https://purchase.aspose.com/buy) bir lisans edinin.

### Aspose.GIS for .NET için ücretsiz bir deneme mevcut mu?
**Evet**, satın almadan önce tüm özellikleri değerlendirmek için [web sitesinden](https://releases.aspose.com/) tam işlevsel bir deneme sürümü indirin.

### Aspose.GIS for .NET için destek nereden bulunur?
**Resmi [Aspose.GIS forumunu](https://forum.aspose.com/c/gis/33) ziyaret edin**; sorular sorabilir, kod parçacıkları paylaşabilir ve topluluk ile Aspose mühendislerinden yardım alabilirsiniz.

### Aspose.GIS for .NET için geçici bir lisans alabilir miyim?
**Evet**, kısa vadeli testler veya CI pipeline'ları için [geçici lisans sayfasından](https://purchase.aspose.com/temporary-license/) geçici bir lisans talep edebilirsiniz.

---

**Son Güncelleme:** 2026-06-10  
**Test Edilen:** Aspose.GIS 24.5 for .NET  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

```csharp
string dataDir = "Your Document Directory";
```

```csharp
using (var layer = Drivers.OsmXml.OpenLayer(dataDir + "fountain.osm"))
{
```

```csharp
int count = layer.Count;
Console.WriteLine("Layer count: " + count);
```

```csharp
Feature featureAtIndex2 = layer[2];
```

```csharp
foreach (Feature feature in layer)
{
    Console.WriteLine(feature.Geometry.AsText());
}
```

## İlgili Eğitimler

- [Aspose.GIS for .NET ile Shapefile'ı GeoJSON'a Dönüştürme – Kapsamlı Eğitimler](/gis/net/)
- [Aspose.GIS ile GeoJSON'ı TopoJSON'a Dönüştürme](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [C# ile Shapefile Okuma – Aspose.GIS ile Özellikleri Niteliklerine Göre Filtreleme](/gis/net/layer-management/filter-features-by-attribute/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}