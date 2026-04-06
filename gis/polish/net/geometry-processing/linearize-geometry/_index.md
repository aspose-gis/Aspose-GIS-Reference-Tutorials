---
date: 2026-04-06
description: Dowiedz się, jak konwertować krzywe na linie i liniaryzować geometrie
  za pomocą Aspose.GIS dla .NET, umożliwiając szybkie przetwarzanie i analizę danych
  geoprzestrzennych w Twoich aplikacjach .NET.
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS linearize geometry
linktitle: Liniaryzuj geometrię
second_title: Aspose.GIS .NET API
title: Konwertuj krzywe na linie przy użyciu Aspose.GIS dla .NET
url: /pl/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konwertowanie krzywych na linie przy użyciu Aspose.GIS dla .NET

## Wprowadzenie
Jeśli potrzebujesz **konwertować krzywe na linie** do mapowania, analizy przestrzennej lub zadań wymiany danych, Aspose.GIS dla .NET zapewnia czysty, programowy sposób na to. W tym samouczku przeprowadzimy Cię przez kompletny, rzeczywisty przykład, który pokaże, jak wziąć złożoną geometrię — zawierającą krzywe i kształty złożone — i przekształcić ją w prostą reprezentację liniową, działającą w każdym systemie GIS.

## Szybkie odpowiedzi
- **Co oznacza liniowanie geometrii?** Konwersja krzywych i złożonych kształtów na odcinki prostych linii.  
- **Dlaczego używać Aspose.GIS?** Obsługuje dziesiątki formatów GIS i obsługuje konwersję geometrii bez zewnętrznych narzędzi.  
- **Wymagania wstępne?** .NET Framework lub .NET Core, Visual Studio oraz biblioteka Aspose.GIS.  
- **Jak długo trwa przykład?** Mniej niż pięć minut po zainstalowaniu biblioteki.  
- **Czy mogę zapisać w innych formatach?** Tak — zamień sterownik KML na Shapefile, GeoJSON itp.

## Co to jest liniowanie geometrii?
Liniowanie geometrii oznacza rozbicie dowolnego zakrzywionego lub złożonego kształtu na szereg odcinków prostych linii (tzw. „geometria liniowa”). Upraszcza to renderowanie, analizę i interoperacyjność z narzędziami, które rozumieją jedynie linie i punkty.

## Dlaczego konwertować krzywe na linie?
- **Wydajność:** Geometrie liniowe są szybsze w renderowaniu i zapytaniach.  
- **Kompatybilność:** Wiele platform GIS (np. starsze usługi mapowe) akceptuje tylko cechy liniowe.  
- **Uproszczenie:** Przydatne do tworzenia miniatur, szybkich podglądów lub dostarczania danych do algorytmów wymagających wejścia liniowego.

## Wymagania wstępne
Przed przystąpieniem do kodu upewnij się, że masz:

1. **Aspose.GIS dla .NET** – pobierz go z [strony Aspose.GIS](https://releases.aspose.com/gis/net/).  
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
W tym przykładzie zapiszemy wynik do pliku KML:
```csharp
using Aspose.GIS.Kml;
```

## Jak konwertować krzywe na linie – przewodnik krok po kroku
Poniżej znajduje się szczegółowy opis każdego wiersza kodu, wyjaśniający **jak konwertować krzywe na linie** i dlaczego każdy krok ma znaczenie.

### Krok 1: Zdefiniuj ścieżkę wyjściową
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
Zastąp `"Your Document Directory"` folderem, w którym chcesz zapisać plik KML.

### Krok 2: Utwórz warstwę dla pliku wyjściowego
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```
*Warstwa* jest kontenerem dla obiektów geograficznych. Tutaj tworzymy nową warstwę KML, która będzie przechowywać naszą zlinearyzowaną geometrię.

### Krok 3: Utwórz nowy obiekt (feature)
```csharp
var feature = layer.ConstructFeature();
```
*Obiekt* (feature) reprezentuje pojedynczy obiekt geograficzny (punkt, linia, wielokąt itp.). Dołączymy naszą geometry liniową do tego obiektu.

### Krok 4: Zdefiniuj oryginalną złożoną geometrię
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```
Tworzymy geometrię z ciągu Well‑Known Text (WKT). Ten przykład zawiera `LineString`, `CompoundCurve` i `CircularString` — idealny do demonstracji konwersji krzywych na linie.

### Krok 5: Liniuj geometrię
```csharp
var linear = geometry.ToLinearGeometry();
```
Metoda `ToLinearGeometry()` konwertuje wszystkie krzywe na odcinki prostych linii, tworząc *liniową* wersję oryginalnej geometrii.

### Krok 6: Przypisz geometry liniową do obiektu
```csharp
feature.Geometry = linear;
```
Teraz obiekt zawiera uproszczoną, liniową geometrię.

### Krok 7: Dodaj obiekt do warstwy
```csharp
layer.Add(feature);
```
Na koniec dodajemy obiekt do warstwy KML, która zapisuje liniową geometrię do pliku wyjściowego po zakończeniu bloku `using`.

## Częste pułapki i wskazówki
- **Separatory ścieżek:** Używaj `Path.Combine` do budowania ścieżek wieloplatformowych.  
- **Duże geometrie:** Liniowanie bardzo złożonych kształtów może wygenerować wiele wierzchołków; rozważ użycie `Simplify()` po liniowaniu, jeśli potrzebujesz mniej punktów.  
- **Wybór sterownika:** Jeśli potrzebujesz innego formatu wyjściowego, zamień `Drivers.Kml` na `Drivers.Shapefile`, `Drivers.GeoJson` itp., i odpowiednio dostosuj rozszerzenie pliku.

## Najczęściej zadawane pytania (Ulepszone)

**P: Czy Aspose.GIS dla .NET jest kompatybilny z .NET Core?**  
**O:** Tak, Aspose.GIS dla .NET działa z .NET Core, umożliwiając budowanie aplikacji wieloplatformowych.

**P: Czy mogę pracować z różnymi formatami plików GIS używając Aspose.GIS dla .NET?**  
**O:** Oczywiście! Aspose.GIS obsługuje KML, Shapefile, GeoJSON i wiele innych formatów.

**P: Czy Aspose.GIS oferuje wsparcie dla operacji i analiz przestrzennych?**  
**O:** Tak, zapewnia szeroki zakres operacji i możliwości analizy przestrzennej, aby radzić sobie ze złożonymi zadaniami geoprzestrzennymi.

**P: Czy dostępna jest darmowa wersja próbna Aspose.GIS dla .NET?**  
**O:** Tak, możesz pobrać darmową wersję próbną ze [strony Aspose](https://releases.aspose.com/).

**P: Gdzie mogę znaleźć pomoc i wsparcie dla Aspose.GIS?**  
**O:** Odwiedź [forum Aspose.GIS](https://forum.aspose.com/c/gis/33), aby uzyskać pomoc od społeczności i zespołu wsparcia Aspose.

**P: Czy mogę liniować geometrie zawierające współrzędne 3D (Z)?**  
**O:** Tak, `ToLinearGeometry()` działa zarówno z geometriami 2D, jak i 3D; wartości Z są zachowywane w powstałych odcinkach linii.

**P: Jak liniowanie wpływa na rozmiar pliku wyjściowego?**  
**O:** Konwersja krzywych na wiele krótkich odcinków linii może zwiększyć rozmiar pliku. Użyj `Simplify()` po liniowaniu, jeśli rozmiar pliku jest istotny.

**P: Czy można kontrolować długość odcinka przy liniowaniu?**  
**O:** Domyślna metoda używa wewnętrznej tolerancji. Aby uzyskać własną segmentację, możesz ręcznie tesselować krzywe przed wywołaniem `ToLinearGeometry()`.

## Podsumowanie
W tym samouczku omówiliśmy **jak konwertować krzywe na linie** przy użyciu Aspose.GIS dla .NET, od konfiguracji środowiska po zapis zlinearyzowanego wyniku do pliku KML. Teraz możesz zintegrować ten przepływ pracy z aplikacjami mapowymi, pipeline'ami przetwarzania danych lub dowolnym projektem związanym z GIS, który wymaga uproszczonych geometrii.

---

**Last Updated:** 2026-04-06  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}