---
date: 2026-06-20
description: Dowiedz się, jak przekonwertować geojson na gdb przy użyciu Aspose.GIS
  dla .NET. Ten przewodnik krok po kroku opisuje odczytywanie GeoJSON w C#, tworzenie
  File Geodatabase oraz radzenie sobie z typowymi problemami.
keywords:
- convert geojson to gdb
- how to convert geojson
- read geojson c#
- asp.net geojson conversion
linktitle: Konwertuj warstwę GeoJSON na GDB
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to convert geojson to gdb with Aspose.GIS for .NET. This
    step‑by‑step guide covers reading GeoJSON in C#, creating a File Geodatabase,
    and handling common issues.
  headline: How to Convert GeoJSON to GDB Using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Converting a GeoJSON layer to a GDB with Aspose.GIS for .NET.
    question: What does this guide teach?
  - answer: '*convert geojson to gdb*.'
    question: Which primary keyword is targeted?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.
    question: Supported .NET versions?
  - answer: Roughly 10‑15 minutes for a basic conversion.
    question: Implementation time?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Jak przekonwertować GeoJSON na GDB przy użyciu Aspose.GIS dla .NET
url: /pl/net/layer-management/convert-geojson-layer-to-file-gdb/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak przekonwertować GeoJSON do GDB przy użyciu Aspose.GIS dla .NET

## Wprowadzenie
Jeśli chcesz **convert geojson to gdb** szybko i niezawodnie, jesteś we właściwym miejscu. Ten samouczek przeprowadzi Cię przez każdy krok — od odczytania pliku GeoJSON w C# po utworzenie File Geodatabase (GDB) przy użyciu Aspose.GIS. Zobaczysz, dlaczego Aspose.GIS jest preferowaną biblioteką do konwersji danych geoprzestrzennych, jak skonfigurować środowisko i jak uruchomić konwersję w zaledwie kilka minut.

## Szybkie odpowiedzi
- **Co omawia ten przewodnik?** Converting a GeoJSON layer to a GDB with Aspose.GIS for .NET.  
- **Jakie główne słowo kluczowe jest celem?** *convert geojson to gdb*.  
- **Czy potrzebuję licencji?** A free trial works for testing; a commercial license is required for production.  
- **Obsługiwane wersje .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Czas implementacji?** Roughly 10‑15 minutes for a basic conversion.

## Co to jest GeoJSON i File GDB?
GeoJSON jest lekkim, tekstowym formatem dla obiektów geograficznych, natomiast File GDB to folder‑oparty, wysokowydajny geobaza danych ESRI.  
GeoJSON przechowuje punkty, linie i poligony jako zwykły tekst, co ułatwia ich udostępnianie i edycję, podczas gdy File GDB trzyma dane w plikach binarnych zapewniających szybkie zapytania przestrzenne i solidną obsługę atrybutów. Razem obejmują zarówno wymianę przyjazną dla sieci, jak i szybkie przetwarzanie w desktopowych systemach GIS.

## Dlaczego używać Aspose.GIS do konwersji danych geoprzestrzennych?
Aspose.GIS zapewnia jednolite, spójne API, które ukrywa specyficzne dla formatu niuanse. Obsługuje **30+ geospatial formats**, może przetwarzać pliki do **2 GB** bez ładowania całego zestawu danych do pamięci i automatycznie zachowuje układy odniesień współrzędnych. Oznacza to mniej czasu na pisanie parserów i więcej na budowanie logiki aplikacji.

## Wymagania wstępne
- Znajomość C# i struktury projektu .NET.  
- Aspose.GIS for .NET installed. If you haven’t installed it yet, download it from [here](https://releases.aspose.com/gis/net/) and follow the installation guide. You can also explore other Aspose products at [here](https://releases.aspose.com/).

## Importowanie przestrzeni nazw
The first step is to bring the required namespaces into scope.

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

## Jak odczytać GeoJSON w C#?
Load the GeoJSON file with the `GeoJsonReader` class, which parses the JSON and creates an in‑memory `FeatureCollection`. The reader automatically detects the coordinate reference system, so you don’t need to handle CRS parsing manually. It also supports streaming large files, preserving attribute types, and can be combined with custom geometry transformations if required.

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

## Krok 1: Przygotuj warstwę GeoJSON
Create a temporary GeoJSON file that contains the attributes and features you want to convert. This example adds two simple point features.

```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```

## Krok 2: Skopiuj zestaw danych testowych
To keep the original test data untouched, duplicate the existing File GDB dataset. This ensures a clean environment for the conversion.

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

## Krok 3: Konwertuj GeoJSON do GDB
`FileGdb` represents a File Geodatabase container and provides methods to manage layers. Open the GeoJSON layer, create a new layer inside the copied File GDB, copy attributes, and transfer each feature. This is the core of the **Aspose.GIS conversion** process.

CODE_BLOCK_PLACEHOLDER_4_END

## Jak przekonwertować GeoJSON do GDB?
Load the GeoJSON with `GeoJsonReader`, instantiate a `FileGdb` object pointing at your destination folder, create a new feature layer, and then iterate over each feature to insert it. In practice it’s a three‑step flow—read, create, copy—that completes in under a minute for typical datasets.

## Typowe problemy i rozwiązania
- **Missing spatial reference:** Ensure the source GeoJSON includes a CRS definition or explicitly set `SpatialReferenceSystem.Wgs84` when creating the GDB layer.  
- **Attribute type mismatch:** The attribute data types in GeoJSON must match the target schema; otherwise, Aspose.GIS will throw an exception.  
- **File access errors:** Verify that the destination folder has write permissions and that no other process is locking the GDB files.

## Najczęściej zadawane pytania
### Czy Aspose.GIS jest kompatybilny z najnowszym frameworkiem .NET?
Tak, Aspose.GIS działa z .NET Framework 4.5+, .NET Core 3.1+, .NET 5 i .NET 6+.

### Czy mogę konwertować inne formaty geoprzestrzenne przy użyciu Aspose.GIS?
Oczywiście! Aspose.GIS obsługuje ponad 30 formatów wejściowych i wyjściowych, w tym Shapefile, KML, GML i SQLite.

### Czy dostępna jest wersja próbna Aspose.GIS?
Tak, możesz zapoznać się z funkcjonalnościami Aspose.GIS, pobierając wersję próbną [here](https://releases.aspose.com/).

### Jak mogę uzyskać wsparcie w kwestiach związanych z Aspose.GIS?
Head over to the Aspose.GIS [forum](https://forum.aspose.com/c/gis/33) for dedicated assistance from the community and product team.

### Czy mogę uzyskać tymczasową licencję na Aspose.GIS?
Tak, możesz zabezpieczyć tymczasową licencję [here](https://purchase.aspose.com/temporary-license/).

---

**Ostatnia aktualizacja:** 2026-06-20  
**Testowano z:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose

## Powiązane samouczki

- [Utwórz zestaw danych File Geodatabase .NET przy użyciu Aspose.GIS](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Odczytaj elementy z File Geodatabase w Aspose.GIS](/gis/net/layer-data-operations/read-features-from-file-geodatabase/)
- [Utwórz warstwę wektorową w File GDB – samouczek Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}