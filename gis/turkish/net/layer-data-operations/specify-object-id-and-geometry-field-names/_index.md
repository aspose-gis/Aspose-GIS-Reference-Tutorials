---
date: 2026-01-02
description: Aspose.GIS for .NET kullanarak alan adlarını ayarlarken nokta özelliği
  eklemeyi ve nesne kimliğini okumayı öğrenin. Geliştiriciler için adım adım rehber.
linktitle: Specify Object ID and Geometry Field Names
second_title: Aspose.GIS .NET API
title: Nokta özelliği ekle ve Nesne Kimliği ile Geometri Alanı Adlarını belirt
url: /tr/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nokta özelliği ekleme ve Nesne Kimliği ile Geometri Alanı İsimlerini Belirleme

## Giriş
Aspose.GIS for .NET kullanarak Coğrafi Bilgi Sistemleri (GIS) dünyasına adım atmak, geliştiriciler ve meraklılar için pek çok olasılık sunar. Bu öğreticide, **nokta özelliği eklemeyi**, **alan isimlerini ayarlamayı** ve **nesne kimliği (object id)** değerlerini **okumayı** öğrenecek, böylece mekânsal verileriniz üzerinde tam kontrol sahibi olacaksınız.

## Hızlı Yanıtlar
- **Bu kılavuzun temel amacı nedir?** Nokta özelliği eklemek ve Nesne Kimliği ile Geometri alanı isimlerini yapılandırmayı göstermek.  
- **Hangi kütüphane kullanılıyor?** Aspose.GIS for .NET.  
- **Lisans gerekir mi?** Ücretsiz deneme sürümü mevcuttur; üretim için lisans gereklidir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Eklemeden sonra Nesne Kimliğini okuyabilir miyim?** Evet – öğreticide katmandan nesne kimliğinin nasıl okunacağı gösterilmektedir.

## Ön Koşullar
Öğreticiye başlamadan önce aşağıdaki ön koşulların sağlandığından emin olun:
- Aspose.GIS for .NET: Kütüphaneyi [buradan](https://releases.aspose.com/gis/net/) indirin ve kurun.
- Belge Dizini: Coğrafi veritabanlarınızı saklamak için bir dizin oluşturun.
- .NET Ortamı: Çalışır durumda bir .NET ortamına sahip olun.

## Ad Alanlarını İçe Aktarma
Projeye gerekli ad alanlarını (namespaces) eklemeniz gerekir. Bu ad alanları, Aspose.GIS for .NET ile etkileşim kurmak için gerekli sınıf ve metodları sağlar.

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## Adım 1: Nokta özelliği ekleme ve Nesne Kimliği ile Geometri Alanı İsimlerini Belirleme
Bu adımda, GIS verileriniz için Nesne Kimliği ve Geometri alanı isimlerini nasıl ayarlayacağınızı öğreneceksiniz. Bu, verileri verimli bir şekilde yönetmek ve daha sonra **nesne kimliğini** **okuyabilmek** için kritiktir.

### 1.1: Belge Dizinini Ayarlama
Belge dizininizin yolunu tanımlayarak başlayın:

```csharp
string dataDir = "Your Document Directory";
```

### 1.2: GeoDatabase Oluşturma ve Seçenekleri Tanımlama
Nesne Kimliği ve Geometri için **alan isimlerini ayarlayarak** bir GeoDatabase oluşturun:

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

### 1.3: Katman Oluşturma ve Ekleme
GeoDatabase içinde bir katman oluşturun ve nokta geometrisini temsil eden bir özellik ekleyin:

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

### 1.4: Katmanı Açma ve Verileri Getirme
Katmanı açın ve az önce eklediğiniz özelliği alın. Bu, veri kümesinden **nesne kimliğini** **okumanın** bir örneğidir:

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## Özel alan isimleri neden ayarlanmalı?
Nesne Kimliği ve Geometri alanı isimlerini özelleştirmeniz, mevcut veritabanlarıyla entegrasyon ya da aşağı akış uygulamaları tarafından talep edilen adlandırma kurallarına uyum sağlarken esneklik kazandırır. Ayrıca veriyi daha kendini açıklayıcı hâle getirerek bakım ve iş birliğini kolaylaştırır.

## Yaygın hatalar ve sorun giderme
- **Dizin eksik** – `dataDir` değişkeninin var olan bir klasöre işaret ettiğinden emin olun; aksi takdirde `Dataset.Create` bir istisna fırlatır.
- **Alan adı çakışması** – Aynı ada sahip bir alan zaten geodatabase içinde varsa oluşturma başarısız olur. Benzersiz isimler seçin.
- **Uzamsal referans uyumsuzluğu** – Depolamayı planladığınız verilerle aynı uzamsal referans sistemini (ör. WGS84) kullandığınızdan emin olun.

## Sonuç
Tebrikler! Aspose.GIS for .NET kullanarak **nokta özelliği eklemeyi**, **alan isimlerini ayarlamayı** ve **nesne kimliğini okumayı** başarıyla öğrendiniz. Bu temel, sağlam GIS uygulamaları oluşturmanıza ve mekânsal verileri güvenle yönetmenize olanak tanır.

## Sık Sorulan Sorular
### S: Aspose.GIS for .NET'i web uygulamalarımda kullanabilir miyim?
C: Evet, Aspose.GIS for .NET hem masaüstü hem de web uygulamaları için uygundur ve çok yönlü coğrafi yetenekler sunar.

### S: Satın almadan önce deneme sürümü mevcut mu?
C: Evet, ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) keşfedebilirsiniz.

### S: Aspose.GIS for .NET için geçici bir lisans nasıl alınır?
C: Değerlendirme amaçlı geçici lisansı [buradan](https://purchase.aspose.com/temporary-license/) edinebilirsiniz.

### S: Aspose.GIS for .NET hangi uzamsal referans sistemlerini destekliyor?
C: Aspose.GIS for .NET, çeşitli uzamsal referans sistemlerini destekleyerek farklı coğrafi veri setleriyle çalışmanıza esneklik sağlar.

### S: Aspose.GIS ile ilgili sorularımı nereden sorabilirim?
C: Destek ve tartışmalar için Aspose.GIS forumunu [burada](https://forum.aspose.com/c/gis/33) ziyaret edin.

## Ek Sık Sorulan Sorular

**S: Katman oluşturulduktan sonra Nesne Kimliği alanını değiştirebilir miyim?**  
C: Hayır. Alan adı katman oluşturulurken tanımlanır; yeni bir `FileGdbOptions` nesnesiyle katmanı yeniden oluşturmanız gerekir.

**S: Nesne Kimliği dışındaki diğer öznitelik değerlerini nasıl alabilirim?**  
C: `feature.GetValue<T>("FieldName")` metodunu kullanın; burada `FieldName` okumak istediğiniz öznitelik adıdır.

**S: Tek seferde birden fazla nokta özelliği eklemek mümkün mü?**  
C: Evet. Verilerinizi döngü içinde işleyin, her nokta için bir özellik oluşturun, geometrisini ayarlayın ve aynı `using` bloğu içinde `layer.Add(feature)` çağrısını yapın.

**S: Aspose.GIS diğer geometri tiplerini destekliyor mu?**  
C: Kesinlikle. `LineString`, `Polygon`, `MultiPoint` ve daha fazlasını uygun geometri nesnelerini oluşturarak kullanabilirsiniz.

**S: Var olmayan bir Nesne Kimliği okumaya çalışırsam ne olur?**  
C: Kapsam dışı bir indeks erişimi (ör. sadece bir özellik varken `layer[10]` çağrısı) `IndexOutOfRangeException` fırlatır. Öncelikle `layer.Count` değerini kontrol edin.

---

**Son Güncelleme:** 2026-01-02  
**Test Edilen Versiyon:** Aspose.GIS for .NET 24.11  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}