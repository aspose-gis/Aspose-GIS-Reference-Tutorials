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

# odniesienie przestrzenne wgs84 – Dodawanie swatwy do GDB przy szączy Aspose.GIS

## Wstęp
Gotowy, aby przyspieszyć swój poław pracy GIS z Aspose.GIS dla .NET? W tym samouczku dowiesz się **jak addatz stawstę do setawu danych Plik GDB** z łążedem z łądyem wspórzydąnych **odniesienie przestrzenne wgs84**. Przeprowadzimy Cię krok po kroku, od przygotowania folderu z danych po werifikakę nowo utvoronej stawtwy, możesz móc pożyce manipulować danymi geograficznymi.

## Szybkie odpowiedzi
- **Jaki jest podstawowy łady współczesny?** odniesienie przestrzenne wgs84 (WGS84)
- **Kiedy biblioteka udostępni API?** Aspose.GIS dla .NET
- **Czy istnieje licencja do testów?** Tak – geguna jest tymczasowa licencja Aspose.
- **Czy mógő addat atrybuty do nowej stawtwy?** Oczywiście, możesz określić nowe atrybuty obekt.
- **Czy jakieś wersje .NET są obschiwane?** .NET Framework4.5+, .NET Core3.1+, .NET5/6.

## Co to jest odniesienie przestrzenne wgs84?
Układ współrzędnych odniesień przestrzennych wgs84 (World Geodetic System 1984) jest najpowszechniejszym uświęcim geograficznym systemem wspórzydąnych. Definiuje serokość i ługną geograficzną w stepniach i jest domyślnym CRS dla wielu zestawów danych GIS, w tym tym kóry utworzymy w tym przedowniku.

## Po co używać Aspose.GIS do dodawania warstwy?
- **Brak zewnętrznych zależności:** Działa od razu z czystym kodem .NET.
- **Pełna kontrola nad schematem:** Możesz zdefiniować własne atrybuty i typy geometrii.
- **Wieloplatformowość:** Zgodność z systemami Windows, Linux i macOS.
- **Licencja Solidna:** Licencja Tymczasowa pojumą szybko ocenić produkt przed decyzją.

## Warunki wstępne
Zanim przygotujz, upewnij się, że masz:

- Biblioteka Aspose.GIS dla .NET: Pobierz i zainstallaj bibliotekę z [Dokumentacja Aspose.GIS dla .NET](https://reference.aspose.com/gis/net/).
- Katalog dokumentów: Utwórz folder dodatkowy na swoim komputerze, w kieromie będź przychowanych plików GIS.

## Importuj przestrzenie nazw
Dodaj wymagane dyrektywy „using” do swojego projektu C#, aby używać klasy Aspose.GIS:

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

## Krok 1: Kopiowanie katalogu
Najpierw skopiuj folder zawierający oryginalny zestaw danych GDB. Posiadanie kopii chroni dane źródłowe podczas eksperymentów.

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Krok 2: Otwieranie zbioru danych i weryfikacja możliwości tworzenia
Otwórz nowo skopiowany zestaw danych i potwierdź, że można w nim tworzyć nowe warstwy. Właściwość `CanCreateLayers` powinna zwrócić **True**.

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Krok 3: Utworzenie i wypełnienie nowej warstwy odniesieniem przestrzennym wgs84
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

## Krok 4: Otwieranie i weryfikacja dodanej warstwy
Na koniec otwieramy warstwę, którą właśnie utworzyliśmy, i weryfikujemy jej zawartość. Konsola pokaże, że warstwa zawiera jedną cechę oraz że atrybut **Name** jest zgodny z ustawioną wartością.

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Typowe problemy i wskazówki
- **Nieprawidłowa piżka:** Upewnij się, że `dataDir` kończy się separatorem piśżki (`/` lub `\`), aby połączone pliki utworzyły się poprawnie.
- **Błędy licencyjne:** Jej pojawienie się następuje o licencji, uruchamianej tymczasową licencją z portalu Aspose przed wydaniem kodu.
- **Niezgodność CRS:** Przy otwieraniu swastwy w innym żyłęcieu GIS, sprawdź, czy wyżęty rozpoznaje WGS84 (EPSG:4326) jako system współorządnych.

## Często zadawane pytania
### P: Czy mogę używać Aspose.GIS dla .NET wraz z innymi bibliotekami GIS?
Aspose.GIS dla .NET jest zaprojektowany do pracy zadznejnej, ale może być zintegrowany z innymi bibliotekami w celu rozszenia funksiółości.

### P: Czy geguna jest tymczasową licencją do cerzul testowych?
Tak, tymczasową szkodę poża obtujące [tutaj](https://purchase.aspose.com/temporary-license/) do testów i oczy.

### P: Jakie systemy monitorowania przestrzennego obstavlja Aspose.GIS dla .NET?
Aspose.GIS dla .NET obsługuje szeroką gamę systemów, zapewniając elastyczność w obsłudze danych geograficznych.

### P: Czy mogę wnieść swój wkład do Aspose.GIS?
Oczywiście! Dołącz do discuzi i podzieł się prącznościami na [forum Aspose.GIS](https://forum.aspose.com/c/gis/33).

### P: Gdzie znaleźć pościową dokumentację Aspose.GIS dla .NET?
Kompletna dokumentacja cinciądze [tutaj](https://reference.aspose.com/gis/net/) – zawiera deszeciący informacje o Aspose.GIS dla .NET.

---

**Ostatnia aktualizacja:** 13.01.2026
**Testowano z:** Aspose.GIS dla .NET (najnowsza wersja stabilna)
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
