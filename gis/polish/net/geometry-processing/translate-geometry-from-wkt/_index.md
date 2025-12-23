---
date: 2025-12-23
description: Naucz się konwertować WKT na geometrię i liczyć punkty przy użyciu Aspose.GIS
  dla .NET. Przewodnik krok po kroku dla programistów.
linktitle: Translate Geometry from WKT
second_title: Aspose.GIS .NET API
title: Jak przekonwertować WKT na geometrię przy użyciu Aspose.GIS w .NET
url: /pl/net/geometry-processing/translate-geometry-from-wkt/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konwertowanie WKT na geometrię przy użyciu Aspose.GIS w .NET

## Wprowadzenie
W tym samouczku odkryjesz **jak konwertować WKT na geometrię** przy użyciu Aspose.GIS dla .NET oraz zobaczysz praktyczny przykład **jak policzyć punkty** w powstałym kształcie. Niezależnie od tego, czy tworzysz usługę mapowania, przetwarzasz dane GIS, czy po prostu potrzebujesz odczytać Well‑Known Text w aplikacji .NET, te kroki szybko pozwolą Ci rozpocząć pracę.

## Szybkie odpowiedzi
- **Czy Aspose.GIS potrafi odczytać WKT?** Tak – metoda `Geometry.FromText` bezpośrednio parsuje ciągi WKT.  
- **Ile linii kodu jest potrzebnych?** Około 5‑6 linii dla podstawowej konwersji i liczenia punktów.  
- **Czy potrzebna jest licencja do produkcji?** Tak, wymagana jest licencja komercyjna do użytku nie‑testowego.  
- **Wspierane wersje .NET?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6+.  
- **Czy liczenie punktów jest wbudowane?** Absolutnie – obiekty geometryczne udostępniają właściwość `Count`.

## Co oznacza „konwertowanie WKT na geometrię”?
Well‑Known Text (WKT) to tekstowy format służący do reprezentacji obiektów geometrycznych. Konwersja WKT na geometrię oznacza przekształcenie tego tekstu w model obiektowy (np. `ILineString`, `IPolygon`), który można programowo manipulować.

## Dlaczego używać Aspose.GIS do tej konwersji?
- **Parsowanie bez zależności** – nie wymaga zewnętrznych bibliotek.  
- **Pełny zestaw funkcji GIS** – obsługuje współrzędne 2D/3D, obsługę SRID oraz wiele formatów plików.  
- **Wysoka wydajność** – zoptymalizowane pod kątem dużych zbiorów danych i scenariuszy wielowątkowych.  

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz:

1. Aspose.GIS for .NET API – pobierz go z [tutaj](https://releases.aspose.com/gis/net/).  
2. Podstawową znajomość C# oraz środowiska programistycznego .NET (Visual Studio, VS Code itp.).

## Importowanie przestrzeni nazw
Najpierw dodaj wymagane przestrzenie nazw do swojego pliku C#:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Krok 1: Utworzenie LineString z WKT
Teraz **konwertujemy WKT na geometrię** tworząc obiekt `LineString` z ciągu WKT zawierającego współrzędne Z:

```csharp
ILineString line = (ILineString)Geometry.FromText("LINESTRING Z (0.1 0.2 0.3, 1 2 1, 12 23 2)");
```

> *Porada:* Metoda `FromText` automatycznie wykrywa typ geometrii, więc możesz rzutować ją na odpowiedni interfejs (`ILineString`, `IPolygon` itp.).

## Jak policzyć punkty w LineString?
Aby odpowiedzieć na drugorzędne zapytanie **jak policzyć punkty**, po prostu odczytaj właściwość `Count` instancji `ILineString`:

```csharp
Console.WriteLine(line.Count); // Output: 3
```

Wynik pokazuje, że linia zawiera trzy wierzchołki, co potwierdza, że konwersja się powiodła i liczba punktów jest prawidłowa.

## Zakończenie
Teraz wiesz **jak konwertować WKT na geometrię** przy użyciu Aspose.GIS dla .NET oraz jak uzyskać liczbę punktów za pomocą jednego wywołania właściwości. Te podstawy pozwalają zintegrować przetwarzanie danych GIS w dowolnej aplikacji .NET, od narzędzi desktopowych po usługi chmurowe.

## FAQ
### Czy mogę używać Aspose.GIS dla .NET w moich projektach komercyjnych?
Tak, możesz. Aspose.GIS dla .NET jest licencjonowane na dewelopera, co pozwala używać go w projektach komercyjnych bez żadnych ograniczeń.

### Czy Aspose.GIS dla .NET obsługuje inne formaty geometryczne poza WKT?
Tak, Aspose.GIS dla .NET obsługuje różne formaty geometryczne, w tym WKB, GeoJSON i Shapefile.

### Czy dostępna jest darmowa wersja próbna Aspose.GIS dla .NET?
Tak, możesz uzyskać darmową wersję próbną z [tutaj](https://releases.aspose.com/).

### Gdzie mogę znaleźć dokumentację Aspose.GIS dla .NET?
Dokumentację znajdziesz [tutaj](https://reference.aspose.com/gis/net/).

### Jak mogę uzyskać wsparcie dla Aspose.GIS dla .NET?
Wsparcie możesz uzyskać na forum Aspose.GIS [tutaj](https://forum.aspose.com/c/gis/33).

## Często zadawane pytania (dodatkowe)

**Q: Co zrobić, jeśli mój ciąg WKT zawiera nieprawidłową składnię?**  
A: `Geometry.FromText` zgłasza `FormatException`. Umieść wywołanie w bloku try‑catch, aby obsłużyć niepoprawny WKT w sposób kontrolowany.

**Q: Czy mogę konwertować kolekcję ciągów WKT jednorazowo?**  
A: Tak – iteruj po liście ciągów, wywołuj `Geometry.FromText` dla każdego elementu i przechowuj wyniki w `List<IGeometry>`.

**Q: Czy Aspose.GIS zachowuje wartości Z przy konwersji?**  
A: Absolutnie. Gdy WKT zawiera współrzędną Z (jak pokazano w przykładzie), wynikowa geometria zachowuje te wartości.

**Q: Czy można wyeksportować geometrię z powrotem do WKT po manipulacji?**  
A: Użyj metody `ToText()` na dowolnej instancji `IGeometry`, aby uzyskać reprezentację WKT.

---

**Ostatnia aktualizacja:** 2025-12-23  
**Testowano z:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}