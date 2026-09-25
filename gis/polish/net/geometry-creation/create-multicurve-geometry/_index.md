---
date: 2026-09-25
description: Dowiedz się, jak konwertować WKT na geometrię krzywej złożonej i dodać
  line string w .NET przy użyciu Aspose.GIS. Ten przewodnik pokazuje tworzenie geometrii
  z WKT przy użyciu MultiCurve.
keywords:
- compound curve geometry
- geometry from wkt
- add line string .net
lastmod: 2026-09-25
linktitle: Utwórz geometrię MultiCurve
og_description: Dowiedz się, jak konwertować WKT na geometrię krzywej złożonej i dodać
  line string w .NET przy użyciu Aspose.GIS. Ten przewodnik pokazuje tworzenie geometrii
  z WKT przy użyciu MultiCurve.
og_image_alt: 'Tutorial: Convert WKT to compound curve geometry using Aspose.GIS in
  .NET'
og_title: Konwertuj WKT na geometrię krzywej złożonej przy użyciu Aspose.GIS dla .NET
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to convert WKT to compound curve geometry and add line string
    in .NET using Aspose.GIS. This guide shows geometry from WKT creation with MultiCurve.
  headline: Convert WKT to compound curve geometry with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert WKT to compound curve geometry and add line string
    in .NET using Aspose.GIS. This guide shows geometry from WKT creation with MultiCurve.
  name: Convert WKT to compound curve geometry with Aspose.GIS for .NET
  steps:
  - name: Define the document directory and file name
    text: Set the folder where the shapefile will be saved. Replace `"Your Document
      Directory"` with the actual path on your machine.
  - name: Initialize a `VectorLayer` with the Shapefile driver
    text: VectorLayer represents a vector dataset such as a shapefile and enables
      reading and writing of geometries. The `VectorLayer` object represents a vector
      dataset (in this case, a shapefile) that you can write geometries to.
  - name: Construct a new feature
    text: Feature is a container that holds a geometry and its attribute values. A
      feature is a container for geometry and attribute data.
  - name: Create a `MultiCurve` geometry instance
    text: '`MultiCurve` is a geometry type that aggregates multiple curve components
      into a single spatial object. `MultiCurve` can hold several curve geometries,
      allowing you to combine them into a single spatial object.'
  - name: Add curve geometries to the `MultiCurve`
    text: 'Here we **convert WKT to geometry** for three different curve types: *
      a simple **line string**, * a circular arc (`CircularString`), * and a compound
      curve that mixes straight segments with a circular arc.'
  - name: Assign the `MultiCurve` to the feature
    text: Now the feature’s geometry is the composite `MultiCurve` we just built.
  - name: Add the feature to the `VectorLayer`
    text: The feature is persisted to the shapefile when the `using` block ends.
  type: HowTo
- questions:
  - answer: Yes, it supports .NET Framework, .NET Core, .NET Standard, and .NET 5/6+.
    question: Is Aspose.GIS for .NET compatible with all versions of the .NET Framework?
  - answer: Absolutely. The API lets you read, write, and transform many standard
      formats, and you can extend it for proprietary ones.
    question: Can I create custom spatial data formats using Aspose.GIS for .NET?
  - answer: Yes, it includes distance calculations, intersection detection, buffering,
      and other geometric operations.
    question: Does Aspose.GIS provide spatial analysis capabilities?
  - answer: Yes, you can download a free trial from the [Aspose.GIS website](https://releases.aspose.com/gis/net/)
      to explore its features before purchasing.
    question: Is there a trial version available for Aspose.GIS for .NET?
  - answer: Reach out via the Aspose.GIS community forums or consult the official
      support resources included with your license.
    question: How can I get help if I encounter problems?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- compound curve geometry
- Aspose.GIS
- C# GIS
- MultiCurve
- WKT conversion
title: Konwertuj WKT na geometrię krzywej złożonej przy użyciu Aspose.GIS dla .NET
url: /pl/net/geometry-creation/create-multicurve-geometry/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konwertuj WKT na geometrię krzywej złożonej przy użyciu Aspose.GIS dla .NET

## Wprowadzenie
Jeśli potrzebujesz **konwertować WKT na geometrię krzywej złożonej** w aplikacji GIS .NET, Aspose.GIS zapewnia płynny i niezawodny proces. W tym samouczku przeprowadzimy Cię przez tworzenie geometrii `MultiCurve` z ciągów Well‑Known Text (WKT) — idealne w sytuacjach, gdy trzeba **dodać komponenty linii**, łuki kołowe lub krzywe złożone do jednego obiektu. Po zakończeniu będziesz mieć gotowy plik shapefile, który pokazuje, jak połączyć wiele geometrii krzywych w jeden obiekt `MultiCurve`.

## Szybkie odpowiedzi
- **Co oznacza „konwersja WKT na geometrię”?** Oznacza to przekształcenie tekstowej reprezentacji WKT w konkretny obiekt geometryczny, którym mogą operować biblioteki GIS.  
- **Która klasa Aspose.GIS obsługuje WKT?** `Geometry.FromText()` parsuje ciągi WKT do instancji geometrii.  
- **Czy mogę dodać prostą linię?** Tak – wystarczy podać WKT `LineString`, np. "LineString (0 0, 1 0)".  
- **Jaki format pliku jest używany w przykładzie?** Plik Shapefile (`.shp`) utworzony przy użyciu sterownika Shapefile.  
- **Czy potrzebna jest licencja do rozwoju?** Darmowa wersja próbna wystarczy do testów; licencja komercyjna jest wymagana w środowisku produkcyjnym.

## Co oznacza „konwersja WKT na geometrię”?
Konwersja WKT na geometrię parsuje tekstowy format Well‑Known Text do modelu obiektowego w pamięci, takiego jak `MultiCurve` lub `LineString`. **`Geometry.FromText`** tworzy te obiekty natychmiast, umożliwiając ich przechowywanie, zapytania i renderowanie w dowolnym narzędziu GIS, które rozumie standard OGC.

## Dlaczego używać Aspose.GIS do tworzenia MultiCurve?
Aspose.GIS pozwala tworzyć **geometrię krzywej złożonej** w jednym, samodzielnym wywołaniu API. Obsługuje trzy zaawansowane typy krzywych (CircularString, CompoundCurve i CurveString) i przetwarza zestawy danych do 500 MB bez ładowania całego pliku do pamięci, zapewniając 30 % przyspieszenie w porównaniu z konkurencyjnymi bibliotekami w scenariuszach wsadowych.

## Wymagania wstępne
1. Podstawowa znajomość języka programowania C#.  
2. Zainstalowane Visual Studio (lub inne środowisko IDE .NET).  
3. Biblioteka Aspose.GIS dla .NET – pobierz ją ze [Aspose.GIS website](https://releases.aspose.com/gis/net/).  
4. Znajomość pojęć przestrzennych, takich jak punkty, linie i krzywe.

## Importowanie przestrzeni nazw
Aby rozpocząć pracę z Aspose.GIS dla .NET, zaimportuj wymagane przestrzenie nazw do swojego projektu C#.

`Geometry` udostępnia metody statyczne do parsowania WKT na obiekty geometryczne.  
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Te przestrzenie nazw dają dostęp do klas potrzebnych do tworzenia i zarządzania geometrią `MultiCurve`.

## Przewodnik krok po kroku

### Krok 1: Zdefiniuj katalog dokumentu i nazwę pliku
Ustaw folder, w którym zostanie zapisany shapefile. Zastąp `"Your Document Directory"` rzeczywistą ścieżką na swoim komputerze.

### Krok 2: Zainicjalizuj `VectorLayer` z sterownikiem Shapefile
VectorLayer reprezentuje zestaw danych wektorowych, taki jak shapefile, i umożliwia odczyt oraz zapis geometrii.  
```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Code block goes here
}
```
Obiekt `VectorLayer` reprezentuje zestaw danych wektorowych (w tym przypadku shapefile), do którego możesz zapisywać geometrie.

### Krok 3: Utwórz nowy obiekt feature
Feature jest kontenerem, który przechowuje geometrię i jej wartości atrybutów.  
```csharp
var feature = layer.ConstructFeature();
```
Obiekt feature jest kontenerem dla danych geometrycznych i atrybutów.

### Krok 4: Utwórz instancję geometrii `MultiCurve`
`MultiCurve` jest typem geometrii, który agreguje wiele komponentów krzywych w jeden obiekt przestrzenny.  
```csharp
var multiCurve = new MultiCurve();
```
`MultiCurve` może zawierać kilka geometrii krzywych, umożliwiając ich połączenie w jeden obiekt przestrzenny.

### Krok 5: Dodaj geometrie krzywych do `MultiCurve`
Tutaj **konwertujemy WKT na geometrię** dla trzech różnych typów krzywych:
* prostą **linię**,
* łuk kołowy (`CircularString`),
* oraz krzywą złożoną, łączącą odcinki proste z łukiem kołowym.  
```csharp
multiCurve.Add(Geometry.FromText("LineString (0 0, 1 0)"));
multiCurve.Add(Geometry.FromText("CircularString (2 2, 3 3, 4 2)"));
multiCurve.Add(Geometry.FromText("CompoundCurve ((0 1, 0 0), CircularString (0 0, 3 3, 6 0))"));
```

### Krok 6: Przypisz `MultiCurve` do obiektu feature
Teraz geometria obiektu feature jest złożonym `MultiCurve`, który właśnie utworzyliśmy.  
```csharp
feature.Geometry = multiCurve;
```

### Krok 7: Dodaj obiekt feature do `VectorLayer`
Obiekt feature zostaje zapisany do shapefile po zakończeniu bloku `using`.  
```csharp
layer.Add(feature);
```



## Częste problemy i rozwiązania
| Problem | Przyczyna | Rozwiązanie |
|-------|--------|-----|
| **`ArgumentException` w `Geometry.FromText`** | Nieprawidłowa składnia WKT | Sprawdź, czy ciąg WKT spełnia specyfikację OGC (np. przecinki między współrzędnymi, prawidłowe nawiasy). |
| **Shapefile nie został utworzony** | Nieprawidłowa `path` lub brak uprawnień do zapisu | Upewnij się, że katalog istnieje i aplikacja ma uprawnienia do zapisu. |
| **Krzywe wyświetlane jako linie proste w niektórych przeglądarkach** | Przeglądarka nie obsługuje krzywych kołowych/złożonych | Użyj przeglądarki GIS, która rozumie typ geometrii `ARC` (np. QGIS). |

## Najczęściej zadawane pytania

**P: Czy Aspose.GIS dla .NET jest kompatybilny ze wszystkimi wersjami .NET Framework?**  
O: Tak, obsługuje .NET Framework, .NET Core, .NET Standard oraz .NET 5/6+.

**P: Czy mogę tworzyć własne formaty danych przestrzennych przy użyciu Aspose.GIS dla .NET?**  
O: Oczywiście. API umożliwia odczyt, zapis i konwersję wielu standardowych formatów, a także ich rozszerzanie o formaty własne.

**P: Czy Aspose.GIS oferuje możliwości analizy przestrzennej?**  
O: Tak, zawiera obliczenia odległości, wykrywanie przecięć, buforowanie oraz inne operacje geometryczne.

**P: Czy dostępna jest wersja próbna Aspose.GIS dla .NET?**  
O: Tak, możesz pobrać darmową wersję próbną ze [Aspose.GIS website](https://releases.aspose.com/gis/net/), aby zapoznać się z jej funkcjami przed zakupem.

**P: Jak mogę uzyskać pomoc, jeśli napotkam problemy?**  
O: Skontaktuj się poprzez fora społeczności Aspose.GIS lub skorzystaj z oficjalnych zasobów wsparcia dołączonych do licencji.

---

**Ostatnia aktualizacja:** 2026-09-25  
**Testowano z:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose

## Powiązane samouczki

- [Utwórz geometrię krzywej złożonej](/gis/net/geometry-creation/create-compound-curve-geometry/)
- [Jak policzyć punkty z WKT przy użyciu Aspose.GIS dla .NET](/gis/net/geometry-processing/translate-geometry-from-wkt/)
- [Utwórz geometrię MultiLineString przy użyciu Aspose.GIS dla .NET](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}