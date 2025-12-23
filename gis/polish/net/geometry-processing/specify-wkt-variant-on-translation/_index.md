---
date: 2025-12-23
description: Dowiedz się, jak konwertować geometrię do formatu WKT z różnymi opcjami,
  ustawiać format liczbowy i regulować precyzję dziesiętną przy użyciu Aspose.GIS
  dla .NET.
linktitle: Convert Geometry to WKT
second_title: Aspose.GIS .NET API
title: Konwertuj geometrię na warianty WKT przy użyciu Aspose.GIS
url: /pl/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konwertowanie geometrii do wariantów WKT przy użyciu Aspose.GIS

## Wprowadzenie
W nowoczesnych aplikacjach .NET, **converting geometry to WKT** jest powszechnym krokiem, gdy trzeba wymieniać dane przestrzenne z innymi systemami lub przechowywać je w formacie tekstowym. Aspose.GIS dla .NET umożliwia tę konwersję bez wysiłku, zapewniając pełną kontrolę nad wariantem WKT, formatem liczbowym i precyzją dziesiętną. W tym samouczku dowiesz się, jak konwertować geometrię do WKT, wybrać odpowiedni wariant i precyzyjnie dostosować wynik do dokładnych wymagań projektu.

## Szybkie odpowiedzi
- **Co oznacza „convert geometry to WKT”?** Przekształca obiekty geometryczne (punkty, linie, wielokąty) do reprezentacji Well‑Known Text.  
- **Jakie warianty WKT są obsługiwane?** `Iso`, `SimpleFeatureAccessOutdated`, and `ExtendedPostGis`.  
- **Jak mogę kontrolować precyzję dziesiętną?** Use the `NumericFormat` options such as `General`, `RoundTrip`, or `Flat`.  
- **Czy potrzebna jest licencja do produkcji?** Yes, a commercial license is required for non‑trial use.  
- **Jakie wersje .NET są kompatybilne?** .NET Framework 4.0+ and .NET 5/6/7.

## Co to jest „convert geometry to WKT”?
Konwertowanie geometrii do WKT tworzy czytelny dla człowieka ciąg znaków opisujący obiekty przestrzenne. Ten format jest powszechnie akceptowany przez narzędzia GIS, bazy danych i usługi internetowe, co czyni go idealnym do wymiany danych.

## Dlaczego warto używać Aspose.GIS do tej konwersji?
- **Precision control** – Wybierz, ile miejsc dziesiętnych ma być wypisywanych.  
- **Variant flexibility** – Dopasuj dokładny dialekt WKT wymagany przez system docelowy.  
- **No external dependencies** – Czysta biblioteka .NET, bez natywnych binarek.

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz:

1. **Aspose.GIS for .NET** – Pobierz i zainstaluj go ze [strony pobierania](https://releases.aspose.com/gis/net/).  
2. **Development Environment** – Dowolna aktualna wersja Visual Studio lub VS Code z .NET SDK.  
3. **Basic C# knowledge** – Znajomość klas, obiektów i platformy .NET.

## Importowanie przestrzeni nazw
Najpierw wprowadź wymagane przestrzenie nazw do zasięgu:

```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```

## Krok 1: Utwórz obiekt Point
Utwórz `Point`, który później **convert geometry to WKT**. Punkt zawiera szerokość geograficzną, długość geograficzną oraz opcjonalną wartość miary (M):

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Krok 2: Ustaw System Referencji Przestrzennej (SRS)
Przypisz system referencji przestrzennej, aby wyjście WKT wiedziało, którego układu współrzędnych używać. Tutaj używamy powszechnego systemu WGS84:

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Krok 3: Określ wariant WKT
Wybierz odpowiedni wariant WKT podczas **convert geometry to WKT**. Każdy wariant formatuje wyjście nieco inaczej:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Krok 4: Kontrola formatu liczbowego (Ustaw format liczbowy i dostosuj precyzję dziesiętną)
Dostosuj reprezentację liczbową współrzędnych. Klasa `NumericFormat` pozwala **set numeric format** i **adjust decimal precision** zgodnie z potrzebami:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

## Typowe problemy i wskazówki
- **Missing M value** – Jeśli nie potrzebujesz miary, pomiń właściwość `M`; wariant ISO automatycznie ją usunie.  
- **Unexpected precision** – Sprawdź ponownie, czy używasz właściwego `NumericFormat`; `General` zachowuje pełną precyzję podwójną, natomiast `Flat` zaokrągla do określonej liczby miejsc dziesiętnych.  
- **SRID not displayed** – Tylko wariant `ExtendedPostGis` dodaje prefiks `SRID=` do wyniku. Wybierz ten wariant, gdy system docelowy oczekuje SRID.

## Podsumowanie
Postępując zgodnie z tymi krokami, teraz wiesz, jak **convert geometry to WKT**, wybrać odpowiedni wariant i precyzyjnie kontrolować wyjściowe wartości liczbowe. Daje to elastyczność integracji Aspose.GIS z dowolnym przepływem pracy GIS, bazą danych lub usługą internetową, które konsumują WKT.

## FAQ
### Czy Aspose.GIS jest kompatybilny ze wszystkimi wersjami .NET?
Tak, Aspose.GIS obsługuje .NET Framework 4.0 i wyższe.  

### Czy mogę używać Aspose.GIS w projektach komercyjnych?
Tak, Aspose.GIS może być używany zarówno w projektach prywatnych, jak i komercyjnych.  

### Czy Aspose.GIS zapewnia wsparcie dla innych formatów danych przestrzennych?
Tak, Aspose.GIS obsługuje szeroką gamę formatów danych przestrzennych, w tym ESRI Shapefile, GeoJSON i KML.  

### Czy dostępna jest darmowa wersja próbna Aspose.GIS?
Tak, możesz pobrać darmową wersję próbną Aspose.GIS z [tutaj](https://releases.aspose.com/).  

### Gdzie mogę uzyskać pomoc lub wsparcie dla Aspose.GIS?
Możesz zamieścić swoje pytania lub poprosić o pomoc w społeczności Aspose.GIS na [forum](https://forum.aspose.com/c/gis/33).

## Najczęściej zadawane pytania
**Q: Jak wyeksportować kolekcję Geometry do pojedynczego ciągu WKT?**  
A: Iteruj po każdej geometrii w kolekcji i łącz wyniki `AsText`, opcjonalnie oddzielając je przecinkami lub znakami nowej linii.

**Q: Czy mogę zmienić SRID bez modyfikacji współrzędnych?**  
A: Tak, ustaw właściwość `SpatialReferenceSystem` na żądany SRID; wartości współrzędnych pozostają niezmienione.

**Q: Co się stanie, jeśli użyję nieobsługiwanego wariantu WKT?**  
A: Aspose.GIS zgłosi `ArgumentException`. Zawsze weryfikuj wariant względem wartości wyliczenia `WktVariant`.

---

**Ostatnia aktualizacja:** 2025-12-23  
**Testowano z:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}