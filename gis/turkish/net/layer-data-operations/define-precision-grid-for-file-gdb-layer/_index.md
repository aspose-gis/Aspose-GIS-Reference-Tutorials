---
date: 2025-12-28
description: Aspose.GIS for .NET kullanarak bir File GDB katmanı için ızgara ayarlamayı,
  katmana özellik eklemeyi ve koordinat aralığını doğrulamayı öğrenin.
linktitle: Define Precision Grid for File GDB Layer
second_title: Aspose.GIS .NET API
title: Aspose.GIS'te File GDB Katmanı İçin Izgara Nasıl Ayarlanır
url: /tr/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS'te Dosya GDB Katmanı İçin Izgara Nasıl Ayarlanır

## Introduction
Bu öğreticide, Aspose.GIS for .NET kullanarak bir File Geodatabase (GDB) katmanı için **izgara nasıl ayarlanır** öğreneceksiniz. Hassas bir ızgara ayarlamak, **koordinat aralığını doğrulamanıza** yardımcı olur, out‑of‑range hatalarını önler ve **katmana özellik eklediğiniz** verilerin doğru ve güvenilir kalmasını sağlar. Her adımı adım adım inceleyecek, ayarların neden önemli olduğunu açıklayacak ve yaygın tuzaklarla nasıl başa çıkılacağını göstereceğiz.

## Quick Answers
- **“Izgara ayarlamak” ne anlama gelir?** Bir GIS katmanı için koordinat hassasiyetini ve geçerli aralığını tanımlar.  
- **Neden hassas bir ızgara kullanmalı?** Verilerinizi geçersiz koordinatlardan korur ve depolama verimliliğini artırır.  
- **Bu özelliği hangi kütüphane sağlar?** Aspose.GIS for .NET.  
- **Lisans gerekir mi?** Deneme sürümü mevcuttur; üretim için ticari lisans gereklidir.  
- **Bunu .NET Core ile kullanabilir miyim?** Evet, Aspose.GIS .NET Framework ve .NET Core’u destekler.

## What is a Precision Grid and Why Set It?
Hassas bir ızgara, GIS motorunun koordinat değerlerini nasıl yuvarlayıp saklayacağını belirten bir dizi parametredir (origin, scale vb.). Bir ızgara tanımlayarak **koordinat aralığını otomatik olarak doğrular** ve ızgara dışına bir nokta eklemeye çalıştığınızda bir istisna fırlatılır—bu da **out of range** senaryolarını geliştirme aşamasında erken yakalamanıza yardımcı olur.

## Prerequisites
Başlamadan önce aşağıdaki bileşenlerin kurulu olduğundan emin olun:

1. **Visual Studio** – herhangi bir yeni sürüm (Community, Professional veya Enterprise).  
2. **Aspose.GIS for .NET** – [web sitesinden](https://releases.aspose.com/gis/net/) indirin.  
3. **Temel C# bilgisi** – .NET console projeleri oluşturabilmelisiniz.

## Import Namespaces
Aspose.GIS ile çalışmak için gerekli ad alanlarını içe aktarın:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Text;
```

## How to Set Grid in a File GDB Layer
Aşağıda, ızgarayı tam olarak nasıl yapılandıracağınızı, bir katman oluşturacağınızı ve **katmana özellik ekleme** işlemini güvenli bir şekilde nasıl yapacağınızı adım adım gösteren bir kılavuz bulacaksınız.

### Step 1: Create a Dataset
Yeni bir File Geodatabase veri kümesi oluşturuyoruz. Katman bu veri kümesinde yer alacak.

```csharp
var path = "Your Document Directory" + "PrecisionGrid_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

### Step 2: Define Precision Grid Options
Burada ızgara parametrelerini belirtiyoruz. Projenizin koordinat sistemine uygun olacak şekilde origin ve scale değerlerini ayarlayın.

```csharp
var options = new FileGdbOptions
{
    CoordinatePrecisionGrid = new FileGdbCoordinatePrecisionGrid
    {
        XOrigin = -400,
        YOrigin = -400,
        XYScale = 1e10,
        MOrigin = 0,
        MScale = 1e4,
    },
    EnsureValidCoordinatesRange = true,
};
```

*`EnsureValidCoordinatesRange = true` bayrağı, Aspose.GIS'in **koordinat aralığını doğrulamasını** eklediğiniz her özellik için sağlar.*

### Step 3: Create a Layer with the Grid
Şimdi, az önce tanımladığımız ızgara seçeneklerini uygulayarak veri kümesi içinde yeni bir katman oluşturuyoruz. WGS84 uzamsal referans sistemini kullanacağız.

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
```

### Step 4: Add Features to the Layer
İki nokta özelliği oluşturuyoruz. İlk nokta ızgara içinde yer alırken, ikincisi kasıtlı olarak dışarıda bırakılarak **out of range** hatalarının nasıl ele alınacağını gösteriyor.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(10, 20) { M = 10.1282 };
layer.Add(feature);
feature = layer.ConstructFeature();
feature.Geometry = new Point(-410, 0) { M = 20.2343 };
```

### Step 5: Handle Exceptions When Adding Out‑of‑Range Features
İkinci özelliği eklemeye çalışmak, X koordinatı (`-410`) tanımlı ızgaranın dışına çıktığı için bir istisna tetikleyecektir. İstisna yakalanır ve net bir mesaj yazdırılır.

```csharp
try
{
    layer.Add(feature);
}
catch (GisException e)
{
    Console.WriteLine(e.Message); // X value -410 is out of valid range.
}
```

### Step 6: Clean Up
`using` ifadeleri, veri kümesi ve katmanın otomatik olarak kapatılıp serbest bırakılmasını sağlar, böylece tüm kaynaklar serbest bırakılır.

## Common Issues and Solutions
| Issue | Why It Happens | Fix |
|-------|----------------|-----|
| **Exception: “X value … is out of valid range.”** | Koordinatlar hassas ızgara dışına düşer. | `XOrigin`, `YOrigin` veya `XYScale` değerlerini verilerinizi kapsayacak şekilde ayarlayın veya giriş verilerinin tanımlı aralık içinde olduğundan emin olun. |
| **Features not appearing in GIS viewer** | Katman kaydedilmemiş veya yanlış uzamsal referans kullanılmış. | `SpatialReferenceSystem.Wgs84` görüntüleyicinin CRS’iyle eşleşiyor mu kontrol edin ve `Dataset.Create` işleminin başarılı olduğundan emin olun. |
| **M values ignored** | `MScale` 0 ya da çok düşük ayarlanmış. | Ölçüm değerlerini saklamak için makul bir `MScale` (ör. `1e4`) belirleyin. |

## Frequently Asked Questions

**Q: Aspose.GIS for .NET'i diğer GIS dosya formatlarıyla kullanabilir miyim?**  
A: Evet, Aspose.GIS Shapefile, GeoJSON, KML ve daha birçok formatı destekler.

**Q: Aspose.GIS for .NET .NET Core ile uyumlu mu?**  
A: Kesinlikle. Kütüphane .NET Framework, .NET Core ve .NET 5/6+ ile çalışır.

**Q: Buffering veya intersection gibi uzamsal işlemler yapabilir miyim?**  
A: Evet, API buffer, intersect ve mesafe hesaplama gibi yöntemleri içerir.

**Q: Aspose.GIS koordinat dönüşüm yetenekleri sunuyor mu?**  
A: Evet, yerleşik reprojection araçlarıyla geometrileri farklı uzamsal referans sistemleri arasında dönüştürebilirsiniz.

**Q: Deneme sürümü mevcut mu?**  
A: Evet, ücretsiz deneme sürümünü [web sitesinden](https://releases.aspose.com/gis/net/) indirebilirsiniz.

---

**Last Updated:** 2025-12-28  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}