---
date: 2026-09-05
description: Dowiedz się, jak utworzyć wewnętrzny pierścień wielokąta z otworem przy
  użyciu Aspose.GIS dla .NET. Ten przewodnik pokazuje, jak dodać otwór do wielokąta
  i pracować z danymi.
keywords:
- polygon interior ring
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
lastmod: 2026-09-05
linktitle: Utwórz Polygon z Hole Geometry
og_description: Dowiedz się, jak utworzyć wewnętrzny pierścień wielokąta z otworem
  przy użyciu Aspose.GIS dla .NET. Ten przewodnik pokazuje, jak dodać otwór do wielokąta
  i pracować z danymi.
og_image_alt: Guide showing how to create a polygon interior ring with a hole using
  Aspose.GIS
og_title: Utwórz wewnętrzny pierścień wielokąta z otworem przy użyciu Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-09-05'
  description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  headline: Create a polygon interior ring with a hole using Aspose.GIS
  type: TechArticle
- description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  name: Create a polygon interior ring with a hole using Aspose.GIS
  steps:
  - name: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
    text: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
  - name: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
    text: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
  - name: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
    text: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
  - name: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
    text: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
  - name: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
    text: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
  type: HowTo
- questions:
  - answer: It means building a polygon that contains one or more interior rings (holes)
      that are excluded from the area.
    question: What does “create polygon with hole” mean?
  - answer: Aspose.GIS for .NET provides full support for exterior and interior rings.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  - answer: Typically under 10 minutes to implement and test.
    question: How long does it take?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- polygon interior ring
- Aspose.GIS
- geospatial .NET
- create polygon with hole
- GIS development
title: Utwórz wewnętrzny pierścień wielokąta z otworem przy użyciu Aspose.GIS
url: /pl/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz wewnętrzny pierścień wielokąta z otworem przy użyciu Aspose.GIS

## Wprowadzenie
W tym samouczku nauczysz się, jak **utworzyć wewnętrzny pierścień wielokąta**, który zawiera otwór, przy użyciu Aspose.GIS dla .NET. Niezależnie od tego, czy tworzysz aplikację mapową, wykonujesz analizę przestrzenną, czy przygotowujesz dane dla usług GIS, osadzenie otworu w wielokącie jest podstawową umiejętnością. Przejdziemy przez cały proces — od konfiguracji środowiska programistycznego po wygenerowanie prawidłowego obiektu wielokąta, który można zapisać w dowolnym obsługiwanym formacie geoprzestrzennym.

## Szybkie odpowiedzi
- **Co oznacza „utworzyć wielokąt z otworem”?** Oznacza to budowanie wielokąta, który zawiera jeden lub więcej wewnętrznych pierścieni (otworów) wykluczonych z powierzchni.  
- **Która biblioteka obsługuje to?** Aspose.GIS for .NET zapewnia pełne wsparcie dla pierścieni zewnętrznych i wewnętrznych.  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna działa w środowisku deweloperskim; licencja komercyjna jest wymagana w produkcji.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Jak długo to trwa?** Zazwyczaj mniej niż 10 minut na implementację i testy.

## Jak dodać otwór do wielokąta przy użyciu Aspose.GIS
Załaduj swoje środowisko GIS, zdefiniuj pierścień zewnętrzny, a następnie dołącz jeden lub więcej pierścieni wewnętrznych. Aspose.GIS automatycznie orientuje pierścienie i waliduje geometrię, dzięki czemu możesz skupić się na współrzędnych reprezentujących potrzebną pustkę.

## Czym jest wewnętrzny pierścień wielokąta?
**Wewnętrzny pierścień wielokąta** to wewnętrzna granica, która odejmuje obszar od zewnętrznego kształtu wielokąta.  
Tworzysz go, definiując zamkniętą sekwencję punktów, które Aspose.GIS traktuje jako otwór, wykluczany przy obliczaniu powierzchni lub renderowaniu kształtu.

## Dlaczego tworzyć wewnętrzny pierścień wielokąta przy użyciu Aspose.GIS?
Aspose.GIS waliduje i koryguje orientację pierścieni w mniej niż 5 ms dla typowych wielokątów o 200 punktach, eliminując potrzebę własnego kodu walidującego. Obsługuje także **ponad 30 formatów plików geoprzestrzennych** (Shapefile, GeoJSON, GML, KML, itp.) i może przetwarzać wielokąty z nawet 10 000 punktami bez wczytywania całego pliku do pamięci, zapewniając zarówno szybkość, jak i skalowalność.

## Scenariusze rzeczywiste dla wielokątów z otworami
1. **Działka z wewnętrznym jeziorem** – jezioro jest modelowane jako otwór, więc nie jest liczone w powierzchni działki.  
2. **Obrys budynków z dziedzińcami** – dziedziniec jest wykluczony z obrysu budynku.  
3. **Strefy chronione wewnątrz większego obszaru ochronnego** – możesz wykluczyć ograniczone sekcje bez tworzenia osobnych warstw.

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz następujące elementy:
1. Biblioteka Aspose.GIS for .NET: możesz ją pobrać ze **strony pobierania Aspose.GIS for .NET**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).  
2. Środowisko programistyczne: Upewnij się, że masz skonfigurowane środowisko programistyczne z Visual Studio lub innym zainstalowanym IDE .NET.

## Importowanie przestrzeni nazw
Przestrzeń nazw `Aspose.Gis` zawiera wszystkie typy geometrii, których będziesz potrzebować, w tym `Polygon`, `LinearRing` oraz metody pomocnicze do walidacji.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Teraz przejdźmy do utworzenia geometrii wielokąta z otworem przy użyciu Aspose.GIS for .NET.

## Krok 1: utwórz obiekt wielokąta
`Polygon` jest typem geometrii Aspose.GIS, który reprezentuje płaski wielokąt z opcjonalnymi pierścieniami wewnętrznymi. Zaczynamy od utworzenia pustego obiektu `Polygon`, który później będzie zawierał zarówno pierścień zewnętrzny, jak i wewnętrzne.

```csharp
Polygon polygon = new Polygon();
```

## Krok 2: zdefiniuj pierścień zewnętrzny
`LinearRing` jest klasą używaną zarówno dla granic zewnętrznych, jak i wewnętrznych. Pierścień zewnętrzny definiuje zewnętrzną granicę wielokąta. Dodaj punkty w kolejności zgodnej z ruchem wskazówek zegara, aby utworzyć zamknięty kształt.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## Krok 3: zdefiniuj pierścień wewnętrzny (otwór)
`LinearRing` reprezentuje również pierścienie wewnętrzne. Pierścień wewnętrzny jest **otworem**, który zostanie wykluczony z powierzchni wielokąta. Punkty zazwyczaj dodaje się w kolejności przeciwnie do ruchu wskazówek zegara, ale Aspose.GIS automatycznie obsługuje orientację.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## Krok 4: przypisz pierścień zewnętrzny i dodaj pierścień wewnętrzny do wielokąta
Metoda `AddInteriorRing` dołącza jeden lub więcej pierścieni wewnętrznych do obiektu `Polygon`. Wywołaj ją po ustawieniu właściwości `ExteriorRing`; możesz powtórzyć wywołanie, aby dodać wiele otworów.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## Wskazówki i najlepsze praktyki
- **Orientacja ma znaczenie dla czytelności** – choć Aspose.GIS automatycznie koryguje orientację, utrzymywanie pierścieni zewnętrznych zgodnie z ruchem wskazówek zegara i pierścieni wewnętrznych przeciwnie do ruchu wskazówek zegara ułatwia przeglądanie geometrii w przeglądarkach GIS.  
- **Zamknij każdy pierścień** – zawsze powtórz pierwszą współrzędną jako ostatni punkt; zapewnia to prawidłowy zamknięty kształt.  
- **Waliduj po utworzeniu** – możesz wywołać `polygon.IsValid`, aby upewnić się, że geometria spełnia standardy OGC przed zapisaniem.

## Typowe problemy i rozwiązania
| Problem | Powód | Rozwiązanie |
|-------|--------|-----|
| Otwór nie wyświetla się w przeglądarce GIS | Odwrócona orientacja pierścienia wewnętrznego | Upewnij się, że punkty są dodawane w przeciwnym kierunku do pierścienia zewnętrznego (przeciwnie do ruchu wskazówek zegara). |
| Błąd nieprawidłowego wielokąta | Pierścienie nie są zamknięte (pierwszy ≠ ostatni punkt) | Powtórz pierwszy punkt jako ostatni w każdym pierścieniu (jak pokazano powyżej). |
| Nieoczekiwana pusta geometria | Zapomniano przypisać `ExteriorRing` przed dodaniem pierścieni wewnętrznych | Najpierw ustaw `polygon.ExteriorRing`, a następnie wywołaj `AddInteriorRing`. |

## Najczęściej zadawane pytania
### 1. Czym jest Aspose.GIS?
Aspose.GIS to biblioteka .NET, która umożliwia programistom pracę z danymi geoprzestrzennymi, pozwalając na tworzenie, odczyt i modyfikację różnych formatów plików geoprzestrzennych.

### 2. Czy mogę używać Aspose.GIS w projektach komercyjnych?
Tak, możesz używać Aspose.GIS zarówno w projektach prywatnych, jak i komercyjnych po zakupie licencji. Odwiedź **stronę zakupu Aspose.GIS**([https://purchase.aspose.com/buy](https://purchase.aspose.com/buy)) po więcej szczegółów.

### 3. Czy dostępna jest darmowa wersja próbna Aspose.GIS?
Tak, możesz skorzystać z darmowej wersji próbnej Aspose.GIS ze **strony pobierania darmowej wersji próbnej Aspose.GIS**([https://releases.aspose.com/](https://releases.aspose.com/)).

### 4. Gdzie mogę znaleźć wsparcie dla Aspose.GIS?
Wsparcie dla Aspose.GIS znajdziesz na [forum Aspose.GIS](https://forum.aspose.com/c/gis/33).

### 5. Jak mogę uzyskać tymczasową licencję dla Aspose.GIS?
Tymczasową licencję dla Aspose.GIS możesz uzyskać na **stronie tymczasowej licencji Aspose.GIS**([https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/)).

**Ostatnia aktualizacja:** 2026-09-05  
**Testowano z:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose

## Powiązane samouczki

- [Jak utworzyć geometrię wielokąta przy użyciu Aspose.GIS dla .NET](/gis/net/geometry-creation/create-polygon-geometry/)
- [Jak utworzyć geometrię MultiPolygon przy użyciu Aspose.GIS](/gis/net/geometry-creation/create-multipolygon-geometry/)
- [Konwertuj wielokąt na linię przy użyciu Aspose.GIS dla .NET](/gis/net/geometry-processing/replace-polygons-with-lines/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}