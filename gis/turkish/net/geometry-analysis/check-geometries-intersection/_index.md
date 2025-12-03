---
date: 2025-12-03
description: C#'ta çokgen geometrisi oluşturmayı ve Aspose.GIS for .NET'in Intersects
  yöntemiyle çakışan çokgenleri tespit etmeyi öğrenin.
language: tr
linktitle: Create Polygon Geometry C#
second_title: Aspose.GIS .NET API
title: C# ile Çokgen Geometrisi Oluşturun ve Aspose.GIS for .NET ile Kesişimi Kontrol
  Edin
url: /net/geometry-analysis/check-geometries-intersection/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Poligon Geometrisi C# Oluşturma ve Aspose.GIS for .NET ile Kesişimi Kontrol Etme

## Giriş
Eğer **polygon geometry C#** oluşturmanız ve iki şeklin çakışıp çakışmadığını hızlıca belirlemeniz gerekiyorsa, Aspose.GIS for .NET size temiz, yüksek‑performanslı bir API sunar. Bu rehberde, kütüphaneyi kurmaktan `Intersects` metodunu kullanarak **çakışan poligonları tespit** etmeye kadar tüm süreci adım adım göstereceğiz. Sonunda, sadece birkaç satır kodla .NET uygulamanıza poligon‑kesişme kontrolleri ekleyebileceksiniz.

## Hızlı Yanıtlar
- **Intersects yöntemi ne yapar?** İki geometri ortak bir alan paylaştığında `true` döner.  
- **Poligon sınıflarını hangi ad alanı içerir?** `Aspose.Gis.Geometries`.  
- **Geliştirme için lisansa ihtiyacım var mı?** Test için ücretsiz deneme çalışır; üretim için ticari lisans gereklidir.  
- **Bunu .NET Core / .NET 6+ ile kullanabilir miyim?** Evet, Aspose.GIS tüm modern .NET çalışma zamanlarını destekler.  
- **Örnek çalıştırma süresi ne kadar?** Tipik bir geliştirme makinesinde bir saniyeden az.

## “create polygon geometry C#” nedir?
C# içinde bir poligon geometrisi oluşturmak, Aspose.GIS tarafından sağlanan `Polygon` sınıfını (veya diğer geometri tiplerini) örnekleyip, şeklin köşe noktalarını tanımlayan `Point` nesnelerinden oluşan kapalı bir halka sağlamaktır. Oluşturulduktan sonra geometri, kesişim, içerme ve mesafe hesaplamaları gibi uzamsal işlemlerde kullanılabilir.

## Neden Aspose.GIS'i çakışan poligonları tespit etmek için kullanmalıyım?
- **Sıfır dış bağımlılık** – saf .NET kütüphanesi, yerel GIS kurulumları yok.  
- **Zengin uzamsal işlemler** – `Intersects`, `Disjoint`, `Contains` vb., hepsi kullanıma hazır.  
- **Yüksek doğruluk** – ortak kenarlar veya köşeler gibi kenar durumlarını sağlam bir şekilde işler.  
- **Çapraz platform** – .NET Core/5/6 ile Windows, Linux ve macOS'ta çalışır.

## Önkoşullar
Başlamadan önce şunların yüklü olduğundan emin olun:

1. **Aspose.GIS for .NET** yüklü (aşağıdaki adımlara bakın).  
2. Bir .NET geliştirme ortamı (Visual Studio, VS Code veya Rider).  
3. .NET Framework 4.6+ veya .NET Core 3.1+.

### Aspose.GIS for .NET Kurulumu
1. **İndirme Sayfasına Git:** En son araç setini edinmek için [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/) adresini ziyaret edin.  
2. **Araç Setini İndir:** Geliştirme ortamınızla uyumlu uygun sürümü seçin ve araç setini indirin.  
3. **Araç Setini Kurun:** Aspose.GIS for .NET'i geliştirme makinenize kurmak için verilen kurulum talimatlarını izleyin.

## Ad Alanlarını İçe Aktarma
Aspose.GIS for .NET ile çalışmaya başlamak için projenize gerekli ad alanlarını eklemeniz gerekir.

1. **Referansları Ekleyin:** Projenizde Aspose.GIS derlemesine referans ekleyin.  
2. **Ad Alanlarını İçe Aktarın:** Kod dosyanızda gerekli ad alanlarını içe aktarın. Aşağıdaki örnek için aşağıdaki ad alanlarını eklediğinizden emin olun:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Aspose.GIS ile polygon geometry C# nasıl oluşturulur?
Ortam hazır olduğuna göre, daha sonra çakışma testini yapacağımız iki basit poligon geometrisi oluşturalım.

### Adım 1: Geometrileri Tanımla
Bu adımda iki dikdörtgen alanı temsil eden poligonlar oluşturacaksınız. Köşe noktaları saat yönünde tanımlanır ve halkayı kapatmak için ilk nokta sonunda tekrar edilir.

```csharp
var geometry1 = new Polygon(new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 3),
    new Point(3, 3),
    new Point(3, 0),
    new Point(0, 0),
}));
var geometry2 = new Polygon(new LinearRing(new[]
{
    new Point(1, 1),
    new Point(1, 4),
    new Point(4, 4),
    new Point(4, 1),
    new Point(1, 1),
}));
```

### Adım 2: Çakışan poligonları tespit etmek için Intersects yöntemini kullan
Geometriler tanımlandıktan sonra `Intersects` metodunu çağırabiliriz. Bu metod **Intersects algoritmasını** kullanarak iki poligonun herhangi bir kısmının aynı alanda olup olmadığını kontrol eder.

```csharp
Console.WriteLine(geometry1.Intersects(geometry2)); // True
Console.WriteLine(geometry2.Intersects(geometry1)); // True
```

### Adım 3: Ayrık geometrileri kontrol et (intersect'in tersine)
İki şeklin **çakışmadığını** doğrulamanız gerekiyorsa, `Disjoint` metodu ters sonucu verir.

```csharp
// 'Disjoint' is opposite to 'Intersects'
Console.WriteLine(geometry1.Disjoint(geometry2)); // False
```

## Yaygın Sorunlar ve Çözümler
| Sorun | Neden Oluşur | Çözüm |
|-------|--------------|------|
| **Her zaman `false` döner** | Poligonlar kapalı değil (ilk nokta ≠ son nokta). | Koordinat dizisinin sonunda ilk noktanın tekrar edildiğinden emin olun. |
| **Kenarların temas etmesi için beklenmedik `true`** | `Intersects` ortak kenarları kesişen olarak kabul eder. | Kenar‑sadece tespiti gerekiyorsa `Touches` metodunu kullanın. |
| **Çok sayıda poligonla performans düşüşü** | Her çağrı tüm köşe çiftlerini kontrol eder. | Destekleniyorsa `GeometryCollection` veya uzamsal indeksleme (R‑tree) ile toplu işleyin. |

## Sıkça Sorulan Sorular

**S: Aspose.GIS for .NET'i diğer .NET framework'leriyle kullanabilir miyim?**  
C: Evet, Aspose.GIS for .NET .NET Core ve .NET Framework dahil olmak üzere çeşitli .NET framework'leriyle uyumludur.

**S: Aspose.GIS for .NET için ücretsiz bir deneme mevcut mu?**  
C: Evet, Aspose.GIS for .NET'in ücretsiz denemesine [buradan](https://releases.aspose.com/) ulaşabilirsiniz.

**S: Aspose.GIS for .NET için destek nereden bulunur?**  
C: Yardım almak ve toplulukla etkileşime geçmek için [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) adresini ziyaret edebilirsiniz.

**S: Aspose.GIS for .NET için geçici bir lisans alabilir miyim?**  
C: Evet, geçici lisansı [buradan](https://purchase.aspose.com/temporary-license/) temin edebilirsiniz.

**S: Aspose.GIS for .NET'in lisanslı sürümünü nereden satın alabilirim?**  
C: Lisanslı sürümü [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Son Güncelleme:** 2025-12-03  
**Test Edilen:** Aspose.GIS 24.11 for .NET  
**Yazar:** Aspose