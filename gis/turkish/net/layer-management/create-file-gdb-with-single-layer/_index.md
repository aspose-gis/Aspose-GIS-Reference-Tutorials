---
date: 2026-06-30
description: Aspose.GIS for .NET kullanarak bir File Geodatabase içinde vector layer
  oluşturmayı öğrenin. Coğrafi verileri spatial reference WGS84 ve file gdb seçenekleriyle
  yönetin.
keywords:
- create vector layer
- add line feature
- manage geospatial data
- feature count example
- file gdb compression
linktitle: Tek Katmanlı File GDB Oluştur
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create vector layer in a File Geodatabase using Aspose.GIS
    for .NET. Manage geospatial data with spatial reference WGS84 and file gdb options.
  headline: Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial
  type: TechArticle
- description: Learn how to create vector layer in a File Geodatabase using Aspose.GIS
    for .NET. Manage geospatial data with spatial reference WGS84 and file gdb options.
  name: Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial
  steps:
  - name: '**Aspose.GIS for .NET** – download it from the [Aspose.GIS for .NET download
      page](https://releases.aspose.com/gis/net/).'
    text: '**Aspose.GIS for .NET** – download it from the [Aspose.GIS for .NET download
      page](https://releases.aspose.com/gis/net/).'
  - name: '**A .NET development environment** – Visual Studio, Rider, or the `dotnet`
      CLI.'
    text: '**A .NET development environment** – Visual Studio, Rider, or the `dotnet`
      CLI.'
  - name: '**A folder** where the File GDB will be created (we’ll call it *Your Document
      Directory*).'
    text: '**A folder** where the File GDB will be created (we’ll call it *Your Document
      Directory*).'
  type: HowTo
- questions:
  - answer: It means adding a new vector dataset (points, lines, or polygons) to a
      geodatabase file.
    question: What does “create vector layer” mean?
  - answer: Aspose.GIS for .NET provides full support for File GDB creation and editing.
    question: Which library should I use?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license for development?
  - answer: Yes – use `SpatialReferenceSystem.Wgs84` for the common WGS84 datum.
    question: Can I set the spatial reference?
  - answer: Less than 30 lines to create the GDB, add a line feature, and read back
      the feature count.
    question: How many lines of code?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: File GDB'de vector layer Oluştur – Aspose.GIS .NET Öğreticisi
url: /tr/net/layer-management/create-file-gdb-with-single-layer/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# File GDB'de Vektör Katmanı Oluştur

## Giriş
Eğer bir File Geodatabase (GDB) içinde **create vector layer** oluşturmanız ve coğrafi verileri verimli bir şekilde yönetmeniz gerekiyorsa, Aspose.GIS for .NET size temiz, kod‑ilk yaklaşımı sunar. Bu adım‑adım kılavuzda bir çizgi özelliği nasıl yazılır, dosya GDB seçenekleri nasıl yapılandırılır ve WGS84 uzamsal referansı ile nasıl çalışılır gösteriyoruz — hepsi birkaç C# satırıyla. Sonunda bir katmandaki özellikleri sayabilir ve elde edilen GDB'yi herhangi bir .NET haritalama veya analiz iş akışına entegre edebilirsiniz.

## Hızlı Yanıtlar
- **“create vector layer” ne anlama geliyor?** Yeni bir vektör veri kümesi (nokta, çizgi veya çokgen) bir coğrafi veritabanı dosyasına eklemek anlamına gelir.  
- **Hangi kütüphaneyi kullanmalıyım?** Aspose.GIS for .NET, File GDB oluşturma ve düzenleme için tam destek sağlar.  
- **Geliştirme için lisansa ihtiyacım var mı?** Test için ücretsiz deneme çalışır; üretim için ticari lisans gereklidir.  
- **Uzamsal referansı ayarlayabilir miyim?** Evet – yaygın WGS84 datum'u için `SpatialReferenceSystem.Wgs84` kullanın.  
- **Kaç satır kod?** GDB'yi oluşturmak, bir çizgi özelliği eklemek ve özellik sayısını geri okumak için 30 satırdan az.

## “create vector layer” işlemi nedir?
Vektör katmanı oluşturmak, geometrik nesneleri (nokta, çizgi, çokgen) ve bunların özniteliklerini depolayan yeni bir tablo tanımlar. Her satır bir özelliği temsil eder ve geometri sütunu şekli tutar. Aspose.GIS'te bunu bir `FeatureClass`'ı `FileGdbDataSource` içinde örnekleyerek ve geometri tipini belirterek oluşturursunuz.

## Vektör katmanı oluşturmak için Aspose.GIS'i neden kullanmalısınız?
Aspose.GIS dış bağımlılıkları ortadan kaldırır ve **50+** GIS formatını destekler, .NET geliştiricileri için tek durak çözüm sunar.  
Yerleşik dosya GDB sıkıştırması (tipik vektör verileri için %70'e kadar azalma), uzamsal indeksleme ve kutudan çıkar çıkmaz tam WGS84 işleme sağlar. Kütüphane .NET Framework 4.6+, .NET Core 2.0+ ve .NET 5/6 üzerinde çalışır, böylece ek yerel kütüphaneler olmadan herhangi bir modern Windows veya çapraz platform ortamını hedefleyebilirsiniz.

## Ön Koşullar
1. **Aspose.GIS for .NET** – [Aspose.GIS for .NET indirme sayfasından](https://releases.aspose.com/gis/net/) indirin.  
2. **Bir .NET geliştirme ortamı** – Visual Studio, Rider veya `dotnet` CLI.  
3. **Bir klasör** File GDB'nin oluşturulacağı (biz ona *Your Document Directory* diyeceğiz).

## Ad Alanlarını İçe Aktarın
`using` ifadeleri gerekli türleri kapsam içine getirir.

`Document` ad alanı temel GIS nesnelerini sağlar, `System.IO` ise dosya yollarını yönetir.

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

## Adım 1: Belge Dizinini Ayarlayın
`"Your Document Directory"` ifadesini, File GDB'nin bulunmasını istediğiniz mutlak yol ile değiştirin.  
Dosyayı önceden oluşturmak, yeni kullanıcıların sıkça karşılaştığı “File not found” hatasını önler.

```csharp
string dataDir = "Your Document Directory";
```

## Adım 2: Tek Katmanlı Bir File Geodatabase Oluşturun
FileGdbOptions, bir File Geodatabase için sıkıştırma, uzamsal indeksleme ve diğer ayarları yapılandırmanıza olanak tanıyan bir sınıftır.  
Bu kod parçacığı `FileGdbOptions` kullanarak **creates a vector layer** oluşturur, basit bir çizgi özelliği yazar ve **spatial reference WGS84** kullanan bir File GDB'ye kaydeder.

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

## Adım 3: File Geodatabase'i Açın ve Katman Bilgilerini Alın
`FileGdbDataSource`, File Geodatabase'leri oluşturmak ve açmak için giriş noktasıdır.  
`FeatureClass`, bir geodatabase içindeki vektör katmanını temsil eder ve özelliklerine erişim sağlar.  
Burada veri kümesini açarak ve özellik sayısını yazdırarak **count features in the layer** gerçekleştiriyoruz – bu örnekte `1`.

```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Output: Features count: 1
}
```

## Katmanın doğru oluşturulduğunu nasıl doğrularsınız?
`FileGdbDataSource.Open` ile geodatabase'i açın ve `FeatureClass`'ı sorgulayın. `Count` özelliği toplam özellik sayısını döndürür, çizginin kalıcı olarak kaydedildiğini doğrular. Bu hızlı doğrulama adımı, özellikle toplu içe aktarımları otomatikleştirirken sorunları erken yakalamanıza yardımcı olur.

## Yaygın Sorunlar ve Çözümler
| Sorun | Sebep | Çözüm |
|-------|--------|-----|
| **`File not found`** | Yanlış `path` değişkeni | `dataDir`'in mevcut bir klasöre işaret ettiğini ve `path`'in bir dosya adıyla birleştirildiğini doğrulayın, örn., `Path.Combine(dataDir, "MyData.gdb")`. |
| **`Unsupported geometry`** | File GDB'de izin verilmeyen bir geometri tipi kullanmak | Temel katmanlar için `Point`, `LineString` veya `Polygon` kullanın. |
| **`License not set`** | Üretimde geçerli bir lisans olmadan çalıştırmak | Lisansınızı şu şekilde kaydedin: `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Sıkça Sorulan Sorular
### Aspose.GIS for .NET'i mevcut .NET projelerimde kullanabilir miyim?
Evet, Aspose.GIS for .NET mevcut .NET projelerinize sorunsuz bir şekilde entegre edilebilir.

### Aspose.GIS for .NET için bir deneme sürümü mevcut mu?
Evet, [ücretsiz deneme sürümünü](https://releases.aspose.com/) indirerek Aspose.GIS for .NET'in özelliklerini keşfedebilirsiniz.

### Aspose.GIS for .NET için ayrıntılı belgeleri nerede bulabilirim?
Aspose.GIS for .NET hakkında kapsamlı bilgi için [belgelere](https://reference.aspose.com/gis/net/) bakın.

### Aspose.GIS for .NET için destek nasıl alabilirim?
Topluluk desteği ve yardım için [Aspose.GIS forumunu](https://forum.aspose.com/c/gis/33) ziyaret edin.

### Aspose.GIS for .NET için geçici lisanslar mevcut mu?
Evet, Aspose.GIS for .NET için bir [geçici lisans](https://purchase.aspose.com/temporary-license/) alabilirsiniz.

---

**Son Güncelleme:** 2026-06-30  
**Test Edilen Versiyon:** Aspose.GIS 24.11 for .NET  
**Yazar:** Aspose

## İlgili Eğitimler

- [Aspose.GIS ile File Geodatabase .NET Veri Kümesi Oluştur](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Vektör Katmanı Oluştur ve Katman Uzamsal Referans Sistemini Ayarla](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Aspose.GIS ile File GDB Veri Kümesinden Katmanı Silme](/gis/net/layer-data-operations/remove-layers-from-file-gdb-dataset/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}