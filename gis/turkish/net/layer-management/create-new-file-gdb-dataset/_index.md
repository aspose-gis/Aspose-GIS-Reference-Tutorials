---
title: Yeni Dosya GDB Veri Kümesi Oluştur
linktitle: Yeni Dosya GDB Veri Kümesi Oluştur
second_title: Aspose.GIS .NET API'si
description: GIS veri kümelerini zahmetsizce oluşturmak ve yönetmek için Aspose.GIS for .NET'i keşfedin. Kesintisiz coğrafi gelişim için hemen indirin. #Aspose #GIS
weight: 10
url: /tr/net/layer-management/create-new-file-gdb-dataset/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Yeni Dosya GDB Veri Kümesi Oluştur

## giriiş
Jeo-uzaysal geliştirme alanında Aspose.GIS for .NET, Coğrafi Bilgi Sistemi (GIS) verilerini yönetmek ve işlemek için güçlü bir araç seti olarak öne çıkıyor. İster deneyimli bir geliştirici olun ister GIS yolculuğunuza yeni başlıyor olun, bu eğitim size Aspose.GIS for .NET kullanarak yeni bir Dosya Geodatabase (GDB) veri seti oluşturma sürecinde yol gösterecektir.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
-  Aspose.GIS for .NET: Aspose.GIS for .NET kütüphanesinin kurulu olduğundan emin olun. adresinden indirebilirsiniz.[Aspose.GIS for .NET indirme sayfası](https://releases.aspose.com/gis/net/).
- Geliştirme Ortamı: Geliştirme ortamınızı Visual Studio gibi uyumlu bir IDE ile kurun ve .NET programlama konusunda temel bilgiye sahip olun.
- Belge Dizini: Kod pasajındaki "Belge Dizininiz"i, GDB veri kümenizi depolamak istediğiniz uygun yolla değiştirin.
- C#'a aşinalık: Bu eğitimde C# programlama diline aşina olduğunuz varsayılmaktadır.
## Ad Alanlarını İçe Aktar
İlk adımlarda, .NET uygulamanızda Aspose.GIS işlevselliğinden yararlanmak için gerekli ad alanlarını içe aktarın:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Adım 1: Yeni Bir Dosya GDB Veri Kümesi Oluşturun
```csharp
string dataDir = "Your Document Directory";
using (var dataset = Dataset.Create(dataDir, Drivers.FileGdb))
{
    Console.WriteLine(dataset.LayersCount); // Çıkış: 0
    // Sonraki adımlarla devam edin...
}
```
 Açıklama: Bu adımda, aşağıdakileri kullanarak yeni bir GDB veri seti oluşturuyoruz:`Dataset.Create` yöntem. Dosya Geodatabase oluşturmak için yolu ve sürücüyü (FileGdb) belirtiyoruz. Konsol çıktısı, bu noktada sıfır olan başlangıç katman sayısını görüntüler.
## 2. Adım: Layer_1'i Oluşturun ve Doldurun
```csharp
using (var layer = dataset.CreateLayer("layer_1"))
{
    layer.Attributes.Add(new FeatureAttribute("value", AttributeDataType.Integer));
    for (int i = 0; i < 10; ++i)
    {
        var feature = layer.ConstructFeature();
        feature.SetValue("value", i);
        feature.Geometry = new Point(i, i);
        layer.Add(feature);
    }
}
```
Açıklama: Bu adım, veri kümesi içinde "katman_1" adlı bir katmanın oluşturulmasını içerir. Tamsayı türünde "değer" adlı bir özniteliği tanımlar ve katmanı, her biri bir nokta geometrisine sahip olan on özellik ile doldurur.
## 3. Adım: Layer_2'yi Oluşturun ve Doldurun
```csharp
using (var layer = dataset.CreateLayer("layer_2"))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```
Açıklama: Burada "layer_2" adında ikinci bir katman oluşturuyoruz ve çizgi dizisi geometrisine sahip tek bir özellik ekliyoruz.
## 4. Adım: Güncellenmiş Katman Sayısını Kontrol Edin
```csharp
Console.WriteLine(dataset.LayersCount); // Çıkış: 2
```
Açıklama: Son olarak iki katmanı ekledikten sonra güncellenen katman sayısını kontrol ediyoruz. Bu durumda çıktı 2 olmalıdır.
## Çözüm
Tebrikler! Aspose.GIS for .NET'i kullanarak başarılı bir şekilde yeni bir File GDB veri seti oluşturdunuz ve onu katmanlarla doldurdunuz. Bu eğitim, .NET ortamında coğrafi verilerle çalışmaya ilişkin temel bir anlayış sağlar.
## Sıkça Sorulan Sorular
### S: Aspose.GIS for .NET'i diğer GIS kütüphaneleriyle birlikte kullanabilir miyim?
Aspose.GIS for .NET bağımsız bir araç setidir; ancak işlevselliği geliştirmek için onu diğer .NET kitaplıklarıyla entegre edebilirsiniz.
### S: Aspose.GIS desteği için bir topluluk forumu var mı?
 Evet, şu konuda destek ve tartışmalar bulabilirsiniz:[Aspose.GIS Forumu](https://forum.aspose.com/c/gis/33).
### S: Aspose.GIS için nasıl geçici lisans alabilirim?
 Ziyaret edin[Geçici Lisans](https://purchase.aspose.com/temporary-license/) Geçici lisans alma konusunda bilgi için sayfa.
### S: Ek örnekler ve belgeler mevcut mu?
 Keşfedin[Aspose.GIS belgeleri](https://reference.aspose.com/gis/net/) Daha fazla örnek ve detaylı bilgi için.
### S: Aspose.GIS for .NET'i nereden satın alabilirim?
 Aspose.GIS for .NET'i şu adresten satın alabilirsiniz:[satın alma sayfası](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
