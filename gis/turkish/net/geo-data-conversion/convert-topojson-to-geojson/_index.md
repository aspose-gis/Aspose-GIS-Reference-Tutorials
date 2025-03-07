---
title: TopoJSON'u GeoJSON'a dönüştür
linktitle: TopoJSON'u GeoJSON'a dönüştür
second_title: Aspose.GIS .NET API'si
description: Aspose.GIS for .NET'i kullanarak TopoJSON'u sorunsuz bir şekilde GeoJSON'a nasıl dönüştüreceğinizi öğrenin. Verimli coğrafi veri işleme için adım adım eğitimimizi izleyin.
weight: 16
url: /tr/net/geo-data-conversion/convert-topojson-to-geojson/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# TopoJSON'u GeoJSON'a dönüştür

## giriiş
Bu eğitimde Aspose.GIS for .NET'i kullanarak TopoJSON'dan GeoJSON'a dönüştürme sürecini ayrıntılı olarak ele alacağız. Aspose.GIS, .NET uygulamalarında coğrafi bilgi işlemeyi kolaylaştırmak için tasarlanmış güçlü bir API'dir. TopoJSON ve GeoJSON, coğrafi verileri temsil etmek için yaygın olarak kullanılan formatlardır ve bunlar arasında dönüşüm yapabilmek, çeşitli GIS uygulamaları için çok önemlidir.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1.  Aspose.GIS for .NET: Aspose.GIS for .NET kitaplığını indirip yüklediğinizden emin olun. adresinden indirebilirsiniz.[Aspose.GIS web sitesi](https://releases.aspose.com/gis/net/).
2. Geliştirme Ortamı: .NET'in yüklü olduğu, çalışan bir geliştirme ortamına ihtiyacınız var.
3. Örnek TopoJSON Dosyası: Örnek bir TopoJSON dosyasını dönüştürme için hazır bulundurun. Eğer elinizde yoksa, onu oluşturabilir veya çeşitli kaynaklardan edinebilirsiniz.

## Ad Alanlarını İçe Aktar
Dönüşüme devam etmeden önce gerekli ad alanlarını projenize aktarın. Bu ad alanları, TopoJSON'dan GeoJSON'a dönüşüm için gereken işlevselliğe erişim sağlayacaktır.

   ```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Artık ortamınızı kurduğunuza ve gerekli ad alanlarını içe aktardığınıza göre, TopoJSON'u GeoJSON'a dönüştürme sürecini adım adım talimatlara ayıralım.
## Adım 1: Giriş ve Çıkış Yollarını Belirleyin

Giriş TopoJSON dosyasının ve çıkış GeoJSON dosyasının yollarını tanımlayın.
```csharp
var sampleTopoJsonPath = "Your Document Directory" + "sample.topojson";
var outputFilePath = "Your Document Directory" + "convertedSample_out.geojson";
```
##  Adım 2: Dönüşümü Gerçekleştirin`VectorLayer.Convert` method to convert TopoJSON to GeoJSON.
```csharp
VectorLayer.Convert(sampleTopoJsonPath, Drivers.TopoJson, outputFilePath, Drivers.GeoJson);
```

## Çözüm
Bu eğitimde Aspose.GIS for .NET kullanarak TopoJSON'u GeoJSON'a nasıl dönüştürebileceğimizi araştırdık. Belirtilen adımları takip ederek ve Aspose.GIS kütüphanesini kullanarak, .NET uygulamalarınızdaki coğrafi veri dönüşümlerini sorunsuz bir şekilde gerçekleştirebilirsiniz.
## SSS'ler
### Aspose.GIS büyük coğrafi veri kümelerini işleyebilir mi?
Evet, Aspose.GIS büyük coğrafi veri kümelerini verimli bir şekilde işleyerek optimum performansı garanti eder.
### Aspose.GIS farklı GIS dosya formatlarıyla uyumlu mu?
Kesinlikle Aspose.GIS, TopoJSON, GeoJSON, Shapefile ve daha fazlası dahil olmak üzere çok çeşitli GIS dosya formatlarını destekler.
### Aspose.GIS dokümantasyon ve destek sağlıyor mu?
 Evet, kapsamlı belgeler ve destek şu adreste mevcuttur:[Aspose.GIS forumu](https://forum.aspose.com/c/gis/33).
### Satın almadan önce Aspose.GIS'i deneyebilir miyim?
 Evet, ücretsiz deneme sürümünden yararlanabilirsiniz.[Web sitesi](https://releases.aspose.com/).
### Aspose.GIS için nasıl geçici lisans alabilirim?
 Geçici lisansı adresinden alabilirsiniz.[Satın alma sayfasını atayın](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
