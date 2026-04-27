---
date: 2026-01-13
description: Aspose.GIS for .NET kullanarak shapefile'ı geojson'a nasıl dönüştüreceğinizi
  öğrenin. Rehber ayrıca katmanlar arasında öznitelikleri kopyalamayı ve C# ile geojson
  dosyası oluşturmayı da kapsar.
linktitle: Extract Features to GeoJSON
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET kullanarak Shapefile'ı GeoJSON'a nasıl dönüştürülür
url: /tr/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Shapefile'ı GeoJSON'a Aspose.GIS for .NET ile Dönüştürme

## Giriş
Bu kapsamlı, adım‑adım öğreticide **shapefile'ı geojson'a nasıl dönüştüreceğinizi** güçlü Aspose.GIS .NET kütüphanesini kullanarak öğreneceksiniz. İster bir haritalama web servisi oluşturuyor olun, ister bir mobil GIS uygulaması için veri hazırlıyor olun ya da sadece formatlar arasında veri alışverişi yapmanız gerekiyor olsun, bu kılavuz tam olarak ne yapmanız gerektiğini, her adımın neden önemli olduğunu ve yaygın hatalardan nasıl kaçınacağınızı gösterir.

## Hızlı Yanıtlar
- **Bu öğreticide ne ele alınıyor?** Bir Shapefile'ı GeoJSON dosyasına dönüştürme, katmanlar arasında öznitelikleri kopyalama ve çıktıyı C# ile oluşturma.
- **Hangi kütüphane gerekli?** Aspose.GIS for .NET.
- **Lisans gerekli mi?** Üretim ortamı için geçici veya tam lisans gerekir; değerlendirme için ücretsiz deneme sürümü çalışır.
- **Uygulama ne kadar sürer?** Temel bir dönüşüm için yaklaşık 10‑15 dakika.
- **.NET Core/.NET 6 üzerinde çalıştırabilir miyim?** Evet – kod tüm desteklenen .NET sürümlerinde çalışır.

## Ön Koşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.GIS for .NET: Kütüphanenin yüklü olduğundan emin olun. Yüklü değilse, [Aspose.GIS for .NET sayfasından](https://releases.aspose.com/gis/net/) indirebilirsiniz.
- Shapefile Verisi: Giriş için bir Shapefile hazır bulundurun. Örnek veri gerekiyorsa, [Aspose.GIS belgelerinde](https://reference.aspose.com/gis/net/) bulabilirsiniz.
- .NET Ortamı: Sağlanan kodu çalıştırmak için bir .NET ortamı kurun.
- Belge Dizini: Kod parçacığında belge dizininizin yolunu tanımlayın.

Her şey hazır olduğuna göre, shapefile'ı geojson'a dönüştürmeye başlayalım!

## “convert shapefile to geojson” nedir?
Shapefile'ı GeoJSON'a dönüştürmek, klasik ESRI Shapefile formatındaki vektör özelliklerini okuyup modern, web‑uyumlu bir GeoJSON belgesi olarak yazmak anlamına gelir. GeoJSON, JavaScript haritalama kütüphanelerinde (Leaflet, Mapbox GL) ve API'lerde yaygın olarak kullanılır; bu da dönüşümü GIS geliştirmede sık bir görev haline getirir.

## Bu dönüşüm için neden Aspose.GIS kullanmalı?
Aspose.GIS, dosya formatlarının düşük‑seviye detaylarını soyutlar, öznitelik tablolarını zahmetsizce kopyalamanızı sağlar ve .NET Framework, .NET Core ve .NET 5/6 üzerinde çalışan temiz, nesne‑yönelimli bir API sunar. Böylece ikili dosyaları ayrıştırmak yerine iş mantığınıza odaklanabilirsiniz.

## Namespace'leri İçeri Aktarın
İlk olarak, kodunuzda gerekli namespace'leri ekleyin:

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Bu namespace'ler, Aspose.GIS işlevselliğiyle çalışmak için gereklidir.

## Shapefile'ı GeoJSON'a Nasıl Dönüştürülür
Aşağıda, net adımlara bölünmüş tam iş akışı yer almaktadır. Her adım kısa bir açıklama ve projenize kopyalamanız gereken tam kod bloğunu içerir.

### Adım 1: Giriş Shapefile'ını Aç
```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```
`VectorLayer.Open` yöntemiyle giriş Shapefile'ını açın. Bu, `Feature` nesnelerinin bir enumerable koleksiyonunu size verir.

### Adım 2: Çıktı GeoJSON'ı Oluştur
```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```
`VectorLayer.Create` yöntemiyle çıktıyı oluşturun ve `Drivers.GeoJson` sürücüsünü belirtin.

### Adım 3: Katmanlar Arasında Öznitelikleri Kopyala
```csharp
outputLayer.CopyAttributes(inputLayer);
```
Bu tek satır, kaynak Shapefile'dan yeni GeoJSON katmanına öznitelik şemasını (alan adları, tipleri) kopyalar – *copy attributes between layers* ikincil anahtar kelimesinin tam olarak tanımladığı şey.

### Adım 4: Özellikleri İşle
```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```
Shapefile'daki her özelliği yineleyerek, çıktıya yazmadan önce istediğiniz özel mantığı uygulayabilirsiniz.

### Adım 5: Özellikleri Tarihe Göre Filtrele
```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```
Bu örnekte, `dob` (date of birth) alanı eksik olan veya 1 Ocak 1982'den önceki kayıtları atlıyoruz. Filtreyi kendi veri gereksinimlerinize göre ayarlayabilirsiniz.

### Adım 6: Yeni Bir Özellik Oluştur (C# Generate GeoJSON File)
```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```
Burada, GeoJSON katmanı için yeni bir `Feature` oluşturur, geometrisini ve öznitelik değerlerini kopyalar ve çıktıya ekleriz. Bu, *c# generate geojson file* ifadesinin çekirdeğidir.

Tebrikler! **shapefile'ı geojson'a dönüştürme** işlemini başarıyla tamamladınız ve bu süreçte katmanlar arasında öznitelikleri nasıl kopyalayacağınızı öğrendiniz.

## Yaygın Sorunlar ve Çözümler
| Sorun | Neden Oluşur | Çözüm |
|-------|--------------|-------|
| Çıktı dosyası boş | `CopyAttributes` çıktı katmanı kapatıldıktan sonra çağrılmış | `outputLayer` için `using` bloğunun, tüm özellikler eklenene kadar açık kalmasını sağlayın. |
| Tarih filtresi tüm kayıtları siliyor | Yanlış alan adı veya beklenmedik tarih formatı | Öznitelik adını (`dob`) doğrulayın ve tarihlerin string olarak saklandığını düşünüyorsanız `GetValue<string>` kullanın. |
| Lisans istisnası | Üretimde geçerli bir Aspose.GIS lisansı olmadan çalıştırılıyor | Aspose belgelerinde açıklandığı gibi geçici veya tam bir lisans uygulayın. |

## Sık Sorulan Sorular
**S: Daha fazla belgeyi nereden bulabilirim?**  
C: Ayrıntılı bilgi için [Aspose.GIS belgelerini](https://reference.aspose.com/gis/net/) ziyaret edin.

**S: Geçici bir lisans nasıl alabilirim?**  
C: Geçici lisansı [buradan](https://purchase.aspose.com/temporary-license/) edinebilirsiniz.

**S: Destek nereden alınır?**  
C: Topluluk desteği ve tartışmalar için [Aspose.GIS forumuna](https://forum.aspose.com/c/gis/33) katılın.

**S: Ücretsiz deneme mevcut mu?**  
C: Evet, ücretsiz denemeyi [buradan](https://releases.aspose.com/) bulabilirsiniz.

**S: Aspose.GIS for .NET'i nereden satın alabilirim?**  
C: Ürünü [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

## Sonuç
Bu öğreticide, Aspose.GIS for .NET kullanarak **shapefile'ı geojson'a dönüştürme** sürecini, katmanlar arasında öznitelikleri kopyalamayı ve *c# generate geojson file* ifadesinin temiz bir uygulamasını inceledik. Farklı filtreler, daha büyük veri setleri veya ek geometri dönüşümleri deneyerek kütüphanenin yeteneklerinden tam anlamıyla yararlanabilirsiniz.

---

**Son Güncelleme:** 2026-01-13  
**Test Edilen:** Aspose.GIS for .NET (en son kararlı sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}