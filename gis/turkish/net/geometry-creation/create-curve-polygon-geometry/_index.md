---
date: 2026-02-15
description: Aspose.GIS for .NET kullanarak vektör katmanı ve eğri çokgen geometrisi
  oluşturmayı, iç halkalar için dairesel dize geometrisini de içerecek şekilde öğrenin.
linktitle: Create Curve Polygon Geometry
second_title: Aspose.GIS .NET API
title: Aspose.GIS ile Vektör Katmanı ve Eğri Çokgen Oluşturma
url: /tr/net/geometry-creation/create-curve-polygon-geometry/
weight: 18
---

 translate code block placeholders.

Also ensure markdown formatting preserved.

Let's craft translation.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS ile vektör katmanı ve eğri çokgen oluşturma

## Giriş
Coğrafi Bilgi Sistemleri (GIS) geliştirme alanında, **Aspose.GIS for .NET** uzamsal verileri oluşturma, düzenleme ve manipüle etme konusunda güçlü bir kütüphane olarak öne çıkar. Bu öğreticide **vektör katmanı oluşturma** ve **eğri çokgen** geometrisini adım adım nasıl oluşturacağınızı öğrenecek ve bu şekilleri doğrudan GIS uygulamalarınıza entegre edebileceksiniz. Rehberin sonunda, dış ve iç halkalara sahip bir eğri çokgen içeren, kullanıma hazır bir Shapefile elde etmiş olacaksınız.

## Hızlı Yanıtlar
- **Hangi kütüphane kullanılıyor?** Aspose.GIS for .NET  
- **Ana görev?** Bir eğri çokgen geometrisi oluşturmak, Shapefile olarak kaydetmek ve veri için **vektör katmanı oluşturma**  
- **Tipik uygulama süresi?** Temel bir şekil için 5–10 dakika  
- **Önkoşullar?** .NET geliştirme ortamı ve Aspose.GIS NuGet paketi  
- **Sonucu görebilir miyim?** Evet – Shapefile (ör. QGIS, ArcGIS) destekleyen herhangi bir GIS görüntüleyici

## Eğri Çokgen Nedir?
*Eğri çokgen*, kenarlarının yalnızca düz çizgiler yerine eğimli segmentler (örneğin dairesel yaylar) içerebildiği bir çokgendir. Bu, göller, adalar veya yumuşak sınırların fayda sağladığı herhangi bir doğal özelliğin daha gerçekçi modellenmesini mümkün kılar.

## Neden Aspose.GIS ile eğri çokgen geometrisi oluşturmalısınız?
- **Precision** – Eğri kenarlar matematiksel olarak saklanır, tam geometri korunur.  
- **Interoperability** – Oluşturulan Shapefile tüm büyük GIS platformlarıyla çalışır.  
- **Productivity** – Karmaşık şekilleri tanımlamak için az kod gerekir, geliştirme döngüleri hızlanır.  
- **Flexibility** – İhtiyacınız olan herhangi bir geometriyi ekleyebileceğiniz **vektör katmanı oluşturma** nesnelerini anında yaratabilirsiniz.

## Önkoşullar
İlerlemeye başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. **Aspose.GIS for .NET** yüklü. [Aspose.GIS for .NET releases page](https://releases.aspose.com/gis/net/) adresinden indirin.  
2. C# ve .NET ekosistemi hakkında temel bilgi.  
3. Visual Studio (herhangi bir yeni sürüm) veya Visual Studio Code gibi bir IDE.

## İsim Uzaylarını İçe Aktarma
Bu adımda, kodumuzda Aspose.GIS işlevlerini kullanmak için gerekli isim uzaylarını içe aktaracağız.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Adım Adım Kılavuz

### Adım 1: Dosya Yolunu Tanımlama
İlk olarak, oluşturulan Eğri Çokgen Shapefile'ının nereye kaydedileceğini belirtin.

```csharp
string path = "Your Document Directory" + "CreateCurvePolygon_out.shp";
```

`"Your Document Directory"` ifadesini makinenizdeki gerçek klasör yolu ile değiştirin.

### Adım 2: Bir Vektör Katmanı Oluşturma
Shapefile sürücüsü kullanarak yeni bir vektör katmanı örnekleyin. Bu, geometrimiz için konteyneri hazırlayan **vektör katmanı oluşturma** adımıdır.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Your code for creating the Curve Polygon Geometry will go here
}
```

`using` ifadesi, kaynakların doğru bir şekilde serbest bırakılmasını garanti eder.

### Adım 3: Bir Özellik (Feature) Oluşturma
Geometriyi ve olası öznitelik verilerini tutacak bir feature nesnesi oluşturun.

```csharp
var feature = layer.ConstructFeature();
```

### Adım 4: Eğri Çokgen Geometrisi Oluşturma
Şimdi boş bir `CurvePolygon` nesnesi oluşturacağız.

```csharp
var curvePolygon = new CurvePolygon();
```

### Adım 5: Dış Halka Tanımlama
Poligonun dış sınırını oluşturan bir circular string ekleyin.

```csharp
var exterior = new CircularString();
exterior.AddPoint(-2, 0);
exterior.AddPoint(0, 2);
exterior.AddPoint(2, 0);
exterior.AddPoint(0, -2);
exterior.AddPoint(-2, 0);
curvePolygon.ExteriorRing = exterior;
```

Yukarıdaki koordinatlar torus benzeri bir şekil üretir.

### Adım 6: İç Halka Tanımlama (İsteğe Bağlı)
Poligon içinde bir delik ihtiyacınız varsa, bunu başka bir circular string olarak tanımlayın. Bu, **circular string geometry** kullanarak **interior ring polygon** eklemenin bir örneğidir.

```csharp
var interior = new CircularString();
interior.AddPoint(-1, 0);
interior.AddPoint(0, 1);
interior.AddPoint(1, 0);
interior.AddPoint(0, -1);
interior.AddPoint(-1, 0);
curvePolygon.AddInteriorRing(interior);
```

### Adım 7: Geometriyi Özelliğe Atama
Oluşturduğunuz eğri çokgeni, daha önce yarattığınız feature'a bağlayın.

```csharp
feature.Geometry = curvePolygon;
```

### Adım 8: Özelliği Katmana Ekleme
Son olarak, feature'ı vektör katmanına ekleyin; böylece veri setinin bir parçası olur.

```csharp
layer.Add(feature);
```

`using` bloğu sona erdiğinde, Shapefile diske yazılır.

## Yaygın Sorunlar ve Çözümler
| Sorun | Neden Oluşur | Çözüm |
|-------|--------------|------|
| **Dosya oluşturulmadı** | Yanlış yol veya yazma izinlerinin eksik olması | Klasörün var olduğunu ve uygulamanın yazma iznine sahip olduğunu doğrulayın. |
| **Eğri kenarlar bazı görüntüleyicilerde düz çizgi olarak görünür** | Görüntüleyici circular string'leri desteklemiyor | Shapefile spesifikasyonunu tam destekleyen bir GIS uygulaması kullanın (ör. QGIS 3.28+). |
| **`AddPoint` üzerinde `ArgumentException` istisnası** | Noktalar seçilen CRS için geçerli koordinat aralığının dışındadır | Koordinatların kullanmayı planladığınız koordinat referans sisteminin sınırları içinde olduğundan emin olun. |

## Sıkça Sorulan Sorular

**S: Aspose.GIS for .NET diğer GIS kütüphaneleriyle uyumlu mu?**  
C: Evet, Aspose.GIS for .NET birçok popüler GIS formatıyla birlikte çalışabilir ve GDAL/OGR veya Proj.NET gibi kütüphanelerle veri alışverişine olanak tanır.

**S: Oluşturulan Eğri Çokgen Geometrisini GIS yazılımında görselleştirebilir miyim?**  
C: Kesinlikle! Üretilen Shapefile QGIS, ArcGIS veya Shapefile formatını okuyabilen herhangi bir GIS aracıyla açılabilir.

**S: Aspose.GIS for .NET uzamsal analiz yetenekleri sunuyor mu?**  
C: Evet, uzamsal sorgulama, tamponlama, kesişim gibi fonksiyonları içerir; böylece .NET içinde gelişmiş analizler yapabilirsiniz.

**S: Diğer kullanıcılarla fikir alışverişi yapmak veya yardım almak için nereden ulaşabilirim?**  
C: Aspose.GIS topluluk forumuna **[buradan](https://forum.aspose.com/c/gis/33)** katılarak diğer geliştiricilerle iletişime geçebilirsiniz.

**S: Satın almadan önce ücretsiz deneme sürümü mevcut mu?**  
C: Tabii ki! Tüm özellikleri değerlendirebileceğiniz bir ücretsiz deneme sürümünü **[releases page](https://releases.aspose.com/)** adresinden indirebilirsiniz.

## Sonuç
Artık **vektör katmanı oluşturma** ve **eğri çokgen** geometrisini Aspose.GIS for .NET kullanarak nasıl oluşturacağınızı, Shapefile olarak kaydedeceğinizi ve yaygın hatalar ile SSS'leri öğrendiniz. Farklı koordinat setleriyle denemeler yapın, öznitelik verileri ekleyin veya katmanı daha büyük GIS iş akışlarına entegre edin.

---

**Last Updated:** 2026-02-15  
**Tested With:** Aspose.GIS for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}