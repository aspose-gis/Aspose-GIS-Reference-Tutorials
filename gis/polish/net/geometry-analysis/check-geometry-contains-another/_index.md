---
title: Sprawdź, czy geometria zawiera inną
linktitle: Sprawdź, czy geometria zawiera inną
second_title: Aspose.GIS .NET API
description: Poznaj Aspose.GIS dla .NET, solidną bibliotekę do płynnej integracji danych geoprzestrzennych w aplikacjach .NET.
weight: 14
url: /pl/net/geometry-analysis/check-geometry-contains-another/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Sprawdź, czy geometria zawiera inną

## Wstęp
Aspose.GIS dla .NET to potężna biblioteka, która umożliwia programistom płynną pracę z danymi geoprzestrzennymi w aplikacjach .NET. Niezależnie od tego, czy tworzysz aplikację mapującą, przeprowadzasz analizę geoprzestrzenną, czy integrujesz funkcje oparte na lokalizacji w swoim oprogramowaniu, Aspose.GIS upraszcza proces, zapewniając intuicyjne interfejsy API i solidną funkcjonalność.
## Warunki wstępne
Zanim zaczniesz korzystać z Aspose.GIS dla .NET, upewnij się, że spełniasz następujące wymagania wstępne:
### 1. Konfiguracja środowiska programistycznego .NET
Upewnij się, że na komputerze jest skonfigurowane działające środowisko programistyczne .NET. Obejmuje to prawidłowe zainstalowanie i skonfigurowanie zestawu .NET SDK.
### 2. Instalacja Aspose.GIS
 Zainstaluj Aspose.GIS dla .NET, pobierając bibliotekę ze strony wydania[Tutaj](https://releases.aspose.com/gis/net/) . Postępuj zgodnie z instrukcjami instalacji podanymi w dokumentacji[Tutaj](https://reference.aspose.com/gis/net/)aby zintegrować Aspose.GIS z Twoim projektem.
### 3. Podstawowe zrozumienie C#
Zapoznaj się z językiem programowania C#, ponieważ Aspose.GIS dla .NET jest używany głównie z C#.

## Importuj przestrzenie nazw
W swoim projekcie C# zaimportuj niezbędne przestrzenie nazw, aby móc korzystać z funkcjonalności Aspose.GIS:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Krok 1: Zdefiniuj obiekty geometryczne
Najpierw zdefiniuj obiekty geometryczne za pomocą klas Aspose.GIS:
```csharp
var geometry1 = new Polygon();
geometry1.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 4),
    new Point(4, 4),
    new Point(4, 0),
    new Point(0, 0),
});
geometry1.AddInteriorRing(new LinearRing(new[]
{
    new Point(1, 1),
    new Point(1, 3),
    new Point(3, 3),
    new Point(3, 1),
    new Point(1, 1),
}));
var geometry2 = new Point(2, 2);
```
## Krok 2: Sprawdź szczelność przestrzenną
Następnie sprawdź, czy jedna geometria zawiera inną:
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry2)); // FAŁSZ
```
## Krok 3: Zdefiniuj inną geometrię
Zdefiniuj kolejny obiekt geometryczny:
```csharp
var geometry3 = new Point(0.5, 0.5);
```
## Krok 4: Ponownie sprawdź szczelność przestrzenną
Sprawdź, czy nowo zdefiniowana geometria zawiera się w pierwszej geometrii:
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry3)); // PRAWDA
```
## Krok 5: Równoważna funkcjonalność
 Rozumiem to`a.SpatiallyContains(b)` jest równa`b.Within(a)`:
```csharp
Console.WriteLine(geometry3.Within(geometry1)); // PRAWDA
```

## Wniosek
Podsumowując, Aspose.GIS dla .NET zapewnia potężne narzędzia do obsługi danych geoprzestrzennych w aplikacjach .NET. Postępując zgodnie z tym przewodnikiem i korzystając z podanego przykładu, możesz skutecznie przeprowadzać kontrole szczelności przestrzennej i wykorzystywać inne funkcje geoprzestrzenne w swoich projektach.
## Często zadawane pytania
### P1: Czy Aspose.GIS jest kompatybilny z .NET Core?
O: Tak, Aspose.GIS w pełni obsługuje .NET Core, umożliwiając tworzenie aplikacji geoprzestrzennych na różnych platformach.
### P2: Czy mogę przeprowadzić analizę geoprzestrzenną przy użyciu Aspose.GIS?
Odpowiedź: Oczywiście, Aspose.GIS oferuje różne funkcjonalności do analizy geoprzestrzennej, w tym zapytania przestrzenne, obliczenia odległości i manipulacje geometrią.
### P3: Jak często wydawane są aktualizacje dla Aspose.GIS?
Odp.: Aspose.GIS regularnie publikuje aktualizacje w celu poprawy wydajności, dodania nowych funkcji i rozwiązania wszelkich zgłoszonych problemów. Możesz być na bieżąco, odwiedzając stronę wydania.
### P4: Czy istnieje forum społecznościowe dla użytkowników Aspose.GIS?
O: Tak, możesz dołączyć do forum społeczności Aspose.GIS[Tutaj](https://forum.aspose.com/c/gis/33) aby łączyć się z innymi użytkownikami, zadawać pytania i dzielić się swoimi doświadczeniami.
### P5: Czy mogę wypróbować Aspose.GIS przed zakupem?
 Odp.: Oczywiście, możesz eksplorować Aspose.GIS, pobierając bezpłatną wersję próbną ze strony[Tutaj](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
