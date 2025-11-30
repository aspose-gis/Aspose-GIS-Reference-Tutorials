---
date: 2025-11-30
description: Aspose.GIS kullanarak .NET’te Shapefile’ı sorunsuz bir şekilde GeoJSON’a
  nasıl dönüştüreceğinizi öğrenin. Kesintisiz coğrafi veri birlikte çalışabilirliği
  için adım adım rehberimizi izleyin.
language: tr
linktitle: Convert Shapefile to GeoJSON
second_title: Aspose.GIS .NET API
title: Shapefile'ı GeoJSON'a Dönüştür
url: /net/geo-data-conversion/convert-shapefile-to-geojson/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Shapefile'ı GeoJSON'a Dönüştür

## Giriş
Modern Coğrafi Bilgi Sistemleri (GIS)'de **geospatial data interoperability**, güçlü mekansal analizlerin kilidini açmanın anahtarıdır. En yaygın dönüşüm görevlerinden biri **convert shapefile to geojson**'dır, bu da web haritaları, mobil uygulamalar ve bulut hizmetleriyle hafif veri alışverişini mümkün kılar. Bu öğretici, **Aspose.GIS .NET** kütüphanesini kullanarak tüm süreci adım adım gösterir, böylece dönüşümü doğrudan C# uygulamalarınıza entegre edebilirsiniz.

## Hızlı Yanıtlar
- **Dönüşümü hangi kütüphane yönetir?** Aspose.GIS for .NET  
- **Uygulama ne kadar sürer?** Tek bir dosya için genellikle 10 dakikadan az  
- **Bir lisansa ihtiyacım var mı?** Geliştirme için ücretsiz deneme yeterlidir; üretim için lisans gereklidir  
- **Desteklenen .NET sürümleri?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **Birden fazla dosyayı dönüştürebilir miyim?** Evet – sadece `VectorLayer.Convert` çağrısını döngü içinde kullanın  

## “convert shapefile to geojson” nedir?
Shapefile'ı (`.shp`, `.shx`, `.dbf` dosyalarından oluşan bir koleksiyon) GeoJSON'a dönüştürmek, veriyi tek bir JSON‑tabanlı formata çevirir; bu format web tarayıcılarında okunması, düzenlenmesi ve render edilmesi kolaydır. GeoJSON, özellikle Leaflet veya Mapbox gibi JavaScript haritalama kütüphaneleri için uygundur.

## GIS veri formatı dönüşümü için neden Aspose.GIS for .NET kullanmalı?
- **All‑in‑one API** – Dış araçlar olmadan onlarca formatı (GeoTIFF, KML, GML, vb.) yönetir.  
- **Zero‑dependency conversion** – GDAL veya diğer yerel kütüphanelere ihtiyaç yok.  
- **High performance** – Büyük veri setleri ve toplu işleme için optimize edilmiştir.  
- **Rich customization** – Koordinat sistemlerini, öznitelik filtrelerini ve daha fazlasını belirtebilirsiniz.

## Ön Koşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. **Aspose.GIS for .NET installed** – Resmi [Aspose.GIS for .NET documentation](https://reference.aspose.com/gis/net/) üzerindeki talimatları izleyerek projenize NuGet paketini ekleyin.  
2. **A source Shapefile** – Açık veri portalından, bir devlet kurumundan edinin veya QGIS/ArcGIS ile oluşturun.  
3. **Basic C# knowledge** – Kod parçacıkları C# sözdizimini ve .NET konvansiyonlarını kullanır.

## Ad Alanlarını İçe Aktarın
İlk olarak, Aspose.GIS sınıflarına ve standart .NET yardımcı programlarına erişmenizi sağlayan ad alanlarını içe aktarın:

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Adım‑Adım Kılavuz

### Adım 1: Giriş ve Çıkış Yollarını Tanımlayın
Shapefile'ınızı içeren klasörü ve GeoJSON dosyasının hedefini ayarlayın. Ortamınıza uygun şekilde yolu düzenleyin.

```csharp
string dataDir = "Your Document Directory";
string shapefilePath = dataDir + "InputShapeFile.shp";
string jsonPath = dataDir + "output_out.json";
```

> **Pro tip:** Platform bağımsız yol oluşturmak için `Path.Combine(dataDir, "InputShapeFile.shp")` kullanın.

### Adım 2: Dönüşümü Gerçekleştirin
Statik `VectorLayer.Convert` metodunu çağırın. Bu tek satır Shapefile'ı okur, dönüştürür ve bir GeoJSON dosyası yazar.

```csharp
VectorLayer.Convert(shapefilePath, Drivers.Shapefile, jsonPath, Drivers.GeoJson);
```

Çalıştırdıktan sonra, `output_out.json` geçerli bir GeoJSON FeatureCollection içerecek ve bunu herhangi bir web‑harita görüntüleyicisine yükleyebilirsiniz.

## Yaygın Sorunlar ve Çözümler
| Sorun | Neden Oluşur | Çözüm |
|-------|----------------|-----|
| **Dosya bulunamadı** | `dataDir` hatalı veya `.shp` dosyası eksik | Yolu doğrulayın ve üç Shapefile bileşeninin (`.shp`, `.shx`, `.dbf`) mevcut olduğundan emin olun. |
| **Koordinat sistemi uyumsuzluğu** | Kaynak Shapefile, tüketici tarafından tanınmayan bir projeksiyon kullanıyor | Dönüştürmeden önce yeniden projeksiyonlamak için `VectorLayer.Open(...).CoordinateSystem` kullanın. |
| **Büyük dosyalar bellek baskısı oluşturur** | Tüm veri seti belleğe yükleniyor | Özellikleri parçalar halinde işleyin veya akış dönüşümü için `VectorLayer.Stream` kullanın. |

## Sıkça Sorulan Sorular

**S: Aspose.GIS for .NET kullanarak birden fazla Shapefile'ı tek seferde GeoJSON'a dönüştürebilir miyim?**  
C: Evet. Dönüşüm kodunu bir dizindeki her `.shp` dosyasını yineleyen bir `foreach` döngüsü içine yerleştirin.

**S: Aspose.GIS for .NET tüm .NET Framework sürümleriyle uyumlu mu?**  
C: .NET Framework 4.5 ve üzeri, ayrıca .NET Core 3.1+ ve .NET 5/6/7 sürümlerini destekler.

**S: Aspose.GIS for .NET, Shapefile ve GeoJSON dışındaki diğer coğrafi veri formatlarını da destekliyor mu?**  
C: Kesinlikle. Kütüphane GeoTIFF, KML, GML, CSV ve daha birçok formatı işler.

**S: Dönüşüm sürecini, örneğin koordinat sistemi veya öznitelik eşlemeleri belirterek özelleştirebilir miyim?**  
C: Evet. API, hedef koordinat sistemlerini ayarlamak, öznitelikleri filtrelemek ve dönüşüm sırasında özellik geometrisini değiştirmek için aşırı yüklemeler ve özellikler sunar.

**S: Aspose.GIS for .NET için bir deneme sürümü mevcut mu?**  
C: Evet, [Aspose web sitesinden](https://releases.aspose.com/) ücretsiz bir deneme indirebilirsiniz.

## Sonuç
Bu adımları izleyerek artık **how to convert shapefile to geojson**'ı **Aspose.GIS for .NET** kullanarak verimli bir şekilde yapabildiğinizi biliyorsunuz. Bu yetenek, sorunsuz **geospatial data interoperability** sağlar ve mekansal verileri modern web haritalarına, API'lere ve analiz hatlarına beslemenize imkan tanır. Projeleriniz büyüdükçe KML, GML ve raster formatlarını da işleyebilen daha geniş **GIS data format conversion** özelliklerini keşfedin.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Son Güncelleme:** 2025-11-30  
**Test Edilen:** Aspose.GIS for .NET 24.11  
**Yazar:** Aspose