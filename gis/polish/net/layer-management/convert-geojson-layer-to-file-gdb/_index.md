---
date: 2026-01-10
description: Dowiedz się, jak konwertować GeoJSON na File GDB za pomocą Aspose.GIS
  dla .NET. Ten przewodnik krok po kroku obejmuje konwersję danych geoprzestrzennych
  oraz konwersję Aspose GIS.
linktitle: Convert GeoJSON Layer to File GDB
second_title: Aspose.GIS .NET API
title: Jak przekonwertować GeoJSON do File GDB przy użyciu Aspose.GIS dla .NET
url: /pl/net/layer-management/convert-geojson-layer-to-file-gdb/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak przekonwertować GeoJSON na File GDB przy użyciu Aspose.GIS dla .NET

## Wprowadzenie
Jeśli zastanawiasz się **jak przekonwertować GeoJSON** na File Geodatabase (File GDB) w celu solidnych przepływów pracy GIS, trafiłeś we właściwe miejsce. W tym samouczku przeprowadzimy Cię przez cały proces przy użyciu Aspose.GIS dla .NET, pokazując, dlaczego ta biblioteka jest najlepszym wyborem do konwersji danych geoprzestrzennych i jak szybko możesz utworzyć bazę plikową z warstwy GeoJSON.

## Szybkie odpowiedzi
- **Co obejmuje samouczek?** Konwersję warstwy GeoJSON do File GDB przy użyciu Aspose.GIS dla .NET.  
- **Jakie główne słowo kluczowe jest celem?** *how to convert geojson*.  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna wystarczy do testów; licencja komercyjna jest wymagana w produkcji.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Jak długo trwa implementacja?** Około 10‑15 minut dla podstawowej konwersji.

## Co to jest GeoJSON i File GDB?
GeoJSON to lekki, tekstowy format służący do kodowania różnych struktur danych geograficznych. File Geodatabase (File GDB) to format oparty na folderze, o wysokiej wydajności desktopowych GIS. Konwersja między nimi pozwala wykorzystać zalety obu formatów w Twoich projektach.

## Dlaczego warto używać Aspose.GIS do konwersji danych geoprzestrzennych?
Aspose.GIS oferuje jednolite API, które ukrywa złożoność obsługi formatów. Dzięki wbudowanemu wsparciu dla **geojson to file gdb**, możesz:

- Odczytać GeoJSON w C# bez użycia parserów zewnętrznych.  
- Programowo utworzyć bazę plikową.  
- Automatycznie zachować dane atrybutowe oraz informacje o układzie współrzędnych.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

- Praktyczną znajomość programowania w .NET.  
- Zainstalowane Aspose.GIS dla .NET. Jeśli nie, pobierz je [tutaj](https://releases.aspose.com/gis/net/) i postępuj zgodnie z instrukcjami instalacji.

## Importowanie przestrzeni nazw
Pierwszym krokiem jest wprowadzenie wymaganych przestrzeni nazw do zakresu.

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

## Krok 1: Przygotowanie warstwy GeoJSON
Utwórz tymczasowy plik GeoJSON zawierający atrybuty i obiekty, które chcesz przekonwertować. Ten przykład dodaje dwie proste cechy punktowe.

```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    // Add attributes
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    // Construct and add features
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

## Krok 2: Skopiowanie zestawu danych testowych
Aby nie zmodyfikować oryginalnych danych testowych, skopiuj istniejący zestaw danych File GDB. Zapewnia to czyste środowisko do konwersji.

```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```

## Krok 3: Konwersja GeoJSON do File GDB
Otwórz warstwę GeoJSON, utwórz nową warstwę w skopiowanym File GDB, skopiuj atrybuty i przenieś każdy obiekt. To jest rdzeń procesu **aspose gis conversion**.

```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        // Copy attributes
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        // Add features
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```

## Typowe problemy i rozwiązania
- **Brak definicji układu współrzędnych:** Upewnij się, że źródłowy GeoJSON zawiera definicję CRS lub jawnie ustaw `SpatialReferenceSystem.Wgs84` podczas tworzenia warstwy File GDB.  
- **Niezgodność typów atrybutów:** Typy danych atrybutów w GeoJSON muszą odpowiadać docelowemu schematowi; w przeciwnym razie Aspose.GIS zgłosi wyjątek.  
- **Błędy dostępu do pliku:** Sprawdź, czy docelowy folder ma uprawnienia do zapisu i czy żaden inny proces nie blokuje plików GDB.

## Najczęściej zadawane pytania
### Czy Aspose.GIS jest kompatybilny z najnowszą wersją .NET framework?
Tak, Aspose.GIS jest kompatybilny z najnowszymi wersjami .NET framework.

### Czy mogę konwertować inne formaty geoprzestrzenne przy użyciu Aspose.GIS?
Oczywiście! Aspose.GIS obsługuje szeroką gamę formatów geoprzestrzennych, umożliwiając wszechstronną manipulację danymi.

### Czy dostępna jest wersja próbna Aspose.GIS?
Tak, możesz wypróbować funkcjonalności Aspose.GIS, pobierając wersję próbną [tutaj](https://releases.aspose.com/).

### Jak mogę uzyskać wsparcie w sprawach związanych z Aspose.GIS?
Odwiedź forum Aspose.GIS [forum](https://forum.aspose.com/c/gis/33), gdzie znajdziesz dedykowaną pomoc.

### Czy mogę uzyskać tymczasową licencję na Aspose.GIS?
Tak, tymczasową licencję możesz zdobyć [tutaj](https://purchase.aspose.com/temporary-license/).

---

**Ostatnia aktualizacja:** 2026-01-10  
**Testowano z:** Aspose.GIS 24.11 dla .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}