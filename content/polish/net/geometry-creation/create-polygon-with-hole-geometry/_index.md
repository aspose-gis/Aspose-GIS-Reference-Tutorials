---
title: Utwórz wielokąt z geometrią otworu za pomocą Aspose.GIS
linktitle: Utwórz wielokąt z geometrią otworu
second_title: Aspose.GIS .NET API
description: Dowiedz się, jak utworzyć wielokąt z geometrią otworu przy użyciu Aspose.GIS dla .NET. Samouczek krok po kroku z przykładami kodu.
type: docs
weight: 13
url: /pl/net/geometry-creation/create-polygon-with-hole-geometry/
---
## Wstęp
W tym samouczku omówimy proces tworzenia wielokąta z geometrią otworu przy użyciu Aspose.GIS dla .NET. Aspose.GIS to potężna biblioteka, która umożliwia programistom pracę z danymi geoprzestrzennymi w aplikacjach .NET. 
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
1. Biblioteka Aspose.GIS dla .NET: Możesz ją pobrać z[Tutaj](https://releases.aspose.com/gis/net/).
2. Środowisko programistyczne: Upewnij się, że masz skonfigurowane środowisko programistyczne z zainstalowanym programem Visual Studio lub dowolnym innym środowiskiem .NET IDE.
## Importuj przestrzenie nazw
Po pierwsze, musisz zaimportować niezbędne przestrzenie nazw, aby móc pracować z funkcjonalnościami Aspose.GIS. Oto jak to zrobić:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Teraz przejdźmy do tworzenia wielokąta z geometrią otworu przy użyciu Aspose.GIS dla .NET.
## Krok 1: Utwórz obiekt wielokątny
```csharp
Polygon polygon = new Polygon();
```
## Krok 2: Zdefiniuj pierścień zewnętrzny
```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```
## Krok 3: Zdefiniuj pierścień wewnętrzny (otwór)
```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```
## Krok 4: Przypisz pierścień zewnętrzny i dodaj pierścień wewnętrzny do wielokąta
```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```
## Wniosek
Gratulacje! Pomyślnie nauczyłeś się tworzyć wielokąt z geometrią otworu przy użyciu Aspose.GIS dla .NET. Wiedza ta będzie korzystna w różnych zastosowaniach geoprzestrzennych, gdzie takie geometrie są niezbędne.
## Często zadawane pytania
### 1. Co to jest Aspose.GIS?
Aspose.GIS to biblioteka .NET, która umożliwia programistom pracę z danymi geoprzestrzennymi, umożliwiając im tworzenie, odczytywanie i manipulowanie różnymi formatami plików geoprzestrzennych.
### 2. Czy mogę używać Aspose.GIS w projektach komercyjnych?
 Tak, możesz używać Aspose.GIS zarówno do projektów osobistych, jak i komercyjnych, kupując licencję. Odwiedzać[Tutaj](https://purchase.aspose.com/buy) po więcej szczegółów.
### 3. Czy dostępna jest bezpłatna wersja próbna Aspose.GIS?
 Tak, możesz skorzystać z bezpłatnej wersji próbnej Aspose.GIS z[Tutaj](https://releases.aspose.com/).
### 4. Gdzie mogę znaleźć wsparcie dla Aspose.GIS?
 Wsparcie dla Aspose.GIS znajdziesz na stronie[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33).
### 5. Jak mogę uzyskać tymczasową licencję na Aspose.GIS?
 Tymczasową licencję na Aspose.GIS można uzyskać od[Tutaj](https://purchase.aspose.com/temporary-license/).