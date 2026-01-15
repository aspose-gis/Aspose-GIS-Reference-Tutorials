---
date: 2026-01-15
description: Dowiedz się, jak etykietować elementy mapy przy użyciu Aspose.GIS dla
  .NET, z niestandardowymi opcjami stylu etykiet dla etykietowania dużych zestawów
  danych.
linktitle: Label Features on Map
second_title: Aspose.GIS .NET API
title: Etykietowanie elementów mapy przy użyciu Aspose.GIS dla .NET
url: /pl/net/map-rendering/label-features-on-map/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Etykietowanie elementów mapy przy użyciu Aspose.GIS dla .NET

## Wprowadzenie
Etykietowanie elementów mapy jest niezbędne, aby przekształcić surowe dane geoprzestrzenne w czytelne, przyjazne dla użytkownika wizualizacje. W tym samouczku dowiesz się **jak etykietować elementy mapy** (główne słowo kluczowe) przy użyciu Aspose.GIS dla .NET, poznasz niestandardowe style etykiet oraz techniki działające nawet przy dużych zestawach danych. Po zakończeniu będziesz w stanie dodać informacyjny tekst bezpośrednio na mapy, czyniąc je bardziej wartościowymi dla analityków i użytkowników końcowych.

## Szybkie odpowiedzi
- **Jaka jest główna klasa do renderowania?** `Map` (Aspose.Gis.Rendering)
- **Która klasa etykietowania dodaje prosty tekst?** `SimpleLabeling`
- **Czy mogę stylizować etykiety (halo, czcionka, obrót)?** Tak – poprzez właściwości takie jak `HaloSize`, `FontStyle` i `Placement`
- **Jak radzić sobie z dużymi zestawami danych?** Użyj `FeatureBasedConfiguration`, aby priorytetyzować etykiety na podstawie wartości atrybutów
- **Czy potrzebna jest licencja?** Wersja próbna działa w środowisku deweloperskim; licencja komercyjna jest wymagana w produkcji

## Co to są etykiety elementów mapy?
`label map features` oznacza dołączanie czytelnego tekstu (np. nazw miast, liczb ludności lub własnych identyfikatorów) do obiektów geometrycznych — punktów, linii lub wielokątów — tak, aby mapa jednocześnie przekazywała informacje przestrzenne i atrybutowe w jednym spojrzeniu.

## Dlaczego warto używać Aspose.GIS do etykietowania elementów mapy?
- **Zero zewnętrznych zależności** – czysta biblioteka .NET, bez potrzeby natywnych plików binarnych GIS.  
- **Bogate opcje stylizacji** – halo, własne czcionki, obrót i punkty kotwiczenia pozwalają precyzyjnie dopasować wygląd.  
- **Świadomość wydajności** – wbudowane etykietowanie oparte na cechach umożliwia priorytetyzację najważniejszych etykiet przy renderowaniu dużych zestawów danych.  
- **Wiele formatów wyjściowych** – SVG, PNG, PDF itp., z jednolitymi rezultatami etykietowania.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

- Praktyczną znajomość C# i platformy .NET.  
- Zainstalowane Aspose.GIS dla .NET. Możesz pobrać je **[here](https://releases.aspose.com/gis/net/)**.  
- Plik GeoJSON zawierający dane punktowe (lub dowolny obsługiwany format wektorowy).  

## Importowanie przestrzeni nazw
W kodzie C# zaimportuj wymagane przestrzenie nazw:

```csharp
using System;
using System.Drawing;
using Aspose.Gis;
using Aspose.Gis.Rendering;
using Aspose.Gis.Rendering.Labelings;
using Aspose.Gis.Rendering.Symbolizers;
using Aspose.GIS.Examples.CSharp;
using FontStyle = Aspose.Gis.Rendering.Labelings.FontStyle;
```

Teraz przejdziemy przez kilka scenariuszy etykietowania, każdy budujący się na poprzednim.

## Etykietowanie punktów – Jak etykietować punkty
### Krok 1: Ustaw ścieżkę do katalogu dokumentów
```csharp
string dataDir = "Your Document Directory";
```

### Krok 2: Utwórz mapę z prostym symbolem znacznika
```csharp
using (var map = new Map(500, 200))
{
    var symbol = new SimpleMarker
    {
        FillColor = Color.LightGray,
        StrokeStyle = StrokeStyle.None
    };
    var labeling = new SimpleLabeling(labelAttribute: "name");
    // 3. Add a vector layer and apply labeling
    map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), symbol, labeling);
    map.Padding = 50;
    // 4. Render the map to an SVG file
    map.Render(dataDir + "points_labeling_out.svg", Renderers.Svg);
}
```

W tym podstawowym przykładzie **how to label points** używamy atrybutu `name` z pliku GeoJSON.

## Etykietowanie punktów ze stylem – Niestandardowy styl etykiety
Postępuj zgodnie z krokami 1 i 2 z poprzedniego przykładu, a następnie dostosuj styl etykietowania:

```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 2,
    HaloColor = Color.LightGray,
    FontSize = 15,
    FontStyle = FontStyle.Italic,
};
// Rest of the steps remain the same
```

Dodane halo i kursywa nadają etykietom **custom label style**, który wyróżnia się na zatłoczonym tle.

## Etykietowanie punktów z pozycjonowaniem – Zaawansowane opcje rozmieszczenia
Ponownie rozpocznij od kroków 1 i 2 z pierwszego przykładu, a potem dostosuj pozycjonowanie:

```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 1,
    Placement = new PointLabelPlacement
    {
        VerticalAnchorPoint = VerticalAnchor.Bottom,
        HorizontalAnchorPoint = HorizontalAnchor.Left,
        HorizontalOffset = 2,
        VerticalOffset = 2,
        Rotation = 10,
    }
};
// Rest of the steps remain the same
```

Tutaj kontrolujemy punkty kotwiczenia, offsety i obrót, co daje precyzyjną kontrolę nad **how to label points** w gęsto zaludnionych obszarach mapy.

## Etykietowanie punktów oparte na cechach – Etykietowanie dużych zestawów danych
Gdy masz do czynienia z wieloma punktami, możesz chcieć priorytetyzować etykiety na podstawie atrybutu, takiego jak populacja. Postępuj zgodnie z krokami 1 i 2 z pierwszego przykładu, a następnie wdroż etykietowanie oparte na cechach:

```csharp
var pointLabeling = new SimpleLabeling("name")
{
    HaloSize = 1,
    Placement = new PointLabelPlacement
    {
        VerticalAnchorPoint = VerticalAnchor.Bottom,
        HorizontalAnchorPoint = HorizontalAnchor.Left,
        VerticalOffset = 4,
        HorizontalOffset = 4,
    },
    FeatureBasedConfiguration = (feature, labeling) =>
    {
        // Retrieve population from the feature.
        var population = feature.GetValue<int>("population");
        // Font size is computed and is based on the population.
        labeling.FontSize = Math.Min(20, 5 * population / 1000);
        // Priority of the label is also based on the population.
        // The greater the priority is, the more likely label will appear on the output image.
        labeling.Priority = population;
    }
};
// Rest of the steps remain the same
```

Ta strategia **large dataset labeling** zapewnia, że najważniejsze miasta (według liczby ludności) są wyświetlane jako pierwsze, a mniej istotne punkty mogą zostać pominięte, gdy przestrzeń jest ograniczona.

## Zakończenie
Gratulacje! Teraz znasz różne sposoby **label map features** przy użyciu Aspose.GIS dla .NET — od prostego etykietowania punktów po zaawansowane, oparte na cechach stylizowanie dużych zestawów danych. Eksperymentuj z halo, obrotami i regułami priorytetów, aby tworzyć mapy, które dokładnie przekazują to, co Twoja publiczność musi zobaczyć.

## Najczęściej zadawane pytania

**Q: Czy mogę etykietować elementy przy użyciu własnych czcionek?**  
A: Tak. Ustaw `FontFamily` i `FontStyle` w konfiguracji `SimpleLabeling`, aby używać dowolnej zainstalowanej czcionki.

**Q: Czy Aspose.GIS jest kompatybilny z innymi formatami danych GIS?**  
A: Absolutnie. Obsługuje GeoJSON, Shapefile, KML, GML i wiele innych formatów.

**Q: Jak mogę radzić sobie z dużymi zestawami danych przy etykietowaniu?**  
A: Użyj `FeatureBasedConfiguration`, aby przypisywać priorytety i dynamicznie dostosowywać rozmiary czcionek na podstawie wartości atrybutów, jak pokazano w przykładzie opartym na cechach.

**Q: Czy dostępne są zaawansowane opcje rozmieszczania etykiet?**  
A: Tak. Możesz precyzyjnie dostroić pozycjonowanie za pomocą `PointLabelPlacement`, regulując punkty kotwiczenia, offsety i obrót.

**Q: Czy mogę zautomatyzować generowanie etykiet w procesie wsadowym?**  
A: Oczywiście. Umieść kod renderujący mapę w pętli lub usłudze w tle, aby automatycznie przetwarzać wiele warstw lub plików.

---

**Ostatnia aktualizacja:** 2026-01-15  
**Testowano z:** Aspose.GIS 24.11 dla .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}