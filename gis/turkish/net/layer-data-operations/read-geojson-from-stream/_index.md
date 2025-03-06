---
title: Aspose.GIS for .NET ile GeoJSON'u Akıştan Okumak
linktitle: Akıştan GeoJSON'u okuyun
second_title: Aspose.GIS .NET API'si
description: Aspose.GIS for .NET kullanarak GeoJSON'u bir akıştan nasıl okuyacağınızı öğrenin. Jeouzamsalın uygulamalarınıza kusursuz entegrasyonu için adım adım kılavuzumuzu izleyin.
weight: 14
url: /tr/net/layer-data-operations/read-geojson-from-stream/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET ile GeoJSON'u Akıştan Okumak

## giriiş
Bir akıştan GeoJSON'u okumak için Aspose.GIS for .NET kullanımına ilişkin adım adım kılavuzumuza hoş geldiniz. Aspose.GIS, .NET uygulamalarına coğrafi özellikler sağlayan, çeşitli GIS formatlarıyla sorunsuz bir şekilde çalışmanıza olanak tanıyan güçlü bir API'dir. Bu eğitimde, Aspose.GIS kullanarak bir akıştan GeoJSON verilerini okuma sürecinde size yol göstereceğiz ve netlik ve anlama kolaylığı için her adımı parçalara ayıracağız.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. Temel C# Bilgisi: C# programlama diline ve sözdizimine aşina olmalısınız.
2.  Aspose.GIS Kurulumu: Aspose.GIS for .NET'i yüklediğinizden emin olun. Değilse, adresinden indirebilirsiniz.[Burada](https://releases.aspose.com/gis/net/).
3. Geliştirme Ortamı: Visual Studio veya JetBrains Rider gibi tercih ettiğiniz geliştirme ortamını kurun.

## Ad Alanlarını İçe Aktar
Başlamak için gerekli ad alanlarını C# kodunuza aktaralım:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## 1. Adım: GeoJSON Verilerini Tanımlayın
Öncelikle GeoJSON verilerini C# kodumuzda string olarak tanımlamamız gerekiyor. Örneğin:
```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```
## Adım 2: GeoJSON'u Akıştan Okuyun
Daha sonra Aspose.GIS kullanarak bir akıştan GeoJSON verilerini okuyacağız:
```csharp
using (var memoryStream = new MemoryStream(Encoding.UTF8.GetBytes(geoJson)))
using (var layer = VectorLayer.Open(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    Console.WriteLine(layer.Count); // Çıkış: 2
    Console.WriteLine(layer[1].GetValue<string>("name")); // Çıktı: Meryem
}
```

## Çözüm
Bu eğitimde Aspose.GIS for .NET kullanarak GeoJSON verilerini bir akıştan nasıl okuyacağımızı öğrendik. Yukarıda özetlenen adımları takip ederek, coğrafi yetenekleri .NET uygulamalarınıza zahmetsizce entegre edebilirsiniz.
## SSS'ler
### Aspose.GIS diğer GIS formatlarıyla uyumlu mu?
Evet, Aspose.GIS, GeoJSON, Shapefile, KML ve daha fazlası gibi çeşitli GIS formatlarını destekler.
### Satın almadan önce Aspose.GIS'i deneyebilir miyim?
 Evet, Aspose.GIS'in ücretsiz deneme sürümünü şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/).
### Aspose.GIS belgelerini nerede bulabilirim?
 Aspose.GIS belgelerini burada bulabilirsiniz[Burada](https://reference.aspose.com/gis/net/).
### Aspose.GIS için nasıl destek alabilirim?
 Aspose forumlarından Aspose.GIS için destek alabilirsiniz[Burada](https://forum.aspose.com/c/gis/33).
### Aspose.GIS'i kullanmak için geçici bir lisansa ihtiyacım var mı?
 Aspose.GIS için geçici bir lisansı şu adresten alabilirsiniz:[Burada](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
