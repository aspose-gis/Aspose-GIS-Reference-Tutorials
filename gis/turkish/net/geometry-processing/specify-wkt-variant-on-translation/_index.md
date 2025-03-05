---
title: Aspose.GIS kullanarak Çeviride WKT Varyantını Belirleyin
linktitle: Çeviride WKT Varyantını Belirtin
second_title: Aspose.GIS .NET API'si
description: Uzamsal veri temsil formatını ve hassasiyetini etkili bir şekilde kontrol etmek için Aspose.GIS for .NET'te WKT değişkenlerini nasıl belirleyeceğinizi öğrenin.
type: docs
weight: 19
url: /tr/net/geometry-processing/specify-wkt-variant-on-translation/
---
## giriiş
Aspose.GIS for .NET, geliştiricilerin .NET uygulamalarında coğrafi bilgi sistemi (GIS) verileriyle zahmetsizce çalışmasına olanak tanıyan güçlü bir kütüphanedir. Aspose.GIS'in sağladığı temel özelliklerden biri, çeviri sırasında İyi Bilinen Metin (WKT) değişkenini belirleyerek kullanıcıların konumsal veri temsillerinin formatını ve hassasiyetini kontrol edebilmesidir. Bu eğitimde, Aspose.GIS for .NET'i kullanarak WKT varyantlarının adım adım nasıl belirleneceğini inceleyeceğiz.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
1. Aspose.GIS for .NET: Aspose.GIS for .NET'i şu adresten indirip yükleyin:[indirme sayfası](https://releases.aspose.com/gis/net/).
2. Geliştirme Ortamı: Bir .NET geliştirme ortamı kurduğunuzdan emin olun.
3. Temel Bilgi: C# programlama dili ve .NET çerçevesine aşinalık.

## Ad Alanlarını İçe Aktar
Kodunuzda Aspose.GIS işlevini kullanmadan önce gerekli ad alanlarını içe aktarın:
```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```
## Adım 1: Bir Nokta Nesnesi Oluşturun
 Öncelikle bir tane oluşturun`Point` enlem, boylam ve isteğe bağlı ölçü (M) değerlerine sahip nesne:
```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```
## Adım 2: Uzamsal Referans Sistemini (SRS) Ayarlayın
Nokta nesnesine bir uzaysal referans sistemi (SRS) atayın. Bu örnekte WGS84 mekansal referans sistemini kullanıyoruz:
```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```
## 3. Adım: WKT Varyantını Belirleyin
 Şimdi çeviri için WKT varyantını belirtin. Aspose.GIS, aşağıdakiler de dahil olmak üzere çeşitli WKT varyantlarını destekler:`Iso`, `SimpleFeatureAccessOutdated` , Ve`ExtendedPostGis`. Gereksinimlerinize göre uygun varyantı seçin:
```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // M NOKTASI (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // NOKTA (23,5732, 25,3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23,5732, 25,3421, 40,3)
```
## Adım 4: Sayısal Formatı Kontrol Edin
WKT gösteriminde koordinatların sayısal biçimini kontrol edebilirsiniz. Aspose.GIS ondalık kesinliği belirlemek için seçenekler sunar:
```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // M NOKTASI (23,5732 25,342099999999999 40,299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // M NOKTASI (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // M NOKTASI (23,6 25,3 40,3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // M NOKTASI (23.573 25.342 40.3)
```

## Çözüm
Bu eğitimde Aspose.GIS for .NET kullanarak çeviride WKT değişkenlerini nasıl belirleyeceğimizi öğrendik. Geliştiriciler, yukarıda özetlenen adımları izleyerek, .NET uygulamalarındaki uzamsal veri temsillerinin formatını ve hassasiyetini etkili bir şekilde kontrol edebilir, böylece coğrafi bilgi sistemlerinin esnekliğini ve kullanılabilirliğini artırabilirler.
## SSS'ler
### Aspose.GIS .NET'in tüm sürümleriyle uyumlu mu?
Evet, Aspose.GIS .NET Framework 4.0 ve üzerini destekler.
### Aspose.GIS'i ticari projeler için kullanabilir miyim?
Evet, Aspose.GIS hem kişisel hem de ticari projeler için kullanılabilir.
### Aspose.GIS diğer mekansal veri formatlarını destekliyor mu?
Evet, Aspose.GIS, ESRI Shapefile, GeoJSON ve KML dahil olmak üzere çok çeşitli mekansal veri formatlarını destekler.
### Aspose.GIS'in ücretsiz deneme sürümü mevcut mu?
 Evet, Aspose.GIS'in ücretsiz deneme sürümünü şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/).
### Aspose.GIS için nereden yardım veya destek alabilirim?
 Aspose.GIS topluluğundan sorularınızı gönderebilir veya yardım isteyebilirsiniz.[forum](https://forum.aspose.com/c/gis/33).