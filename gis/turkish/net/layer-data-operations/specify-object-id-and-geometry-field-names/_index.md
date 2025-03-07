---
title: Nesne Kimliğini ve Geometri Alan Adlarını Belirleyin
linktitle: Nesne Kimliğini ve Geometri Alan Adlarını Belirleyin
second_title: Aspose.GIS .NET API'si
description: Aspose.GIS for .NET ile GIS büyüsünü keşfedin! Jeo-uzamsal verileri zahmetsizce yönetin. Hemen indirin ve mekansal zekanın gücünü açığa çıkarın.
weight: 20
url: /tr/net/layer-data-operations/specify-object-id-and-geometry-field-names/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nesne Kimliğini ve Geometri Alan Adlarını Belirleyin

## giriiş
Aspose.GIS for .NET'i kullanarak Coğrafi Bilgi Sistemleri (GIS) alanına doğru bir yolculuğa çıkmak, hem geliştiriciler hem de meraklılar için bir fırsatlar dünyasının kapılarını açıyor. Bu güçlü kitaplık, coğrafi verileri zahmetsizce işlemenizi sağlar. Bu eğitimde, Nesne Kimliği ve Geometri alan adlarını belirleme sürecinde size rehberlik ederek GIS çalışmalarınızın temelini atacağız.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
-  Aspose.GIS for .NET: Kütüphaneyi şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/gis/net/).
- Belge Dizini: Belgelerinizin coğrafi veritabanlarını depolaması için bir dizin oluşturun.
- .NET Ortamı: Çalışan bir .NET ortamınız olduğundan emin olun.
## Ad Alanlarını İçe Aktar
İşleri başlatmak için gerekli ad alanlarını projenize aktarmanız gerekir. Bu ad alanları Aspose.GIS for .NET ile etkileşim için gerekli sınıfları ve yöntemleri sağlar.
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```
## Adım 1: Nesne Kimliğini ve Geometri Alan Adlarını Belirleyin
Bu adımda GIS verileriniz için Nesne Kimliği ve Geometri alan adlarını nasıl ayarlayacağınızı öğreneceksiniz. Bu, verimli veri yönetimi için çok önemlidir.
## Adım 1.1: Belge Dizinini Ayarlayın
Belge dizininizin yolunu tanımlayarak başlayın:
```csharp
string dataDir = "Your Document Directory";
```
## Adım 1.2: GeoDatabase Oluşturun ve Seçenekleri Tanımlayın
Belirtilen Nesne Kimliği ve Geometri alan adlarıyla bir GeoDatabase oluşturun:
```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Nesne Kimliği alan adını belirtin
        GeometryFieldName = "POINT",       // Geometri alanı adını belirtin
    };
```
## Adım 1.3: Katman Oluşturun ve Ekleyin
GeoDatabase'de bir katman oluşturun ve belirli bir geometriye sahip bir özellik ekleyin:
```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  //Geometriyi belirtin (bu durumda bir nokta)
    layer.Add(feature);
}
```
## Adım 1.4: Katmanı Açın ve Verileri Alın
Katmanı açın ve belirtilen Nesne Kimliğine göre katmandan veri alın:
```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Çıkış: 1
}
```
## Çözüm
Tebrikler! Aspose.GIS for .NET'i kullanarak Nesne Kimliği ve Geometri alan adlarını belirleme sürecini başarıyla tamamladınız. Bu, GIS projeleriniz için sağlam bir temel oluşturarak coğrafi verileri kolaylıkla yönetmenize olanak tanır.
## Sıkça Sorulan Sorular
### S: Aspose.GIS for .NET'i web uygulamalarımda kullanabilir miyim?
C: Evet, Aspose.GIS for .NET hem masaüstü hem de web uygulamaları için uygundur ve çok yönlü coğrafi özellikler sunar.
### S: Satın almadan önce deneme sürümü mevcut mu?
 C: Evet, Aspose.GIS for .NET'in özelliklerini ücretsiz deneme sürümüyle keşfedebilirsiniz[Burada](https://releases.aspose.com/).
### S: Aspose.GIS for .NET için nasıl geçici lisans alabilirim?
 C: Geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/) değerlendirme amaçlı.
### S: Aspose.GIS for .NET hangi mekansal referans sistemlerini destekliyor?
C: Aspose.GIS for .NET, çeşitli mekansal referans sistemlerini destekleyerek farklı coğrafi veri kümeleri için esneklik sağlar.
### S: Nereden yardım isteyebilirim veya Aspose.GIS ile ilgili soruları tartışabilirim?
 C: Aspose.GIS forumunu ziyaret edin[Burada](https://forum.aspose.com/c/gis/33) Destek ve tartışmalar için.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
