---
date: 2026-06-10
description: Aspose.GIS for .NET'i ExtendedPostGis varyantı ile kullanarak linestring
  geometrisini .NET'te oluşturmayı ve geometrileri WKB'ye dönüştürmeyi öğrenin.
keywords:
- create linestring geometry .net
- WKB variant Aspose GIS
- EWKB conversion .NET
linktitle: Çeviride WKB Varyantını Belirtin
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  headline: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  name: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  steps:
  - name: Creating a Geometry Object
    text: The `Geometry` class is Aspose.GIS's base type that represents any spatial
      object in memory. Linestring represents a series of connected points forming
      a linear geometry. In this step we instantiate a `Linestring` with a collection
      of coordinate pairs that model a simple road segment.
  - name: Generating WKB Representation
    text: '`WkbVariant.ExtendedPostGis` is the enum value that tells Aspose.GIS to
      include SRID in the output binary. Here we call the `AsBinary` method, passing
      the EWKB variant, which returns a `byte[]` containing the full binary representation.'
  - name: Writing to File
    text: '`File.WriteAllBytes` writes the binary array to disk. The resulting file
      (`EWkbFile.ewkb`) can be imported directly into a PostGIS table using the `ST_GeomFromEWKB`
      function.'
  type: HowTo
- questions:
  - answer: Yes, the `ExtendedPostGis` variant produces EWKB that includes SRID, which
      PostGIS reads directly via `ST_GeomFromEWKB`.
    question: Can I use the EWKB file with PostGIS?
  - answer: Absolutely. Use `Geometry.FromBinary(byteArray)` to reconstruct the geometry
      from its binary form.
    question: Is it possible to read a WKB file back into a geometry object?
  - answer: Yes, Aspose.GIS handles points, linestrings, polygons, multipolygons,
      and many more spatial types.
    question: Does the library support other geometry types like polygons?
  - answer: Set the `SRID` property on the geometry object before calling `AsBinary`,
      e.g., `linestring.SRID = 4326;`.
    question: How do I specify a different SRID when creating the geometry?
  - answer: Yes, the same API works across .NET Framework, .NET Core, and .NET 5/6
      without modification.
    question: Will this code work on .NET Core?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET'te Linestring Geometrisi ve WKB Varyantı Oluşturma
url: /tr/net/geometry-processing/specify-wkb-variant-on-translation/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET ile Satır Geometrisi ve WKB Varyantı Oluşturma

## Giriş
Eğer **linestring geometry .NET** oluşturmanız ve ardından bu geometrinin ikili bir forma dönüştürülmesi gerekiyorsa, Aspose.GIS for .NET .NET Framework, .NET Core ve .NET 5/6+ üzerinde çalışan temiz, yüksek‑performanslı bir API sunar. Bu öğreticide, ad alanlarını içe aktarmaktan EWKB dosyası yazmaya kadar her adımı adım adım göstereceğiz; böylece SRID bilgisini koruyabilir ve GIS verilerini PostgreSQL/PostGIS ya da herhangi bir ikili‑temelli iş akışına sorunsuz bir şekilde entegre edebilirsiniz.

## Hızlı Yanıtlar
- **WKB ne anlama gelir?** Well‑Known Binary, geometrik nesnelerin kompakt ikili temsili.  
- **Hangi WKB varyantı SRID'yi depolar?** `ExtendedPostGis` (EWKB) varyantı SRID'yi doğrudan ikili içinde gömer.  
- **Lisans gerekli mi?** Üretim dağıtımları için geçici veya tam bir Aspose.GIS lisansı gereklidir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+ ve .NET 5/6+.  
- **Uygulama ne kadar sürer?** Temel bir örnek için genellikle 10 dakikadan az.

## Linestring Geometrisi Nedir?
Linestring geometrisi, sıralı bir nokta listesiyle oluşturulan ve düz çizgi segmentleriyle birbirine bağlanan basit bir şekildir. Uzay veritabanlarında yollar, boru hatları veya nehir yolları gibi doğrusal özelliklerin temsilinde tercih edilen bir formattır.

## Neden WKB Varyantı Belirtilir?
Doğru WKB varyantını kullanmak, kritik meta verilerin—özellikle Uzamsal Referans Sistemi Tanımlayıcısı (SRID)—geometriyle birlikte taşınmasını garanti eder. `ExtendedPostGis` (EWKB) varyantı SRID'yi ikili yük içinde saklar ve PostGIS, Oracle Spatial veya SRID‑bilgili ikili bekleyen herhangi bir sistemle sorunsuz bir geri‑dönüş sağlar.

## Ön Koşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

### Aspose.GIS for .NET Kurulumu
1. Aspose.GIS'i indirin: En son paketi edinmek için [indirme bağlantısını](https://releases.aspose.com/gis/net/) ziyaret edin.  
2. NuGet paketini projenize ekleyin (ör. `Install-Package Aspose.GIS`).  

### C# Programlamaya Hakimiyet
- C# sözdizimi ve proje yapısına temel bir anlayış.  
- .NET konsol veya sınıf‑kütüphane projesi çalıştırabilme yeteneği.

## Ad Alanlarını (Namespaces) İçe Aktarma
`Aspose.GIS` ad alanı, tüm geometry‑ile ilgili sınıflara erişim sağlar.  

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Bu ad alanları, geometry oluşturma, dönüşüm ve ikili serileştirme dahil olmak üzere temel GIS işlevselliğini sağlar.

## Linestring Geometrisi Nasıl Oluşturulur?
Bir linestring oluşturmak için, koordinat çiftlerinden oluşan sıralı bir listeyle bir `Linestring` nesnesi örnekleyin, gerekirse SRID'sini ayarlayın ve ardından istediğiniz WKB varyantına serileştirin. İşlem üç adımdan oluşur: geometry oluşturma, SRID'yi korumak için `ExtendedPostGis` varyantını seçme ve ortaya çıkan bayt dizisini bir dosyaya yazma.

### Adım 1: Geometry Nesnesi Oluşturma
`Geometry` sınıfı, Aspose.GIS'in bellek içindeki herhangi bir uzamsal nesneyi temsil eden temel tipidir.  
Linestring, doğrusal bir geometry oluşturan bağlanmış noktalar serisini temsil eder.  

```csharp
IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
```
Bu adımda, basit bir yol segmentini modelleyen koordinat çiftlerinden oluşan bir koleksiyonla bir `Linestring` örnekliyoruz.

### Adım 2: WKB Temsili Oluşturma
`WkbVariant.ExtendedPostGis` enum değeri, Aspose.GIS'e çıktıda SRID'yi dahil etmesini söyler.  

```csharp
byte[] wkb = geometry.AsBinary(WkbVariant.ExtendedPostGis);
```
Burada `AsBinary` metodunu çağırarak EWKB varyantını geçiriyoruz; bu, tam ikili temsili içeren bir `byte[]` döndürür.

### Adım 3: Dosyaya Yazma
`File.WriteAllBytes` ikili diziyi diske yazar.  

```csharp
File.WriteAllBytes(Path.Combine("Your Document Directory", "EWkbFile.ewkb"), wkb);
```
Ortaya çıkan dosya (`EWkbFile.ewkb`), `ST_GeomFromEWKB` fonksiyonu kullanılarak doğrudan bir PostGIS tablosuna içe aktarılabilir.

## Yaygın Sorunlar ve Çözümler
| Sorun | Neden | Çözüm |
|-------|--------|----------|
| **Boş dosya** | `Path.Combine` var olmayan bir dizine işaret ediyor. | Hedef dizinin var olduğundan emin olun veya `Directory.CreateDirectory` ile oluşturun. |
| **Yanlış SRID** | Varsayılan `WkbVariant.Standard` kullanılması SRID'yi atar. | SRID korunması gerektiğinde her zaman `WkbVariant.ExtendedPostGis` kullanın. |
| **Lisans istisnası** | Üretimde geçerli bir lisans olmadan çalıştırmak. | Üretim ortamında kodu çalıştırmadan önce geçici veya tam bir lisans uygulayın. |

## Sık Sorulan Sorular
**S: EWKB dosyasını PostGIS ile kullanabilir miyim?**  
C: Evet, `ExtendedPostGis` varyantı SRID'yi içeren bir EWKB üretir; PostGIS bunu `ST_GeomFromEWKB` aracılığıyla doğrudan okur.  

**S: WKB dosyasını tekrar bir geometry nesnesine okuyabilir miyim?**  
C: Kesinlikle. Geometry'yi ikili formundan yeniden oluşturmak için `Geometry.FromBinary(byteArray)` kullanın.  

**S: Kütüphane poligon gibi diğer geometry tiplerini destekliyor mu?**  
C: Evet, Aspose.GIS nokta, linestring, poligon, multipolygon ve daha birçok uzamsal tipi işler.  

**S: Geometry oluştururken farklı bir SRID nasıl belirlenir?**  
C: `AsBinary` çağırmadan önce geometry nesnesinin `SRID` özelliğini ayarlayın, ör. `linestring.SRID = 4326;`.  

**S: Bu kod .NET Core üzerinde çalışır mı?**  
C: Evet, aynı API .NET Framework, .NET Core ve .NET 5/6 üzerinde değişiklik yapmadan çalışır.

---

**Son Güncelleme:** 2026-06-10  
**Test Edilen Sürüm:** Aspose.GIS for .NET 23.9 (yazım anındaki en son sürüm)  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Eğitimler

- [Aspose.GIS for .NET ile Geometriyi WKB Formatına Dönüştürme](/gis/net/geometry-processing/translate-geometry-to-wkb/)
- [Aspose.GIS kullanarak Çeviride WKT Varyantı Belirtme](/gis/net/geometry-processing/specify-wkt-variant-on-translation/)
- [Aspose.GIS for .NET ile MultiLineString Geometrisi Oluşturma](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}