---
date: 2026-01-10
description: Aspose.GIS for .NET kullanarak bir Dosya Coğrafi Veritabanı'nda vektör
  katmanı nasıl oluşturulacağını öğrenin. Coğrafi verileri WGS84 uzamsal referansı
  ve dosya gdb seçenekleriyle yönetin.
linktitle: Create File GDB with Single Layer
second_title: Aspose.GIS .NET API
title: File GDB'de Vektör Katmanı Oluşturma – Aspose.GIS .NET Öğreticisi
url: /tr/net/layer-management/create-file-gdb-with-single-layer/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dosya GDB'de Vektör Katmanı Oluşturma

## Giriş
Dosya Coğrafi Veritabanı (GDB) içinde **vektör katmanı** oluşturmanız ve coğrafi verileri verimli bir şekilde yönetmeniz gerekiyorsa, Aspose.GIS for .NET size temiz, kod‑ilk yaklaşımı sunar. Bu adım‑adım kılavuzda bir çizgi özelliği nasıl yazılır, dosya gdb seçenekleri nasıl yapılandırılır ve WGS84 uzamsal referansı nasıl kullanılır gösteriyoruz — tümü birkaç C# satırıyla. Sonunda bir katmandaki özellikleri sayabilir ve elde edilen GDB'yi herhangi bir .NET haritalama veya analiz iş akışına entegre edebilirsiniz.

## Hızlı Yanıtlar
- **“vektör katmanı oluşturma” ne anlama gelir?** Yeni bir vektör veri kümesi (nokta, çizgi veya çokgen) bir coğrafi veritabanı dosyasına eklemek anlamına gelir.  
- **Hangi kütüphaneyi kullanmalıyım?** Aspose.GIS for .NET, Dosya GDB oluşturma ve düzenleme için tam destek sağlar.  
- **Geliştirme için lisansa ihtiyacım var mı?** Test için ücretsiz deneme sürümü çalışır; üretim için ticari lisans gereklidir.  
- **Uzamsal referansı ayarlayabilir miyim?** Evet – yaygın WGS84 datumu için `SpatialReferenceSystem.Wgs84` kullanın.  
- **Kaç satır kod?** GDB'yi oluşturmak, bir çizgi özelliği eklemek ve özellik sayısını geri okumak için 30 satırdan az.

## “Vektör katmanı oluşturma” işlemi nedir?
Vektör katmanı oluşturmak, geometrik nesneleri (nokta, çizgi, çokgen) ve bunların özniteliklerini depolayan yeni bir tabloyu bir coğrafi veritabanı içinde tanımlamak anlamına gelir. Bu işlem, **coğrafi verileri yönetmesi** gereken herhangi bir GIS‑tabanlı uygulamanın temelini oluşturur.

## Vektör katmanı oluşturmak için neden Aspose.GIS kullanılmalı?
- **Sıfır dış bağımlılık** – API, .NET Framework, .NET Core ve .NET 5/6 üzerinde kutudan çıkar çıkmaz çalışır.  
- **Dosya GDB için tam destek** – sıkıştırma, uzamsal indeksleme ve daha fazlasını kontrol etmek için `FileGdbOptions` yapılandırabilirsiniz.  
- **Yerleşik uzamsal referans işleme** – küresel koordinat sisteminde çalışmak için sadece `SpatialReferenceSystem.Wgs84` geçirin.  
- **Basit API** – çizgi özelliği yazın, bir katmana ekleyin ve sadece birkaç metod çağrısıyla özellik sayısını alın.

## Önkoşullar
Başlamadan önce, şunların olduğundan emin olun:

1. **Aspose.GIS for .NET** – bunu [Aspose.GIS for .NET indirme sayfasından](https://releases.aspose.com/gis/net/) indirin.  
2. **Bir .NET geliştirme ortamı** – Visual Studio, Rider veya `dotnet` CLI.  
3. **Bir klasör** – Dosya GDB'nin oluşturulacağı yer (biz buna *Your Document Directory* diyeceğiz).

## Ad Alanlarını İçe Aktarın
C# dosyanızın en üstüne gerekli `using` ifadelerini ekleyin:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```

## Adım 1: Belge Dizininizi Ayarlayın
```csharp
string dataDir = "Your Document Directory";
```
`"Your Document Directory"` ifadesini, Dosya GDB'nin bulunmasını istediğiniz mutlak yol ile değiştirin.

## Adım 2: Tek Katmanlı Bir Dosya Coğrafi Veritabanı Oluşturun
```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
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
Bu kod parçacığı `FileGdbOptions` kullanarak **bir vektör katmanı oluşturur**, basit bir çizgi özelliği yazar ve **WGS84 uzamsal referansı** kullanan bir Dosya GDB'de depolar.

## Adım 3: Dosya Coğrafi Veritabanını Açın ve Katman Bilgilerini Alın
```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Output: Features count: 1
}
```
Burada veri kümesini açarak ve özellik sayısını yazdırarak **katmandaki özellikleri sayıyoruz** – bu örnekte `1`.

## Yaygın Sorunlar ve Çözümleri
| Sorun | Neden | Çözüm |
|-------|--------|-----|
| **`File not found`** | Yanlış `path` değişkeni | `dataDir`'in mevcut bir klasöre işaret ettiğini ve `path`'in bir dosya adıyla birleştirildiğini doğrulayın, örn., `Path.Combine(dataDir, "MyData.gdb")`. |
| **`Unsupported geometry`** | Dosya GDB'de izin verilmeyen bir geometri türü kullanılıyor | Temel katmanlar için `Point`, `LineString` veya `Polygon` kullanın. |
| **`License not set`** | Üretimde geçerli bir lisans olmadan çalışıyor | Lisansınızı şu şekilde kaydedin: `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Sık Sorulan Sorular
### Aspose.GIS for .NET'i mevcut .NET projelerimde kullanabilir miyim?
Evet, Aspose.GIS for .NET mevcut .NET projelerinize sorunsuz bir şekilde entegre edilebilir.

### Aspose.GIS for .NET için deneme sürümü mevcut mu?
Evet, [ücretsiz deneme sürümünü](https://releases.aspose.com/) indirerek Aspose.GIS for .NET'in özelliklerini keşfedebilirsiniz.

### Aspose.GIS for .NET için ayrıntılı belgeleri nerede bulabilirim?
Aspose.GIS for .NET hakkında kapsamlı bilgi için [belgelere](https://reference.aspose.com/gis/net/) bakın.

### Aspose.GIS for .NET için destek nasıl alabilirim?
Topluluk desteği ve yardım için [Aspose.GIS forumunu](https://forum.aspose.com/c/gis/33) ziyaret edin.

### Aspose.GIS for .NET için geçici lisanslar mevcut mu?
Evet, Aspose.GIS for .NET için bir [geçici lisans](https://purchase.aspose.com/temporary-license/) alabilirsiniz.

---

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}