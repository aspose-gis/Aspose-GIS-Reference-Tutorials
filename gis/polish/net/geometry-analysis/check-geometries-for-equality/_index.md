---
date: 2026-06-05
description: Dowiedz się, jak porównać geometrie w .NET przy użyciu Aspose.GIS, wykrywać
  zduplikowane geometrie i sprawdzać równość geometrii w swoich aplikacjach.
keywords:
- how to compare geometries
- detect duplicate geometries
- Aspose.GIS geometry equality
linktitle: Jak porównać geometrie pod kątem równości
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to compare geometries in .NET using Aspose.GIS, detect duplicate
    geometries, and check geometry equality in your applications.
  headline: How to Compare Geometries for Equality using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS works with .NET Framework, .NET Core, and .NET Standard
      projects.
    question: Can I use Aspose.GIS for .NET with other .NET frameworks?
  - answer: Absolutely. Download a trial from the [Aspose.GIS releases page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Detailed docs are on the [Aspose.GIS documentation page](https://reference.aspose.com/gis/net/).
    question: Where can I find the full API documentation?
  - answer: Post your question on the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How do I get help if I run into an issue?
  - answer: Yes, temporary licenses are available on the [purchase page](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for evaluation?
  type: FAQPage
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
W tym samouczku nauczysz się **jak porównać geometrie** przy użyciu Aspose.GIS dla .NET, co jest kluczowe, gdy musisz wykrywać duplikaty geometrii, walidować dane przestrzenne lub egzekwować reguły topologiczne. Niezależnie od tego, czy tworzysz usługę mapowania, przeprowadzasz wsadową analizę przestrzenną, czy po prostu weryfikujesz, że dwa kształty zajmują tę samą lokalizację, ten przewodnik poprowadzi Cię przez tworzenie, modyfikowanie i testowanie równości geometrii przy użyciu czystego, gotowego do produkcji kodu C#.

## Szybkie odpowiedzi
- **Co oznacza „compare geometries”?** Sprawdza, czy dwa obiekty geometryczne zajmują tę samą przestrzeń, niezależnie od tego, jak zostały skonstruowane.  
- **Która metoda jest używana?** `SpatiallyEquals` z API Aspose.GIS.  
- **Czy potrzebuję licencji do rozwoju?** Darmowa wersja próbna działa do testów; licencja komercyjna jest wymagana w produkcji.  
- **Obsługiwane wersje .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Typowy czas implementacji?** Około 5‑10 minut dla podstawowego sprawdzenia równości.

## Co to jest równość geometrii?
Równość geometrii, zwana także równością przestrzenną, oznacza, że dwie geometrie reprezentują dokładnie ten sam zestaw punktów na powierzchni ziemi. Nawet jeśli jedna geometria jest zbudowana jako `MultiLineString`, a druga jako pojedynczy `LineString`, są uznawane za równe, gdy każdy współrzędny pasuje w ramach określonej tolerancji. Ta definicja pozwala programistom niezawodnie wykrywać duplikaty geometrii w różnych źródłach danych.

## Dlaczego używać Aspose.GIS do porównywania geometrii?
Aspose.GIS oferuje wysokowydajny, offline'owy silnik geometryczny, który eliminuje potrzebę korzystania z usług zewnętrznych. **Obsługuje ponad 30 formatów wektorowych i rastrowych** (w tym WKT, GeoJSON, Shapefile, KML, GML) i może przetwarzać pliki z **setkami tysięcy wierzchołków**, przy zużyciu pamięci poniżej 50 MB. Metoda `SpatiallyEquals` biblioteki jest świadoma precyzji, zapewniając deterministyczne wyniki nawet przy współrzędnych zmiennoprzecinkowych.

### Dlaczego to ma znaczenie dla programistów
Gdy potrzebujesz **wykrywać duplikaty geometrii** w procesach wsadowych, w czasie rzeczywistym w potokach walidacji lub migracjach danych GIS, sprawdzona biblioteka eliminuje zgadywanie i zapewnia spójne wyniki w różnych dostawcach danych.

## Wymagania wstępne
Zanim zaczniesz, upewnij się, że masz następujące:

- **.NET Framework lub .NET Core zainstalowane** – dowolna wersja obsługiwana przez Aspose.GIS.  
- **Biblioteka Aspose.GIS dla .NET** – pobierz ze [strony pobierania Aspose.GIS](https://releases.aspose.com/gis/net/).  
- **Środowisko IDE do programowania** – Visual Studio, Rider lub VS Code z rozszerzeniami C#.

## Importowanie przestrzeni nazw
W swoim projekcie .NET dodaj wymagane instrukcje `using`, aby kompilator wiedział, gdzie znaleźć klasy GIS:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Krok 1: Zdefiniuj geometrie
`MultiLineString` reprezentuje kolekcję komponentów linii, podczas gdy `LineString` definiuje pojedynczą ciągłą linię. Obie klasy dziedziczą po bazowym typie `Geometry`.

Najpierw tworzymy dwie geometrie, które będziemy porównywać. W tym przykładzie `geometry1` jest `MultiLineString` składającym się z dwóch odcinków linii, natomiast `geometry2` jest pojedynczym `LineString`, który obejmuje te same punkty początkowy i końcowy.

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
`SpatiallyEquals` ocenia, czy dwie geometrie zajmują ten sam zestaw punktów, opcjonalnie przyjmując wartość tolerancji dla nieprecyzyjności zmiennoprzecinkowych.

Teraz używamy metody `SpatiallyEquals`, aby sprawdzić, czy dwa kształty są uznawane za równe przez silnik GIS.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // True
```

Konsola wypisuje `True`, ponieważ pomimo innej konstrukcji, obie geometrie pokrywają tę samą linię od (0,0) do (2,2).

## Krok 3: Zmodyfikuj jedną geometrię
Aby zilustrować, jak zmiana wpływa na równość, dodajemy dodatkowy punkt do `geometry2`.

```csharp
geometry2.AddPoint(3, 3);
```

## Krok 4: Ponownie sprawdź równość po modyfikacji
Po modyfikacji geometrie nie są już takie same, więc `SpatiallyEquals` zwraca `False`.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // False
```

Wynik `False` potwierdza, że dodatkowy punkt zerwał równość przestrzenną.

## Jak wykrywać duplikaty geometrii?
Wczytaj każdą geometrię, wywołaj `SpatiallyEquals` z odpowiednią tolerancją i odfiltruj te, które zwracają `True`. Ten wzorzec dobrze skaluje się z LINQ, umożliwiając identyfikację duplikatów kształtów w dużych kolekcjach przy użyciu kilku linii kodu. Możesz także połączyć go z `GroupBy`, aby zagregować identyczne geometrie i zmniejszyć koszty przechowywania.

## Typowe problemy i wskazówki
- **Problemy z precyzją** – Jeśli pracujesz z bardzo wysoką precyzją współrzędnych, rozważ zaokrąglanie lub użycie przeciążenia z tolerancją metody `SpatiallyEquals`.  
- **Różne SRID** – Upewnij się, że obie geometrie mają ten sam identyfikator systemu odniesienia przestrzennego (SRID) przed porównaniem.  
- **Wydajność** – Dla dużych kolekcji, porównania wsadowe przy użyciu LINQ lub pętli równoległych mogą znacznie zmniejszyć narzut.

## Najczęściej zadawane pytania
**Q: Czy mogę używać Aspose.GIS dla .NET z innymi frameworkami .NET?**  
A: Tak, Aspose.GIS działa z projektami .NET Framework, .NET Core i .NET Standard.

**Q: Czy dostępna jest darmowa wersja próbna?**  
A: Oczywiście. Pobierz wersję próbną ze [strony wydań Aspose.GIS](https://releases.aspose.com/).

**Q: Gdzie mogę znaleźć pełną dokumentację API?**  
A: Szczegółowa dokumentacja znajduje się na [stronie dokumentacji Aspose.GIS](https://reference.aspose.com/gis/net/).

**Q: Jak uzyskać pomoc, jeśli napotkam problem?**  
A: Zamieść swoje pytanie na forum społeczności Aspose.GIS [tutaj](https://forum.aspose.com/c/gis/33).

**Q: Czy mogę kupić tymczasową licencję do oceny?**  
A: Tak, tymczasowe licencje są dostępne na [stronie zakupu](https://purchase.aspose.com/temporary-license/).

## Podsumowanie
Teraz wiesz **jak porównać geometrie** przy użyciu Aspose.GIS dla .NET, od tworzenia obiektów po sprawdzanie równości przestrzennej i obsługę modyfikacji. Ta funkcjonalność jest podstawą dla bardziej zaawansowanych analiz przestrzennych, takich jak walidacja topologii, wykrywanie duplikatów i filtrowanie oparte na geometrii.

---

**Ostatnia aktualizacja:** 2026-06-05  
**Testowano z:** Aspose.GIS for .NET 24.11  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Utwórz geometrię wielokąta C# i sprawdź przecięcie przy użyciu Aspose.GIS dla .NET](/gis/net/geometry-analysis/check-geometries-intersection/)
- [Jak wykonać analizę nakładania się geometrii przestrzennych przy użyciu Aspose.GIS dla .NET](/gis/net/geometry-analysis/check-geometries-overlap/)
- [Sprawdzenie tras sieciowych: Stykające się geometrie z Aspose.GIS](/gis/net/geometry-analysis/check-geometries-touching/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}