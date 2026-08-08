---
date: 2026-08-08
description: Poznaj analizę nakładania GIS z różnicą symetryczną przy użyciu Aspose.GIS
  for .NET. Ten samouczek pokazuje, jak wykonać overlay, polygon intersection, union,
  difference i symmetric difference w C#.
keywords:
- symmetric difference gis
- calculate polygon intersection
- how to perform overlay
lastmod: 2026-08-08
linktitle: Znajdź Geometry Overlays
og_description: Odkryj, jak wykonać analizę nakładania GIS z różnicą symetryczną przy
  użyciu Aspose.GIS for .NET. Przewodnik krok po kroku obejmuje intersection, union,
  difference i więcej.
og_image_alt: Screenshot of Aspose.GIS overlay operations in a .NET console app
og_title: Nakładanie GIS z różnicą symetryczną przy użyciu Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn symmetric difference GIS overlay analysis using Aspose.GIS for
    .NET. This tutorial shows how to perform overlay, polygon intersection, union,
    difference, and symmetric difference in C#.
  headline: Symmetric difference GIS overlay with Aspose.GIS for .NET
  type: TechArticle
- description: Learn symmetric difference GIS overlay analysis using Aspose.GIS for
    .NET. This tutorial shows how to perform overlay, polygon intersection, union,
    difference, and symmetric difference in C#.
  name: Symmetric difference GIS overlay with Aspose.GIS for .NET
  steps:
  - name: create polygon objects
    text: A `Polygon` represents a closed shape defined by a series of coordinate
      points.
  - name: perform intersection operation
    text: '`Intersection` computes the common area shared by two polygons.'
  - name: print intersection points
    text: '`PrintRing` is a helper that prints each coordinate of a polygon’s exterior
      ring.'
  - name: perform union operation
    text: '`Union` merges two polygons into a single geometry covering all areas.'
  - name: print union points
    text: Output the coordinates of the united geometry.
  - name: perform difference operation
    text: '`Difference` subtracts the second polygon from the first, leaving the non‑overlapping
      portion.'
  - name: print difference points
    text: Show the remaining vertices after the subtraction.
  - name: perform symmetric difference operation
    text: '`SymmetricDifference` returns the parts belonging to either polygon but
      not both, producing a `MultiPolygon`.'
  - name: print symmetric difference polygons
    text: Iterate through each polygon in the `MultiPolygon` and print its points.
  type: HowTo
- questions:
  - answer: Yes, a valid commercial license permits unrestricted use in production
      applications.
    question: Can I use Aspose.GIS for .NET in my commercial projects?
  - answer: Yes, you can download a free trial from the [Aspose releases page](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.GIS for .NET?
  - answer: Support is available through the Aspose GIS forum [Aspose GIS forum](https://forum.aspose.com/c/gis/33).
    question: How can I get support for Aspose.GIS for .NET?
  - answer: Yes, temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses offered for testing?
  - answer: You can buy a license directly from the website [Aspose purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase a full license for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- gis overlay
- Aspose.GIS
- .NET geometry analysis
title: Nakładanie GIS z różnicą symetryczną przy użyciu Aspose.GIS for .NET
url: /pl/net/geometry-analysis/find-geometry-overlays/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Symetryczna różnica GIS: wykonaj operacje nakładania przy użyciu Aspose.GIS dla .NET

Analiza nakładania jest podstawową techniką w każdym **samouczku nakładania przestrzennego** — pozwala łączyć, porównywać i wyciągać wnioski z wielu warstw geograficznych. W tym przewodniku nauczysz się **jak wykonywać operacje nakładania** takie jak Przecięcie, Suma, Różnica i Symetryczna różnica, korzystając z potężnej biblioteki Aspose.GIS dla .NET. Po zakończeniu samouczka będziesz mógł zastosować te metody do rzeczywistych problemów GIS, takich jak planowanie zagospodarowania przestrzennego, analizy wpływu środowiskowego i optymalizacja tras.

## Szybkie odpowiedzi
- **Czym jest operacja nakładania?** Nakładanie łączy dwie geometrie, aby utworzyć nowy kształt — przecięcie, sumę, różnicę lub symetryczną różnicę.  
- **Która biblioteka .NET obsługuje nakładanie?** Aspose.GIS dla .NET zapewnia w pełni zarządzane API dla wszystkich operacji geometrycznych opartych na teorii zbiorów.  
- **Jak długo trwa podstawowa implementacja?** Około 10‑15 minut, aby napisać, skompilować i uruchomić przykładowy kod.  
- **Czy potrzebna jest licencja do produkcji?** Tak — wymagana jest komercyjna licencja do wdrożeń produkcyjnych; dostępna jest darmowa wersja próbna do oceny.  
- **Czy mogę uruchomić to na .NET 6+?** Oczywiście — Aspose.GIS obsługuje .NET Core, .NET 5, .NET 6 i nowsze wersje.

## Czym jest operacja nakładania?

Operacje nakładania obliczają nową geometrię na podstawie relacji przestrzennej dwóch wejściowych kształtów. **Przecięcie** zwraca wspólny obszar, **Suma** łączy obszary, **Różnica** odejmuje jeden kształt od drugiego, a **Symetryczna różnica** daje części należące do jednego z kształtów, ale nie do obu. Te funkcje teorii zbiorów są matematyczną podstawą analizy GIS, umożliwiając odpowiedzi na pytania takie jak „gdzie dwa parceli gruntowe nakładają się na siebie?” lub „jaki obszar pozostaje po usunięciu strefy chronionej”.

## Dlaczego warto używać Aspose.GIS do nakładania?

Aspose.GIS obsługuje **ponad 50 formatów wektorowych i rastrowych**, może przetwarzać **zestawy danych setek stron bez ładowania całego pliku do pamięci** i działa na Windows, Linux oraz macOS. Jego zarządzane API eliminuje potrzebę natywnych bibliotek GIS, zmniejszając złożoność wdrożenia i pozwalając utrzymać całą logikę w jednym rozwiązaniu .NET.

## Typowe przypadki użycia
- **Planowanie zagospodarowania przestrzennego:** Identyfikacja nakładających się stref między proponowanymi inwestycjami a obszarami chronionymi.  
- **Analiza środowiskowa:** Obliczanie przecięcia siedlisk z źródłami zanieczyszczeń.  
- **Routing infrastruktury:** Określanie, gdzie nowe drogi przecinają istniejące korytarze użyteczności publicznej.  
- **Analiza miejska:** Łączenie wielu granic gminnych w celu stworzenia widoku regionalnego.

## Wymagania wstępne
- Działające środowisko programistyczne .NET (Visual Studio, VS Code lub .NET CLI).  
- Biblioteka Aspose.GIS dla .NET – pobierz najnowszą wersję ze [strony oficjalnej](https://releases.aspose.com/gis/net/).  

### Importuj przestrzenie nazw
Zanim zaczniesz korzystać z Aspose.GIS dla .NET, musisz zaimportować niezbędne przestrzenie nazw do swojego projektu.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Jak wykonywać operacje nakładania w .NET

`Polygon` reprezentuje zamknięty płaski kształt zdefiniowany przez zewnętrzny pierścień i opcjonalne pierścienie wewnętrzne. Każda metoda nakładania (`Intersection`, `Union`, `Difference`, `SymmetricDifference`) wykonuje określoną operację teorii zbiorów na dwóch geometriach.

Wczytaj dwa obiekty wielokątów, a następnie wywołaj odpowiednią metodę nakładania — Przecięcie, Sumę, Różnicę lub Symetryczną różnicę. Cały przepływ pracy mieści się w kilku zwięzłych linijkach kodu, a każda metoda zwraca geometrię, którą możesz dalej przetwarzać lub eksportować.

**Bezpośrednia odpowiedź:** Aby wykonać nakładanie w Aspose.GIS, utwórz dwa obiekty `Polygon`, a następnie wywołaj żądaną metodę (`Intersection`, `Union`, `Difference` lub `SymmetricDifference`). Każde wywołanie zwraca nową geometrię reprezentującą wynik, którą możesz zserializować do WKT, GeoJSON lub dowolnego obsługiwanego formatu.

### Krok 1: utwórz obiekty wielokątów
`Polygon` reprezentuje zamknięty kształt zdefiniowany przez serię punktów współrzędnych.

```csharp
var polygon1 = new Polygon();
polygon1.ExteriorRing = new LinearRing(new[]
{
	 new Point(0, 0),
	 new Point(0, 2),
	 new Point(2, 2),
	 new Point(2, 0),
	 new Point(0, 0),
 });
var polygon2 = new Polygon();
polygon2.ExteriorRing = new LinearRing(new[]
{
	new Point(1, 1),
	new Point(1, 3),
	new Point(3, 3),
	new Point(3, 1),
	new Point(1, 1),
});
```

### Krok 2: wykonaj operację przecięcia
`Intersection` oblicza wspólny obszar współdzielony przez dwa wielokąty.

```csharp
var intersection = polygon1.Intersection(polygon2);
Console.WriteLine("Intersection type is {0}", intersection.GeometryType); // Polygon
```

### Krok 3: wydrukuj punkty przecięcia
`PrintRing` to pomocnicza metoda, która wypisuje każdą współrzędną zewnętrznego pierścienia wielokąta.

```csharp
PrintRing(((IPolygon)intersection).ExteriorRing);
```

### Krok 4: wykonaj operację sumy
`Union` łączy dwa wielokąty w jedną geometrię obejmującą wszystkie obszary.

```csharp
var union = polygon1.Union(polygon2);
Console.WriteLine("Union type is {0}", union.GeometryType); // Polygon
```

### Krok 5: wydrukuj punkty sumy
Wyświetl współrzędne połączonej geometrii.

```csharp
PrintRing(((IPolygon)union).ExteriorRing);
```

### Krok 6: wykonaj operację różnicy
`Difference` odejmuje drugi wielokąt od pierwszego, pozostawiając nieprzecięty fragment.

```csharp
var difference = polygon1.Difference(polygon2);
Console.WriteLine("Difference type is {0}", difference.GeometryType); // Polygon
```

### Krok 7: wydrukuj punkty różnicy
Pokaż pozostałe wierzchołki po odjęciu.

```csharp
PrintRing(((IPolygon)difference).ExteriorRing);
```

### Krok 8: wykonaj operację symetrycznej różnicy
`SymmetricDifference` zwraca części należące do jednego z wielokątów, ale nie do obu, tworząc `MultiPolygon`.

```csharp
var symDifference = polygon1.SymDifference(polygon2);
Console.WriteLine("Symmetric Difference type is {0}", symDifference.GeometryType); // MultiPolygon
```

### Krok 9: wydrukuj wielokąty symetrycznej różnicy
Iteruj przez każdy wielokąt w `MultiPolygon` i wypisz jego punkty.

```csharp
var multiPolygon = (IMultiPolygon)symDifference;
Console.WriteLine("Polygons count is {0}", multiPolygon.Count); // 2
PrintRing(((IPolygon)multiPolygon[0]).ExteriorRing);
PrintRing(((IPolygon)multiPolygon[1]).ExteriorRing);
```

## Typowe problemy i rozwiązania
| Problem | Dlaczego się pojawia | Rozwiązanie |
|---------|----------------------|-------------|
| `null` wynik z `Intersection` | Wielokąty faktycznie się nie nakładają. | Zweryfikuj współrzędne lub użyj sprawdzenia `Intersects` przed wywołaniem `Intersection`. |
| Nieoczekiwany `MultiPolygon` z `SymDifference` | Symetryczna różnica może generować rozłączone komponenty. | Rzutuj na `IMultiPolygon` i iteruj jak pokazano. |
| Spowolnienie wydajności przy dużych zestawach danych | Każda operacja przelicza geometrię od nowa. | Ponownie używaj wyników pośrednich lub upraszczaj geometrie przy pomocy `Simplify()` przed nakładaniem. |

## Często zadawane pytania

**Q:** Czy mogę używać Aspose.GIS dla .NET w moich projektach komercyjnych?  
**A:** Tak, ważna licencja komercyjna pozwala na nieograniczone użycie w aplikacjach produkcyjnych.

**Q:** Czy dostępna jest wersja próbna Aspose.GIS dla .NET?  
**A:** Tak, możesz pobrać darmową wersję próbną ze [strony wydań Aspose](https://releases.aspose.com/).

**Q:** Jak mogę uzyskać wsparcie dla Aspose.GIS dla .NET?  
**A:** Wsparcie jest dostępne poprzez forum Aspose GIS [Aspose GIS forum](https://forum.aspose.com/c/gis/33).

**Q:** Czy oferowane są tymczasowe licencje do testów?  
**A:** Tak, tymczasowe licencje można uzyskać na [stronie tymczasowej licencji](https://purchase.aspose.com/temporary-license/).

**Q:** Gdzie mogę kupić pełną licencję na Aspose.GIS dla .NET?  
**A:** Licencję można zakupić bezpośrednio na stronie [Aspose purchase page](https://purchase.aspose.com/buy).

---

**Ostatnia aktualizacja:** 2026-08-08  
**Testowano z:** Aspose.GIS 24.11 dla .NET  
**Autor:** Aspose

## Powiązane samouczki

- [Create Polygon Geometry C# and Check Intersection with Aspose.GIS for .NET](/gis/net/geometry-analysis/check-geometries-intersection/)
- [How to Perform Spatial Overlap Analysis of Geometries with Aspose.GIS for .NET](/gis/net/geometry-analysis/check-geometries-overlap/)
- [Create Geometry Buffer Using Aspose.GIS for .NET](/gis/net/geometry-analysis/create-geometry-buffer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}