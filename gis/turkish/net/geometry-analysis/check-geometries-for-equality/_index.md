---
title: Eşitlik Açısından Geometrileri Kontrol Edin
linktitle: Eşitlik Açısından Geometrileri Kontrol Edin
second_title: Aspose.GIS .NET API'si
description: Bu kapsamlı eğitimle .NET uygulamalarınızda geometrilerin eşitliğini kontrol etmek için Aspose.GIS for .NET'i nasıl kullanacağınızı öğrenin.
weight: 10
url: /tr/net/geometry-analysis/check-geometries-for-equality/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Eşitlik Açısından Geometrileri Kontrol Edin

## giriiş
Aspose.GIS for .NET, geliştiricilerin .NET uygulamalarında coğrafi verilerle verimli bir şekilde çalışmasına olanak tanıyan güçlü bir kütüphanedir. İster haritalama uygulamaları, mekansal analiz araçları oluşturuyor olun, ister coğrafi mekansal işlevselliği mevcut yazılıma entegre ediyor olun, Aspose.GIS işinizi tamamlamak için ihtiyacınız olan araçları sağlar.
## Önkoşullar
Aspose.GIS for .NET'i kullanmaya başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
### .NET Framework Yüklü
Sisteminizde .NET Framework'ün kurulu olduğundan emin olun. Microsoft'un web sitesinden indirebilirsiniz.
### Aspose.GIS for .NET Kütüphanesi
 Aspose.GIS for .NET kütüphanesini şu adresten indirip yükleyin:[indirme sayfası](https://releases.aspose.com/gis/net/). Belgelerde sağlanan kurulum talimatlarını izleyin.
### Geliştirme Ortamı
.NET geliştirme için Visual Studio gibi tercih ettiğiniz geliştirme ortamını kurun.

## Ad Alanlarını İçe Aktar
Aspose.GIS işlevselliğini kullanmak için .NET uygulamanıza gerekli ad alanlarını içe aktarın:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Adım 1: Geometrileri Tanımlayın
Öncelikle karşılaştırmak istediğiniz geometrileri tanımlayın. Bu örnekte iki geometrimiz var:`geometry1` Ve`geometry2`.
```csharp
var geometry1 = new MultiLineString
{
    new LineString(new [] { new Point(0, 0), new Point(1, 1) }),
    new LineString(new [] { new Point(1, 1), new Point(2, 2) }),
};
var geometry2 = new LineString(new[]
{
    new Point(0, 0), new Point(2, 2),
});
```
## Adım 2: Geometrileri Eşitlik Açısından Kontrol Edin
 Şimdi geometrilerin mekansal olarak eşit olup olmadığını kontrol edin.`SpatiallyEquals` Aspose.GIS tarafından sağlanan yöntem.
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // Doğru
```
 Bu yazdırılacak`True` o zamandan beri konsola`geometry1` Ve`geometry2` uzaysal olarak eşittir.
## Adım 3: Geometriyi Değiştirin
 Sonra değiştirelim`geometry2` yeni bir nokta ekleyerek.
```csharp
geometry2.AddPoint(3, 3);
```
## 4. Adım: Eşitliği Yeniden Kontrol Edin
Şimdi değişiklikten sonra geometrilerin eşitliğini tekrar kontrol edin.
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // YANLIŞ
```
 Bu sefer çıktı şu şekilde olacak:`False` yapılan değişiklik nedeniyle geometriler artık uzaysal olarak eşit olmadığından`geometry2`.

## Çözüm
Sonuç olarak Aspose.GIS for .NET, .NET uygulamalarında coğrafi verilerle çalışmak için güçlü araçlar sağlar. Bu adım adım kılavuzu takip ederek Aspose.GIS yöntemlerini kullanarak geometrilerin eşitliğini kolayca kontrol edebilirsiniz.
## SSS'ler
### Aspose.GIS for .NET'i diğer .NET çerçeveleriyle kullanabilir miyim?
Evet, Aspose.GIS for .NET, .NET Core ve .NET Standard dahil olmak üzere çeşitli .NET çerçeveleriyle uyumludur.
### Aspose.GIS for .NET'in ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[sürümler sayfası](https://releases.aspose.com/).
### Aspose.GIS for .NET belgelerini nerede bulabilirim?
 Ayrıntılı belgeleri şu adreste bulabilirsiniz:[Aspose.GIS dokümantasyon sayfası](https://reference.aspose.com/gis/net/).
### Aspose.GIS for .NET için nasıl destek alabilirim?
 Aspose.GIS topluluk forumundan destek alabilirsiniz[Burada](https://forum.aspose.com/c/gis/33).
### Aspose.GIS for .NET için geçici bir lisans satın alabilir miyim?
 Evet, geçici lisansı şu adresten satın alabilirsiniz:[satın alma sayfası](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
