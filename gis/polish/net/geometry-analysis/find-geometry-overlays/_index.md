---
date: 2025-12-07
description: Dowiedz się, jak wykonywać operacje nakładania w tym samouczku dotyczącym
  nakładania przestrzennego przy użyciu Aspose.GIS dla .NET. Opanuj przecięcie, sumę,
  różnicę i różnicę symetryczną.
linktitle: Find Geometry Overlays
second_title: Aspose.GIS .NET API
title: Jak wykonać operacje nakładania przy użyciu Aspose.GIS dla .NET
url: /pl/net/geometry-analysis/find-geometry-overlays/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak wykonać operacje nakładania przy użyciu Aspose.GIS dla .NET

## Wprowadzenie
Analiza nakładania jest podstawową techniką w każdym **spatial overlay tutorial** — pozwala łączyć, porównywać i wyciągać wnioski z wielu warstw geograficznych. W tym przewodniku nauczysz się **jak wykonywać operacje nakładania** takie jak Intersection, Union, Difference i Symmetric Difference przy użyciu potężnej biblioteki Aspose.GIS dla .NET. Po zakończeniu tutorialu będziesz w stanie zastosować te metody do rzeczywistych problemów GIS, takich jak planowanie zagospodarowania przestrzennego, studia oddziaływania środowiskowego i optymalizacja tras.

## Szybkie odpowiedzi
- **Czym jest operacja nakładania?** Metoda przestrzenna, która łączy dwie geometrie, tworząc nową geometrię (intersection, union itp.).  
- **Która biblioteka obsługuje nakładanie w .NET?** Aspose.GIS dla .NET.  
- **Jak długo trwa implementacja?** Około 10‑15 minut dla podstawowego przykładu.  
- **Czy potrzebna jest licencja?** wersja próbna jest darmowa; licencja komercyjna jest wymagana w środowisku produkcyjnym.  
- **Czy mogę uruchomić to na .NET Core / .NET 6+?** Tak — Aspose.GIS obsługuje wszystkie nowoczesne środowiska .NET.

## Czym jest operacja nakładania?
Operacja nakładania przyjmuje dwa kształty geometryczne i oblicza nowy kształt w oparciu o ich relację przestrzenną.  
- **Intersection** zwraca obszar wspólny dla obu kształtów.  
- **Union** łączy kształty w jedną geometrię.  
- **Difference** odejmuje jeden kształt od drugiego.  
- **Symmetric Difference** zwraca części, które należą do jednego z kształtów, ale nie do obu.

## Dlaczego używać Aspose.GIS do nakładania?
Aspose.GIS oferuje czyste, w pełni zarządzane API, które ukrywa niskopoziomową matematykę, pozwalając skupić się na logice biznesowej. Działa wieloplatformowo, efektywnie obsługuje duże zestawy danych i integruje się bezproblemowo z innymi komponentami .NET.

## Wymagania wstępne
- Środowisko programistyczne .NET (Visual Studio, VS Code lub .NET CLI).  
- Biblioteka Aspose.GIS dla .NET – pobierz najnowszą wersję ze [official site](https://releases.aspose.com/gis/net/).  

### Importowanie przestrzeni nazw
Zanim zaczniesz korzystać z Aspose.GIS dla .NET, musisz zaimportować niezbędne przestrzenie nazw do swojego projektu.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Jak wykonać operacje nakładania w .NET
Poniżej znajduje się krok po kroku przewodnik tworzenia dwóch wielokątów i zastosowania każdej metody nakładania.

### Krok 1: Utwórz obiekty wielokątów
Najpierw definiujemy dwa proste kwadratowe wielokąty, które częściowo się nakładają. Posłużą one jako dane testowe.

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

### Krok 2: Wykonaj operację Intersection
**Intersection** daje nam obszar nakładający się obu wielokątów.

```csharp
var intersection = polygon1.Intersection(polygon2);
Console.WriteLine("Intersection type is {0}", intersection.GeometryType); // Polygon
```

### Krok 3: Wyświetl punkty Intersection
Używamy metody pomocniczej (`PrintRing`), aby wyświetlić współrzędne powstałego wielokąta.

```csharp
PrintRing(((IPolygon)intersection).ExteriorRing);
```

### Krok 4: Wykonaj operację Union
**Union** łączy oba wielokąty w jedną figurę, obejmującą cały obszar pokryty przez którykolwiek z nich.

```csharp
var union = polygon1.Union(polygon2);
Console.WriteLine("Union type is {0}", union.GeometryType); // Polygon
```

### Krok 5: Wyświetl punkty Union
Wyświetl współrzędne połączonej geometrii.

```csharp
PrintRing(((IPolygon)union).ExteriorRing);
```

### Krok 6: Wykonaj operację Difference
**Difference** odejmuje `polygon2` od `polygon1`, pozostawiając tylko tę część `polygon1`, która nie przecina się z `polygon2`.

```csharp
var difference = polygon1.Difference(polygon2);
Console.WriteLine("Difference type is {0}", difference.GeometryType); // Polygon
```

### Krok 7: Wyświetl punkty Difference
Pokaż pozostałe wierzchołki po odjęciu.

```csharp
PrintRing(((IPolygon)difference).ExteriorRing);
```

### Krok 8: Wykonaj operację Symmetric Difference
**Symmetric Difference** zwraca obszary, które należą do jednego z wielokątów, ale nie do obu. Wynikiem jest `MultiPolygon`.

```csharp
var symDifference = polygon1.SymDifference(polygon2);
Console.WriteLine("Symmetric Difference type is {0}", symDifference.GeometryType); // MultiPolygon
```

### Krok 9: Wyświetl wielokąty Symmetric Difference
Iteruj po każdym wielokącie w `MultiPolygon` i wypisz jego punkty.

```csharp
var multiPolygon = (IMultiPolygon)symDifference;
Console.WriteLine("Polygons count is {0}", multiPolygon.Count); // 2
PrintRing(((IPolygon)multiPolygon[0]).ExteriorRing);
PrintRing(((IPolygon)multiPolygon[1]).ExteriorRing);
```

## Typowe problemy i rozwiązania
| Problem | Dlaczego się pojawia | Rozwiązanie |
|-------|----------------|-----|
| `null` result from `Intersection` | Wielokąty w rzeczywistości się nie nakładają. | Zweryfikuj współrzędne lub użyj sprawdzenia `Intersects` przed wywołaniem `Intersection`. |
| Unexpected `MultiPolygon` from `SymDifference` | Symmetric Difference może generować oddzielne komponenty. | Rzutuj na `IMultiPolygon` i iteruj tak, jak pokazano. |
| Performance slowdown on large datasets | Każda operacja przelicza geometrię od nowa. | Ponownie używaj wyników pośrednich lub upraszczaj geometrie przy pomocy `Simplify()` przed nakładaniem. |

## Najczęściej zadawane pytania

**Q: Czy mogę używać Aspose.GIS dla .NET w moich projektach komercyjnych?**  
**A:** Tak, Aspose.GIS dla .NET może być używany zarówno w projektach komercyjnych, jak i niekomercyjnych przy posiadaniu ważnej licencji.

**Q: Czy dostępna jest wersja próbna Aspose.GIS dla .NET?**  
**A:** Tak, darmową wersję próbną można pobrać [tutaj](https://releases.aspose.com/).

**Q: Jak mogę uzyskać wsparcie dla Aspose.GIS dla .NET?**  
**A:** Wsparcie dostępne jest na forum społeczności Aspose.GIS [tutaj](https://forum.aspose.com/c/gis/33).

**Q: Czy dostępne są tymczasowe licencje dla Aspose.GIS dla .NET?**  
**A:** Tak, tymczasowe licencje są dostępne do testów i oceny. Można je uzyskać [tutaj](https://purchase.aspose.com/temporary-license/).

**Q: Czy mogę kupić Aspose.GIS dla .NET bezpośrednio?**  
**A:** Tak, zakup Aspose.GIS dla .NET możliwy jest na stronie [tutaj](https://purchase.aspose.com/buy).

---

**Ostatnia aktualizacja:** 2025-12-07  
**Testowano z:** Aspose.GIS 24.11 dla .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}