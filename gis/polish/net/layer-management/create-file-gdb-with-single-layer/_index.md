---
title: Utwórz plik GDB z pojedynczą warstwą
linktitle: Utwórz plik GDB z pojedynczą warstwą
second_title: Aspose.GIS .NET API
description: Odblokuj potencjał zarządzania danymi geoprzestrzennymi w .NET dzięki Aspose.GIS. Dowiedz się, jak krok po kroku tworzyć geobazy plikowe i warstwy. Pobierz teraz!
weight: 11
url: /pl/net/layer-management/create-file-gdb-with-single-layer/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz plik GDB z pojedynczą warstwą

## Wstęp
Czy jesteś gotowy, aby ulepszyć swoje aplikacje geoprzestrzenne dzięki solidnym geobazom plikowym i warstwom? Nie szukaj dalej niż Aspose.GIS dla .NET. W tym samouczku przeprowadzimy Cię przez proces tworzenia geobazy plikowej (GDB) z pojedynczą warstwą przy użyciu Aspose.GIS dla .NET. Wykorzystaj bez wysiłku możliwości zarządzania danymi przestrzennymi i wizualizacji w aplikacjach .NET.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
1.  Aspose.GIS dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.GIS. Można go pobrać z[Strona pobierania Aspose.GIS dla .NET](https://releases.aspose.com/gis/net/).
2. Środowisko programistyczne: Skonfiguruj działające środowisko programistyczne .NET na swoim komputerze.
3. Katalog dokumentów: Wybierz lub utwórz katalog w swoim systemie, w którym będziesz przechowywać pliki danych geoprzestrzennych.
## Importuj przestrzenie nazw
Aby rozpocząć, musisz zaimportować niezbędne przestrzenie nazw do swojego projektu .NET. Te przestrzenie nazw zapewnią dostęp do funkcjonalności Aspose.GIS. Dodaj następujące wiersze na początku pliku kodu:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```
## Krok 1: Skonfiguruj katalog dokumentów
```csharp
string dataDir = "Your Document Directory";
```
Zastąp „Twój katalog dokumentów” ścieżką do katalogu, w którym chcesz przechowywać pliki danych geoprzestrzennych.
## Krok 2: Utwórz geobazę plikową z pojedynczą warstwą
```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```
Ten fragment kodu tworzy geobazę plikową z pojedynczą warstwą i dodaje do niej element liniowy.
## Krok 3: Otwórz geobazę plików i pobierz informacje o warstwach
```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Dane wyjściowe: Liczba funkcji: 1
}
```
W tym kroku otwieramy utworzoną geobazę plikową, pobieramy warstwę o nazwie „warstwa” i drukujemy liczbę obiektów w warstwie.
## Wniosek
Gratulacje! Pomyślnie utworzyłeś geobazę plikową z pojedynczą warstwą przy użyciu Aspose.GIS dla .NET. Z łatwością poznaj szerokie możliwości zarządzania danymi przestrzennymi w swoich aplikacjach.
## Często Zadawane Pytania
### Czy mogę używać Aspose.GIS dla .NET w moich istniejących projektach .NET?
Tak, Aspose.GIS dla .NET można bezproblemowo zintegrować z istniejącymi projektami .NET.
### Czy dostępna jest wersja próbna Aspose.GIS dla .NET?
 Tak, możesz poznać funkcje Aspose.GIS dla .NET, pobierając plik[bezpłatna wersja próbna](https://releases.aspose.com/).
### Gdzie mogę znaleźć szczegółową dokumentację Aspose.GIS dla .NET?
 Patrz[dokumentacja](https://reference.aspose.com/gis/net/) aby uzyskać wyczerpujące informacje na temat Aspose.GIS dla .NET.
### Jak mogę uzyskać wsparcie dla Aspose.GIS dla .NET?
 Odwiedzić[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33) za wsparcie i pomoc społeczną.
### Czy dostępne są licencje tymczasowe dla Aspose.GIS dla .NET?
 Tak, możesz uzyskać[licencja tymczasowa](https://purchase.aspose.com/temporary-license/) dla Aspose.GIS dla .NET.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
