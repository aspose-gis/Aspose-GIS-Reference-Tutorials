---
date: 2026-01-18
description: Dowiedz się, jak dodać miasta do mapy i wygenerować mapę SVG przy użyciu
  Aspose.GIS dla .NET. Twórz oszałamiające wizualizacje szybko.
linktitle: Render a Map
second_title: Aspose.GIS .NET API
title: Jak dodać miasta do mapy przy użyciu Aspose.GIS dla .NET
url: /pl/net/map-rendering/render-a-map/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dodać miasta do mapy przy użyciu Aspose.GIS dla .NET

## Wprowadzenie
Witamy w ekscytującym świecie Aspose.GIS dla .NET! W tym przewodniku krok po kroku nauczysz się **jak dodać miasta do mapy** i wygenerować wysokiej jakości wyjście SVG. Niezależnie od tego, czy tworzysz pulpit nawigacyjny na komputerze, czy portal GIS oparty na sieci, ten tutorial pokaże Ci, jak rysować warstwy wektorowe, ustawiać wymiary mapy i ładować mapę GeoJSON z łatwością.

## Szybkie odpowiedzi
- **Co obejmuje ten tutorial?** Dodawanie miast do mapy i eksportowanie jej jako plik SVG.  
- **Jakiej biblioteki wymaga?** Aspose.GIS for .NET.  
- **Czy potrzebna jest licencja?** Dostępna jest darmowa wersja próbna; licencja jest wymagana w środowisku produkcyjnym.  
- **Czy mogę używać tego w aplikacjach webowych?** Tak – ten sam kod działa w ASP.NET, Blazor i innych frameworkach webowych .NET.  
- **Jaki format wyjściowy jest generowany?** Mapa SVG, którą można wyświetlić w przeglądarkach lub dalej edytować.

## Wymagania wstępne
Przed rozpoczęciem tutorialu upewnij się, że spełniasz następujące wymagania:
- Biblioteka Aspose.GIS for .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.GIS for .NET. Możesz ją pobrać [tutaj](https://releases.aspose.com/gis/net/).
- Pliki danych: Przygotuj niezbędne pliki shapefile i dane GeoJSON do tutorialu. Przykładowe dane znajdziesz w dokumentacji lub użyj własnych plików.
- Środowisko programistyczne: Skonfiguruj środowisko programistyczne .NET, w tym edytor kodu taki jak Visual Studio.

## Importowanie przestrzeni nazw
Aby rozpocząć, zaimportuj wymagane przestrzenie nazw do swojego projektu .NET. Te przestrzenie nazw są niezbędne do pracy z funkcjami Aspose.GIS.

```csharp
using Aspose.Gis;
using Aspose.Gis.Rendering;
using Aspose.Gis.Rendering.Symbolizers;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.Drawing.Text;
using System.IO;
using System.Linq;
```

## Krok 1: Konfiguracja mapy (ustaw wymiary mapy)
```csharp
string dataDir = "Your Document Directory";
using (var map = new Map(800, 476))
{
    // Additional code for map setup can be added here.
}
```
W tym kroku inicjalizujemy nową mapę o szerokości 800 pikseli i wysokości 476 pikseli. Dostosuj wymiary do wymagań swojego projektu.

## Krok 2: Dodanie mapy bazowej (rysowanie warstwy wektorowej)
```csharp
var baseMapSymbolizer = new SimpleFill { FillColor = Color.Salmon, StrokeWidth = 0.75 };
map.Add(VectorLayer.Open(dataDir + "basemap.shp", Drivers.Shapefile), baseMapSymbolizer);
```
Tutaj **rysujemy warstwę wektorową** dla mapy bazowej przy użyciu pliku shapefile. Śmiało zmień właściwości `SimpleFill`, aby dopasować je do swojego stylu wizualnego.

## Krok 3: Dodanie miast do mapy (dodaj miasta do mapy, załaduj mapę GeoJSON)
```csharp
var citiesSymbolizer = new SimpleMarker() { FillColor = Color.LightBlue };
citiesSymbolizer.FeatureBasedConfiguration = (feature, symbolizer) =>
{
    // Additional configuration logic can be added here.
};
map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), citiesSymbolizer);
```
Ten krok ładuje plik GeoJSON zawierający dane punktowe miast i **dodaje miasta do mapy**. Możesz rozbudować delegata `FeatureBasedConfiguration`, aby stylizować miasta na podstawie atrybutów, takich jak populacja.

## Krok 4: Renderowanie mapy (eksport mapy SVG, generowanie mapy SVG)
```csharp
map.Render(dataDir + "cities_out.svg", Renderers.Svg);
```
Na koniec **eksportujemy mapę jako plik SVG**. Powstały plik `cities_out.svg` można otworzyć w dowolnej nowoczesnej przeglądarce lub edytorze grafiki wektorowej.

## Podsumowanie
Gratulacje! Pomyślnie **dodałeś miasta do mapy** i wygenerowałeś mapę SVG przy użyciu Aspose.GIS dla .NET. Ten tutorial pokazał, jak ustawić wymiary mapy, rysować warstwy wektorowe, ładować dane GeoJSON i eksportować wynik jako skalowalny SVG — idealny zarówno dla scenariuszy internetowych, jak i drukowanych.

## FAQ
### Czy mogę używać Aspose.GIS dla .NET w moich aplikacjach webowych?
Tak, Aspose.GIS dla .NET nadaje się zarówno do aplikacji desktopowych, jak i webowych.

### Czy dostępna jest wersja próbna?
Tak, wersję próbną możesz wypróbować [tutaj](https://releases.aspose.com/).

### Gdzie mogę znaleźć wsparcie dla Aspose.GIS dla .NET?
Odwiedź [forum Aspose.GIS](https://forum.aspose.com/c/gis/33), aby uzyskać pomoc lub zadać pytania.

### Czy mogę kupić tymczasową licencję na krótkoterminowe projekty?
Tak, tymczasowa licencja jest dostępna [tutaj](https://purchase.aspose.com/temporary-license/).

### Czy są dostępne dodatkowe tutoriale dla Aspose.GIS dla .NET?
Tak, sprawdź [dokumentację](https://reference.aspose.com/gis/net/), aby uzyskać kompleksowe tutoriale i przewodniki.

---

**Last Updated:** 2026-01-18  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}