---
title: Konwersja współrzędnych za pomocą Aspose.GIS
linktitle: Konwersja współrzędnych
second_title: Aspose.GIS .NET API
description: Dowiedz się, jak konwertować współrzędne za pomocą Aspose.GIS dla .NET. Podano przewodnik krok po kroku, wymagania wstępne i często zadawane pytania.
type: docs
weight: 25
url: /pl/net/geometry-creation/convert-coordinates/
---
## Wstęp
W tym samouczku zagłębimy się w świat systemów informacji geograficznej (GIS) przy użyciu potężnej biblioteki Aspose.GIS dla .NET. Aspose.GIS to kompleksowy zestaw narzędzi, który umożliwia programistom bezproblemową pracę z danymi przestrzennymi. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz, ten samouczek poprowadzi Cię przez proces wykorzystania Aspose.GIS do efektywnej konwersji współrzędnych.
## Warunki wstępne
Przed przystąpieniem do samouczka upewnij się, że spełniasz następujące wymagania wstępne:
1. Podstawowa znajomość języka C#: Znajomość języka programowania C# jest niezbędna do zrozumienia i wdrożenia dostarczonych przykładów kodu.
  
2.  Instalacja Aspose.GIS: Upewnij się, że pobrałeś i zainstalowałeś bibliotekę Aspose.GIS dla .NET. Można go pobrać z[Witryna internetowa Aspose.GIS](https://releases.aspose.com/gis/net/).

## Importuj przestrzenie nazw
Zanim zaczniemy, zaimportujmy niezbędne przestrzenie nazw, aby uzyskać dostęp do funkcjonalności Aspose.GIS:
```csharp
using System;
using Aspose.Gis;
```

Aby ułatwić zrozumienie, podzielmy podany przykład na wiele kroków:
## Krok 1: Rozpocznij proces konwersji
```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```
W tej linii wyświetlany jest po prostu komunikat wskazujący rozpoczęcie procesu konwersji współrzędnych.
## Krok 2: Konwertuj na stopnie dziesiętne
```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```
 Tutaj konwertujemy współrzędne (25,5, 45,5) na format stopni dziesiętnych za pomocą`AsPointText` metoda z`PointFormats.DecimalDegrees` parametr. Wynik jest następnie drukowany na konsoli.
## Krok 3: Konwertuj na stopnie dziesiętne
```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```
Ten krok konwertuje współrzędne do formatu stopni dziesiętnych minut i drukuje wynik.
## Krok 4: Zamień na stopnie-minuty i sekundy
```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```
Podobnie konwertujemy współrzędne na format stopni minut sekund i wyświetlamy wynik.
## Krok 5: Konwertuj na GeoRef
```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```
Na koniec konwertujemy współrzędne do formatu GeoRef i drukujemy wynik.

## Wniosek
tym samouczku omówiliśmy proces konwersji współrzędnych przy użyciu Aspose.GIS dla .NET. Postępując zgodnie z przewodnikiem krok po kroku i wykorzystując bibliotekę Aspose.GIS, możesz efektywnie manipulować danymi przestrzennymi w aplikacjach .NET.
## Często zadawane pytania
### Czy Aspose.GIS jest kompatybilny z innymi językami programowania?
Aspose.GIS jest przeznaczony przede wszystkim dla programistów .NET, ale oferuje interoperacyjność z Javą poprzez Aspose.GIS dla Java.
### Czy mogę wypróbować Aspose.GIS przed zakupem?
 Tak, możesz uzyskać dostęp do bezpłatnej wersji próbnej Aspose.GIS z poziomu[strona internetowa](https://releases.aspose.com/).
### Jak mogę uzyskać wsparcie dla Aspose.GIS?
 Możesz zwrócić się o pomoc na forum społeczności Aspose.GIS[Tutaj](https://forum.aspose.com/c/gis/33).
### Czy dostępne są tymczasowe licencje dla Aspose.GIS?
 Tak, tymczasowe licencje można uzyskać od[strona licencji tymczasowej](https://purchase.aspose.com/temporary-license/).
### Gdzie mogę kupić Aspose.GIS?
 Możesz kupić Aspose.GIS w sklepie[strona zakupu](https://purchase.aspose.com/buy).