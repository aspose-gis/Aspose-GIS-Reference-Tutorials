---
date: 2025-11-29
description: Aspose.GIS for .NET kullanarak belirli bir nesne adıyla GeoJSON'u TopoJSON'a
  nasıl dönüştüreceğinizi öğrenin. Bu adım adım kılavuz, GeoJSON'u TopoJSON'a verimli
  bir şekilde nasıl dönüştüreceğinizi tam olarak gösterir.
language: tr
linktitle: Convert GeoJSON to TopoJSON with Specific Object Name
second_title: Aspose.GIS .NET API
title: GeoJSON'u Belirli Bir Nesne Adı ile TopoJSON'a Dönüştür
url: /net/geo-data-conversion/convert-geojson-to-topojson-with-specific-object-name/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GeoJSON'u Belirli Nesne Adı ile TopoJSON'a Dönüştürme

## Giriş
Çıktı nesnesinin adını kontrol ederken **GeoJSON'u TopoJSON'a dönüştürmeniz** gerekiyorsa, Aspose.GIS for .NET bu işlemi çok kolaylaştırır. Bu öğreticide GeoJSON'u TopoJSON'a nasıl dönüştüreceğinizi, neden özel bir nesne adı isteyebileceğinizi ve kodu mevcut .NET projelerinize nerede ekleyeceğinizi tam olarak göreceksiniz.

## Hızlı Yanıtlar
- **Dönüştürme ne yapar?** GeoJSON özelliklerini bir TopoJSON topolojisine yeniden yazar, isteğe bağlı olarak kök nesnenin adını değiştirir.  
- **Uygulama ne kadar sürer?** Aspose.GIS yüklendikten sonra yaklaşık 5‑10 dakika.  
- **Lisans gerekir mi?** Test için ücretsiz deneme çalışır; üretim için ticari lisans gereklidir.  
- **Hangi .NET sürümleri desteklenir?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Nesne adını belirtebilir miyim?** Evet – `TopoJsonOptions` içinde `DefaultObjectName` kullanın.

## “GeoJSON'u TopoJSON'a Dönüştürmek” nedir?
`convert geojson to topojson` bir GeoJSON dosyasını (coğrafi özelliklerin düz‑JSON temsili) TopoJSON'a dönüştürme sürecidir; TopoJSON, ortak çizgi segmentlerini yaylar (arc) olarak saklayan daha kompakt bir formattır. Bu, dosya boyutunu azaltır ve web haritalarının render performansını artırır.

## GeoJSON'u TopoJSON'a Dönüştürmek için Aspose.GIS for .NET Neden Kullanılmalı?
- **Tam .NET entegrasyonu** – harici CLI araçları gerekmez.  
- **İnce ayarlı kontrol** – çıktı nesne adını, koordinat hassasiyetini ve daha fazlasını ayarlayabilirsiniz.  
- **Çapraz platform** – .NET Core/.NET 5+ ile Windows, Linux ve macOS'ta çalışır.  
- **Sağlam hata yönetimi** – giriş GeoJSON'unun yerleşik doğrulaması ve ayrıntılı istisnalar.

## Önkoşullar
Dönüştürmeye başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. **Aspose.GIS for .NET** – en son sürümü [resmi indirme sayfasından](https://releases.aspose.com/gis/net/) indirin.  
2. **Bir .NET geliştirme ortamı** – Visual Studio, Rider veya C# uzantılı VS Code.  
3. **Bir kaynak GeoJSON dosyası** – TopoJSON'a dönüştürmek istediğiniz geçerli bir GeoJSON dosyası.

## Ad Alanlarını İçe Aktarın
İlk olarak, gerekli ad alanlarını kapsam içine alın:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Adım‑Adım Kılavuz

### Adım 1: Dosya Yollarını Tanımlayın
API'ye kaynak GeoJSON dosyanızın nerede olduğunu ve dönüştürülen TopoJSON'ın nereye kaydedileceğini söyleyin.

```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithObjectName_out.topojson";
```

> **Pro ipucu:** Platform bağımsız yol oluşturmak için `Path.Combine` kullanın.

### Adım 2: Dönüştürme Seçeneklerini Ayarlayın (Özel bir nesne adıyla GeoJSON'u TopoJSON'a nasıl dönüştürülür)
Bir `ConversionOptions` örneği oluşturun ve istediğiniz nesne adını `TopoJsonOptions.DefaultObjectName` aracılığıyla belirtin.

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

Bu, Aspose.GIS'e tüm özellikleri sonuç TopoJSON dosyasındaki `"name_of_the_object"` düğümünün altına yazmasını söyler.

### Adım 3: Dönüştürmeyi Gerçekleştirin
Son olarak, `VectorLayer` üzerindeki statik `Convert` metodunu çağırın. Metod GeoJSON'u okur, seçenekleri uygular ve TopoJSON'u yazar.

```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```

Dönüştürme başarılı olursa, tanımladığınız özel nesne adıyla `outputFilePath` konumunda kompakt bir TopoJSON dosyası bulacaksınız.

## Yaygın Sorunlar ve Çözümler

| Sorun | Neden Oluşur | Çözüm |
|-------|--------------|-------|
| **Dosya bulunamadı** | Yanlış yol veya eksik dosya uzantısı. | `sampleGeoJsonPath`'i `File.Exists` ile doğrulayın. |
| **Geçersiz GeoJSON** | Giriş dosyası GeoJSON spesifikasyonuna uymuyor. | Dönüştürmeden önce `GeoJsonReader` ile doğrulayın. |
| **Nesne adı yoksayıldı** | `DefaultObjectName` özelliği olmayan eski bir Aspose.GIS sürümü kullanılıyor. | En son Aspose.GIS sürümüne yükseltin. |
| **İzin reddedildi** | Çıktı dizini yalnızca okuma iznine sahip. | Uygulamayı uygun dosya sistemi izinleriyle çalıştırın. |

## Sonuç
Artık Aspose.GIS for .NET kullanarak belirli bir nesne adıyla **GeoJSON'u TopoJSON'a nasıl dönüştüreceğinizi** biliyorsunuz. Bu yaklaşım, çıktı topolojisi üzerinde tam kontrol sağlar, dosya boyutunu azaltır ve herhangi bir .NET tabanlı GIS iş akışına sorunsuz bir şekilde entegre olur.

## SSS'ler
### Aspose.GIS for .NET'i ticari projelerimde kullanabilir miyim?
Evet, Aspose.GIS for .NET'i hem ticari hem de kişisel projelerde kullanabilirsiniz.  
### Aspose.GIS for .NET için ücretsiz deneme mevcut mu?
Evet, [buradan](https://releases.aspose.com/) ücretsiz deneme alabilirsiniz.  
### Aspose.GIS for .NET için desteği nereden bulabilirim?
Destek alabileceğiniz yer [Aspose.GIS forumu](https://forum.aspose.com/c/gis/33)'dur.  
### Aspose.GIS for .NET için lisans nasıl satın alınır?
Lisansı [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.  
### Değerlendirme için geçici lisansa ihtiyacım var mı?
Evet, geçici lisansı [buradan](https://purchase.aspose.com/temporary-license/) alabilirsiniz.

## Sıkça Sorulan Sorular

**S: TopoJSON'un GeoJSON'a göre en büyük avantajı nedir?**  
C: TopoJSON, ortak çizgi segmentlerini bir kez depolar, bu da karmaşık haritaların dosya boyutunu büyük ölçüde azaltır.

**S: Yüzlerce MB boyutundaki büyük bir GeoJSON dosyasını dönüştürebilir miyim?**  
C: Evet. Aspose.GIS verileri akış olarak işler, bu yüzden bellek kullanımı düşük kalır; sadece çıktının yeterli disk alanına sahip olduğundan emin olun.

**S: Dönüştürme sırasında koordinat hassasiyetini ayarlamak mümkün mü?**  
C: Kesinlikle. Koordinatları istenen ondalık basamak sayısına yuvarlamak için `TopoJsonOptions.Precision` kullanın.

**S: Dönüştürme tüm GeoJSON özelliklerini korur mu?**  
C: Tüm özellik (feature) özellikleri TopoJSON çıktısına birebir kopyalanır.

**S: Oluşturulan TopoJSON dosyasını JavaScript'te nasıl okurum?**  
C: `topojson-client` gibi kütüphaneler dosyayı ayrıştırabilir ve ayarladığınız özel nesne adını (`name_of_the_object`) referans alabilirsiniz.

---

**Last Updated:** 2025-11-29  
**Tested With:** Aspose.GIS for .NET 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}