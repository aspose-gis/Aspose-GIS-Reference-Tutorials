---
date: 2026-05-21
description: Dowiedz się, jak zapisać GeoJSON do strumienia przy użyciu Aspose.GIS
  dla .NET. Ten samouczek GeoJSON .NET pokazuje krok po kroku konwersję punktów i
  generowanie kodu GeoJSON w C#.
keywords:
- how to write geojson
- convert points geojson
- geojson tutorial .net
- generate geojson c#
linktitle: Zapisz GeoJSON do strumienia
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to write GeoJSON to stream using Aspose.GIS for .NET. This
    geojson tutorial .net shows step‑by‑step conversion of points and generation of
    GeoJSON C# code.
  headline: How to Write GeoJSON to Stream with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes – create a `Feature` for each point, assign a `Point` geometry, and
      add it to the `VectorLayer`.
    question: Can I generate GeoJSON from a collection of latitude/longitude points?
  - answer: You can wrap the `MemoryStream` in a `GZipStream` before saving to produce
      a compressed payload.
    question: Does Aspose.GIS support writing compressed GeoJSON (gzip)?
  - answer: The library can stream files exceeding 2 GB; memory usage stays low because
      data is written incrementally.
    question: What is the maximum size of a GeoJSON file Aspose.GIS can handle?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Jak zapisać GeoJSON do strumienia przy użyciu Aspose.GIS dla .NET
url: /pl/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zapisz GeoJSON do strumienia

## Wprowadzenie
W tym samouczku dowiesz się **jak zapisać GeoJSON do strumienia** w aplikacji .NET przy użyciu Aspose.GIS. Przejdziemy przez każdy krok, od skonfigurowania środowiska po wygenerowanie prawidłowego dokumentu GeoJSON, abyś mógł płynnie integrować dane geoprzestrzenne w swoich usługach.

## Szybkie odpowiedzi
- **Jaka jest podstawowa klasa do wyjścia GeoJSON?** `VectorLayer` with the `GeoJsonDriver`.
- **Czy potrzebuję licencji do rozwoju?** Darmowa wersja próbna działa w środowisku deweloperskim; licencja komercyjna jest wymagana w produkcji.
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Czy mogę konwertować kolekcje punktów do GeoJSON?** Yes – use the `Feature` class and define point geometry.
- **Czy strumieniowanie jest obsługiwane dla dużych zestawów danych?** Absolutely; `MemoryStream` lets you write without intermediate files.

## Czym jest GeoJSON?
GeoJSON jest otwartym standardowym formatem do kodowania różnych struktur danych geograficznych przy użyciu JSON. Definiuje obiekty takie jak FeatureCollection, Feature oraz typy geometrii (Point, LineString, Polygon). Ta lekka, przyjazna dla sieci reprezentacja umożliwia łatwą wymianę i wizualizację danych przestrzennych na wielu platformach i w różnych językach programowania.

## Dlaczego używać Aspose.GIS do generowania GeoJSON?
Aspose.GIS obsługuje ponad 30 formatów plików przestrzennych i może przetwarzać pliki większe niż 2 GB bez ładowania całego dokumentu do pamięci. Jego wysokowydajny silnik strumieniowy zapisuje GeoJSON bezpośrednio do strumieni, zmniejszając obciążenie I/O. Dzięki temu jest idealny dla przedsiębiorstwowych obciążeń geoprzestrzennych, usług chmurowych i aplikacji w czasie rzeczywistym.

## Wymagania wstępne
Zanim przejdziemy do samouczka, upewnij się, że masz następujące wymagania wstępne:
1. Aspose.GIS for .NET Library: Upewnij się, że masz zainstalowaną bibliotekę Aspose.GIS for .NET. Możesz ją pobrać [tutaj](https://releases.aspose.com/gis/net/).
2. Document Directory: Utwórz katalog dokumentów w swoim projekcie i zanotuj jego ścieżkę.

Teraz rozpocznijmy samouczek!

## Jak zapisać GeoJSON do strumienia?
VectorLayer reprezentuje zestaw danych wektorowych, który może być zapisywany w różnych formatach, w tym GeoJSON.  
GeoJsonDriver jest sterownikiem używanym przez Aspose.GIS do odczytu i zapisu plików GeoJSON.  
`layer.Save` zapisuje zawartość warstwy do podanego strumienia przy użyciu określonych opcji zapisu.

Załaduj `VectorLayer` przy użyciu `GeoJsonDriver`, dodaj elementy zawierające geometrię punktu, a następnie wywołaj `layer.Save(stream, new GeoJsonSaveOptions())`. To zapisuje kompletny, zgodny ze standardami dokument GeoJSON bezpośrednio do podanego `MemoryStream` w kilku linijkach kodu. Metoda serializuje kolekcję elementów, automatycznie obsługując dane atrybutowe i konwersję geometrii, dzięki czemu otrzymujesz gotowy do użycia ładunek JSON bez ręcznej manipulacji łańcuchami.

## Importuj przestrzenie nazw
Na początek upewnij się, że dołączasz niezbędne przestrzenie nazw, aby uzyskać dostęp do funkcji Aspose.GIS w swoim kodzie:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Krok 1: Skonfiguruj katalog dokumentów
```csharp
string dataDir = "Your Document Directory";
```
Zastąp „Your Document Directory” rzeczywistą ścieżką do katalogu dokumentów.

## Krok 2: Utwórz strumień pamięci
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code for the next steps goes here
}
```

## Krok 3: Utwórz warstwę wektorową z sterownikiem GeoJSON
Klasa `VectorLayer` reprezentuje zestaw danych wektorowych, który może być zapisywany w różnych formatach, w tym GeoJSON.  
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Code for the next steps goes here
}
```

## Krok 4: Zdefiniuj atrybuty elementów
Zdefiniuj schemat atrybutów dla swoich elementów (np. ID, Name).  
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## Krok 5: Utwórz i dodaj elementy
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

## Krok 6: Wyświetl wynik GeoJSON
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

Gratulacje! Pomyślnie zapisałeś GeoJSON do strumienia przy użyciu Aspose.GIS dla .NET.

## Typowe problemy i rozwiązania
- **Pusty strumień wyjściowy:** Upewnij się, że przed odczytem zresetujesz pozycję strumienia (`stream.Position = 0`).
- **Nieprawidłowa kolejność współrzędnych:** GeoJSON oczekuje kolejności długość‑szerokość; sprawdź wartości swoich punktów.
- **Duże zestawy danych:** Użyj `layer.Save(stream, new GeoJsonSaveOptions { WriteFeatureCollection = true })`, aby strumieniowo zapisywać elementy stopniowo.

## Najczęściej zadawane pytania
### Czy mogę używać Aspose.GIS dla .NET zarówno w środowiskach Windows, jak i Linux?
Tak, Aspose.GIS for .NET jest kompatybilny zarówno z systemami Windows, jak i Linux.

### Czy dostępna jest darmowa wersja próbna?
Oczywiście! Możesz wypróbować darmową wersję próbną [tutaj](https://releases.aspose.com/).

### Gdzie mogę znaleźć szczegółową dokumentację?
Sprawdź dokumentację [tutaj](https://reference.aspose.com/gis/net/).

### Jak mogę uzyskać tymczasową licencję?
Tymczasowe licencje są dostępne [tutaj](https://purchase.aspose.com/temporary-license/).

### Potrzebujesz pomocy lub masz więcej pytań?
Odwiedź nasz forum wsparcia [tutaj](https://forum.aspose.com/c/gis/33).

**Q:** Czy mogę wygenerować GeoJSON z kolekcji punktów szerokość/długość geograficzna?  
**A:** Tak – utwórz `Feature` dla każdego punktu, przypisz geometrię `Point` i dodaj go do `VectorLayer`.

**Q:** Czy Aspose.GIS obsługuje zapisywanie skompresowanego GeoJSON (gzip)?  
**A:** Możesz owinąć `MemoryStream` w `GZipStream` przed zapisem, aby uzyskać skompresowany ładunek.

**Q:** Jaki jest maksymalny rozmiar pliku GeoJSON, który Aspose.GIS może obsłużyć?  
**A:** Biblioteka może strumieniowo obsługiwać pliki przekraczające 2 GB; zużycie pamięci pozostaje niskie, ponieważ dane są zapisywane stopniowo.

---

**Ostatnia aktualizacja:** 2026-05-21  
**Testowano z:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Jak odczytać GeoJSON ze strumienia przy użyciu Aspose.GIS dla .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Jak przekonwertować GeoJSON na TopoJSON przy użyciu Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Jak przekonwertować Shapefile na GeoJSON przy użyciu Aspose.GIS dla .NET](/gis/net/layer-management/extract-features-to-geojson/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}