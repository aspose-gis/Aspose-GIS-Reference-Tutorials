---
title: Konwertuj plik kształtu wielokąta na ciąg liniowy
linktitle: Konwertuj plik kształtu wielokąta na ciąg liniowy
second_title: Aspose.GIS .NET API
description: Odkryj moc Aspose.GIS dla .NET i bez wysiłku konwertuj pliki kształtów wielokątnych na ciągi liniowe. Przyspiesz rozwój swojego GIS już dziś!
type: docs
weight: 18
url: /pl/net/layer-management/convert-polygon-shapefile-to-linestring/
---
## Wstęp
Jeśli pracujesz z systemami informacji geograficznej (GIS) w .NET, Aspose.GIS to potężna biblioteka, która może uprościć Twoje zadania. W tym samouczku przeprowadzimy Cię przez proces konwersji pliku kształtu wielokąta na ciąg liniowy za pomocą Aspose.GIS. Może to być szczególnie przydatne, gdy trzeba wyodrębnić cechy liniowe z danych wielokątnych do różnych zastosowań, takich jak planowanie tras lub analiza sieci.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnij się, że masz następujące elementy:
-  Biblioteka Aspose.GIS: Pobierz i zainstaluj bibliotekę Aspose.GIS z[strona internetowa](https://releases.aspose.com/gis/net/).
- Dane pliku kształtu: przygotuj plik kształtu wielokąta do konwersji. Jeśli ich nie masz, możesz znaleźć przykładowe dane lub utworzyć własne.
- Środowisko programistyczne: Skonfiguruj środowisko programistyczne .NET za pomocą niezbędnych narzędzi.
## Importuj przestrzenie nazw
W kodzie C# musisz zaimportować przestrzenie nazw Aspose.GIS, aby uzyskać dostęp do wymaganych klas i metod. Dodaj następujące przestrzenie nazw na początku pliku kodu:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Krok 1: Ustaw katalog dokumentów
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "Your Document Directory";
```
Zastąp „Twój katalog dokumentów” ścieżką do katalogu, w którym znajduje się Twój plik Shapefile.
## Krok 2: Otwórz plik kształtu źródłowego
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Reszta kodu trafi tutaj
}
```
Ten krok otwiera źródłowy plik kształtu wielokąta do odczytu.
## Krok 3: Utwórz plik kształtu docelowego ciągu liniowego
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Reszta kodu trafi tutaj
}
```
Tutaj tworzymy nowy plik Shapestring Linestring do zapisywania przekonwertowanych danych.
## Krok 4: Iteruj po funkcjach źródłowych
```csharp
foreach (Feature sourceFeature in source)
{
    // Reszta kodu trafi tutaj
}
```
Ta pętla wykonuje iterację po każdej funkcji w źródłowym pliku kształtu wielokąta.
## Krok 5: Konwertuj wielokąt na ciąg liniowy i zapisz w miejscu docelowym
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
Na tym etapie każdy element wielokątny jest konwertowany na ciąg liniowy, a wynikowy element ciąg liniowy jest zapisywany w docelowym pliku kształtu.
## Wniosek
Wykonując poniższe kroki, możesz łatwo przekonwertować plik kształtu wielokąta na ciąg liniowy za pomocą Aspose.GIS dla .NET. Proces ten otwiera nowe możliwości analizy i wizualizacji danych w aplikacjach GIS.

## Często zadawane pytania
### Czy Aspose.GIS jest kompatybilny ze wszystkimi wersjami .NET?
Tak, Aspose.GIS obsługuje różne wersje .NET, zapewniając kompatybilność z Twoim środowiskiem programistycznym.
### Czy mogę używać Aspose.GIS w projektach komercyjnych?
 Tak, możesz. Aby używać Aspose.GIS w projektach komercyjnych, rozważ zakup licencji[Tutaj](https://purchase.aspose.com/buy).
### Czy są dostępne jakieś przykłady lub dokumentacja?
 Tak, obszerną dokumentację i przykłady można znaleźć na stronie[strona z dokumentacją](https://reference.aspose.com/gis/net/).
### Czy dostępna jest wersja próbna?
 Tak, możesz eksplorować Aspose.GIS w ramach bezpłatnej wersji próbnej, odwiedzając stronę[ten link](https://releases.aspose.com/).
### Gdzie mogę szukać pomocy lub wsparcia?
 Odwiedzić[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33) w przypadku jakichkolwiek pytań związanych z pomocą lub wsparciem.