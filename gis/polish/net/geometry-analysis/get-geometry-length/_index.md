---
date: 2026-08-13
description: Dowiedz się, jak obliczyć długość geometrii w .NET przy użyciu Aspose.GIS,
  aby efektywnie obsługiwać dane przestrzenne. Zawiera przykłady pobierania długości
  linii w C# oraz obliczania długości linii w C#.
keywords:
- calculate geometry length .net
- Aspose.GIS length calculation
- C# geometry length
lastmod: 2026-08-13
linktitle: Pobierz długość geometrii
og_description: Oblicz długość geometrii w .NET przy użyciu Aspose.GIS. Przykłady
  pobierania długości linii w C# oraz obwodu wielokąta w zwięzłym, wydajnym przewodniku
  dla programistów .NET.
og_image_alt: Developer guide showing how to calculate geometry length in .NET with
  Aspose.GIS
og_title: Oblicz długość geometrii w .NET z Aspose.GIS – Szybkie pomiary przestrzenne
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to calculate geometry length .NET using Aspose.GIS for efficient
    spatial data handling. Includes get line length C# and calculate line length C#
    examples.
  headline: How to Calculate Geometry Length .NET with Aspose.GIS
  type: TechArticle
- description: Learn how to calculate geometry length .NET using Aspose.GIS for efficient
    spatial data handling. Includes get line length C# and calculate line length C#
    examples.
  name: How to Calculate Geometry Length .NET with Aspose.GIS
  steps:
  - name: Create geometry objects
    text: To begin with, create the geometry objects representing the shapes for which
      you want to calculate the length. This can include lines, polygons, or any other
      geometrical shapes.
  - name: Calculate line length in C#
    text: Once you have created the line geometry, you can calculate its length using
      the `GetLength()` method. This demonstrates **calculate line length c#** in
      a single line of code.
  - name: Create polygon geometry
    text: Similarly, you can create polygon geometry objects using the `Polygon` and
      `LinearRing` classes.
  - name: Get length of a polygon
    text: For polygons, the `GetLength()` method returns the perimeter, which is effectively
      the **how to get length** of the shape.
  type: HowTo
- questions:
  - answer: Aspose.GIS for .NET is compatible with .NET Framework 4.6.1 or later versions,
      as well as .NET 5/6/7.
    question: Is Aspose.GIS for .NET compatible with all .NET frameworks?
  - answer: Yes, you can avail of a free trial of Aspose.GIS for .NET from [here](https://releases.aspose.com/).
    question: Can I try Aspose.GIS for .NET before purchasing?
  - answer: You can find support and assistance from the Aspose.GIS community forum
      [here](https://forum.aspose.com/c/gis/33).
    question: Where can I find support for Aspose.GIS for .NET?
  - answer: You can acquire a temporary license from [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: Yes, Aspose.GIS for .NET provides various formatting options to customize
      the output format as per your requirements.
    question: Can I customize the output format for geometry length calculations?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geometry length
- Aspose.GIS
- C# GIS
- spatial calculations
- line length
title: Jak obliczyć długość geometrii w .NET przy użyciu Aspose.GIS
url: /pl/net/geometry-analysis/get-geometry-length/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak obliczyć długość geometrii .NET z Aspose.GIS

## Wprowadzenie
Jeśli szukasz jasnego, praktycznego sposobu na **obliczanie długości geometrii w .NET**, trafiłeś we właściwe miejsce. Aspose.GIS dla .NET dostarcza bogaty zestaw API skoncentrowanych na GIS, które upraszczają i przyspieszają obliczenia przestrzenne — takie jak mierzenie długości linii czy obwodu wielokąta. W tym samouczku przeprowadzimy Cię przez cały proces, od konfiguracji środowiska po napisanie kodu C#, który zwraca dokładne wartości długości.

## Szybkie odpowiedzi
- **Co zwraca „GetLength()”?** Dla linii zwraca długość linii; dla wielokątów zwraca obwód.  
- **Jaka przestrzeń nazw jest wymagana?** `Aspose.Gis.Geometries`.  
- **Czy mogę używać tego z .NET 6?** Tak, Aspose.GIS obsługuje .NET 5, .NET 6 i nowsze.  
- **Czy potrzebna jest licencja do rozwoju?** Darmowa wersja próbna wystarczy do oceny; licencja jest wymagana w produkcji.  
- **Czy obliczenia są świadome jednostek?** Długość jest zwracana w jednostkach układu współrzędnych (np. metry dla układów rzutowanych).

## Czym jest długość geometrii?
`Geometry.GetLength()` oblicza całkowitą odległość liniową obiektu geometrycznego na podstawie jego wartości współrzędnych. Dla `LineString` sumuje odległości pomiędzy kolejnymi wierzchołkami, zwracając długość linii. Zastosowane do `Polygon` dodaje długości wszystkich krawędzi, efektywnie podając obwód kształtu.

## Dlaczego warto używać Aspose.GIS do obliczeń długości?
Aspose.GIS oferuje w pełni zarządzaną bibliotekę .NET, która wykonuje obliczenia przestrzenne bez potrzeby natywnych binariów, co upraszcza wdrażanie na Windows, Linux i macOS. Obsługuje ponad pięćdziesiąt układów odniesienia współrzędnych, dostarczając wyniki o wysokiej precyzji podwójnej precyzji nawet dla linii o długości setek kilometrów, i integruje się bezproblemowo z projektami .NET 5/6/7, zapewniając spójną wydajność i dokładność.

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz następujące:

### 1. Biblioteka Aspose.GIS dla .NET
Po pierwsze, musisz mieć zainstalowaną bibliotekę Aspose.GIS dla .NET w swoim środowisku programistycznym. Jeśli jeszcze tego nie zrobiłeś, możesz pobrać ją ze strony [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/) .

### 2. Środowisko programistyczne .NET
Upewnij się, że masz skonfigurowane środowisko programistyczne .NET na swoim komputerze. Obejmuje to posiadanie Visual Studio lub innego kompatybilnego IDE.

### 3. Podstawowa znajomość C#
Podstawowa znajomość języka programowania C# jest niezbędna, aby śledzić ten samouczek.

## Importowanie przestrzeni nazw
Aby wykorzystać funkcje udostępniane przez Aspose.GIS dla .NET, musisz zaimportować niezbędne przestrzenie nazw do swojego projektu C#.

### Importuj przestrzeń nazw Aspose.GIS
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Jak uzyskać długość linii w C#
`LineString` w Aspose.GIS reprezentuje serię dwóch lub więcej punktów połączonych prostymi odcinkami, modelując cechy liniowe takie jak drogi, rzeki czy linie użyteczności publicznej w określonym układzie odniesienia współrzędnych. Po skonstruowaniu `LineString` z pożądanymi wierzchołkami, wywołanie metody `GetLength()` zwraca całkowitą odległość mierzoną w jednostkach CRS geometrii, co pozwala szybko uzyskać precyzyjne pomiary linii do routingu, analiz opartych na odległości lub raportowania, i może być dalej przetwarzane lub przechowywane w razie potrzeby.

### Krok 1: Utwórz obiekty geometryczne
Na początek utwórz obiekty geometryczne reprezentujące kształty, dla których chcesz obliczyć długość. Mogą to być linie, wielokąty lub inne kształty geometryczne.

```csharp
var line = new LineString();
line.AddPoint(0, 0);
line.AddPoint(2, 2);
line.AddPoint(2, 0);
```

### Krok 2: Oblicz długość linii w C#
Gdy już utworzysz geometrię linii, możesz obliczyć jej długość przy użyciu metody `GetLength()`. To demonstruje **obliczanie długości linii w C#** w jednej linii kodu.

```csharp
Console.WriteLine("{0:F}", line.GetLength()); // Output: 4.83
```

## Jak obliczyć długość linii w C# dla wielokątów
`Polygon` w Aspose.GIS składa się z zewnętrznego `LinearRing`, który definiuje jego granicę, oraz opcjonalnych wewnętrznych pierścieni reprezentujących otwory, modelując cechy powierzchniowe takie jak działki, jeziora czy strefy administracyjne w określonym odniesieniu przestrzennym. Utwórz zewnętrzny `LinearRing`, podając wierzchołki wielokąta, a następnie zainstaluj `Polygon` z tym pierścieniem; wywołanie `GetLength()` na wielokącie oblicza całkowity obwód, co jest przydatne przy szacowaniu długości ogrodzenia, raportowaniu granic lub konwersji wartości obwodu na inne jednostki.

### Krok 3: Utwórz geometrię wielokąta
Podobnie, możesz tworzyć obiekty geometrii wielokąta przy użyciu klas `Polygon` i `LinearRing`.

```csharp
var rectangle = new Polygon(new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 1),
    new Point(1, 1),
    new Point(1, 0),
    new Point(0, 0),
}));
```

### Krok 4: Pobierz długość wielokąta
Dla wielokątów metoda `GetLength()` zwraca obwód, co jest w praktyce **sposobem uzyskania długości** kształtu.

```csharp
Console.WriteLine("{0:F}", rectangle.GetLength()); // Output: 4.00
```

## Typowe problemy i rozwiązania
| Problem | Rozwiązanie |
|-------|----------|
| **Nieoczekiwana zerowa długość** | Zweryfikuj, czy układ współrzędnych geometrii odpowiada dostarczonym danym; duplikaty punktów mogą powodować segmenty o zerowej długości. |
| **Nieprawidłowe jednostki** | Pamiętaj, że `GetLength()` zwraca wartości w jednostkach CRS. Przelicz na metry/stopę w razie potrzeby. |
| **Wydajność przy dużych zestawach danych** | Ponownie używaj obiektów geometrycznych, gdy to możliwe, i unikaj tworzenia tysięcy tymczasowych punktów w ciasnych pętlach. |

## Najczęściej zadawane pytania

**P: Czy Aspose.GIS dla .NET jest kompatybilny ze wszystkimi frameworkami .NET?**  
O: Aspose.GIS dla .NET jest kompatybilny z .NET Framework 4.6.1 lub nowszymi wersjami, a także z .NET 5/6/7.

**P: Czy mogę wypróbować Aspose.GIS dla .NET przed zakupem?**  
O: Tak, możesz skorzystać z darmowej wersji próbnej Aspose.GIS dla .NET [tutaj](https://releases.aspose.com/).

**P: Gdzie mogę znaleźć wsparcie dla Aspose.GIS dla .NET?**  
O: Wsparcie i pomoc możesz uzyskać na forum społeczności Aspose.GIS [tutaj](https://forum.aspose.com/c/gis/33).

**P: Jak mogę uzyskać tymczasową licencję dla Aspose.GIS dla .NET?**  
O: Tymczasową licencję możesz uzyskać [tutaj](https://purchase.aspose.com/temporary-license/).

**P: Czy mogę dostosować format wyjściowy obliczeń długości geometrii?**  
O: Tak, Aspose.GIS dla .NET oferuje różne opcje formatowania, aby dostosować format wyjściowy do Twoich wymagań.

## Podsumowanie
W tym samouczku omówiliśmy **jak obliczyć długość geometrii w .NET** dla zarówno linii, jak i geometrii wielokątów przy użyciu Aspose.GIS dla .NET. Postępując zgodnie z przykładami krok po kroku, możesz teraz zintegrować precyzyjne pomiary przestrzenne w dowolnej aplikacji .NET, niezależnie od tego, czy jest to narzędzie GIS na pulpit, usługa internetowa, czy potok przetwarzania danych w tle.

---

**Ostatnia aktualizacja:** 2026-08-13  
**Testowano z:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose

## Powiązane samouczki

- [Dowiedz się, jak utworzyć geometrię LineString przy użyciu Aspose.GIS dla .NET](/gis/net/geometry-creation/create-linestring-geometry/)
- [Jak obliczyć powierzchnię przy użyciu Aspose.GIS dla .NET](/gis/net/geometry-analysis/get-geometry-area/)
- [Jak utworzyć geometrię punktu i uzyskać typ geometrii przy użyciu Aspose.GIS dla .NET](/gis/net/geometry-analysis/get-geometry-type/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}