---
title: Aspose.GIS for .NET ile Dışbükey Gövdeyi Hesaplayın
linktitle: Geometri Dışbükey Gövde Alın
second_title: Aspose.GIS .NET API'si
description: Aspose.GIS'i kullanarak .NET'te bir geometrinin dışbükey gövdesini nasıl hesaplayacağınızı öğrenin. Kod örnekleri ve SSS içeren kapsamlı eğitim.
type: docs
weight: 20
url: /tr/net/geometry-analysis/get-geometry-convex-hull/
---
## giriiş
Aspose.GIS for .NET, .NET uygulamalarında coğrafi bilgi sistemleri (GIS) ile çalışmak için geniş bir işlevsellik yelpazesi sunan güçlü bir kütüphanedir. İster haritalama uygulamaları oluşturuyor olun, ister mekansal verileri analiz ediyor, ister jeouzaysal operasyonlar gerçekleştiriyor olun, Aspose.GIS, sezgisel API'si ve kapsamlı özellik seti ile süreci basitleştirir.
## Önkoşullar
Aspose.GIS for .NET kullanarak bir geometrinin dışbükey gövdesinin nasıl elde edileceğine ilişkin eğitime dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
### 1. Aspose.GIS for .NET'i yükleyin
 Ziyaret edin[İndirme: {link](https://releases.aspose.com/gis/net/) Aspose.GIS for .NET'in en son sürümünü edinmek için. .NET ortamınıza sorunsuz entegrasyon için belgelerde sağlanan kurulum talimatlarını izleyin.
### 2. .NET Geliştirmeye Aşinalık
Bu eğitimdeki örneklerin yanı sıra temel C# ve .NET geliştirme bilgisi gereklidir. .NET'te yeniyseniz, başlamak için giriş kaynaklarını keşfetmeyi düşünün.
### 3. Geliştirme Ortamını Kurun
Visual Studio veya .NET geliştirme için tercih edilen herhangi bir IDE de dahil olmak üzere uygun bir geliştirme ortamının yapılandırılmış olduğundan emin olun.

## Ad Alanlarını İçe Aktar
.NET projenize Aspose.GIS tarafından sağlanan işlevlere erişmek için gerekli ad alanlarını içe aktararak başlayın.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
Bu ad alanı, coğrafi verilerle çalışmaya yönelik sınıflar ve yöntemler de dahil olmak üzere Aspose.GIS for .NET'in temel işlevlerine erişim sağlar.

Sistem ad alanı, .NET çerçevesinin temel giriş/çıkış işlemleri ve diğer temel işlevleri için gereklidir.

Şimdi Aspose.GIS for .NET'i kullanarak bir geometrinin dışbükey gövdesini elde etmenin adım adım sürecine dalalım.
## Adım 1: Çok Noktalı Geometri Oluşturun
İlk olarak, birden çok nokta içeren çok noktalı bir geometri tanımlayın. Bu noktalar dışbükey gövdenin hesaplanmasında temel oluşturacaktır.
```csharp
var geometry = new MultiPoint
{
    new Point(3, 2),
    new Point(0, 0),
    new Point(6, 5),
    new Point(5, 10),
    new Point(10, 0),
    new Point(8, 2),
    new Point(4, 3),
};
```
Bu kod parçacığı, yedi farklı noktadan oluşan çok noktalı bir geometri oluşturur.
## Adım 2: Dışbükey Gövde Alın
 Ardından, şunu çağırın:`GetConvexHull()` Dışbükey gövdeyi hesaplamak için geometri nesnesindeki yöntem.
```csharp
var convexHull = geometry.GetConvexHull();
```
Bu yöntem, girdi geometrisinin dışbükey kabuğunu hesaplar ve dışbükey kabuğu temsil eden yeni bir geometri elde edilir.
## Adım 3: Dışbükey Gövde Noktalarına Erişim
Dışbükey gövde hesaplandıktan sonra onu oluşturan noktalara erişebilirsiniz.
```csharp
var ring = (ILinearRing)convexHull;
for (int i = 0; i < ring.Count; ++i)
{
    Console.WriteLine("[{0}] = ({1} {2})", i, ring[i].X, ring[i].Y);
}
```
Bu döngü, dışbükey gövdenin noktaları boyunca yinelenir ve bunların koordinatlarını konsola yazdırır.

## Çözüm
Bu derste, bir geometrinin dışbükey gövdesini elde etmek için Aspose.GIS for .NET'in nasıl kullanılacağını araştırdık. Adım adım kılavuzu takip ederek, coğrafi verilerin verimli bir şekilde işlenmesine ve analizine olanak tanıyarak, coğrafi uzamsal işlevleri .NET uygulamalarınıza sorunsuz bir şekilde entegre edebilirsiniz.
## SSS'ler
### S: Aspose.GIS for .NET hem masaüstü hem de web uygulamaları için uygun mudur?
Evet, Aspose.GIS for .NET hem masaüstü hem de web uygulamalarında kullanılabilir ve coğrafi veri işlemede çok yönlülük sunar.
### S: Aspose.GIS çeşitli coğrafi formatları destekliyor mu?
Kesinlikle Aspose.GIS, şekil dosyaları, GeoJSON, KML ve daha fazlası dahil olmak üzere çok çeşitli coğrafi formatları destekleyerek çeşitli veri kaynaklarıyla kesintisiz birlikte çalışabilirliği kolaylaştırır.
### S: Satın almadan önce Aspose.GIS for .NET'i deneyebilir miyim?
 Evet, sağlanan Aspose.GIS for .NET ücretsiz deneme sürümünden yararlanabilirsiniz.[bağlantı](https://releases.aspose.com/)özelliklerini keşfetmenize ve projelerinize uygunluğunu değerlendirmenize olanak tanır.
### S: Aspose.GIS için nasıl geçici lisans alabilirim?
 Aspose.GIS için geçici lisanslar belirlenen adresten edinilebilir.[geçici lisans bağlantısı](https://purchase.aspose.com/temporary-license/)Deneme sürelerinde veya kısa süreli projelerde kesintisiz kullanıma olanak sağlar.
### S: Aspose.GIS ile ilgili nereden yardım alabilirim veya tartışmalara katılabilirim?
Destek, rehberlik ve topluluk etkileşimi için Aspose.GIS forumunu ziyaret edin[Burada](https://forum.aspose.com/c/gis/33), diğer geliştiricilerle iletişim kurabileceğiniz, sorular sorabileceğiniz ve içgörüleri paylaşabileceğiniz yer.