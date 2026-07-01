---
date: 2026-04-03
description: Dowiedz się, jak tworzyć wielokąt z otworem przy użyciu Aspose.GIS dla
  .NET. Ten przewodnik pokazuje, jak utworzyć otwór w wielokącie i pracować z danymi
  geoprzestrzennymi.
keywords:
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
linktitle: Utwórz wielokąt z geometrią otworu
second_title: Aspose.GIS .NET API
title: Utwórz wielokąt z otworem geometrycznym przy użyciu Aspose.GIS
url: /pl/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz wielokąt z otworem przy użyciu Aspose.GIS

## Wprowadzenie
W tym samouczku **create polygon with hole** geometrię przy użyciu Aspose.GIS dla .NET. Niezależnie od tego, czy tworzysz aplikację mapową, wykonujesz analizę przestrzenną, czy przygotowujesz dane dla usług GIS, znajomość sposobu wstawiania otworu w wielokącie jest niezbędna. Przeprowadzimy Cię przez cały proces krok po kroku, od konfiguracji środowiska po wygenerowanie ostatecznego obiektu wielokąta.

## Szybkie odpowiedzi
- **Co oznacza „create polygon with hole”?** Oznacza to tworzenie wielokąta, który zawiera jeden lub więcej wewnętrznych pierścieni (otworów) wykluczonych z powierzchni.  
- **Która biblioteka obsługuje to?** Aspose.GIS dla .NET zapewnia pełne wsparcie dla pierścieni zewnętrznych i wewnętrznych.  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna działa w środowisku deweloperskim; licencja komercyjna jest wymagana w produkcji.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Jak długo to trwa?** Zazwyczaj mniej niż 10 minut, aby zaimplementować i przetestować.

## Jak dodać otwór do wielokąta przy użyciu Aspose.GIS
Dodanie otworu to po prostu zdefiniowanie **interior ring** i dołączenie go do wielokąta. Biblioteka zajmuje się orientacją i poprawnością, więc możesz skoncentrować się na współrzędnych reprezentujących potrzebną pustkę.

## Czym jest „create polygon with hole”?
Tworzenie wielokąta z otworem polega na zdefiniowaniu **exterior ring**, który wyznacza zewnętrzną granicę, oraz jednego lub więcej **interior rings**, które wycinają puste przestrzenie. Pierścienie wewnętrzne są często nazywane *holes*, ponieważ reprezentują obszary, które nie są częścią powierzchni wielokąta.

## Dlaczego tworzyć otwór w wielokącie przy użyciu Aspose.GIS?
- **Accurate spatial modeling:** Rzeczywiste cechy, takie jak jeziora wewnątrz działek lub dziedzińce w budynkach, wymagają otworów.  
- **Interoperability:** Formaty takie jak Shapefile, GeoJSON i GML natywnie obsługują pierścienie wewnętrzne; Aspose.GIS je zachowuje.  
- **Performance:** Biblioteka zarządza poprawnością geometrii, więc nie musisz pisać własnego kodu walidacji.

## Scenariusze rzeczywiste dla wielokątów z otworami
1. **Land parcel with an internal lake** – jezioro jest modelowane jako otwór, więc nie jest liczone w powierzchni działki.  
2. **Building footprints with courtyards** – dziedziniec jest wyłączony z obrysu budynku.  
3. **Protected zones inside a larger conservation area** – możesz wykluczyć ograniczone sekcje bez tworzenia osobnych warstw.

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
1. Biblioteka Aspose.GIS dla .NET: możesz ją pobrać z [here](https://releases.aspose.com/gis/net/).  
2. Środowisko programistyczne: upewnij się, że masz skonfigurowane środowisko programistyczne z Visual Studio lub innym zainstalowanym IDE .NET.

## Importowanie przestrzeni nazw
Najpierw musisz zaimportować niezbędne przestrzenie nazw, aby pracować z funkcjami Aspose.GIS. Oto jak to zrobić:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Teraz przejdźmy do tworzenia geometrii wielokąta z otworem przy użyciu Aspose.GIS dla .NET.

## Krok 1: Utwórz obiekt Polygon
Zaczynamy od utworzenia pustego obiektu `Polygon`, który później będzie zawierał zarówno pierścień zewnętrzny, jak i wewnętrzny.

```csharp
Polygon polygon = new Polygon();
```

## Krok 2: Zdefiniuj pierścień zewnętrzny
Pierścień zewnętrzny definiuje zewnętrzną granicę wielokąta. Dodaj punkty w kolejności zgodnej z ruchem wskazówek zegara, aby utworzyć zamknięty kształt.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## Krok 3: Zdefiniuj pierścień wewnętrzny (otwór)
Następnie tworzymy pierścień wewnętrzny — to **hole**, który zostanie wykluczony z powierzchni wielokąta. Punkty są zazwyczaj dodawane w kolejności przeciwnie do ruchu wskazówek zegara, ale Aspose.GIS automatycznie obsługuje orientację.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## Krok 4: Przypisz pierścień zewnętrzny i dodaj pierścień wewnętrzny do wielokąta
Na koniec dołącz pierścień zewnętrzny do wielokąta, a następnie dodaj pierścień wewnętrzny (otwór). Metodę `AddInteriorRing` można wywołać wielokrotnie, jeśli potrzebujesz kilku otworów.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## Wskazówki i najlepsze praktyki
- **Orientation matters for readability** – choć Aspose.GIS automatycznie koryguje orientację, utrzymywanie pierścieni zewnętrznych w kierunku zgodnym z ruchem wskazówek zegara i pierścieni wewnętrznych przeciwnie ułatwia przeglądanie geometrii w przeglądarkach GIS.  
- **Close each ring** – zawsze powtarzaj pierwszą współrzędną jako ostatni punkt; zapewnia to poprawny zamknięty kształt.  
- **Validate after creation** – możesz wywołać `polygon.IsValid`, aby upewnić się, że geometria spełnia standardy OGC przed zapisaniem.

## Typowe problemy i rozwiązania
| Problem | Przyczyna | Rozwiązanie |
|-------|--------|-----|
| Otwór nie wyświetla się w przeglądarce GIS | Orientacja pierścienia wewnętrznego odwrócona | Upewnij się, że punkty są dodawane w przeciwnym kierunku do pierścienia zewnętrznego (przeciwnie do ruchu wskazówek zegara). |
| Błąd nieprawidłowego wielokąta | Pierścienie nie są zamknięte (pierwszy ≠ ostatni punkt) | Powtórz pierwszy punkt jako ostatni w każdym pierścieniu (jak pokazano powyżej). |
| Nieoczekiwana pusta geometria | Zapomniano przypisać `ExteriorRing` przed dodaniem pierścieni wewnętrznych | Ustaw najpierw `polygon.ExteriorRing`, a następnie wywołaj `AddInteriorRing`. |

## Najczęściej zadawane pytania
### 1. Co to jest Aspose.GIS?
Aspose.GIS jest biblioteką .NET, która umożliwia programistom pracę z danymi geoprzestrzennymi, pozwalając tworzyć, odczytywać i manipulować różnymi formatami plików geoprzestrzennych.

### 2. Czy mogę używać Aspose.GIS w projektach komercyjnych?
Tak, możesz używać Aspose.GIS zarówno w projektach prywatnych, jak i komercyjnych, kupując licencję. Odwiedź [here](https://purchase.aspose.com/buy) po więcej szczegółów.

### 3. Czy dostępna jest darmowa wersja próbna Aspose.GIS?
Tak, możesz skorzystać z darmowej wersji próbnej Aspose.GIS z [here](https://releases.aspose.com/).

### 4. Gdzie mogę znaleźć wsparcie dla Aspose.GIS?
Wsparcie dla Aspose.GIS znajdziesz na [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).

### 5. Jak mogę uzyskać tymczasową licencję dla Aspose.GIS?
Tymczasową licencję dla Aspose.GIS możesz uzyskać z [here](https://purchase.aspose.com/temporary-license/).

---

**Ostatnia aktualizacja:** 2026-04-03  
**Testowane z:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}