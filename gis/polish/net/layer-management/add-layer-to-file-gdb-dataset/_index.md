---
date: 2026-06-30
description: Dowiedz się, jak dodać warstwę do zestawu danych File GDB przy użyciu
  Aspose.GIS z odniesieniem przestrzennym WGS84. Postępuj zgodnie z tym przewodnikiem
  krok po kroku, aby dodać warstwę w .NET.
keywords:
- how to add layer
- spatial reference wgs84
- Aspose.GIS .NET
- File GDB dataset
linktitle: Dodaj warstwę do zestawu danych File GDB
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to add layer to a File GDB dataset using Aspose.GIS with
    spatial reference WGS84. Follow this step‑by‑step guide to add a layer in .NET.
  headline: How to Add Layer to File GDB Dataset with spatial reference WGS84 using
    Aspose.GIS
  type: TechArticle
- questions:
  - answer: spatial reference wgs84 (WGS 84)
    question: What is the primary coordinate system used?
  - answer: Aspose.GIS for .NET
    question: Which library provides the API?
  - answer: Yes – a temporary Aspose license is available.
    question: Do I need a license for testing?
  - answer: Absolutely, you can define any number of feature attributes.
    question: Can I add attributes to the new layer?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Jak dodać warstwę do zestawu danych File GDB z odniesieniem przestrzennym WGS84
  przy użyciu Aspose.GIS
url: /pl/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# jak dodać warstwę – odniesienie przestrzenne wgs84 z Aspose.GIS

## Wprowadzenie
Gotowy, aby przyspieszyć swój przepływ pracy GIS z Aspose.GIS dla .NET? W tym samouczku nauczysz się **jak dodać warstwę** do zestawu danych File GDB, pracując z układem współrzędnych **odniesienie przestrzenne WGS84**. Przejdziemy przez każdy krok, od przygotowania folderu z danymi po weryfikację nowo utworzonej warstwy, abyś mógł pewnie i efektywnie manipulować danymi geograficznymi.

## Szybkie odpowiedzi
- **Jaki jest podstawowy system współrzędnych używany?** spatial reference wgs84 (WGS 84)  
- **Która biblioteka udostępnia API?** Aspose.GIS for .NET  
- **Czy potrzebuję licencji do testowania?** Tak – tymczasowa licencja Aspose jest dostępna.  
- **Czy mogę dodać atrybuty do nowej warstwy?** Zdecydowanie, możesz zdefiniować dowolną liczbę atrybutów obiektów.  
- **Jakie wersje .NET są wspierane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## Co to jest spatial reference wgs84?
Spatial reference wgs84 (World Geodetic System 1984) jest najczęściej używanym systemem współrzędnych geograficznych. Definiuje szerokość i długość geograficzną w stopniach i służy jako domyślny CRS dla wielu zestawów danych GIS, w tym tego, który utworzymy w tym przewodniku.

## Dlaczego używać Aspose.GIS do dodania warstwy?
Wczytaj swoje dane GIS bez binariów firm trzecich i zachowaj pełną kontrolę nad definicją schematu. Aspose.GIS obsługuje **ponad 40 systemów odniesień przestrzennych**, może przetwarzać pliki większe niż **2 GB** bez ładowania całego zestawu danych do pamięci oraz działa na Windows, Linux i macOS. Dzięki temu jest niezawodnym, wieloplatformowym rozwiązaniem do automatyzacji GIS na poziomie przedsiębiorstwa.

## Wymagania wstępne
- Aspose.GIS for .NET Library: Pobierz i zainstaluj bibliotekę z [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/).  
- Document Directory: Utwórz dedykowany folder na swoim komputerze do przechowywania plików GIS.  
- Tymczasowa licencja Aspose (opcjonalnie do oceny) – zobacz FAQ poniżej, aby uzyskać link do pobrania.

## Importowanie przestrzeni nazw
Add the required `using` statements to your C# project so you can access Aspose.GIS classes:

*Nie jest wymagany blok kodu; po prostu dodaj następujące linie na początku pliku:*

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.Geometries.Collections;
using Aspose.Gis.SpatialReference;
```

## Krok 1: Skopiuj katalog
**Definition anchor:** Zbiór danych File GDB jest bazą geodezyjną ESRI opartą na folderze, która przechowuje dane przestrzenne w zestawie plików.  
Najpierw skopiuj folder zawierający oryginalny zestaw danych GDB. Zachowanie kopii chroni dane źródłowe podczas eksperymentów.

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

## Krok 2: Otwórz zestaw danych i zweryfikuj możliwość tworzenia
`Dataset` reprezentuje kolekcję warstw GIS przechowywanych w File GDB. Otwórz nowo skopiowany zestaw danych i potwierdź, że może tworzyć nowe warstwy. Właściwość `CanCreateLayers` powinna zwrócić **True**. **`CanCreateLayers` jest właściwością typu bool, wskazującą, czy zestaw danych obsługuje tworzenie nowych warstw.**

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Krok 3: Utwórz i wypełnij nową warstwę z spatial reference wgs84
Teraz tworzymy warstwę o nazwie **data** i wyraźnie ustawiamy jej odniesienie przestrzenne na **Wgs84**. Dodajemy także prosty atrybut o nazwie **Name** i wstawiamy jedną cechę punktową. **`CreateLayer` tworzy nową warstwę w zestawie danych o podanej nazwie i odniesieniu przestrzennym.** **`SpatialReference` reprezentuje system współrzędnych używany przez warstwę.** **`Feature` jest pojedynczym obiektem geograficznym (punkt, linia lub wielokąt) przechowywanym w warstwie.**

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Krok 4: Otwórz i zweryfikuj dodaną warstwę
Na koniec otwórz warstwę, którą właśnie utworzyłeś, i zweryfikuj jej zawartość. Konsola pokaże, że warstwa zawiera jedną cechę oraz że atrybut **Name** odpowiada temu, co ustawiliśmy. **`Layer.Open` otwiera istniejącą warstwę do odczytu lub edycji.** Potwierdza to, że warstwa została poprawnie dodana i że odniesienie przestrzenne to WGS84.

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

## Jak dodać warstwę do zestawu danych File GDB?
Wczytaj zestaw danych, wywołaj `CreateLayer` z żądaną nazwą i odniesieniem przestrzennym, zdefiniuj schemat atrybutów, a następnie wstaw cechy. Wszystko to można wykonać za pomocą kilku wywołań metod Aspose.GIS, a API automatycznie obsługuje blokowanie plików i walidację schematu. Proces zapewnia, że nowa warstwa jest zgodna z odniesieniem przestrzennym zestawu danych, definicje atrybutów są przechowywane w schemacie warstwy oraz że dane mogą być dostępne w dowolnym oprogramowaniu GIS obsługującym File GDB.

## Typowe problemy i wskazówki
- **Nieprawidłowa ścieżka:** Upewnij się, że `dataDir` kończy się separatorem ścieżki (`/` lub `\`), aby połączone ciągi tworzyły prawidłowe ścieżki plików.  
- **Błędy licencji:** Jeśli pojawią się ostrzeżenia licencyjne, zastosuj tymczasową licencję z portalu Aspose przed uruchomieniem kodu.  
- **Niezgodność CRS:** Podczas otwierania warstwy później w innym narzędziu GIS, upewnij się, że narzędzie rozpoznaje WGS 84 (EPSG:4326) jako system współrzędnych.  
- **Duże zestawy danych:** Dla zestawów danych przekraczających 1 GB, rozważ użycie `Dataset.OpenReadOnly`, aby zmniejszyć zużycie pamięci.

## Najczęściej zadawane pytania
### P: Czy mogę używać Aspose.GIS dla .NET z innymi bibliotekami GIS?
O: Tak, Aspose.GIS działa niezależnie, ale może być łączony z bibliotekami takimi jak GDAL lub NetTopologySuite do zaawansowanego przetwarzania.

### P: Czy dostępna jest tymczasowa licencja do celów testowych?
O: Tak, możesz uzyskać tymczasową licencję z [tutaj](https://purchase.aspose.com/temporary-license/) do testów i oceny.

### P: Jakie systemy odniesień przestrzennych obsługuje Aspose.GIS dla .NET?
O: Aspose.GIS obsługuje ponad **40 kodów EPSG**, w tym popularne systemy takie jak WGS84 (EPSG:4326), Web Mercator (EPSG:3857) i NAD83 (EPSG:4269). Zapoznaj się z pełną dokumentacją [tutaj](https://reference.aspose.com/gis/net/).

### P: Czy mogę przyczynić się do społeczności Aspose.GIS?
O: Zdecydowanie! Dołącz do dyskusji i podziel się swoimi doświadczeniami na [forum Aspose.GIS](https://forum.aspose.com/c/gis/33).

### P: Gdzie mogę znaleźć szczegółową dokumentację Aspose.GIS dla .NET?
O: Zapoznaj się z pełną dokumentacją [tutaj](https://reference.aspose.com/gis/net/) aby uzyskać szczegółowe informacje o wszystkich klasach, metodach i najlepszych praktykach.

---

**Ostatnia aktualizacja:** 2026-06-30  
**Testowano z:** Aspose.GIS for .NET (latest stable version)  
**Autor:** Aspose

{{< blocks/products/products-backtop-button >}}

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Powiązane samouczki

- [Utwórz zestaw danych File Geodatabase .NET przy użyciu Aspose.GIS](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Utwórz warstwę wektorową w File GDB – Samouczek Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Utwórz zestaw danych File GDB i ustaw tolerancje dla warstwy](/gis/net/layer-data-operations/set-tolerances-for-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}