---
date: 2026-01-07
description: Aspose.GIS for .NET kullanarak KML dosyası nasıl yazılır, KML nasıl oluşturulur,
  Boolean özniteliği nasıl eklenir ve uygulamalarınızda nasıl bir çizgi dizesi (line
  string) oluşturulur öğrenin.
linktitle: Interact with KML Layer
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET ile KML Dosyası Nasıl Yazılır
url: /tr/net/layer-interaction-and-data-access/interact-with-kml-layer/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET ile KML Dosyası Nasıl Yazılır

## Introduction
Günümüzün veri odaklı dünyasında, **write KML file** işlevini programlı olarak gerçekleştirebilmek, coğrafi bilgileri platformlar arasında paylaşma, haritalarda rotaları görselleştirme ve konum verilerini web ya da mobil uygulamalara entegre etme gücünü size verir. Aspose.GIS for .NET bu süreci basitleştirir, dosya formatı incelikleri yerine mantığa odaklanmanızı sağlar. Bu öğreticide bir KML katmanı oluşturmayı, nitelikler eklemeyi (boolean nitelik dahil) ve bir line string geometrisi inşa etmeyi adım adım net kod örnekleriyle göstereceğiz.

## Quick Answers
- **“write KML file” ne anlama geliyor?** Coğrafi özellikleri (nokta, çizgi, çokgen vb.) tanımlayan bir KML (Keyhole Markup Language) belgesi oluşturmak.  
- **.NET için en iyi kütüphane hangisidir?** Aspose.GIS for .NET, KML dosyaları oluşturmak ve düzenlemek için akıcı bir API sunar.  
- **Geliştirme için lisansa ihtiyacım var mı?** Değerlendirme için ücretsiz deneme sürümü yeterlidir; üretim kullanımı için lisans gereklidir.  
- **Özel nitelikler ekleyebilir miyim?** Evet – her özelliğe string, integer, boolean ve double nitelikler ekleyebilirsiniz.  
- **Geometri oluşturma destekleniyor mu?** Kesinlikle – nokta, line string, çokgen ve daha fazlasını oluşturabilirsiniz.

## Prerequisites
Bu yolculuğa başlamadan önce aşağıdaki ön koşulların sağlandığından emin olun:
- Aspose.GIS for .NET: Kütüphaneyi [Aspose.GIS for .NET indirme sayfasından](https://releases.aspose.com/gis/net/) indirin ve kurun.
- Geliştirme Ortamı: Visual Studio gibi uygun bir geliştirme ortamı kurarak Aspose.GIS'i .NET projelerinize sorunsuz bir şekilde entegre edin.

## Import Namespaces
KML katmanlarıyla etkileşime geçmeden önce projenize gerekli ad alanlarını eklediğinizden emin olun. Bu adım, coğrafi veri manipülasyonu için gereken sınıf ve metodlara erişmenizi sağlar.

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Drawing;
using System.Threading;
using Aspose.Gis.Formats.Kml;
using Aspose.Gis.Formats.Kml.Styles;
using Aspose.Gis.Geometries;
using Point = Aspose.Gis.Geometries.Point;
```

## Step 1: Set the Document Directory
KML dosyalarının saklanacağı belge dizininin yolunu tanımlayın.

```csharp
string dataDir = "Your Document Directory";
```

## Step 2: Create a KML Layer
Aspose.GIS kullanarak bir KML katmanı başlatın ve KML dosyasının yolunu belirtin.

```csharp
using (var layer = Drivers.Kml.CreateLayer(dataDir + "Kml_File_out.kml"))
{
```

## Step 3: Define Attributes (add boolean attribute)
KML katmanına string, integer, **boolean** ve double gibi farklı veri tiplerini temsil eden nitelikler ekleyin. İşte her özelliğe “boolean attribute” eklediğiniz kısım.

```csharp
layer.Attributes.Add(new FeatureAttribute("string_data", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("int_data", AttributeDataType.Integer));
layer.Attributes.Add(new FeatureAttribute("bool_data", AttributeDataType.Boolean));
layer.Attributes.Add(new FeatureAttribute("float_data", AttributeDataType.Double));
```

## Step 4: Construct and Populate Features (create line string)
Coğrafi varlıkları temsil eden özellikler oluşturun ve tanımlanan niteliklere değerler atayın. Burada basit bir yolu göstermek için **create line string** geometrisini oluşturuyoruz.

```csharp
Feature feature = layer.ConstructFeature();
feature.SetValue("string_data", "string value");
feature.SetValue("int_data", 10);
feature.SetValue("bool_data", true);
feature.SetValue("float_data", 3.14);
feature.Geometry = new LineString(new[] { new Point(0, 0), new Point(1, 1) });
layer.Add(feature);
```

## Step 5: Add Another Feature
Farklı nitelik değerleri ve null geometriye sahip ikinci bir özellik eklemek için işlemi tekrarlayın.

```csharp
Feature feature2 = layer.ConstructFeature();
feature2.SetValue("string_data", "string value2");
feature2.SetValue("int_data", 100);
feature2.SetValue("bool_data", false);
feature2.SetValue("float_data", 3.1415);
feature2.Geometry = Geometry.Null;
layer.Add(feature2);
```

## How to Write KML File – Putting It All Together
Yukarıdaki adımları izleyerek artık özel nitelikler (boolean bayrağı dahil) ve bir line string geometrisi içeren tam işlevsel bir KML dosyanız var. Oluşan `Kml_File_out.kml` dosyasını Google Earth, ArcGIS veya KML destekleyen herhangi bir GIS görüntüleyicide açabilirsiniz.

## Common Issues & Troubleshooting
- **Dosya yolu hataları** – `dataDir` değişkeninin işletim sisteminize uygun bir yol ayırıcı (`\\` veya `/`) ile bittiğinden emin olun.  
- **Lisans eksikliği** – Deneme sürümü değerlendirme için çalışır, ancak KML dosyalarının sınırsız yazımı için lisanslı bir sürüm gerekir.  
- **Null geometri** – `Geometry.Null` ayarı, uzamsal veri olmayan özellikler için kasıtlıdır; her zaman geometriye ihtiyaç duyuyorsanız bu ayarı kaldırın.

## Frequently Asked Questions
### Aspose.GIS diğer GIS formatlarıyla uyumlu mu?
Evet, Aspose.GIS shapefile, GeoJSON ve KML dahil olmak üzere çeşitli GIS formatlarını destekler.

### Aspose.GIS ile oluşturulan coğrafi verileri görselleştirebilir miyim?
Kesinlikle! Aspose.GIS harita kütüphaneleriyle sorunsuz bir şekilde entegre olur ve coğrafi verilerinizi görselleştirmenizi sağlar.

### Aspose.GIS için bir deneme sürümü mevcut mu?
Evet, Aspose.GIS'in özelliklerini keşfetmek için [free trial version](https://releases.aspose.com/) indirebilirsiniz.

### Aspose.GIS için destek nasıl alabilirim?
Topluluk desteği için [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) adresini ziyaret edin veya premium destek seçeneklerini [buradan](https://purchase.aspose.com/buy) inceleyin.

### Aspose.GIS için geçici lisanslar mevcut mu?
Evet, geçici bir lisansı [buradan](https://purchase.aspose.com/temporary-license/) alabilirsiniz.

## Additional Frequently Asked Questions

**Q: How do I **how to create KML** files with custom styling?**  
A: `Aspose.Gis.Formats.Kml.Styles` ad alanını kullanarak özellik eklemeden önce simgeler, çizgi renkleri ve etiket stilleri tanımlayın.

**Q: Can I write large KML files efficiently?**  
A: Özellikleri toplu olarak yazın ve katmanı periyodik olarak flush ederek bellek kullanımını düşük tutun.

**Q: Does Aspose.GIS support .NET Core and .NET 6+?**  
A: Evet, kütüphane .NET Core, .NET 5 ve .NET 6 ile tam uyumludur.

---

**Last Updated:** 2026-01-07  
**Tested With:** Aspose.GIS 24.10 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}