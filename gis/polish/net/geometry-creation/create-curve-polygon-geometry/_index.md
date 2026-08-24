---
date: 2026-08-24
description: Dowiedz się, jak utworzyć warstwę wektorową i curve polygon geometry
  przy użyciu Aspose.GIS dla .NET, w tym circular string geometry dla interior rings.
keywords:
- create vector layer
- define curved polygon
- Aspose.GIS curve polygon
- .NET GIS development
lastmod: 2026-08-24
linktitle: Utwórz Curve Polygon Geometry
og_description: Utwórz warstwę wektorową i curve polygon geometry przy użyciu Aspose.GIS
  dla .NET. Dowiedz się krok po kroku, jak w kilka minut wygenerować Shapefile z zakrzywionymi
  krawędziami.
og_image_alt: Screenshot showing a curve polygon Shapefile created with Aspose.GIS
  in a GIS viewer
og_title: Utwórz warstwę wektorową i curve polygon z Aspose.GIS dla .NET
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to create vector layer and curve polygon geometry using Aspose.GIS
    for .NET, including circular string geometry for interior rings.
  headline: Create vector layer and curve polygon with Aspose.GIS
  type: TechArticle
- description: Learn how to create vector layer and curve polygon geometry using Aspose.GIS
    for .NET, including circular string geometry for interior rings.
  name: Create vector layer and curve polygon with Aspose.GIS
  steps:
  - name: define the file path
    text: First, specify where the generated Curve Polygon Shapefile will be saved.
      **Definition anchor:** `string shapefilePath = "...";` holds the absolute or
      relative path to the Shapefile that will be created on disk. Replace `"Your
      Document Directory"` with the actual folder path on your machine.
  - name: create a vector layer
    text: 'Instantiate a new vector layer using the Shapefile driver. This is the
      **create vector layer** step that prepares the container for our geometry. **Definition
      anchor:** `VectorLayer layer = new VectorLayer(shapefilePath, Drivers.Shapefile);`
      creates a writable layer tied to a Shapefile data source. '
  - name: construct a feature
    text: Create a feature object that will hold the geometry and any attribute data.
      **Definition anchor:** `Feature feature = layer.ConstructFeature();` builds
      an empty feature ready to receive geometry and attribute values.
  - name: create curve polygon geometry
    text: Now we’ll create an empty `CurvePolygon` object. **Definition anchor:**
      `CurvePolygon curvePolygon = new CurvePolygon();` represents a polygon whose
      rings may consist of straight segments or circular strings.
  - name: define the exterior ring
    text: Add a circular string that forms the outer boundary of the polygon. **Definition
      anchor:** `CircularString exterior = new CircularString();` stores a sequence
      of points that define one or more circular arcs. The coordinates above produce
      a torus‑like shape.
  - name: define an interior ring (optional)
    text: 'If you need a hole inside the polygon, define it as another circular string.
      This demonstrates how to add an **interior ring polygon** using **circular string
      geometry**. **Definition anchor:** `CircularString interior = new CircularString();`
      creates the inner ring that will be subtracted from the '
  - name: assign geometry to the feature
    text: Link the curve polygon to the feature you created earlier. **Definition
      anchor:** `feature.Geometry = curvePolygon;` attaches the fully built geometry
      to the feature, making it ready for persistence.
  - name: add the feature to the layer
    text: Finally, add the feature to the vector layer so it becomes part of the dataset.
      **Definition anchor:** `layer.Add(feature);` writes the feature into the Shapefile;
      the `using` block will flush the data to disk when it ends. When the `using`
      block ends, the Shapefile is written to disk.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS for .NET supports interoperability with many popular GIS
      formats, allowing seamless data exchange with GDAL/OGR, Proj.NET, and other
      .NET GIS toolkits.
    question: Is Aspose.GIS for .NET compatible with other GIS libraries?
  - answer: Absolutely. The Shapefile produced can be opened in QGIS, ArcGIS, or any
      GIS tool that reads the Shapefile format and supports circular strings.
    question: Can I visualize the generated curve polygon geometry in GIS software?
  - answer: Yes, it includes spatial querying, buffering, intersection, and other
      analysis functions, enabling advanced geoprocessing directly in .NET.
    question: Does Aspose.GIS for .NET provide spatial analysis capabilities?
  - answer: Join the Aspose.GIS community forum [Aspose.GIS community forum](https://forum.aspose.com/c/gis/33)
      to connect with other developers.
    question: Where can I ask for help or discuss ideas with other users?
  - answer: Of course! You can download a free trial from the [Aspose.GIS free trial
      downloads](https://releases.aspose.com/) and evaluate all features.
    question: Is a free trial available before purchasing?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- create vector layer
- Aspose.GIS
- curve polygon
- .NET GIS
- C# shapefile
title: Utwórz warstwę wektorową i curve polygon z Aspose.GIS
url: /pl/net/geometry-creation/create-curve-polygon-geometry/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz warstwę wektorową i krzywą wielokąt z Aspose.GIS

## Wprowadzenie
W dziedzinie rozwoju Systemów Informacji Geograficznej (GIS) **Aspose.GIS for .NET** wyróżnia się jako potężna biblioteka do tworzenia, edytowania i manipulacji danymi przestrzennymi. W tym samouczku nauczysz się, jak **create vector layer** i **create curve polygon** krok po kroku, aby móc osadzać zaawansowane kształty bezpośrednio w swoich aplikacjach GIS. Po zakończeniu przewodnika będziesz mieć gotowy do użycia plik Shapefile zawierający krzywą wielokąt z zarówno zewnętrznymi, jak i wewnętrznymi pierścieniami.

## Szybkie odpowiedzi
- **Jaka biblioteka jest używana?** Aspose.GIS for .NET.  
- **Główne zadanie?** Utwórz geometrię curve polygon, zapisz ją jako Shapefile i **create vector layer** dla danych.  
- **Typowy czas implementacji?** 5–10 minut dla podstawowego kształtu.  
- **Wymagania wstępne?** Środowisko programistyczne .NET oraz pakiet NuGet Aspose.GIS.  
- **Czy mogę zobaczyć wynik?** Tak – dowolny przeglądarka GIS obsługująca Shapefile (np. QGIS, ArcGIS).

## Czym jest curve polygon?
Curve polygon to wielokąt, którego krawędzie mogą zawierać odcinki krzywych, takie jak łuki kołowe, umożliwiając płynne, realistyczne granice. Ten typ geometrii jest szczególnie przydatny do modelowania naturalnych cech, takich jak jeziora, wyspy czy zakrzywione korytarze drogowe.

## Dlaczego tworzyć geometrię curve polygon przy użyciu Aspose.GIS?
Aspose.GIS może przechowywać krzywe krawędzie w sposób matematyczny, zachowując dokładną geometrię przy jednoczesnej kompatybilności ze specyfikacją Shapefile. Biblioteka obsługuje **30+ vector formats** i może przetwarzać pliki do **2 GB** bez ładowania całego zestawu danych do pamięci, zapewniając wysoką wydajność obsługi dużych projektów przestrzennych.

## Wymagania wstępne
Zanim zanurzysz się w temat, upewnij się, że masz następujące:

1. **Aspose.GIS for .NET** zainstalowany. Pobierz go ze [strony wydania Aspose.GIS for .NET](https://releases.aspose.com/gis/net/).  
2. Praktyczna znajomość C# i ekosystemu .NET.  
3. IDE, takie jak Visual Studio (dowolna nowsza wersja) lub Visual Studio Code.

## Importuj przestrzenie nazw
Dyrektywy `using` poniżej wprowadzają podstawowe klasy GIS do zakresu.

**Definition anchor:** `using Aspose.Gis;` importuje główną przestrzeń nazw GIS, która zawiera klasy `VectorLayer`, `Feature` oraz klasy geometrii potrzebne w tym samouczku.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Przewodnik krok po kroku

### Krok 1: określ ścieżkę pliku
Najpierw określ, gdzie zostanie zapisany wygenerowany plik Shapefile z Curve Polygon.

**Definition anchor:** `string shapefilePath = "...";` przechowuje bezwzględną lub względną ścieżkę do pliku Shapefile, który zostanie utworzony na dysku.  

```csharp
string path = "Your Document Directory" + "CreateCurvePolygon_out.shp";
```

Zastąp "Your Document Directory" rzeczywistą ścieżką folderu na swoim komputerze.

### Krok 2: utwórz warstwę wektorową
Zainicjuj nową warstwę wektorową przy użyciu sterownika Shapefile. To jest krok **create vector layer**, który przygotowuje kontener dla naszej geometrii.

**Definition anchor:** `VectorLayer layer = new VectorLayer(shapefilePath, Drivers.Shapefile);` tworzy zapisywalną warstwę powiązaną ze źródłem danych Shapefile.  

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Your code for creating the Curve Polygon Geometry will go here
}
```

Instrukcja `using` zapewnia prawidłowe zwolnienie zasobów.

### Krok 3: skonstruuj obiekt feature
Utwórz obiekt feature, który będzie przechowywał geometrię oraz ewentualne dane atrybutowe.

**Definition anchor:** `Feature feature = layer.ConstructFeature();` buduje pusty obiekt feature gotowy do przyjęcia geometrii i wartości atrybutów.  

```csharp
var feature = layer.ConstructFeature();
```

### Krok 4: utwórz geometrię curve polygon
Teraz utworzymy pusty obiekt `CurvePolygon`.

**Definition anchor:** `CurvePolygon curvePolygon = new CurvePolygon();` reprezentuje wielokąt, którego pierścienie mogą składać się z odcinków prostych lub łańcuchów kołowych.  

```csharp
var curvePolygon = new CurvePolygon();
```

### Krok 5: zdefiniuj pierścień zewnętrzny
Dodaj łańcuch kołowy, który tworzy zewnętrzną granicę wielokąta.

**Definition anchor:** `CircularString exterior = new CircularString();` przechowuje sekwencję punktów definiujących jedną lub więcej łuków kołowych.  

```csharp
var exterior = new CircularString();
exterior.AddPoint(-2, 0);
exterior.AddPoint(0, 2);
exterior.AddPoint(2, 0);
exterior.AddPoint(0, -2);
exterior.AddPoint(-2, 0);
curvePolygon.ExteriorRing = exterior;
```

Powyższe współrzędne tworzą kształt przypominający torus.

### Krok 6: zdefiniuj pierścień wewnętrzny (opcjonalnie)
Jeśli potrzebujesz otworu wewnątrz wielokąta, zdefiniuj go jako kolejny łańcuch kołowy. To pokazuje, jak dodać **interior ring polygon** przy użyciu **circular string geometry**.

**Definition anchor:** `CircularString interior = new CircularString();` tworzy wewnętrzny pierścień, który zostanie odjęty od obszaru zewnętrznego.  

```csharp
var interior = new CircularString();
interior.AddPoint(-1, 0);
interior.AddPoint(0, 1);
interior.AddPoint(1, 0);
interior.AddPoint(0, -1);
interior.AddPoint(-1, 0);
curvePolygon.AddInteriorRing(interior);
```

### Krok 7: przypisz geometrię do obiektu feature
Połącz curve polygon z wcześniej utworzonym obiektem feature.

**Definition anchor:** `feature.Geometry = curvePolygon;` dołącza w pełni zbudowaną geometrię do obiektu feature, przygotowując go do zapisania.  

```csharp
feature.Geometry = curvePolygon;
```

### Krok 8: dodaj obiekt feature do warstwy
Na koniec dodaj obiekt feature do warstwy wektorowej, aby stał się częścią zestawu danych.

**Definition anchor:** `layer.Add(feature);` zapisuje obiekt feature do pliku Shapefile; blok `using` wypisze dane na dysk po zakończeniu.  

```csharp
layer.Add(feature);
```

Gdy blok `using` się kończy, plik Shapefile zostaje zapisany na dysku.

## Typowe problemy i rozwiązania

| Problem | Dlaczego się dzieje | Rozwiązanie |
|-------|----------------|-----|
| **File not created** | Nieprawidłowa ścieżka lub brak uprawnień do zapisu | Sprawdź, czy katalog istnieje i aplikacja ma dostęp do zapisu. |
| **Curved edges appear as straight lines in some viewers** | Przeglądarka nie obsługuje łańcuchów kołowych | Użyj aplikacji GIS, która w pełni obsługuje specyfikację Shapefile (np. QGIS 3.28+). |
| **Exception `ArgumentException` on `AddPoint`** | Punkty znajdują się poza prawidłowym zakresem współrzędnych dla wybranego układu odniesienia (CRS) | Upewnij się, że współrzędne mieszczą się w układzie odniesienia, którego zamierzasz używać. |

## Najczęściej zadawane pytania

**Q: Czy Aspose.GIS for .NET jest kompatybilny z innymi bibliotekami GIS?**  
A: Tak, Aspose.GIS for .NET obsługuje interoperacyjność z wieloma popularnymi formatami GIS, umożliwiając płynną wymianę danych z GDAL/OGR, Proj.NET i innymi zestawami narzędzi GIS dla .NET.

**Q: Czy mogę zwizualizować wygenerowaną geometrię curve polygon w oprogramowaniu GIS?**  
A: Oczywiście. Utworzony plik Shapefile można otworzyć w QGIS, ArcGIS lub dowolnym narzędziu GIS, które odczytuje format Shapefile i obsługuje łańcuchy kołowe.

**Q: Czy Aspose.GIS for .NET zapewnia możliwości analizy przestrzennej?**  
A: Tak, zawiera zapytania przestrzenne, buforowanie, przecięcia i inne funkcje analizy, umożliwiając zaawansowane przetwarzanie geoprzestrzenne bezpośrednio w .NET.

**Q: Gdzie mogę poprosić o pomoc lub dyskutować pomysły z innymi użytkownikami?**  
A: Dołącz do forum społeczności Aspose.GIS [Aspose.GIS community forum](https://forum.aspose.com/c/gis/33), aby połączyć się z innymi programistami.

**Q: Czy dostępna jest darmowa wersja próbna przed zakupem?**  
A: Oczywiście! Możesz pobrać darmową wersję próbną z [Aspose.GIS free trial downloads](https://releases.aspose.com/) i ocenić wszystkie funkcje.

## Podsumowanie
Teraz nauczyłeś się, jak **create vector layer** i **create curve polygon** przy użyciu Aspose.GIS for .NET, zapisać to jako Shapefile oraz poznać typowe pułapki i FAQ. Śmiało eksperymentuj z różnymi zestawami współrzędnych, dodawaj dane atrybutowe lub integruj warstwę w większych przepływach pracy GIS.

---

**Ostatnia aktualizacja:** 2026-08-24  
**Testowano z:** Aspose.GIS for .NET 24.11  
**Autor:** Aspose

## Powiązane samouczki

- [Utwórz warstwę wektorową i Circular String w Aspose.GIS for .NET](/gis/net/geometry-creation/create-circular-string-geometry/)
- [Jak utworzyć warstwę wektorową z SRS przy użyciu Aspose.GIS for .NET](/gis/net/layer-management/create-vector-layer-with-srs/)
- [Utwórz wielokąt z otworem (Polygon with Hole) przy użyciu Aspose.GIS](/gis/net/geometry-creation/create-polygon-with-hole-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}