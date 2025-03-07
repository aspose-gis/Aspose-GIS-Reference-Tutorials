---
title: .NET'te Aspose.GIS ile Bileşik Eğri Geometrisi Oluşturun
linktitle: Bileşik Eğri Geometrisi Oluşturun
second_title: Aspose.GIS .NET API'si
description: Kesintisiz coğrafi veri işleme için Aspose.GIS'i kullanarak .NET'te bileşik eğri geometrilerinin nasıl oluşturulacağını öğrenin.
weight: 19
url: /tr/net/geometry-creation/create-compound-curve-geometry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET'te Aspose.GIS ile Bileşik Eğri Geometrisi Oluşturun

## giriiş
.NET geliştirme dünyasında Aspose.GIS, coğrafi verilerle çalışmak için çok sayıda işlevsellik sunan güçlü bir araçtır. İster haritalama, konum tabanlı hizmetler veya coğrafi analiz için uygulamalar geliştiriyor olun, Aspose.GIS, geliştirme sürecinizi kolaylaştırmak için gerekli araçları sağlar.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulları oluşturduğunuzdan emin olun:
### Visual Studio Yüklü
Sisteminizde Visual Studio'nun kurulu olduğundan emin olun. Visual Studio web sitesinden indirip yükleyebilirsiniz.
### Aspose.GIS for .NET Yüklendi
 Aspose.GIS for .NET'i şu adresten indirip yükleyin:[indirme sayfası](https://releases.aspose.com/gis/net/). Aspose.GIS'i geliştirme ortamınıza kurmak için verilen kurulum talimatlarını izleyin.

## Ad Alanlarını İçe Aktar
.NET projenizde Aspose.GIS ile çalışmaya başlamak için gerekli ad alanlarını içe aktarmanız gerekir. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:
## 1. Adım: Visual Studio Projenizi Açın
Visual Studio'yu başlatın ve Aspose.GIS'i kullanmayı düşündüğünüz .NET projenizi açın.
## 2. Adım: Ad Alanı Referansları Ekleme
Kod dosyanızın başına aşağıdaki ad alanlarını ekleyin:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Bileşik Eğri Geometrisi Oluşturun
Şimdi Aspose.GIS for .NET'i kullanarak bileşik eğri geometrisi oluşturmaya çalışalım. Bu örnek, birden fazla bağlantılı eğriden oluşan ve karmaşık bir şekil oluşturan bir bileşik eğrinin nasıl oluşturulacağını gösterir.
### Adım 1: Çıkış Yolunu Tanımlayın
```csharp
string path = "Your Document Directory" + "CreateCompoundCurve_out.shp";
```
 Yer değiştirmek`"Your Document Directory"` çıktı Shapefile'ı kaydetmek istediğiniz yolla.
### Adım 2: Vektör Katmanı Oluşturun
```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Bileşik eğri geometrisini oluşturmaya yönelik kod bloğu buraya eklenecektir.
}
```
Bu kod parçacığı, bileşik eğri geometrisini Shapefile formatında depolamak için yeni bir VectorLayer'ı başlatır.
### Adım 3: Bileşik Eğriyi Oluşturun
```csharp
var feature = layer.ConstructFeature();
var compoundCurve = new CompoundCurve();
```
Burada yeni bir özelliği ve bileşik eğri geometrisini başlatıyoruz.
### Adım 4: Bileşen Eğrilerini Tanımlayın
```csharp
var bottom = (ILineString)Geometry.FromText("LineString (0 0, 3 0)");
var firstArc = (ICircularString)Geometry.FromText("CircularString (3 0, 4 1, 3 2)");
var middle = (ILineString)Geometry.FromText("LineString (3 2, 1 2)");
var secondArc = (ICircularString)Geometry.FromText("CircularString (1 2, 0 3, 1 4)");
var top = (ILineString)Geometry.FromText("LineString (1 4, 4 4)");
```
Bileşik eğriyi oluşturacak bileşen eğrilerini tanımlayın. Bunlara çizgi dizeleri ve dairesel dizeler dahildir.
### Adım 5: Bileşik Eğriye Bileşen Eğrileri Ekleme
```csharp
compoundCurve.AddCurve(bottom);
compoundCurve.AddCurve(firstArc);
compoundCurve.AddCurve(middle);
compoundCurve.AddCurve(secondArc);
compoundCurve.AddCurve(top);
```
Tanımlanan bileşen eğrilerini bileşik eğri geometrisine ekleyin.
### Adım 6: Özellik için Geometriyi Ayarlayın
```csharp
feature.Geometry = compoundCurve;
```
Bileşik eğri geometrisini özelliğe atayın.
### Adım 7: Katmana Özellik Ekleme
```csharp
layer.Add(feature);
```
Bileşik eğri geometrisine sahip özelliği vektör katmanına ekleyin.

## Çözüm
Bu eğitimde Aspose.GIS for .NET'i kullanarak bileşik eğri geometrisinin nasıl oluşturulacağını öğrendiniz. Adım adım kılavuzu takip ederek, jeo-uzaysal veri işleme için karmaşık geometrileri .NET uygulamalarınıza verimli bir şekilde dahil edebilirsiniz.
## SSS'ler
### Aspose.GIS for .NET'i diğer .NET çerçeveleriyle kullanabilir miyim?
Evet, Aspose.GIS for .NET; .NET Framework, .NET Core ve .NET Standard dahil olmak üzere çeşitli .NET çerçeveleriyle uyumludur.
### Aspose.GIS farklı coğrafi dosya formatlarının okunmasını ve yazılmasını destekliyor mu?
Kesinlikle! Aspose.GIS, Shapefile, GeoJSON, KML ve daha fazlası gibi popüler coğrafi dosya formatlarının okunması ve yazılması için kapsamlı destek sağlar.
### Aspose.GIS hem masaüstü hem de web uygulamaları için uygun mudur?
Evet, Aspose.GIS hem masaüstü hem de web uygulamalarında kullanılabilir ve jeouzaysal geliştirmede çok yönlülük sunar.
### Aspose.GIS for .NET ile mekansal analiz yapabilir miyim?
Evet, Aspose.GIS mesafe hesaplaması, geometrik işlemler ve mekansal sorgular da dahil olmak üzere çeşitli mekansal analiz işlevleri sunar.
### Aspose.GIS kullanıcıları için bir topluluk forumu veya destek kanalı var mı?
 Evet, ziyaret edebilirsiniz[Aspose.GIS forumu](https://forum.aspose.com/c/gis/33) sorular sormak, fikirleri paylaşmak ve topluluktan ve destek ekibinden yardım istemek.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
