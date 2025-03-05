---
title: Konwersja GeoJSON do pliku GDB wyjaśniona
linktitle: Konwertuj warstwę GeoJSON na plik GDB
second_title: Aspose.GIS .NET API
description: Odblokuj cuda geoprzestrzenne dzięki Aspose.GIS dla .NET! Bez wysiłku konwertuj warstwy GeoJSON na geobazy plikowe. Spróbuj teraz! #Aspose #GIS
type: docs
weight: 17
url: /pl/net/layer-management/convert-geojson-layer-to-file-gdb/
---
## Wstęp
W dynamicznej dziedzinie systemów informacji geograficznej (GIS) kluczowa jest możliwość płynnej konwersji danych pomiędzy różnymi formatami. Aspose.GIS dla .NET okazuje się potężnym sojusznikiem, oferującym kompleksowy zestaw narzędzi do łatwej obsługi danych geoprzestrzennych. W tym samouczku zagłębimy się w proces konwersji warstwy GeoJSON do geobazy plikowej (pliku GDB) przy użyciu Aspose.GIS dla .NET.
## Warunki wstępne
Przed wyruszeniem w tę podróż geoprzestrzenną upewnij się, że spełnione są następujące wymagania wstępne:
- Praktyczna znajomość programowania .NET.
-  Zainstalowany Aspose.GIS dla .NET. Jeśli nie, pobierz go z[Tutaj](https://releases.aspose.com/gis/net/) i postępuj zgodnie z instrukcją instalacji.
## Importuj przestrzenie nazw
Aby rozpocząć proces konwersji, zacznij od zaimportowania niezbędnych przestrzeni nazw:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
Podzielmy teraz proces na przewodnik krok po kroku:
## Krok 1: Skonfiguruj warstwę GeoJSON
Zacznij od utworzenia warstwy GeoJSON z odpowiednimi atrybutami i funkcjami. Oto fragment, który Cię poprowadzi:
```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    // Dodaj atrybuty
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    //Konstruuj i dodawaj funkcje
    Feature firstFeature = layer.ConstructFeature();
    firstFeature.Geometry = new Point(33.97, -118.25);
    firstFeature.SetValue("name", "John");
    firstFeature.SetValue("age", 23);
    layer.Add(firstFeature);
    Feature secondFeature = layer.ConstructFeature();
    secondFeature.Geometry = new Point(35.81, -96.28);
    secondFeature.SetValue("name", "Mary");
    secondFeature.SetValue("age", 54);
    layer.Add(secondFeature);
}
```
## Krok 2: Skopiuj testowy zbiór danych
Aby zachować integralność danych testowych, utwórz kopię zbioru danych. Użyj następującego fragmentu kodu:
```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```
## Krok 3: Konwertuj GeoJSON na plik GDB
Teraz nadszedł czas na wykonanie konwersji. Wykorzystaj następujący kod:
```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        // Skopiuj atrybuty
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        // Dodać funkcje
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```
## Wniosek
W tym samouczku poruszaliśmy się po intrygującym terenie konwersji warstwy GeoJSON na geobazę plikową przy użyciu Aspose.GIS dla .NET. Uzbrojony w tę wiedzę, możesz teraz bezproblemowo manipulować danymi geoprzestrzennymi w aplikacjach .NET.
## Często zadawane pytania
### Czy Aspose.GIS jest kompatybilny z najnowszym frameworkiem .NET?
Tak, Aspose.GIS jest kompatybilny z najnowszymi wersjami frameworku .NET.
### Czy mogę konwertować inne formaty geoprzestrzenne za pomocą Aspose.GIS?
Absolutnie! Aspose.GIS obsługuje szeroką gamę formatów geoprzestrzennych, umożliwiając wszechstronną manipulację danymi.
### Czy dostępna jest wersja próbna Aspose.GIS?
 Tak, możesz poznać funkcjonalności Aspose.GIS pobierając wersję próbną[Tutaj](https://releases.aspose.com/).
### Jak mogę uzyskać pomoc dotyczącą zapytań związanych z Aspose.GIS?
 Przejdź do Aspose.GIS[forum](https://forum.aspose.com/c/gis/33) za dedykowane wsparcie.
### Czy mogę uzyskać tymczasową licencję na Aspose.GIS?
 Tak, możesz zabezpieczyć licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).