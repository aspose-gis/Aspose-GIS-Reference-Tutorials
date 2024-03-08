---
title: Konwertuj GeoJSON na TopoJSON z określoną nazwą obiektu
linktitle: Konwertuj GeoJSON na TopoJSON z określoną nazwą obiektu
second_title: Aspose.GIS .NET API
description: Dowiedz się, jak przekonwertować GeoJSON na TopoJSON z określoną nazwą obiektu przy użyciu Aspose.GIS dla .NET. Ten samouczek zawiera przewodnik krok po kroku dotyczący wydajnej manipulacji danymi geograficznymi.
type: docs
weight: 12
url: /pl/net/geo-data-conversion/convert-geojson-to-topojson-with-specific-object-name/
---
## Wstęp
Aspose.GIS dla .NET to potężne narzędzie do pracy z danymi geograficznymi w aplikacjach .NET. Niezależnie od tego, czy tworzysz aplikację mapującą, analizujesz dane przestrzenne, czy manipulujesz plikami geojson, Aspose.GIS zapewnia kompleksowy zestaw funkcji usprawniających przepływ pracy.
## Warunki wstępne
Zanim zajmiemy się konwersją GeoJSON na TopoJSON z określoną nazwą obiektu przy użyciu Aspose.GIS dla .NET, upewnij się, że masz następujące elementy:
### 1. Zainstaluj Aspose.GIS dla .NET
 Udaj się do[strona pobierania](https://releases.aspose.com/gis/net/) i pobierz najnowszą wersję Aspose.GIS dla .NET.
### 2. Skonfiguruj swoje środowisko programistyczne
Upewnij się, że w systemie skonfigurowano program Visual Studio lub inne środowisko programistyczne .NET.
### 3. Przygotuj plik GeoJSON
Masz plik GeoJSON, który chcesz przekonwertować na TopoJSON. Jeśli go nie masz, w tym samouczku możesz użyć dowolnego przykładowego pliku GeoJSON.

## Importuj przestrzenie nazw
Zanim rozpoczniemy proces konwersji, zaimportujmy niezbędne przestrzenie nazw:
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Krok 1: Zdefiniuj ścieżki plików
```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithObjectName_out.topojson";
```
 Zastępować`"Your Document Directory"` rzeczywistą ścieżką katalogu, w którym znajduje się plik GeoJSON i gdzie chcesz zapisać przekonwertowany plik TopoJSON.
## Krok 2: Ustaw opcje konwersji
```csharp
var options = new ConversionOptions
{
    DestinationDriverOptions = new TopoJsonOptions
    {
        // określ nazwę obiektu, w którym mają zostać zapisane cechy
        DefaultObjectName = "name_of_the_object",
    }
};
```
 Na tym etapie tworzymy plik`ConversionOptions` obiekt i określić`DefaultObjectName`, czyli nazwa obiektu, w którym mają zostać zapisane funkcje w wynikowym pliku TopoJSON.
## Krok 3: Wykonaj konwersję
```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```
 Na koniec nazywamy`Convert` metoda`VectorLayer` class, przekazując ścieżkę wejściowego pliku GeoJSON, sterowniki wejściowe i wyjściowe oraz opcje konwersji.

## Wniosek
W tym samouczku nauczyliśmy się, jak przekonwertować GeoJSON na TopoJSON z określoną nazwą obiektu przy użyciu Aspose.GIS dla .NET. Wykonując poniższe kroki, można efektywnie zarządzać danymi geograficznymi i manipulować nimi w aplikacjach .NET.
## Często zadawane pytania
### Czy mogę używać Aspose.GIS dla .NET w moich projektach komercyjnych?
Tak, możesz używać Aspose.GIS dla .NET zarówno w projektach komercyjnych, jak i osobistych.
### Czy dostępna jest bezpłatna wersja próbna Aspose.GIS dla .NET?
Tak, możesz uzyskać bezpłatną wersję próbną od[Tutaj](https://releases.aspose.com/).
### Gdzie mogę znaleźć wsparcie dla Aspose.GIS dla .NET?
 Możesz uzyskać wsparcie od[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33).
### Jak mogę kupić licencję na Aspose.GIS dla .NET?
 Możesz kupić licencję od[Tutaj](https://purchase.aspose.com/buy).
### Czy potrzebuję tymczasowej licencji do oceny?
 Tak, możesz uzyskać licencję tymczasową od[Tutaj](https://purchase.aspose.com/temporary-license/).