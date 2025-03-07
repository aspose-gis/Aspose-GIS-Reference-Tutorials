---
title: GeoJSON, GDB Dönüşümünün Gizemini Açıklayacak
linktitle: GeoJSON Katmanını Dosya GDB'ye Dönüştür
second_title: Aspose.GIS .NET API'si
description: Aspose.GIS for .NET ile coğrafi harikaların kilidini açın! GeoJSON katmanlarını zahmetsizce Dosya Coğrafi Veritabanlarına dönüştürün. Şimdi dene! #Aspose #GIS
weight: 17
url: /tr/net/layer-management/convert-geojson-layer-to-file-gdb/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GeoJSON, GDB Dönüşümünün Gizemini Açıklayacak

## giriiş
Coğrafi Bilgi Sistemlerinin (GIS) dinamik alanında, verileri farklı formatlar arasında sorunsuz bir şekilde dönüştürme yeteneği çok önemlidir. Aspose.GIS for .NET, coğrafi verilerin zahmetsizce işlenmesi için kapsamlı bir araç paketi sunan güçlü bir müttefik olarak ortaya çıkıyor. Bu eğitimde, Aspose.GIS for .NET kullanarak bir GeoJSON katmanını Dosya Geodatabase'ine (Dosya GDB) dönüştürme sürecini derinlemesine inceleyeceğiz.
## Önkoşullar
Bu jeouzaysal yolculuğa çıkmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
- .NET programlama konusunda çalışma bilgisi.
-  Aspose.GIS for .NET kuruldu. Değilse, şuradan indirin:[Burada](https://releases.aspose.com/gis/net/) ve kurulum talimatlarını takip edin.
## Ad Alanlarını İçe Aktar
Dönüştürme sürecini başlatmak için gerekli ad alanlarını içe aktararak başlayın:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
Şimdi süreci adım adım kılavuza ayıralım:
## 1. Adım: GeoJSON Katmanını ayarlayın
İlgili nitelik ve özelliklere sahip bir GeoJSON katmanı oluşturarak başlayın. İşte size yol gösterecek bir pasaj:
```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    // Nitelik ekle
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    //Özellik oluşturma ve ekleme
    Feature firstFeature = layer.ConstructFeature();
    firstFeature.Geometry = new Point(33.97, -118.25);
    firstFeature.SetValue("name", "John");
    firstFeature.SetValue("age", 23);
    layer.Add(firstFeature);
    Feature secondFeature = layer.ConstructFeature();
    secondFeature.Geometry = new Point(35.81, -96.28);
    secondFeature.SetValue("name", "Mary");
    secondFeature.SetValue("age", 54);
    layer.Add(secondFeature);
}
```
## Adım 2: Test Veri Kümesini Kopyalayın
Test verilerinizin bütünlüğünü korumak için veri kümesinin bir kopyasını oluşturun. Aşağıdaki kod parçacığını kullanın:
```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```
## Adım 3: GeoJSON'u Dosya GDB'ye Dönüştürün
Şimdi dönüşümü gerçekleştirmenin zamanı geldi. Aşağıdaki kodu kullanın:
```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        // Nitelikleri kopyala
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        // Özellik ekle
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```
## Çözüm
Bu eğitimde, Aspose.GIS for .NET'i kullanarak bir GeoJSON katmanını Dosya Geodatabase'ine dönüştürmenin ilgi çekici alanında gezindik. Bu bilgiyle donanmış olarak artık .NET uygulamalarınızdaki coğrafi verileri sorunsuz bir şekilde yönetebilecek donanıma sahipsiniz.
## SSS
### Aspose.GIS en son .NET çerçevesiyle uyumlu mu?
Evet, Aspose.GIS en son .NET framework sürümleriyle uyumludur.
### Aspose.GIS'i kullanarak diğer coğrafi formatları dönüştürebilir miyim?
Kesinlikle! Aspose.GIS, çok yönlü veri manipülasyonu için çok çeşitli coğrafi formatları destekler.
### Aspose.GIS'in deneme sürümü mevcut mu?
 Evet, deneme sürümünü indirerek Aspose.GIS'in işlevlerini keşfedebilirsiniz.[Burada](https://releases.aspose.com/).
### Aspose.GIS ile ilgili sorgular için nasıl destek alabilirim?
 Aspose.GIS'e gidin[forum](https://forum.aspose.com/c/gis/33) özel destek için.
### Aspose.GIS için geçici lisans alabilir miyim?
 Evet, geçici bir lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
