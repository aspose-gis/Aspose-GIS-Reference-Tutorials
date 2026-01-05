---
date: 2026-01-05
description: Dowiedz się, jak pobierać wartości atrybutów i ustawiać wartości domyślne
  w Aspose.GIS dla .NET. Ten przewodnik krok po kroku pokazuje, jak tworzyć warstwy
  GeoJSON i konstruować obiekty GIS.
linktitle: How to Get Attribute Value (Default)
second_title: Aspose.GIS .NET API
title: Jak pobrać wartość atrybutu (domyślną) przy użyciu Aspose.GIS dla .NET
url: /pl/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak pobrać wartość atrybutu (domyślną) przy użyciu Aspose.GIS dla .NET

## Wprowadzenie
W tym obszernym samouczku dowiesz się, **jak pobrać wartości atrybutów** z obiektu GIS przy użyciu Aspose.GIS dla .NET oraz jak pracować z wartościami domyślnymi, gdy atrybut jest nieobecny. Niezależnie od tego, czy tworzysz silnik analizy przestrzennej, czy prostą przeglądarkę map, opanowanie pobierania atrybutów i obsługi wartości domyślnych jest kluczowe dla niezawodnych aplikacji GIS.

## Szybkie odpowiedzi
- **Jaka jest podstawowa metoda?** `Feature.GetValueOrDefault<T>()`  
- **Czy mogę ustawić własną wartość domyślną?** Tak, poprzez przeciążenie przyjmujące wartość domyślną lub definiując `DefaultValue` dla atrybutu.  
- **Czy potrzebna jest licencja do rozwoju?** Bezpłatna wersja próbna wystarczy do testów; licencja komercyjna jest wymagana w produkcji.  
- **Obsługiwane formaty geometrii?** GeoJSON, Shapefile, GML i wiele innych dzięki sterownikom Aspose.GIS.  
- **Działa z .NET Core/.NET 6+?** Absolutnie – biblioteka jest wieloplatformowa.

## Wymagania wstępne
Zanim przejdziemy dalej, upewnij się, że masz:

- Podstawową znajomość C# i ekosystemu .NET.  
- Zainstalowane Aspose.GIS dla .NET. Jeśli jeszcze tego nie zrobiłeś, pobierz je [tutaj](https://releases.aspose.com/gis/net/).  
- Edytor kodu, taki jak Visual Studio lub Visual Studio Code.

## Importowanie przestrzeni nazw
Dodaj wymagane dyrektywy `using` do swojego pliku C#, aby typy API były dostępne:

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Teraz przejdźmy krok po kroku przez każdy przykład.

## Jak pobrać wartość atrybutu (domyślną)
### Krok 1: Przygotowanie środowiska
Zdefiniuj ścieżkę do folderu zawierającego Twoje dokumenty testowe:

```csharp
string dataDir = "Your Document Directory";
```

### Krok 2: Utworzenie warstwy GeoJSON
**Utworzymy warstwę GeoJSON** — pierwsze miejsce, w którym definiujemy atrybut, który może być pusty lub nieustawiony:

```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```

### Krok 3: Konstrukcja obiektu GIS
Teraz **tworzymy obiekt GIS** — daje nam to nową instancję obiektu, która respektuje schemat atrybutów, który właśnie zdefiniowaliśmy:

```csharp
    Feature feature = layer.ConstructFeature();
```

### Krok 4: Pobieranie wartości
Na koniec **pobieramy wartości atrybutów** obiektu przy użyciu kilku scenariuszy, demonstrując działanie wartości domyślnych:

```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // value == null
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // value == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // value == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```

## Jak ustawić wartości domyślne
### Krok 1: Utworzenie kolejnej warstwy GeoJSON
Tym razem **ustawimy domyślną wartość atrybutu** bezpośrednio w schemacie:

```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```

### Krok 2: Konstrukcja obiektu GIS (ponownie)
```csharp
    Feature feature = layer.ConstructFeature();
```

### Krok 3: Pobieranie i ustawianie wartości
Pobieramy wartość domyślną, a następnie zmieniamy ją, aby zobaczyć efekt **ustawiania domyślnej wartości** w czasie działania:

```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); // value == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); // value == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); // value == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```

## Typowe pułapki i wskazówki
- **Nigdy nie zapominaj zamknąć bloku `using`.** Warstwa jest automatycznie zwalniana, co zwalnia uchwyty plików.  
- **Gdy `CanBeNull` jest false, `GetValueOrDefault` zawsze zwróci wartość** (przechowywaną lub zdefiniowaną domyślną).  
- **Używaj przeciążenia generycznego** (`GetValueOrDefault<T>`) aby uniknąć boxing/unboxing dla typów wartościowych.  
- **Pro tip:** Jeśli potrzebujesz sprawdzić, czy atrybut jest faktycznie ustawiony, użyj `feature.IsAttributeSet("attribute")` przed wywołaniem `GetValueOrDefault`.

## Najczęściej zadawane pytania
### Czy Aspose.GIS jest kompatybilny z .NET Core?
Tak, Aspose.GIS jest w pełni kompatybilny z .NET Core, zapewniając wsparcie wieloplatformowe.

### Czy mogę używać Aspose.GIS w projektach komercyjnych?
Oczywiście! Aspose.GIS posiada licencję komercyjną, która pozwala na używanie jej w aplikacjach komercyjnych bez żadnych ograniczeń.

### Gdzie mogę znaleźć dodatkowe wsparcie i zasoby?
Odwiedź [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) w celu uzyskania pomocy społeczności oraz zapoznaj się z [dokumentacją](https://reference.aspose.com/gis/net/) dla szczegółowych informacji.

### Czy dostępna jest bezpłatna wersja próbna?
Tak, możesz wypróbować Aspose.GIS w wersji próbnej. Pobierz ją [tutaj](https://releases.aspose.com/).

### Jak uzyskać tymczasową licencję do testów?
W celu uzyskania tymczasowej licencji, przejdź [tutaj](https://purchase.aspose.com/temporary-license/).

## Dodatkowe FAQ
**P: Co się stanie, jeśli wywołam `GetValueOrDefault` na atrybucie, który nie istnieje?**  
O: Metoda rzuca `ArgumentException`. Zawsze weryfikuj nazwę atrybutu lub najpierw użyj `feature.HasAttribute("name")`.

**P: Czy mogę zmienić wartość domyślną po utworzeniu warstwy?**  
O: Tak, możesz zmodyfikować `attribute.DefaultValue`, a następnie wywołać `layer.UpdateAttribute(attribute)`, aby zmiana została zapisana.

**P: Czy Aspose.GIS obsługuje masowe aktualizacje wartości atrybutów?**  
O: Możesz iterować po kolekcji obiektów i wywoływać `SetValue` dla każdego z nich; przy dużych zestawach danych rozważ użycie API `FeatureCursor` dla lepszej wydajności.

## Podsumowanie
W tym przewodniku omówiliśmy **jak pobrać wartości atrybutów**, jak definiować i nadpisywać wartości domyślne oraz jak **tworzyć schematy warstw GeoJSON** dopasowane do potrzeb Twojej aplikacji. Dzięki tym technikom możesz budować solidne rozwiązania GIS, które elegancko radzą sobie z brakującymi lub opcjonalnymi danymi.

---

**Ostatnia aktualizacja:** 2026-01-05  
**Testowano z:** Aspose.GIS 24.11 dla .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}