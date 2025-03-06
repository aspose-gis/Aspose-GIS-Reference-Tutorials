---
title: Poligon Şekil Dosyasını Linestring'e Dönüştür
linktitle: Poligon Şekil Dosyasını Linestring'e Dönüştür
second_title: Aspose.GIS .NET API'si
description: Aspose.GIS for .NET'in gücünü keşfedin ve Poligon Şekil dosyalarını zahmetsizce Çizgi Dizilerine dönüştürün. CBS gelişiminizi bugün artırın!
weight: 18
url: /tr/net/layer-management/convert-polygon-shapefile-to-linestring/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Poligon Şekil Dosyasını Linestring'e Dönüştür

## giriiş
.NET'te coğrafi bilgi sistemleri (GIS) ile çalışıyorsanız Aspose.GIS, görevlerinizi kolaylaştırabilecek güçlü bir kütüphanedir. Bu eğitimde, Aspose.GIS kullanarak bir Poligon Şekil dosyasını Linestring'e dönüştürme sürecinde size rehberlik edeceğiz. Bu, rota planlama veya ağ analizi gibi çeşitli uygulamalar için çokgen verilerden doğrusal özellikler çıkarmanız gerektiğinde özellikle yararlı olabilir.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdakilerin mevcut olduğundan emin olun:
-  Aspose.GIS Kütüphanesi: Aspose.GIS kütüphanesini şu adresten indirip yükleyin:[İnternet sitesi](https://releases.aspose.com/gis/net/).
- Şekil Dosyası Verileri: Dönüşüm için bir Çokgen Şekil Dosyasını hazırlayın. Elinizde yoksa örnek veriler bulabilir veya kendinizinkini oluşturabilirsiniz.
- Geliştirme Ortamı: .NET geliştirme ortamınızı gerekli araçlarla kurun.
## Ad Alanlarını İçe Aktar
Gerekli sınıflara ve yöntemlere erişmek için C# kodunuzda Aspose.GIS ad alanlarını içe aktarmanız gerekir. Kod dosyanızın başına aşağıdaki ad alanlarını ekleyin:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## 1. Adım: Belge Dizinini Ayarlayın
```csharp
// Belgeler dizininin yolu.
string dataDir = "Your Document Directory";
```
"Belge Dizininiz"i Shapefile'ınızın bulunduğu dizinin yolu ile değiştirin.
## Adım 2: Kaynak Şekil Dosyasını Açın
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Kodun geri kalanı buraya gelecek
}
```
Bu adım kaynak Polygon Shapefile dosyasını okumak için açar.
## Adım 3: Hedef Linestring Şekil Dosyasını Oluşturun
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Kodun geri kalanı buraya gelecek
}
```
Burada dönüştürülen verileri yazmak için yeni bir Linestring Şekil dosyası oluşturuyoruz.
## Adım 4: Kaynak Özellikleri Üzerinden Yineleme Yapın
```csharp
foreach (Feature sourceFeature in source)
{
    // Kodun geri kalanı buraya gelecek
}
```
Bu döngü, kaynak Polygon Shapefile'daki her özellik boyunca yinelenir.
## Adım 5: Poligonu Linestring'e Dönüştürün ve Hedefe Yazın
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
Bu adımda, her Poligon özelliği bir Linestring'e dönüştürülür ve elde edilen Linestring özelliği hedef Shapefile'a yazılır.
## Çözüm
Bu adımları izleyerek, Aspose.GIS for .NET'i kullanarak bir Poligon Şekil dosyasını kolayca Linestring'e dönüştürebilirsiniz. Bu süreç CBS uygulamalarında veri analizi ve görselleştirme için yeni olanaklar açar.

## SSS
### Aspose.GIS .NET'in tüm sürümleriyle uyumlu mu?
Evet, Aspose.GIS, .NET'in çeşitli sürümlerini destekleyerek geliştirme ortamınızla uyumluluğu garanti eder.
### Aspose.GIS'i ticari projeler için kullanabilir miyim?
 Evet yapabilirsin. Aspose.GIS'i ticari projelerde kullanmak için bir lisans satın almayı düşünün[Burada](https://purchase.aspose.com/buy).
### Herhangi bir örnek veya belge mevcut mu?
 Evet, kapsamlı belgeleri ve örnekleri şurada bulabilirsiniz:[dokümantasyon sayfası](https://reference.aspose.com/gis/net/).
### Deneme sürümü mevcut mu?
 Evet, Aspose.GIS'i ziyaret ederek ücretsiz deneme sürümüyle keşfedebilirsiniz.[bu bağlantı](https://releases.aspose.com/).
### Nereden yardım veya destek alabilirim?
 Ziyaret edin[Aspose.GIS forumu](https://forum.aspose.com/c/gis/33) Yardım veya destekle ilgili sorularınız için.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
