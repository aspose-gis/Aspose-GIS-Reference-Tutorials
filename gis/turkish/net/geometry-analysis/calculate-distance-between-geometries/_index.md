---
title: Aspose.GIS ile Geometriler Arasındaki Mesafeyi Hesaplayın
linktitle: Geometriler Arasındaki Mesafeyi Hesaplayın
second_title: Aspose.GIS .NET API'si
description: Aspose.GIS'i kullanarak .NET'te geometriler arasındaki mesafeleri nasıl hesaplayacağınızı öğrenin. Kod örnekleri içeren adım adım kılavuz. Jeo-uzamsal uygulamalarınızı geliştirin.
weight: 21
url: /tr/net/geometry-analysis/calculate-distance-between-geometries/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS ile Geometriler Arasındaki Mesafeyi Hesaplayın

## giriiş
Jeouzaysal programlama alanında, farklı geometriler arasındaki mesafeleri hesaplama yeteneği çok önemlidir. İster çokgenler, çizgiler veya noktalarla ilgileniyor olun, aralarındaki mesafeyi bilmek haritalamadan lojistik planlamaya kadar çeşitli uygulamalar için çok önemli olabilir. Aspose.GIS for .NET, bu tür hesaplamaları kolaylıkla ve hassasiyetle gerçekleştirmek için güçlü araçlar sağlar.
## Önkoşullar
Aspose.GIS for .NET'i kullanarak geometriler arasındaki mesafeleri hesaplamaya başlamadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
### Aspose.GIS for .NET'i yükleyin
 Başlamak için sisteminizde Aspose.GIS for .NET'in kurulu olması gerekir. Kütüphaneyi adresinden indirebilirsiniz.[Aspose.GIS for .NET sürüm sayfası](https://releases.aspose.com/gis/net/) ve belgelerde verilen kurulum talimatlarını izleyin.
### .NET Geliştirmeye aşinalık
Bu eğitimdeki örnekleri takip etmek için C# kullanarak .NET geliştirme konusunda temel bir anlayış gereklidir. .NET geliştirme konusunda yeniyseniz, devam etmeden önce C#'ın temel bilgilerini tazelemeyi düşünün.

## Ad Alanlarını İçe Aktar
Geometriler arasındaki mesafeleri hesaplamak için Aspose.GIS for .NET'i kullanmaya başlamadan önce gerekli ad alanlarını C# projenize aktarmanız gerekir. Gerekli ad alanlarını içe aktarmak için şu adımları izleyin:
## C# Projenizi Açın
Visual Studio gibi tercih ettiğiniz Tümleşik Geliştirme Ortamında (IDE) C# projenize gidin.
## Ad Alanı Referansları Ekle
Uzaklık hesaplamalarını gerçekleştirmeyi planladığınız C# dosyanızda, dosyanın başına aşağıdaki ad alanı referanslarını ekleyin:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Aspose.GIS for .NET kullanarak geometriler arasındaki mesafenin nasıl hesaplanacağını anlamak için verilen örneği birden fazla adıma ayıralım:
## Adım 1: Çokgen Geometrisi Oluşturun
```csharp
var polygon = new Polygon();
```
Bu adım, çokgen geometrisinin yeni bir örneğini oluşturur.
## Adım 2: Poligon Dış Halkayı Tanımlayın
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
Burada çokgenin sınırını oluşturan noktaların sırasını belirterek çokgenin dış halkasını tanımlarız.
## Adım 3: Çizgi Dizisi Geometrisi Oluşturun
```csharp
var line = new LineString();
```
Bu adım, çizgi dizisi geometrisinin yeni bir örneğini başlatır.
## Adım 4: Satır Dizisine Nokta Ekleme
```csharp
line.AddPoint(2, 0);
line.AddPoint(1, 3);
```
Çizgi dizisine şeklini ve yörüngesini tanımlayarak iki nokta ekliyoruz.
## Adım 5: Mesafeyi Hesaplayın
```csharp
double distance = polygon.GetDistanceTo(line);
```
Bu adım, çokgen ile çizgi dizisi arasındaki mesafeyi hesaplar.
## Adım 6: Çıktı Sonucu
```csharp
Console.WriteLine(distance.ToString("F")); // 0,63
```
Son olarak, konsola hesaplanan mesafeyi iki ondalık basamağı gösterecek şekilde biçimlendirilmiş olarak yazdırıyoruz.

## Çözüm
Geometriler arasındaki mesafeleri hesaplamak, jeouzaysal programlamada temel bir görevdir ve Aspose.GIS for .NET, sezgisel API'si ile bu süreci basitleştirir. Bu öğreticide özetlenen adımları izleyerek, .NET uygulamalarınızdaki çokgenler, çizgiler ve noktalar arasındaki mesafeleri zahmetsizce hesaplayabilirsiniz.
## SSS'ler
### Aspose.GIS for .NET tüm .NET çerçeveleriyle uyumlu mu?
Evet, Aspose.GIS for .NET, .NET Framework 4.6 ve üzeri ile uyumludur.
### Karmaşık mekansal analizler gerçekleştirmek için Aspose.GIS for .NET'i kullanabilir miyim?
Kesinlikle! Aspose.GIS for .NET, gelişmiş mekansal analiz görevleri için geniş bir işlevsellik yelpazesi sunar.
### Aspose.GIS for .NET hem 2D hem de 3D geometrileri destekliyor mu?
Evet, Aspose.GIS for .NET'i kullanarak hem 2D hem de 3D geometrilerle çalışabilirsiniz.
### Aspose.GIS for .NET'i diğer GIS kütüphaneleriyle entegre edebilir miyim?
Aspose.GIS for .NET, diğer GIS kütüphaneleriyle birlikte çalışabilirlik sağlayarak ek işlevlerden yararlanmanıza olanak tanır.
### Aspose.GIS for .NET kullanıcıları için teknik destek mevcut mu?
 Evet, Aspose.GIS for .NET kullanıcıları Aspose aracılığıyla teknik desteğe erişebilirler.[forumlar](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
