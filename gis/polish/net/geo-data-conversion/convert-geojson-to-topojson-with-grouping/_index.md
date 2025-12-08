---
date: 2025-12-06
description: Dowiedz się, jak konwertować GeoJSON na TopoJSON z grupowaniem, ustawić
  atrybut nazwy obiektu oraz grupować elementy GeoJSON przy użyciu Aspose.GIS dla
  .NET.
language: pl
linktitle: How to Convert GeoJSON to TopoJSON with Grouping using Aspose.GIS
second_title: Aspose.GIS .NET API
title: Jak przekonwertować GeoJSON na TopoJSON z grupowaniem przy użyciu Aspose.GIS
url: /net/geo-data-conversion/convert-geojson-to-topojson-with-grouping/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak przekonwertować GeoJSON na TopoJSON z grupowaniem przy użyciu Aspose.GIS

## Wprowadzenie

W tym samouczku krok po kroku nauczysz się **jak konwertować pliki GeoJSON** na TopoJSON, grupując elementy na podstawie wybranego atrybutu. Użycie API Aspose.GIS .NET sprawia, że konwersja jest szybka, niezawodna i w pełni kontrolowana z poziomu Twojego kodu C#. Niezależnie od tego, czy tworzysz usługę konwersji GeoJSON w ASP.NET, czy narzędzie GIS na pulpit, ten przewodnik pokaże Ci dokładnie, co należy zrobić.

## Szybkie odpowiedzi
- **Jaka biblioteka obsługuje konwersję?** Aspose.GIS for .NET  
- **Jak długo trwa implementacja?** Zazwyczaj 5‑10 minut dla podstawowej konfiguracji  
- **Czy potrzebna jest licencja do produkcji?** Tak, wymagana jest licencja komercyjna (dostępna wersja próbna)  
- **Czy mogę grupować elementy według dowolnego atrybutu?** Tak – ustaw `ObjectNameAttribute` na pole, według którego chcesz grupować  
- **Czy .NET Core jest obsługiwany?** Zdecydowanie – API działa z .NET Core, .NET 5/6 oraz klasycznym .NET Framework  

## Czym jest GeoJSON i TopoJSON?

GeoJSON to powszechnie używany format JSON służący do kodowania obiektów geograficznych, takich jak punkty, linie i wielokąty. TopoJSON rozszerza GeoJSON, przechowując topologię (wspólne odcinki linii), co zmniejsza rozmiar pliku i poprawia wydajność renderowania skomplikowanych map. Konwersja pomiędzy nimi jest typowym krokiem, gdy potrzebujesz kompaktowych danych mapowych do wizualizacji internetowych.

## Dlaczego grupować elementy GeoJSON?

Grupowanie (`group geojson features`) pozwala organizować powiązane geometrie pod jednym nazwanym obiektem w wynikowym TopoJSON. Jest to szczególnie przydatne, gdy:
- Chcesz utworzyć osobne warstwy dla różnych jednostek administracyjnych.  
- Twoja biblioteka mapowa po stronie front‑endu oczekuje nazwanych obiektów do stylizacji lub interakcji.  
- Musisz zmniejszyć duplikację, udostępniając granice pomiędzy sąsiadującymi elementami.

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:

1. **Aspose.GIS for .NET** – pobierz i zainstaluj z oficjalnej strony [tutaj](https://releases.aspose.com/gis/net/).  
2. **Środowisko programistyczne** – Visual Studio, Visual Studio Code lub dowolne IDE obsługujące C#.  
3. **Przykładowy plik GeoJSON** – plik zawierający elementy, które chcesz przekonwertować.  

## Importowanie przestrzeni nazw

Najpierw dołącz niezbędne przestrzenie nazw w swoim projekcie:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
```

## Przewodnik krok po kroku

### Krok 1: Zdefiniuj ścieżki plików

Określ, gdzie znajduje się źródłowy plik GeoJSON oraz gdzie ma zostać zapisany TopoJSON:

```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithGrouping_out.topojson";
```

> **Wskazówka:** Użyj `Path.Combine` do budowania ścieżek wieloplatformowych, jeśli celujesz w .NET Core.

### Krok 2: Skonfiguruj opcje konwersji (ustaw atrybut nazwy obiektu)

Utwórz instancję `ConversionOptions` i poinformuj Aspose.GIS, jak grupować elementy:

```csharp
var options = new ConversionOptions
{
    DestinationDriverOptions = new TopoJsonOptions
    {
        // Specify the attribute in GeoJSON layer by which we are going to group into objects
        ObjectNameAttribute = "group",
        // Specify the default object name for features with unknown attribute values
        DefaultObjectName = "unnamed",
    }
};
```

Zastąp `"group"` rzeczywistą nazwą właściwości w Twoim GeoJSON, której chcesz użyć do **grupowania elementów GeoJSON**. `DefaultObjectName` zapewnia, że każdy element trafi do obiektu TopoJSON, nawet jeśli atrybut jest nieobecny.

### Krok 3: Wykonaj konwersję (konwertuj GeoJSON na TopoJSON)

Uruchom konwersję jednym wywołaniem API:

```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```

Po wykonaniu, `convertedSampleWithGrouping_out.topojson` będzie zawierał reprezentację TopoJSON, z elementami pogrupowanymi zgodnie z podanym atrybutem.

## Typowe problemy i rozwiązywanie

| Objaw | Prawdopodobna przyczyna | Rozwiązanie |
|---------|--------------|-----|
| **Wszystkie elementy trafiają do „unnamed”** | `ObjectNameAttribute` nie pasuje do żadnej właściwości w GeoJSON | Zweryfikuj dokładną nazwę właściwości (uwzględniając wielkość liter) i zaktualizuj opcję |
| **Plik wyjściowy jest pusty** | Nieprawidłowa ścieżka pliku lub brak uprawnień do odczytu | Użyj ścieżek bezwzględnych lub upewnij się, że aplikacja ma dostęp do systemu plików |
| **Konwersja zgłasza `NotSupportedException`** | Próba konwersji GeoJSON z nieobsługiwanymi typami geometrii (np. GeometryCollection) | Uprość dane źródłowe lub zaktualizuj do najnowszej wersji Aspose.GIS |

## Najczęściej zadawane pytania

**P: Czy mogę grupować elementy na podstawie wielu atrybutów?**  
O: Tak, możesz połączyć kilka pól w jeden wirtualny atrybut lub wykonać wiele przebiegów konwersji z różnymi wartościami `ObjectNameAttribute`.

**P: Czy Aspose.GIS jest kompatybilny z ASP.NET Core?**  
O: Zdecydowanie – biblioteka działa z ASP.NET Core, .NET 5, .NET 6 oraz klasycznym .NET Framework.

**P: Czy mogę konwertować inne formaty geograficzne oprócz GeoJSON?**  
O: Tak, Aspose.GIS obsługuje Shapefile, KML, GML, CSV i wiele innych formatów zarówno przy imporcie, jak i eksporcie.

**P: Czy Aspose.GIS oferuje wersję próbną?**  
O: Tak, możesz uzyskać darmową wersję próbną Aspose.GIS [tutaj](https://releases.aspose.com/).

**P: Gdzie mogę uzyskać wsparcie dla Aspose.GIS?**  
O: Wsparcie możesz uzyskać na forum społeczności Aspose.GIS [tutaj](https://forum.aspose.com/c/gis/33).

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**Ostatnia aktualizacja:** 2025-12-06  
**Testowano z:** Aspose.GIS for .NET (latest release)  
**Autor:** Aspose  

---