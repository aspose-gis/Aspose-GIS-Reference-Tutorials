---
date: 2025-12-07
description: Aspose.GIS kullanarak .NET’te geometri uzunluğunu nasıl hesaplayacağınızı
  öğrenin, verimli mekansal veri işleme için. Kod örnekleriyle adım adım rehber.
language: tr
linktitle: Get Geometry Length
second_title: Aspose.GIS .NET API
title: Aspose.GIS ile .NET’te Geometrinin Uzunluğunu Nasıl Hesaplayabilirsiniz
url: /net/geometry-analysis/get-geometry-length/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET'te Aspose.GIS ile Geometri Uzunluğunu Hesaplama

## Giriş
Eğer .NET uygulamasında geometrik nesnelerin **uzunluğunu nasıl hesaplayacağınız** konusunda net ve pratik bir yol arıyorsanız, doğru yerdesiniz. Aspose.GIS for .NET, uzamsal hesaplamaları—örneğin çizgi uzunluğunu veya çokgen çevresini ölçmeyi—kolay ve yüksek performanslı hale getiren GIS odaklı zengin bir API seti sunar. Bu öğreticide, ortamı kurmaktan doğru uzunluk değerlerini döndüren C# kodunu yazmaya kadar tüm süreci adım adım inceleyeceğiz.

## Hızlı Yanıtlar
- **“GetLength()” ne döndürür?** Çizgiler için çizgi uzunluğunu; çokgenler için çevresini döndürür.  
- **Hangi ad alanı (namespace) gereklidir?** `Aspose.Gis.Geometries`.  
- **Bunu .NET 6 ile kullanabilir miyim?** Evet, Aspose.GIS .NET 5, .NET 6 ve üzerini destekler.  
- **Geliştirme için lisansa ihtiyacım var mı?** Değerlendirme için ücretsiz deneme yeterlidir; üretim için lisans gereklidir.  
- **Hesaplama birim‑bilincine sahip mi?** Uzunluk, koordinat sisteminin birimlerinde döndürülür (ör. projeksiyonlu CRS için metre).

## Ön Koşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

### 1. Aspose.GIS for .NET Kütüphanesi
İlk olarak, geliştirme ortamınıza Aspose.GIS for .NET kütüphanesini kurmuş olmanız gerekir. Henüz yapmadıysanız, [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/) sayfasından indirebilirsiniz.

### 2. .NET Geliştirme Ortamı
Makinenizde bir .NET geliştirme ortamının kurulu olduğundan emin olun. Bu, Visual Studio ya da başka bir uyumlu IDE'nin yüklü olmasını içerir.

### 3. C# Temel Bilgisi
Bu öğreticiyi takip edebilmek için C# programlama diline temel bir anlayışa sahip olmanız gereklidir.

## Ad Alanlarını (Namespaces) İçe Aktarma
Aspose.GIS for .NET tarafından sağlanan işlevselliği kullanabilmek için C# projenize gerekli ad alanlarını (namespaces) içe aktarmanız gerekir.

### Aspose.GIS Ad Alanını İçe Aktarma
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Geometri Uzunluğu Nedir?
`Geometry.GetLength()` bir geometri nesnesinin doğrusal ölçümünü döndüren bir yöntemdir. `LineString` için toplam çizgi uzunluğunu, `Polygon` için ise çevresini (tüm kenarların toplamı) verir. Bu yöntem, alttaki matematiği soyutlayarak daha üst düzey GIS mantığına odaklanmanızı sağlar.

## Uzunluk Hesaplamaları İçin Neden Aspose.GIS Kullanılmalı?
- **Harici bağımlılık yok** – saf .NET kütüphanesi, yerel DLL gerektirmez.  
- **Yüksek hassasiyet** – doğru sonuçlar için çift duyarlıklı (double) aritmetik kullanır.  
- **Çapraz platform** – .NET Core/5/6+ ile Windows, Linux ve macOS'ta çalışır.

## Adım‑Adım Kılavuz

### Adım 1: Geometri Nesneleri Oluşturma
İlk olarak, uzunluğunu hesaplamak istediğiniz şekilleri temsil eden geometri nesnelerini oluşturun. Bu, çizgileri, çokgenleri veya diğer geometrik şekilleri içerebilir.

```csharp
var line = new LineString();
line.AddPoint(0, 0);
line.AddPoint(2, 2);
line.AddPoint(2, 0);
```

### Adım 2: C#'ta Çizgi Uzunluğunu Nasıl Hesaplayabilirsiniz
Çizgi geometrisini oluşturduktan sonra, uzunluğunu `GetLength()` yöntemiyle hesaplayabilirsiniz. Bu, **calculate line length c#** işlemini tek bir kod satırıyla gösterir.

```csharp
Console.WriteLine("{0:F}", line.GetLength()); // Output: 4.83
```

### Adım 3: Çokgen Geometrisi Oluşturma
Benzer şekilde, `Polygon` ve `LinearRing` sınıflarını kullanarak çokgen geometri nesneleri oluşturabilirsiniz.

```csharp
var rectangle = new Polygon(new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 1),
    new Point(1, 1),
    new Point(1, 0),
    new Point(0, 0),
}));
```

### Adım 4: Bir Çokgenin Uzunluğunu Nasıl Alabilirsiniz
Çokgenler için `GetLength()` yöntemi çevreyi döndürür; bu, şeklin **how to get length** (uzunluğunu nasıl alacağınız) anlamına gelir.

```csharp
Console.WriteLine("{0:F}", rectangle.GetLength()); // Output: 4.00
```

## Yaygın Sorunlar ve Çözümleri
| Sorun | Çözüm |
|-------|----------|
| **Beklenmeyen sıfır uzunluk** | Geometrinin koordinat sisteminin sağladığınız verilerle eşleştiğini doğrulayın; yinelenen noktalar sıfır‑uzunluklu segmentlere neden olabilir. |
| **Yanlış birimler** | `GetLength()`'in CRS birimlerindeki değerleri döndürdüğünü unutmayın. Gerekirse metre/feet'e dönüştürün. |
| **Büyük veri setlerinde performans** | Mümkün olduğunda geometri nesnelerini yeniden kullanın ve sık döngüler içinde binlerce geçici nokta oluşturmaktan kaçının. |

## Sıkça Sorulan Sorular

**S: Aspose.GIS for .NET tüm .NET framework'leriyle uyumlu mu?**  
C: Aspose.GIS for .NET, .NET Framework 4.6.1 veya daha sonraki sürümlerle, ayrıca .NET 5/6/7 ile uyumludur.

**S: Aspose.GIS for .NET'i satın almadan deneyebilir miyim?**  
C: Evet, Aspose.GIS for .NET'in ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) alabilirsiniz.

**S: Aspose.GIS for .NET için desteği nereden bulabilirim?**  
C: Aspose.GIS topluluk forumundan [burada](https://forum.aspose.com/c/gis/33) destek ve yardım alabilirsiniz.

**S: Aspose.GIS for .NET için geçici bir lisans nasıl alabilirim?**  
C: Geçici lisansı [buradan](https://purchase.aspose.com/temporary-license/) edinebilirsiniz.

**S: Geometri uzunluğu hesaplamaları için çıktı formatını özelleştirebilir miyim?**  
C: Evet, Aspose.GIS for .NET, gereksinimlerinize göre çıktı formatını özelleştirmenize olanak tanıyan çeşitli biçimlendirme seçenekleri sunar.

## Sonuç
Bu öğreticide, Aspose.GIS for .NET kullanarak çizgi ve çokgen geometrilerinin **uzunluğunu nasıl hesaplayacağınızı** ele aldık. Adım‑adım örnekleri izleyerek, artık herhangi bir .NET uygulamasına, ister masaüstü GIS aracı, ister web servisi, ister arka uç veri işleme hattı olsun, kesin uzamsal ölçümler entegre edebilirsiniz.

---

**Son Güncelleme:** 2025-12-07  
**Test Edilen Versiyon:** Aspose.GIS 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}