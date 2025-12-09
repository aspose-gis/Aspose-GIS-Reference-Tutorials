---
date: 2025-11-30
description: Aspose.GIS for .NET kullanarak belirli bir nesne adıyla GeoJSON'u TopoJSON'a
  nasıl dönüştüreceğinizi öğrenin – Aspose GIS dönüşümü için kapsamlı bir rehber.
linktitle: How to Convert GeoJSON to TopoJSON with Specific Object Name
second_title: Aspose.GIS .NET API
title: GeoJSON'ı Belirli Bir Nesne Adı ile TopoJSON'a Nasıl Dönüştürülür
url: /tr/net/geo-data-conversion/convert-geojson-to-topojson-with-specific-object-name/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GeoJSON'u Belirli Bir Nesne Adı ile TopoJSON'a Nasıl Dönüştürülür

## Introduction
Bu öğreticide **GeoJSON** dosyalarını **Aspose.GIS for .NET** kullanarak özel bir nesne adı atayarak TopoJSON'a nasıl dönüştüreceğinizi keşfedeceksiniz. Haritalama servisi oluşturuyor, web görselleştirmeleri için veri hazırlıyor ya da çıktının nesnesini yeniden adlandırmanın temiz bir yoluna ihtiyacınız varsa, bu adım‑adım kılavuz tam olarak ne yapmanız gerektiğini gösterir.

## Quick Answers
- **Dönüştürme ne yapar?** Bir GeoJSON özellik koleksiyonunu TopoJSON topolojisine dönüştürür ve kök nesne adını ayarlamanıza izin verir.  
- **Hangi kütüphane dönüşümü gerçekleştirir?** Aspose.GIS for .NET (Aspose GIS dönüşüm paketinin bir parçası).  
- **Lisans gerekli mi?** Test için ücretsiz deneme sürümü çalışır; üretim için ticari lisans gerekir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Uygulama ne kadar sürer?** Ortam hazır olduğunda yaklaşık 5‑10 dakika.

## What is “convert GeoJSON to TopoJSON”?
GeoJSON'u TopoJSON'a dönüştürmek, standart bir GeoJSON özellik koleksiyonunu TopoJSON topolojisi olarak kodlamak anlamına gelir. TopoJSON, geometri kenarlarını paylaşarak dosya boyutunu azaltır ve Aspose.GIS ile **DefaultObjectName** belirleyerek çıktının istediğiniz adla adlandırılmış bir nesne içermesini sağlar.

## Why use Aspose.GIS .NET for this conversion?
- **Sağlam API** – Büyük veri setlerini ve karmaşık geometrileri manuel ayrıştırma olmadan işler.  
- **Yerleşik dönüşüm seçenekleri** – Nesne adlarını, koordinat hassasiyetini ve daha fazlasını doğrudan ayarlayabilirsiniz.  
- **Çapraz platform** – Masaüstü uygulamalardan bulut hizmetlerine kadar herhangi bir .NET ortamında çalışır.  
- **Kapsamlı destek** – Düzenli güncellemeler ve belgeler sunan Aspose GIS dönüşüm ailesinin bir parçasıdır.

## Prerequisites
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

### 1. Install Aspose.GIS for .NET
Aspose.GIS for .NET'i kurun  
[download page](https://releases.aspose.com/gis/net/) adresine gidin ve Aspose.GIS for .NET'in en son sürümünü indirin.

### 2. Set Up Your Development Environment
Geliştirme ortamınızı kurun  
Visual Studio, Rider veya herhangi bir .NET uyumlu IDE çalışır. Projenizin .NET Framework 4.5+ veya .NET Core 3.1+ hedeflediğinden emin olun.

### 3. Prepare a GeoJSON File
Bir GeoJSON dosyası hazırlayın  
Dönüştürmek istediğiniz bir GeoJSON dosyanız olsun. Yoksa basit bir tane oluşturabilir ya da bu öğretici için herhangi bir örnek GeoJSON dosyasını kullanabilirsiniz.

## Import Namespaces
İsim alanlarını içe aktarın  
Dönüştürme işlemine başlamadan önce gerekli isim alanlarını içe aktaralım:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Step‑by‑Step Guide

### Step 1: Define File Paths
```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithObjectName_out.topojson";
```
`"Your Document Directory"` ifadesini, giriş GeoJSON dosyanızın bulunduğu ve TopoJSON sonucunun kaydedileceği gerçek klasörle değiştirin.

### Step 2: Set Conversion Options (Aspose GIS conversion)
```csharp
var options = new ConversionOptions
{
    DestinationDriverOptions = new TopoJsonOptions
    {
        // specify the name of the object where features should be written
        DefaultObjectName = "name_of_the_object",
    }
};
```
Burada bir `ConversionOptions` örneği oluşturup `DefaultObjectName` ayarlıyoruz. Bu, Aspose.GIS'e oluşturulan TopoJSON dosyasında tüm özellikleri **name_of_the_object** adlı nesne altında yazmasını söyler.

### Step 3: Perform the Conversion (convert geojson to topojson)
```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```
`VectorLayer.Convert` yöntemi işi halleder: kaynak GeoJSON'u okur, yukarıda tanımlanan seçenekleri uygular ve özel nesne adıyla bir TopoJSON dosyası yazar.

## Common Issues & Tips
- **Yol Hataları** – Dizin dizgilerinin bir yol ayırıcı (`\` veya `/`) ile bittiğinden emin olun ya da güvenlik için `Path.Combine` kullanın.  
- **Büyük Dosyalar** – Çok büyük GeoJSON dosyaları için işlem belleği limitini artırmayı veya veriyi akış olarak işlemeyi düşünün.  
- **Nesne Adı Çakışmaları** – `DefaultObjectName` TopoJSON dosyası içinde benzersiz olmalıdır; aksi takdirde mevcut nesneler üzerine yazılabilir.

## Conclusion
Artık Aspose.GIS for .NET kullanarak **belirli bir nesne adıyla GeoJSON'u TopoJSON'a nasıl dönüştüreceğinizi** biliyorsunuz. Bu teknik, web haritaları için veri hazırlamayı kolaylaştırır, dosya boyutunu azaltır ve çıktının topolojisinin yapısı üzerinde tam kontrol sağlar.

## Frequently Asked Questions

**S: Aspose.GIS for .NET'i ticari projelerde kullanabilir miyim?**  
C: Evet, geçerli bir lisansla Aspose.GIS for .NET hem ticari hem de kişisel uygulamalarda kullanılabilir.

**S: Aspose.GIS for .NET için ücretsiz deneme sürümü mevcut mu?**  
C: Evet, [buradan](https://releases.aspose.com/) ücretsiz deneme alabilirsiniz.

**S: Aspose.GIS for .NET için desteği nereden bulabilirim?**  
C: Destek, [Aspose.GIS forumu](https://forum.aspose.com/c/gis/33) üzerinden sağlanmaktadır.

**S: Aspose.GIS for .NET lisansını nasıl satın alabilirim?**  
C: Lisansları [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

**S: Değerlendirme için geçici bir lisansa ihtiyacım var mı?**  
C: Evet, geçici değerlendirme lisansı [buradan](https://purchase.aspose.com/temporary-license/) temin edilebilir.

---

**Last Updated:** 2025-11-30  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}