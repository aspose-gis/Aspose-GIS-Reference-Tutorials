---
title: Aspose.GIS kullanarak Delik Geometrili Çokgen Oluşturma
linktitle: Delik Geometrisiyle Çokgen Oluşturma
second_title: Aspose.GIS .NET API'si
description: Aspose.GIS for .NET'i kullanarak delik geometrili çokgen oluşturmayı öğrenin. Kod örnekleriyle adım adım eğitim.
type: docs
weight: 13
url: /tr/net/geometry-creation/create-polygon-with-hole-geometry/
---
## giriiş
Bu eğitimde Aspose.GIS for .NET'i kullanarak delik geometrili bir çokgen oluşturma sürecini anlatacağız. Aspose.GIS, geliştiricilerin .NET uygulamalarında coğrafi verilerle çalışmasına olanak tanıyan güçlü bir kütüphanedir. 
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. Aspose.GIS for .NET Library: Buradan indirebilirsiniz.[Burada](https://releases.aspose.com/gis/net/).
2. Geliştirme Ortamı: Visual Studio veya herhangi bir başka .NET IDE'nin kurulu olduğu bir geliştirme ortamına sahip olduğunuzdan emin olun.
## Ad Alanlarını İçe Aktar
Öncelikle Aspose.GIS işlevleriyle çalışmak için gerekli ad alanlarını içe aktarmanız gerekir. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Şimdi Aspose.GIS for .NET'i kullanarak delik geometrisine sahip bir çokgen oluşturmaya devam edelim.
## Adım 1: Çokgen Nesnesi Oluşturun
```csharp
Polygon polygon = new Polygon();
```
## Adım 2: Dış Halkayı Tanımlayın
```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```
## Adım 3: İç Halkayı (Delik) Tanımlayın
```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```
## Adım 4: Dış Halkayı Atayın ve Çokgene İç Halkayı Ekleyin
```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```
## Çözüm
Tebrikler! Aspose.GIS for .NET'i kullanarak delik geometrili çokgen oluşturmayı başarıyla öğrendiniz. Bu bilgi, bu tür geometrilerin gerekli olduğu çeşitli coğrafi uygulamalar için faydalı olacaktır.
## SSS'ler
### 1. Aspose.GIS nedir?
Aspose.GIS, geliştiricilerin jeo-uzamsal verilerle çalışmasına, çeşitli coğrafi-uzamsal dosya formatlarını oluşturmasına, okumasına ve değiştirmesine olanak tanıyan bir .NET kütüphanesidir.
### 2. Aspose.GIS'i ticari projeler için kullanabilir miyim?
 Evet, Aspose.GIS'i lisans satın alarak hem kişisel hem de ticari projeleriniz için kullanabilirsiniz. Ziyaret etmek[Burada](https://purchase.aspose.com/buy) daha fazla ayrıntı için.
### 3. Aspose.GIS'in ücretsiz deneme sürümü mevcut mu?
 Evet, Aspose.GIS'in ücretsiz deneme sürümünden şu adresten yararlanabilirsiniz:[Burada](https://releases.aspose.com/).
### 4. Aspose.GIS desteğini nerede bulabilirim?
 Aspose.GIS desteğini şu adreste bulabilirsiniz:[Aspose.GIS forumu](https://forum.aspose.com/c/gis/33).
### 5. Aspose.GIS için nasıl geçici lisans alabilirim?
 Aspose.GIS için geçici bir lisansı şu adresten alabilirsiniz:[Burada](https://purchase.aspose.com/temporary-license/).