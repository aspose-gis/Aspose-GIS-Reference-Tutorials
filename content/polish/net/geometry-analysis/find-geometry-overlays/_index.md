---
title: Opanowanie nakładek geometrycznych za pomocą Aspose.GIS dla .NET
linktitle: Znajdź nakładki geometryczne
second_title: Aspose.GIS .NET API
description: Dowiedz się, jak wykonywać operacje nakładania geometrycznego przy użyciu Aspose.GIS dla .NET. Opanuj operacje na przecięciach, sumach, różnicach i różnicach symetrycznych.
type: docs
weight: 16
url: /pl/net/geometry-analysis/find-geometry-overlays/
---
## Wstęp
dziedzinie systemów informacji geograficznej (GIS) operacje nakładania mają fundamentalne znaczenie dla analizy przestrzennej. Umożliwiają porównywanie i łączenie różnych zbiorów danych przestrzennych w celu uzyskania cennych spostrzeżeń. Aspose.GIS dla .NET zapewnia solidną funkcjonalność do wydajnego wykonywania nakładek geometrycznych. W tym samouczku zajmiemy się różnymi operacjami nakładek, takimi jak przecięcie, suma, różnica i różnica symetryczna, przy użyciu Aspose.GIS dla .NET.
## Warunki wstępne
Przed przystąpieniem do samouczka upewnij się, że spełniasz następujące wymagania wstępne:
### 1. Środowisko programistyczne .NET
Upewnij się, że na komputerze jest skonfigurowane środowisko programistyczne .NET. Zestaw SDK platformy .NET można pobrać i zainstalować z witryny internetowej platformy .NET.
### 2. Biblioteka Aspose.GIS dla .NET
 Pobierz i zainstaluj bibliotekę Aspose.GIS dla .NET z[strona internetowa](https://releases.aspose.com/gis/net/).
## Importuj przestrzenie nazw
Zanim zaczniesz używać Aspose.GIS dla .NET, musisz zaimportować niezbędne przestrzenie nazw do swojego projektu.
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Krok 1: Utwórz obiekty wielokątne
Najpierw zdefiniujemy dwa obiekty wielokątne reprezentujące obszary przestrzenne.
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
## Krok 2: Wykonaj operację przecięcia
Następnie znajdźmy przecięcie dwóch wielokątów.
```csharp
var intersection = polygon1.Intersection(polygon2);
Console.WriteLine("Intersection type is {0}", intersection.GeometryType); // Wielokąt
```
## Krok 3: Wydrukuj punkty przecięcia
Wydrukujemy punkty wielokąta przecięcia.
```csharp
PrintRing(((IPolygon)intersection).ExteriorRing);
```
## Krok 4: Wykonaj operację Unii
Teraz znajdźmy sumę dwóch wielokątów.
```csharp
var union = polygon1.Union(polygon2);
Console.WriteLine("Union type is {0}", union.GeometryType); // Wielokąt
```
## Krok 5: Wydrukuj punkty Union
Wydrukuj punkty wielokąta sumy.
```csharp
PrintRing(((IPolygon)union).ExteriorRing);
```
## Krok 6: Wykonaj operację różnicową
Następnie znajdźmy różnicę między dwoma wielokątami.
```csharp
var difference = polygon1.Difference(polygon2);
Console.WriteLine("Difference type is {0}", difference.GeometryType); // Wielokąt
```
## Krok 7: Wydrukuj punkty różnicowe
Wydrukuj punkty wielokąta różnicowego.
```csharp
PrintRing(((IPolygon)difference).ExteriorRing);
```
## Krok 8: Wykonaj operację różnicy symetrycznej
Na koniec znajdźmy różnicę symetryczną między dwoma wielokątami.
```csharp
var symDifference = polygon1.SymDifference(polygon2);
Console.WriteLine("Symmetric Difference type is {0}", symDifference.GeometryType); // Multiwielokąt
```
## Krok 9: Wydrukuj wielokąty różnic symetrycznych
Wydrukuj punkty każdego wielokąta w różnicy symetrycznej.
```csharp
var multiPolygon = (IMultiPolygon)symDifference;
Console.WriteLine("Polygons count is {0}", multiPolygon.Count); // 2
PrintRing(((IPolygon)multiPolygon[0]).ExteriorRing);
PrintRing(((IPolygon)multiPolygon[1]).ExteriorRing);
```
## Wniosek
Opanowanie nakładek geometrycznych ma kluczowe znaczenie w analizie przestrzennej, a Aspose.GIS dla .NET zapewnia kompleksowy zestaw narzędzi do wydajnego wykonywania tych operacji. Wykonując ten samouczek, nauczyłeś się wykorzystywać Aspose.GIS dla .NET do wykonywania operacji przecięcia, sumy, różnicy i różnicy symetrycznej na kształtach geometrycznych.
## Często zadawane pytania
### P: Czy mogę używać Aspose.GIS dla .NET w moich projektach komercyjnych?
Tak, Aspose.GIS dla .NET może być używany zarówno w projektach komercyjnych, jak i niekomercyjnych.
### P: Czy dostępna jest wersja próbna Aspose.GIS dla .NET?
 Tak, możesz pobrać bezpłatną wersję próbną ze strony[Tutaj](https://releases.aspose.com/).
### P: Jak mogę uzyskać wsparcie dla Aspose.GIS dla .NET?
 Możesz uzyskać pomoc na forum społeczności Aspose.GIS[Tutaj](https://forum.aspose.com/c/gis/33).
### P: Czy dostępne są jakieś tymczasowe licencje dla Aspose.GIS dla .NET?
 Tak, dostępne są licencje tymczasowe do celów testowania i oceny. Można je uzyskać od[Tutaj](https://purchase.aspose.com/temporary-license/).
### P: Czy mogę kupić Aspose.GIS bezpośrednio dla .NET?
 Tak, możesz kupić Aspose.GIS dla .NET na stronie internetowej[Tutaj](https://purchase.aspose.com/buy).