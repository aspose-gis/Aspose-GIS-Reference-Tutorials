---
date: 2026-05-31
description: Dowiedz się, jak utworzyć GeoJSON, skonfigurować opcje GeoJSON i dodać
  obiekt do warstwy przy użyciu Aspose.GIS dla .NET. Postępuj zgodnie z tym przewodnikiem
  krok po kroku.
keywords:
- how to create geojson
- add feature to layer
- configure geojson options
linktitle: Ustaw tolerancję Linearization
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  headline: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  name: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  steps:
  - name: Configure GeoJSON Options (how to set tolerance)
    text: '`GeoJsonOptions` specifies the serialization settings used when writing
      GeoJSON files. `GeoJsonOptions` defines how Aspose.GIS serializes GeoJSON, including
      linearization tolerance, coordinate precision, and other output settings. We’ll
      create a `GeoJsonOptions` object and tell Aspose.GIS how close '
  - name: Define the Output Path (how to export GeoJSON)
    text: Specify the full file path where the resulting GeoJSON will be saved. Ensure
      the folder exists and the application has write permissions.
  - name: '**Create Vector Layer** with the configured options'
    text: The `VectorLayer` class represents a GIS container that can read and write
      spatial data. `Drivers.GeoJson` is the driver identifier for writing GeoJSON
      format files. Using `VectorLayer.Create` together with the `Drivers.GeoJson`
      driver and the previously configured `GeoJsonOptions` creates a new Geo
  - name: Construct a Geometry (e.g., a circular string)
    text: '`CircularString` is a curved line geometry that Aspose.GIS can linearize
      based on the tolerance you set. You can replace this with any valid WKT representation
      such as `POINT`, `LINESTRING`, or `POLYGON`.'
  - name: '**Add Feature to Layer** and save'
    text: '`Feature` is the object that couples a geometry with attribute data. After
      creating a `Feature` instance, assign the geometry, optionally add attribute
      values, and call `layer.Add(feature)` to persist it. When the `using` block
      ends, the layer is automatically written to the file defined in `path`. '
  type: HowTo
- questions:
  - answer: Yes, it works with .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6/7.
    question: Is Aspose.GIS for .NET compatible with other .NET frameworks?
  - answer: Absolutely. A commercial license removes all evaluation restrictions and
      provides full technical support.
    question: Can I use Aspose.GIS in commercial projects?
  - answer: Yes, it supports over 30 formats—including Shapefile, KML, GML, and CSV—allowing
      seamless conversion between them.
    question: Does Aspose.GIS support other GIS formats besides GeoJSON?
  - answer: You can download a free 30‑day trial from the Aspose website; it includes
      all features.
    question: Is there a trial version available?
  - answer: Use the Aspose forums, the dedicated support portal, or the “Contact Support”
      link in the product dashboard.
    question: Where can I get support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Jak utworzyć GeoJSON z tolerancją w Aspose.GIS dla .NET
url: /pl/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak tworzyć GeoJSON z tolerancją Aspose.GIS dla .NET

## Wprowadzenie
Jeśli chcesz **dowiedzieć się, jak tworzyć GeoJSON** pliki, kontrolować precyzję krzywych i wyeksportować wynik jako gotowy‑do‑użycia dokument, Aspose.GIS dla .NET czyni to prostym. W tym samouczku odkryjesz, jak skonfigurować opcje GeoJSON, ustawić tolerancję linearyzacji oraz **dodać funkcję do warstwy** obiektów, zachowując kod czysty i gotowy do produkcji.

## Szybkie odpowiedzi
- **Co oznacza „create vector layer”?** Tworzy nowy zestaw danych wektorowych GIS (np. plik GeoJSON), który może przechowywać geometrie i atrybuty.  
- **Jak ustawić tolerancję linearyzacji?** Ustaw właściwość `LinearizationTolerance` na instancji `GeoJsonOptions` przed utworzeniem warstwy.  
- **Czy mogę bezpośrednio wyeksportować plik GeoJSON?** Tak — użyj `VectorLayer.Create` z sterownikiem `Drivers.GeoJson` i skonfigurowanymi opcjami.  
- **Czy potrzebna jest licencja?** Ważna licencja Aspose.GIS odblokowuje wszystkie funkcje; tymczasowy klucz ewaluacyjny działa w trybie testowym.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Co to jest „create vector layer”?
Tworzenie warstwy wektorowej oznacza zainicjowanie nowego kontenera GIS (takiego jak plik GeoJSON), który może przechowywać punkty, linie, wielokąty oraz powiązane dane atrybutowe. Warstwa ta staje się celem dla każdej tworzonej geometrii i wszystkich dołączanych atrybutów.

## Dlaczego konfigurować opcje GeoJSON?
Konfigurowanie opcji GeoJSON — szczególnie **tolerancji linearyzacji** — zapewnia, że zakrzywione geometrie (np. `CircularString`) są przybliżane z precyzją spełniającą wymagania dokładności Twojej aplikacji. Odpowiednia konfiguracja zmniejsza rozmiar pliku, zachowując jednocześnie wierność wizualną, co jest kluczowe, gdy GeoJSON jest wykorzystywany w mapach internetowych lub narzędziach analizy przestrzennej.

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz:

1. **Visual Studio** (dowolna nowsza wersja).  
2. **Licencję Aspose.GIS** (lub tymczasowy klucz ewaluacyjny).  
3. Bibliotekę **Aspose.GIS for .NET** dodaną do projektu.  
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
`GeoJsonOptions` określa ustawienia serializacji używane przy zapisywaniu plików GeoJSON.  
`GeoJsonOptions` definiuje, w jaki sposób Aspose.GIS serializuje GeoJSON, w tym tolerancję linearyzacji, precyzję współrzędnych i inne ustawienia wyjściowe.  
Utworzymy obiekt `GeoJsonOptions` i poinformujemy Aspose.GIS, jak blisko zlinearyzowana geometria musi być do oryginalnej krzywej.

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### Krok 2: Definiowanie ścieżki wyjściowej (jak wyeksportować GeoJSON)
Określ pełną ścieżkę pliku, w którym zostanie zapisany wynikowy GeoJSON. Upewnij się, że folder istnieje i aplikacja ma uprawnienia do zapisu.

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### Krok 3: **Create Vector Layer** z skonfigurowanymi opcjami
Klasa `VectorLayer` reprezentuje kontener GIS, który może odczytywać i zapisywać dane przestrzenne.  
`Drivers.GeoJson` jest identyfikatorem sterownika do zapisu plików w formacie GeoJSON.  
Użycie `VectorLayer.Create` wraz ze sterownikiem `Drivers.GeoJson` i wcześniej skonfigurowanymi `GeoJsonOptions` tworzy nowy plik GeoJSON gotowy do wstawiania funkcji.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### Krok 4: Tworzenie geometrii (np. ciąg kołowy)
`CircularString` to zakrzywiona linia, którą Aspose.GIS może zlinearyzować na podstawie ustawionej tolerancji. Możesz ją zamienić na dowolną prawidłową reprezentację WKT, taką jak `POINT`, `LINESTRING` lub `POLYGON`.

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### Krok 5: **Add Feature to Layer** i zapisz
`Feature` to obiekt łączący geometrię z danymi atrybutowymi. Po utworzeniu instancji `Feature` przypisz geometrię, opcjonalnie dodaj wartości atrybutów i wywołaj `layer.Add(feature)`, aby ją zachować. Gdy blok `using` się zakończy, warstwa zostanie automatycznie zapisana do pliku określonego w `path`.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

Gdy blok `using` się zakończy, warstwa zostanie automatycznie zapisana do pliku określonego w `path`, dając Ci gotowy do użycia plik GeoJSON.

## Typowe problemy i wskazówki
- **Nieprawidłowa ścieżka** – Sprawdź, czy katalog istnieje i masz uprawnienia do zapisu.  
- **Zbyt niska tolerancja** – Ustawienie `LinearizationTolerance` na bardzo małą wartość może znacznie zwiększyć rozmiar pliku; tolerancja 0,001 zazwyczaj balansuje precyzję i rozmiar.  
- **Błędy licencji** – Jeśli pojawiają się ostrzeżenia licencyjne, upewnij się, że plik licencji jest załadowany przed jakimikolwiek wywołaniami Aspose.GIS.  
- **Uwaga dotycząca wydajności** – Aspose.GIS obsługuje przetwarzanie plików do 2 GB bez ładowania całego dokumentu do pamięci, dzięki architekturze strumieniowej.

## Najczęściej zadawane pytania

**P: Czy Aspose.GIS dla .NET jest kompatybilny z innymi frameworkami .NET?**  
O: Tak, działa z .NET Framework 4.5+, .NET Core 3.1+ oraz .NET 5/6/7.

**P: Czy mogę używać Aspose.GIS w projektach komercyjnych?**  
O: Zdecydowanie tak. Licencja komercyjna usuwa wszystkie ograniczenia wersji próbnej i zapewnia pełne wsparcie techniczne.

**P: Czy Aspose.GIS obsługuje inne formaty GIS poza GeoJSON?**  
O: Tak, obsługuje ponad 30 formatów — w tym Shapefile, KML, GML i CSV — umożliwiając płynną konwersję między nimi.

**P: Czy dostępna jest wersja próbna?**  
O: Możesz pobrać darmową 30‑dniową wersję próbną ze strony Aspose; zawiera wszystkie funkcje.

**P: Gdzie mogę uzyskać wsparcie?**  
O: Skorzystaj z forów Aspose, dedykowanego portalu wsparcia lub linku „Contact Support” w panelu produktu.

## Zakończenie
Postępując zgodnie z tymi krokami, teraz wiesz **jak tworzyć GeoJSON**, konfigurować tolerancję linearyzacji i **dodać funkcję do warstwy** w celu bezproblemowego eksportu GeoJSON. Eksploruj dodatkowe typy geometrii, obsługę atrybutów i scenariusze przetwarzania wsadowego, aby w pełni wykorzystać możliwości Aspose.GIS w swoich projektach .NET GIS.

---

**Ostatnia aktualizacja:** 2026-05-31  
**Testowano z:** Aspose.GIS 24.11 dla .NET  
**Autor:** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Jak konwertować GeoJSON – Aspose.GIS dla .NET](/gis/net/geo-data-conversion/)
- [Utwórz warstwę wektorową, ogranicz precyzję przy użyciu Aspose.GIS dla .NET](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [Utwórz warstwę wektorową w pliku GDB – Samouczek Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}