---
title: Aspose.GIS for .NET ile Eğri Çokgen Geometrisi Oluşturun
linktitle: Eğri Çokgen Geometrisi Oluşturun
second_title: Aspose.GIS .NET API'si
description: Aspose.GIS for .NET'i kullanarak Eğri Çokgen Geometrisini verimli bir şekilde nasıl oluşturacağınızı öğrenin. CBS uygulamalarınızda sorunsuz bir şekilde yer almak için adım adım kılavuzumuzu izleyin.
weight: 18
url: /tr/net/geometry-creation/create-curve-polygon-geometry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET ile Eğri Çokgen Geometrisi Oluşturun

## giriiş
Coğrafi Bilgi Sistemleri (GIS) geliştirme alanında Aspose.GIS for .NET, konumsal verileri oluşturmak, düzenlemek ve işlemek için güçlü bir araç olarak öne çıkıyor. Bu eğitimin amacı Aspose.GIS for .NET'i kullanarak Eğri Çokgen Geometrisi oluşturma sürecinde size rehberlik etmektir. Bu eğitimin sonunda, CBS uygulamalarınız için karmaşık geometrileri verimli bir şekilde oluşturma bilgisine sahip olacaksınız.
## Önkoşullar
Bu eğitime dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
### 1. Aspose.GIS for .NET'in Kurulumu
 Başlamak için geliştirme ortamınızda Aspose.GIS for .NET'in kurulu olması gerekir. Henüz yapmadıysanız, kütüphaneyi şuradan indirebilirsiniz:[Aspose.GIS for .NET sürüm sayfası](https://releases.aspose.com/gis/net/).
### 2. .NET Geliştirmeye Aşinalık
Bu öğreticiyi takip etmek için C# programlama ve .NET geliştirme konusunda temel bir anlayış gereklidir.
### 3. Geliştirme Ortamı Kurulumu
Visual Studio veya seçtiğiniz herhangi bir .NET IDE dahil uygun bir geliştirme ortamının kurulduğundan emin olun.

## Ad Alanlarını İçe Aktar
Bu adımda Aspose.GIS işlevlerini kodumuzda kullanmak için gerekli ad alanlarını içe aktaracağız.
## Ad Alanlarını İçe Aktarma
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 1. Adım: Dosya Yolunu Tanımlayın
İlk olarak, oluşturulan Eğri Çokgen Şekil dosyasını kaydetmek istediğiniz dosya yolunu belirtin.
```csharp
string path = "Your Document Directory" + "CreateCurvePolygon_out.shp";
```
 Yer değiştirmek`"Your Document Directory"` dosyayı kaydetmek istediğiniz dizin yolu ile.
## Adım 2: Vektör Katmanı Oluşturun
Belirtilen dosya yolunu ve Shapefile sürücüsünü kullanarak yeni bir Vektör Katmanı oluşturun.
```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Eğri Çokgen Geometrisini oluşturma kodunuz buraya gelecek
}
```
`using` beyanı, kullanımdan sonra kaynakların uygun şekilde imha edilmesini sağlar.
## Adım 3: Özellik Oluşturun
Vektör Katmanında yeni bir özellik oluşturun.
```csharp
var feature = layer.ConstructFeature();
```
Bu, geometri ve nitelikleri atayabileceğiniz yeni bir özellik nesnesini başlatacaktır.
## Adım 4: Eğri Çokgen Geometrisi Oluşturun
Şimdi Eğri Çokgen Geometrisini oluşturmaya devam edelim.
```csharp
var curvePolygon = new CurvePolygon();
```
 Yeni bir örnek oluştur`CurvePolygon` eğri çokgen geometrisini temsil eden nesne.
## Adım 5: Dış Halkayı Tanımlayın
Eğri Çokgeninin dış halkasını tanımlayın.
```csharp
var exterior = new CircularString();
exterior.AddPoint(-2, 0);
exterior.AddPoint(0, 2);
exterior.AddPoint(2, 0);
exterior.AddPoint(0, -2);
exterior.AddPoint(-2, 0);
curvePolygon.ExteriorRing = exterior;
```
Eğri Çokgeninin dış halkasının koordinatlarını belirtin. Bu örnekte simit benzeri bir şekil oluşturuyoruz.
## Adım 6: İç Halkayı Tanımlayın
İsteğe bağlı olarak Eğri Çokgeni için iç halkaları tanımlayabilirsiniz.
```csharp
var interior = new CircularString();
interior.AddPoint(-1, 0);
interior.AddPoint(0, 1);
interior.AddPoint(1, 0);
interior.AddPoint(0, -1);
interior.AddPoint(-1, 0);
curvePolygon.AddInteriorRing(interior);
```
Eğri Çokgeninin içine delikler eklemek istiyorsanız iç halkaları buna göre tanımlayın.
## Adım 7: Özellik için Geometriyi Ayarlayın
Oluşturulan Eğri Çokgen Geometrisini özelliğe atayın.
```csharp
feature.Geometry = curvePolygon;
```
 Yı kur`Geometry` özelliğin özelliğini oluşturulan Eğri Çokgen Geometrisine aktarın.
## Adım 8: Katmana Özellik Ekleme
Eğri Çokgen Geometrisini içeren özelliği Vektör Katmanına ekleyin.
```csharp
layer.Add(feature);
```
Bu, özelliği Vektör Katmanına ekleyecek ve onu uzamsal veri kümesinin bir parçası haline getirecektir.

## Çözüm
Tebrikler! Aspose.GIS for .NET kullanarak Eğri Çokgen Geometrisinin nasıl oluşturulacağını başarıyla öğrendiniz. Bu eğitimde özetlenen adım adım kılavuzu takip ederek artık karmaşık geometrileri GIS uygulamalarınıza kolaylıkla dahil edebilirsiniz.
## SSS'ler
### Aspose.GIS for .NET diğer GIS kütüphaneleriyle uyumlu mu?
Evet, Aspose.GIS for .NET diğer popüler GIS kütüphaneleri ve formatlarıyla birlikte çalışabilirliği destekleyerek mevcut iş akışlarına kusursuz entegrasyon sağlar.
### Oluşturulan Eğri Poligon Geometrisini GIS yazılımında görselleştirebilir miyim?
Kesinlikle! Oluşturulan Eğri Çokgen Geometrisini QGIS veya ArcGIS gibi Shapefile formatını destekleyen çeşitli GIS yazılımlarında görselleştirebilirsiniz.
### Aspose.GIS for .NET mekansal analiz desteği sunuyor mu?
Evet, Aspose.GIS for .NET geniş yelpazede mekansal analiz işlevleri sunarak geliştiricilerin mekansal sorgulama, tamponlama ve daha fazlası gibi görevleri gerçekleştirmesine olanak sağlar.
### Yardım isteyebileceğim ve diğer Aspose.GIS kullanıcılarıyla işbirliği yapabileceğim bir topluluk forumu var mı?
 Evet, Aspose.GIS topluluk forumuna katılabilirsiniz[Burada](https://forum.aspose.com/c/gis/33) diğer kullanıcılarla etkileşime geçmek, sorular sormak ve deneyimlerinizi paylaşmak için.
### Satın almadan önce Aspose.GIS for .NET'i deneyebilir miyim?
 Elbette! Aspose.GIS for .NET'in ücretsiz denemesinden şu adresten yararlanabilirsiniz:[sürümler sayfası](https://releases.aspose.com/)Bir satın alma işlemi yapmadan önce özelliklerini keşfetmenize olanak tanır.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
