---
date: 2025-12-09
description: Aspose.GIS for .NET kullanarak bir noktanın çokgen içinde olup olmadığını
  nasıl kontrol edeceğinizi öğrenin. Yüzeydeki noktayı alma, C# ile çokgen oluşturma
  ve çokgen üzerindeki noktayı elde etme adım adım rehberi.
linktitle: Check Point Inside Polygon and Get Point on Surface
second_title: Aspose.GIS .NET API
title: Poligon İçindeki Noktayı Kontrol Et ve Yüzeydeki Noktayı Al
url: /tr/net/geometry-analysis/get-point-on-geometry-surface/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Poligon İçinde Nokta Kontrolü ve Yüzey Üzerinde Nokta Alma

## Giriş
Bu öğreticide Aspose.GIS for .NET ile **poligon içinde nokta kontrolünün** nasıl yapılacağını ve ayrıca bir geometrinin **yüzeyindeki noktayı** nasıl alacağınızı öğreneceksiniz. C#'ta bir poligon oluşturmayı, poligonun yüzeyinde bulunan bir noktayı almaya ve bu noktanın gerçekten poligon içinde olup olmadığını doğrulamaya adım adım geçeceğiz. Sonunda, herhangi bir .NET coğrafi uygulamasına ekleyebileceğiniz hazır bir kod parçacığına sahip olacaksınız.

## Hızlı Yanıtlar
- **“check point inside polygon” ne anlama geliyor?** Verilen bir koordinatın bir poligon geometrisinin sınırları içinde olup olmadığını doğrular.  
- **Hangi yöntem poligonun iç kısmında bir nokta döndürür?** `GetPointOnSurface()` poligon içinde olduğundan emin olunan bir nokta döndürür.  
- **Örneği çalıştırmak için lisansa ihtiyacım var mı?** Değerlendirme için ücretsiz deneme çalışır; üretim için tam lisans gereklidir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework, .NET Core ve .NET Standard hepsi uyumludur.  
- **Uygulamanın süresi ne kadar?** Kopyalama, derleme ve çalıştırma yaklaşık 5‑10 dakika sürer.

## Ön Koşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

### Ortam Kurulumu
1. Aspose.GIS for .NET'i kurun: Aspose.GIS for .NET kütüphanesini [buradan](https://releases.aspose.com/gis/net/) indirin ve kurun.  
2. Geliştirme Ortamınızı Kurun: .NET programlaması için çalışan bir geliştirme ortamına sahip olduğunuzdan emin olun. Yoksa Visual Studio ya da tercih ettiğiniz başka bir .NET geliştirme ortamını kurabilirsiniz.  
3. C# Temel Bilgisi: C# programlama dilinin temellerine hâlâ aşina değilseniz, kendinizi bu konuda geliştirin.  
4. Belgelere Erişim: Öğretici boyunca başvurmak için [belgelere](https://reference.aspose.com/gis/net/) ulaşılabilir bir yerde tutun.

## Ad Alanlarını İçe Aktarın
Uygulamaya geçmeden önce gerekli ad alanlarını içe aktararak başlayalım:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Ortamı kurup gerekli ad alanlarını içe aktardığımıza göre, örneği daha iyi anlamak için birden fazla adıma ayıralım.

## Poligon Nasıl Oluşturulur C#  

İlk olarak **bir poligon** geometrisi oluşturmamız gerekir. Poligonun dış halkasını köşelerini belirterek tanımlarız.

```csharp
var polygon = new Polygon();
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 1),
    new Point(1, 1),
    new Point(0, 0),
});
```

## Yüzey Üzerinde Nokta Nasıl Alınır  

Sonra, `GetPointOnSurface()` yöntemiyle poligonun yüzeyinde bir nokta alırız. Bu **yüzey üzerindeki nokta alma** adımıdır.

```csharp
IPoint pointOnSurface = polygon.GetPointOnSurface();
```

## Poligon İçinde Nokta Nasıl Kontrol Edilir  

Alınan noktanın poligon içinde olup olmadığını `SpatiallyContains()` yöntemiyle doğrulayabiliriz. Bu **poligon üzerindeki noktayı alma** ve ardından kontrol etme sürecini gösterir.

```csharp
Console.WriteLine(polygon.SpatiallyContains(pointOnSurface)); // True
```

## Yaygın Sorunlar ve Çözümler
- **Boş poligon** – Dış halkanın en az üç farklı köşesi olduğundan emin olun; aksi takdirde `GetPointOnSurface()` tanımsız bir nokta döndürebilir.  
- **Saat yönü vs. Saat yönünün tersine** – Halkanın yönü içerik kontrolünü etkilemez, ancak tutarlı bir yön sırası diğer uzamsal işlemlerde yardımcı olur.  
- **Koordinat Sistemi** – Örnek basit bir Kartezyen düzlem kullanır; gerçek dünya koordinatlarıyla çalışırken CRS (koordinat referans sistemi) doğru tanımlandığından emin olun.

## Sonuç
Bu öğreticide Aspose.GIS for .NET kullanarak **poligon içinde nokta kontrolünü** nasıl yapacağımızı, **yüzey üzerindeki bir nokta** elde etmeyi ve bu noktanın içeride olup olmadığını doğrulamayı öğrendik. Aspose.GIS ile coğrafi verileri işlemek etkili ve basit hale gelir, geliştiricileri sağlam coğrafi uygulamalar geliştirmeye güç verir.

## SSS
### Aspose.GIS diğer .NET çerçeveleriyle uyumlu mu?
Evet, Aspose.GIS .NET Framework, .NET Core ve .NET Standard dahil olmak üzere çeşitli .NET çerçevelerini destekler.

### Satın almadan önce Aspose.GIS'i deneyebilir miyim?
Evet, Aspose.GIS'in ücretsiz denemesini [buradan](https://releases.aspose.com/) indirebilirsiniz.

### Aspose.GIS için destek nasıl alabilirim?
Destek almak ve diğer kullanıcılar ve geliştiricilerle etkileşimde bulunmak için Aspose.GIS forumunu [buradan](https://forum.aspose.com/c/gis/33) ziyaret edebilirsiniz.

### Aspose.GIS geçici lisanslar sunuyor mu?
Evet, Aspose.GIS için geçici lisansları [buradan](https://purchase.aspose.com/temporary-license/) temin edebilirsiniz.

### Aspose.GIS'i nereden satın alabilirim?
Aspose.GIS'i satın alma sayfasından [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

**Ek Soru‑Cevap**

**S:** Büyük poligon veri setlerini yönetmenin en iyi yolu nedir?  
**C:** Geometrileri tembel (lazy) yükleyin ve bellek yükünü azaltmak için tek bir `GeometryFactory` örneğini yeniden kullanın.

**S:** Yüzey üzerinde birden fazla nokta alabilir miyim?  
**C:** `GetPointOnSurface()` tek bir iç nokta döndürür. Birden fazla iç nokta üretmek için poligonun sınırlayıcı kutusu içinde rastgele nokta üreteci kullanabilir ve her birini `SpatiallyContains()` ile test edebilirsiniz.

**S:** Oluşturulduktan sonra poligonu shapefile olarak dışa aktarmak mümkün mü?  
**C:** Evet, Aspose.GIS `FeatureSet` ve `ShapefileWriter` sınıflarını sağlayarak geometrileri Shapefile formatına yazmanıza olanak tanır.

---

**Last Updated:** 2025-12-09  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
