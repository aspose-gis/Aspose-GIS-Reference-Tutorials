---
date: 2025-12-20
description: Dowiedz się, jak ograniczyć precyzję przy zapisywaniu geometrii przy
  użyciu Aspose.GIS dla .NET. Ten przewodnik krok po kroku pomaga zarządzać danymi
  przestrzennymi z dokładną kontrolą współrzędnych.
linktitle: Limit Precision Writing Geometries
second_title: Aspose.GIS .NET API
title: Jak ograniczyć precyzję przy zapisywaniu geometrii w Aspose.GIS
url: /pl/net/geometry-processing/limit-precision-writing-geometries/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak ograniczyć precyzję przy zapisywaniu geometrii przy użyciu Aspose.GIS

Jeśli zastanawiasz się **jak ograniczyć precyzję** przy zapisywaniu geometrii w aplikacji .NET GIS, Aspose.GIS dla .NET oferuje prosty, wysokowydajny sposób kontrolowania zaokrąglania współrzędnych. W tym samouczku przeprowadzimy Cię przez cały proces — od przygotowania środowiska po weryfikację, że wynikowy plik spełnia zdefiniowane reguły precyzji.

## Szybkie odpowiedzi
- **Co oznacza „ograniczyć precyzję”?** Zaokrągla wartości współrzędnych do określonej liczby cyfr po przecinku podczas zapisywania pliku przestrzennego.  
- **Jakiego formatu użyto w przykładzie?** GeoJSON, ale te same opcje mają zastosowanie do innych obsługiwanych formatów.  
- **Czy potrzebna jest licencja, aby wypróbować to rozwiązanie?** Darmowa wersja próbna działa w celach rozwojowych i testowych; licencja komercyjna jest wymagana w środowisku produkcyjnym.  
- **Jakie wersje .NET są wspierane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Czy mogę kontrolować precyzję współrzędnej Z osobno?** Tak — użyj `ZPrecisionModel`, aby ustawić dokładne lub zaokrąglone wartości.

## Jak ograniczyć precyzję przy zapisywaniu geometrii
Ograniczanie precyzji jest niezbędne, gdy potrzebujesz spójnej reprezentacji współrzędnych w różnych narzędziach GIS, chcesz zmniejszyć rozmiar pliku lub spełnić standardy wymiany danych. Poniżej zdefiniujemy opcje precyzji, zapiszemy geometrię, a następnie odczytamy ją, aby potwierdzić zaokrąglenie.

## Wymagania wstępne

### 1. Pobranie i instalacja
Pobierz najnowszy pakiet Aspose.GIS dla .NET z oficjalnej strony: [download link](https://releases.aspose.com/gis/net/). Postępuj zgodnie z przewodnikiem instalacji, aby dodać pakiet NuGet do swojego projektu.

### 2. Import przestrzeni nazw
Dodaj wymagane przestrzenie nazw, aby uzyskać dostęp do klas GIS i pomocniczych narzędzi.

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Przewodnik krok po kroku

### Krok 1: Zdefiniuj opcje precyzji
Utwórz instancję `GeoJsonOptions` i określ, ile cyfr po przecinku ma być zachowanych dla współrzędnych X/Y oraz Z.

```csharp
var options = new GeoJsonOptions
{
    // Limit X and Y coordinates to 3 fractional digits.
    XYPrecisionModel = PrecisionModel.Rounding(3),

    // Write all fractional digits of the Z coordinate.
    ZPrecisionModel = PrecisionModel.Exact
};
```

### Krok 2: Ustaw ścieżkę wyjściową
Określ, gdzie zostanie zapisany wynikowy plik GeoJSON.

```csharp
var path = "Your Document Directory" + "LimitPrecisionWhenWritingGeometries_out.json";
```

### Krok 3: Utwórz i wypełnij geometrię
Otwórz nową `VectorLayer` z wcześniej zdefiniowanymi opcjami, skonstruuj geometrię `Point` i dodaj ją do warstwy.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    var point = new Point();
    point.X = 1.8888888;
    point.Y = 1.00123;
    point.Z = 1.123456789;

    Feature feature = layer.ConstructFeature();
    feature.Geometry = point;
    layer.Add(feature);
}
```

### Krok 4: Odczytaj i zweryfikuj precyzję
Otwórz właśnie utworzony plik i wypisz współrzędne. Powinieneś zobaczyć wartości X/Y zaokrąglone do trzech miejsc po przecinku, podczas gdy wartość Z pozostaje dokładna.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.GeoJson))
{
    var point = (IPoint)layer[0].Geometry;

    // Output: 1.889, 1.001, 1.123456789
    Console.WriteLine("{0}, {1}, {2}", point.X, point.Y, point.Z);
}
```

## Typowe problemy i wskazówki

- **Błędy ścieżki:** Upewnij się, że katalog w `path` istnieje lub użyj `Path.Combine` wraz z `Environment.CurrentDirectory`, aby zbudować bezpieczną ścieżkę pliku.  
- **Precyzja nie została zastosowana:** Sprawdź, czy przekazujesz obiekt `GeoJsonOptions` podczas tworzenia warstwy; w przeciwnym razie używana jest domyślna precyzja (pełny podwójny).  
- **Duże zestawy danych:** W przypadku operacji masowych rozważ ponowne użycie jednej instancji `VectorLayer` i dodawanie funkcji partiami, aby zwiększyć wydajność.

## Najczęściej zadawane pytania

**P: Czy Aspose.GIS dla .NET jest kompatybilny z innymi formatami GIS?**  
O: Tak, obsługuje Shapefile, GeoJSON, KML, GML i wiele innych, umożliwiając płynną konwersję między formatami.

**P: Czy mogę wypróbować Aspose.GIS dla .NET przed zakupem?**  
O: Oczywiście. Darmowa wersja próbna jest dostępna na stronie pobierania, dając pełny dostęp do wszystkich funkcji w celach oceny.

**P: Jak uzyskać tymczasową licencję do testów?**  
O: Tymczasowe licencje ewaluacyjne można wygenerować w portalu licencyjnym Aspose; są ważne przez 30 dni.

**P: Gdzie mogę uzyskać pomoc w razie problemów?**  
O: Forum Aspose.GIS oraz tag na Stack Overflow `aspose-gis` to świetne miejsca, aby zadawać pytania i znajdować rozwiązania od społeczności.

**P: Czy biblioteka sprawdzi się zarówno w małych skryptach, jak i w aplikacjach o skali przedsiębiorstwa?**  
O: Tak, Aspose.GIS został zaprojektowany tak, aby obsługiwać wszystko — od szybkich prototypów po wysokowydajne aplikacje serwerowe.

## Zakończenie
Postępując zgodnie z powyższymi krokami, teraz wiesz **jak ograniczyć precyzję** przy zapisywaniu geometrii przy użyciu Aspose.GIS dla .NET. Kontrolowanie zaokrąglania współrzędnych pomaga utrzymać dane przestrzenne w czystości, zapewnia interoperacyjność i efektywność przechowywania — kluczowe korzyści dla każdego projektu skoncentrowanego na GIS.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ostatnia aktualizacja:** 2025-12-20  
**Testowano z:** Aspose.GIS 24.11 dla .NET  
**Autor:** Aspose