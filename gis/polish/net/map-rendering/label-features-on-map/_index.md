---
title: Opanowanie etykietowania funkcji za pomocą Aspose.GIS dla .NET
linktitle: Oznacz funkcje na mapie
second_title: Aspose.GIS .NET API
description: Poznaj Aspose.GIS dla .NET i opanuj sztukę oznaczania obiektów na mapach. Ulepsz swoje wizualizacje geoprzestrzenne bez wysiłku. #Aspose #GIS
weight: 11
url: /pl/net/map-rendering/label-features-on-map/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Opanowanie etykietowania funkcji za pomocą Aspose.GIS dla .NET

## Wstęp
świecie wizualizacji danych geoprzestrzennych etykietowanie obiektów na mapie odgrywa kluczową rolę w skutecznym przekazywaniu informacji. Aspose.GIS dla .NET zapewnia potężny zestaw narzędzi umożliwiający bezproblemowe osiągnięcie tego celu. W tym samouczku omówimy różne metody oznaczania punktów na mapie za pomocą Aspose.GIS, wzbogacając wizualizacje map za pomocą etykiet informacyjnych.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Praktyczna znajomość C# i frameworka .NET.
-  Zainstalowany Aspose.GIS dla .NET. Możesz go pobrać[Tutaj](https://releases.aspose.com/gis/net/).
- Plik GeoJSON zawierający dane punktowe. Jeśli go nie masz, możesz użyć przykładowego pliku do przetestowania.
## Importuj przestrzenie nazw
Upewnij się, że w kodzie C# zaimportowałeś przestrzenie nazw niezbędne do pracy z Aspose.GIS:
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
Teraz podzielmy każdy przykład na wiele kroków w formie przewodnika krok po kroku.
##  Etykietowanie punktów

### Krok 1: Ustaw ścieżkę do katalogu dokumentów:
```csharp
string dataDir = "Your Document Directory";
```
### Krok 2: Utwórz mapę z prostym symbolem znacznika:
```csharp
using (var map = new Map(500, 200))
{
    var symbol = new SimpleMarker
    {
        FillColor = Color.LightGray,
        StrokeStyle = StrokeStyle.None
    };
    var labeling = new SimpleLabeling(labelAttribute: "name");
    // 3. Dodaj warstwę wektorową i zastosuj etykietowanie
    map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), symbol, labeling);
    map.Padding = 50;
    // 4. Wyrenderuj mapę do pliku SVG
    map.Render(dataDir + "points_labeling_out.svg", Renderers.Svg);
}
```
## Styl etykietowania punktów

Wykonaj kroki 1 i 2 z poprzedniego przykładu.

### Krok 1: Dostosuj styl etykietowania:
```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 2,
    HaloColor = Color.LightGray,
    FontSize = 15,
    FontStyle = FontStyle.Italic,
};
// Pozostałe kroki pozostają takie same
```
## Umieszczone oznakowanie punktów

Wykonaj kroki 1 i 2 z pierwszego przykładu.
### Krok 2: Dostosuj położenie etykiety:
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
// Pozostałe kroki pozostają takie same
```
## Etykietowanie punktów oparte na funkcjach

Wykonaj kroki 1 i 2 z pierwszego przykładu.

### Krok 1: Wdróż etykietowanie oparte na funkcjach:
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
        // Pobierz populację z obiektu.
        var population = feature.GetValue<int>("population");
        // Rozmiar czcionki jest obliczany na podstawie populacji.
        labeling.FontSize = Math.Min(20, 5 * population / 1000);
        // Priorytet etykiety zależy również od populacji.
        // Im wyższy priorytet, tym większe prawdopodobieństwo pojawienia się etykiety na obrazie wyjściowym.
        labeling.Priority = population;
    }
};
// Pozostałe kroki pozostają takie same
```
## Wniosek
Gratulacje! Nauczyłeś się, jak ulepszać wizualizacje map, etykietując obiekty za pomocą Aspose.GIS dla .NET. Eksperymentuj z różnymi stylami i lokalizacjami, aby tworzyć atrakcyjne mapy dostosowane do Twoich danych.
## Często zadawane pytania
### Czy mogę oznaczać obiekty przy użyciu niestandardowych czcionek?
Tak, możesz dostosować styl i rozmiar czcionki w konfiguracji etykietowania.
### Czy Aspose.GIS jest kompatybilny z innymi formatami danych GIS?
Aspose.GIS obsługuje różne formaty geoprzestrzenne, w tym GeoJSON, Shapefile i inne.
### Jak mogę obsługiwać duże zbiory danych do etykietowania?
Aspose.GIS jest zoptymalizowany pod kątem wydajności, ale rozważ użycie konfiguracji opartych na funkcjach, aby nadać priorytet etykietom na podstawie atrybutów danych.
### Czy dostępne są zaawansowane opcje umieszczania etykiet?
Tak, możesz dostosować rozmieszczenie etykiet, korzystając z opcji takich jak obrót, punkty kontrolne i przesunięcia.
### Czy mogę zautomatyzować generowanie etykiet w procesie wsadowym?
Oczywiście możesz zintegrować Aspose.GIS ze swoimi zautomatyzowanymi przepływami pracy w celu wsadowego generowania etykiet.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
