---
date: 2026-01-05
description: Aspose.GIS for .NET kullanarak C# ile shapefile okuma, tüm özellik öznitelik
  değerlerini alma ve öznitelikleri verimli bir şekilde dökme konusunda öğrenin.
linktitle: Get All Feature Attribute Values
second_title: Aspose.GIS .NET API
title: Shapefile'i C# ile Okuma – Tüm Özellik Nitelik Değerlerini Al
url: /tr/net/layer-interaction-and-data-access/get-all-feature-attribute-values/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tüm Özellik Nitelik Değerlerini Alın

## Giriş
Aspose.GIS for .NET ile coğrafi uzamsal geliştirme dünyasına hoş geldiniz! Bu öğreticide **C# ile shapefile okuma** ve özelliklerinin her bir nitelik değerini almayı öğreneceksiniz. İster bir haritalama uygulaması geliştirin ister toplu olarak uzamsal verileri işleyin, nitelik çıkarımını ustalaşmak çok önemlidir. Hadi derinlemesine inceleyelim ve kodun nasıl çalıştığını görelim.

## Hızlı Yanıtlar
- **Bu kod ne yapar?** Bir Shapefile'ı açar ve her özelliğin tüm, birkaç veya döküm (dump) nitelik değerlerini okur.  
- **Hangi kütüphane gereklidir?** Aspose.GIS for .NET (.NET Framework ve .NET Core ile uyumludur).  
- **Lisans gerekiyor mu?** Test için geçici bir lisans çalışır; üretim için tam lisans gereklidir.  
- **Diğer formatları okuyabilir miyim?** Evet – aynı API GeoJSON, KML ve daha birçok formatı destekler.  
- **Nitelikleri nasıl döküm (dump) alırım?** Esnek bir nesne dizisi elde etmek için `feature.GetValuesDump()` kullanın.

## “C# ile shapefile okuma” nedir?
C# ile bir Shapefile okumak, .shp dosyasını bir GIS kütüphanesiyle açmak, vektör özellikleri üzerinde döngü yapmak ve eşlik eden .dbf dosyasında depolanan nitelik verilerine erişmek anlamına gelir. Aspose.GIS düşük‑seviye dosya işlemlerini soyutlayarak ihtiyacınız olan nitelik değerlerine odaklanmanızı sağlar.

## Nitelikleri okumak için neden Aspose.GIS kullanılmalı?
- **Basit API** – `GetValues` ve `GetValuesDump` gibi sezgisel yöntemler.  
- **Çapraz platform** – .NET Core ile Windows, Linux ve macOS'ta çalışır.  
- **Zengin format desteği** – ek eklentiler olmadan Shapefile, GeoJSON, GML ve daha fazlasını işleyebilir.  
- **Performans‑optimizeli** – büyük veri setlerinde hızlı yineleme.

## Önkoşullar
Bu heyecan verici yolculuğa başlamadan önce, aşağıdaki önkoşulların yerine getirildiğinden emin olun:
- Aspose.GIS for .NET: Kütüphaneyi [Aspose.GIS for .NET indirme sayfasından](https://releases.aspose.com/gis/net/) indirin ve kurun.
- Geliştirme Ortamı: Visual Studio gibi bir .NET geliştirme ortamı kurun.
- Shapefile: Belge dizininizde hazır bir örnek Shapefile (ör. "InputShapeFile.shp") bulundurun.

## Ad Alanlarını İçe Aktarın
C# kodunuzda, Aspose.GIS işlevselliğinden yararlanmak için gerekli ad alanlarını içe aktararak başlayın:
```csharp
using System;
using Aspose.Gis;
```

## Adım 1: Belge Dizinini Ayarla
```csharp
string dataDir = "Your Document Directory";
```
"Your Document Directory" ifadesini Shapefile'ınızın bulunduğu gerçek yol ile değiştirin.

## Adım 2: VectorLayer'ı Aç
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for further steps goes here
}
```
Bu adım, Aspose.GIS kullanarak Shapefile'ı açmayı, dosya yolunu ve formatını (bu durumda Shapefile) belirtmeyi içerir.

## Adım 3: Tüm Özellik Nitelik Değerlerini Al
```csharp
foreach (var feature in layer)
{
    // reads all the attributes into an array.
    object[] all = new object[3];
    feature.GetValues(all);
    Console.WriteLine("all    : {0}, {1}, {2}", all);
    // Your code for handling all attribute values goes here
    Console.WriteLine();
}
```
Bu kod parçacığı, her özellik için nitelikleri **nasıl okuyacağınızı** sabit boyutlu bir diziye yükleyerek gösterir.

## Adım 4: Birkaç Özellik Nitelik Değerini Al
```csharp
foreach (var feature in layer)
{
    // reads several attributes into an array.
    object[] several = new object[2];
    feature.GetValues(several);
    Console.WriteLine("several: {0}, {1}", several);
    // Your code for handling several attribute values goes here
    Console.WriteLine();
}
```
Burada, yalnızca bir alan alt kümesine ihtiyacınız olduğunda **belirli nitelik değerlerini nasıl okuyacağınızı** gösteriyoruz.

## Adım 5: Nitelik Değerlerini Nesne Dökümü Olarak Al
```csharp
foreach (var feature in layer)
{
    // reads attributes as a dump of objects.
    var dump = feature.GetValuesDump();
    Console.WriteLine("dump   : {0}, {1}, {2}", dump);
    // Your code for handling dumped attribute values goes here
    Console.WriteLine();
}
```
Bu son adım, `GetValuesDump()` kullanarak **nitelikleri nasıl döküm alacağınızı** gösterir; bu yöntem, inceleyebileceğiniz veya serileştirebileceğiniz esnek bir koleksiyon döndürür.

## Yaygın Sorunlar ve Çözümler
- **Dizi boyutu uyuşmazlığı** – `GetValues`'a gönderdiğiniz dizinin beklediğiniz nitelik sayısıyla eşleştiğinden emin olun; aksi takdirde `null` girdileri alırsınız.  
- **Dosya bulunamadı** – `dataDir`'in doğru klasöre işaret ettiğini ve Shapefile adının tam olarak doğru yazıldığını doğrulayın.  
- **Lisans istisnası** – Bir lisans hatası görürseniz, herhangi bir API metodunu çağırmadan önce geçici veya tam bir lisans uygulayın.

## Sık Sorulan Sorular
### Aspose.GIS .NET Core ile uyumlu mu?
Evet, Aspose.GIS .NET Core ile tamamen uyumludur ve çapraz‑platform uygulamalar oluşturmanıza olanak tanır.

### Aspose.GIS ile farklı GIS dosya formatlarıyla çalışabilir miyim?
Kesinlikle! Aspose.GIS, Shapefile, GeoJSON ve daha fazlası dahil olmak üzere çeşitli formatları destekler.

### Aspose.GIS desteği için bir topluluk forumu var mı?
Evet, [destek forumunda](https://forum.aspose.com/c/gis/33) yardım bulabilir ve Aspose.GIS topluluğuyla etkileşime geçebilirsiniz.

### Aspose.GIS için geçici bir lisans nasıl alabilirim?
Test amaçlı geçici bir lisans alabilirsiniz [buradan](https://purchase.aspose.com/temporary-license/).

### Aspose.GIS için ayrıntılı belgeleri nerede bulabilirim?
Kapsamlı dokümantasyon [burada](https://reference.aspose.com/gis/net/) mevcuttur.

### Her özelliğin sadece “Name” niteliğini nasıl alırım?
`GetValues`'ı tek elemanlık bir diziyle kullanın ve “Name” alanının indeksini geçin, ya da doğrudan `feature["Name"]` çağırın.

### `GetValues` ile `GetValuesDump` arasındaki fark nedir?
`GetValues`, önceden tahsis edilmiş bir diziyi ham değerlerle doldurur, `GetValuesDump` ise şemayı önceden bilmeden yineleyebileceğiniz bir nesne dizisi döndürür.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Son Güncelleme:** 2026-01-05  
**Test Edilen:** Aspose.GIS for .NET (latest release)  
**Yazar:** Aspose  

---