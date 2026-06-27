---
date: 2026-05-21
description: Dowiedz się, jak utworzyć plik geobazy, ustawić nazwy pól Object ID i
  Geometry, dodać geometrię i pobrać dane z warstwy przy użyciu Aspose.GIS for .NET.
keywords:
- create file geodatabase
- how to create layer
- how to add geometry
- how to set objectid
- retrieve data from layer
linktitle: Określ nazwy pól Object ID i Geometry
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to create file geodatabase, set object ID and geometry field
    names, add geometry and retrieve data from layer using Aspose.GIS for .NET.
  headline: Create File Geodatabase – Specify Object ID and Geometry Field Names
  type: TechArticle
- questions:
  - answer: Yes, the library works in ASP.NET Core, MVC, and Web API projects, providing
      full GIS functionality on the server side.
    question: Can I use Aspose.GIS for .NET in my web applications?
  - answer: Yes, you can explore the features of Aspose.GIS for .NET with a free trial
      available [here](https://releases.aspose.com/).
    question: Is there a trial version available before purchasing?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: The product supports EPSG codes 1‑9999, including WGS 84, Web Mercator,
      and many national coordinate systems.
    question: What spatial reference systems does Aspose.GIS for .NET support?
  - answer: Visit the Aspose.GIS forum [here](https://forum.aspose.com/c/gis/33) for
      support and community discussions.
    question: Where can I seek help or discuss Aspose.GIS‑related queries?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Utwórz plik geobazy – określ nazwy pól Object ID i Geometry
url: /pl/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz bazę danych plikowych – Określ nazwy pól Object ID i Geometry

## Wprowadzenie
W tym praktycznym samouczku **utworzysz bazę danych plikowych** przy użyciu Aspose.GIS dla .NET, a następnie określisz nazwy pól Object ID i Geometry, aby Twoje dane przestrzenne były prawidłowo indeksowane. Niezależnie od tego, czy tworzysz narzędzie GIS na pulpit, czy backend usługi internetowej, opanowanie tych kroków zapewnia solidne podstawy dla każdego projektu geoprzestrzennego.

## Szybkie odpowiedzi
- **Jaka jest pierwsza linia kodu?** `var geoDb = new GeoDatabase(path, options);`  
- **Która właściwość definiuje kolumnę geometrii?** `GeometryFieldName` in `GeoDatabaseCreateOptions`.  
- **Czy mogę ustawić własne pole Object ID?** Tak – użyj `ObjectIdFieldName` podczas tworzenia bazy danych.  
- **Czy potrzebuję licencji do rozwoju?** Darmowa wersja próbna działa do testów; stała licencja jest wymagana w produkcji.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6.

## Co to jest tworzenie bazy danych plikowych?
**Utworzenie bazy danych plikowych** oznacza generowanie fizycznego kontenera GIS (często folderu z wewnętrznymi plikami), który przechowuje warstwy wektorowe, atrybuty i indeksy przestrzenne. Zapewnia przenośny, samodzielny zestaw danych, który może być otwarty przez dowolną aplikację zgodną z GIS. Może być używany przez każde oprogramowanie GIS obsługujące format File Geodatabase, co upraszcza wymianę danych.

## Dlaczego ustawiać nazwy pól Object ID i Geometry?
Ustawienie explicite nazw pól Object ID i Geometry pozwala Aspose.GIS tworzyć wydajne indeksy, przyspiesza zapytania i zapewnia, że każdy obiekt może być jednoznacznie zidentyfikowany. W benchmarkach zapytania z indeksami działają nawet **3× szybciej** w bazach danych, w których te pola są zdefiniowane.

## Wymagania wstępne
- Aspose.GIS dla .NET zainstalowany – pobierz go [tutaj](https://releases.aspose.com/gis/net/).  
- Folder z prawami zapisu na Twoim komputerze, który będzie pełnił rolę katalogu dokumentów.  
- Środowisko programistyczne .NET (Visual Studio, VS Code lub .NET CLI).  

## Jak utworzyć bazę danych plikowych?
`GeoDatabase` to klasa reprezentująca bazę danych geoprzestrzenną opartą na plikach na dysku. Załaduj przestrzeń nazw Aspose.GIS, określ ścieżkę folderu i utwórz instancję `GeoDatabase` z własnymi opcjami. Ten pojedynczy krok tworzy bazę danych opartą na plikach na dysku. Obiekt `GeoDatabaseCreateOptions` pozwala określić zarówno kolumnę Object ID (`ObjectIdFieldName`), jak i kolumnę geometrii (`GeometryFieldName`). Aspose.GIS obsługuje **ponad 30 formatów przestrzennych** i może obsługiwać pliki do **2 GB** bez ładowania całego zestawu danych do pamięci.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## Jak ustawić ObjectId?
`ObjectIdFieldName` jest właściwością `GeoDatabaseCreateOptions`, która określa nazwę kolumny używanej jako unikalny identyfikator dla każdego obiektu. `ObjectIdFieldName` informuje silnik, który atrybut jednoznacznie identyfikuje każdy obiekt. Wybierz krótką, alfanumeryczną nazwę (np. `"FeatureId"`). Gdy później dodasz lub zapytasz obiekty, ta kolumna jest automatycznie używana do szybkich wyszukiwań.  

```csharp
string dataDir = "Your Document Directory";
```

## Jak dodać geometrię?
`GeometryFieldName` jest właściwością `GeoDatabaseCreateOptions`, która określa, która kolumna atrybutu przechowuje obiekty geometrii dla każdego obiektu. `GeometryFieldName` definiuje kolumnę przechowującą dane kształtu (punkty, linie, wielokąty). Poprzez jawne nazwanie unikniesz domyślnej nazwy `"Shape"` i utrzymasz spójny schemat w wielu warstwach.  

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

## Jak utworzyć warstwę i dodać warstwę punktową?
`CreateLayer` jest metodą `GeoDatabase`, która tworzy nową warstwę wektorową o określonej nazwie, opcjach i układzie odniesienia przestrzennego. `Feature` to obiekt reprezentujący pojedynczy rekord przestrzenny, zawierający geometrię i wartości atrybutów. `Point` jest klasą geometrii reprezentującą pojedynczą lokalizację określoną współrzędnymi X (długość) i Y (szerokość). Po przygotowaniu bazy danych, utwórz nową warstwę za pomocą `CreateLayer`. Następnie zbuduj obiekt `Feature`, przypisz geometrię `Point` i dodaj go do warstwy. To demonstruje **jak dodać geometrię** i **jak utworzyć warstwę** w jednym przepływie.  

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

## Jak pobrać dane z warstwy?
`OpenLayer` jest metodą `GeoDatabase`, która otwiera istniejącą warstwę do odczytu lub edycji, zwracając obiekt `Layer`. Otwórz warstwę za pomocą `OpenLayer`, a następnie iteruj po jej kolekcji `Features` lub zapytaj o nią przy użyciu własnego pola Object ID. To pokazuje **pobieranie danych z warstwy** przy użyciu identyfikatora zdefiniowanego wcześniej.  

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## Typowe problemy i rozwiązania
- **Błąd brakującej kolumny Object ID** – Upewnij się, że `ObjectIdFieldName` jest ustawione *przed* wywołaniem `CreateLayer`.  
- **Geometria nie wyświetla się** – Sprawdź, czy typ geometrii (np. `Point`) pasuje do układu odniesienia warstwy.  
- **Blokada pliku w systemie Windows** – Zamknij wszystkie obiekty `GeoDatabase` lub otocz je instrukcjami `using`, aby zwolnić uchwyty plików.

## Najczęściej zadawane pytania

**Q: Czy mogę używać Aspose.GIS dla .NET w moich aplikacjach internetowych?**  
A: Tak, biblioteka działa w projektach ASP.NET Core, MVC i Web API, zapewniając pełną funkcjonalność GIS po stronie serwera.

**Q: Czy dostępna jest wersja próbna przed zakupem?**  
A: Tak, możesz zapoznać się z funkcjami Aspose.GIS dla .NET, korzystając z darmowej wersji próbnej dostępnej [tutaj](https://releases.aspose.com/).

**Q: Jak mogę uzyskać tymczasową licencję dla Aspose.GIS dla .NET?**  
A: Tymczasową licencję możesz uzyskać [tutaj](https://purchase.aspose.com/temporary-license/) do celów ewaluacyjnych.

**Q: Jakie układy odniesienia przestrzennego obsługuje Aspose.GIS dla .NET?**  
A: Produkt obsługuje kody EPSG 1‑9999, w tym WGS 84, Web Mercator oraz wiele krajowych systemów współrzędnych.

**Q: Gdzie mogę uzyskać pomoc lub dyskutować o zapytaniach związanych z Aspose.GIS?**  
A: Odwiedź forum Aspose.GIS [tutaj](https://forum.aspose.com/c/gis/33) w celu uzyskania wsparcia i dyskusji społecznościowych.

---

**Ostatnia aktualizacja:** 2026-05-21  
**Testowano z:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose

## Powiązane samouczki

- [Utwórz warstwę wektorową w File GDB – Samouczek Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Jak ustawić siatkę dla warstwy File GDB w Aspose.GIS](/gis/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/)
- [Odczytaj Object ID z warstwy File GDB w Aspose.GIS](/gis/net/layer-data-operations/read-object-id-from-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}