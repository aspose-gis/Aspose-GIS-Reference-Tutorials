---
date: 2026-01-05
description: Dowiedz się, jak odczytywać pliki shapefile w C# przy użyciu Aspose.GIS
  dla .NET, pobierać wszystkie wartości atrybutów obiektów i wydajnie wyświetlać atrybuty.
linktitle: Get All Feature Attribute Values
second_title: Aspose.GIS .NET API
title: Odczyt pliku Shapefile w C# – Pobierz wszystkie wartości atrybutów obiektów
url: /pl/net/layer-interaction-and-data-access/get-all-feature-attribute-values/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pobierz wszystkie wartości atrybutów obiektów

## Wprowadzenie
Witamy w świecie programowania geoprzestrzennego z Aspose.GIS dla .NET! W tym samouczku dowiesz się **jak odczytać shapefile w C#** i pobrać każdą wartość atrybutu z jego obiektów. Niezależnie od tego, czy tworzysz aplikację mapową, czy przetwarzasz dane przestrzenne wsadowo, opanowanie ekstrakcji atrybutów jest niezbędne. Zanurzmy się i zobaczmy kod w działaniu.

## Szybkie odpowiedzi
- **Co robi ten kod?** Otwiera plik Shapefile i odczytuje wszystkie, wybrane lub zrzucane wartości atrybutów z każdego obiektu.  
- **Jakiej biblioteki potrzebuję?** Aspose.GIS dla .NET (kompatybilny z .NET Framework i .NET Core).  
- **Czy potrzebna jest licencja?** Licencja tymczasowa działa w trybie testowym; pełna licencja jest wymagana w środowisku produkcyjnym.  
- **Czy mogę odczytywać inne formaty?** Tak – to samo API obsługuje GeoJSON, KML i wiele innych.  
- **Jak zrzucić atrybuty?** Użyj `feature.GetValuesDump()`, aby uzyskać elastyczną tablicę obiektów.

## Co oznacza „read shapefile C#”?
Odczytanie Shapefile w C# oznacza otwarcie pliku .shp przy użyciu biblioteki GIS, iterację po jego wektorowych obiektach oraz dostęp do danych atrybutowych przechowywanych w powiązanym pliku .dbf. Aspose.GIS abstrahuje niskopoziomową obsługę plików, pozwalając skupić się na potrzebnych wartościach atrybutów.

## Dlaczego warto używać Aspose.GIS do odczytu atrybutów?
- **Proste API** – intuicyjne metody takie jak `GetValues` i `GetValuesDump`.  
- **Cross‑platform** – działa na Windows, Linux i macOS z .NET Core.  
- **Bogate wsparcie formatów** – obsługuje Shapefile, GeoJSON, GML i inne bez dodatkowych wtyczek.  
- **Wydajność** – szybka iteracja po dużych zestawach danych.

## Wymagania wstępne
Zanim wyruszysz w tę ekscytującą podróż, upewnij się, że masz spełnione następujące wymagania:
- Aspose.GIS dla .NET: pobierz i zainstaluj bibliotekę ze [strony pobierania Aspose.GIS dla .NET](https://releases.aspose.com/gis/net/).
- Środowisko programistyczne: skonfiguruj środowisko .NET, np. Visual Studio.
- Shapefile: przygotuj przykładowy plik Shapefile (np. „InputShapeFile.shp”) w katalogu dokumentów.

## Importowanie przestrzeni nazw
W swoim kodzie C# rozpocznij od zaimportowania niezbędnych przestrzeni nazw, aby wykorzystać funkcje Aspose.GIS:
```csharp
using System;
using Aspose.Gis;
```

## Krok 1: Ustaw katalog dokumentów
```csharp
string dataDir = "Your Document Directory";
```
Zastąp „Your Document Directory” rzeczywistą ścieżką, w której znajduje się Twój plik Shapefile.

## Krok 2: Otwórz warstwę wektorową
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for further steps goes here
}
```
Ten krok polega na otwarciu pliku Shapefile przy użyciu Aspose.GIS, określając ścieżkę do pliku i format (w tym przypadku Shapefile).

## Krok 3: Pobierz wszystkie wartości atrybutów obiektów
```csharp
foreach (var feature in layer)
{
    // reads all the attributes into an array.
    object[] all = new object[3];
    feature.GetValues(all);
    Console.WriteLine("all    : {0}, {1}, {2}", all);
    // Your code for handling all attribute values goes here
    Console.WriteLine();
}
```
Fragment kodu pokazuje **jak odczytać atrybuty** dla każdego obiektu, ładując je do tablicy o stałym rozmiarze.

## Krok 4: Pobierz wybrane wartości atrybutów obiektów
```csharp
foreach (var feature in layer)
{
    // reads several attributes into an array.
    object[] several = new object[2];
    feature.GetValues(several);
    Console.WriteLine("several: {0}, {1}", several);
    // Your code for handling several attribute values goes here
    Console.WriteLine();
}
```
Tutaj demonstrujemy **jak odczytać konkretne wartości atrybutów**, gdy potrzebny jest tylko podzbiór pól.

## Krok 5: Pobierz wartości atrybutów jako zrzut obiektów
```csharp
foreach (var feature in layer)
{
    // reads attributes as a dump of objects.
    var dump = feature.GetValuesDump();
    Console.WriteLine("dump   : {0}, {1}, {2}", dump);
    // Your code for handling dumped attribute values goes here
    Console.WriteLine();
}
```
Ostatni krok prezentuje **jak zrzucić atrybuty** przy użyciu `GetValuesDump()`, który zwraca elastyczną kolekcję, którą możesz przeglądać lub serializować.

## Typowe problemy i rozwiązania
- **Niezgodność rozmiaru tablicy** – Upewnij się, że tablica przekazywana do `GetValues` ma taką samą liczbę elementów, jaką oczekujesz; w przeciwnym razie otrzymasz wpisy `null`.  
- **Plik nie został znaleziony** – Sprawdź, czy `dataDir` wskazuje na właściwy folder i czy nazwa pliku Shapefile jest zapisana dokładnie.  
- **Wyjątek licencyjny** – Jeśli pojawi się błąd licencji, zastosuj licencję tymczasową lub pełną przed wywołaniem jakichkolwiek metod API.

## Najczęściej zadawane pytania
### Czy Aspose.GIS jest kompatybilny z .NET Core?
Tak, Aspose.GIS jest w pełni kompatybilny z .NET Core, co pozwala tworzyć aplikacje cross‑platformowe.

### Czy mogę pracować z różnymi formatami plików GIS przy użyciu Aspose.GIS?
Oczywiście! Aspose.GIS obsługuje różne formaty, w tym Shapefile, GeoJSON i wiele innych.

### Czy istnieje forum społecznościowe wsparciaose.GIS?
Tak, pomoc i dyskusje ze społecznością Aspose.GIS znajdziesz na [forum wsparcia](https://forum.aspose.com/c/gis/33).

### Jak mogę uzyskać licencję tymczasową dla Aspose.GIS?
Licencję tymczasową do testów możesz zdobyć [tutaj](https://purchase.aspose.com/-license).

### Gdzie znajdę szczegółową dokumentację Aspose.GIS?
Kompleksowa dokumentacja jest dostępna [tutaj](https://reference.aspose.com/gis/net/).

### Jak pobrać tylko atrybut „Name” z każdego obiektu?
Użyj `GetValues` z tablicą o rozmiarze jednego elementu i przekaż indeks pola „Name”, albo wywołaj bezpośrednio `feature["Name"]`.

### Jaka jest różnica między `GetValues` a `GetValuesDump`?
`GetValues` wypełnia wcześniej przydzieloną tablicę surowymi wartościami, natomiast `GetValuesDump` zwraca tablicę obiektów, którą można iterować bez wcześniejszej znajomości schematu.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ostatnia aktualizacja:** 2026-01-05  
**Testowano z:** Aspose.GIS dla .NET (najnowsze wydanie)  
**Autor:** Aspose  

---