---
date: 2026-01-13
description: Dowiedz się, jak utworzyć nowy plik shapefile przy użyciu Aspose.GIS
  dla .NET. Ten przewodnik krok po kroku pokazuje, jak zdefiniować warstwę wektorową,
  dodać atrybut daty i zarządzać danymi przestrzennymi.
linktitle: Create New Shapefile
second_title: Aspose.GIS .NET API
title: Utwórz nowy shapefile
url: /pl/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz nowy shapefile

## Wprowadzenie
Jeśli zagłębiasz się w rozwój systemów informacji geograficznej (GIS) w .NET, Aspose.GIS jest Twoim rozwiązaniem. Ta potężna biblioteka umożliwia programistom płynną pracę z danymi przestrzennymi, a w tym samouczku pokażemy, jak **utworzyć nowy shapefile** przy użyciu Aspose.GIS dla .NET. Zobaczysz, dlaczego definiowanie warstwy wektorowej i dodanie atrybutu daty są kluczowymi krokami w solidnych projektach GIS.

## Szybkie odpowiedzi
- **Co uczy ten samouczek?** Jak utworzyć nowy shapefile, zdefiniować warstwę wektorową i dodać atrybuty (w tym pole daty).  
- **Jakiej biblioteki potrzebujesz?** Aspose.GIS dla .NET.  
- **Czy potrzebna jest licencja?** Bezpłatna wersja próbna wystarczy do nauki; licencja komercyjna jest wymagana w produkcji.  
- **Jakie IDE powinienem używać?** Visual Studio (dowolna nowsza wersja).  
- **Jak długo trwa implementacja?** Około 10‑15 minut dla podstawowego przykładu.

## Wymagania wstępne
Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania:
- Podstawowa znajomość języka programowania C#.
- Zainstalowany Visual Studio na komputerze.
- Biblioteka Aspose.GIS dla .NET. Możesz ją pobrać [tutaj](https://releases.aspose.com/gis/net/).

## Importowanie przestrzeni nazw
Rozpocznij od zaimportowania niezbędnych przestrzeni nazw, aby wykorzystać funkcjonalność Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Krok 1: Konfiguracja projektu
Rozpocznij od utworzenia nowego projektu C# w Visual Studio i dołącz biblioteki Aspose.GIS.

## Krok 2: Definiowanie katalogu dokumentów
```csharp
string dataDir = "Your Document Directory";
```
Zastąp *Your Document Directory* rzeczywistą ścieżką, w której chcesz zapisać nowy shapefile.

## Krok 3: Utworzenie VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
Ten fragment kodu **definiuje warstwę wektorową** i deklaruje trzy atrybuty: pole tekstowe (`name`), pole liczb całkowitych (`age`) oraz pole daty i czasu (`dob`). Dodanie atrybutu daty jest kluczowe dla analiz czasowych w GIS.

## Krok 4: Dodawanie obiektów
### Przypadek 1: Ustawianie wartości indywidualnie
```csharp
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
firstFeature.SetValue("dob", new DateTime(1982, 2, 5, 16, 30, 0));
layer.Add(firstFeature);
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
secondFeature.SetValue("dob", new DateTime(1984, 12, 15, 15, 30, 0));
layer.Add(secondFeature);
```
Tutaj tworzymy dwa punkty, ustawiamy każdy atrybut osobno i dodajemy obiekty do warstwy.

### Przypadek 2: Ustawianie nowych wartości dla wszystkich atrybutów
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
W tym podejściu wypełniamy wszystkie wartości atrybutów w jednym wywołaniu przy użyciu tablicy obiektów — przydatne, gdy masz wiele atrybutów.

## Dlaczego to jest ważne
Programowe tworzenie shapefile pozwala automatyzować przepływy danych, generować zestawy testowe lub integrować wyniki GIS bezpośrednio z usługami internetowymi. Opanowując **tworzenie shapefile** przy użyciu Aspose.GIS, uzyskasz pełną kontrolę nad geometrią obiektów, schematem atrybutów i zgodnością formatu pliku.

## Częste pułapki i wskazówki
- **Separatory ścieżek:** Używaj `Path.Combine` dla kompatybilności międzyplatformowej zamiast konkatenacji ciągów.  
- **Kolejność atrybutów:** Kolejność wartości w `SetValues` musi odpowiadać kolejności, w jakiej dodano atrybuty.  
- **Obsługa dat:** Zawsze używaj `DateTimeKind.Utc`, jeśli Twoje dane GIS będą udostępniane w różnych strefach czasowych.

## Zakończenie
Gratulacje! Pomyślnie utworzyłeś nowy shapefile przy użyciu Aspose.GIS dla .NET. Ten samouczek obejmował podstawy konfiguracji projektu, definiowania warstwy wektorowej i dodawania obiektów — w tym atrybutu daty. W miarę dalszej eksploracji odwołuj się do [dokumentacji](https://reference.aspose.com/gis/net/) w celu poznania zaawansowanych funkcji i możliwości.

## Najczęściej zadawane pytania
### P: Czy mogę używać Aspose.GIS z innymi językami programowania?
Aspose.GIS głównie obsługuje .NET, ale dostępne są także wersje dla Javy.

### P: Czy dostępna jest bezpłatna wersja próbna?
Tak, bezpłatną wersję próbną możesz uzyskać [tutaj](https://releases.aspose.com/).

### P: Gdzie mogę znaleźć wsparcie dla Aspose.GIS?
Odwiedź [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) w celu uzyskania wsparcia społeczności i dyskusji.

### P: Jak mogę uzyskać tymczasową licencję?
Uzyskaj tymczasową licencję [tutaj](https://purchase.aspose.com/temporary-license/).

### P: Gdzie mogę kupić Aspose.GIS dla .NET?
Bibliotekę możesz kupić [tutaj](https://purchase.aspose.com/buy).

**Ostatnia aktualizacja:** 2026-01-13  
**Testowano z:** Aspose.GIS 24.11 dla .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}