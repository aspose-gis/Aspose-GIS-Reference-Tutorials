---
title: Policz geometrie w geometrii za pomocą Aspose.GIS
linktitle: Policz geometrie w geometrii
second_title: Aspose.GIS .NET API
description: Dowiedz się, jak liczyć geometrie w geometrii przy użyciu Aspose.GIS dla .NET. Samouczek krok po kroku z przykładami kodu dla programistów.
type: docs
weight: 23
url: /pl/net/geometry-creation/count-geometries-in-geometry/
---
## Wstęp
Aspose.GIS dla .NET to potężne narzędzie dla programistów chcących włączyć funkcjonalność geoprzestrzenną do swoich aplikacji .NET. Niezależnie od tego, czy tworzysz oprogramowanie do mapowania, usługi oparte na lokalizacji, czy narzędzia do analizy przestrzennej, Aspose.GIS zapewnia kompleksowy zestaw funkcji spełniających Twoje potrzeby. W tym samouczku odkryjemy, jak liczyć geometrie w geometrii przy użyciu Aspose.GIS dla .NET.
## Warunki wstępne
Zanim zagłębisz się w ten samouczek, upewnij się, że spełniasz następujące wymagania wstępne:
1. Visual Studio: Upewnij się, że masz zainstalowany program Visual Studio w swoim systemie.
2. Aspose.GIS dla .NET: Pobierz i zainstaluj Aspose.GIS dla .NET z[strona pobierania](https://releases.aspose.com/gis/net/).
3. Podstawowa znajomość języka C#: Zapoznaj się z podstawami języka programowania C#.

## Importuj przestrzenie nazw
Zanim zaczniesz kodować, musisz zaimportować niezbędne przestrzenie nazw, aby uzyskać dostęp do funkcjonalności Aspose.GIS.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Krok 2: Utwórz geometrię punktową
```csharp
Point point = new Point(40.7128, -74.006);
```
 Tutaj tworzymy`Point` geometria o szerokości geograficznej 40,7128 i długości geograficznej -74,006.
## Krok 3: Utwórz geometrię LineString
```csharp
LineString line = new LineString();
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```
 Ten krok tworzy`LineString` geometrii i dodaje do niej dwa punkty.
## Krok 4: Utwórz kolekcję geometrii
```csharp
GeometryCollection geometryCollection = new GeometryCollection();
geometryCollection.Add(point);
geometryCollection.Add(line);
```
 Następnie tworzymy`GeometryCollection` i dodaj do niego wcześniej utworzoną geometrię punktów i linii.
## Krok 5: Policz geometrie
```csharp
int geometriesCount = geometryCollection.Count;
```
 W tym kroku zliczana jest liczba geometrii w obrębie`GeometryCollection`.
## Krok 6: Wyświetl liczbę
```csharp
Console.WriteLine(geometriesCount); // 2
```
 Na koniec wypisujemy liczbę geometrii, która w tym przypadku jest`2`.

## Wniosek
tym samouczku nauczyliśmy się liczyć geometrie w geometrii przy użyciu Aspose.GIS dla .NET. Wykonując poniższe kroki, można z łatwością włączyć funkcje geoprzestrzenne do aplikacji .NET.
## Często zadawane pytania
### Czy Aspose.GIS dla .NET nadaje się zarówno do aplikacji komputerowych, jak i internetowych?
Tak, Aspose.GIS dla .NET może być bezproblemowo używany zarówno w aplikacjach stacjonarnych, jak i internetowych.
### Czy mogę wykonywać zapytania przestrzenne przy użyciu Aspose.GIS dla .NET?
Absolutnie Aspose.GIS dla .NET zapewnia solidną obsługę wykonywania zapytań przestrzennych na geometrię.
### Czy Aspose.GIS dla .NET obsługuje różne formaty plików GIS?
Tak, Aspose.GIS dla .NET obsługuje szeroką gamę formatów plików GIS, w tym SHP, KML i GeoJSON.
### Czy dostępna jest bezpłatna wersja próbna Aspose.GIS dla .NET?
 Tak, możesz pobrać bezpłatną wersję próbną ze strony[strona internetowa](https://releases.aspose.com/).
### Gdzie mogę znaleźć wsparcie dla Aspose.GIS dla .NET?
 Wsparcie znajdziesz na stronie[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33).