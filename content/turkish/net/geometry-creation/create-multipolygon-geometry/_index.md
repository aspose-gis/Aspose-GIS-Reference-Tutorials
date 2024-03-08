---
title: Aspose.GIS ile Çoklu Çokgen Geometri Oluşturun
linktitle: Çok Çokgen Geometri Oluşturun
second_title: Aspose.GIS .NET API'si
description: Aspose.GIS for .NET'i kullanarak MultiPolygon geometrisini nasıl oluşturacağınızı öğrenin. Yeni başlayanlar için adım adım kılavuz. Ücretsiz deneme mevcut.
type: docs
weight: 16
url: /tr/net/geometry-creation/create-multipolygon-geometry/
---
## giriiş
Coğrafi Bilgi Sistemleri (GIS) geliştirme dünyasında Aspose.GIS for .NET, jeouzaysal verileri oluşturmak, düzenlemek ve analiz etmek için güçlü bir araç olarak öne çıkıyor. İster deneyimli bir geliştirici olun ister yeni başlıyor olun, Aspose.GIS'te uzmanlaşmak projeleriniz için bir olasılıklar dünyasının kapılarını açabilir.
## Önkoşullar
Aspose.GIS for .NET'i kullanmaya başlamadan önce, yerine getirmeniz gereken birkaç önkoşul vardır:
### Aspose.GIS for .NET'in Kurulumu
1.  Aspose.GIS'i indirin:[indirme sayfası](https://releases.aspose.com/gis/net/)ve geliştirme ortamınız için uygun sürümü seçin.
2. Aspose.GIS'i yükleyin: Aspose.GIS for .NET'i makinenize kurmak için belgelerde verilen kurulum talimatlarını izleyin.

## Ad Alanlarını İçe Aktarma
.NET projenizde Aspose.GIS ile çalışmaya başlamak için gerekli ad alanlarını içe aktarmanız gerekir:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Adım 1: Doğrusal Halkalar Oluşturun
Öncelikle her poligon için LinearRing'ler oluşturmamız gerekiyor. Her LinearRing, bir çokgenin sınırını oluşturan kapalı bir çizgi dizisini temsil eder.
```csharp
LinearRing firstRing = new LinearRing();
firstRing.AddPoint(8.5, -2.5);
firstRing.AddPoint(-8.5, 2.5);
firstRing.AddPoint(8.5, -2.5);
LinearRing secondRing = new LinearRing();
secondRing.AddPoint(7.6, -3.6);
secondRing.AddPoint(-9.6, 1.5);
secondRing.AddPoint(7.6, -3.6);
```
## Adım 2: Çokgenler Oluşturun
Daha sonra tanımladığımız LinearRing'leri kullanarak Polygon nesneleri oluşturacağız.
```csharp
Polygon firstPolygon = new Polygon(firstRing);
Polygon secondPolygon = new Polygon(secondRing);
```
## 3. Adım: Çoklu Çokgen Oluşturun
Şimdi bu çokgenleri Çoklu Çokgen geometrisinde birleştirelim.
```csharp
MultiPolygon multiPolygon = new MultiPolygon();
multiPolygon.Add(firstPolygon);
multiPolygon.Add(secondPolygon);
```
Tebrikler! Aspose.GIS for .NET'i kullanarak başarılı bir şekilde MultiPolygon geometrisi oluşturdunuz.

## Çözüm
Aspose.GIS for .NET'e hakim olmak, coğrafi verilerle çalışan geliştiricilere fırsatlar dünyasının kapılarını açar. Bu adım adım kılavuzu takip ederek, daha karmaşık GIS uygulamalarının temelini oluşturan Çoklu Çokgen geometrisinin nasıl oluşturulacağını öğrendiniz.
## SSS'ler
### Aspose.GIS for .NET yeni başlayanlar için uygun mu?
Kesinlikle! Aspose.GIS, her düzeydeki geliştiricinin başlangıç yapmasına yardımcı olacak kapsamlı belgeler ve eğitimler sunar.
### Satın almadan önce Aspose.GIS'i deneyebilir miyim?
 Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Burada](https://releases.aspose.com/) Bir satın alma işlemi yapmadan önce özelliklerini keşfetmek için.
### Aspose.GIS için desteği nerede bulabilirim?
 Aspose.GIS forumunu ziyaret edebilirsiniz[Burada](https://forum.aspose.com/c/gis/33) Soru sormak ve topluluktan yardım almak.
### Aspose.GIS için geçici bir lisans mevcut mu?
 Evet, adresinden geçici lisans alabilirsiniz.[Burada](https://purchase.aspose.com/temporary-license/) değerlendirme amaçlı.
### Aspose.GIS'i doğrudan satın alabilir miyim?
 Evet, Aspose.GIS'i web sitesinden satın alabilirsiniz.[Burada](https://purchase.aspose.com/buy).