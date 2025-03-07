---
title: Geometriyi Kontrol Et Başka Bir Şey İçerir
linktitle: Geometriyi Kontrol Et Başka Bir Şey İçerir
second_title: Aspose.GIS .NET API'si
description: Aspose.GIS for .NET'i, .NET uygulamalarınızda kesintisiz coğrafi veri entegrasyonu için güçlü bir kitaplık olarak keşfedin.
weight: 14
url: /tr/net/geometry-analysis/check-geometry-contains-another/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Geometriyi Kontrol Et Başka Bir Şey İçerir

## giriiş
Aspose.GIS for .NET, geliştiricilerin .NET uygulamalarında coğrafi verilerle sorunsuz bir şekilde çalışmasına olanak tanıyan güçlü bir kütüphanedir. İster bir haritalama uygulaması oluşturuyor olun, ister jeo-uzaysal analiz gerçekleştiriyor olun, ister konum tabanlı özellikleri yazılımınıza entegre ediyor olun, Aspose.GIS, sezgisel API'ler ve sağlam işlevsellik sunarak süreci basitleştirir.
## Önkoşullar
Aspose.GIS for .NET'i kullanmaya başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
### 1. .NET Geliştirme Ortamı Kurulumu
Makinenizde çalışan bir .NET geliştirme ortamının kurulu olduğundan emin olun. Buna .NET SDK'nın düzgün şekilde kurulması ve yapılandırılması da dahildir.
### 2. Aspose.GIS Kurulumu
 Yayın sayfasından kitaplığı indirerek Aspose.GIS for .NET'i yükleyin[Burada](https://releases.aspose.com/gis/net/) . Belgelerde sağlanan kurulum talimatlarını izleyin[Burada](https://reference.aspose.com/gis/net/)Aspose.GIS'i projenize entegre etmek için.
### 3. C#'ın Temel Anlayışı
Aspose.GIS for .NET öncelikle C# ile kullanıldığından, C# programlama dilini öğrenin.

## Ad Alanlarını İçe Aktar
Aspose.GIS işlevlerini kullanmak için C# projenize gerekli ad alanlarını içe aktarın:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Adım 1: Geometri Nesnelerini Tanımlayın
İlk olarak Aspose.GIS sınıflarını kullanarak geometri nesnelerini tanımlayın:
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
## Adım 2: Uzaysal Sınırlamayı Kontrol Edin
Daha sonra bir geometrinin diğerini içerip içermediğini kontrol edin:
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry2)); // YANLIŞ
```
## Adım 3: Başka Bir Geometri Tanımlayın
Başka bir geometri nesnesi tanımlayın:
```csharp
var geometry3 = new Point(0.5, 0.5);
```
## Adım 4: Uzaysal Sınırlamayı Tekrar Kontrol Edin
Yeni tanımlanan geometrinin ilk geometrinin içinde olup olmadığını kontrol edin:
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry3)); // Doğru
```
## Adım 5: Eşdeğer İşlevsellik
 Anlaşıldı`a.SpatiallyContains(b)` eşdeğerdir`b.Within(a)`:
```csharp
Console.WriteLine(geometry3.Within(geometry1)); // Doğru
```

## Çözüm
Sonuç olarak Aspose.GIS for .NET, .NET uygulamalarında coğrafi verilerin işlenmesi için güçlü araçlar sağlar. Bu kılavuzu takip ederek ve verilen örneği kullanarak, mekansal çevreleme kontrollerini verimli bir şekilde gerçekleştirebilir ve projelerinizdeki diğer coğrafi mekansal işlevselliklerden yararlanabilirsiniz.
## SSS'ler
### S1: Aspose.GIS .NET Core ile uyumlu mu?
C: Evet, Aspose.GIS, .NET Core'u tam olarak destekleyerek farklı platformlarda coğrafi uygulamalar geliştirmenize olanak tanır.
### S2: Aspose.GIS'i kullanarak coğrafi analiz yapabilir miyim?
C: Kesinlikle Aspose.GIS, mekansal sorgular, mesafe hesaplamaları ve geometri manipülasyonları da dahil olmak üzere coğrafi analiz için çeşitli işlevler sunar.
### S3: Aspose.GIS için güncellemeler ne sıklıkla yayınlanıyor?
C: Aspose.GIS performansı artırmak, yeni özellikler eklemek ve bildirilen sorunları çözmek için düzenli olarak güncellemeler yayınlar. Sürüm sayfasını ziyaret ederek güncel kalabilirsiniz.
### S4: Aspose.GIS kullanıcıları için bir topluluk forumu var mı?
C: Evet, Aspose.GIS topluluk forumuna katılabilirsiniz[Burada](https://forum.aspose.com/c/gis/33) diğer kullanıcılarla bağlantı kurmak, sorular sormak ve deneyimlerinizi paylaşmak için.
### S5: Satın almadan önce Aspose.GIS'i deneyebilir miyim?
 C: Elbette, Aspose.GIS'i aşağıdaki ücretsiz deneme sürümünü indirerek keşfedebilirsiniz.[Burada](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
