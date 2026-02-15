---
date: 2026-02-15
description: Aspose.GIS kullanarak .NET’te eğrileri eklemeyi ve bileşik eğri geometrileri
  oluşturmayı öğrenin; sorunsuz coğrafi veri işleme için.
linktitle: How to Add Curves – Compound Curve Geometry
second_title: Aspose.GIS .NET API
title: Eğrileri Nasıl Eklenir - Aspose.GIS ile Bileşik Eğri Geometrisi
url: /tr/net/geometry-creation/create-compound-curve-geometry/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Eğrileri Ekleme: Aspose.GIS ile Bileşik Eğri Geometrisi

## Giriş
.NET geliştirme dünyasında, Aspose.GIS ile **eğrileri nasıl ekleyeceğinizi** öğrenmek, gelişmiş coğrafi bilgi sistemleri uygulamaları oluşturmak için çok önemlidir. İster etkileşimli haritalar oluşturuyor, ister mekânsal analizler yapıyor ya da karmaşık GIS veri setleri üretiyor olun, Aspose.GIS gelişmiş geometrilerle hızlı ve güvenilir bir şekilde çalışmanız için gereken araçları sunar. Bu kılavuz, **eğrileri nasıl ekleyeceğinizi** ve bunları tek bir yeniden kullanılabilir bileşik eğri geometrisi içinde birleştirmenizi adım adım gösterir.

## Hızlı Yanıtlar
- **Ana hedef nedir?** Shapefile içinde eğrileri eklemek ve bir bileşik eğri geometrisi oluşturmak.  
- **Hangi kütüphane kullanılıyor?** Aspose.GIS for .NET.  
- **Önkoşullar?** Visual Studio, Aspose.GIS yüklü ve temel bir C# projesi.  
- **Tipik uygulama süresi?** Çalışan bir örnek için yaklaşık 10‑15 dakika.  
- **Desteklenen çıktı formatı?** Shapefile (ancak aynı yaklaşım GeoJSON, KML vb. için de çalışır).

## Bileşik Eğri Nedir?
Bir **bileşik eğri**, birden fazla bağlı eğri bileşeninden (düz hat dizileri ve dairesel yaylar) oluşan tek bir geometridir ve daha karmaşık bir şekil oluşturmak üzere bir araya getirilir. Tek bir basit hat, yolların kıvrımları ya da nehir kıvrımları gibi istenen yolu doğru şekilde temsil edemediğinde bu yapı faydalıdır.

## Neden Aspose.GIS ile Eğri Eklemeliyiz?
- **Zengin geometri API’si:** Çizgi dizileri, dairesel diziler ve bileşik eğrileri kutudan çıkar çıkmaz destekler.  
- **Çapraz platform:** .NET Framework, .NET Core ve .NET 5/6+ ile çalışır.  
- **Harici bağımlılık yok:** Yerel GIS kütüphanelerine ya da COM interop’a ihtiyaç duymaz.  
- **Kolay dışa aktarma:** Direkt olarak Shapefile, GeoJSON, KML ve birçok başka formata yazılabilir.

## Bunun Önemi Nedir?
Eğrileri eklemek, gerçek dünya özelliklerini daha doğru modellemenizi sağlar; bu da harita render’larında görsel kaliteyi artırır ve yakınlık aramaları ya da ağ rotalama gibi mekânsal analizlerde hassasiyeti yükseltir. **Eğrileri nasıl ekleyeceğinizi** öğrenerek, herhangi bir GIS‑odaklı .NET çözümünün doğruluğunu artırabilirsiniz.

## Yaygın Kullanım Senaryoları
- **Ulaşım ağları:** Yumuşak kıvrımlara sahip otoyollar, demiryolları veya bisiklet yolları modelleyin.  
- **Hidrolik:** Doğal yayları izleyen nehir hatlarını temsil edin.  
- **Şehir planlaması:** Eğri bölümler içeren arazi sınırlarını çizin.  
- **Özel semboller:** Harita lejandları için dekoratif veya şematik şekiller oluşturun.

## Önkoşullar
- **Visual Studio** çalışma ortamınıza kurulu olmalı.  
- **Aspose.GIS for .NET**, [indirme sayfasından](https://releases.aspose.com/gis/net/) temin edilmelidir.  
- .NET 6 (veya desteklenen başka bir sürüm) hedefleyen bir C# projesi.

## Ad Alanlarını İçe Aktarma
Aspose.GIS ile çalışmaya başlamak için C# dosyanızın en üst kısmına gerekli ad alanlarını ekleyin:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Bileşik Eğri Geometrisi Oluşturma Adım Adım Kılavuzu

### Adım 1: Çıktı Yolunu Tanımlama
İlk olarak, kütüphaneye sonucu nereye yazacağını söyleyin. Yer tutucuyu makinenizdeki gerçek bir klasörle değiştirin.

```csharp
string path = "Your Document Directory" + "CreateCompoundCurve_out.shp";
```

### Adım 2: Bir Vektör Katmanı Oluşturma
`VectorLayer`, mekânsal özellikler için bir konteyner görevi görür. Tüm geometri çalışmaları bu `using` bloğu içinde gerçekleşir ve kaynakların doğru şekilde serbest bırakılmasını da sağlar.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Code block for creating the compound curve geometry will be inserted here.
}
```

### Adım 3: Bileşik Eğri Özelliğini Oluşturma
Katman içinde yeni bir özellik ve bireysel eğri parçalarını tutacak boş bir `CompoundCurve` nesnesi oluştururuz.

```csharp
var feature = layer.ConstructFeature();
var compoundCurve = new CompoundCurve();
```

### Adım 4: Bileşen Eğrileri Tanımlama
Burada beş ayrı parça hazırlıyoruz—iki düz `LineString`, iki `CircularString` yay ve son bir `LineString`. Bu parçalar, tam bileşik eğriyi oluşturmak için birleştirilecek.

```csharp
var bottom = (ILineString)Geometry.FromText("LineString (0 0, 3 0)");
var firstArc = (ICircularString)Geometry.FromText("CircularString (3 0, 4 1, 3 2)");
var middle = (ILineString)Geometry.FromText("LineString (3 2, 1 2)");
var secondArc = (ICircularString)Geometry.FromText("CircularString (1 2, 0 3, 1 4)");
var top = (ILineString)Geometry.FromText("LineString (1 4, 4 4)");
```

### Adım 5: Bileşen Eğrileri Bileşik Eğriye Ekleme
Her bileşen sırasıyla eklenir, böylece geometri sürekli ve doğru yönlendirilmiş olur.

```csharp
compoundCurve.AddCurve(bottom);
compoundCurve.AddCurve(firstArc);
compoundCurve.AddCurve(middle);
compoundCurve.AddCurve(secondArc);
compoundCurve.AddCurve(top);
```

### Adım 6: Geometrinin Özelliğe Atanması
Şimdi birleştirilen `CompoundCurve`, saklayacağımız özelliğin geometrisi haline gelir.

```csharp
feature.Geometry = compoundCurve;
```

### Adım 7: Özelliği Katmana Ekleme
Son olarak, özelliği Shapefile’a yazarız. `using` bloğu sona erdiğinde dosya kapanır ve herhangi bir GIS uygulamasında kullanılmaya hazır hâle gelir.

```csharp
layer.Add(feature);
```

## Yaygın Sorunlar ve İpuçları
- **Koordinat sırası:** Aspose.GIS koordinatları `X Y` (boylam, enlem) sırasıyla bekler. Sıra karışırsa geometriler ters dönebilir.  
- **CircularString sözdizimi:** `CircularString`’in orta noktasının istenen yay üzerinde olduğundan emin olun; aksi takdirde eğri düzleşir.  
- **Dosya üzerine yazma:** Hedef Shapefile zaten varsa, `VectorLayer.Create` uyarı vermeden üzerine yazar—geliştirme sırasında benzersiz bir dosya adı kullanın.  
- **Performans:** Büyük veri setleri için, `using` bloğu içinde tek tek eklemek yerine toplu olarak özellik ekleyin.  
- **Pro ipucu:** Benzer birden çok özellik oluştururken aynı `CompoundCurve` nesnesini yeniden kullanın; yeniden doldurmadan önce `compoundCurve.Clear()` ile eğrileri temizleyin.

## Sıkça Sorulan Sorular

**S: Aspose.GIS for .NET’i diğer .NET framework’leriyle kullanabilir miyim?**  
C: Evet, Aspose.GIS for .NET .NET Framework, .NET Core ve .NET Standard ile çalışır.

**S: Aspose.GIS farklı coğrafi dosya formatlarını okuma ve yazma desteği sunuyor mu?**  
C: Kesinlikle! Shapefile, GeoJSON, KML, GML ve daha birçok formatı destekler.

**S: Aspose.GIS hem masaüstü hem de web uygulamaları için uygun mu?**  
C: Evet, kütüphane masaüstü, web ve bulut servislerinde kullanılabilir.

**S: Aspose.GIS for .NET ile mekânsal analiz yapabilir miyim?**  
C: Evet, mesafe hesaplamaları, geometrik işlemler ve mekânsal sorgular gerçekleştirebilirsiniz.

**S: Aspose.GIS topluluğundan nereden destek alabilirim?**  
C: Sorularınızı sormak ve fikirlerinizi paylaşmak için [Aspose.GIS forumunu](https://forum.aspose.com/c/gis/33) ziyaret edin.

---

**Son Güncelleme:** 2026-02-15  
**Test Edilen Versiyon:** Aspose.GIS for .NET (en son kararlı sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}