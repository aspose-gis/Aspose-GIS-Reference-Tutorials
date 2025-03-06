---
title: Aspose.GIS ile Geometride Geometrileri Sayma
linktitle: Geometride Geometrileri Sayma
second_title: Aspose.GIS .NET API'si
description: Aspose.GIS for .NET kullanarak bir geometrideki geometrileri nasıl sayacağınızı öğrenin. Geliştiriciler için kod örnekleri içeren adım adım eğitim.
weight: 23
url: /tr/net/geometry-creation/count-geometries-in-geometry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS ile Geometride Geometrileri Sayma

## giriiş
Aspose.GIS for .NET, jeouzaysal işlevselliği .NET uygulamalarına dahil etmek isteyen geliştiriciler için güçlü bir araçtır. Haritalama yazılımı, konum tabanlı hizmetler veya mekansal analiz araçları oluşturuyor olsanız da, Aspose.GIS ihtiyaçlarınızı karşılayacak kapsamlı özellikler sunar. Bu derste Aspose.GIS for .NET kullanarak bir geometri içindeki geometrilerin nasıl sayılacağını inceleyeceğiz.
## Önkoşullar
Bu eğitime dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. Visual Studio: Sisteminizde Visual Studio'nun kurulu olduğundan emin olun.
2. Aspose.GIS for .NET: Aspose.GIS for .NET'i şu adresten indirip yükleyin:[indirme sayfası](https://releases.aspose.com/gis/net/).
3. Temel C# Bilgisi: C# programlama dilinin temellerine aşina olun.

## Ad Alanlarını İçe Aktar
Kodlamaya başlamadan önce Aspose.GIS işlevselliğine erişmek için gerekli ad alanlarını içe aktarmanız gerekir.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Adım 2: Nokta Geometrisi Oluşturun
```csharp
Point point = new Point(40.7128, -74.006);
```
 Burada bir oluşturuyoruz`Point` 40.7128 enlem ve -74.006 boylamlı geometri.
## Adım 3: LineString Geometrisi Oluşturun
```csharp
LineString line = new LineString();
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```
 Bu adım bir oluşturur`LineString` geometriye iki nokta ekler.
## Adım 4: Geometri Koleksiyonu Oluşturun
```csharp
GeometryCollection geometryCollection = new GeometryCollection();
geometryCollection.Add(point);
geometryCollection.Add(line);
```
 Daha sonra bir oluştururuz`GeometryCollection` ve önceden oluşturulmuş nokta ve çizgi geometrilerini buna ekleyin.
## Adım 5: Geometrileri Sayma
```csharp
int geometriesCount = geometryCollection.Count;
```
 Bu adım, içindeki geometrilerin sayısını sayar.`GeometryCollection`.
## Adım 6: Sayımı Görüntüleyin
```csharp
Console.WriteLine(geometriesCount); // 2
```
 Son olarak geometrilerin sayısını yazdırıyoruz; bu durumda bu`2`.

## Çözüm
Bu eğitimde Aspose.GIS for .NET kullanarak bir geometri içindeki geometrilerin nasıl sayılacağını öğrendik. Bu adımları izleyerek jeouzaysal işlevselliği .NET uygulamalarınıza kolaylıkla dahil edebilirsiniz.
## SSS'ler
### Aspose.GIS for .NET hem masaüstü hem de web uygulamaları için uygun mu?
Evet, Aspose.GIS for .NET hem masaüstü hem de web uygulamalarında sorunsuz bir şekilde kullanılabilir.
### Aspose.GIS for .NET'i kullanarak uzamsal sorgular gerçekleştirebilir miyim?
Aspose.GIS for .NET kesinlikle geometriler üzerinde uzamsal sorgulamalar gerçekleştirmek için güçlü bir destek sağlıyor.
### Aspose.GIS for .NET çeşitli GIS dosya formatlarını destekliyor mu?
Evet, Aspose.GIS for .NET, SHP, KML ve GeoJSON dahil çok çeşitli GIS dosya formatlarını destekler.
### Aspose.GIS for .NET'in ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[İnternet sitesi](https://releases.aspose.com/).
### Aspose.GIS for .NET desteğini nerede bulabilirim?
 Şu adreste destek bulabilirsiniz:[Aspose.GIS forumu](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
