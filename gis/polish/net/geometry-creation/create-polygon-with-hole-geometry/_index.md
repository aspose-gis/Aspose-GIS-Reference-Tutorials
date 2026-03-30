---
date: 2025-12-20
description: „Dowiedz się, jak tworzyć wielokąty z otworem przy użyciu Aspose.GIS
  dla .NET. Ten przewodnik pokazuje, jak utworzyć otwór w wielokącie i pracować z
  danymi geoprzestrzennymi.”
linktitle: Create Polygon with Hole Geometry
second_title: Aspose.GIS .NET API
title: Utwórz wielokąt z otworem geometrycznym przy użyciu Aspose.GIS
url: /pl/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tworzenie wielokąta z otworem przy użyciu Aspose.GIS

## Wprowadzenie
W tym samouczku **utworzysz wielokąt z otworem** przy użyciu Aspose.GIS dla .NET. Niezależnie od tego, czy budujesz aplikację mapową, wykonujesz analizę przestrzenną, czy przygotowujesz dane dla usług GIS, znajomość wstawiania otworu wewnątrz wielokąta jest niezbędna. Przeprowadzimy Cię krok po kroku, od konfiguracji środowiska po wygenerowanie ostatecznego obiektu wielokąta.

## Szybkie odpowiedzi
- **Co oznacza „tworzenie wielokąta z otworem”?** Oznacza to budowanie wielokąta, który zawiera jeden lub więcej pierścieni wewnętrznych (otworów) wyłączonych z powierzchni.
- **Która biblioteka to obsługuje?** Aspose.GIS dla .NET zapewnia pełne wsparcie dla pierścieni zewnętrznych i wewnętrznych.
- **Czy potrzebna jest licencja?** Darmowa wersja próbna wystarcza do rozwoju; licencja komercyjna jest wymagana w produkcji.
- **Jakie wersje .NET są wspierane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Ile to zajmuje?** Zazwyczaj mniej niż 10 minut na implementację i testy.

## Co to jest „tworzenie wielokąta z otworem”?
Tworzenie wielokąta z otworem polega na zdefiniowaniu **pierścienia zewnętrznego**, który wyznacza granicę zewnętrzną, oraz jednego lub więcej **pierścieni wewnętrznych**, które wycinają puste przestrzenie. Pierścienie wewnętrzne często nazywane są *otworami*, ponieważ reprezentują obszary niebędące częścią powierzchni wielokąta.

## Dlaczego tworzyć otwór w wielokącie przy użyciu Aspose.GIS?
- **Precyzyjne modelowanie przestrzenne:** Rzeczywiste obiekty, takie jak jeziora w obrębie parceli ziemi czy dziedzińce w budynkach, wymagają otworów.
- **Interoperacyjność:** Formatów takich jak Shapefile, GeoJSON i GML natywnie obsługują pierścienie wewnętrzne; Aspose.GIS je zachowuje.
- **Wydajność:** Biblioteka zarządza poprawnością geometrii, więc nie musisz pisać własnego kodu walidacji.

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz następujące elementy:
1. Biblioteka Aspose.GIS dla .NET: możesz ją pobrać [tutaj](https://releases.aspose.com/gis/net/).
2. Środowisko programistyczne: zapewnij, że masz skonfigurowane środowisko programistyczne z Visual Studio lub innym IDE .NET.

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

Teraz przejdźmy do tworzenia wielokąta z otworem przy użyciu Aspose.GIS dla .NET.

## Krok 1: Utworzenie obiektu Polygon
Zaczynamy od zainicjowania pustego obiektu `Polygon`, który później będzie zawierał zarówno pierścień zewnętrzny, jak i wewnętrzny.

```csharp
Polygon polygon = new Polygon();
```

## Krok 2: Definiowanie pierścienia zewnętrznego
Pierścień zewnętrzny definiuje granicę zewnętrzną wielokąta. Dodaj punkty w kolejności zgodnej z ruchem wskazówek zegara, aby utworzyć zamkniętą figurę.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## Krok 3: Definiowanie pierścienia wewnętrznego (Otwór)
Następnie tworzymy pierścień wewnętrzny — to **otwór**, który zostanie wykluczony z powierzchni wielokąta. Punkty zazwyczaj dodaje się w kolejności przeciwną do ruchu wskazówek zegara, ale Aspose.GIS automatycznie obsługuje orientację.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## Krok 4: Przypisanie pierścienia zewnętrznego i dodanie pierścienia wewnętrznego do wielokąta
Na koniec podłącz pierścień zewnętrzny do wielokąta, a następnie dodaj pierścień wewnętrzny (otwór). Metodę `AddInteriorRing` można wywołać wielokrotnie, jeśli potrzebujesz kilku otworów.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## Częste problemy i rozwiązania
| Problem | Powód | Rozwiązanie |
|---------|-------|-------------|
| Otwór nie wyświetla się w przeglądarce GIS | Odwrócona orientacja pierścienia wewnętrznego | Upewnij się, że punkty są dodane w przeciwnym kierunku do pierścienia zewnętrznego (przeciwnie do ruchu wskazówek zegara). |
| Błąd nieprawidłowego wielokąta | Pierścienie nie zamknięte (pierwszy ≠ ostatni punkt) | Powtórz pierwszy punkt jako ostatni w każdym pierścieniu (jak pokazano powyżej). |
| Nieoczekiwana pusta geometria | Zapomniano przypisać `ExteriorRing` przed dodaniem pierścieni wewnętrznych | Najpierw ustaw `polygon.ExteriorRing`, a potem wywołaj `AddInteriorRing`. |

## Podsumowanie
Gratulacje! Pomyślnie nauczyłeś się **tworzyć wielokąt z otworem** przy użyciu Aspose.GIS dla .NET. Ta technika jest podstawą wielu scenariuszy geoprzestrzennych, w których trzeba przedstawić złożone kształty z wewnętrznymi pustkami.

## Najczęściej zadawane pytania
### 1. Co to jest Aspose.GIS?
Aspose.GIS to biblioteka .NET, która umożliwia programistom pracę z danymi geoprzestrzennymi, pozwalając na tworzenie, odczyt i manipulację różnymi formatami plików geoprzestrzennych.

### 2. Czy mogę używać Aspose.GIS w projektach komercyjnych?
Tak, możesz używać Aspose.GIS zarówno w projektach prywatnych, jak i komercyjnych po zakupie licencji. Odwiedź [tutaj](https://purchase.aspose.com/buy) po więcej szczegółów.

### 3. Czy dostępna jest darmowa wersja próbna Aspose.GIS?
Tak, możesz skorzystać z darmowej wersji próbnej Aspose.GIS [tutaj](https://releases.aspose.com/).

### 4. Gdzie mogę znaleźć wsparcie dla Aspose.GIS?
Wsparcie dla Aspose.GIS znajdziesz na [forum Aspose.GIS](https://forum.aspose.com/c/gis/33).

### 5. Jak mogę uzyskać tymczasową licencję dla Aspose.GIS?
Tymczasową licencję dla Aspose.GIS możesz uzyskać [tutaj](https://purchase.aspose.com/temporary-license/).

---

**Ostatnia aktualizacja:** 2025-12-20  
**Testowano z:** Aspose.GIS 24.11 dla .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}