---
date: 2026-09-10
description: Dowiedz się, jak konwertować krzywe na linie (linearize geometry) przy
  użyciu Aspose.GIS for .NET, umożliwiając efektywne geospatial processing i analysis
  w Twoich aplikacjach .NET.
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS .NET
lastmod: 2026-09-10
linktitle: Linearize a Geometry
og_description: Konwertuj krzywe na linie (linearize geometry) przy użyciu Aspose.GIS
  for .NET. Dowiedz się step‑by‑step, jak simplify geometries dla szybszego rendering
  i szerszej compatibility.
og_image_alt: Guide showing how to linearize curved geometries to straight lines using
  Aspose.GIS in a .NET application
og_title: Konwertuj krzywe na linie przy użyciu Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  headline: How to Convert Curves to Lines with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  name: How to Convert Curves to Lines with Aspose.GIS for .NET
  steps:
  - name: Define the output path
    text: '`Path.Combine` builds a platform‑independent file path, handling Windows
      backslashes and Unix forward slashes automatically. Replace `"Your Document
      Directory"` with the folder where you want the KML file saved.'
  - name: Create a layer for the output file
    text: A *layer* groups geographic features of the same type. Here we instantiate
      a new KML layer that will store the linearized geometry.
  - name: Construct a new feature
    text: A *feature* represents a single geographic object (point, line, polygon,
      etc.). We’ll attach our linear geometry to this feature.
  - name: Define the original complex geometry
    text: '`Geometry.FromWkt` parses a Well‑Known Text (WKT) string into a geometry
      object. The sample WKT includes a `LineString`, a `CompoundCurve`, and a `CircularString`
      to showcase curve handling.'
  - name: Convert curves to lines
    text: '`ToLinearGeometry()` tessellates every curve in the source geometry into
      straight‑line segments, returning a new linear geometry that retains any Z‑coordinates.'
  - name: Assign the linear geometry to the feature
    text: The feature’s `Geometry` property now holds the simplified, linear version
      of the original shape.
  - name: Add the feature to the layer
    text: Adding the feature to the KML layer queues it for writing; when the `using`
      block ends, the layer flushes the data to the output file.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS works with .NET Core, enabling cross‑platform applications.
    question: Is Aspose.GIS for .NET compatible with .NET Core?
  - answer: Absolutely! The library supports KML, Shapefile, GeoJSON, and many more
      formats—over 30 in total.
    question: Can I work with different GIS file formats using Aspose.GIS for .NET?
  - answer: Yes, it provides a wide range of spatial functions, from buffering to
      spatial joins.
    question: Does Aspose.GIS offer spatial operations and analysis?
  - answer: Yes, you can download a free trial from the [Aspose.GIS website](https://releases.aspose.com/gis/net/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      and staff support.
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert curves to lines
- Aspose.GIS
- .NET GIS processing
title: Jak konwertować krzywe na linie przy użyciu Aspose.GIS for .NET
url: /pl/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konwertowanie krzywych na linie (liniaryzacja geometrii) z Aspose.GIS dla .NET

## Wprowadzenie
Jeśli potrzebujesz **konwertować krzywe na linie** do mapowania, analizy przestrzennej lub zadań wymiany danych, Aspose.GIS dla .NET zapewnia czysty, programowy sposób realizacji tego. W tym samouczku przeprowadzimy Cię przez kompletny, rzeczywisty przykład, który pokaże, jak wziąć złożoną geometrię — zawierającą krzywe i złożone kształty — i przekształcić ją w prostą reprezentację liniową, działającą w każdym systemie GIS.

## Szybkie odpowiedzi
- **Co oznacza „konwertować krzywe na linie”?** Przekształca zakrzywione geometrie w odcinki prostych linii.  
- **Dlaczego wybrać Aspose.GIS?** Biblioteka obsługuje ponad 30 formatów GIS i radzi sobie z konwersją geometrii bez zewnętrznych narzędzi.  
- **Czego potrzebuję wcześniej?** .NET Framework lub .NET Core, Visual Studio (lub dowolne IDE C#) oraz pakiet NuGet Aspose.GIS.  
- **Jak długo będzie działał przykład?** Mniej niż pięć minut po zainstalowaniu biblioteki.  
- **Czy mogę eksportować do innych formatów?** Oczywiście — zamień sterownik KML na Shapefile, GeoJSON itp.  
Możesz pobrać pełny zestaw produktów ze [strony Aspose](https://releases.aspose.com/).

## Co oznacza konwertowanie krzywych na linie?
Konwertowanie krzywych na linie (zwane także **liniaryzacją geometrii**) zastępuje każdy zakrzywiony odcinek serią krótkich prostych odcinków, tworząc *geometrię liniową*. Dzięki temu renderowanie jest nawet pięć razy szybsze, zmniejsza się zużycie pamięci i zapewnia, że dane mogą być używane przez starsze usługi GIS, które akceptują wyłącznie cechy liniowe.

## Dlaczego konwertować krzywe na linie?
Geometrie liniowe renderują i przetwarzają zapytania nawet **5× szybciej** niż ich zakrzywione odpowiedniki, a **ponad 30 platform GIS** akceptuje wyłącznie cechy liniowe. Uproszczenie geometrii zmniejsza również rozmiar pliku w podglądach internetowych i umożliwia algorytmy — takie jak analiza sieciowa czy grupowanie — które wymagają danych w postaci prostych linii.

## Jak liniaryzować geometrię?
Użyj metody `ToLinearGeometry()` udostępnionej przez Aspose.GIS. Automatycznie tesseluje każdą krzywą w geometrii na odcinki prostych linii, zachowując przy tym wartości Z, dzięki czemu otrzymujesz liniową aproksymację bez utraty danych wysokościowych. Możesz także określić tolerancję, aby kontrolować maksymalne odchylenie między oryginalną krzywą a wygenerowanymi odcinkami, co pozwala zrównoważyć dokładność i rozmiar pliku. Metoda działa zarówno dla geometrii 2‑D, jak i 3‑D.

## Prerequisites
Przed zanurzeniem się w kod, upewnij się, że masz:

1. **Aspose.GIS dla .NET** – pobierz go ze [strony Aspose.GIS](https://releases.aspose.com/gis/net/).  
2. **.NET Framework** (lub .NET Core) zainstalowany na Twoim komputerze deweloperskim.  
3. **Visual Studio** (lub dowolne IDE kompatybilne z C#) do pisania i uruchamiania przykładu.

## Importowanie przestrzeni nazw
Aby rozpocząć korzystanie z funkcjonalności Aspose.GIS, zaimportuj wymagane przestrzenie nazw.

### Podstawowe przestrzenie nazw Aspose.GIS
Przestrzeń nazw `Aspose.Gis` zawiera podstawowe klasy geometrii, sterowniki i narzędzia niezbędne do wszystkich operacji GIS.  
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Sterownik dla docelowego formatu
`Aspose.Gis.Drivers` udostępnia statyczne fabryki dla każdego obsługiwanego formatu pliku; `Drivers.Kml` tworzy zapisujący KML.  
```csharp
using Aspose.GIS.Kml;
```

## Przewodnik krok po kroku konwertowania krzywych na linie
Poniżej znajduje się szczegółowy opis każdego wiersza kodu, wyjaśniający **jak konwertować krzywe na linie** i dlaczego każdy krok ma znaczenie.

### Krok 1: Zdefiniuj ścieżkę wyjściową
`Path.Combine` tworzy platformowo‑niezależną ścieżkę pliku, automatycznie obsługując ukośniki wsteczne Windows i ukośniki zwykłe Unix.  
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
Zastąp `"Your Document Directory"` folderem, w którym chcesz zapisać plik KML.

### Krok 2: Utwórz warstwę dla pliku wyjściowego
*Warstwa* grupuje cechy geograficzne tego samego typu. Tutaj tworzymy nową warstwę KML, która będzie przechowywać liniaryzowaną geometrię.  
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```

### Krok 3: Utwórz nowy obiekt (feature)
*Obiekt* (feature) reprezentuje pojedynczy element geograficzny (punkt, linia, wielokąt itp.). Dołączymy naszą liniową geometrię do tego obiektu.  
```csharp
var feature = layer.ConstructFeature();
```

### Krok 4: Zdefiniuj pierwotną złożoną geometrię
`Geometry.FromWkt` parsuje ciąg znaków Well‑Known Text (WKT) do obiektu geometrii. Przykładowy WKT zawiera `LineString`, `CompoundCurve` i `CircularString`, aby zaprezentować obsługę krzywych.  
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```

### Krok 5: Konwertuj krzywe na linie
`ToLinearGeometry()` tesseluje każdą krzywą w źródłowej geometrii na odcinki prostych linii, zwracając nową geometrię liniową zachowującą współrzędne Z.  
```csharp
var linear = geometry.ToLinearGeometry();
```

### Krok 6: Przypisz liniową geometrię do obiektu
Właściwość `Geometry` obiektu teraz przechowuje uproszczoną, liniową wersję pierwotnego kształtu.  
```csharp
feature.Geometry = linear;
```

### Krok 7: Dodaj obiekt do warstwy
Dodanie obiektu do warstwy KML umieszcza go w kolejce do zapisu; po zakończeniu bloku `using` warstwa zapisuje dane do pliku wyjściowego.  
```csharp
layer.Add(feature);
```

## Częste pułapki i wskazówki profesjonalne
- **Separatory ścieżek:** Używaj `Path.Combine`, aby uniknąć problemów w Windows i Linux.  
- **Bardzo duże geometrie:** Liniaryzacja skomplikowanych kształtów może wygenerować tysiące wierzchołków; rozważ wywołanie `Simplify()` po liniaryzacji, aby zmniejszyć liczbę punktów.  
- **Wybór sterownika:** Jeśli potrzebujesz innego formatu wyjściowego, zamień `Drivers.Kml` na `Drivers.Shapefile`, `Drivers.GeoJson` itp., i odpowiednio zmień rozszerzenie pliku.  
- **Zachowanie wartości Z:** `ToLinearGeometry()` zachowuje współrzędne 3‑D (Z), więc nie tracisz danych wysokościowych.

## Najczęściej zadawane pytania (FAQ)

**Q: Czy Aspose.GIS dla .NET jest kompatybilny z .NET Core?**  
A: Tak, Aspose.GIS działa z .NET Core, umożliwiając aplikacje wieloplatformowe.

**Q: Czy mogę pracować z różnymi formatami plików GIS używając Aspose.GIS dla .NET?**  
A: Oczywiście! Biblioteka obsługuje KML, Shapefile, GeoJSON i wiele innych formatów — ponad 30 łącznie.

**Q: Czy Aspose.GIS oferuje operacje i analizy przestrzenne?**  
A: Tak, zapewnia szeroki zakres funkcji przestrzennych, od buforowania po łączenia przestrzenne.

**Q: Czy dostępna jest darmowa wersja próbna?**  
A: Tak, możesz pobrać darmową wersję próbną ze [strony Aspose.GIS](https://releases.aspose.com/gis/net/).

**Q: Gdzie mogę uzyskać pomoc w razie problemów?**  
A: Odwiedź [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) w celu uzyskania wsparcia od społeczności i zespołu.

### Dodatkowe często zadawane pytania

**Q: Czy mogę liniaryzować geometrie zawierające współrzędne 3D (Z)?**  
A: Tak, `ToLinearGeometry()` działa zarówno z geometriami 2D, jak i 3D; wartości Z są zachowywane.

**Q: Jak liniaryzacja wpływa na rozmiar pliku?**  
A: Konwertowanie krzywych na wiele krótkich odcinków może zwiększyć rozmiar pliku; uruchom `Simplify()` po liniaryzacji, jeśli rozmiar jest problemem.

**Q: Czy mogę kontrolować długość odcinków przy konwertowaniu krzywych na linie?**  
A: Domyślna metoda używa wewnętrznej tolerancji. Aby uzyskać własną segmentację, możesz ręcznie tesselować krzywe przed wywołaniem `ToLinearGeometry()`.

## Zakończenie
W tym samouczku omówiliśmy **jak konwertować krzywe na linie** (liniaryzacja geometrii) przy użyciu Aspose.GIS dla .NET, od konfiguracji środowiska po zapisanie wyniku liniaryzacji do pliku KML. Teraz możesz wbudować ten przepływ pracy w aplikacje mapujące, potoki przetwarzania danych lub dowolny projekt związany z GIS, który wymaga uproszczonych geometrii.

---

**Ostatnia aktualizacja:** 2026-09-10  
**Testowano z:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose

## Powiązane samouczki

- [Jak utworzyć GeoJSON z tolerancją przy użyciu Aspose.GIS dla .NET](/gis/net/geometry-processing/set-linearization-tolerance/)
- [Konwertowanie wielokąta na linię przy użyciu Aspose.GIS dla .NET](/gis/net/geometry-processing/replace-polygons-with-lines/)
- [Jak utworzyć geometrię LineString przy użyciu Aspose.GIS dla .NET](/gis/net/geometry-creation/create-linestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}