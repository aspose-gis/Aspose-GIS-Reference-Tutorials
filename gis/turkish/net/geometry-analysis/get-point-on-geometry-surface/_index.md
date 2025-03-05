---
title: Geometri Yüzeyinde Nokta Alma
linktitle: Geometri Yüzeyinde Nokta Alma
second_title: Aspose.GIS .NET API'si
description: Aspose.GIS for .NET'i kullanarak coğrafi verilerle verimli bir şekilde nasıl çalışacağınızı öğrenin. Adım adım kılavuz ve SSS'ler dahildir.
type: docs
weight: 25
url: /tr/net/geometry-analysis/get-point-on-geometry-surface/
---
## giriiş
Bu derste, geometrilerle çalışmak ve yüzeylerindeki noktaları almak için Aspose.GIS for .NET'i nasıl kullanabileceğimizi keşfedeceğiz. Aspose.GIS, .NET uygulamalarında coğrafi veri işleme, manipülasyon ve görselleştirme için çeşitli işlevler sağlayan güçlü bir kütüphanedir.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
### Ortam Kurulumu
1. Aspose.GIS for .NET'i yükleyin: Aspose.GIS for .NET kitaplığını şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/gis/net/).
2. Geliştirme Ortamınızı Kurun: .NET programlama için çalışan bir geliştirme ortamına sahip olduğunuzdan emin olun. Değilse, Visual Studio'yu veya tercih ettiğiniz başka bir .NET geliştirme ortamını kurabilirsiniz.
3. Temel C# Bilgisi: Henüz bilgi sahibi değilseniz, C# programlama dilinin temellerine aşina olun.
4.  Dokümantasyona Erişim:[dokümantasyon](https://reference.aspose.com/gis/net/) eğitim boyunca referans olması açısından kullanışlıdır.

## Ad Alanlarını İçe Aktar
Uygulamaya geçmeden önce gerekli ad alanlarını içe aktararak başlayalım:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Artık ortamımızı kurduğumuza ve gerekli ad alanlarını içe aktardığımıza göre, daha iyi anlamak için örneği birden çok adıma ayıralım.
## Adım 1: Çokgen Oluşturun
Öncelikle çokgen geometrisi oluşturmamız gerekiyor. Çokgenin dış halkasını köşelerini belirterek tanımlarız.
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
## Adım 2: Yüzeyde Puan Alın
Daha sonra poligonun yüzeyindeki bir noktayı kullanarak alırız.`GetPointOnSurface()` yöntem.
```csharp
IPoint pointOnSurface = polygon.GetPointOnSurface();
```
## Adım 3: Çokgenin İçindeki Noktayı Doğrulayın
 Alınan noktanın poligonun içinde olup olmadığını aşağıdaki komutu kullanarak doğrulayabiliriz:`SpatiallyContains()` yöntem.
```csharp
Console.WriteLine(polygon.SpatiallyContains(pointOnSurface)); // Doğru
```

## Çözüm
Bu eğitimde, çokgen geometrisinin yüzeyinde bir nokta elde etmek ve bu noktanın çokgen içindeki yerini doğrulamak için Aspose.GIS for .NET'i nasıl kullanacağımızı öğrendik. Aspose.GIS ile jeo-uzamsal verilerin işlenmesi verimli ve kolay hale geliyor ve geliştiricilerin sağlam coğrafi-uzamsal uygulamalar geliştirmesine olanak tanıyor.
## SSS'ler
### Aspose.GIS diğer .NET çerçeveleriyle uyumlu mu?
Evet, Aspose.GIS, .NET Framework, .NET Core ve .NET Standard dahil olmak üzere çeşitli .NET çerçevelerini destekler.
### Satın almadan önce Aspose.GIS'i deneyebilir miyim?
 Evet, Aspose.GIS'in ücretsiz deneme sürümünü şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/).
### Aspose.GIS için nasıl destek alabilirim?
 Aspose.GIS forumunu ziyaret edebilirsiniz[Burada](https://forum.aspose.com/c/gis/33) yardım istemek ve diğer kullanıcılar ve geliştiricilerle etkileşimde bulunmak.
### Aspose.GIS geçici lisanslar sunuyor mu?
 Evet, Aspose.GIS için geçici lisansları şu adresten alabilirsiniz:[Burada](https://purchase.aspose.com/temporary-license/).
### Aspose.GIS'i nereden satın alabilirim?
 Aspose.GIS'i satın alma sayfasından satın alabilirsiniz.[Burada](https://purchase.aspose.com/buy).