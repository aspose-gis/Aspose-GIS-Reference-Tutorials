---
date: 2026-06-15
description: Dowiedz się, jak utworzyć vector layer i ustawić spatial reference system
  warstwy przy użyciu Aspose.GIS for .NET. Opanuj definiowanie spatial reference,
  dodawanie point feature oraz pobieranie EPSG code.
keywords:
- create vector layer
- add point feature
- set layer coordinate system
- define epsg code
- how to set crs
linktitle: Ustaw Spatial Reference System warstwy
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  headline: Create Vector Layer and Set Layer Spatial Reference System
  type: TechArticle
- description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  name: Create Vector Layer and Set Layer Spatial Reference System
  steps:
  - name: Specify the Document Directory
    text: Begin by specifying the path to your document directory. This will be the
      location where your spatial data files are stored.
  - name: Define Spatial Reference and Set Shapefile Coordinate System
    text: SpatialReferenceSystem represents the CRS of a layer, identified by an EPSG
      code. Define the path for the Shapefile, and **define spatial reference** using
      the EPSG code (26918 in this example). This step **sets the shapefile coordinate
      system** for the layer.
  - name: Create Vector Layer
    text: '`ConstructFeature` creates a new feature object that can hold geometry
      and attribute data. Now **create vector layer** with the specified Shapefile
      path, driver type (Shapefile), and the spatial reference system you just defined.'
  - name: Add Point Feature to the Layer
    text: Construct a new feature and **add point feature** by setting its geometry
      (a `Point` with coordinates 60, 24). Then add the feature to the vector layer.
  - name: Retrieve Spatial Reference System Information (Retrieve EPSG Code)
    text: Open the Vector Layer and retrieve information about the spatial reference
      system, such as the EPSG code and the human‑readable name. This demonstrates
      how to **retrieve EPSG code** and **set layer CRS**.
  type: HowTo
- questions:
  - answer: Open the layer, create a new `SpatialReferenceSystem` with the desired
      EPSG code, assign it to `layer.SpatialReferenceSystem`, then save the layer.
    question: How do I change the CRS of an existing Shapefile?
  - answer: Yes—replace `new Point(x, y)` with `new Polygon(...)` or `new LineString(...)`
      as needed.
    question: Can I add other geometry types (e.g., polygons) using the same approach?
  - answer: Use streaming APIs (`VectorLayer.Create` with `FeatureCollection`) and
      dispose layers promptly to free resources.
    question: Is it possible to work with large datasets efficiently?
  - answer: Yes—use `Geometry.Transform(targetSrs)` to reproject geometries between
      different spatial references.
    question: Does Aspose.GIS support coordinate transformation?
  - answer: Aspose.GIS works with .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Utwórz Vector Layer i ustaw Spatial Reference System warstwy
url: /pl/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz warstwę wektorową i ustaw system odniesienia przestrzennego warstwy

## Wprowadzenie
W rozległym krajobrazie Systemów Informacji Geograficznej (GIS) **Aspose.GIS for .NET** wyróżnia się jako solidna, wysokowydajna biblioteka, która obsługuje ponad **70** formatów wektorowych i rastrowych oraz może przetwarzać pliki większe niż **10 GB** bez ładowania całego zestawu danych do pamięci. W tym samouczku **utworzysz warstwę wektorową**, określisz jej odniesienie przestrzenne, **dodasz cechę punktową** i pobierzesz kod EPSG — wszystko z jasnym, krok po kroku przewodnikiem. Niezależnie od tego, czy tworzysz usługę mapowania, pipeline konwersji danych, czy silnik analizy przestrzennej, opanowanie tych podstaw zapewni dokładny system współrzędnych pliku shapefile i niezawodny przepływ pracy GIS.

## Szybkie odpowiedzi
- **Co oznacza „create vector layer”?** Tworzy nową warstwę GIS (np. Shapefile), która może przechowywać geometrie takie jak punkty, linie lub wielokąty.  
- **Jaki kod EPSG jest użyty w przykładzie?** EPSG 26918 (NAD83 / UTM strefa 18N).  
- **Czy mogę dodać cechę punktową po utworzeniu warstwy?** Tak — użyj `ConstructFeature()` i przypisz geometrię `Point`.  
- **Jak pobrać CRS warstwy?** Odczytaj `layer.SpatialReferenceSystem.EpsgCode` lub `.Name`.  
- **Czy potrzebna jest licencja na Aspose.GIS?** Dostępna jest bezpłatna wersja próbna; licencja jest wymagana do użytku produkcyjnego.

## Czym jest utworzenie warstwy wektorowej?
Operacja **create vector layer** tworzy nowy zestaw danych wektorowych (np. Shapefile), który może przechowywać cechy geometryczne oraz dane atrybutowe. W Aspose.GIS odbywa się to poprzez utworzenie obiektu `VectorLayer` z określonym sterownikiem i systemem odniesienia przestrzennego.

## Dlaczego prawidłowo ustawić układ współrzędnych warstwy (CRS)?
Ustawienie prawidłowego układu współrzędnych (CRS) zapewnia, że każda przechowywana geometria jest zgodna z innymi zestawami danych przestrzennych. Dzięki Aspose.GIS możesz określić CRS przy użyciu standardowego kodu EPSG, co gwarantuje interoperacyjność z oprogramowaniem GIS na całym świecie. Na przykład EPSG 26918 definiuje NAD83 / UTM strefa 18N, powszechną projekcję dla danych wschodnich Stanów Zjednoczonych.

## Wymagania wstępne
- Doświadczenie w programowaniu .NET (C# lub VB.NET).  
- Visual Studio 2022 lub nowszy.  
- Biblioteka Aspose.GIS for .NET – pobierz ją **[here](https://releases.aspose.com/gis/net/)**.  
- Podstawowa znajomość systemów odniesienia przestrzennego (CRS/EPSG).

## Importowanie przestrzeni nazw
Przestrzeń nazw `Aspose.Gis` dostarcza podstawowe klasy GIS, natomiast `Aspose.Gis.Geometries` udostępnia typy geometrii, takie jak `Point`.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## Jak utworzyć warstwę wektorową w Aspose.GIS dla .NET?
VectorLayer reprezentuje zestaw danych wektorowych, taki jak Shapefile, i udostępnia metody do tworzenia, odczytu i edycji cech.  
SpatialReferenceSystem definiuje układ współrzędnych przy użyciu kodu EPSG.  

Załaduj docelowy folder, zdefiniuj `SpatialReferenceSystem` z kodem EPSG i wywołaj `VectorLayer.Create` z sterownikiem Shapefile. To pojedyncze wywołanie tworzy nowy plik `.shp`, zapisuje powiązane pliki `.shx` i `.dbf` oraz osadza metadane CRS, gotowe do efektywnego wstawiania cech.

### Krok 1: Określ katalog dokumentu
Zacznij od określenia ścieżki do katalogu dokumentów. Będzie to miejsce, w którym przechowywane są pliki danych przestrzennych.

```csharp
string dataDir = "Your Document Directory";
```

### Krok 2: Zdefiniuj odniesienie przestrzenne i ustaw układ współrzędnych pliku Shapefile
SpatialReferenceSystem reprezentuje CRS warstwy, identyfikowany kodem EPSG.  

Zdefiniuj ścieżkę do pliku Shapefile i **zdefiniuj odniesienie przestrzenne** przy użyciu kodu EPSG (26918 w tym przykładzie). Ten krok **ustawia układ współrzędnych pliku Shapefile** dla warstwy.

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## Jak dodać cechę punktową do warstwy wektorowej?
`Point` jest typem geometrii reprezentującym pojedynczą parę współrzędnych X/Y.  

Utwórz nową cechę, przypisz geometrię `Point` z żądanymi współrzędnymi X/Y i dodaj cechę do otwartego `VectorLayer`. Operacja zapisuje geometrię do pliku `.shp` oraz rekord atrybutu do pliku `.dbf` w jednej transakcji.

### Krok 3: Utwórz warstwę wektorową
`ConstructFeature` tworzy nowy obiekt cechy, który może przechowywać dane geometryczne i atrybuty.  

Teraz **utwórz warstwę wektorową** z określoną ścieżką Shapefile, typem sterownika (Shapefile) oraz systemem odniesienia przestrzennego, który właśnie zdefiniowałeś.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

### Krok 4: Dodaj cechę punktową do warstwy
Utwórz nową cechę i **dodaj cechę punktową** ustawiając jej geometrię (obiekt `Point` o współrzędnych 60, 24). Następnie dodaj cechę do warstwy wektorowej.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

### Krok 5: Pobierz informacje o systemie odniesienia przestrzennego (pobierz kod EPSG)
Otwórz warstwę wektorową i pobierz informacje o systemie odniesienia przestrzennego, takie jak kod EPSG i czytelna nazwa. To pokazuje, jak **pobrać kod EPSG** i **ustawić CRS warstwy**.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

## Typowe problemy i rozwiązania
| Problem | Dlaczego się pojawia | Rozwiązanie |
|---------|----------------------|-------------|
| **Warstwa nie otwiera się** | Nieprawidłowy sterownik lub uszkodzona ścieżka pliku | Sprawdź `Drivers.Shapefile` i upewnij się, że `path` wskazuje istniejący plik `.shp`. |
| **Wyświetlany nieprawidłowy CRS** | Użycie niewłaściwego kodu EPSG | Sprawdź ponownie kod EPSG w autorytatywnym źródle (np. EPSG.io). |
| **Cecha nie została zapisana** | Nie wywołano `layer.Add(feature)` wewnątrz bloku `using` | Upewnij się, że metoda `Add` jest wykonana przed zwolnieniem warstwy. |

## Najczęściej zadawane pytania
**Q: Jak zmienić CRS istniejącego pliku Shapefile?**  
A: Otwórz warstwę, utwórz nowy `SpatialReferenceSystem` z żądanym kodem EPSG, przypisz go do `layer.SpatialReferenceSystem`, a następnie zapisz warstwę.

**Q: Czy mogę dodać inne typy geometrii (np. wielokąty) używając tego samego podejścia?**  
A: Tak — zamień `new Point(x, y)` na `new Polygon(...)` lub `new LineString(...)` w zależności od potrzeb.

**Q: Czy możliwe jest efektywne przetwarzanie dużych zestawów danych?**  
A: Używaj interfejsów strumieniowych (`VectorLayer.Create` z `FeatureCollection`) i szybko zwalniaj warstwy, aby zwolnić zasoby.

**Q: Czy Aspose.GIS obsługuje transformację współrzędnych?**  
A: Tak — użyj `Geometry.Transform(targetSrs)`, aby przekształcić geometrie między różnymi systemami odniesienia.

**Q: Jakie wersje .NET są obsługiwane?**  
A: Aspose.GIS działa z .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.

---

**Last Updated:** 2026-06-15  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Create Vector Layer and Set Linearization Tolerance using Aspose.GIS for .NET](/gis/net/geometry-processing/set-linearization-tolerance/)
- [Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [spatial reference wgs84 – Add Layer to GDB using Aspose.GIS](/gis/net/layer-management/add-layer-to-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}