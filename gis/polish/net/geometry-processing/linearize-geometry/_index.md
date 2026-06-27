---
date: 2026-04-09
description: Poznaj sposób konwertowania krzywych na linie (liniaryzacja geometrii)
  przy użyciu Aspose.GIS dla .NET, co umożliwia efektywne przetwarzanie i analizę
  danych geoprzestrzennych w Twoich aplikacjach .NET.
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS .NET
linktitle: Zlinearyzuj geometrię
second_title: Aspose.GIS .NET API
title: Jak konwertować krzywe na linie przy użyciu Aspose.GIS dla .NET
url: /pl/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konwertuj krzywe na linie (liniaryzacja geometrii) przy użyciu Aspose.GIS dla .NET

## Wprowadzenie
Jeśli potrzebujesz **konwertować krzywe na linie** do mapowania, analizy przestrzennej lub zadań wymiany danych, Aspose.GIS dla .NET zapewnia czysty, programowy sposób realizacji. W tym samouczku przeprowadzimy Cię przez kompletny, rzeczywisty przykład, który pokaże, jak wziąć złożoną geometrię — zawierającą krzywe i kształty złożone — i przekształcić ją w prostą liniową reprezentację działającą w każdym systemie GIS.

## Szybkie odpowiedzi
- **Co oznacza „convert curves to lines”?** Przekształca zakrzywione geometrie w odcinki prostych linii.  
- **Dlaczego wybrać Aspose.GIS?** Biblioteka obsługuje dziesiątki formatów GIS i radzi sobie z konwersją geometrii bez zewnętrznych narzędzi.  
- **Czego potrzebuję wcześniej?** .NET Framework lub .NET Core, Visual Studio (lub dowolne IDE C#) oraz pakiet NuGet Aspose.GIS.  
- **Jak długo będzie działał przykład?** Mniej niż pięć minut po zainstalowaniu biblioteki.  
- **Czy mogę eksportować do innych formatów?** Oczywiście — zamień sterownik KML na Shapefile, GeoJSON itp.

## Co oznacza konwersja krzywych na linie?
Konwersja krzywych na linie (zwane również **liniaryzacją geometrii**) rozkłada dowolny zakrzywiony lub złożony kształt na serię odcinków prostych linii, znanych jako „geometria liniowa”. To uproszczenie przyspiesza renderowanie, zwiększa kompatybilność ze starszymi usługami GIS i zmniejsza złożoność algorytmów przestrzennych.

## Dlaczego konwertować krzywe na linie?
- **Wydajność:** Geometrie liniowe renderują się i są przeszukiwane znacznie szybciej.  
- **Kompatybilność:** Wiele platform GIS (szczególnie starsze usługi) akceptuje tylko cechy liniowe.  
- **Uproszczenie:** Idealne do miniatur, szybkich podglądów lub przekazywania danych do algorytmów wymagających wejścia liniowego.

## Wymagania wstępne
Zanim zagłębisz się w kod, upewnij się, że masz:

1. **Aspose.GIS for .NET** – pobierz go ze [strony Aspose.GIS](https://releases.aspose.com/gis/net/).  
2. **.NET Framework** (lub .NET Core) zainstalowany na maszynie deweloperskiej.  
3. **Visual Studio** (lub dowolne IDE kompatybilne z C#) do pisania i uruchamiania przykładu.

## Importowanie przestrzeni nazw
Aby rozpocząć korzystanie z funkcjonalności Aspose.GIS, zaimportuj wymagane przestrzenie nazw.

### Krok 1: Podstawowe przestrzenie nazw Aspose.GIS
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Krok 2: Sterownik dla docelowego formatu
Dla tego przykładu zapisujemy wynik do pliku KML:
```csharp
using Aspose.GIS.Kml;
```

## Przewodnik krok po kroku konwertowania krzywych na linie
Poniżej znajduje się szczegółowe omówienie każdego wiersza kodu, wyjaśniające **jak konwertować krzywe na linie** oraz dlaczego każdy krok ma znaczenie.

### Krok 1: Zdefiniuj ścieżkę wyjściową
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
Zastąp `"Your Document Directory"` folderem, w którym chcesz zapisać plik KML. Zaleca się użycie `Path.Combine` dla kompatybilności międzyplatformowej.

### Krok 2: Utwórz warstwę dla pliku wyjściowego
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```
*Warstwa* jest kontenerem dla obiektów geograficznych. Tutaj tworzymy nową warstwę KML, która będzie przechowywać naszą liniaryzowaną geometrię.

### Krok 3: Utwórz nowy obiekt (feature)
```csharp
var feature = layer.ConstructFeature();
```
*Obiekt* (feature) reprezentuje pojedynczy element geograficzny (punkt, linia, wielokąt itp.). Dołączymy naszą liniową geometrię do tego obiektu.

### Krok 4: Zdefiniuj oryginalną złożoną geometrię
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```
Tworzymy geometrię z ciągu Well‑Known Text (WKT). Ten przykład zawiera `LineString`, `CompoundCurve` i `CircularString` — idealny do demonstracji **konwersji krzywych na linie**.

### Krok 5: Konwertuj krzywe na linie
```csharp
var linear = geometry.ToLinearGeometry();
```
Metoda `ToLinearGeometry()` konwertuje wszystkie krzywe na odcinki prostych linii, tworząc *liniową* wersję oryginalnej geometrii.

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

## Typowe pułapki i wskazówki profesjonalne
- **Separatory ścieżek:** Używaj `Path.Combine`, aby uniknąć problemów w Windows vs. Linux.  
- **Bardzo duże geometrie:** Liniaryzacja skomplikowanych kształtów może wygenerować tysiące wierzchołków; rozważ wywołanie `Simplify()` po liniaryzacji, aby zmniejszyć liczbę punktów.  
- **Wybór sterownika:** Jeśli potrzebujesz innego formatu wyjściowego, zamień `Drivers.Kml` na `Drivers.Shapefile`, `Drivers.GeoJson` itp., i odpowiednio zmień rozszerzenie pliku.  
- **Zachowanie wartości Z:** `ToLinearGeometry()` zachowuje współrzędne 3‑D (Z), więc nie tracisz danych wysokościowych.

## Najczęściej zadawane pytania (FAQ)

**P:** Czy Aspose.GIS dla .NET jest kompatybilny z .NET Core?  
**O:** Tak, Aspose.GIS działa z .NET Core, umożliwiając aplikacje wieloplatformowe.

**P:** Czy mogę pracować z różnymi formatami plików GIS przy użyciu Aspose.GIS dla .NET?  
**O:** Oczywiście! Biblioteka obsługuje KML, Shapefile, GeoJSON i wiele innych formatów.

**P:** Czy Aspose.GIS oferuje operacje i analizy przestrzenne?  
**O:** Tak, zapewnia szeroki zakres funkcji przestrzennych, od buforowania po łączenia przestrzenne.

**P:** Czy dostępna jest darmowa wersja próbna?  
**O:** Tak, możesz pobrać darmową wersję próbną ze [strony Aspose](https://releases.aspose.com/).

**P:** Gdzie mogę uzyskać pomoc, jeśli napotkam problemy?  
**O:** Odwiedź [forum Aspose.GIS](https://forum.aspose.com/c/gis/33), aby uzyskać wsparcie od społeczności i personelu.

### Dodatkowe typowe pytania

**P:** Czy mogę liniaryzować geometrie zawierające współrzędne 3D (Z)?  
**O:** Tak, `ToLinearGeometry()` działa zarówno z geometriami 2D, jak i 3D; wartości Z są zachowane.

**P:** Jak liniaryzacja wpływa na rozmiar pliku?  
**O:** Konwersja krzywych na wiele krótkich odcinków może zwiększyć rozmiar pliku. Użyj `Simplify()` po liniaryzacji, jeśli rozmiar jest problemem.

**P:** Czy mogę kontrolować długość odcinków przy konwersji krzywych na linie?  
**O:** Domyślna metoda używa wewnętrznej tolerancji. Aby uzyskać własną segmentację, możesz ręcznie tesselować krzywe przed wywołaniem `ToLinearGeometry()`.

## Podsumowanie
W tym samouczku omówiliśmy **jak konwertować krzywe na linie** (liniaryzacja geometrii) przy użyciu Aspose.GIS dla .NET, od konfiguracji środowiska po zapisanie wyników liniaryzacji do pliku KML. Teraz możesz wbudować ten przepływ pracy w aplikacje mapujące, potoki przetwarzania danych lub dowolny projekt związany z GIS, który wymaga uproszczonych geometrii.

**Ostatnia aktualizacja:** 2026-04-09  
**Testowano z:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}