---
title: Dokunarak Geometrileri Kontrol Edin
linktitle: Dokunarak Geometrileri Kontrol Edin
second_title: Aspose.GIS .NET API'si
description: Aspose.GIS for .NET ile mekansal veri işlemenin gücünü ortaya çıkarın. Bu çok yönlü araç seti ile mekansal işlevleri uygulamalarınıza sorunsuz bir şekilde entegre edin.
type: docs
weight: 13
url: /tr/net/geometry-analysis/check-geometries-touching/
---
## giriiş
Coğrafi Bilgi Sistemleri (GIS) alanında, Aspose.GIS for .NET, mekansal işlevleri uygulamalarına sorunsuz bir şekilde dahil etmek isteyen geliştiriciler için güçlü bir araç olarak öne çıkıyor. Aspose.GIS, sağlam özellikleri ve kullanıcı dostu arayüzü ile geliştiricilerin analiz, görselleştirme veya geometrileri manipüle etme gibi konumsal verilerle zahmetsizce çalışmasına olanak tanır.
## Önkoşullar
Aspose.GIS for .NET'in inceliklerine dalmadan önce yerine getirmeniz gereken birkaç ön koşul var:
### Ortamınızı Kurma
1. Visual Studio'yu Kurun: Sisteminizde Visual Studio'nun kurulu olduğundan emin olun. Web sitesinden indirebilirsiniz.
   
2.  Aspose.GIS for .NET'i indirin:[İndirme: {link](https://releases.aspose.com/gis/net/)ve Aspose.GIS for .NET'in en son sürümünü edinin.
3.  Lisans Alın: Aspose.GIS'in tüm potansiyelinden yararlanmak için geçerli bir lisansa ihtiyacınız var. Bir tane satın alabilir veya ücretsiz denemeyi tercih edebilirsiniz.[Burada](https://releases.aspose.com/).

## Ad Alanlarını İçe Aktar
Aspose.GIS for .NET'in gücünden yararlanmaya başlamak için gerekli ad alanlarını projenize aktarmanız gerekir. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Artık ortamınızı kurduğunuza ve gerekli ad alanlarını içe aktardığınıza göre, Aspose.GIS for .NET kullanarak geometrileri kontrol etmenin pratik bir örneğini inceleyelim.
## Adım 1: Geometriler Oluşturun
```csharp
var geometry1 = new LineString();
geometry1.AddPoint(0, 0);
geometry1.AddPoint(2, 2);
var geometry2 = new LineString();
geometry2.AddPoint(2, 2);
geometry2.AddPoint(3, 3);
var geometry3 = new Point(2, 2);
var geometry4 = new LineString();
geometry4.AddPoint(1, 1);
geometry4.AddPoint(4, 4);
```
## Adım 2: Dokunmayı Kontrol Edin
```csharp
Console.WriteLine(geometry1.Touches(geometry2)); // Doğru
Console.WriteLine(geometry2.Touches(geometry1)); // Doğru
Console.WriteLine(geometry1.Touches(geometry3)); // Doğru
Console.WriteLine(geometry1.Touches(geometry4)); // YANLIŞ
```

## Çözüm
Sonuç olarak Aspose.GIS for .NET, .NET geliştiricileri için konumsal veri işleme ve analizini kolaylaştıran çok yönlü bir araç setidir. Bu öğreticiyi takip ederek, mekansal işlevleri uygulamalarınıza sorunsuz bir şekilde entegre edebilir, yeteneklerini ve kullanıcı deneyimini geliştirebilirsiniz.
## SSS'ler
### Aspose.GIS tüm .NET çerçeveleriyle uyumlu mu?
Aspose.GIS, .NET Framework, .NET Core ve .NET Standard gibi çeşitli .NET çerçevelerini destekleyerek çok çeşitli geliştirme ortamlarında uyumluluk sağlar.
### Lisans satın almadan önce Aspose.GIS'i deneyebilir miyim?
 Evet, Aspose web sitesinden ücretsiz deneme süresinden yararlanabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/) Bir satın alma kararı vermeden önce özelliklerini ve işlevlerini keşfetmek.
### Aspose.GIS ile ilgili sorgular için desteği nerede bulabilirim?
 Ziyaret edebilirsiniz[Aspose.GIS forumu](https://forum.aspose.com/c/gis/33) topluluktan yardım istemek veya aklınıza takılan soruları dile getirmek için.
### Aspose.GIS için güncellemeler ne sıklıkla yayınlanıyor?
Aspose.GIS, en son teknolojilerle uyumluluğu sağlamak ve bildirilen sorunları çözmek için düzenli olarak güncellemeler ve geliştirmeler alır.
### Aspose.GIS için geçici lisans alabilir miyim?
 Evet, adresinden geçici lisans alabilirsiniz.[Burada](https://purchase.aspose.com/temporary-license/) Aspose.GIS'in yeteneklerini geliştirme ortamınızda değerlendirmek için.