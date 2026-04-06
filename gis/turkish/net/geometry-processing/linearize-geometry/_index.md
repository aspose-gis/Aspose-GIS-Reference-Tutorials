---
date: 2026-04-06
description: Aspose.GIS for .NET ile eğrileri çizgilere dönüştürmeyi ve geometrileri
  doğrusal hâle getirmeyi öğrenin; böylece .NET uygulamalarınızda hızlı coğrafi veri
  işleme ve analizi sağlayabilirsiniz.
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS linearize geometry
linktitle: Geometriyi Doğrusallaştır
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET kullanarak Eğrileri Çizgilere Dönüştür
url: /tr/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET kullanarak Eğrileri Çizgilere Dönüştürme

## Giriş
Haritalama, mekânsal analiz veya veri‑değişim görevleri için **eğrileri çizgilere dönüştürmeniz** gerekiyorsa, Aspose.GIS for .NET size temiz ve programatik bir yol sunar. Bu öğreticide, karmaşık bir geometriyi—eğriler ve birleşik şekiller içeren—herhangi bir GIS sistemiyle çalışabilen basit bir çizgi temsiline nasıl dönüştüreceğinizi gösteren eksiksiz, gerçek‑dünya bir örnek üzerinden adım adım ilerleyeceğiz.

## Hızlı Yanıtlar
- **Bir geometriyi doğrusal hâle getirmek ne anlama gelir?** Eğrileri ve karmaşık şekilleri düz‑çizgi segmentlerine dönüştürmek.  
- **Neden Aspose.GIS kullanılmalı?** Onlarca GIS formatını destekler ve geometri dönüşümünü dış araçlara ihtiyaç duymadan gerçekleştirir.  
- **Önkoşullar?** .NET Framework veya .NET Core, Visual Studio ve Aspose.GIS kütüphanesi.  
- **Örnek ne kadar sürer?** Kütüphane kurulduktan sonra beş dakikadan az bir sürede çalışır.  
- **Diğer formatlara kaydedebilir miyim?** Evet—KML sürücüsünü Shapefile, GeoJSON vb. ile değiştirin.

## Geometriyi Doğrusal Hale Getirmek Nedir?
Geometriyi doğrusal hâle getirmek, herhangi bir eğri veya birleşik şekli bir dizi düz‑çizgi segmentine (bir “doğrusal geometri”) bölmek anlamına gelir. Bu, yalnızca çizgi ve nokta anlayan araçlarla render, analiz ve birlikte çalışabilirliği basitleştirir.

## Neden Eğrileri Çizgilere Dönüştürülür?
- **Performans:** Doğrusal geometriler daha hızlı render edilir ve sorgulanır.  
- **Uyumluluk:** Birçok GIS platformu (ör. eski harita servisleri) yalnızca doğrusal özellikleri kabul eder.  
- **Basitleştirme:** Küçük ön izlemeler, ön izleme görselleri oluşturma veya doğrusal girdi gerektiren algoritmalara veri besleme için kullanışlıdır.

## Önkoşullar
Kodlamaya başlamadan önce şunların kurulu olduğundan emin olun:

1. **Aspose.GIS for .NET** – [Aspose.GIS web sitesinden](https://releases.aspose.com/gis/net/) indirin.  
2. **.NET Framework** (veya .NET Core) geliştirme makinenizde kurulu olmalı.  
3. **Visual Studio** (veya C# uyumlu herhangi bir IDE) örnek kodu yazmak ve çalıştırmak için.

## Ad Alanlarını İçe Aktarın
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
Bu örnek sonucu bir KML dosyasına yazacaktır:
```csharp
using Aspose.GIS.Kml;
```

## Eğrileri Çizgilere Dönüştürme – Adım‑Adım Kılavuz
Aşağıda, **eğrileri çizgilere nasıl dönüştüreceğinizi** ve her adımın neden önemli olduğunu açıklayan kod satırlarının ayrıntılı bir yürütmesi yer almaktadır.

### Adım 1: Çıktı Yolunu Tanımlayın
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
`"Your Document Directory"` ifadesini KML dosyasının kaydedileceği klasörle değiştirin.

### Adım 2: Çıktı Dosyası İçin Bir Katman Oluşturun
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```
*Katman*, coğrafi özelliklerin bir konteyneridir. Burada doğrusal hâle getirilmiş geometrimizi tutacak yeni bir KML katmanı oluşturuyoruz.

### Adım 3: Yeni Bir Özellik (Feature) Oluşturun
```csharp
var feature = layer.ConstructFeature();
```
*Özellik*, tek bir coğrafi nesneyi (nokta, çizgi, çokgen vb.) temsil eder. Doğrusal geometrimizi bu özelliğe ekleyeceğiz.

### Adım 4: Orijinal Karmaşık Geometriyi Tanımlayın
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```
Well‑Known Text (WKT) dizesinden bir geometri oluşturuyoruz. Bu örnek bir `LineString`, bir `CompoundCurve` ve bir `CircularString` içeriyor—eğrileri çizgilere dönüştürmeyi göstermek için ideal.

### Adım 5: Geometriyi Doğrusal Hale Getirin
```csharp
var linear = geometry.ToLinearGeometry();
```
`ToLinearGeometry()` yöntemi, tüm eğrileri düz‑çizgi segmentlerine dönüştürerek orijinal geometrinin *doğrusal* bir versiyonunu üretir.

### Adım 6: Doğrusal Geometriyi Özelliğe Atayın
```csharp
feature.Geometry = linear;
```
Artık özellik, sadeleştirilmiş doğrusal geometriyi tutuyor.

### Adım 7: Özelliği Katmana Ekleyin
```csharp
layer.Add(feature);
```
Son olarak, özelliği KML katmanına ekliyoruz; `using` bloğu sona erdiğinde doğrusal geometri çıktı dosyasına yazılır.

## Yaygın Tuzaklar ve İpuçları
- **Yol ayırıcıları:** Çapraz‑platform yol oluşturmak için `Path.Combine` kullanın.  
- **Büyük geometriler:** Çok karmaşık şekilleri doğrusal hâle getirmek çok sayıda köşe oluşturabilir; daha az nokta isterseniz doğrusal hâle getirdikten sonra `Simplify()` kullanmayı düşünün.  
- **Sürücü seçimi:** Farklı bir çıktı formatına ihtiyacınız varsa `Drivers.Kml` yerine `Drivers.Shapefile`, `Drivers.GeoJson` vb. ile değiştirin ve dosya uzantısını buna göre ayarlayın.

## Sıkça Sorulan Sorular (Geliştirilmiş)

**S: Aspose.GIS for .NET .NET Core ile uyumlu mu?**  
C: Evet, Aspose.GIS for .NET .NET Core ile çalışır ve çapraz‑platform uygulamalar oluşturmanıza olanak tanır.

**S: Aspose.GIS for .NET farklı GIS dosya formatlarıyla çalışabilir mi?**  
C: Kesinlikle! Aspose.GIS KML, Shapefile, GeoJSON ve birçok diğer formatı destekler.

**S: Aspose.GIS mekânsal işlemler ve analizler için destek sağlıyor mu?**  
C: Evet, karmaşık coğrafi görevleri yönetmek için geniş bir mekânsal işlem ve analiz yetenekleri sunar.

**S: Aspose.GIS for .NET için ücretsiz deneme sürümü var mı?**  
C: Evet, ücretsiz deneme sürümünü [Aspose web sitesinden](https://releases.aspose.com/) indirebilirsiniz.

**S: Aspose.GIS için yardım ve destek nereden bulunur?**  
C: Topluluk ve Aspose destek ekibinden yardım almak için [Aspose.GIS forumunu](https://forum.aspose.com/c/gis/33) ziyaret edin.

**Ek Soru‑Cevap**

**S: 3D (Z) koordinatları içeren geometrileri doğrusal hâle getirebilir miyim?**  
C: Evet, `ToLinearGeometry()` hem 2D hem de 3D geometrilerle çalışır; Z değerleri sonuçtaki çizgi segmentlerinde korunur.

**S: Doğrusal hâle getirme çıktı dosyasının boyutunu nasıl etkiler?**  
C: Eğrileri çok sayıda kısa çizgi segmentine dönüştürmek dosya boyutunu artırabilir. Dosya boyutu bir endişe ise doğrusal hâle getirdikten sonra `Simplify()` kullanın.

**S: Doğrusal hâle getirirken segment uzunluğunu kontrol etmek mümkün mü?**  
C: Varsayılan yöntem dahili bir tolerans kullanır. Özel segmentasyon istiyorsanız, `ToLinearGeometry()` çağrısından önce eğrileri manuel olarak tessellate edebilirsiniz.

## Sonuç
Bu öğreticide, Aspose.GIS for .NET kullanarak **eğrileri çizgilere nasıl dönüştüreceğinizi**, ortamı kurmaktan doğrusal sonucu bir KML dosyasına yazmaya kadar adım adım ele aldık. Artık bu iş akışını haritalama uygulamaları, veri‑işleme hatları veya basitleştirilmiş geometriler gerektiren herhangi bir GIS‑ile ilgili projeye entegre edebilirsiniz.

---

**Son Güncelleme:** 2026-04-06  
**Test Edilen Sürüm:** Aspose.GIS 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}