---
date: 2026-08-24
description: Dowiedz się, jak tworzyć geometrię linii zakrzywionej i dodawać krzywe
  przy użyciu Aspose.GIS dla .NET, umożliwiając precyzyjne przetwarzanie danych geoprzestrzennych.
keywords:
- create curved line
- how to add curves
- create compound curve
- circular arc geometry
lastmod: 2026-08-24
linktitle: Jak dodać krzywe – geometria krzywych złożonych
og_description: Dowiedz się, jak tworzyć geometrię linii zakrzywionej przy użyciu
  Aspose.GIS dla .NET. Ten samouczek pokazuje krok po kroku, jak dodawać krzywe i
  budować krzywe złożone w ciągu kilku minut.
og_image_alt: Screenshot of Aspose.GIS creating a compound curved line geometry in
  a .NET project
og_title: Jak tworzyć geometrię linii zakrzywionej przy użyciu Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to create curved line geometry and add curves using Aspose.GIS
    for .NET, enabling precise geospatial data processing.
  headline: How to create curved line geometry with Aspose.GIS
  type: TechArticle
- description: Learn how to create curved line geometry and add curves using Aspose.GIS
    for .NET, enabling precise geospatial data processing.
  name: How to create curved line geometry with Aspose.GIS
  steps:
  - name: define the output path
    text: First, specify where the resulting Shapefile will be saved. Replace the
      placeholder with a valid folder on your machine.
  - name: create a vector layer
    text: '`VectorLayer` represents a spatial layer that holds features and their
      geometries within a GIS dataset. The `using` block ensures the file is closed
      properly after writing.'
  - name: construct the compound curve feature
    text: The `CompoundCurve` class is Aspose.GIS's top‑level object for a geometry
      that consists of multiple connected curve parts. Here we instantiate an empty
      compound curve that will later receive individual components.
  - name: define component curves
    text: 'We prepare five pieces—two straight `LineString`s, two `CircularString`
      arcs, and a final `LineString`. `LineString` represents a simple straight line
      defined by an ordered list of points. `CircularString` is Aspose.GIS’s representation
      of a circular arc defined by three points (start, middle, end) '
  - name: add component curves to the compound curve
    text: Each component is appended in order, preserving continuity and orientation.
      The `Add` method automatically validates that the end point of one segment matches
      the start point of the next.
  - name: assign geometry to the feature
    text: Now the assembled `CompoundCurve` becomes the geometry of the feature we
      will store in the layer.
  - name: add the feature to the layer
    text: Finally, we write the feature into the Shapefile. When the `using` block
      ends, the file is closed and ready for use in any GIS application.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS works with .NET Framework, .NET Core, and .NET Standard,
      covering versions from 4.6 up to .NET 7.
    question: Can I use Aspose.GIS for .NET with other .NET frameworks?
  - answer: Absolutely. It reads and writes Shapefile, GeoJSON, KML, GML, and more
      than 30 additional formats.
    question: Does Aspose.GIS support reading and writing different geospatial file
      formats?
  - answer: Yes, the library can be used in desktop, web, and cloud services without
      any platform‑specific dependencies.
    question: Is Aspose.GIS suitable for both desktop and web applications?
  - answer: Yes, you can calculate distances, execute geometric operations, and run
      spatial queries directly on the geometries.
    question: Can I perform spatial analysis with Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) to ask
      questions and share ideas with other developers.
    question: Where can I get community help for Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- GIS geometry
- Aspose.GIS
- .NET geospatial
- compound curve
title: Jak tworzyć geometrię linii zakrzywionej przy użyciu Aspose.GIS
url: /pl/net/geometry-creation/create-compound-curve-geometry/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć geometrię linii zakrzywionej przy użyciu Aspose.GIS

## Wprowadzenie
W tym przewodniku odkryjesz **jak utworzyć geometrię linii zakrzywionej** przy użyciu Aspose.GIS dla .NET. Niezależnie od tego, czy tworzysz interaktywne mapy, przeprowadzasz analizy przestrzenne, czy generujesz zestawy danych GIS, opanowanie umiejętności dodawania krzywych pozwala modelować rzeczywiste obiekty — takie jak kręte drogi czy meandrujące rzeki — z wysoką precyzją. Samouczek przeprowadzi Cię przez każdy krok, od konfiguracji projektu po eksportowanie wielokrotnego użycia geometrii krzywej złożonej.

## Szybkie odpowiedzi
- **Jaki jest główny cel?** Zbudować geometrię krzywej złożonej, łączącą proste linie i łuki kołowe.  
- **Która biblioteka jest używana?** Aspose.GIS for .NET.  
- **Wymagania wstępne?** Visual Studio, zainstalowany Aspose.GIS oraz projekt C# targetujący .NET 6 lub nowszy.  
- **Typowy czas implementacji?** Około 10‑15 minut dla działającego przykładu.  
- **Obsługiwany format wyjściowy?** Shapefile (ten sam kod zapisuje także GeoJSON, KML i inne formaty).

## Czym jest krzywa złożona?
Krzywa złożona to pojedyncza geometria składająca się z wielu połączonych komponentów krzywych — prostych `LineString` i łuków kołowych — połączonych w bardziej złożony kształt. Jest idealna, gdy pojedyncza prosta linia nie może dokładnie przedstawić ścieżki, takiej jak autostrada z płynnymi zakrętami lub rzeka podążająca naturalnym łukiem.

## Dlaczego używać Aspose.GIS do dodawania krzywych?
Aspose.GIS zapewnia **bogate API geometrii**, które natywnie obsługuje linie, ciągi kołowe i krzywe złożone, eliminując potrzebę zewnętrznych bibliotek GIS. Biblioteka jest **cross‑platform**, działa z .NET Framework 4.6+, .NET Core 2.0+, oraz .NET 5/6/7+. **Przetwarza do 500‑stronicowych zestawów danych wektorowych bez ładowania całego pliku do pamięci**, zapewniając szybkie i pamięcio‑oszczędne operacje. Eksport jest prosty: możesz zapisywać bezpośrednio do Shapefile, GeoJSON, KML, GML i ponad 30 innych formatów.

## Dlaczego to ma znaczenie
Dodawanie krzywych pozwala modelować rzeczywiste obiekty dokładniej, co poprawia jakość wizualną renderowanych map i zwiększa precyzję analiz przestrzennych, takich jak wyszukiwania w pobliżu czy wyznaczanie tras w sieciach. Opanowanie **jak utworzyć geometrię linii zakrzywionej** podnosi wiarygodność każdej rozwiązania .NET opartego na GIS.

## Typowe przypadki użycia
- **Sieci transportowe:** Modelowanie autostrad, linii kolejowych lub ścieżek rowerowych z płynnymi zakrętami.  
- **Hydrologia:** Przedstawianie koryt rzek, które podążają za naturalnymi łukami.  
- **Planowanie urbanistyczne:** Rysowanie granic nieruchomości zawierających odcinki zakrzywione.  
- **Niestandardowe symbole:** Tworzenie dekoracyjnych lub schematycznych kształtów dla legend map.

## Wymagania wstępne
- Visual Studio (dowolna aktualna edycja).  
- Aspose.GIS for .NET pobrany ze [strony pobierania](https://releases.aspose.com/gis/net/).  
- Projekt C# targetujący .NET 6 (lub dowolną obsługiwaną wersję).

## Importowanie przestrzeni nazw
Dyrektywy `using` wprowadzają wymagane typy Aspose.GIS do zakresu.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Przewodnik krok po kroku tworzenia geometrii krzywej złożonej

### Krok 1: określ ścieżkę wyjściową
Najpierw określ, gdzie zostanie zapisany wynikowy Shapefile. Zastąp symbol zastępczy prawidłowym folderem na swoim komputerze.

```csharp
string path = "Your Document Directory" + "CreateCompoundCurve_out.shp";
```

### Krok 2: utwórz warstwę wektorową
`VectorLayer` reprezentuje warstwę przestrzenną, która przechowuje obiekty i ich geometrie w zestawie danych GIS. Blok `using` zapewnia prawidłowe zamknięcie pliku po zapisaniu.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Code block for creating the compound curve geometry will be inserted here.
}
```

### Krok 3: skonstruuj obiekt krzywej złożonej
Klasa `CompoundCurve` jest głównym obiektem Aspose.GIS dla geometrii składającej się z wielu połączonych części krzywych. Tutaj tworzymy pustą krzywą złożoną, która później otrzyma poszczególne komponenty.

```csharp
var feature = layer.ConstructFeature();
var compoundCurve = new CompoundCurve();
```

### Krok 4: zdefiniuj krzywe składowe
Przygotowujemy pięć elementów — dwa proste `LineString`, dwa łuki `CircularString` oraz końcowy `LineString`. `LineString` reprezentuje prostą linię zdefiniowaną uporządkowaną listą punktów. `CircularString` jest reprezentacją łuku kołowego w Aspose.GIS, definiowaną przez trzy punkty (początek, środek, koniec) leżące na tej samej okręgu.

```csharp
var bottom = (ILineString)Geometry.FromText("LineString (0 0, 3 0)");
var firstArc = (ICircularString)Geometry.FromText("CircularString (3 0, 4 1, 3 2)");
var middle = (ILineString)Geometry.FromText("LineString (3 2, 1 2)");
var secondArc = (ICircularString)Geometry.FromText("CircularString (1 2, 0 3, 1 4)");
var top = (ILineString)Geometry.FromText("LineString (1 4, 4 4)");
```

### Krok 5: dodaj krzywe składowe do krzywej złożonej
Każdy komponent jest dodawany w kolejności, zachowując ciągłość i orientację. Metoda `Add` automatycznie weryfikuje, czy punkt końcowy jednego segmentu pasuje do punktu początkowego kolejnego.

```csharp
compoundCurve.AddCurve(bottom);
compoundCurve.AddCurve(firstArc);
compoundCurve.AddCurve(middle);
compoundCurve.AddCurve(secondArc);
compoundCurve.AddCurve(top);
```

### Krok 6: przypisz geometrię do obiektu
Teraz zbudowana `CompoundCurve` staje się geometrią obiektu, który zostanie zapisany w warstwie.

```csharp
feature.Geometry = compoundCurve;
```

### Krok 7: dodaj obiekt do warstwy
Na koniec zapisujemy obiekt do Shapefile. Gdy blok `using` się kończy, plik jest zamykany i gotowy do użycia w dowolnej aplikacji GIS.

```csharp
layer.Add(feature);
```

## Typowe problemy i wskazówki
- **Kolejność współrzędnych:** Aspose.GIS oczekuje współrzędnych w kolejności `X Y` (długość, szerokość). Zamiana kolejności odwraca geometrię.  
- **Składnia CircularString:** Punkt środkowy musi leżeć na zamierzonym łuku; w przeciwnym razie krzywa zapada się w prostą linię.  
- **Nadpisywanie pliku:** `VectorLayer.Create` nadpisuje istniejący Shapefile bez ostrzeżenia — używaj unikalnej nazwy pliku podczas rozwoju.  
- **Wydajność:** Dla dużych zestawów danych, dodawaj funkcje partiami zamiast wstawiać je pojedynczo w bloku `using`.  
- **Porada pro:** Ponownie używaj tej samej instancji `CompoundCurve` przy tworzeniu wielu podobnych obiektów; wywołaj `compoundCurve.Clear()` przed ponownym wypełnieniem, aby zmniejszyć alokacje.

## Najczęściej zadawane pytania

**Q: Czy mogę używać Aspose.GIS for .NET z innymi frameworkami .NET?**  
A: Tak, Aspose.GIS działa z .NET Framework, .NET Core i .NET Standard, obejmując wersje od 4.6 do .NET 7.

**Q: Czy Aspose.GIS obsługuje odczyt i zapis różnych formatów plików geoprzestrzennych?**  
A: Absolutnie. Odczytuje i zapisuje Shapefile, GeoJSON, KML, GML oraz ponad 30 dodatkowych formatów.

**Q: Czy Aspose.GIS nadaje się zarówno do aplikacji desktopowych, jak i webowych?**  
A: Tak, biblioteka może być używana w aplikacjach desktopowych, webowych i usługach chmurowych bez zależności specyficznych dla platformy.

**Q: Czy mogę wykonywać analizy przestrzenne przy użyciu Aspose.GIS for .NET?**  
A: Tak, możesz obliczać odległości, wykonywać operacje geometryczne i uruchamiać zapytania przestrzenne bezpośrednio na geometriach.

**Q: Gdzie mogę uzyskać pomoc społeczności dla Aspose.GIS?**  
A: Odwiedź [forum Aspose.GIS](https://forum.aspose.com/c/gis/33), aby zadawać pytania i dzielić się pomysłami z innymi programistami.

---

**Ostatnia aktualizacja:** 2026-08-24  
**Testowano z:** Aspose.GIS for .NET (latest stable release)  
**Autor:** Aspose

## Powiązane samouczki

- [Utwórz warstwę wektorową i Circular String w Aspose.GIS dla .NET](/gis/net/geometry-creation/create-circular-string-geometry/)
- [Utwórz warstwę wektorową i krzywą wielokątową z Aspose.GIS](/gis/net/geometry-creation/create-curve-polygon-geometry/)
- [Konwertuj WKT na Geometrię: MultiCurve z Aspose.GIS .NET](/gis/net/geometry-creation/create-multicurve-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}