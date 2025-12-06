---
date: 2025-12-06
description: Aspose.GIS for .NET kullanarak GeoJSON'ı gruplayarak TopoJSON'a dönüştürmeyi,
  nesne ad özniteliğini ayarlamayı ve GeoJSON özelliklerini gruplamayı öğrenin.
language: tr
linktitle: How to Convert GeoJSON to TopoJSON with Grouping using Aspose.GIS
second_title: Aspose.GIS .NET API
title: Aspose.GIS Kullanarak Gruplama ile GeoJSON'dan TopoJSON'a Nasıl Dönüştürülür
url: /net/geo-data-conversion/convert-geojson-to-topojson-with-grouping/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GeoJSON'u TopoJSON'a Gruplama ile Aspose.GIS Kullanarak Nasıl Dönüştürülür

## Giriş

Bu adım‑adım öğreticide **GeoJSON** dosyalarını, seçtiğiniz bir niteliğe göre özellikleri gruplayarak TopoJSON'a nasıl dönüştüreceğinizi öğreneceksiniz. Aspose.GIS .NET API'si, dönüşümü hızlı, güvenilir ve C# kodunuzdan tam kontrol edilebilir hâle getirir. İster bir ASP.NET GeoJSON dönüşüm servisi ister masaüstü GIS aracı geliştirin, bu kılavuz tam olarak ne yapmanız gerektiğini gösterir.

## Hızlı Yanıtlar
- **Dönüşümü hangi kütüphane yönetiyor?** Aspose.GIS for .NET  
- **Uygulama ne kadar sürer?** Temel bir kurulum için genellikle 5‑10 dakika  
- **Üretim için lisansa ihtiyacım var mı?** Evet, ticari bir lisans gereklidir (ücretsiz deneme mevcut)  
- **Özellikleri herhangi bir niteliğe göre gruplayabilir miyim?** Evet – `ObjectNameAttribute`'u gruplayacağınız alan olarak ayarlayın  
- **.NET Core destekleniyor mu?** Kesinlikle – API .NET Core, .NET 5/6 ve klasik .NET Framework ile çalışır  

## GeoJSON ve TopoJSON Nedir?

GeoJSON, nokta, çizgi ve çokgen gibi coğrafi özellikleri kodlamak için yaygın olarak kullanılan bir JSON formatıdır. TopoJSON, topolojiyi (paylaşılan çizgi segmentlerini) depolayarak dosya boyutunu küçültür ve karmaşık haritaların render performansını artırır. Web görselleştirmeleri için kompakt harita verilerine ihtiyaç duyduğunuzda aralarında dönüşüm yapmak yaygın bir adımdır.

## GeoJSON Özelliklerini Neden Gruplamalıyız?

`group geojson features` (geojson özelliklerini gruplayarak) elde edilen TopoJSON içinde ilgili geometrileri tek bir adlandırılmış nesne altında düzenlemenizi sağlar. Bu özellikle şu durumlarda faydalıdır:
- Farklı idari bölgeler için ayrı katmanlar oluşturmak istediğinizde.  
- Ön‑uç harita kütüphanenizin stil veya etkileşim için adlandırılmış nesneler beklediği durumlarda.  
- Bitişik özellikler arasında sınırları paylaşarak tekrarı azaltmak istediğinizde.

## Ön Koşullar

Başlamadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

1. **Aspose.GIS for .NET** – resmi siteden [buradan](https://releases.aspose.com/gis/net/) indirip kurun.  
2. **Geliştirme Ortamı** – Visual Studio, Visual Studio Code veya C# destekleyen herhangi bir IDE.  
3. **Örnek GeoJSON Dosyası** – dönüştürmek istediğiniz özellikleri içeren bir dosya.  

## Ad Alanlarını İçe Aktarın

Projeye gerekli ad alanlarını ekleyin:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
```

## Adım‑Adım Kılavuz

### Adım 1: Dosya Yollarını Tanımlayın

Kaynak GeoJSON dosyasının nerede bulunduğunu ve TopoJSON dosyasının nereye yazılacağını belirtin:

```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithGrouping_out.topojson";
```

> **İpucu:** .NET Core hedefliyorsanız, platformlar arası yol oluşturma için `Path.Combine` kullanın.

### Adım 2: Dönüşüm Seçeneklerini Yapılandırın (Nesne Adı Niteliğini Ayarlayın)

Bir `ConversionOptions` örneği oluşturun ve Aspose.GIS'e özellikleri nasıl gruplayacağını söyleyin:

```csharp
var options = new ConversionOptions
{
    DestinationDriverOptions = new TopoJsonOptions
    {
        // Specify the attribute in GeoJSON layer by which we are going to group into objects
        ObjectNameAttribute = "group",
        // Specify the default object name for features with unknown attribute values
        DefaultObjectName = "unnamed",
    }
};
```

`"group"` ifadesini, **geojson feature grouping** (geojson özellik gruplaması) için kullanmak istediğiniz gerçek alan adıyla değiştirin. `DefaultObjectName`, niteliğin eksik olduğu durumlarda bile her özelliğin bir TopoJSON nesnesine yerleştirilmesini sağlar.

### Adım 3: Dönüşümü Gerçekleştirin (GeoJSON'u TopoJSON'a Dönüştürün)

Tek bir API çağrısı ile dönüşümü çalıştırın:

```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```

Çalıştırdıktan sonra, `convertedSampleWithGrouping_out.topojson` dosyası, belirttiğiniz niteliğe göre gruplanmış TopoJSON temsili içerecektir.

## Yaygın Sorunlar ve Çözüm Yolları

| Belirti | Muhtemel Neden | Çözüm |
|---------|----------------|------|
| **Tüm özellikler “unnamed” içinde görünüyor** | `ObjectNameAttribute` GeoJSON içinde hiçbir özelliğe eşleşmiyor | Tam alan adını (büyük/küçük harf duyarlı) doğrulayın ve seçeneği güncelleyin |
| **Çıktı dosyası boş** | Yanlış dosya yolu veya okuma izni eksikliği | Mutlak yollar kullanın veya uygulamanın dosya sistemi erişimini sağlayın |
| **Dönüşüm `NotSupportedException` hatası veriyor** | Desteklenmeyen geometri tipleri (ör. GeometryCollection) içeren GeoJSON | Kaynak veriyi sadeleştirin veya Aspose.GIS'in en yeni sürümüne yükseltin |

## Sık Sorulan Sorular

**S: Özellikleri birden fazla niteliğe göre gruplayabilir miyim?**  
C: Evet, birden fazla alanı tek bir sanal nitelikte birleştirerek veya farklı `ObjectNameAttribute` değerleriyle birden çok dönüşüm geçişi yaparak mümkün.

**S: Aspose.GIS ASP.NET Core ile uyumlu mu?**  
C: Kesinlikle – kütüphane ASP.NET Core, .NET 5, .NET 6 ve klasik .NET Framework ile çalışır.

**S: GeoJSON dışındaki diğer coğrafi formatları da dönüştürebilir miyim?**  
C: Evet, Aspose.GIS Shapefile, KML, GML, CSV ve daha birçok formatı içe ve dışa aktarabilir.

**S: Aspose.GIS ücretsiz deneme sunuyor mu?**  
C: Evet, ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) alabilirsiniz.

**S: Aspose.GIS için destek nereden alınır?**  
C: Aspose.GIS topluluk forumundan [burada](https://forum.aspose.com/c/gis/33) destek alabilirsiniz.

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**Son Güncelleme:** 2025-12-06  
**Test Edilen Versiyon:** Aspose.GIS for .NET (en son sürüm)  
**Yazar:** Aspose  

---