---
title: Gruplama ile GeoJSON'u TopoJSON'a dönüştürün
linktitle: Gruplama ile GeoJSON'u TopoJSON'a dönüştürün
second_title: Aspose.GIS .NET API'si
description: Bu kapsamlı eğitimde Aspose.GIS for .NET kullanarak GeoJSON'u gruplamayla TopoJSON'a nasıl dönüştüreceğinizi öğrenin.
type: docs
weight: 13
url: /tr/net/geo-data-conversion/convert-geojson-to-topojson-with-grouping/
---
## giriiş

Gruplamayla GeoJSON'u TopoJSON'a dönüştürmek için Aspose.GIS for .NET'i kullanmayla ilgili adım adım kılavuzumuza hoş geldiniz. Aspose.GIS, geliştiricilerin coğrafi verilerle sorunsuz bir şekilde çalışmasına olanak tanıyan güçlü bir .NET API'sidir. Bu eğitimde, özellikleri belirtilen niteliklere göre gruplandırırken GeoJSON dosyalarını TopoJSON'a dönüştürme sürecinde size yol göstereceğiz.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

1.  Aspose.GIS for .NET: Aspose.GIS for .NET kitaplığını indirip yüklediğinizden emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/gis/net/).

2. Geliştirme Ortamı: Visual Studio veya başka bir uyumlu IDE ile kurulmuş bir çalışma geliştirme ortamınız olmalıdır.

3. Örnek GeoJSON Dosyası: Dönüştürmek istediğiniz örnek bir GeoJSON dosyası hazırlayın. Örnek GeoJSON dosyalarını çeşitli kaynaklardan edinebilir veya kendinizinkini oluşturabilirsiniz.

## Ad Alanlarını İçe Aktar

Öncelikle projenize gerekli ad alanlarını eklediğinizden emin olun:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
```


Şimdi dönüştürme sürecini birden çok adıma ayıralım:

## 1. Adım: Dosya Yollarını Tanımlayın

Giriş GeoJSON dosyanızın ve çıkış TopoJSON dosyanızın yollarını tanımlayın:

```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithGrouping_out.topojson";
```

 Yer değiştirmek`"Your Document Directory"` dosyalarınızın bulunduğu gerçek dizinle.

## 2. Adım: Dönüşüm Seçeneklerini Yapılandırın

Gruplandırmanın nasıl gerçekleştirileceğini belirtmek için dönüştürme seçeneklerini yapılandırın. Bu örnekte özellikleri belirli bir özelliğe göre gruplandıracağız.

```csharp
var options = new ConversionOptions
{
    DestinationDriverOptions = new TopoJsonOptions
    {
        // GeoJSON katmanında nesnelere göre gruplandıracağımız özelliği belirtin
        ObjectNameAttribute = "group",
        // Bilinmeyen öznitelik değerlerine sahip özellikler için varsayılan nesne adını belirtin
        DefaultObjectName = "unnamed",
    }
};
```

 Ayarlayın`ObjectNameAttribute` Ve`DefaultObjectName` GeoJSON verilerinize göre özellikler.

## 3. Adım: Dönüşümü Gerçekleştirin

Aspose.GIS API'yi kullanarak dönüştürme sürecini yürütün:

```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```

Bu kod satırı, GeoJSON dosyasını belirtilen gruplama seçenekleriyle TopoJSON'a dönüştürecektir.

## Çözüm

Bu eğitimde Aspose.GIS for .NET kullanarak GeoJSON'u gruplamayla TopoJSON'a nasıl dönüştüreceğimizi öğrendik. Bu basit adımları izleyerek .NET uygulamalarınızda coğrafi veri formatlarını verimli bir şekilde kullanabilirsiniz.

## SSS'ler

### S1: Özellikleri birden çok özelliğe göre gruplayabilir miyim?
C: Evet, özellikleri birden çok özelliğe göre gruplandırmak için dönüştürme seçeneklerini özelleştirebilirsiniz.

### S2: Aspose.GIS .NET Core ile uyumlu mu?
C: Evet, Aspose.GIS geleneksel .NET Framework'ün yanı sıra .NET Core'u da destekler.

### S3: Aspose.GIS'i kullanarak diğer coğrafi veri formatlarını dönüştürebilir miyim?
C: Evet, Aspose.GIS, GeoJSON ve TopoJSON'un ötesinde çeşitli coğrafi veri formatları için destek sağlar.

### S4: Aspose.GIS ücretsiz deneme sunuyor mu?
 C: Evet, Aspose.GIS'in ücretsiz deneme sürümünü şu adresten edinebilirsiniz:[Burada](https://releases.aspose.com/).

### S5: Aspose.GIS için nereden destek alabilirim?
 C: Aspose.GIS topluluk forumundan destek alabilirsiniz.[Burada](https://forum.aspose.com/c/gis/33).