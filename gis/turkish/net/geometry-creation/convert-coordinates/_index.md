---
title: Aspose.GIS ile Dönüşümü Koordine Et
linktitle: Koordinatları Dönüştür
second_title: Aspose.GIS .NET API'si
description: Aspose.GIS for .NET ile koordinatları nasıl dönüştüreceğinizi öğrenin. Adım adım kılavuz, ön koşullar ve SSS sağlanmıştır.
type: docs
weight: 25
url: /tr/net/geometry-creation/convert-coordinates/
---
## giriiş
Bu derste, .NET için güçlü Aspose.GIS kütüphanesini kullanarak coğrafi bilgi sistemleri (GIS) dünyasını derinlemesine inceleyeceğiz. Aspose.GIS, geliştiricilerin konumsal verilerle zahmetsizce çalışmasını sağlayan kapsamlı bir araç setidir. İster deneyimli bir geliştirici olun ister yeni başlıyor olun, bu eğitim size koordinatları etkili bir şekilde dönüştürmek için Aspose.GIS'i kullanma sürecinde rehberlik edecektir.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. Temel C# Bilgisi: Sağlanan kod örneklerini anlamak ve uygulamak için C# programlama diline aşina olmak çok önemlidir.
  
2.  Aspose.GIS Kurulumu: .NET için Aspose.GIS kütüphanesini indirip yüklediğinizden emin olun. adresinden indirebilirsiniz.[Aspose.GIS web sitesi](https://releases.aspose.com/gis/net/).

## Ad Alanlarını İçe Aktar
Başlamadan önce Aspose.GIS'in işlevlerine erişmek için gerekli ad alanlarını içe aktaralım:
```csharp
using System;
using Aspose.Gis;
```

Daha net bir anlayış için verilen örneği birden fazla adıma ayıralım:
## Adım 1: Dönüşüm Sürecini Başlatın
```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```
Bu satır, koordinat dönüştürme sürecinin başladığını belirten bir mesajı görüntüler.
## Adım 2: Ondalık Dereceye Dönüştürün
```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```
 Burada koordinatları (25.5, 45.5) ondalık derece formatına dönüştürüyoruz.`AsPointText` yöntemi ile`PointFormats.DecimalDegrees` parametre. Sonuç daha sonra konsola yazdırılır.
## Adım 3: Derece Ondalık Dakikaya Dönüştürme
```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```
Bu adım, koordinatları derece ondalık dakika biçimine dönüştürür ve sonucu yazdırır.
## Adım 4: Derece Dakika Saniyeye Dönüştürün
```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```
Benzer şekilde koordinatları derece dakika saniye formatına dönüştürüp çıktıyı görüntülüyoruz.
## Adım 5: GeoRef'e Dönüştürün
```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```
Son olarak koordinatları GeoRef formatına dönüştürüp sonucu yazdırıyoruz.

## Çözüm
Bu eğitimde Aspose.GIS for .NET kullanarak koordinatları dönüştürme sürecini inceledik. Adım adım kılavuzu takip ederek ve Aspose.GIS kütüphanesini kullanarak, .NET uygulamalarınızdaki mekansal verileri verimli bir şekilde yönetebilirsiniz.
## SSS'ler
### Aspose.GIS diğer programlama dilleriyle uyumlu mu?
Aspose.GIS öncelikle .NET geliştiricilerini hedefler ancak Aspose.GIS for Java aracılığıyla Java ile birlikte çalışabilirlik sunar.
### Satın almadan önce Aspose.GIS'i deneyebilir miyim?
 Evet, Aspose.GIS'in ücretsiz deneme sürümüne şu adresten erişebilirsiniz:[İnternet sitesi](https://releases.aspose.com/).
### Aspose.GIS için nasıl destek alabilirim?
 Aspose.GIS topluluk forumundan yardım isteyebilirsiniz.[Burada](https://forum.aspose.com/c/gis/33).
### Aspose.GIS için geçici lisanslar mevcut mu?
 Evet, geçici lisanslar şu adresten alınabilir:[geçici lisans sayfası](https://purchase.aspose.com/temporary-license/).
### Aspose.GIS'i nereden satın alabilirim?
 Aspose.GIS'i şu adresten satın alabilirsiniz:[satın alma sayfası](https://purchase.aspose.com/buy).