---
date: 2026-07-24
description: Aspose.GIS'i kullanarak .NET'te Shapefile'ı GeoJSON'a sorunsuz bir şekilde
  dönüştürmeyi ve C# ile Shapefile okurken kesintisiz coğrafi veri birlikte çalışabilirliğini
  nasıl sağlayacağınızı öğrenin.
keywords:
- convert shapefile to geojson
- read shapefile c#
- c# shapefile to geojson
- export geojson c#
- convert shapefile to json
lastmod: 2026-07-24
linktitle: Shapefile'ı GeoJSON'a Dönüştür
og_description: Aspose.GIS for .NET kullanarak shapefile'ı geojson'a hızlıca dönüştürün.
  10 dakikadan kısa sürede adım adım C# kodunu, ön koşulları ve sorun giderme yöntemlerini
  öğrenin.
og_image_alt: 'Developer guide: Convert Shapefile to GeoJSON in C# with Aspose.GIS'
og_title: Shapefile'ı GeoJSON'a Dönüştür – Hızlı C# Rehberi (50‑60 karakter)
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Learn how to effortlessly convert Shapefile to GeoJSON in .NET using
    Aspose.GIS and achieve seamless geospatial data interoperability while reading
    Shapefile in C#.
  headline: Convert Shapefile to GeoJSON
  type: TechArticle
- questions:
  - answer: Yes. Place the conversion code inside a `foreach` loop that iterates over
      each `.shp` file in a directory, calling `VectorLayer.Convert` for every file.
    question: Can I convert multiple Shapefiles to GeoJSON in one go using Aspose.GIS
      for .NET?
  - answer: It supports .NET Framework 4.5 and higher, as well as .NET Core 3.1+ and
      .NET 5/6/7.
    question: Is Aspose.GIS for .NET compatible with all versions of .NET Framework?
  - answer: Absolutely. The library handles formats such as GeoTIFF, KML, GML, CSV,
      and many more—over 60 in total.
    question: Does Aspose.GIS for .NET provide support for other geospatial formats
      apart from Shapefile and GeoJSON?
  - answer: Yes. The API offers overloads and properties to set target coordinate
      systems, filter attributes, and modify feature geometry during conversion.
    question: Can I customize the conversion process, such as specifying a coordinate
      system or attribute mappings?
  - answer: Yes, you can download a free trial from the [Aspose website](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert shapefile
- Aspose.GIS
- C# geospatial processing
- geojson export
title: Shapefile'ı GeoJSON'a Dönüştür
url: /tr/net/geo-data-conversion/convert-shapefile-to-geojson/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Shapefile'i GeoJSON'a Dönüştür

## Giriş
Modern Coğrafi Bilgi Sistemleri (GIS) içinde, **coğrafi veri birlikte çalışabilirliği** güçlü mekansal analizlerin kilidini açmanın anahtarıdır. En yaygın dönüşüm görevlerinden biri **shapefile'i geojson'a dönüştürmek** olup, web haritaları, mobil uygulamalar ve bulut hizmetleriyle hafif veri alışverişi sağlar. Bu öğreticide **C#'ta shapefile okuma** ve Aspose.GIS .NET kütüphanesini kullanarak GeoJSON olarak dışa aktarma yöntemini göreceksiniz, böylece dönüşümü doğrudan uygulamalarınıza entegre edebilirsiniz.

## Hızlı Yanıtlar
- **Dönüşümü hangi kütüphane yönetir?** Aspose.GIS for .NET  
- **Uygulama ne kadar sürer?** Tek bir dosya için genellikle 10 dakikadan az  
- **Lisans gerekir mi?** Geliştirme için ücretsiz deneme çalışır; üretim için lisans gereklidir  
- **Desteklenen .NET sürümleri?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **Birden fazla dosyayı dönüştürebilir miyim?** Evet – sadece `VectorLayer.Convert` çağrısını döngüye alın  

## “shapefile'i geojson'a dönüştürmek” nedir?
Bir Shapefile'i (`.shp`, `.shx`, `.dbf` dosyalarının üçlüsü) GeoJSON'a dönüştürmek, veriyi tek bir JSON‑tabanlı formata çevirir; bu format tarayıcılarda okunması, düzenlenmesi ve görüntülenmesi kolaydır. GeoJSON, özellikle Leaflet veya Mapbox gibi JavaScript haritalama kütüphaneleri için uygundur.

## GIS veri formatı dönüşümü için .NET için Aspose.GIS'i neden kullanmalısınız?
Aspose.GIS, 60'tan fazla vektör ve raster formatını destekleyen kapsamlı, tamamen yönetilen bir çözüm sunar, harici bağımlılıkları ortadan kaldırır ve büyük veri setleri için bile yüksek hızlı dönüşümler sağlar; bu da güvenilirliğin ve performansın bugün kritik olduğu kurumsal ve bulut ortamları için ideal kılar.

- **All‑in‑one API** – **60+** coğrafi vektör ve raster formatını, KML, GML, CSV, GeoTIFF ve daha fazlasını destekler.  
- **Zero‑dependency conversion** – GDAL, Proj4 veya yerel ikili dosyalar gerekmez; her şey saf yönetilen kodda çalışır.  
- **High performance** – Tipik bir sunucu VM'sinde **500 MB** dosyaları **5 saniye** altında işler ve aşırı bellek kullanımı olmadan toplu işleri yönetebilir.  
- **Rich customization** – Hedef koordinat sistemlerini belirtebilir, öznitelikleri filtreleyebilir ve geometrileri anında dönüştürebilirsiniz.  

## Önkoşullar
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

1. **Aspose.GIS for .NET yüklü** – Resmi [Aspose.GIS for .NET documentation](https://reference.aspose.com/gis/net/) üzerindeki talimatları izleyerek projenize NuGet paketini ekleyin.  
2. **Bir kaynak Shapefile** – Açık veri portalından, bir devlet kurumundan edinin veya QGIS/ArcGIS ile oluşturun.  
3. **Temel C# bilgisi** – Kod parçacıkları C# sözdizimini ve .NET konvansiyonlarını kullanır.  

## Ad Alanlarını İçe Aktarma
`Aspose.GIS` ad alanları, vektör verilerini okuma ve yazma için gereken sınıfları sağlar.

`Aspose.GIS.Geometries` ad alanı geometri tiplerini içerirken, `Aspose.GIS.VectorLayers` format dönüşümünü gerçekleştiren `VectorLayer` sınıfını barındırır. `Aspose.GIS.VectorLayers` ad alanı da format dönüşümü için kullanılan `VectorLayer` sınıfını içerir.

## C#'ta shapefile'i GeoJSON'a nasıl dönüştürülür?
`VectorLayer.Open` yöntemi, bir dosyadan vektör veri setini bir `VectorLayer` nesnesine yükler.  
`VectorLayer.Convert` ise bir kaynak vektör dosyasını doğrudan GeoJSON gibi hedef bir formata dönüştüren statik bir yöntemdir.

Kaynak Shapefile'i `VectorLayer.Open` ile yükleyin, ardından tek satırda bir GeoJSON dosyası yazmak için statik `VectorLayer.Convert` yöntemini çağırın. Bu yaklaşım kaynağı okur, isteğe bağlı olarak yeniden projeler ve sonucu doğrudan diske akıtarak ara nesnelere ihtiyaç duymaz.

### Adım 1: Giriş ve Çıkış Yollarını Tanımlayın
Shapefile'inizi içeren klasörü ve GeoJSON dosyasının hedefini ayarlayın. Yolu ortamınıza uygun şekilde düzenleyin.

Platform bağımsız yol oluşturmak için `Path.Combine(dataDir, "InputShapeFile.shp")` ve sonuç dosyası için `Path.Combine(outputDir, "output.geojson")` kullanın.

> **Pro ipucu:** Üç Shapefile bileşenini (`.shp`, `.shx`, `.dbf`) aynı klasörde tutun; `VectorLayer.Open` ilgili dosyaları otomatik olarak bulur.

### Adım 2: Dönüşümü Gerçekleştirin
`VectorLayer.Convert(inputPath, outputPath, OutputFormat.GeoJSON)` çağrısını yapın. Bu tek satır Shapefile'i okur, dönüştürür ve geçerli bir GeoJSON FeatureCollection yazar.

Çalıştırdıktan sonra `output.geojson`, herhangi bir web‑harita görüntüleyici, GIS sunucusu veya analiz hattına yükleyebileceğiniz tam uyumlu bir GeoJSON belgesi içerecektir.

## Bunun Önemi Nedir?
Shapefile'leri GeoJSON'a dönüştürmek, modern web‑haritalama kütüphaneleriyle sorunsuz entegrasyon sağlar, dosya boyutunu azaltır ve platformlar arasında veri alışverişini basitleştirir; geliştiricilerin eski format karmaşıklıklarıyla uğraşmadan duyarlı GIS uygulamaları oluşturmasına olanak tanır ve mekansal veriyle çalışan ekiplerin genel iş akışı verimliliğini artırır.

- **Interoperability:** GeoJSON'a dönüştürmek, veriyi özel formatlar hakkında endişelenmeden geniş bir web‑tabanlı GIS araçları yelpazesiyle paylaşmanıza olanak tanır.  
- **Performance:** Aspose.GIS dönüşümü bellek içinde işler, bu da harici komut satırı araçlarını çağırmaktan daha hızlıdır.  
- **Scalability:** Aynı yaklaşım bir döngüye veya arka plan hizmetine sarılarak veri hatları için toplu dönüşümleri yönetebilir.  

## Yaygın Sorunlar ve Çözümler

| Sorun | Neden Oluşur | Çözüm |
|-------|----------------|-----|
| **Dosya bulunamadı** | `dataDir` hatalı veya `.shp` dosyası eksik | Yolu doğrulayın ve üç Shapefile bileşeninin (`.shp`, `.shx`, `.dbf`) mevcut olduğundan emin olun. |
| **Koordinat sistemi uyuşmazlığı** | Kaynak Shapefile, tüketici tarafından tanınmayan bir projeksiyon kullanıyor | Dönüşümden önce yeniden projeksiyon yapmak için `VectorLayer.Open(...).CoordinateSystem` kullanın. |
| **Büyük dosyalar bellek baskısına neden olur** | Tüm veri seti belleğe yüklendi | Özellikleri parçalar halinde işleyin veya akış dönüşümü için `VectorLayer.Stream` kullanın. |

## Sıkça Sorulan Sorular

**S: Aspose.GIS for .NET kullanarak birden fazla Shapefile'i tek seferde GeoJSON'a dönüştürebilir miyim?**  
C: Evet. Dönüşüm kodunu bir dizindeki her `.shp` dosyasını yineleyen bir `foreach` döngüsü içine yerleştirin ve her dosya için `VectorLayer.Convert` çağırın.

**S: Aspose.GIS for .NET tüm .NET Framework sürümleriyle uyumlu mu?**  
C: .NET Framework 4.5 ve üzeri, ayrıca .NET Core 3.1+ ve .NET 5/6/7'yi destekler.

**S: Aspose.GIS for .NET, Shapefile ve GeoJSON dışındaki diğer coğrafi formatları da destekliyor mu?**  
C: Kesinlikle. Kütüphane GeoTIFF, KML, GML, CSV ve daha birçok formatı—toplamda 60'tan fazlasını—destekler.

**S: Dönüşüm sürecini, örneğin bir koordinat sistemi veya öznitelik eşlemeleri belirterek özelleştirebilir miyim?**  
C: Evet. API, hedef koordinat sistemlerini ayarlamak, öznitelikleri filtrelemek ve dönüşüm sırasında özellik geometrisini değiştirmek için aşırı yüklemeler ve özellikler sunar.

**S: Aspose.GIS for .NET için bir deneme sürümü mevcut mu?**  
C: Evet, [Aspose web sitesinden](https://releases.aspose.com/) ücretsiz bir deneme indirebilirsiniz.

## Sonuç
Bu adımları izleyerek artık **shapefile'i geojson'a nasıl dönüştüreceğinizi** **Aspose.GIS for .NET** kullanarak verimli bir şekilde biliyorsunuz. Bu yetenek, sorunsuz **coğrafi veri birlikte çalışabilirliği** sağlar ve mekansal verileri modern web haritalarına, API'lere ve analiz hatlarına beslemenize olanak tanır. Projeleriniz geliştikçe KML, GML, raster formatları ve daha fazlasını yönetmek için Aspose.GIS'in daha geniş **GIS veri formatı dönüşümü** özelliklerini keşfedin.

---

**Son Güncelleme:** 2026-07-24  
**Test Edilen Versiyon:** Aspose.GIS for .NET 24.11  
**Yazar:** Aspose

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

```csharp
string dataDir = "Your Document Directory";
string shapefilePath = dataDir + "InputShapeFile.shp";
string jsonPath = dataDir + "output_out.json";
```

```csharp
VectorLayer.Convert(shapefilePath, Drivers.Shapefile, jsonPath, Drivers.GeoJson);
```

## İlgili Öğreticiler

- [Aspose.GIS for .NET ile Akıştan GeoJSON Okuma](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Aspose.GIS ile GeoJSON'ı TopoJSON'a Dönüştürme](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Aspose.GIS ile Shapefile C# – Özellikleri Öznitelik ile Filtreleme](/gis/net/layer-management/filter-features-by-attribute/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}