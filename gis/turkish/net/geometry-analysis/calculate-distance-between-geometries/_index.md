---
date: 2025-12-02
description: Aspose.GIS for .NET kullanarak geometriler arasındaki mesafeyi nasıl
  hesaplayacağınızı öğrenin. Bu adım‑adım kılavuz, Aspose.GIS'i nasıl kullanacağınızı,
  geometriye olan mesafeyi nasıl alacağınızı ve mesafe hesaplamalarını uygulamalarınıza
  nasıl entegre edeceğinizi gösterir.
linktitle: How to Calculate Distance Between Geometries
second_title: Aspose.GIS .NET API
title: Aspose.GIS ile Geometriler Arasındaki Mesafeyi Nasıl Hesaplayabilirsiniz
url: /tr/net/geometry-analysis/calculate-distance-between-geometries/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Geometriler Arasındaki Mesafeyi Aspose.GIS ile Nasıl Hesaplanır

## Giriş
İki mekansal nesne arasındaki **mesafeyi nasıl hesaplayacağınızı** bilmeniz gerektiğinde—ister bir yol ağı, teslimat bölgeleri, ister çevresel özellikler olsun—bu kılavuz tam size göre. .NET'te Aspose.GIS, mesafe hesaplamalarını basit, doğru ve yüksek performanslı bir şekilde sunar. Aspose.GIS'in **nasıl kullanılacağını**, basit geometriler oluşturmayı ve **GetDistanceTo** metodunu çağırarak aralarındaki mesafeyi elde etmeyi gösteren gerçek bir örnek üzerinden ilerleyeceğiz.

## Hızlı Yanıtlar
- **GIS'te “mesafe hesaplamak” ne anlama gelir?** İki geometri arasındaki en kısa (Öklid) mesafeyi döndürür.  
- **Hesaplamayı sağlayan Aspose.GIS sınıfı hangisidir?** `Geometry.GetDistanceTo(Geometry other)`.  
- **Geliştirme için lisansa ihtiyacım var mı?** Test için ücretsiz deneme sürümü yeterlidir; üretim ortamı için lisans gereklidir.  
- **3‑B geometriler için mesafe hesaplayabilir miyim?** Evet, Aspose.GIS 2‑B ve 3‑B hesaplamaları destekler.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.

## Coğrafi Programlamada Mesafe Hesaplaması Nedir?
Mesafe hesaplaması, iki geometriyi birbirine bağlayan en kısa çizgiyi ölçer. Yakınlık analizi, rotalama, kümeleme ve mekansal indeksleme gibi görevler için temel bir işlemdir.

## Neden Aspose.GIS ile Mesafe Hesaplaması Yapmalısınız?
- **Yüksek hassasiyet** – Double‑precision aritmetik kullanır.  
- **Sıfır bağımlılık** – Yerel GIS kütüphanelerine ihtiyaç duymaz.  
- **Çapraz platform** – Windows, Linux ve macOS üzerinde .NET Core/5+ ile çalışır.  
- **Zengin geometri modeli** – Noktalar, çizgiler, çokgenler ve çoklu‑geometrileri kutudan çıkar çıkmaz destekler.

## Önkoşullar
- **Aspose.GIS for .NET** yüklü (indir: [Aspose.GIS for .NET releases page](https://releases.aspose.com/gis/net/)).  
- C# ve .NET proje yapısı hakkında temel bilgi.  
- Visual Studio 2022 veya VS Code gibi bir geliştirme ortamı.

## Namespace'leri İçe Aktarın
Aspose.GIS'i kullanmaya başlamadan önce C# dosyanıza gerekli namespace'leri ekleyin:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Adım 1: Bir Polygon Geometrisi Oluşturun
```csharp
var polygon = new Polygon();
```
İlk olarak, daha sonra dikdörtgen bir alanı temsil edecek boş bir çokgen oluşturuyoruz.

### Adım 2: Polygon Dış Çevresini Tanımlayın
```csharp
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 1),
    new Point(1, 1),
    new Point(1, 0),
    new Point(0, 0),
});
```
Dış çevre, çokgenin sınırını tanımlayan kapalı bir nokta döngüsüdür. Bu örnekte 1 × 1 bir kare oluşturuyoruz.

### Adım 3: Bir LineString Geometrisi Oluşturun
```csharp
var line = new LineString();
```
`LineString`, birbirine bağlı çizgi segmentlerinden oluşan bir seridir. Bunu bir yol veya patika olarak kullanacağız.

### Adım 4: LineString'e Noktalar Ekleyin
```csharp
line.AddPoint(2, 0);
line.AddPoint(1, 3);
```
Bu iki nokta, çizgiye çokgenle kesişmeyen eğik bir şekil verir; bu da mesafe hesabını ilginç kılar.

### Adım 5: Mesafeyi Hesaplayın
```csharp
double distance = polygon.GetDistanceTo(line);
```
Burada `GetDistanceTo` metodunu çağırarak **geometriye olan mesafeyi** alıyoruz. Aspose.GIS, çokgenin kenarı ile çizgi arasındaki en kısa mesafeyi hesaplar.

### Adım 6: Sonucu Çıktılayın
```csharp
Console.WriteLine(distance.ToString("F")); // 0.63
```
Sonuç iki ondalık basamakla (`0.63`) yazdırılır. Bu değer, kare ile çizgi arasındaki minimum Öklid mesafesini temsil eder.

## Yaygın Kullanım Senaryoları
- **Lojistik:** Bir teslimat rotasına en yakın depoyu bulun.  
- **Çevre izleme:** Bir kirletici bulutunun korunan bir alandan ne kadar uzakta olduğunu ölçün.  
- **Şehir planlaması:** Önerilen altyapı ile mevcut yapıların arasındaki mesafeyi belirleyin.

## Sorun Giderme ve İpuçları
- **Koordinat sistemi önemlidir:** Mesafe hesaplamadan önce her iki geometrinin aynı CRS'yi (koordinat referans sistemi) kullandığından emin olun.  
- **Performans:** Büyük veri setleri için O(N²) karşılaştırmalardan kaçınmak amacıyla mekansal indeksleme (R‑tree) kullanın.  
- **Hassasiyet:** Jeodezik (büyük daire) mesafelere ihtiyacınız varsa, önce koordinatları uygun bir projeksiyona dönüştürün.

## SSS'ler
### Aspose.GIS for .NET tüm .NET framework'leriyle uyumlu mu?
Evet, Aspose.GIS for .NET .NET Framework 4.6 ve üzeri sürümlerle uyumludur.

### Aspose.GIS for .NET ile karmaşık mekansal analizler yapabilir miyim?
Kesinlikle! Aspose.GIS for .NET, gelişmiş mekansal analiz görevleri için geniş bir işlevsellik sunar.

### Aspose.GIS for .NET 2D ve 3D geometrileri destekliyor mu?
Evet, Aspose.GIS for .NET ile hem 2D hem de 3D geometrilerle çalışabilirsiniz.

### Aspose.GIS for .NET'i diğer GIS kütüphaneleriyle entegre edebilir miyim?
Aspose.GIS for .NET, diğer GIS kütüphaneleriyle birlikte çalışabilirlik sağlar ve ek işlevselliklerden yararlanmanıza imkan tanır.

### Aspose.GIS for .NET kullanıcıları için teknik destek mevcut mu?
Evet, Aspose.GIS for .NET kullanıcıları teknik desteğe Aspose [forumları](https://forum.aspose.com/c/gis/33) üzerinden erişebilir.

## Sık Sorulan Sorular

**S: `GetDistanceTo` tarafından döndürülen mesafe ne kadar doğrudur?**  
C: Metod, double‑precision aritmetik kullanır ve OGC Simple Features Specification'a uygun olarak tipik plan koordinatlar için sub‑metre doğruluk sağlar.

**S: `Point` ile `Polygon` arasında mesafe hesaplayabilir miyim?**  
C: Evet—sadece `point.GetDistanceTo(polygon)` (veya tersini) çağırın, Aspose.GIS en kısa mesafeyi döndürür.

**S: API toplu mesafe hesaplamalarını destekliyor mu?**  
C: Tek bir toplu metod bulunmamakla birlikte, geometri koleksiyonları üzerinde döngü kurarak aynı `GetDistanceTo` çağrısını verimli bir şekilde yeniden kullanabilirsiniz.

**S: Geometriler kesişirse ne olur?**  
C: Kesişen geometriler için metod `0.0` döndürür, çünkü en kısa mesafe sıfırdır.

**S: Her iki geometri üzerindeki en yakın noktaları elde etmenin bir yolu var mı?**  
C: Evet—`Geometry.GetNearestPoints(Geometry other)` metodunu kullanarak her iki geometri üzerindeki en yakın noktaları içeren bir tuple alabilirsiniz.

## Sonuç
Geometriler arasındaki mesafe hesabı, herhangi bir GIS‑entegre .NET uygulamasının temel bir işlemidir. Yukarıdaki adımları izleyerek **mesafeyi nasıl hesaplayacağınızı**, **Aspose** ile geometrileri nasıl oluşturup yöneteceğinizi ve **geometriye olan mesafeyi** tek bir metod çağrısıyla nasıl alacağınızı öğrendiniz. Farklı şekiller, koordinat sistemleri ve daha büyük veri setleriyle deneyler yaparak bu yeteneğin bir sonraki mekansal analiz projenizi nasıl güçlendirebileceğini keşfedin.

---

**Son Güncelleme:** 2025-12-02  
**Test Edilen Versiyon:** Aspose.GIS 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}