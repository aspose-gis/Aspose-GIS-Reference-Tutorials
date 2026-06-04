---
date: 2026-02-05
description: C# kullanarak bir noktanın bir çokgenin içinde olup olmadığını nasıl
  belirleyeceğinizi öğrenin. Bu Aspose.GIS .NET öğreticisi, geometri içinde nokta
  kontrolleri, coğrafi veri analizi .NET teknikleri ve Aspose.GIS .NET ile en iyi
  uygulamaları kapsar.
linktitle: point inside polygon c# – Check Geometry Contains Another
second_title: Aspose.GIS .NET API
title: nokta çokgen içinde c# – Geometri başka birini içeriyor mu kontrol et
url: /tr/net/geometry-analysis/check-geometry-contains-another/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# c# içinde nokta poligon – Geometri İçeriyor mu Kontrolü

## Giriiş
Eğer **jeo-uzamsal analiz .net** projeleri üzerinde çalışıyorsanız, en yaygın görevlerden biri belirli bir konumun (bir noktanın) tanımlı bir alanın (bir poligonun) içinde olup olmadığının belirlenmesidir. Bu öğreticide, **Aspose.GIS .NET** kütüphanesini kullanarak **point inside polygon c#** kontrol adım adım nasıl kaydedileceğiniz. Haritalama uygulaması, dağınık temelli hizmet veya uzamsal kapsama mantığı çerçevesinde herhangi bir çözüm geliştiriliyor olun, aşağıdaki kodda sizi dakikalar içinde çalışır duruma gelecektir.

## Hızlı Yanıtlar
- **“point inside polygon c#” ne anlama geliyor?** Bir nokta geometrisinin tamamen bir poligon geometrisinin içinde yer alması durumunda doğru (true) dönen bir uzamsal sorgudur.
- **Bu .NET'te hangi kütüphane bulunur?** Aspose.GIS for .NET, `SpatiallyContains` ve `Within` yöntemlerini sunar.
- **Lisans gerekir mi?** Ücretsiz deneme mevcuttur; üretim kullanımı için ticari lisans gereklidir.
- **.NET Core / .NET 6+ ile uyumlu mu?** Evet – Aspose.GIS modern .NET çalışma zamanlarını tam olarak destekleme.
- **Uygulama ne kadar sürer?** Kodu kopyalayıp örnek kullanarak yaklaşık 10dakika devam eder.

## C# poligonunun içindeki nokta nedir?
Bir *point inside polygon* testi, bir `Nokta' nesnesinin koordinatlarının bir `Polygon` nesnesinin yarıçapının içinde olup olmadığını kontrol eder. C#'ta bu genellikle **Ray Casting** veya **Sarım Numarası** eklentilerini uygulayan geometri uygulamalarıyla yapılır. Aspose.GIS bu ayrıntıları soyutlayarak basit bir API sunar: `polygon.SpatiallyContains(point)`.

## Nokta kontrolleri içeren geometri için neden Aspose.GIS .NET kullanmalısınız?
- **Zengin geometri modeli** – Poligonlar, çoklu poligonlar, doğrusal halkalar ve daha fazlasının.
- **Yüksek performanslı uzamsal işlemler** – Büyük veri kitapları için optimize edilmiştir.
- **Çapraz platform** – .NET Framework, .NET Core ve .NET5/6+ üzerinde çalışır.
- **Kapsamlı dokümantasyon** – **jeouzaysal analiz .net** senaryoları için çok sayıda örnek içerir.

## Çokgen içindeki nokta için Yaygın Kullanım Durumları c#
- **Geofencing**: Bir cihaz önceden tanımlanmış bir alanda kayıtlı veya olduğunda eylemler tetiklenir.
- **Harita görselleştirme**: Kullanıcı‑seçili bir noktayı kapsayan bölge vurgulanır.
- **Uzaysal analitik**: Veri kitapları, yalnızca bir çalışma dosyası içinde kalan kayıtlarla filtrelenir.
- **Teslimat rotası**: Bir teslimat adresinin hizmet bölgesi içinde olup olmadığı doğrulanır.

## Önkoşullar
Başlamadan önce programın kuruluşunun olduğundan emin olun:

1. **.NET geliştirme ortamı** – .NET6 SDK (veya daha yeni) yüklü.
2. **Aspose.GIS for .NET** – Resmi sürüm sürümünün indirilmesi ve projenize NuGet paketi olarak eklenmesi.
3. **Temel C# bilgisi** – Sınıflar, nesneler ve konsol uygulamaları hakkında temel bilgiler.

### 1. .NET Geliştirme Ortamı Kurulumu
Makinenizde çalışan bir .NET geliştirme ortamının kurulu olduğundan emin olun. Bu, .NET SDK’nın doğru şekilde yüklü ve ele alınmasını içerir.

### 2. Aspose.GIS Kurulumu
Aspose.GIS for .NET’i, sürüm sürümünün [burada](https://releases.aspose.com/gis/net/) kütüphaneyi indirerek yüklenir. Belgelendirmede verilen kurulum talimatlarını [burada](https://reference.aspose.com/gis/net/) izleyerek Aspose.GIS'i projenize entegre edin.

### 3. Temel C# Anlayışı
Aspose.GIS for .NET esas olarak C# ile paylaşıldığında, C# programlama diline dair bilgi alın.

## Ad Alanlarını İçe Aktar
C# projenizde Aspose.GIS işlevselliğini kullanmak için gerekli ad alanlarını içe aktarın:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Adım 1: Geometri Nesnelerini Tanımlayın
İlk olarak, Aspose.GIS sınıflarını kullanarak geometri nesnelerini tanımlayın. Burada dış halkalı ve iç halkalı (bir delik) bir poligon ve ardından kapsama testini yapacağımız bir nokta oluşturuyoruz.
```csharp
var geometry1 = new Polygon();
geometry1.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 4),
    new Point(4, 4),
    new Point(4, 0),
    new Point(0, 0),
});
geometry1.AddInteriorRing(new LinearRing(new[]
{
    new Point(1, 1),
    new Point(1, 3),
    new Point(3, 3),
    new Point(3, 1),
    new Point(1, 1),
}));
var geometry2 = new Point(2, 2);
```

## Adım 2: Mekansal Kapsamı Kontrol Edin
Sonra, poligon **geometry1**’in nokta **geometry2**’yi içerip içermediğini kontrol edin. `SpatiallyContains` metodu, nokta iç halkada (delikte) bulunduğu için `false` döndürür.
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry2)); // False
```

## Adım 3: Başka Bir Geometri Tanımlayın
Şimdi, dış halkada ama iç halkanın dışında kalan ikinci bir nokta tanımlıyoruz.
```csharp
var geometry3 = new Point(0.5, 0.5);
```

## Adım 4: Mekansal Kapsamı Tekrar Kontrol Edin
Yeni nokta ile aynı kapsama kontrolünü çalıştırdığınızda `true` döner ve noktanın poligonun dış sınırı içinde olduğunu doğrular.
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry3)); // True
```

## Adım 5: Eşdeğer İşlevsellik
Aspose.GIS ayrıca ters metot olan `Within`’ı da sağlar. Aşağıdaki satır, `geometry3.Within(geometry1)` ifadesinin `geometry1.SpatiallyContains(geometry3)` ile aynı sonucu verdiğini gösterir.
```csharp
Console.WriteLine(geometry3.Within(geometry1)); // True
```

## Sık Karşılaşılan Sorunlar ve Çözümler
| Sorun | Neden Oluşur | Çözüm |

|-------|----------------|-----|

| **Beklenmeyen `false` sonuç** | Nokta, çokgenin bir deliğinin (iç halkasının) içinde yer alıyor. | Doğru çokgene karşı test yaptığınızdan emin olun veya deliksiz basit çokgenler için `geometry1.ExteriorRing` kullanın. |

| **NullReferenceException** | `SpatiallyContains` çağrılmadan önce geometri nesneleri başlatılmamış. | Mekansal yöntemleri çağırmadan önce hem çokgen hem de nokta nesnelerini örnekleyin. |

| **Büyük veri kümelerinde performans yavaşlaması** | Döngüler içinde tekrar tekrar geometri nesneleri oluşturuluyor. | Geometri örneklerini yeniden kullanın veya `GeometryCollection` kullanarak toplu işlem yapın. |

## Sıkça Sorulan Sorular

**S: Aspose.GIS, .NET Core ile uyumlu mu?**
C: Evet, Aspose.GIS, .NET Core'u tam olarak destekleyerek farklı platformlarda coğrafi bilgi sistemleri uygulamaları geliştirmenize olanak tanır.

**S: Aspose.GIS kullanarak coğrafi bilgi sistemleri analizi yapabilir miyim?**
C: Kesinlikle, Aspose.GIS, mekansal sorgular, mesafe hesaplamaları ve geometri manipülasyonları dahil olmak üzere coğrafi bilgi sistemleri analizi için çeşitli işlevler sunar.

**S: Aspose.GIS için güncellemeler ne sıklıkla yayınlanıyor?**
C: Aspose.GIS, performansı iyileştirmek, yeni özellikler eklemek ve bildirilen sorunları gidermek için düzenli olarak güncellemeler yayınlar. Yayın sayfasını ziyaret ederek güncel kalabilirsiniz.

**S: Aspose.GIS kullanıcıları için bir topluluk forumu var mı?**
C: Evet, diğer kullanıcılarla bağlantı kurmak, sorular sormak ve deneyimlerinizi paylaşmak için Aspose.GIS topluluk forumuna [buradan](https://forum.aspose.com/c/gis/33) katılabilirsiniz.

**S: Satın almadan önce Aspose.GIS'i deneyebilir miyim?**
C: Elbette, [buradan](https://releases.aspose.com/) ücretsiz deneme sürümünü indirerek Aspose.GIS'i keşfedebilirsiniz.

**S: Tam olarak poligon kenarında bulunan bir noktayı test edersem ne olur?**
C: Aspose.GIS, `SpatiallyContains` yöntemi için sınır üzerindeki noktaları **içeride** olarak ele alır. Farklı bir davranışa ihtiyacınız varsa `Touches` yöntemini kullanın.

## Sonuç
Bu kılavuzda, Aspose.GIS for .NET kullanarak pratik bir **poligon içindeki nokta c#** çözümünü gösterdik. Geometrilerinizi tanımlayıp `SpatiallyContains` (veya `Within`) yöntemini kullanarak uzamsal kapsamlı sorularıa hızlı yanıt sunumu, **coğrafi uzamsal analiz .net** iş akışınızın kritik bir bölümünü kolayca tamamlayabilirsiniz. Daha büyük veri kitapları, farklı geometri tipleriyle denemeler yapın ve bu kontrolleri uzaklık programlamaları veya uzamsal indeksleme gibi diğer Aspose.GIS yeteneğiyle birleştirin.

---

**Son Güncelleme:** 2026-02-05
**Şunlarla test edilmiştir:** Aspose.GIS 24.11 for .NET
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}