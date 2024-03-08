---
title: Sprawdź geometrię pod kątem równości
linktitle: Sprawdź geometrię pod kątem równości
second_title: Aspose.GIS .NET API
description: Dzięki temu wszechstronnemu samouczkowi dowiesz się, jak używać Aspose.GIS dla .NET do sprawdzania równości geometrii w aplikacjach .NET.
type: docs
weight: 10
url: /pl/net/geometry-analysis/check-geometries-for-equality/
---
## Wstęp
Aspose.GIS dla .NET to potężna biblioteka, która umożliwia programistom efektywną pracę z danymi geoprzestrzennymi w aplikacjach .NET. Niezależnie od tego, czy tworzysz aplikacje mapowe, narzędzia do analizy przestrzennej, czy integrujesz funkcjonalność geoprzestrzenną z istniejącym oprogramowaniem, Aspose.GIS zapewnia narzędzia potrzebne do wykonania tego zadania.
## Warunki wstępne
Zanim zaczniesz korzystać z Aspose.GIS dla .NET, upewnij się, że spełniasz następujące wymagania wstępne:
### Zainstalowano .NET Framework
Upewnij się, że w systemie zainstalowano platformę .NET Framework. Można go pobrać ze strony internetowej Microsoft.
### Aspose.GIS dla biblioteki .NET
 Pobierz i zainstaluj bibliotekę Aspose.GIS dla .NET z[strona pobierania](https://releases.aspose.com/gis/net/). Postępuj zgodnie z instrukcjami instalacji podanymi w dokumentacji.
### Środowisko Rozwoju
Skonfiguruj preferowane środowisko programistyczne, takie jak Visual Studio, do programowania w platformie .NET.

## Importuj przestrzenie nazw
W aplikacji .NET zaimportuj niezbędne przestrzenie nazw, aby móc korzystać z funkcjonalności Aspose.GIS:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Krok 1: Zdefiniuj geometrię
Najpierw zdefiniuj geometrię, którą chcesz porównać. W tym przykładzie mamy dwie geometrie:`geometry1` I`geometry2`.
```csharp
var geometry1 = new MultiLineString
{
    new LineString(new [] { new Point(0, 0), new Point(1, 1) }),
    new LineString(new [] { new Point(1, 1), new Point(2, 2) }),
};
var geometry2 = new LineString(new[]
{
    new Point(0, 0), new Point(2, 2),
});
```
## Krok 2: Sprawdź równość geometrii
 Teraz sprawdź, czy geometrie są przestrzennie równe za pomocą`SpatiallyEquals` metoda dostarczona przez Aspose.GIS.
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // PRAWDA
```
 To zostanie wydrukowane`True` do konsoli od`geometry1` I`geometry2` są przestrzennie równe.
## Krok 3: Zmodyfikuj geometrię
 Następnie zmodyfikujmy`geometry2` poprzez dodanie nowego punktu.
```csharp
geometry2.AddPoint(3, 3);
```
## Krok 4: Sprawdź ponownie równość
Teraz sprawdź ponownie równość geometrii po modyfikacji.
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // FAŁSZ
```
 Tym razem wynik będzie`False` ponieważ geometrie nie są już przestrzennie równe ze względu na dokonaną modyfikację`geometry2`.

## Wniosek
Podsumowując, Aspose.GIS dla .NET zapewnia potężne narzędzia do pracy z danymi geoprzestrzennymi w aplikacjach .NET. Postępując zgodnie z tym przewodnikiem krok po kroku, możesz łatwo sprawdzić równość geometrii przy użyciu metod Aspose.GIS.
## Często zadawane pytania
### Czy mogę używać Aspose.GIS dla .NET z innymi frameworkami .NET?
Tak, Aspose.GIS dla .NET jest kompatybilny z różnymi frameworkami .NET, w tym .NET Core i .NET Standard.
### Czy dostępna jest bezpłatna wersja próbna Aspose.GIS dla .NET?
 Tak, możesz pobrać bezpłatną wersję próbną ze strony[strona z wydaniami](https://releases.aspose.com/).
### Gdzie mogę znaleźć dokumentację Aspose.GIS dla .NET?
 Szczegółową dokumentację można znaleźć na stronie[Strona dokumentacji Aspose.GIS](https://reference.aspose.com/gis/net/).
### Jak mogę uzyskać wsparcie dla Aspose.GIS dla .NET?
 Możesz uzyskać pomoc na forum społeczności Aspose.GIS[Tutaj](https://forum.aspose.com/c/gis/33).
### Czy mogę kupić tymczasową licencję na Aspose.GIS dla .NET?
 Tak, możesz kupić tymczasową licencję na stronie[strona zakupu](https://purchase.aspose.com/temporary-license/).