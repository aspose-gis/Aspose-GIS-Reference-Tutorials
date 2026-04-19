---
date: 2026-01-10
description: Dowiedz się, jak odczytywać pliki shapefile w C# i konwertować shapefile
  z wielokątem na linię (linestring) przy użyciu Aspose.GIS dla .NET. Zwiększ efektywność
  swojego rozwoju GIS dzięki jasnym, krok po kroku instrukcjom.
linktitle: Convert Polygon Shapefile to Linestring
second_title: Aspose.GIS .NET API
title: Odczyt pliku Shapefile w C# – konwersja shapefile poligonowego na Linestring
url: /pl/net/layer-management/convert-polygon-shapefile-to-linestring/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Odczyt pliku Shapefile C# – Konwersja pliku Shapefile wielokąta na Linestring

## Wprowadzenie
Jeśli pracujesz z systemami informacji geograficznej (GIS) w .NET, **read shapefile c#** jest powszechnym pierwszym krokiem przed manipulacją danymi. Aspose.GIS upraszcza ten proces, umożliwiając konwersję pliku Shapefile wielokąta na Linestring przy użyciu kilku linii kodu. Ta funkcja jest szczególnie przydatna, gdy potrzebujesz wyodrębnić cechy liniowe z zestawów danych wielokątnych do takich zadań jak planowanie tras, analiza sieci czy wizualizacja danych.

## Szybkie odpowiedzi
- **Która biblioteka pomaga w odczycie shapefile c#?** Aspose.GIS for .NET  
- **Czy można przekształcić wielokąt w linię?** Tak – użyj `LineString` z zewnętrznym pierścieniem wielokąta.  
- **Czy potrzebna jest licencja do produkcji?** Wymagana jest licencja komercyjna do użytku produkcyjnego.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Czy dostępna jest wersja próbna?** Oczywiście – pobierz darmową wersję próbną ze strony Aspose.

## Czym jest „read shapefile c#”?
Odczyt pliku shapefile w C# oznacza wczytanie pliku `.shp` do pamięci, aby móc zapytać, modyfikować lub przekształcać jego geometrie. Aspose.GIS udostępnia prosty interfejs API, który ukrywa szczegóły niskiego poziomu i pozwala skupić się na logice GIS.

## Dlaczego konwertować wielokąt na linię przy użyciu Aspose.GIS?
- **Zachowanie topologii** – konwersja zachowuje dokładny zewnętrzny obrys każdego wielokąta.  
- **Wydajność** – biblioteka jest zoptymalizowana pod kątem dużych zestawów danych, co przyspiesza konwersje wsadowe.  
- **Elastyczność** – możesz później zapisać linestringi do innego pliku shapefile, GeoJSON lub dowolnego obsługiwanego formatu.

## Wymagania wstępne
Zanim przejdziemy do samouczka, upewnij się, że masz następujące elementy:

- **Aspose.GIS Library** – Pobierz i zainstaluj bibliotekę Aspose.GIS ze [strony internetowej](https://releases.aspose.com/gis/net/).  
- **Shapefile Data** – Przygotuj plik Shapefile wielokąta gotowy do konwersji. Jeśli go nie masz, możesz znaleźć przykładowe dane lub stworzyć własny.  
- **Development Environment** – Skonfiguruj środowisko programistyczne .NET z niezbędnymi narzędziami (Visual Studio, .NET SDK itp.).

## Importowanie przestrzeni nazw
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

## Jak przekonwertować shapefile z wielokąta na linię?
Poniżej znajduje się przewodnik krok po kroku, który pokazuje **jak przekonwertować shapefile** z wielokąta na linię przy użyciu Aspose.GIS.

### Krok 1: Ustaw katalog dokumentu
```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```
Zastąp `"Your Document Directory"` rzeczywistą ścieżką, w której znajduje się Twój plik shapefile.

### Krok 2: Otwórz źródłowy shapefile
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
Ten wiersz **otwiera źródłowy plik Polygon Shapefile**, abyś mógł odczytać jego elementy.

### Krok 3: Utwórz docelowy shapefile Linestring
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
Tutaj **tworzymy nowy Linestring Shapefile**, który będzie przechowywał przekonwertowane geometrie.

### Krok 4: Iteruj przez elementy źródłowe
```csharp
foreach (Feature sourceFeature in source)
{
    // Rest of the code will go here
}
```
Pętla przechodzi przez każdy element wielokąta w oryginalnym pliku.

### Krok 5: Konwertuj wielokąt na Linestring i zapisz do docelowego pliku
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
W tym bloku **konwertujemy wielokąt na linię** (`LineString`) i dodajemy nowy element do docelowego shapefile.

## Typowe problemy i wskazówki
- **Niezgodność układu współrzędnych** – Upewnij się, że zarówno warstwa źródłowa, jak i docelowa używają tego samego odniesienia przestrzennego; w przeciwnym razie linie mogą być przesunięte.  
- **Duże pliki** – Przy przetwarzaniu bardzo dużych shapefile rozważ strumieniowe przetwarzanie elementów zamiast ładowania ich wszystkich do pamięci jednocześnie.  
- **Puste geometrie** – Zabezpiecz się przed elementami z pustymi geometriami, aby uniknąć wyjątków w czasie wykonywania.

## Najczęściej zadawane pytania

**P: Czy Aspose.GIS jest kompatybilny ze wszystkimi wersjami .NET?**  
O: Tak, Aspose.GIS obsługuje różne wersje .NET, zapewniając kompatybilność z Twoim środowiskiem programistycznym.

**P: Czy mogę używać Aspose.GIS w projektach komercyjnych?**  
O: Tak, możesz. Aby używać Aspose.GIS w projektach komercyjnych, rozważ zakup licencji [tutaj](https://purchase.aspose.com/buy).

**P: Czy dostępne są przykłady lub dokumentacja?**  
O: Tak, możesz znaleźć pełną dokumentację i przykłady na [stronie dokumentacji](https://reference.aspose.com/gis/net/).

**P: Czy dostępna jest wersja próbna?**  
O: Tak, możesz wypróbować Aspose.GIS w wersji próbnej, odwiedzając [ten link](https://releases.aspose.com/).

**P: Gdzie mogę uzyskać pomoc lub wsparcie?**  
O: Odwiedź [forum Aspose.GIS](https://forum.aspose.com/c/gis/33), aby uzyskać pomoc lub odpowiedzi na pytania związane ze wsparciem.

---

**Ostatnia aktualizacja:** 2026-01-10  
**Testowano z:** Aspose.GIS for .NET (latest release)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}