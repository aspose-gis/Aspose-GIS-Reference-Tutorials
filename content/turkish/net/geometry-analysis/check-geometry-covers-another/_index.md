---
title: Geometrinin Diğerini Kapsadığını Kontrol Edin
linktitle: Geometrinin Diğerini Kapsadığını Kontrol Edin
second_title: Aspose.GIS .NET API'si
description: Coğrafi verilerle verimli bir şekilde çalışmak, konumsal bilgileri analiz etmek ve haritalama özelliklerini .NET uygulamalarınıza entegre etmek için Aspose.GIS for .NET'i nasıl kullanacağınızı öğrenin.
type: docs
weight: 15
url: /tr/net/geometry-analysis/check-geometry-covers-another/
---
## giriiş
Aspose.GIS for .NET, geliştiricilere .NET uygulamalarında coğrafi verilerle verimli bir şekilde çalışabilmeleri için araçlar sağlayan güçlü bir kütüphanedir. İster bir haritalama uygulaması oluşturuyor olun, ister konumsal verileri analiz ediyor olun, ister coğrafi özellikleri yazılımınıza entegre ediyor olun, Aspose.GIS, geliştirme sürecinizi kolaylaştırmak için kapsamlı bir dizi işlevsellik sunar.
## Önkoşullar
Aspose.GIS for .NET'i kullanmaya başlamadan önce aşağıdaki önkoşulları oluşturduğunuzdan emin olun:
### 1. Visual Studio'yu yükleyin
Sisteminizde Visual Studio'nun kurulu olduğundan emin olun. Aspose.GIS for .NET, Visual Studio ile sorunsuz bir şekilde bütünleşerek sorunsuz bir geliştirme deneyimi sağlar.
### 2. Aspose.GIS for .NET'i edinin
 Aspose.GIS for .NET kütüphanesini şu adresten indirin:[İnternet sitesi](https://releases.aspose.com/gis/net/). Kitaplığı doğrudan indirebilir veya projenize yüklemek için NuGet gibi bir paket yöneticisi kullanabilirsiniz.
### 3. .NET Framework'e aşinalık
Aspose.GIS for .NET'i etkili bir şekilde kullanmak için .NET çerçevesi ve C# programlama dili hakkında temel bilgi gereklidir.
### 4. Dokümantasyona ve Desteğe Erişim
 Bakın[dokümantasyon](https://reference.aspose.com/gis/net/) Aspose.GIS API'leri ve işlevleri hakkında ayrıntılı bilgi için. Herhangi bir sorunla karşılaşırsanız veya sorularınız varsa,[Aspose.GIS forumu](https://forum.aspose.com/c/gis/33) yardım için.
### 5. İsteğe Bağlı: Geçici Lisans
 Aspose.GIS for .NET'i araştırıyorsanız, şu adresten geçici bir lisans alabilirsiniz:[Burada](https://purchase.aspose.com/temporary-license/) Kütüphanenin özelliklerini değerlendirmek.

## Ad Alanlarını İçe Aktar
Aspose.GIS for .NET'i projenizde kullanmadan önce gerekli ad alanlarını içe aktarmanız gerekir:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Şimdi Aspose.GIS for .NET kullanarak bir geometrinin diğerini kapsayıp kapsamadığının nasıl kontrol edileceğini anlamak için verilen örneği birden fazla adıma ayıralım.
## Adım 1: LineString Nesnesi Oluşturun
```csharp
var line = new LineString();
```
 Burada yeni bir örnek oluşturuyoruz`LineString` İki boyutlu bir uzayda birbirine bağlı çizgi parçalarının bir dizisini temsil eden nesne.
## Adım 2: LineString'e Nokta Ekleme
```csharp
line.AddPoint(0, 0);
line.AddPoint(1, 1);
```
 Puanları ekliyoruz`LineString` kullanmak`AddPoint` yöntem. Bu örnekte iki nokta ekliyoruz: (0, 0) ve (1, 1) ve bir doğru parçası oluşturuyoruz.
## Adım 3: Nokta Nesnesi Oluşturun
```csharp
var point = new Point(0, 0);
```
 Bir örnek oluştur`Point` iki boyutlu uzayda tek bir noktayı temsil eden nesne. Burada (0, 0) koordinatlarında bir nokta oluşturuyoruz.
## Adım 4: Çizginin Noktayı Kapsadığını Kontrol Edin
```csharp
Console.WriteLine(line.Covers(point));    // Doğru
```
 Kullan`Covers` çizginin noktayı kapsayıp kapsamadığını kontrol etme yöntemi. Bu durumda geri döner`True` çünkü (0, 0) noktası doğrunun üzerindedir.
## Adım 5: Noktanın Çizgiyle Kaplanıp Kaplanmadığını Kontrol Edin
```csharp
Console.WriteLine(point.CoveredBy(line)); // Doğru
```
Benzer şekilde, şunu kullanın:`CoveredBy` Noktanın çizgi tarafından kapsanıp kapsanmadığını kontrol etme yöntemi. (0, 0) noktası doğrunun üzerinde olduğundan şunu döndürür:`True`.

## Çözüm
Sonuç olarak Aspose.GIS for .NET, .NET uygulamalarında coğrafi verilerle çalışmak için güçlü araçlar sağlar. Yukarıda özetlenen adımları takip ederek Aspose.GIS işlevlerini verimli bir şekilde kullanarak bir geometrinin diğerini kapsayıp kapsamadığını kontrol edebilir, yazılımınızın mekansal analiz yeteneklerini geliştirebilirsiniz.
## SSS'ler
### Aspose.GIS for .NET'i ticari projelerimde kullanabilir miyim?
Evet, uygun lisansı aldıktan sonra Aspose.GIS for .NET'i hem ticari hem de ticari olmayan projelerde kullanabilirsiniz.
### Aspose.GIS for .NET, .NET Core ile uyumlu mu?
Evet, Aspose.GIS for .NET, hem .NET Framework hem de .NET Core ortamlarıyla uyumludur.
### Aspose.GIS for .NET çeşitli GIS formatlarını destekliyor mu?
Evet, Aspose.GIS for .NET, Shapefile, GeoJSON, KML ve daha fazlasını içeren çok çeşitli GIS formatlarını destekler.
### Aspose.GIS for .NET'in geliştirilmesine katkıda bulunabilir miyim?
Aspose.GIS for .NET, Aspose tarafından geliştirilen özel bir kütüphanedir, dolayısıyla harici geliştiricilerin katkıları kabul edilmez. Ancak kütüphaneyi geliştirmek için geri bildirim ve önerilerde bulunabilirsiniz.
### Aspose.GIS for .NET için güncellemeler ne sıklıkta yayınlanıyor?
 Aspose.GIS for .NET'e yönelik güncellemeler, yeni özellikler, geliştirmeler ve hata düzeltmeleri sunmak üzere düzenli olarak yayınlanmaktadır. Kontrol edin[İnternet sitesi](https://releases.aspose.com/gis/net/) En son sürümler için.