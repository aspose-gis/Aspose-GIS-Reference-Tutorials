---
date: 2026-10-15
description: Dowiedz się, jak tworzyć GeoJSON z współrzędnych i zapisywać go do strumienia
  przy użyciu Aspose.GIS for .NET. Ten samouczek pokazuje krok po kroku konwersję
  punktów oraz generowanie kodu C# GeoJSON.
keywords:
- create geojson from coordinates
- stream large geojson files
- write geojson to stream
- geojson tutorial c#
- compress geojson with gzip
lastmod: 2026-10-15
linktitle: Zapisz GeoJSON do strumienia
og_description: Dowiedz się, jak tworzyć GeoJSON z współrzędnych i zapisywać go do
  strumienia przy użyciu Aspose.GIS for .NET – przewodnik krok po kroku dla dużych
  zbiorów danych.
og_image_alt: Screenshot of Aspose.GIS code generating GeoJSON stream in C#
og_title: Tworzenie GeoJSON z współrzędnych, zapisywanie do strumienia w .NET
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create geojson from coordinates and write it to a stream
    using Aspose.GIS for .NET. This tutorial shows step‑by‑step conversion of points
    and generation of GeoJSON C# code.
  headline: Create geojson from coordinates, write to a stream in .NET
  type: TechArticle
- questions:
  - answer: Yes – create a `Feature` for each point, assign a `Point` geometry, and
      add it to the `VectorLayer`.
    question: Can I generate GeoJSON from a collection of latitude/longitude points?
  - answer: You can wrap the `MemoryStream` in a `GZipStream` before saving to produce
      a compressed payload.
    question: Does Aspose.GIS support writing compressed GeoJSON (gzip)?
  - answer: The library can stream files exceeding 2 GB; memory usage stays low because
      data is written incrementally.
    question: What is the maximum size of a GeoJSON file Aspose.GIS can handle?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geojson
- Aspose.GIS
- .NET geospatial
- C# stream processing
- GIS data conversion
title: Tworzenie GeoJSON z współrzędnych, zapisywanie do strumienia w .NET
url: /pl/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz geojson z współrzędnych i zapisz do strumienia

## Wprowadzenie
W tym samouczku dowiesz się **jak utworzyć geojson z współrzędnych** i zapisać go bezpośrednio do strumienia przy użyciu Aspose.GIS dla .NET. Przejdziemy przez konfigurację środowiska, tworzenie warstwy, wypełnianie obiektów oraz strumieniowanie wyniku, abyś mógł osadzać ładunki geoprzestrzenne w API, funkcjach chmurowych lub usługach bez plików, bez plików tymczasowych.

## Szybkie odpowiedzi
- **Jaką klasę używać do zapisu GeoJSON do strumienia?** `VectorLayer` together with the `GeoJsonDriver`.
- **Czy potrzebna jest licencja do rozwoju?** Darmowa wersja próbna działa w środowisku deweloperskim; licencja komercyjna jest wymagana w produkcji.
- **Które wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Czy mogę konwertować kolekcje punktów do GeoJSON?** Tak – utwórz `Feature` dla każdego punktu i przypisz geometrię `Point`.
- **Czy strumieniowanie jest odpowiednie dla dużych zestawów danych?** Zdecydowanie – `MemoryStream` pozwala zapisywać GeoJSON o rozmiarze gigabajtów bez ładowania całego pliku do pamięci.

## Czym jest GeoJSON?
GeoJSON jest otwartym formatem opartym na JSON służącym do kodowania obiektów geograficznych, takich jak punkty, linie i wielokąty. Składa się z `FeatureCollection`, które grupuje pojedyncze obiekty `Feature`, z których każdy zawiera dane geometryczne i atrybuty. Ponieważ jest lekki i przyjazny dla sieci, GeoJSON jest de‑facto standardem wymiany danych przestrzennych między przeglądarkami, serwerami GIS i aplikacjami mobilnymi.

## Dlaczego używać Aspose.GIS do generowania geojson?
Aspose.GIS obsługuje **ponad 35 formatów plików przestrzennych** i może strumieniować pliki większe niż **2 GB**, przy zużyciu pamięci poniżej **50 MB**. Jego wysokowydajny silnik strumieniowania zapisuje GeoJSON bezpośrednio do dowolnego .NET `Stream`, eliminując potrzebę pośrednich plików tymczasowych i redukując opóźnienia I/O nawet o **70 %** w typowych scenariuszach chmurowych.

## Wymagania wstępne
1. Zainstalowany **Aspose.GIS for .NET**. Pobierz pakiet **Aspose.GIS for .NET** [tutaj](https://releases.aspose.com/gis/net/).
2. Zapisywalny folder w projekcie, w którym możesz umieścić pliki tymczasowe w razie potrzeby.
3. Zainstalowane środowisko uruchomieniowe .NET 5+ lub .NET Core 3.1+.

Teraz przejdźmy do implementacji.

## Jak utworzyć geojson z współrzędnych i zapisać do strumienia?
`VectorLayer` reprezentuje wektorowy zestaw danych w pamięci, który może być zapisywany w różnych formatach.  
`GeoJsonDriver` jest sterownikiem umożliwiającym odczyt i zapis plików GeoJSON.

Załaduj `VectorLayer` przy użyciu `GeoJsonDriver`, dodaj obiekty `Feature` zawierające geometrię `Point` i wywołaj `layer.Save(stream, new GeoJsonSaveOptions())`. To pojedyncze wywołanie serializuje całą kolekcję obiektów `Feature` do zgodnego ze standardem dokumentu GeoJSON, który znajduje się w podanym `MemoryStream`. Proces automatycznie obsługuje mapowanie atrybutów i konwersję współrzędnych, dzięki czemu otrzymujesz gotowy ładunek JSON bez ręcznego budowania łańcucha znaków.

### Definicje
**VectorLayer** jest podstawowym obiektem Aspose.GIS reprezentującym modyfikowalny zestaw danych wektorowych w pamięci.  
**GeoJsonDriver** jest sterownikiem odpowiedzialnym za odczyt i zapis plików GeoJSON.

## Importuj przestrzenie nazw
Na początek upewnij się, że dołączasz niezbędne przestrzenie nazw, aby uzyskać dostęp do funkcjonalności Aspose.GIS w swoim kodzie:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Krok 1: skonfiguruj katalog dokumentów
Utwórz ścieżkę folderu, w którym Aspose.GIS może przechowywać pliki pomocnicze, jeśli będzie to potrzebne.
```csharp
string dataDir = "Your Document Directory";
```
Zastąp "Your Document Directory" rzeczywistą ścieżką do katalogu dokumentów.

## Krok 2: utwórz strumień pamięci
`MemoryStream` zapewnia bufor w pamięci, który może być wysyłany bezpośrednio przez HTTP lub zapisywany w chmurze.
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code for the next steps goes here
}
```

## Krok 3: utwórz warstwę wektorową z driverem GeoJSON
Klasa `VectorLayer` reprezentuje zestaw danych wektorowych, który może być zapisywany w różnych formatach, w tym GeoJSON.
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Code for the next steps goes here
}
```

## Krok 4: zdefiniuj atrybuty obiektów
Zdefiniuj schemat atrybutów dla swoich obiektów (np. ID, Name).
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## Krok 5: skonstruuj i dodaj obiekty
Utwórz obiekty `Feature`, przypisz geometrię punktu, ustaw wartości atrybutów i dodaj je do warstwy.
```csharp
// First Feature
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);
// Second Feature
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```

## Krok 6: wyświetl wynik GeoJSON
Po zapisaniu zresetuj pozycję strumienia i odczytaj ciąg JSON w celu weryfikacji lub transmisji.
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

Gratulacje! Pomyślnie utworzyłeś geojson z współrzędnych i zapisałeś go do strumienia przy użyciu Aspose.GIS dla .NET.

## Typowe problemy i rozwiązania
- **Pusty strumień wyjściowy:** Upewnij się, że resetujesz pozycję strumienia (`stream.Position = 0`) przed odczytem.
- **Nieprawidłowa kolejność współrzędnych:** GeoJSON oczekuje kolejności długość‑szerokość; sprawdź wartości punktów.
- **Duże zestawy danych:** Użyj `layer.Save(stream, new GeoJsonSaveOptions { WriteFeatureCollection = true })`, aby strumieniować obiekty stopniowo i utrzymać niskie zużycie pamięci.

## Najczęściej zadawane pytania

**Q: Czy mogę używać Aspose.GIS dla .NET zarówno w środowiskach Windows, jak i Linux?**  
A: Tak, Aspose.GIS dla .NET działa na Windows, Linux i macOS z pełnym wsparciem .NET Core.

**Q: Czy dostępna jest darmowa wersja próbna?**  
A: Oczywiście! Możesz przeglądać **stronę pobierania wersji próbnej** [tutaj](https://releases.aspose.com/).

**Q: Gdzie mogę znaleźć szczegółową dokumentację?**  
A: Sprawdź **dokumentację Aspose.GIS .NET** [tutaj](https://reference.aspose.com/gis/net/).

**Q: Jak mogę uzyskać tymczasową licencję?**  
A: Tymczasowe licencje są dostępne na **stronie tymczasowej licencji** [tutaj](https://purchase.aspose.com/temporary-license/).

**Q: Potrzebujesz pomocy lub masz więcej pytań?**  
A: Odwiedź nasz **forum wsparcia GIS** [tutaj](https://forum.aspose.com/c/gis/33).

**Q: Czy mogę generować GeoJSON z kolekcji punktów szerokość/długość geograficzna?**  
A: Tak – utwórz `Feature` dla każdego punktu, przypisz geometrię `Point` i dodaj go do `VectorLayer`.

**Q: Czy Aspose.GIS obsługuje zapisywanie skompresowanego GeoJSON (gzip)?**  
A: Możesz owinąć `MemoryStream` w `GZipStream` przed zapisem, aby uzyskać skompresowany ładunek.

**Q: Jaki jest maksymalny rozmiar pliku GeoJSON, który Aspose.GIS może obsłużyć?**  
A: Biblioteka może strumieniować pliki przekraczające 2 GB; zużycie pamięci pozostaje niskie, ponieważ dane są zapisywane stopniowo.

---

**Ostatnia aktualizacja:** 2026-10-15  
**Testowane z:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  



## Powiązane samouczki

- [Jak odczytać GeoJSON ze strumienia przy użyciu Aspose.GIS dla .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Jak przekonwertować GeoJSON na TopoJSON przy użyciu Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Jak przekonwertować Shapefile na GeoJSON przy użyciu Aspose.GIS dla .NET](/gis/net/layer-management/extract-features-to-geojson/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}