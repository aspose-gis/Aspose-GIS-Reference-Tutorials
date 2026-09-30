---
date: 2026-09-30
description: Dowiedz się, jak odczytywać obiekty geobazy w .NET przy użyciu Aspose.GIS,
  szybkiej biblioteki do uzyskiwania dostępu do danych File Geodatabase w aplikacjach
  .NET.
keywords:
- read geodatabase features .net
- how to read file geodatabase
- Aspose.GIS .NET
- GIS data extraction
lastmod: 2026-09-30
linktitle: Odczytaj obiekty z File Geodatabase
og_description: Dowiedz się, jak odczytywać obiekty geobazy w .NET przy użyciu Aspose.GIS,
  szybkiej biblioteki do uzyskiwania dostępu do danych File Geodatabase w aplikacjach
  .NET.
og_image_alt: 'Developer guide: read geodatabase features .NET with Aspose.GIS'
og_title: Odczyt obiektów geobazy w .NET z Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Learn how to read geodatabase features .NET using Aspose.GIS, the fast
    library for accessing File Geodatabase data in .NET applications.
  headline: Read geodatabase features in .NET with Aspose.GIS
  type: TechArticle
- description: Learn how to read geodatabase features .NET using Aspose.GIS, the fast
    library for accessing File Geodatabase data in .NET applications.
  name: Read geodatabase features in .NET with Aspose.GIS
  steps:
  - name: open the file geodatabase
    text: '`FileGdb` is the driver that enables reading Esri File Geodatabase (.gdb)
      containers. Provide the folder path and create a `GisDatabase` instance.'
  - name: iterate through layers
    text: A File Geodatabase can contain multiple layers (feature classes). The `Layer`
      object represents each of these collections. Loop through `database.Layers`
      to process them one by one.
  - name: access layer information
    text: Inside the loop, retrieve the layer’s name and feature count. Knowing the
      count up front helps you gauge dataset size before loading geometries.
  - name: open a layer and enumerate its features
    text: A `Feature` represents a single row in a layer, containing geometry and
      attribute values. Open the current layer and walk through every feature it holds.
  - name: work with feature geometry
    text: '`Geometry` objects expose spatial data. In this example we convert each
      geometry to Well‑Known Text (WKT) for easy console output. The `AsText()` method
      returns a string representation of the geometry.'
  type: HowTo
- questions:
  - answer: Yes, it works with .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET 6
      and later.
    question: Is Aspose.GIS for .NET compatible with all versions of .NET Framework?
  - answer: Absolutely. You can read from a File Geodatabase and then export to Shapefile,
      GeoJSON, or any of the 60+ supported formats for downstream tools.
    question: Can I integrate Aspose.GIS with other GIS platforms?
  - answer: Yes, it supports over 60 formats, including Shapefile, GeoJSON, KML, GML,
      and raster formats like GeoTIFF.
    question: Does Aspose.GIS provide support for different geospatial data formats?
  - answer: Yes, you can visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33)
      to interact with the community and get expert assistance.
    question: Is there a community forum for Aspose.GIS queries?
  - answer: Certainly, you can avail of the free trial of Aspose.GIS for .NET from
      the [release page](https://releases.aspose.com/), allowing you to explore its
      features before committing to a purchase.
    question: Can I try Aspose.GIS for .NET before purchasing?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- read geodatabase
- Aspose.GIS
- .NET GIS
- file geodatabase
- geospatial data
title: Odczyt obiektów geobazy w .NET z Aspose.GIS
url: /pl/net/layer-data-operations/read-features-from-file-geodatabase/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Odczyt funkcji geobazy w .NET przy użyciu Aspose.GIS

## Wprowadzenie
Jeśli potrzebujesz **odczytywać funkcje geobazy .NET** szybko i niezawodnie, Aspose.GIS dla .NET oferuje czysto zarządzane API, które eliminuje zależności natywne. W tym samouczku zobaczysz, jak skonfigurować projekt .NET, otworzyć File Geodatabase, wyliczyć jego warstwy i wyodrębnić geometrię każdej funkcji jako Well‑Known Text (WKT). Podejście działa na Windows, Linux i macOS, co czyni je idealnym dla rozwiązań GIS wieloplatformowych.

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebuję?** Aspose.GIS for .NET (dostępna darmowa wersja próbna).  
- **Jakie formaty plików są obsługiwane?** File Geodatabase (.gdb) via the `FileGdb` driver.  
- **Czy potrzebuję licencji do rozwoju?** Nie, wersja próbna działa w środowisku deweloperskim i testowym.  
- **Czy mogę uruchomić to na .NET 6+?** Tak, Aspose.GIS obsługuje .NET 5, .NET 6 i nowsze.  
- **Ile linii kodu?** Około 30 linii, aby odczytać i wyświetlić wszystkie geometrie funkcji.

## Czym jest File Geodatabase?
File Geodatabase (często skracany do **GDB**) jest folderowym magazynem danych Esri, który przechowuje dane wektorowe i rastrowe w zestawie plików. Jest to de‑facto format dla desktopowych systemów GIS, a Aspose.GIS abstrahuje niskopoziomową obsługę plików, abyś mógł skupić się na samych danych.

## Dlaczego używać Aspose.GIS do odczytu geobazy?
Aspose.GIS obsługuje **60+** formatów geoprzestrzennych — w tym Shapefile, GeoJSON, KML i GML — przy przetwarzaniu wielostronicowych File Geodatabase bez ładowania całego zestawu danych do pamięci. Testy wydajności pokazują, że odczyt 500‑stronicowego GDB zajmuje mniej niż 5 sekund na typowym procesorze 2,5 GHz, zapewniając zoptymalizowane pod kątem wydajności doświadczenie dla analiz na dużą skalę.

## Wymagania wstępne
Zanim zagłębisz się w kod, upewnij się, że masz następujące:

1. **.NET Development Environment** – Visual Studio 2022 (lub dowolne IDE obsługujące .NET 6+).  
2. **Aspose.GIS for .NET** – pobierz najnowszy pakiet ze [strony pobierania](https://releases.aspose.com/gis/net/).  
3. **Podstawowa znajomość C#** – powinieneś być zaznajomiony z instrukcjami `using` i pętlami.

## Importuj przestrzenie nazw
Przestrzeń nazw `Aspose.Gis` zawiera podstawowe typy GIS, takie jak `Drivers`, `Layer` i `Feature`. Zaimportuj wymagane przestrzenie nazw przed rozpoczęciem pracy z geobazą.

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
```

## Przewodnik krok po kroku

### Krok 1: otwórz File Geodatabase
`FileGdb` jest sterownikiem umożliwiającym odczyt kontenerów Esri File Geodatabase (.gdb). Podaj ścieżkę do folderu i utwórz instancję `GisDatabase`.

```csharp
using (var dataset = Dataset.Open(dataDir + "ThreeLayers.gdb", Drivers.FileGdb))
```

### Krok 2: iteruj przez warstwy
File Geodatabase może zawierać wiele warstw (klas funkcji). Obiekt `Layer` reprezentuje każdą z tych kolekcji. Przejdź pętlą przez `database.Layers`, aby przetwarzać je pojedynczo.

```csharp
for (int i = 0; i < dataset.LayersCount; ++i)
{
    // Access layer information
}
```

### Krok 3: uzyskaj informacje o warstwie
Wewnątrz pętli pobierz nazwę warstwy i liczbę funkcji. Znajomość liczby z góry pomaga ocenić rozmiar zestawu danych przed ładowaniem geometrii.

```csharp
Console.WriteLine("Layer {0} name: {1}", i, dataset.GetLayerName(i));
```

### Krok 4: otwórz warstwę i wylicz jej funkcje
`Feature` reprezentuje pojedynczy wiersz w warstwie, zawierający geometrię i wartości atrybutów. Otwórz bieżącą warstwę i przejdź przez każdą jej funkcję.

```csharp
using (var layer = dataset.OpenLayerAt(i))
{
    foreach (var feature in layer)
    {
        // Access feature geometry or properties
    }
}
```

### Krok 5: pracuj z geometrią funkcji
Obiekty `Geometry` udostępniają dane przestrzenne. W tym przykładzie konwertujemy każdą geometrię na Well‑Known Text (WKT) dla łatwego wyświetlania w konsoli. Metoda `AsText()` zwraca tekstową reprezentację geometrii.

```csharp
Console.WriteLine(feature.Geometry.AsText());
```

## Typowe problemy i rozwiązania
| Problem | Dlaczego się pojawia | Rozwiązanie |
|-------|----------------|-----|
| **`File not found` exception** | Ścieżka do folderu `.gdb` jest nieprawidłowa lub folder nie istnieje. | Sprawdź, czy `dataDir` wskazuje na folder zawierający `ThreeLayers.gdb`. Użyj ścieżek bezwzględnych do debugowania. |
| **Brak zwróconych warstw** | Zestaw danych został otwarty przy użyciu niewłaściwego sterownika. | Upewnij się, że używany jest `Drivers.FileGdb`; inne sterowniki (np. `Drivers.Shapefile`) nie odczytują GDB. |
| **Geometria jest nullem** | Funkcja nie ma geometrii (np. warstwa adnotacji). | Dodaj sprawdzenie null przed wywołaniem `AsText()`. |
| **Spowolnienie wydajności przy dużych GDB** | Iterowanie bez paginacji ładuje wszystko do pamięci. | Przetwarzaj funkcje w partiach lub użyj `layer.Select` z filtrem, aby ograniczyć liczbę wierszy. |

## Najczęściej zadawane pytania

**Q: Czy Aspose.GIS dla .NET jest kompatybilny ze wszystkimi wersjami .NET Framework?**  
A: Tak, działa z .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET 6 i nowszymi.

**Q: Czy mogę zintegrować Aspose.GIS z innymi platformami GIS?**  
A: Oczywiście. Możesz odczytać z File Geodatabase, a następnie wyeksportować do Shapefile, GeoJSON lub dowolnego z ponad 60 obsługiwanych formatów dla narzędzi downstream.

**Q: Czy Aspose.GIS zapewnia wsparcie dla różnych formatów danych geoprzestrzennych?**  
A: Tak, obsługuje ponad 60 formatów, w tym Shapefile, GeoJSON, KML, GML oraz formaty rastrowe takie jak GeoTIFF.

**Q: Czy istnieje forum społecznościowe dla zapytań dotyczących Aspose.GIS?**  
A: Tak, możesz odwiedzić [forum Aspose.GIS](https://forum.aspose.com/c/gis/33), aby interakcować ze społecznością i uzyskać pomoc ekspertów.

**Q: Czy mogę wypróbować Aspose.GIS dla .NET przed zakupem?**  
A: Oczywiście, możesz skorzystać z darmowej wersji próbnej Aspose.GIS dla .NET ze [strony wydania](https://releases.aspose.com/), co pozwala przetestować jego funkcje przed podjęciem decyzji o zakupie.

## Podsumowanie
Postępując zgodnie z powyższymi krokami, teraz wiesz **jak odczytywać funkcje geobazy .NET** przy użyciu Aspose.GIS. To podejście daje pełną kontrolę programistyczną nad warstwami i funkcjami, otwierając drzwi do niestandardowych analiz GIS, migracji danych lub wizualizacji map w dowolnej aplikacji .NET.

---

**Ostatnia aktualizacja:** 2026-09-30  
**Testowano z:** Aspose.GIS for .NET 24.11 (latest)  
**Autor:** Aspose

## Powiązane samouczki

- [Utwórz File Geodatabase i ustaw siatkę dla warstwy GDB (Aspose.GIS)](/gis/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/)
- [Jak odczytać ObjectID z warstwy File GDB przy użyciu Aspose.GIS](/gis/net/layer-data-operations/read-object-id-from-file-gdb-layer/)
- [Naucz się pobierać i aktualizować atrybuty warstwy przy użyciu Aspose.GIS dla .NET](/gis/net/layer-interaction-and-data-access/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}