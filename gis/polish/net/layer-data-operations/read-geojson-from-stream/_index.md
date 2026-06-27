---
date: 2026-04-24
description: Dowiedz się, **jak odczytać geojson** ze strumienia przy użyciu Aspose.GIS
  dla .NET. Ten przewodnik krok po kroku pokazuje, jak **załadować strumień geojson**,
  przetworzyć go i wyodrębnić właściwości w C#.
keywords:
- how to read geojson
- load geojson stream
- Aspose GIS GeoJSON
linktitle: Odczytaj GeoJSON ze strumienia
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
Jeśli zastanawiasz się **jak odczytać geojson** w aplikacji .NET, trafiłeś we właściwe miejsce. W tym samouczku przeprowadzimy Cię przez kompletny **przykład C# GeoJSON**, który pokazuje, jak przekonwertować ciąg GeoJSON, **załadować strumień geojson** do pamięciowego strumienia, otworzyć warstwę GeoJSON i wyodrębnić właściwości GeoJSON przy użyciu Aspose.GIS. Po zakończeniu będziesz mieć wielokrotnego użytku wzorzec, który możesz wstawić do dowolnego projektu potrzebującego pracy z danymi geoprzestrzennymi.

## Szybkie odpowiedzi
- **Jakiej biblioteki powinienem używać?** Aspose.GIS dla .NET – obsługuje wiele formatów GIS od razu.  
- **Czy mogę odczytać GeoJSON bezpośrednio ze strumienia?** Tak – użyj `VectorLayer.Open` z `AbstractPath.FromStream`.  
- **Czy potrzebuję licencji do rozwoju?** Darmowa wersja próbna działa do testów; pełna licencja jest wymagana w produkcji.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Czy wyodrębnianie właściwości jest proste?** Zdecydowanie – wywołaj `GetValue<T>(columnName)` na obiekcie feature.

## Co to jest „jak odczytać geojson”?
Odczytywanie GeoJSON oznacza parsowanie formatu opartego na JSON, który opisuje cechy geograficzne (punkty, linie, wielokąty) i przekształcanie tych cech w obiekty, które możesz zapytać, edytować lub renderować w swojej aplikacji.

## Dlaczego używać Aspose.GIS do **otwierania warstwy geojson**?
Aspose.GIS abstrahuje szczegóły niskopoziomowego parsowania i zapewnia spójne API dla wielu formatów GIS. Pozwala **otworzyć warstwę geojson** bezpośrednio ze strumienia, efektywnie obsługiwać duże pliki i uzyskać dostęp do atrybutów cech bez pisania własnych parserów JSON.

## Kiedy **załadować strumień geojson**?
- Importowanie danych z usługi internetowej, która zwraca GeoJSON w treści odpowiedzi.  
- Przetwarzanie plików GeoJSON przesłanych przez użytkownika bez zapisywania ich najpierw na dysku.  
- Praca z danymi w pamięci generowanymi w locie (np. z bazy danych lub innego API).  

## Wymagania wstępne
Zanim zanurkujemy, upewnij się, że masz:

1. **Podstawowa znajomość C#** – powinieneś być zaznajomiony ze składnią .NET i środowiskiem Visual Studio IDE.  
2. **Aspose.GIS zainstalowany** – pobierz bibliotekę z [here](https://releases.aspose.com/gis/net/).  
3. **Środowisko programistyczne** – Visual Studio, Visual Studio Code lub JetBrains Rider będą odpowiednie.  

## Importowanie przestrzeni nazw
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## Krok 1: **Konwersja ciągu GeoJSON** – **przykład C# GeoJSON**
Najpierw tworzymy ciąg JSON, który reprezentuje prostą `FeatureCollection`. To jest część **konwersji ciągu geojson** w tym przepływie pracy.

```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```

## Krok 2: **Załaduj strumień GeoJSON** i **wyodrębnij właściwości geojson**
Teraz wprowadzamy ciąg do `MemoryStream`, otwieramy go jako warstwę GIS i demonstrujemy, jak odczytać wartości atrybutów (krok **wyodrębniania właściwości geojson**).

```csharp
using (var memoryStream = new MemoryStream(Encoding.UTF8.GetBytes(geoJson)))
using (var layer = VectorLayer.Open(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    Console.WriteLine(layer.Count); // Output: 2
    Console.WriteLine(layer[1].GetValue<string>("name")); // Output: Mary
}
```

> **Wskazówka:** `VectorLayer.Open` automatycznie wykrywa format GeoJSON, gdy przekazujesz `Drivers.GeoJson`. Możesz także otwierać pliki bezpośrednio, podając ścieżkę do pliku zamiast strumienia.

## Typowe problemy i rozwiązania
| Problem | Rozwiązanie |
|-------|----------|
| **Nieprawidłowy format JSON** | Sprawdź, czy ciąg GeoJSON jest poprawnie sformatowany; użyj walidatora JSON. |
| **Problemy z kodowaniem** | Upewnij się, że strumień używa UTF‑8 (`Encoding.UTF8.GetBytes`). |
| **Brakujące właściwości** | Sprawdź, czy nazwa właściwości jest poprawnie napisana (`\"name\"` w przykładzie). |
| **Wyjątek licencyjny** | Użyj licencji próbnej do testów; zastosuj stałą licencję w produkcji. |

## Często zadawane pytania
### Czy Aspose.GIS jest kompatybilny z innymi formatami GIS?
Tak, Aspose.GIS obsługuje GeoJSON, Shapefile, KML, GML i wiele innych formatów.

### Czy mogę wypróbować Aspose.GIS przed zakupem?
Tak, możesz pobrać darmową wersję próbną Aspose.GIS z [here](https://releases.aspose.com/).

### Gdzie mogę znaleźć dokumentację Aspose.GIS?
Dokumentację Aspose.GIS znajdziesz [here](https://reference.aspose.com/gis/net/).

### Jak mogę uzyskać wsparcie dla Aspose.GIS?
Wsparcie dla Aspose.GIS możesz uzyskać na forum Aspose [here](https://forum.aspose.com/c/gis/33).

### Czy potrzebuję tymczasowej licencji do używania Aspose.GIS?
Tymczasową licencję do Aspose.GIS możesz uzyskać z [here](https://purchase.aspose.com/temporary-license/).

## Podsumowanie
W tym przewodniku omówiliśmy **jak odczytać geojson** z pamięciowego strumienia przy użyciu Aspose.GIS dla .NET, przedstawiliśmy przepływ **C# odczyt geojson** oraz pokazaliśmy, jak **wyodrębnić właściwości geojson** z otwartej warstwy. Dzięki tym krokom możesz płynnie zintegrować obsługę danych geoprzestrzennych w dowolnej aplikacji .NET.

---

**Ostatnia aktualizacja:** 2026-04-24  
**Testowano z:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}