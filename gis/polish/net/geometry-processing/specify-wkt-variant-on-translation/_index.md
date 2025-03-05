---
title: Określ wariant WKT w tłumaczeniu za pomocą Aspose.GIS
linktitle: Określ wariant WKT w tłumaczeniu
second_title: Aspose.GIS .NET API
description: Dowiedz się, jak określić warianty WKT w Aspose.GIS dla .NET, aby skutecznie kontrolować format i precyzję reprezentacji danych przestrzennych.
type: docs
weight: 19
url: /pl/net/geometry-processing/specify-wkt-variant-on-translation/
---
## Wstęp
Aspose.GIS dla .NET to potężna biblioteka, która umożliwia programistom bezproblemową pracę z danymi systemu informacji geograficznej (GIS) w aplikacjach .NET. Jedną z podstawowych funkcji udostępnianych przez Aspose.GIS jest możliwość określenia wariantu tekstu dobrze znanego (WKT) podczas tłumaczenia, umożliwiając użytkownikom kontrolowanie formatu i precyzji reprezentacji danych przestrzennych. W tym samouczku przyjrzymy się, jak krok po kroku określić warianty WKT przy użyciu Aspose.GIS dla .NET.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:
1. Aspose.GIS dla .NET: Pobierz i zainstaluj Aspose.GIS dla .NET z[strona pobierania](https://releases.aspose.com/gis/net/).
2. Środowisko programistyczne: Upewnij się, że masz skonfigurowane środowisko programistyczne .NET.
3. Podstawowa wiedza: Znajomość języka programowania C# i frameworku .NET.

## Importuj przestrzenie nazw
Przed użyciem funkcjonalności Aspose.GIS w swoim kodzie zaimportuj niezbędne przestrzenie nazw:
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
## Krok 1: Utwórz obiekt punktowy
 Najpierw utwórz`Point` obiekt z szerokością, długością geograficzną i opcjonalnymi wartościami miary (M):
```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```
## Krok 2: Ustaw przestrzenny system odniesienia (SRS)
Przypisz system odniesień przestrzennych (SRS) do obiektu punktowego. W tym przykładzie używamy systemu odniesień przestrzennych WGS84:
```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```
## Krok 3: Określ wariant WKT
 Teraz określ wariant WKT do tłumaczenia. Aspose.GIS obsługuje różne warianty WKT, w tym`Iso`, `SimpleFeatureAccessOutdated` , I`ExtendedPostGis`. Wybierz odpowiedni wariant w oparciu o swoje wymagania:
```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // PUNKT M (23,5732, 25,3421, 40,3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // PUNKT (23,5732, 25,3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;PUNKT (23,5732, 25,3421, 40,3)
```
## Krok 4: Kontroluj format liczbowy
Można kontrolować format numeryczny współrzędnych w reprezentacji WKT. Aspose.GIS udostępnia opcje określenia precyzji dziesiętnej:
```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // PUNKT M (23,5732 25,342099999999999 40,299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // PUNKT M (23,5732 25,3421 40,3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // PUNKT M (23,6 25,3 40,3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // PUNKT M (23,573 25,342 40,3)
```

## Wniosek
tym samouczku nauczyliśmy się, jak określić warianty WKT podczas tłumaczenia przy użyciu Aspose.GIS dla .NET. Wykonując kroki opisane powyżej, programiści mogą skutecznie kontrolować format i precyzję reprezentacji danych przestrzennych w swoich aplikacjach .NET, zwiększając elastyczność i użyteczność systemów informacji geograficznej.
## Często zadawane pytania
### Czy Aspose.GIS jest kompatybilny ze wszystkimi wersjami .NET?
Tak, Aspose.GIS obsługuje .NET Framework 4.0 i nowsze wersje.
### Czy mogę używać Aspose.GIS w projektach komercyjnych?
Tak, Aspose.GIS może być używany zarówno w projektach osobistych, jak i komercyjnych.
### Czy Aspose.GIS zapewnia obsługę innych formatów danych przestrzennych?
Tak, Aspose.GIS obsługuje szeroką gamę formatów danych przestrzennych, w tym ESRI Shapefile, GeoJSON i KML.
### Czy dostępna jest bezpłatna wersja próbna Aspose.GIS?
 Tak, możesz pobrać bezpłatną wersję próbną Aspose.GIS ze strony[Tutaj](https://releases.aspose.com/).
### Gdzie mogę uzyskać pomoc lub wsparcie dla Aspose.GIS?
 Możesz zamieścić swoje zapytania lub zwrócić się o pomoc do społeczności Aspose.GIS na stronie[forum](https://forum.aspose.com/c/gis/33).