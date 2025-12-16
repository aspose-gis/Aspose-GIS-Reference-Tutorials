---
date: 2025-12-15
description: Aspose.GIS for .NET kullanarak eğri çokgen geometrisi oluşturmayı öğrenin.
  GIS uygulamalarınızda eğri çokgen şekillerini verimli bir şekilde oluşturmak için
  adım adım rehberimizi izleyin.
linktitle: Create Curve Polygon Geometry
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET ile Eğri Çokgen Geometrisi Oluşturma
url: /tr/net/geometry-creation/create-curve-polygon-geometry/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET ile Eğri Çokgen Geometrisi Oluşturma

## Giriş
Coğrafi Bilgi Sistemleri (GIS) geliştirme alanında **Aspose.GIS for .NET** güçlü bir kütüphane olarak öne çıkar; mekânsal verileri oluşturma, düzenleme ve manipüle etme imkanı sunar. Bu öğreticide, **eğri çokgen** geometrisini adım adım nasıl oluşturacağınızı öğrenecek ve böylece karmaşık şekilleri doğrudan GIS uygulamalarınıza yerleştirebileceksiniz. Kılavuzun sonunda, dış ve iç halkalara sahip bir eğri çokgen içeren, kullanıma hazır bir Shapefile elde edeceksiniz.

## Hızlı Yanıtlar
- **Hangi kütüphane kullanılıyor?** Aspose.GIS for .NET  
- **Ana görev?** Eğri çokgen geometrisini oluşturmak ve Shapefile olarak kaydetmek  
- **Tipik uygulama süresi?** Temel bir şekil için 5–10 dakika  
- **Önkoşullar?** .NET geliştirme ortamı ve Aspose.GIS NuGet paketi  
- **Sonucu görüntüleyebilir miyim?** Evet – Shapefile destekleyen herhangi bir GIS görüntüleyici (ör. QGIS, ArcGIS)

## Eğri Çokgen Nedir?
*Eğri çokgen*, kenarları yalnızca düz çizgiler yerine eğri segmentlerden (örneğin dairesel yaylar) oluşabilen bir çokgendir. Bu, göller, adalar gibi doğal özelliklerin veya pürüzsüz sınırların fayda sağladığı herhangi bir şeklin daha gerçekçi modellenmesini sağlar.

## Aspose.GIS ile eğri çokgen geometrisi neden oluşturulmalı?
- **Doğruluk** – Eğri kenarlar matematiksel olarak depolanır, tam geometri korunur.  
- **Uyumluluk** – Oluşturulan Shapefile tüm büyük GIS platformlarıyla çalışır.  
- **Verimlilik** – Karmaşık şekilleri tanımlamak için az kod gerekir, geliştirme döngüleri hızlanır.

## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. **Aspose.GIS for .NET** yüklü. Bunu [Aspose.GIS for .NET releases page](https://releases.aspose.com/gis/net/) adresinden indirin.  
2. C# ve .NET ekosistemi hakkında temel bilgi.  
3. Visual Studio (herhangi bir yeni sürüm) veya Visual Studio Code gibi bir IDE.

## Ad Alanlarını İçe Aktarma
Bu adımda, kodumuzda Aspose.GIS işlevlerini kullanmak için gerekli ad alanlarını içe aktaracağız.

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

`"Your Document Directory"` ifadesini, makinenizdeki gerçek klasör yolu ile değiştirin.

### Adım 2: Bir Vektör Katmanı Oluşturma
Shapefile sürücüsünü kullanarak yeni bir vektör katmanı örnekleyin.

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

### Adım 5: Dış Halkayı Tanımlama
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

### Adım 6: İç Halkayı Tanımlama (İsteğe Bağlı)
Poligon içinde bir delik ihtiyacınız varsa, bunu başka bir circular string olarak tanımlayın.

```csharp
var interior = new CircularString();
interior.AddPoint(-1, 0);
interior.AddPoint(0, 1);
interior.AddPoint(1, 0);
interior.AddPoint(0, -1);
interior.AddPoint(-1, 0);
curvePolygon.AddInteriorRing(interior);
```

### Adım 7: Geometriyi Feature'a Atama
Eğri çokgeni, daha önce oluşturduğunuz feature'a bağlayın.

```csharp
feature.Geometry = curvePolygon;
```

### Adım 8: Feature'ı Katmana Ekleme
Son olarak, feature'ı vektör katmanına ekleyin, böylece veri setinin bir parçası olur.

```csharp
layer.Add(feature);
```

`using` bloğu sona erdiğinde, Shapefile diske yazılır.

## Yaygın Sorunlar ve Çözümler
| Sorun | Neden Oluşur | Çözüm |
|-------|----------------|-----|
| **Dosya oluşturulmadı** | Yanlış yol veya yazma izinlerinin eksik olması | Dizinin mevcut olduğunu ve uygulamanın yazma erişimine sahip olduğunu doğrulayın. |
| **Eğri kenarlar bazı görüntüleyicilerde düz çizgi olarak görünür** | Görüntüleyici circular string'leri desteklemiyor | Shapefile spesifikasyonunu tam olarak destekleyen bir GIS uygulaması kullanın (ör. QGIS 3.28+). |
| **`AddPoint` üzerinde `ArgumentException` istisnası** | Noktalar seçilen CBS için geçerli koordinat aralığının dışındadır | Kullanmayı planladığınız koordinat referans sisteminin içinde koordinatların olduğundan emin olun. |

## Sıkça Sorulan Sorular

**Q: Aspose.GIS for .NET diğer GIS kütüphaneleriyle uyumlu mu?**  
A: Evet, Aspose.GIS for .NET birçok popüler GIS formatı ile uyumluluk sağlar, GDAL/OGR veya Proj.NET gibi kütüphanelerle veri alışverişi yapmanıza olanak tanır.

**Q: Oluşturulan Eğri Çokgen Geometrisini GIS yazılımında görselleştirebilir miyim?**  
A: Kesinlikle! Oluşturulan Shapefile, QGIS, ArcGIS veya Shapefile formatını okuyabilen herhangi bir GIS aracıyla açılabilir.

**Q: Aspose.GIS for .NET mekânsal analiz yetenekleri sunuyor mu?**  
A: Evet, mekânsal sorgulama, tamponlama, kesişim ve daha fazlası için fonksiyonlar içerir, bu da .NET içinde doğrudan gelişmiş analiz yapmanıza olanak tanır.

**Q: Diğer kullanıcılarla yardım isteyebileceğim veya fikir tartışabileceğim yer neresi?**  
A: Diğer geliştiricilerle bağlantı kurmak için Aspose.GIS topluluk forumuna [buradan](https://forum.aspose.com/c/gis/33) katılın.

**Q: Satın almadan önce ücretsiz deneme sürümü mevcut mu?**  
A: Elbette! [releases page](https://releases.aspose.com/) adresinden ücretsiz deneme sürümünü indirebilir ve tüm özellikleri değerlendirebilirsiniz.

## Sonuç
Artık Aspose.GIS for .NET kullanarak **eğri çokgen** geometrisini nasıl oluşturacağınızı, Shapefile olarak kaydedeceğinizi ve yaygın hatalar ile SSS'leri incelediğinizi öğrendiniz. Farklı koordinat setleriyle denemeler yapmaktan, öznitelik verileri eklemekten veya katmanı daha büyük GIS iş akışlarına entegre etmekten çekinmeyin.

---

**Son Güncelleme:** 2025-12-15  
**Test Edilen Versiyon:** Aspose.GIS for .NET 24.11  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}