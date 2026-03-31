---
date: 2025-12-28
description: Aspose.GIS for .NET kullanarak bir akıştan GeoJSON nasıl okunur öğrenin.
  Bu C# GeoJSON okuma rehberi, coğrafi veri entegrasyonu için adım adım bir örnek
  sunar.
linktitle: Read GeoJSON from Stream
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET ile Akıştan GeoJSON Nasıl Okunur
url: /tr/net/layer-data-operations/read-geojson-from-stream/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET için Aspose.GIS ile Akıştan GeoJSON Okuma

## Giriş
Bir .NET uygulamasında **geojson nasıl okunur** diye merak ediyorsanız, doğru yerdesiniz. Bu öğreticide, bir GeoJSON dizesini dönüştürmeyi, bir bellek akışından GeoJSON katmanını açmayı ve Aspose.GIS kullanarak GeoJSON özelliklerini çıkarmayı gösteren eksiksiz bir **c# geojson örneği** üzerinden ilerleyeceğiz. Sonunda, coğrafi veriyle çalışması gereken herhangi bir projeye ekleyebileceğiniz yeniden kullanılabilir bir desen elde edeceksiniz.

## Hızlı Yanıtlar
- **Hangi kütüphaneyi kullanmalıyım?** Aspose.GIS for .NET  
- **GeoJSON'u doğrudan bir akıştan okuyabilir miyim?** Evet – `VectorLayer.Open` ile `AbstractPath.FromStream` kullanın.  
- **Geliştirme için lisansa ihtiyacım var mı?** Test için ücretsiz deneme çalışır; üretim için lisans gere  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Özellikleri çıkarmak basit mi?** Evet – bir özellik üzerinde `GetValue<T>(columnName)` çağırın.

## “geojson nasıl okunur” nedir?
GeoJSON okuma, coğrafi özellikleri (nokta, çizgi, çokgen) tanımlayan JSON tabanlı formatı ayrıştırmak ve bu özellikleri uygulamanızda sorgulayabileceğiniz, düzenleyebileceğiniz veya render edebileceğiniz nesneler olarak kullanılabilir hâle getirmek anlamına gelir.

## Aspose.GIS'i **geojson katmanı açmak** için neden kullanmalısınız?
Aspose.GIS, düşük seviyeli ayrıştırma detaylarını soyutlar ve birçok GIS formatı için tutarlı bir API sunar. **geojson katmanı** doğrudan bir akıştan açmanıza, büyük dosyaları verimli bir şekilde işlemenize ve özel JSON ayrıştırıcıları yazmadan özellik niteliklerine erişmenize olanak tanır.

## Önkoşullar
1. **C# temel bilgisi** – .NET sözdizimi ve Visual Studio IDE'sine aşina olmalısınız.  
2. **Aspose.GIS yüklü** – kütüphaneyi [buradan](https://releases.aspose.com/gis/net/) indirin.  
3. **Bir geliştirme ortamı** – Visual Studio, Visual Studio Code veya JetBrains Rider kullanılabilir.  

## Ad Alanlarını İçe Aktarın
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## Adım 1: **GeoJSON dizesini dönüştür** – bir **c# geojson örneği**
İlk olarak, basit bir `FeatureCollection` temsil eden bir JSON dizesi oluşturuyoruz. Bu, iş akışının **convert geojson string** kısmıdır.

```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```

## Adım 2: Akıştan **GeoJSON katmanı aç** ve **geojson özelliklerini çıkar**
Şimdi dizeyi bir `MemoryStream` içine aktararak bir GIS katmanı olarak açıyoruz ve öznitelik değerlerini okumanın nasıl yapılacağını gösteriyoruz (**extract geojson properties** adımı).

```csharp
using (var memoryStream = new MemoryStream(Encoding.UTF8.GetBytes(geoJson)))
using (var layer = VectorLayer.Open(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    Console.WriteLine(layer.Count); // Output: 2
    Console.WriteLine(layer[1].GetValue<string>("name")); // Output: Mary
}
```

> **Pro ipucu:** `VectorLayer.Open`, `Drivers.GeoJson` geçirdiğinizde GeoJSON formatını otomatik olarak algılar. Ayrıca bir akış yerine dosya yolu sağlayarak dosyaları doğrudan açabilirsiniz.

## Yaygın Sorunlar ve Çözümler
| Sorun | Çözüm |
|-------|----------|
| **Geçersiz JSON formatı** | GeoJSON dizesinin doğru biçimlendiğini doğrulayın; bir JSON doğrulayıcı kullanın. |
| **Kodlama sorunları** | Akışın UTF-8 kullandığından emin olun (`Encoding.UTF8.GetBytes`). |
| **Eksik özellikler** | Özellik adının doğru yazıldığını kontrol edin (`"name"` örnekte). |
| **Lisans istisnası** | Test için deneme lisansı kullanın; üretim için kalıcı lisans uygulayın. |

## Sık Sorulan Sorular
### Aspose.GIS diğer GIS formatlarıyla uyumlu mu?
Evet, Aspose.GIS GeoJSON, Shapefile, KML, GML ve daha birçok formatı destekler.

### Aspose.GIS'i satın almadan önce deneyebilir miyim?
Evet, Aspose.GIS'in ücretsiz denemesini [buradan](https://releases.aspose.com/) indirebilirsiniz.

### Aspose.GIS belgelerini nerede bulabilirim?
Aspose.GIS belgelerini [burada](https://reference.aspose.com/gis/net/) bulabilirsiniz.

### Aspose.GIS için destek nasıl alabilirim?
Aspose.GIS için desteği Aspose forumlarından [burada](https://forum.aspose.com/c/gis/33) alabilirsiniz.

### Aspose.GIS'i kullanmak için geçici bir lisansa ihtiyacım var mı?
Aspose.GIS için geçici bir lisansı [buradan](https://purchase.aspose.com/temporary-license/) edinebilirsiniz.

## Sonuç
Bu rehberde, .NET için Aspose.GIS kullanarak bir bellek akışından **geojson nasıl okunur** konusunu ele aldık, bir **c# read geojson** iş akışını gösterdik ve açılan katmandan **geojson özelliklerini çıkarmanın** nasıl yapılacağını gösterdik. Bu adımlarla, coğrafi veri işleme yeteneğini herhangi bir .NET uygulamasına sorunsuz bir şekilde entegre edebilirsiniz.

---

**Last Updated:** 2025-12-28  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}