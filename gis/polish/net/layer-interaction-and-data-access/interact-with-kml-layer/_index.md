---
date: 2026-05-26
description: Dowiedz się, jak tworzyć warstwę KML w C# przy użyciu Aspose.GIS dla
  .NET. Przewodnik krok po kroku, jak manipulować danymi geoprzestrzennymi, z fragmentami
  kodu i najlepszymi praktykami. Pobierz darmową wersję próbną już teraz!
keywords:
- create kml layer c#
- Aspose.GIS .NET
- geospatial data C#
linktitle: Interakcja z warstwą KML
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to create KML layer C# using Aspose.GIS for .NET. Step‑by‑step
    guide to manipulate geospatial data, with code snippets and best practices. Download
    the free trial now!
  headline: How to Create KML Layer in C# with Aspose.GIS
  type: TechArticle
- questions:
  - answer: Yes – Aspose.GIS lets you create KML layers programmatically.
    question: Can I generate KML files with C#?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  - answer: A free trial works for evaluation; a license is required for production.
    question: Do I need a license for development?
  - answer: Over 30 input and output formats, including KML, Shapefile, GeoJSON, and
      GML.
    question: How many GIS formats does Aspose.GIS handle?
  - answer: Files up to 2 GB are processed without loading the entire document into
      memory.
    question: Is there a size limit for KML files?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Jak utworzyć warstwę KML w C# przy użyciu Aspose.GIS
url: /pl/net/layer-interaction-and-data-access/interact-with-kml-layer/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć warstwę KML w C# przy użyciu Aspose.GIS

## Wprowadzenie
Jeśli potrzebujesz szybko i niezawodnie **create KML layer C#** kod, Aspose.GIS dla .NET zapewnia w pełni funkcjonalne API działające na każdej platformie .NET. W tym samouczku przeprowadzimy Cię przez dokładne kroki niezbędne do zbudowania warstwy KML, dodania atrybutów, wypełnienia obiektów i zapisania pliku — wszystko bez opuszczania Visual Studio. Po zakończeniu zrozumiesz, dlaczego Aspose.GIS jest gotowym do produkcji rozwiązaniem do manipulacji danymi geoprzestrzennymi.

## Szybkie odpowiedzi
- **Czy mogę generować pliki KML w C#?** Tak – Aspose.GIS umożliwia programowe tworzenie warstw KML.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Czy potrzebuję licencji do rozwoju?** Darmowa wersja próbna działa w celach oceny; licencja jest wymagana w produkcji.  
- **Ile formatów GIS obsługuje Aspose.GIS?** Ponad 30 formatów wejściowych i wyjściowych, w tym KML, Shapefile, GeoJSON i GML.  
- **Czy istnieje limit rozmiaru plików KML?** Pliki do 2 GB są przetwarzane bez ładowania całego dokumentu do pamięci.

## Czym jest warstwa KML?
Warstwa KML jest kontenerem danych geograficznych, który przechowuje znaczniki, style i geometrie w formacie Keyhole Markup Language, szeroko używanym w mapach internetowych i Google Earth. Może zawierać punkty, linie, wielokąty oraz powiązane metadane, umożliwiając bogate wizualizacje w przeglądarkach, aplikacjach GIS i Google Earth. Format oparty jest na XML, co czyni go zarówno czytelnym dla człowieka, jak i przetwarzalnym przez maszyny.

## Dlaczego warto używać Aspose.GIS do tworzenia warstw KML?
Aspose.GIS obsługuje **30+ formatów GIS** i może przetwarzać **pliki o rozmiarze setek megabajtów**, utrzymując zużycie pamięci poniżej 100 MB dzięki architekturze strumieniowej. Biblioteka zapewnia także **100 % zgodność ze schematem**, więc wygenerowany KML działa bezbłędnie we wszystkich głównych przeglądarkach. Dodatkowo biblioteka oferuje wbudowaną walidację i automatyczną obsługę układów odniesienia współrzędnych, więc nie potrzebujesz zewnętrznych narzędzi, aby zapewnić zgodność.

## Wymagania wstępne
Przed rozpoczęciem upewnij się, że masz spełnione następujące wymagania:
- Aspose.GIS for .NET: Pobierz i zainstaluj bibliotekę ze [strony pobierania Aspose.GIS dla .NET](https://releases.aspose.com/gis/net/).
- Środowisko programistyczne: Skonfiguruj odpowiednie środowisko programistyczne, takie jak Visual Studio, aby płynnie zintegrować Aspose.GIS z projektami .NET.

Teraz zanurzmy się w samouczek.

## Importowanie przestrzeni nazw
Przestrzeń nazw `Aspose.Gis` dostarcza podstawowe klasy do pracy z danymi GIS. Importowanie jej zapewnia dostęp do `KmlLayer`, `Feature` oraz narzędzi obsługi atrybutów.

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Drawing;
using System.Threading;
using Aspose.Gis.Formats.Kml;
using Aspose.Gis.Formats.Kml.Styles;
using Aspose.Gis.Geometries;
using Point = Aspose.Gis.Geometries.Point;
```

## Jak utworzyć warstwę KML w C#?
Załaduj docelowy katalog, utwórz obiekt `KmlLayer` z żądaną nazwą pliku i wywołaj `Save()` – to wszystko, czego potrzebujesz, aby wygenerować prawidłowy plik KML. API automatycznie zapisuje wymaganą strukturę XML, więc nie musisz samodzielnie zarządzać niskopoziomowym markupem.

## Krok 1: Ustaw katalog dokumentu
Zdefiniuj ścieżkę do katalogu dokumentów, w którym będą przechowywane pliki KML.

```csharp
string dataDir = "Your Document Directory";
```

## Krok 2: Utwórz warstwę KML
Klasa `KmlLayer` jest reprezentacją pliku KML na dysku w Aspose.GIS. Inicjalizacja jej przy użyciu ścieżki pliku tworzy pustą warstwę gotową na obiekty.

```csharp
using (var layer = Drivers.Kml.CreateLayer(dataDir + "Kml_File_out.kml"))
{
```

## Krok 3: Zdefiniuj atrybuty
`FeatureAttribute` reprezentuje definicję kolumny dla obiektu, określając jej nazwę i typ danych. Dodaj atrybuty do warstwy KML, aby reprezentować różne typy danych, takie jak string, integer, boolean i double.

```csharp
layer.Attributes.Add(new FeatureAttribute("string_data", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("int_data", AttributeDataType.Integer));
layer.Attributes.Add(new FeatureAttribute("bool_data", AttributeDataType.Boolean));
layer.Attributes.Add(new FeatureAttribute("float_data", AttributeDataType.Double));
```

## Krok 4: Tworzenie i wypełnianie obiektów
`Feature` jest obiektem, który przechowuje geometrię i wartości atrybutów dla pojedynczego rekordu GIS. Twórz obiekty reprezentujące jednostki geoprzestrzenne i ustawiaj wartości dla zdefiniowanych atrybutów.

```csharp
Feature feature = layer.ConstructFeature();
feature.SetValue("string_data", "string value");
feature.SetValue("int_data", 10);
feature.SetValue("bool_data", true);
feature.SetValue("float_data", 3.14);
feature.Geometry = new LineString(new[] { new Point(0, 0), new Point(1, 1) });
layer.Add(feature);
```

## Krok 5: Dodaj kolejny obiekt
Powtórz proces, aby dodać drugi obiekt z innymi wartościami atrybutów i geometrią równą null.

```csharp
Feature feature2 = layer.ConstructFeature();
feature2.SetValue("string_data", "string value2");
feature2.SetValue("int_data", 100);
feature2.SetValue("bool_data", false);
feature2.SetValue("float_data", 3.1415);
feature2.Geometry = Geometry.Null;
layer.Add(feature2);
```

## Częste problemy i rozwiązania
- **Ostrzeżenie o null geometry** – Jeśli obiekt nie ma geometrii, upewnij się, że przed zapisem jawnie ustawisz geometrię na `null`; w przeciwnym razie API może zgłosić wyjątek.  
- **Niezgodność typu atrybutu** – Przypisywana wartość musi odpowiadać zadeklarowanemu typowi atrybutu; w przeciwnym razie wystąpi błąd w czasie wykonywania.  
- **Błędy ścieżki pliku** – Używaj ścieżek bezwzględnych lub sprawdź, czy aplikacja ma uprawnienia do zapisu w docelowym folderze.

## Najczęściej zadawane pytania

### Czy Aspose.GIS jest kompatybilny z innymi formatami GIS?
Tak, Aspose.GIS obsługuje różne formaty GIS, w tym shapefile, GeoJSON i KML.

### Czy mogę wizualizować dane geoprzestrzenne utworzone przy użyciu Aspose.GIS?
Zdecydowanie! Aspose.GIS płynnie integruje się z bibliotekami mapującymi, umożliwiając wizualizację Twoich danych geoprzestrzennych.

### Czy dostępna jest wersja próbna Aspose.GIS?
Tak, możesz zapoznać się z funkcjami Aspose.GIS, pobierając [wersję próbną](https://releases.aspose.com/).

### Jak mogę uzyskać wsparcie dla Aspose.GIS?
Odwiedź [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) w celu uzyskania wsparcia społeczności lub zapoznaj się z opcjami wsparcia premium [tutaj](https://purchase.aspose.com/buy).

### Czy dostępne są tymczasowe licencje dla Aspose.GIS?
Tak, możesz uzyskać tymczasową licencję [tutaj](https://purchase.aspose.com/temporary-license/).

---

**Ostatnia aktualizacja:** 2026-05-26  
**Testowano z:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose

## Powiązane samouczki

- [Jak zmodyfikować warstwę – Interakcja warstw Aspose.GIS .NET](/gis/net/layer-interaction-and-data-access/)
- [Pobierz atrybuty warstwy – Uzyskaj informacje o atrybutach warstwy przy użyciu Aspose.GIS dla .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Jak przyciąć obiekty warstwy przy użyciu Aspose.GIS dla .NET](/gis/net/layer-management/crop-layer-features/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}