---
date: 2026-01-13
description: Aspose.GIS for .NET ile yeni bir shapefile oluşturmayı öğrenin. Bu adım
  adım kılavuz, vektör katmanını nasıl tanımlayacağınızı, tarih özniteliği ekleyeceğinizi
  ve mekânsal verileri nasıl yöneteceğinizi gösterir.
linktitle: Create New Shapefile
second_title: Aspose.GIS .NET API
title: Yeni Shapefile Oluştur
url: /tr/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Yeni Shapefile Oluştur

## Introduction
Geographic information systems (GIS) geliştirmesine .NET ile dalıyorsanız, Aspose.GIS sizin başvuracağınız çözümdür. Bu güçlü kütüphane, geliştiricilerin mekansal verilerle sorunsuz çalışmasını sağlar ve bu öğreticide, Aspose.GIS for .NET kullanarak **yeni shapefile oluşturmayı** adım adım göstereceğiz. Vektör katmanı tanımlamanın ve tarih özniteliği eklemenin sağlam GIS projeleri için neden önemli adımlar olduğunu göreceksiniz.

## Quick Answers
- **Bu öğretici ne öğretir?** Yeni bir shapefile oluşturmayı, bir vektör katmanı tanımlamayı ve öznitelikler eklemeyi (tarih alanı dahil) öğretir.  
- **Hangi kütüphane gereklidir?** Aspose.GIS for .NET.  
- **Lisans gerekli mi?** Öğrenme için ücretsiz deneme yeterlidir; üretim için ticari lisans gereklidir.  
- **Hangi IDE kullanılmalı?** Visual Studio (herhangi bir yeni sürüm).  
- **Uygulama ne kadar sürer?** Temel örnek için yaklaşık 10‑15 dakika.

## Prerequisites
Öğreticiye başlamadan önce aşağıdaki ön koşulların sağlandığından emin olun:
- C# programlama diline temel bir anlayış.
- Makinenizde Visual Studio yüklü.
- Aspose.GIS for .NET kütüphanesi. Bunu [buradan](https://releases.aspose.com/gis/net/) indirebilirsiniz.

## Import Namespaces
Aspose.GIS işlevselliğinden yararlanmak için gerekli ad alanlarını (namespaces) içe aktararak başlayın:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Step 1: Set Up Your Project
Visual Studio'da yeni bir C# projesi oluşturarak ve Aspose.GIS kütüphanesini ekleyerek başlayın.

## Step 2: Define the Document Directory
```csharp
string dataDir = "Your Document Directory";
```
*Your Document Directory* ifadesini yeni shapefile'inizi kaydetmek istediğiniz gerçek yol ile değiştirin.

## Step 3: Create a VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
Bu kod bölümü **bir vektör katmanı tanımlar** ve üç öznitelik bildirir: bir metin alanı (`name`), bir tam sayı alanı (`age`) ve bir tarih‑zaman alanı (`dob`). Tarih özniteliği eklemek, zamansal GIS analizleri için kritik öneme sahiptir.

## Step 4: Add Features
### Case 1: Sets Values Individually
```csharp
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
firstFeature.SetValue("dob", new DateTime(1982, 2, 5, 16, 30, 0));
layer.Add(firstFeature);
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
secondFeature.SetValue("dob", new DateTime(1984, 12, 15, 15, 30, 0));
layer.Add(secondFeature);
```
Burada iki nokta oluşturuyor, her özniteliği ayrı ayrı ayarlıyor ve özellikleri katmana ekliyoruz.

### Case 2: Sets New Values for All Attributes
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
Bu yöntemde, bir nesne dizisi kullanarak tüm öznitelik değerlerini tek bir çağrıda dolduruyoruz—çok sayıda özniteliğiniz olduğunda kullanışlıdır.

## Why This Matters
Programatik olarak shapefile oluşturmak, veri boru hatlarını otomatikleştirmenize, test veri setleri oluşturmanıza veya GIS çıktısını doğrudan web hizmetlerine entegre etmenize olanak tanır. Aspose.GIS ile **shapefile oluşturmayı** ustalaşarak, özellik geometrisi, öznitelik şeması ve dosya formatı uyumluluğu üzerinde tam kontrol elde edersiniz.

## Common Pitfalls & Tips
- **Yol ayırıcıları:** Dize birleştirme yerine çapraz platform uyumluluğu için `Path.Combine` kullanın.  
- **Öznitelik sırası:** `SetValues` içindeki değerlerin sırası, eklediğiniz özniteliklerin sırası ile aynı olmalıdır.  
- **Tarih işleme:** GIS verileriniz zaman dilimleri arasında paylaşılacaksa her zaman `DateTimeKind.Utc` kullanın.

## Conclusion
Tebrikler! Aspose.GIS for .NET kullanarak yeni bir shapefile'i başarıyla oluşturdunuz. Bu öğreticide projenizi kurma, bir vektör katmanı tanımlama ve özellik ekleme (tarih özniteliği dahil) temelleri ele alındı. Daha fazla keşfederken, gelişmiş özellikler ve işlevsellikler için [belgelere](https://reference.aspose.com/gis/net/) başvurun.

## Frequently Asked Questions
### Q: Can I use Aspose.GIS with other programming languages?
Aspose.GIS öncelikle .NET'i destekler, ancak Java için de sürümleri mevcuttur.  

### Q: Is there a free trial available?
Evet, ücretsiz deneme sürümüne [buradan](https://releases.aspose.com/) ulaşabilirsiniz.  

### Q: Where can I find support for Aspose.GIS?
Topluluk desteği ve tartışmalar için [Aspose.GIS forumunu](https://forum.aspose.com/c/gis/33) ziyaret edin.  

### Q: How can I obtain a temporary license?
Geçici lisansınızı [buradan](https://purchase.aspose.com/temporary-license/) edinin.  

### Q: Where can I purchase Aspose.GIS for .NET?
Kütüphaneyi [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

---

**Last Updated:** 2026-01-13  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}