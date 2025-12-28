---
date: 2025-12-28
description: Dowiedz się, jak odczytywać GeoJSON ze strumienia przy użyciu Aspose.GIS
  dla .NET. Ten przewodnik po odczycie GeoJSON w C# zawiera krok po kroku przykład
  integracji danych geoprzestrzennych.
linktitle: Read GeoJSON from Stream
second_title: Aspose.GIS .NET API
title: Jak odczytać GeoJSON ze strumienia przy użyciu Aspose.GIS dla .NET
url: /pl/net/layer-data-operations/read-geojson-from-stream/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak odczytać GeoJSON ze strumienia przy użyciu Aspose.GIS dla .NET

## Wprowadzenie
Jeśli zastanawiasz się **jak odczytać geojson** w aplikacji .NET, trafiłeś we właściwe miejsce. W tym samouczku przejdziemy przez kompletny **c# geojson example**, który pokazuje, jak zamienić ciąg GeoJSON, otworzyć warstwę GeoJSON z pamięciowego strumienia oraz wyodrębnić właściwości GeoJSON przy użyciu Aspose.GIS. Po zakończeniu będziesz mieć gotowy wzorzec, który możesz wkleić do dowolnego projektu wymagającego pracy z danymi geoprzestrzennymi.

## Szybkie odpowiedzi
- **Jakiej biblioteki powinienem używać?** Aspose.GIS dla .NET  
- **Czy mogę odczytać GeoJSON bezpośrednio ze strumienia?** Tak – użyj `VectorLayer.Open` z `AbstractPath.FromStream`.  
- **Czy potrzebna jest licencja do rozwoju?** Darmowa wersja próbna wystarczy do testów; licencja jest wymagana w produkcji.  
- **Jakie wersje .NET są wspierane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Czy wyodrębnianie właściwości jest proste?** Tak – wywołaj `GetValue<T>(columnName)` na obiekcie feature.

## Co oznacza „jak odczytać geojson”?
Odczyt GeoJSON oznacza parsowanie formatu opartego na JSON, który opisuje elementy geograficzne (punkty, linie, wielokąty) i udostępnianie tych elementów jako obiektów, które możesz zapytać, edytować lub renderować w swojej aplikacji.

## Dlaczego warto używać Aspose.GIS do **otwierania warstwy geojson**?
Aspose.GIS ukrywa szczegóły niskopoziomowego parsowania i zapewnia spójne API dla wielu formatów GIS. Pozwala **otworzyć warstwę geojson** bezpośrednio ze strumienia, efektywnie obsługiwać duże pliki i uzyskać dostęp do atrybutów elementów bez pisania własnych parserów JSON.

## Wymagania wstępne
Zanim przejdziemy dalej, upewnij się, że masz:

1. **Podstawową znajomość C#** – powinieneś być pewny w składni .NET i środowisku Visual Studio.  
2. **Zainstalowany Aspose.GIS** – pobierz bibliotekę z [tutaj](https://releases.aspose.com/gis/net/).  
3. **Środowisko programistyczne** – Visual Studio, Visual Studio Code lub JetBrains Rider będą w porządku.  

## Importowanie przestrzeni nazw
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## Krok 1: **Konwersja ciągu GeoJSON** – **c# geojson example**
Najpierw tworzymy ciąg JSON, który reprezentuje prostą `FeatureCollection`. To jest część **convert geojson string** w naszym przepływie pracy.

```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```

## Krok 2: **Otwórz warstwę GeoJSON** ze strumienia i **wyodrębnij właściwości geojson**
Teraz wprowadzamy ciąg do `MemoryStream`, otwieramy go jako warstwę GIS i demonstrujemy, jak odczytać wartości atrybutów (krok **extract geojson properties**).

```csharp
using (var memoryStream = new MemoryStream(Encoding.UTF8.GetBytes(geoJson)))
using (var layer = VectorLayer.Open(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    Console.WriteLine(layer.Count); // Output: 2
    Console.WriteLine(layer[1].GetValue<string>("name")); // Output: Mary
}
```

> **Wskazówka:** `VectorLayer.Open` automatycznie wykrywa format GeoJSON, gdy przekażesz `Drivers.GeoJson`. Możesz także otwierać pliki bezpośrednio, podając ścieżkę do pliku zamiast strumienia.

## Typowe problemy i rozwiązania
| Problem | Rozwiązanie |
|-------|----------|
| **Nieprawidłowy format JSON** | Sprawdź, czy ciąg GeoJSON jest poprawnie sformułowany; użyj walidatora JSON. |
| **Problemy z kodowaniem** | Upewnij się, że strumień używa UTF‑8 (`Encoding.UTF8.GetBytes`). |
| **Brakujące właściwości** | Sprawdź, czy nazwa właściwości jest poprawnie napisana (`"name"` w przykładzie). |
| **Wyjątek licencyjny** | Użyj licencji próbnej do testów; zastosuj stałą licencję w produkcji. |

## Najczęściej zadawane pytania
### Czy Aspose.GIS jest kompatybilny z innymi formatami GIS?
Tak, Aspose.GIS obsługuje GeoJSON, Shapefile, KML, GML i wiele innych formatów.

### Czy mogę wypróbować Aspose.GIS przed zakupem?
Tak, możesz pobrać darmową wersję próbną Aspose.GIS z [tutaj](https://releases.aspose.com/).

### Gdzie znajdę dokumentację Aspose.GIS?
Dokumentację Aspose.GIS znajdziesz [tutaj](https://reference.aspose.com/gis/net/).

### Jak mogę uzyskać wsparcie dla Aspose.GIS?
Wsparcie dla Aspose.GIS dostępne jest na forach Aspose [tutaj](https://forum.aspose.com/c/gis/33).

### Czy potrzebuję tymczasowej licencji do używania Aspose.GIS?
Tymczasową licenc Aspose.GIS możesz uzyskać [tutaj](https://purchase.aspose.com/temporary-license/).

## Zakończenie
W tym przewodniku omówiliśmy **jak odczytać geojson** z pamięciowego strumienia przy użyciu Aspose.GIS dla .NET, zaprezentowaliśmy przepływ **c# read geojson** oraz pokazaliśmy, jak **wyodrębnić właściwości geojson** z otwartej warstwy. Dzięki tym krokom możesz płynnie integrować obsługę danych geoprzestrzennych w dowolnej aplikacji .NET.

---

**Ostatnia aktualizacja:** 2025-12-28  
**Testowano z:** Aspose.GIS 24.11 dla .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}