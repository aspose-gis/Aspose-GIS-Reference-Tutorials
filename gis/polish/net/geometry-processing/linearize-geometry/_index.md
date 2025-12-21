---
date: 2025-12-21
description: Dowiedz się, jak liniaryzować geometrię przy użyciu Aspose.GIS dla .NET,
  umożliwiając efektywne przetwarzanie danych geoprzestrzennych, analizę przestrzenną
  i manipulację geometrią w aplikacjach .NET.
linktitle: Linearize a Geometry
second_title: Aspose.GIS .NET API
title: Jak zlinearyzować geometrię przy użyciu Aspose.GIS dla .NET
url: /pl/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Liniaryzacja geometrii

## Wstęp
Jeśli potrzebujesz **jak liniaryzować geometrię** do mapowania, analizy przestrzennej lub zadań wymiany danych, Aspose.GIS dla .NET zapewnia czysty, programowy sposób na to. W tym samouczku przeprowadzimy Cię przez kompletny, rzeczywisty przykład, który pokazuje, jak wziąć złożoną geometrię — zawierającą krzywe i kształty złożone — i przekształcić ją w prostą liniową reprezentację, działającą w każdym systemie GIS.

## Szybkie odpowiedzi
- **Co oznacza liniaryzacja geometrii?** Konwersja krzywych i złożonych kształtów na odcinki prostych linii.  
- **Dlaczego używać Aspose.GIS?** Obsługuje dziesiątki formatów GIS i radzi sobie z konwersją geometrii bez zewnętrznych narzędzi.  
- **Wymagania wstępne?** .NET Framework lub .NET Core, Visual Studio oraz biblioteka Aspose.GIS.  
- **Jak długo trwa przykład?** Mniej niż pięć minut po zainstalowaniu biblioteki.  
- **Czy mogę zapisać w innych formatach?** Tak — zamień sterownik KML na Shapefile, GeoJSON itp.

## Co to jest liniaryzacja geometrii?
Liniaryzacja geometrii oznacza rozbicie dowolnego zakrzywionego lub złożonego kształtu na szereg odcinków prostych linii (tzw. „geometria liniowa”). Upraszcza to renderowanie, analizę i interoperacyjność z narzędziami, które rozumieją jedynie linie i punkty.

## Dlaczego liniaryzować geometrię?
- **Wydajność:** Geometrie liniowe są szybsze w renderowaniu i zapytaniach.  
- **Kompatybilność:** Wiele platform GIS (np. starsze usługi mapowe) akceptuje jedynie cechy liniowe.  
- **Uproszczenie:** Przydatne przy tworzeniu miniatur, szybkich podglądów lub dostarczaniu danych do algorytmów wymagających wejścia liniowego.

## Wymagania wstępne
Zanim zanurzysz się w kod, upewnij się, że masz:

1. **Aspose.GIS for .NET** – pobierz go ze [strony Aspose.GIS](https://releases.aspose.com/gis/net/).  
2. **.NET Framework** (lub .NET Core) zainstalowany na Twoim komputerze deweloperskim.  
3. **Visual Studio** (lub dowolne IDE kompatybilne z C#) do pisania i uruchamiania przykładu.

## Importowanie przestrzeni nazw
Aby rozpocząć korzystanie z funkcjonalności Aspose.GIS, zaimportuj wymagane przestrzenie nazw.

### Krok 1: Importuj podstawowe przestrzenie nazw Aspose.GIS
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Krok 2: Importuj sterownik dla docelowego formatu
W tym przykładzie zapisujemy wynik do pliku KML:
```csharp
using Aspose.GIS.Kml;
```

## Jak liniaryzować geometrię – przewodnik krok po kroku
Poniżej znajduje się szczegółowe omówienie każdego wiersza kodu, wyjaśniające **jak liniaryzować geometrię** i dlaczego każdy krok ma znaczenie.

### Krok 1: Zdefiniuj ścieżkę wyjściową
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
Zastąp `"Your Document Directory"` folderem, w którym chcesz zapisać plik KML.

### Krok 2: Utwórz warstwę dla pliku wyjściowego
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```
*Warstwa* to kontener dla obiektów geograficznych. Tutaj tworzymy nową warstwę KML, która będzie przechowywać naszą liniaryzowaną geometrię.

### Krok 3: Utwórz nowy obiekt
```csharp
var feature = layer.ConstructFeature();
```
*Obiekt* (feature) reprezentuje pojedynczy element geograficzny (punkt, linia, wielokąt itp.). Dołączymy naszą liniową geometrię do tego obiektu.

### Krok 4: Zdefiniuj pierwotną złożoną geometrię
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```
Tworzymy geometrię z ciągu Well‑Known Text (WKT). Ten przykład zawiera `LineString`, `CompoundCurve` i `CircularString` — idealne do demonstracji liniaryzacji.

### Krok 5: Liniaryzuj geometrię
```csharp
var linear = geometry.ToLinearGeometry();
```
Metoda `ToLinearGeometry()` konwertuje wszystkie krzywe na odcinki prostych linii, tworząc *liniową* wersję pierwotnej geometrii.

### Krok 6: Przypisz liniową geometrię do obiektu
```csharp
feature.Geometry = linear;
```
Teraz obiekt zawiera uproszczoną, liniową geometrię.

### Krok 7: Dodaj obiekt do warstwy
```csharp
layer.Add(feature);
```
Na koniec dodajemy obiekt do warstwy KML, co zapisuje liniową geometrię do pliku wyjściowego po zakończeniu bloku `using`.

## Typowe pułapki i wskazówki
- **Separatory ścieżek:** Używaj `Path.Combine` do budowania ścieżek wieloplatformowych.  
- **Duże geometrie:** Liniaryzacja bardzo złożonych kształtów może wygenerować wiele wierzchołków; rozważ użycie `Simplify()` po liniaryzacji, jeśli potrzebujesz mniej punktów.  
- **Wybór sterownika:** Jeśli potrzebujesz innego formatu wyjściowego, zamień `Drivers.Kml` na `Drivers.Shapefile`, `Drivers.GeoJson` itp., i odpowiednio dostosuj rozszerzenie pliku.

## Zakończenie
W tym samouczku omówiliśmy **jak liniaryzować geometrię** przy użyciu Aspose.GIS dla .NET, od konfiguracji środowiska po zapisanie wyniku liniaryzacji do pliku KML. Teraz możesz zintegrować ten przepływ pracy z aplikacjami mapowymi, pipeline'ami przetwarzania danych lub dowolnym projektem związanym z GIS, który wymaga uproszczonych geometrii.

## FAQ
### Q: Czy Aspose.GIS dla .NET jest kompatybilny z .NET Core?
Tak, Aspose.GIS dla .NET jest kompatybilny z .NET Core, co pozwala tworzyć aplikacje wieloplatformowe.

### Q: Czy mogę pracować z różnymi formatami plików GIS używając Aspose.GIS dla .NET?
Oczywiście! Aspose.GIS obsługuje różne formaty plików GIS, w tym KML, Shapefile, GeoJSON i inne.

### Q: Czy Aspose.GIS oferuje wsparcie dla operacji i analiz przestrzennych?
Tak, Aspose.GIS zapewnia szeroki zakres operacji i możliwości analizy przestrzennej, aby radzić sobie ze złożonymi zadaniami geoprzestrzennymi.

### Q: Czy dostępna jest darmowa wersja próbna Aspose.GIS dla .NET?
Tak, możesz pobrać darmową wersję próbną ze [strony Aspose](https://releases.aspose.com/).

### Q: Gdzie mogę znaleźć pomoc i wsparcie dla Aspose.GIS?
Możesz odwiedzić [forum Aspose.GIS](https://forum.aspose.com/c/gis/33), aby uzyskać pomoc od społeczności i zespołu wsparcia Aspose.

## Frequently Asked Questions (Additional)

**Q: Czy mogę liniaryzować geometrie zawierające współrzędne 3D (Z)?**  
A: Tak, `ToLinearGeometry()` działa zarówno z geometriami 2D, jak i 3D; wartości Z są zachowywane w powstałych odcinkach linii.

**Q: Jak liniaryzacja wpływa na rozmiar pliku wyjściowego?**  
A: Konwersja krzywych na wiele krótkich odcinków linii może zwiększyć rozmiar pliku. Użyj `Simplify()` po liniaryzacji, jeśli rozmiar pliku jest istotny.

**Q: Czy można kontrolować długość segmentu przy liniaryzacji?**  
A: Domyślna metoda używa wewnętrznej tolerancji. Aby uzyskać własną segmentację, możesz ręcznie tesselować krzywe przed wywołaniem `ToLinearGeometry()`.

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}