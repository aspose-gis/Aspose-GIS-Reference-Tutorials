---
date: 2025-12-21
description: Dowiedz się, jak utworzyć warstwę wektorową, ustawić tolerancję liniaryzacji
  i dodać obiekt do warstwy przy użyciu Aspose.GIS dla .NET. Postępuj zgodnie z tym
  przewodnikiem krok po kroku, aby wyeksportować pliki GeoJSON.
linktitle: Set Linearization Tolerance
second_title: Aspose.GIS .NET API
title: Utwórz warstwę wektorową i ustaw tolerancję liniaryzacji przy użyciu Aspose.GIS
  dla .NET
url: /pl/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tworzenie warstwy wektorowej i ustawianie tolerancji linearyzacji przy użyciu Aspose.GIS dla .NET

## Wprowadzenie
Jeśli potrzebujesz **utworzyć warstwę wektorową**, kontrolować precyzję krzywych i wyeksportować wynik jako dokument GeoJSON, Aspose.GIS dla .NET umożliwia to w prosty sposób. W tym samouczku dowiesz się, jak skonfigurować opcje GeoJSON, ustawić tolerancję linearyzacji oraz **dodać obiekt do warstwy** — wszystko przy zachowaniu czystego i gotowego do produkcji kodu.

## Szybkie odpowiedzi
- **Co oznacza „utworzyć warstwę wektorową”?** Tworzy nowy zestaw danych GIS (np. plik GeoJSON), który może przechowywać geometrie i atrybuty.  
- **Jak ustawić tolerancję?** Użyj właściwości `LinearizationTolerance` klasy `GeoJsonOptions`.  
- **Czy mogę wyeksportować plik GeoJSON?** Tak — wystarczy utworzyć `VectorLayer` z sterownikiem `Drivers.GeoJson`.  
- **Czy potrzebna jest licencja?** Ważna licencja Aspose.GIS odblokowuje wszystkie funkcje; licencja tymczasowa działa w trybie ewaluacyjnym.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Co to jest „utworzyć warstwę wektorową”?
Utworzenie warstwy wektorowej oznacza zainicjowanie nowego kontenera GIS (takiego jak plik GeoJSON), który może przechowywać elementy geometryczne takie jak punkty, linie i wielokąty. Warstwa ta staje się celem dla każdej tworzonej geometrii oraz przypisywanych atrybutów.

## Dlaczego konfigurować opcje GeoJSON?
Konfiguracja opcji GeoJSON — szczególnie **tolerancji linearyzacji** — zapewnia, że zakrzywione geometrie (np. `CircularString`) są aproksymowane z precyzją spełniającą wymagania Twojej aplikacji. Ten krok jest kluczowy, gdy później **eksportujesz plik GeoJSON** do użycia w mapach internetowych lub analizach przestrzennych.

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz:

1. **Visual Studio** zainstalowane (dowolna aktualna wersja).  
2. **Licencję Aspose.GIS** (lub tymczasowy klucz ewaluacyjny).  
3. Bibliotekę **Aspose.GIS dla .NET** pobraną i dodaną jako referencję w projekcie.  
4. Podstawową znajomość **C#**.

## Importowanie przestrzeni nazw
Najpierw zaimportuj wymagane przestrzenie nazw, aby kompilator wiedział, gdzie znaleźć klasy GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Przewodnik krok po kroku

### Krok 1: Konfiguracja opcji GeoJSON (jak ustawić tolerancję)
Utworzymy obiekt `GeoJsonOptions` i poinformujemy Aspose.GIS, jak blisko zlinearyzowana geometria ma być oryginalnej krzywej.

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### Krok 2: Definicja ścieżki wyjściowej (jak wyeksportować GeoJSON)
Określ, gdzie ma zostać zapisany wynikowy plik. Zamień symbol zastępczy na rzeczywistą ścieżkę folderu.

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### Krok 3: **Utworzenie warstwy wektorowej** z skonfigurowanymi opcjami
Teraz faktycznie **tworzymy warstwę wektorową** przy użyciu metody `VectorLayer.Create`. Blok `using` zapewnia prawidłowe zwolnienie zasobów.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### Krok 4: Budowa geometrii (np. ciąg kołowy)
Tutaj budujemy przykładową geometrię — `CircularString`. Możesz zamienić ją na dowolny prawidłowy WKT.

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### Krok 5: **Dodanie obiektu do warstwy** i zapis
Na koniec tworzymy obiekt, przypisujemy mu geometrię i dodajemy go do warstwy. To jest sedno operacji **add feature to layer**.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

Gdy blok `using` zakończy się, warstwa zostaje automatycznie zapisana do pliku określonego w `path`, dając gotowy do użycia plik GeoJSON.

## Typowe problemy i wskazówki
- **Nieprawidłowa ścieżka** — Upewnij się, że katalog istnieje i masz uprawnienia do zapisu.  
- **Zbyt niska tolerancja** — Ustawienie `LinearizationTolerance` na bardzo małą wartość może dramatycznie zwiększyć rozmiar pliku. Dostosuj ją do potrzebnej dokładności.  
- **Błędy licencji** — Jeśli pojawiają się ostrzeżenia licencyjne, sprawdź, czy plik licencji został poprawnie załadowany przed jakimikolwiek wywołaniami Aspose.GIS.

## Najczęściej zadawane pytania

**P: Czy Aspose.GIS dla .NET jest kompatybilny z innymi frameworkami .NET?**  
O: Tak, działa z .NET Framework, .NET Core oraz .NET 5/6/7.

**P: Czy mogę używać Aspose.GIS w projektach komercyjnych?**  
O: Oczywiście. Licencja komercyjna usuwa wszystkie ograniczenia wersji ewaluacyjnej.

**P: Czy Aspose.GIS obsługuje inne formaty GIS poza GeoJSON?**  
O: Tak, obsługuje Shapefile, KML, GML i wiele innych.

**P: Czy dostępna jest wersja próbna?**  
O: Tak, możesz pobrać darmową wersję próbną ze strony Aspose.

**P: Gdzie mogę uzyskać wsparcie?**  
O: Skorzystaj z forów Aspose lub linku wsparcia w sekcji zasobów.

## Zakończenie
Postępując zgodnie z tymi krokami, teraz wiesz, jak **utworzyć warstwę wektorową**, skonfigurować tolerancję linearyzacji oraz **dodać obiekt do warstwy** w celu bezproblemowego **eksportu pliku GeoJSON**. Eksperymentuj z dodatkowymi typami geometrii i obsługą atrybutów, aby w pełni wykorzystać możliwości Aspose.GIS w swoich projektach GIS opartych na .NET.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ostatnia aktualizacja:** 2025-12-21  
**Testowano z:** Aspose.GIS 24.11 dla .NET  
**Autor:** Aspose  

---