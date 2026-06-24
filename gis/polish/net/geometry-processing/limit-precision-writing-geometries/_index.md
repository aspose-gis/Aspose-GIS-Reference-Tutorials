---
date: 2026-05-31
description: Dowiedz się, jak ograniczyć precyzję przy zapisywaniu geometrii za pomocą
  Aspose.GIS dla .NET, zmniejszając rozmiar GeoJSON i zachowując kontrolę nad współrzędnymi.
keywords:
- how to limit precision
- reduce geojson size
- Aspose.GIS precision control
linktitle: Ogranicz precyzję przy zapisywaniu geometrii
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to limit precision when writing geometries with Aspose.GIS
    for .NET, reducing GeoJSON size and keeping coordinate control.
  headline: How to Limit Precision Writing Geometries with Aspose.GIS
  type: TechArticle
- description: Learn how to limit precision when writing geometries with Aspose.GIS
    for .NET, reducing GeoJSON size and keeping coordinate control.
  name: How to Limit Precision Writing Geometries with Aspose.GIS
  steps:
  - name: Define Precision Options
    text: The `GeoJsonOptions` class lets you specify how many fractional digits to
      keep for X/Y and Z coordinates. `PrecisionModel` defines how coordinate values
      are rounded or kept exact during writing.
  - name: Set Output Path
    text: Specify where the resulting GeoJSON file will be saved. `VectorLayer` is
      Aspose.GIS's container for a collection of features that share the same schema;
      it writes to the path you provide using the options set earlier.
  - name: Create and Populate Geometry
    text: Open a new `VectorLayer` with the options defined above, construct a `Point`
      geometry, and add it to the layer. `Point` represents a single coordinate (X,
      Y, optional Z) in a spatial reference system. It is the simplest geometry type
      and is used here to demonstrate precision rounding.
  - name: Read and Verify Precision
    text: Open the file you just created and print the coordinates. You should see
      the X/Y values rounded to three decimal places while the Z value remains exact.
      When you read the file back, Aspose.GIS parses the rounded values directly,
      so the in‑memory `Point` reflects the precision you defined during writ
  type: HowTo
- questions:
  - answer: Yes, it supports **50+** formats—including Shapefile, GeoJSON, KML, GML,
      and CSV—allowing seamless conversion between them.
    question: Is Aspose.GIS for .NET compatible with other GIS formats?
  - answer: Absolutely. A free trial is available from the download page, giving you
      full access to all features for evaluation.
    question: Can I try Aspose.GIS for .NET before purchasing?
  - answer: Temporary evaluation licenses can be generated via the Aspose license
      portal; they are valid for 30 days.
    question: How do I obtain a temporary license for testing?
  - answer: The Aspose.GIS forum and Stack Overflow tag `aspose-gis` are great places
      to ask questions and find community solutions.
    question: Where can I get help if I run into issues?
  - answer: Yes, Aspose.GIS is designed to handle everything from quick prototypes
      to high‑throughput server workloads, processing multi‑gigabyte datasets with
      low memory overhead.
    question: Does the library work for both small scripts and enterprise‑scale applications?
  type: FAQPage
second_title: Aspise.GIS .NET API
title: Jak ograniczyć precyzję przy zapisywaniu geometrii za pomocą Aspose.GIS
url: /pl/net/geometry-processing/limit-precision-writing-geometries/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak ograniczyć precyzję przy zapisywaniu geometrii za pomocą Aspose.GIS

Jeśli zastanawiasz się **jak ograniczyć precyzję** przy zapisywaniu geometrii w aplikacji .NET GIS, Aspose.GIS dla .NET oferuje prosty, wysokowydajny sposób kontrolowania zaokrąglania współrzędnych. W tym samouczku przeprowadzimy Cię przez cały proces — od konfiguracji środowiska po weryfikację, że wynik respektuje zdefiniowane reguły precyzji.

## Szybkie odpowiedzi
- **Co oznacza „limit precision”?** Zaokrągla wartości współrzędnych do określonej liczby cyfr po przecinku podczas zapisywania pliku przestrzennego.  
- **Jaki format jest użyty w przykładzie?** GeoJSON, ale te same opcje mają zastosowanie do innych obsługiwanych formatów.  
- **Czy potrzebuję licencji, aby to wypróbować?** Darmowa wersja próbna działa w środowisku deweloperskim i testowym; licencja komercyjna jest wymagana w produkcji.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Czy mogę kontrolować precyzję współrzędnej Z osobno?** Tak — użyj `ZPrecisionModel`, aby ustawić dokładne lub zaokrąglone wartości.

## Jak ograniczyć precyzję przy zapisywaniu geometrii

Załaduj swój zapisujący GeoJSON przy użyciu obiektu `GeoJsonOptions`, który określa wymaganą precyzję współrzędnych X/Y oraz Z, następnie zapisz geometrię i odczytaj ją ponownie — cały ten przepływ pracy mieści się w mniej niż dziesięciu linijkach kodu i gwarantuje, że wszystkie współrzędne są zaokrąglone dokładnie tak, jak zdefiniowano.

Ograniczanie precyzji jest niezbędne, gdy potrzebujesz spójnej reprezentacji współrzędnych w różnych narzędziach GIS, zmniejszenia rozmiaru pliku lub spełnienia standardów wymiany danych. Poniżej zdefiniujemy opcje precyzji, zapiszemy geometrię, a następnie odczytamy ją ponownie, aby potwierdzić zaokrąglenie.

## Czym jest ograniczanie precyzji?

Ograniczanie precyzji to proces zaokrąglania ułamkowej części wartości współrzędnych do stałej liczby cyfr przed zapisaniem geometrii w formacie pliku. Zapewnia to, że każdy odbiorca pliku widzi te same wartości liczbowe, co pomaga uniknąć drobnych niezgodności, które mogą powodować błędy topologiczne.

## Dlaczego używać Aspose.GIS do kontroli precyzji?

Aspose.GIS obsługuje **ponad 50** formatów wejściowych i wyjściowych — w tym GeoJSON, Shapefile, KML i GML — i może przetwarzać pliki zawierające **setki tysięcy obiektów** bez ładowania całego zestawu danych do pamięci. Wbudowane modele precyzji pozwalają zaokrąglić współrzędne w jednym wywołaniu, eliminując potrzebę ręcznych skryptów post‑processingowych.

## Wymagania wstępne

### 1. Pobranie i instalacja
Pobierz najnowszy pakiet Aspose.GIS dla .NET ze strony oficjalnej: [download link](https://releases.aspose.com/gis/net/). Postępuj zgodnie z przewodnikiem instalacji, aby dodać pakiet NuGet do swojego projektu.

### 2. Import przestrzeni nazw
Dodaj wymagane przestrzenie nazw, aby uzyskać dostęp do klas GIS i pomocniczych narzędzi.

## Przewodnik krok po kroku

### Krok 1: Zdefiniuj opcje precyzji
Klasa `GeoJsonOptions` pozwala określić, ile cyfr po przecinku zachować dla współrzędnych X/Y oraz Z.

`PrecisionModel` definiuje, jak wartości współrzędnych są zaokrąglane lub zachowywane dokładnie podczas zapisu.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Krok 2: Ustaw ścieżkę wyjściową
Określ, gdzie zostanie zapisany wynikowy plik GeoJSON.

`VectorLayer` jest kontenerem Aspose.GIS dla kolekcji obiektów, które współdzielą ten sam schemat; zapisuje do podanej ścieżki, używając wcześniej ustawionych opcji.  

```csharp
var options = new GeoJsonOptions
{
    // Limit X and Y coordinates to 3 fractional digits.
    XYPrecisionModel = PrecisionModel.Rounding(3),

    // Write all fractional digits of the Z coordinate.
    ZPrecisionModel = PrecisionModel.Exact
};
```

### Krok 3: Utwórz i wypełnij geometrię
Otwórz nowy `VectorLayer` z wcześniej zdefiniowanymi opcjami, utwórz geometrię `Point` i dodaj ją do warstwy.

`Point` reprezentuje pojedynczą współrzędną (X, Y, opcjonalnie Z) w systemie odniesienia przestrzennego. Jest to najprostszy typ geometrii i jest używany tutaj do demonstracji zaokrąglania precyzji.  

```csharp
var path = "Your Document Directory" + "LimitPrecisionWhenWritingGeometries_out.json";
```

### Krok 4: Odczytaj i zweryfikuj precyzję
Otwórz właśnie utworzony plik i wypisz współrzędne. Powinieneś zobaczyć, że wartości X/Y są zaokrąglone do trzech miejsc po przecinku, podczas gdy wartość Z pozostaje dokładna.

Podczas odczytu pliku Aspose.GIS bezpośrednio parsuje zaokrąglone wartości, więc obiekt `Point` w pamięci odzwierciedla precyzję zdefiniowaną podczas zapisu.  

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    var point = new Point();
    point.X = 1.8888888;
    point.Y = 1.00123;
    point.Z = 1.123456789;

    Feature feature = layer.ConstructFeature();
    feature.Geometry = point;
    layer.Add(feature);
}
```

## Typowe problemy i wskazówki

- **Błędy ścieżki:** Upewnij się, że katalog w `path` istnieje lub użyj `Path.Combine` z `Environment.CurrentDirectory`, aby zbudować bezpieczną ścieżkę pliku.  
- **Precyzja nie zastosowana:** Sprawdź, czy przekazujesz obiekt `GeoJsonOptions` przy tworzeniu warstwy; w przeciwnym razie używana jest domyślna precyzja (pełny podwójny).  
- **Duże zestawy danych:** W przypadku operacji masowych rozważ ponowne użycie jednej instancji `VectorLayer` i dodawanie obiektów partiami, aby poprawić wydajność.

## Najczęściej zadawane pytania

**Q: Czy Aspose.GIS dla .NET jest kompatybilny z innymi formatami GIS?**  
A: Tak, obsługuje **ponad 50** formatów — w tym Shapefile, GeoJSON, KML, GML i CSV — umożliwiając płynną konwersję między nimi.

**Q: Czy mogę wypróbować Aspose.GIS dla .NET przed zakupem?**  
A: Oczywiście. Darmowa wersja próbna jest dostępna na stronie pobierania, zapewniając pełny dostęp do wszystkich funkcji w celu oceny.

**Q: Jak uzyskać tymczasową licencję do testów?**  
A: Tymczasowe licencje ewaluacyjne można wygenerować poprzez portal licencyjny Aspose; są ważne przez 30 dni.

**Q: Gdzie mogę uzyskać pomoc, jeśli napotkam problemy?**  
A: Forum Aspose.GIS oraz tag `aspose-gis` na Stack Overflow to doskonałe miejsca, aby zadawać pytania i znajdować rozwiązania od społeczności.

**Q: Czy biblioteka działa zarówno dla małych skryptów, jak i aplikacji na skalę przedsiębiorstwa?**  
A: Tak, Aspose.GIS jest zaprojektowany tak, aby obsługiwać wszystko, od szybkich prototypów po wysokowydajne obciążenia serwerowe, przetwarzając zestawy danych wielogigabajtowe przy niskim zużyciu pamięci.

---

**Ostatnia aktualizacja:** 2026-05-31  
**Testowano z:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose

## Powiązane samouczki

- [Utwórz warstwę wektorową, ogranicz precyzję za pomocą Aspose.GIS dla .NET](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [Jak konwertować GeoJSON – Aspose.GIS dla .NET](/gis/net/geo-data-conversion/)
- [Jak sprawdzić geometrię za pomocą Aspose.GIS dla .NET](/gis/net/geometry-analysis/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.GeoJson))
{
    var point = (IPoint)layer[0].Geometry;

    // Output: 1.889, 1.001, 1.123456789
    Console.WriteLine("{0}, {1}, {2}", point.X, point.Y, point.Z);
}
```

{{< /blocks/products/pf/main-wrap-class >}}