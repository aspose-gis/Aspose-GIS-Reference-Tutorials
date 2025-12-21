---
date: 2025-12-21
description: Aspose.GIS for .NET ile geometriyi doğrusal hâle getirmeyi öğrenin; .NET
  uygulamalarınızda verimli coğrafi veri işleme, mekânsal analiz ve geometri manipülasyonu
  sağlayın.
linktitle: Linearize a Geometry
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET ile Geometriyi Nasıl Doğrusal Hale Getirirsiniz
url: /tr/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Geometriyi Doğrusal Hale Getirme

## Giriş
Haritalama, mekansal analiz veya veri‑değişim görevleri için **geometriyi nasıl doğrusal hale getireceğinizi** öğrenmeniz gerekiyorsa, Aspose.GIS for .NET size temiz ve programatik bir yol sunar. Bu öğreticide, eğriler ve birleşik şekiller içeren karmaşık bir geometriyi alıp, herhangi bir GIS sistemiyle çalışan basit bir doğrusal temsile dönüştürmeyi gösteren eksiksiz, gerçek dünya örneğini adım adım inceleyeceğiz.

## Hızlı Yanıtlar
- **Geometrinin doğrusal hale getirilmesi ne anlama gelir?** Eğrileri ve karmaşık şekilleri düz çizgi segmentlerine dönüştürmek.  
- **Neden Aspose.GIS kullanılmalı?** Onlarca GIS formatını destekler ve dış araçlar olmadan geometri dönüşümünü gerçekleştirir.  
- **Önkoşullar?** .NET Framework veya .NET Core, Visual Studio ve Aspose.GIS kütüphanesi.  
- **Örnek ne kadar sürer?** Kütüphane kurulduktan sonra beş dakikadan az bir sürede çalışır.  
- **Başka formatlarda kaydedebilir miyim?** Evet—KML sürücüsünü Shapefile, GeoJSON vb. ile değiştirin.

## Geometrinin Doğrusal Hale Getirilmesi Nedir?
Doğrusal hale getirme, eğri veya birleşik bir şekli bir dizi düz‑çizgi segmentine (bir “doğrusal geometri”) bölmek anlamına gelir. Bu, yalnızca çizgi ve nokta anlayan araçlarla render, analiz ve birlikte çalışabilirliği basitleştirir.

## Neden Geometriyi Doğrusal Hale Getirmeli?
- **Performans:** Doğrusal geometriler daha hızlı render ve sorgu yapılır.  
- **Uyumluluk:** Birçok GIS platformu (ör. eski harita hizmetleri) yalnızca doğrusal özellikleri kabul eder.  
- **Basitleştirme:** Küçük resimler, hızlı ön izlemeler oluşturmak veya doğrusal girdi gerektiren algoritmalara veri sağlamak için faydalıdır.

## Önkoşullar
1. **Aspose.GIS for .NET** – bunu [Aspose.GIS web sitesinden](https://releases.aspose.com/gis/net/) indirebilirsiniz.  
2. Geliştirme makinenizde kurulu **.NET Framework** (veya .NET Core).  
3. Örneği yazmak ve çalıştırmak için **Visual Studio** (veya herhangi bir C# uyumlu IDE).

## Ad Alanlarını İçe Aktarma
Aspose.GIS işlevselliğini kullanmaya başlamak için gerekli ad alanlarını içe aktarın.

### Adım 1: Aspose.GIS Core Ad Alanlarını İçe Aktarın
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Adım 2: Hedef Formatınız İçin Sürücüyü İçe Aktarın
Bu örnek için sonucu bir KML dosyasına yazacağız:
```csharp
using Aspose.GIS.Kml;
```

## Geometrinin Doğrusal Hale Getirilmesi – Adım Adım Kılavuz
Aşağıda her kod satırını ayrıntılı olarak inceleyerek **geometriyi nasıl doğrusal hale getireceğinizi** ve her adımın neden önemli olduğunu açıklıyoruz.

### Adım 1: Çıktı Yolunu Tanımlayın
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
`"Your Document Directory"` ifadesini KML dosyasını kaydetmek istediğiniz klasörle değiştirin.

### Adım 2: Çıktı Dosyası İçin Bir Katman Oluşturun
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```
*layer* coğrafi özellikler için bir konteynerdir. Burada doğrusal hale getirilmiş geometrimizi tutacak yeni bir KML katmanı oluşturuyoruz.

### Adım 3: Yeni Bir Özellik Oluşturun
```csharp
var feature = layer.ConstructFeature();
```
*feature* tek bir coğrafi nesneyi (nokta, çizgi, çokgen vb.) temsil eder. Doğrusal geometrimizi bu özelliğe ekleyeceğiz.

### Adım 4: Orijinal Karmaşık Geometriyi Tanımlayın
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```
Well‑Known Text (WKT) dizesinden bir geometri oluşturuyoruz. Bu örnek, doğrusal hale getirmeyi göstermek için mükemmel olan bir `LineString`, bir `CompoundCurve` ve bir `CircularString` içerir.

### Adım 5: Geometriyi Doğrusal Hale Getirin
```csharp
var linear = geometry.ToLinearGeometry();
```
`ToLinearGeometry()` yöntemi tüm eğrileri düz çizgi segmentlerine dönüştürerek, orijinal geometrinin *doğrusal* bir versiyonunu üretir.

### Adım 6: Doğrusal Geometriyi Özelliğe Atayın
```csharp
feature.Geometry = linear;
```
Artık özellik, basitleştirilmiş, doğrusal geometriyi tutuyor.

### Adım 7: Özelliği Katmana Ekleyin
```csharp
layer.Add(feature);
```
Son olarak, özelliği KML katmanına ekliyoruz; `using` bloğu sona erdiğinde doğrusal geometri çıktı dosyasına yazılır.

## Yaygın Tuzaklar ve İpuçları
- **Yol ayırıcıları:** Çapraz platform yol oluşturma için `Path.Combine` kullanın.  
- **Büyük geometriler:** Çok karmaşık şekilleri doğrusal hale getirmek çok sayıda köşe oluşturabilir; daha az nokta gerekiyorsa doğrusal hale getirmeden sonra `Simplify()` kullanmayı düşünün.  
- **Sürücü seçimi:** Farklı bir çıktı formatına ihtiyacınız varsa `Drivers.Kml` yerine `Drivers.Shapefile`, `Drivers.GeoJson` vb. ile değiştirin ve dosya uzantısını buna göre ayarlayın.

## Sonuç
Bu öğreticide, Aspose.GIS for .NET kullanarak **geometriyi nasıl doğrusal hale getireceğinizi** ortamı kurmaktan doğrusal sonucu bir KML dosyasına yazmaya kadar ele aldık. Artık bu iş akışını haritalama uygulamaları, veri‑işleme hatları veya basitleştirilmiş geometrilere ihtiyaç duyan herhangi bir GIS‑ilişkili projeye entegre edebilirsiniz.

## Sık Sorulan Sorular
### Q: Aspose.GIS for .NET .NET Core ile uyumlu mu?
Evet, Aspose.GIS for .NET .NET Core ile uyumludur ve çapraz platform uygulamaları oluşturmanıza olanak tanır.

### Q: Aspose.GIS for .NET ile farklı GIS dosya formatlarıyla çalışabilir miyim?
Kesinlikle! Aspose.GIS, KML, Shapefile, GeoJSON ve daha fazlası dahil olmak üzere çeşitli GIS dosya formatlarını destekler.

### Q: Aspose.GIS mekansal işlemler ve analiz desteği sunuyor mu?
Evet, Aspose.GIS karmaşık coğrafi uzamsal görevleri yönetmek için geniş bir mekansal işlem ve analiz yetenekleri yelpazesi sunar.

### Q: Aspose.GIS for .NET için ücretsiz deneme mevcut mu?
Evet, ücretsiz denemeyi [Aspose web sitesinden](https://releases.aspose.com/) indirebilirsiniz.

### Q: Aspose.GIS için yardım ve destek nereden bulabilirim?
Topluluk ve Aspose destek ekibinden yardım almak için [Aspose.GIS forumunu](https://forum.aspose.com/c/gis/33) ziyaret edebilirsiniz.

## Sık Sorulan Sorular (Ek)

**S: 3D (Z) koordinatları içeren geometrileri doğrusal hale getirebilir miyim?**  
Evet, `ToLinearGeometry()` 2D ve 3D geometrilerle çalışır; Z değerleri sonuçtaki çizgi segmentlerinde korunur.

**S: Doğrusal hale getirme çıktı dosyasının boyutunu nasıl etkiler?**  
Eğrileri birçok kısa çizgi segmentine dönüştürmek dosya boyutunu artırabilir. Dosya boyutu bir sorun ise doğrusal hale getirmeden sonra `Simplify()` kullanın.

**S: Doğrusal hale getirirken segment uzunluğunu kontrol etmek mümkün mü?**  
Varsayılan yöntem dahili bir tolerans kullanır. Özel segmentasyon için `ToLinearGeometry()` çağırmadan önce eğrileri manuel olarak tessellate edebilirsiniz.

**Son Güncelleme:** 2025-12-21  
**Test Edilen Versiyon:** Aspose.GIS 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}