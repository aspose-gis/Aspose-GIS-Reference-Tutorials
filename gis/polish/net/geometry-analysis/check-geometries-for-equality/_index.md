---
date: 2026-02-05
description: Dowiedz się, jak porównywać geometrie w .NET przy użyciu Aspose.GIS i
  sprawdzać równość geometrii w swoich aplikacjach.
linktitle: How to Compare Geometries for Equality
second_title: Aspose.GIS .NET API
title: Jak porównać geometrie pod kątem równości przy użyciu Aspose.GIS dla .NET
url: /pl/net/geometry-analysis/check-geometries-for-equality/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak porównać geometrie pod kątem równości przy użyciu Aspose.GIS dla .NET

## Wprowadzenie
W tym samouczku poznasz **sposób porównywania geometrii** przy użyciu Aspose.GIS dla .NET. Niezależnie od tego, czy tworzysz usługę mapowania, wykonujesz analizę przestrzenną, czy po prostu musisz zweryfikować, że dwa kształty reprezentują to samo miejsce, znajomość porównywania geometrii jest niezbędna. Przeprowadzimy Cię przez kompletny, end‑to‑end przykład, który pokaże, jak tworzyć, modyfikować i testować równość geometrii w kilku linijkach kodu C#.

## Szybkie odpowiedzi
- **Co oznacza „porównywanie geometrii”?** Sprawdza, czy dwa obiekty geometryczne zajmują tę samą przestrzeń, niezależnie od sposobu ich konstrukcji.  
- **Która metoda jest używana?** `SpatiallyEquals` z API Aspose.GIS.  
- **Czy potrzebna jest licencja do rozwoju?** Darmowa wersja próbna wystarczy do testów; licencja komercyjna jest wymagana w produkcji.  
- **Obsługiwane wersje .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Typowy czas implementacji?** Około 5‑10 minut dla podstawowego sprawdzenia równości.

## Co to jest równość geometrii?
Równość geometrii (często nazywana równością przestrzenną) oznacza, że dwie geometrie reprezentują dokładnie ten sam zestaw punktów na powierzchni ziemi. Dwa kształty mogą być zbudowane inaczej — np. MultiLineString vs pojedynczy LineString — ale nadal być przestrzennie równe.

## Dlaczego warto używać Aspose.GIS do porównywania geometrii?
Aspose.GIS dostarcza solidny, wysokowydajny silnik geometryczny, który:
- Obsługuje szeroką gamę formatów wektorowych (WKT, GeoJSON, Shapefile itp.).
- Oferuje metody porównywania świadome precyzji, takie jak `SpatiallyEquals`.
- Działa offline, bez zewnętrznych usług, co czyni go idealnym dla środowisk zabezpieczonych lub odizolowanych.

### Dlaczego to ważne dla deweloperów
Gdy potrzebujesz **sposobu porównywania geometrii** w procesach wsadowych, rutynach wykrywania duplikatów lub walidacji w czasie rzeczywistym, niezawodna biblioteka eliminuje zgadywanie i zapewnia spójne wyniki niezależnie od źródła danych.

## Wymagania wstępne
Zanim zaczniesz, upewnij się, że masz następujące elementy:

- **Zainstalowany .NET Framework lub .NET Core** – dowolna wersja wspierana przez Aspose.GIS.  
- **Biblioteka Aspose.GIS dla .NET** – pobierz z [strony pobierania Aspose.GIS](https://releases.aspose.com/gis/net/).  
- **Środowisko IDE** – Visual Studio, Rider lub VS Code z rozszerzeniami C#.

## Importowanie przestrzeni nazw
W swoim projekcie .NET dodaj wymagane dyrektywy `using`, aby kompilator wiedział, gdzie znajdują się klasy GIS:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Krok 1: Definiowanie geometrii
Najpierw tworzymy dwie geometrie, które będziemy porównywać. W tym przykładzie `geometry1` jest `MultiLineString` składającym się z dwóch odcinków, natomiast `geometry2` to pojedynczy `LineString` obejmujący te same punkty początkowy i końcowy.

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

## Krok 2: Sprawdzenie równości geometrii
Teraz używamy metody `SpatiallyEquals`, aby sprawdzić, czy dwa kształty są uznawane za równe przez silnik GIS.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // True
```

Konsola wypisuje `True`, ponieważ pomimo innej konstrukcji obie geometrie obejmują tę samą linię od (0,0) do (2,2).

## Krok 3: Modyfikacja jednej geometrii
Aby zobrazować, jak zmiana wpływa na równość, dodajemy dodatkowy punkt do `geometry2`.

```csharp
geometry2.AddPoint(3, 3);
```

## Krok 4: Ponowne sprawdzenie równości po modyfikacji
Po modyfikacji geometrie nie są już takie same, więc `SpatiallyEquals` zwraca `False`.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // False
```

Wynik `False` potwierdza, że dodatkowy punkt zerwał równość przestrzenną.

## Typowe problemy i wskazówki
- **Problemy z precyzją** – Jeśli pracujesz z bardzo precyzyjnymi współrzędnymi, rozważ zaokrąglanie lub użycie przeciążenia `SpatiallyEquals` z tolerancją.  
- **Różne SRID** – Upewnij się, że obie geometrie mają ten sam Spatial Reference System Identifier (SRID) przed porównaniem.  
- **Wydajność** – Dla dużych kolekcji, porównania wsadowe przy użyciu LINQ mogą zmniejszyć obciążenie.

## Najczęściej zadawane pytania
**P: Czy mogę używać Aspose.GIS dla .NET z innymi frameworkami .NET?**  
O: Tak, Aspose.GIS działa z projektami .NET Framework, .NET Core i .NET Standard.

**P: Czy dostępna jest darmowa wersja próbna?**  
O: Oczywiście. Pobierz wersję próbną ze [strony wydań Aspose.GIS](https://releases.aspose.com/).

**P: Gdzie mogę znaleźć pełną dokumentację API?**  
O: Szczegółowa dokumentacja znajduje się na [stronie dokumentacji Aspose.GIS](https://reference.aspose.com/gis/net/).

**P: Jak uzyskać pomoc w razie problemów?**  
O: Zadaj pytanie na forum społeczności Aspose.GIS [tutaj](https://forum.aspose.com/c/gis/33).

**P: Czy mogę kupić tymczasową licencję do oceny?**  
O: Tak, tymczasowe licencje są dostępne na [stronie zakupu](https://purchase.aspose.com/temporary-license/).

## Zakończenie
Teraz wiesz **jak porównywać geometrie** przy użyciu Aspose.GIS dla .NET, od tworzenia obiektów po sprawdzanie równości przestrzennej i obsługę modyfikacji. Ta funkcjonalność jest podstawą dla bardziej zaawansowanych analiz przestrzennych, takich jak walidacja topologiczna, wykrywanie duplikatów i filtrowanie oparte na geometrii.

---

**Ostatnia aktualizacja:** 2026-02-05  
**Testowano z:** Aspose.GIS dla .NET 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}