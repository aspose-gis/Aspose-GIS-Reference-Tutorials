---
date: 2026-01-10
description: Aspose.GIS for .NET kullanarak shapefile'ı C# ile nasıl okuyacağınızı
  ve bir poligon shapefile'ını linestring'e nasıl dönüştüreceğinizi öğrenin. Açık
  adım adım rehberlikle GIS geliştirmelerinizi hızlandırın.
linktitle: Convert Polygon Shapefile to Linestring
second_title: Aspose.GIS .NET API
title: Shapefile Okuma C# – Poligon Shapefile'ı Linestring'e Dönüştür
url: /tr/net/layer-management/convert-polygon-shapefile-to-linestring/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Shapefile Okuma C# – Poligon Shapefile'ını Linestring'e Dönüştür

## Introduction
.NET'te coğrafi bilgi sistemleri (GIS) ile çalışıyorsanız, **read shapefile c#** veriyi manipüle edebilmeden önce yaygın bir ilk adımdır. Aspose.GIS bu süreci birkaç satır kodla basitleştirir ve bir Poligon Shapefile'ını Linestring'e dönüştürmenizi sağlar. Bu yetenek, rotalama, ağ analizi veya veri görselleştirme gibi görevler için poligon veri setlerinden doğrusal özellikler çıkarmanız gerektiğinde özellikle kullanışlıdır.

## Quick Answers
- **Hangi kütüphane shapefile c# okumanıza yardımcı olur?** Aspose.GIS for .NET  
- **Poligonu bir çizgiye dönüştürebilir miyim?** Evet – poligonun dış halkasını `LineString` ile kullanın.  
- **Üretim için lisansa ihtiyacım var mı?** Üretim kullanımında ticari bir lisans gereklidir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Deneme sürümü mevcut mu?** Kesinlikle – Aspose sitesinden ücretsiz deneme sürümünü indirebilirsiniz.

## What is “read shapefile c#”?
C#'ta bir shapefile okumak, `.shp` dosyasını belleğe yükleyerek geometrilerini sorgulamanıza, değiştirmenize veya dönüştürmenize olanak tanır. Aspose.GIS, düşük‑seviye detayları soyutlayan ve GIS mantığınıza odaklanmanızı sağlayan basit bir API sunar.

## Why convert polygon to line with Aspose.GIS?
- **Topolojiyi koru** – dönüşüm, her poligonun dış sınırını tam olarak korur.  
- **Performans** – kütüphane büyük veri setleri için optimize edilmiştir, toplu dönüşümler hızlı gerçekleşir.  
- **Esneklik** – daha sonra linestring'leri başka bir shapefile, GeoJSON veya desteklenen herhangi bir formata yazabilirsiniz.

## Prerequisites
Tutoriala başlamadan önce aşağıdakilerin hazır olduğundan emin olun:

- **Aspose.GIS Library** – [web sitesinden](https://releases.aspose.com/gis/net/) Aspose.GIS kütüphanesini indirin ve kurun.  
- **Shapefile Data** – Dönüştürme için bir Poligon Shapefile'ınız olsun. Yoksa örnek veri bulabilir ya da kendiniz oluşturabilirsiniz.  
- **Development Environment** – Gerekli araçlarla (.NET SDK, Visual Studio vb.) .NET geliştirme ortamınızı kurun.

## Import Namespaces
C# kodunuzda gerekli sınıf ve metodlara erişmek için Aspose.GIS ad alanlarını içe aktarmanız gerekir. Kod dosyanızın başına aşağıdaki ad alanlarını ekleyin:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## How to convert shapefile from polygon to line?
Aşağıda, Aspose.GIS kullanarak **shapefile** verisini poligondan çizgiye dönüştürmenizi gösteren adım‑adım bir rehber bulabilirsiniz.

### Step 1: Set the Document Directory
```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```
`"Your Document Directory"` ifadesini shapefile'ınızın bulunduğu gerçek yol ile değiştirin.

### Step 2: Open the Source Shapefile
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
Bu satır, **kaynak Poligon Shapefile'ını** açar ve özelliklerini okuyabilmenizi sağlar.

### Step 3: Create the Destination Linestring Shapefile
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
Burada, dönüştürülmüş geometrileri depolayacak **yeni bir Linestring Shapefile** oluşturulur.

### Step 4: Iterate Through Source Features
```csharp
foreach (Feature sourceFeature in source)
{
    // Rest of the code will go here
}
```
Döngü, orijinal dosyadaki her poligon özelliği üzerinden geçer.

### Step 5: Convert Polygon to Linestring and Write to Destination
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
Bu blokta **poligon çizgiye** (`LineString`) dönüştürülür ve yeni özellik hedef shapefile'a eklenir.

## Common Issues and Tips
- **Koordinat Sistemi Uyumsuzluğu** – Hem kaynak hem de hedef katmanların aynı mekansal referansı kullandığından emin olun; aksi takdirde çizgiler yer değiştirebilir.  
- **Büyük Dosyalar** – Çok büyük shapefile'ları işlerken, tüm veriyi bir kerede belleğe yüklemek yerine özellikleri akış (stream) olarak işlemeyi düşünün.  
- **Boş Geometriler** – Boş geometrilere sahip özelliklere karşı koruma sağlayarak çalışma zamanı hatalarını önleyin.

## Frequently Asked Questions

**S: Aspose.GIS tüm .NET sürümleriyle uyumlu mu?**  
C: Evet, Aspose.GIS çeşitli .NET sürümlerini destekler ve geliştirme ortamınızla uyumludur.

**S: Aspose.GIS'i ticari projelerde kullanabilir miyim?**  
C: Evet. Ticari projelerde Aspose.GIS kullanmak için [buradan](https://purchase.aspose.com/buy) lisans satın alabilirsiniz.

**S: Örnekler veya dokümantasyon mevcut mu?**  
C: Evet, kapsamlı dokümantasyon ve örnekleri [dokümantasyon sayfasında](https://reference.aspose.com/gis/net/) bulabilirsiniz.

**S: Deneme sürümü var mı?**  
C: Evet, ücretsiz deneme sürümünü [bu linkten](https://releases.aspose.com/) keşfedebilirsiniz.

**S: Yardım veya destek nereden alınır?**  
C: Her türlü soru ve destek için [Aspose.GIS forumunu](https://forum.aspose.com/c/gis/33) ziyaret edebilirsiniz.

---

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}