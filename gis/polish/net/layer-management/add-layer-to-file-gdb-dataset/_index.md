---
date: 2026-01-13
description: Dowiedz się, jak dodać warstwę do zestawu danych File GDB przy użyciu
  Aspose.GIS, z obsługą układu współrzędnych WGS84. Postępuj zgodnie z tym przewodnikiem
  krok po kroku, aby dodać warstwę do GDB w .NET.
linktitle: Add Layer to File GDB Dataset
second_title: Aspose.GIS .NET API
title: odniesienie przestrzenne wgs84 – Dodaj warstwę do GDB przy użyciu Aspose.GIS
url: /pl/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# spatial reference wgs84 – Dodawanie warstwy do GDB przy użyciu Aspose.GIS

## Introduction
Gotowy, aby przyspieszyć swój przepływ pracy GIS z Aspose.GIS dla .NET? W tym samouczku dowiesz się **jak dodać warstwę do zestawu danych File GDB** pracując z układem współrzędnych **spatial reference wgs84**. Przeprowadzimy Cię krok po kroku, od przygotowania folderu z danymi po weryfikację nowo utworzonej warstwy, abyś mógł pewnie manipulować danymi geograficznymi.

## Quick Answers
- **Jaki jest podstawowy układ współrzędnych?** spatial reference wgs84 (WGS 84)  
- **Która biblioteka udostępnia API?** Aspose.GIS for .NET  
- **Czy potrzebna jest licencja do testów?** Tak – dostępna jest tymczasowa licencja Aspose.  
- **Czy mogę dodać atrybuty do nowej warstwy?** Oczywiście, możesz zdefiniować dowolną liczbę atrybutów obiektów.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## What is spatial reference wgs84?
Układ współrzędnych spatial reference wgs84 (World Geodetic System 1984) jest najpowszechniej używanym geograficznym systemem współrzędnych. Definiuje szerokość i długość geograficzną w stopniach i jest domyślnym CRS dla wielu zestawów danych GIS, w tym tego, który utworzymy w tym przewodniku.

## Why use Aspose.GIS to add a layer?
- **Brak zewnętrznych zależności:** Działa od razu z czystym kodem .NET.  
- **Pełna kontrola nad schematem:** Możesz definiować własne atrybuty i typy geometrii.  
- **Cross‑platform:** Kompatybilny z środowiskami Windows, Linux i macOS.  
- **Solidna licencja:** Tymczasowe licencje pozwalają szybko ocenić produkt przed podjęciem decyzji.

## Prerequisites
Zanim rozpoczniesz, upewnij się, że masz:

- Bibliotekę Aspose.GIS for .NET: Pobierz i zainstaluj bibliotekę z [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/).  
- Katalog dokumentów: Utwórz dedykowany folder na swoim komputerze, w którym będą przechowywane pliki GIS.

## Import Namespaces
Dodaj wymagane dyrektywy `using` do swojego projektu C#, aby móc korzystać z klas Aspose.GIS:

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

## Step 1: Copy Directory
Najpierw skopiuj folder zawierający oryginalny zestaw danych GDB. Posiadanie kopii chroni dane źródłowe podczas eksperymentów.

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Step 2: Open Dataset and Verify Creation Capability
Otwórz nowo skopiowany zestaw danych i potwierdź, że można w nim tworzyć nowe warstwy. Właściwość `CanCreateLayers` powinna zwrócić **True**.

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Step 3: Create and Populate a New Layer with spatial reference wgs84
Teraz tworzymy warstwę o nazwie **data** i explicite ustawiamy jej układ współrzędnych na **Wgs84**. Dodajemy także prosty atrybut **Name** oraz wstawiamy jedną cechę punktową.

```csharp
using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
{
    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
    var feature = layer.ConstructFeature();
    feature.SetValue("Name", "Name_1");
    feature.Geometry = new Point(12.21, 23.123, 20, -200);
    layer.Add(feature);
}
```

## Step 4: Open and Validate the Added Layer
Na koniec otwieramy warstwę, którą właśnie utworzyliśmy, i weryfikujemy jej zawartość. Konsola pokaże, że warstwa zawiera jedną cechę oraz że atrybut **Name** jest zgodny z ustawioną wartością.

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Common Issues & Tips
- **Nieprawidłowa ścieżka:** Upewnij się, że `dataDir` kończy się separatorem ścieżki (`/` lub `\`), aby połączone ciągi tworzyły prawidłowe ścieżki plików.  
- **Błędy licencyjne:** Jeśli pojawią się ostrzeżenia o licencji, zastosuj tymczasową licencję z portalu Aspose przed uruchomieniem kodu.  
- **Niezgodność CRS:** Przy otwieraniu warstwy w innym narzędziu GIS, sprawdź, czy narzędzie rozpoznaje WGS 84 (EPSG:4326) jako system współrzędnych.

## Frequently Asked Questions
### Q: Czy mogę używać Aspose.GIS for .NET wraz z innymi bibliotekami GIS?
Aspose.GIS for .NET jest zaprojektowany do pracy niezależnej, ale może być integrowany z innymi bibliotekami w celu rozszerzenia funkcjonalności.  

### Q: Czy dostępna jest tymczasowa licencja do celów testowych?
Tak, tymczasową licencję można uzyskać [tutaj](https://purchase.aspose.com/temporary-license/) do testów i oceny.  

### Q: Jakie systemy odniesienia przestrzennego obsługuje Aspose.GIS for .NET?
Aspose.GIS for .NET obsługuje szeroką gamę systemów odniesienia przestrzennego, zapewniając elastyczność w obsłudze danych geograficznych.  

### Q: Czy mogę przyczynić się do społeczności Aspose.GIS?
Oczywiście! Dołącz do dyskusji i podziel się doświadczeniami na [forum Aspose.GIS](https://forum.aspose.com/c/gis/33).  

### Q: Gdzie znajdę szczegółową dokumentację Aspose.GIS for .NET?
Kompletną dokumentację znajdziesz [tutaj](https://reference.aspose.com/gis/net/) – zawiera ona szczegółowe informacje o Aspose.GIS for .NET.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ostatnia aktualizacja:** 2026-01-13  
**Testowano z:** Aspose.GIS for .NET (najnowsza stabilna wersja)  
**Autor:** Aspose