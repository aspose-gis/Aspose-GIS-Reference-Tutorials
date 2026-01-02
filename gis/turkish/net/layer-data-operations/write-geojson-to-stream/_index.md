---
date: 2026-01-02
description: C#'ta Aspose.GIS for .NET kullanarak GeoJSON'u bir akıma nasıl yazacağınızı
  öğrenin. GeoJSON C# örneklerini görüntüleyin ve coğrafi bilgi uygulamalarınızı güçlendirin.
linktitle: Write GeoJSON to Stream
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET ile GeoJSON'u Akıma Yazma
url: /tr/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GeoJSON'u Akışa Nasıl Yazılır

## Giriş
Eğer bir .NET uygulamasında **how to write geojson**'ı doğrudan bir bellek veya dosya akışına yazmanız gerekiyorsa, doğru yerdesiniz. Bu öğreticide Aspose.GIS for .NET kütüphanesini kullanarak GeoJSON'u bir akışa yazmanın tam adımlarını göstereceğiz ve ayrıca **display GeoJSON C#** çıktısını konsolda nasıl göstereceğinizi göstereceğiz. Sonunda, herhangi bir coğrafi uzamsal projeye ekleyebileceğiniz yeniden kullanılabilir bir desen elde edeceksiniz.

## Hızlı Cevaplar
- **“write GeoJSON to stream” ne anlama geliyor?** Bu, bir vektör katmanını GeoJSON formatına serileştirip baytları bir `Stream` nesnesine (ör. `MemoryStream`) göndermek anlamına gelir.  
- **Hangi kütüphane bunu yönetir?** Aspose.GIS for .NET yerleşik bir GeoJSON sürücüsü sağlar.  
- **Geliştirme için lisansa ihtiyacım var mı?** Ücretsiz deneme geliştirme için çalışır; üretim için ticari lisans gereklidir.  
- **Bunu Linux'ta çalıştırabilir miyim?** Evet – Aspose.GIS çapraz‑platformdur ve Windows, Linux ve macOS'ta çalışır.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## .NET'te “how to write geojson” nedir?
Aspose.GIS, bir `VectorLayer` oluşturmanıza, özellik eklemenize ve ardından katmanı `Drivers.GeoJson` sürücüsüyle serileştirmenize olanak tanır. Sürücü, GeoJSON metnini doğrudan herhangi bir `Stream` içine yazar; böylece verinin nereye gideceği (bellek, dosya, ağ vb.) üzerinde tam kontrol sahibi olursunuz.

## Bu görev için Aspose.GIS'i neden kullanmalısınız?
- **Zero‑dependency serialization** – harici JSON kütüphaneleri gerekmez.  
- **Full GeoJSON spec compliance** – FeatureCollection, özellikler ve koordinat hassasiyetini destekler.  
- **Cross‑platform** – Windows, Linux ve macOS'ta aynı şekilde çalışır.  
- **Performance‑optimized** – ara stringler olmadan doğrudan akışa yazar.

## Önkoşullar
1. **Aspose.GIS for .NET** – bunu [buradan](https://releases.aspose.com/gis/net/) indirin.  
2. **Document directory** – geçici dosyaları veya çıktı akışlarını nerede tutmak istediğinize karar verin.

Şimdi, koda dalalım.

## Ad Alanlarını İçe Aktarın
İlk olarak, Aspose.GIS sınıflarına ve standart .NET I/O yardımcı programlarına erişmenizi sağlayan ad alanlarını ekleyin:

```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Adım 1: Belge Dizinini Ayarlayın
Gerekebileceğiniz geçici dosyaları barındıracak klasörü tanımlayın.

```csharp
string dataDir = "Your Document Directory";
```

Makinenizdeki gerçek yol ile `"Your Document Directory"` ifadesini değiştirin.

## Adım 2: Memory Stream Oluşturun
Bir `MemoryStream`, GeoJSON'u bellekte tutmanıza olanak tanır; bu, API'ler için veya veriyi doğrudan bir istemciye döndürmek istediğinizde mükemmeldir.

```csharp
using (var memoryStream = new MemoryStream())
{
    // Subsequent steps will be placed inside this block
}
```

## Adım 3: GeoJSON Sürücüsüyle Bir Vector Layer Oluşturun
Memory‑stream bloğu içinde, GeoJSON sürücüsünü kullanan bir `VectorLayer` oluşturun. Bu, Aspose.GIS'e katmanı GeoJSON olarak serileştirmesini söyler.

```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Feature creation goes here
}
```

## Adım 4: Özellik Niteliklerini Tanımlayın
Son GeoJSON çıktısında özellik olarak görünecek nitelik tanımlamaları ekleyin.

```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## Adım 5: Özellikleri Oluşturun ve Ekleyin
İki örnek nokta oluşturun, nitelik değerlerini atayın ve katmana ekleyin.

```csharp
// First Feature
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);

// Second Feature
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```

## Adım 6: GeoJSON C# Çıktısını Görüntüleyin
Katman doldurulduktan sonra, akışın baytlarını UTF‑8 bir dizeye dönüştürün ve konsola yazdırın. Bu, **display GeoJSON C#** sonuçlarını nasıl göstereceğinizi demonstrasyon eder.

```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

Geçerli bir GeoJSON FeatureCollection'ın terminale yazdırıldığını görmelisiniz.

## Yaygın Sorunlar ve Çözümler
| Sorun | Neden Oluşur | Çözüm |
|-------|----------------|-----|
| Boş çıktı | Okuma sırasında akış konumu sonundadır | Dizeye dönüştürmeden önce `memoryStream.Position = 0;` çağırın. |
| Geçersiz geometri | Koordinatlar geçerli aralıkların dışındadır | Enlemin -90 ile 90 arasında, boylamın -180 ile 180 arasında olduğundan emin olun. |
| Lisans istisnası | Üretimde geçerli bir lisans olmadan çalıştırılıyor | Geçici veya tam lisansı şu şekilde uygulayın: `License license = new License(); license.SetLicense("Aspose.GIS.lic");` |

## Sık Sorulan Sorular
### Aspose.GIS for .NET'i hem Windows hem de Linux ortamlarında kullanabilir miyim?
Evet, Aspose.GIS for .NET hem Windows hem de Linux sistemleriyle uyumludur.  

### Ücretsiz deneme sürümü mevcut mu?
Kesinlikle! Ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) keşfedebilirsiniz.  

### Detaylı belgeleri nerede bulabilirim?
Belgelere [buradan](https://reference.aspose.com/gis/net/) göz atın.  

### Geçici lisans nasıl alabilirim?
Geçici lisanslar [buradan](https://purchase.aspose.com/temporary-license/) temin edilebilir.  

### Yardıma mı ihtiyacınız var ya da daha fazla sorunuz mu var?
Destek forumumuzu [buradan](https://forum.aspose.com/c/gis/33) ziyaret edin.

## SSS
**S: MemoryStream yerine doğrudan bir dosyaya GeoJSON yazabilir miyim?**  
C: Evet—`MemoryStream` yerine `FileStream` kullanın ve bir dosya yolu sağlayın. Aynı sürücü çalışır.

**S: Oluşturulan GeoJSON'un girinti veya biçimlendirmesini nasıl kontrol ederim?**  
C: Aspose.GIS varsayılan olarak sıkıştırılmış JSON yazar. Güzel biçimlendirilmiş çıktı için dizeyi `JsonSerializerOptions { WriteIndented = true }` ile sonradan işleyin.

**S: Katmana daha karmaşık geometriler (ör. poligonlar) eklemek mümkün mü?**  
C: Kesinlikle. Bir `Polygon` veya `LineString` nesnesi oluşturun, `Feature.Geometry`'ye atayın ve yukarıda gösterildiği gibi özelliği ekleyin.

**S: Büyük veri setleri bir `MemoryStream` içine sığar mı?**  
C: Çok büyük koleksiyonlar için doğrudan bir dosyaya akış yapmayı veya yüksek bellek tüketimini önlemek amacıyla `BufferedStream` kullanmayı düşünün.

**S: GeoJSON sürücüsü CRS (Koordinat Referans Sistemi) tanımlarını destekliyor mu?**  
C: Evet—gerektiğinde WGS84 dışı bir CRS için özellik eklemeden önce katmanın `SpatialReferenceSystem` özelliğini ayarlayın.

## Sonuç
Artık Aspose.GIS kullanarak **how to write geojson**'ı herhangi bir .NET akışına yazmak için eksiksiz, üretime hazır bir deseniniz var. Web API'den GeoJSON döndürmeniz, bir dosyaya kaydetmeniz veya sadece konsolda görüntülemeniz gerektiğinde, yukarıdaki adımlar tüm iş akışını kapsar. Kütüphaneyi Shapefile, KML veya GML gibi diğer formatlarla çalışmak için keşfedin ve daha zengin coğrafi uzamsal uygulamalar geliştirmeye devam edin.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-02  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

---