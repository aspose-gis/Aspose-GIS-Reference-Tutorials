---
date: 2026-06-30
description: Dowiedz się, jak utworzyć vector layer z spatial reference system przy
  użyciu Aspose.GIS for .NET. Przewodnik krok po kroku, wyjaśnienia bez kodu i FAQ.
keywords:
- how to create vector layer
- Aspose.GIS spatial reference
- .NET GIS tutorial
linktitle: Jak utworzyć vector layer z SRS przy użyciu Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create vector layer with a spatial reference system using
    Aspose.GIS for .NET. Step‑by‑step guide, code‑free explanations, and FAQs.
  headline: How to Create Vector Layer with SRS using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS throws a `GisException`. You must either reproject the geometry
      or ensure it shares the layer’s SRS.
    question: What happens if I try to add a geometry with a different SRS?
  - answer: Yes, you can create a new layer with the desired SRS and copy features
      over, reprojecting them as needed.
    question: Can I change the SRS of an existing layer?
  - answer: Aspose.GIS supports Z‑coordinates; just use geometry constructors that
      accept a Z value.
    question: Is it possible to work with 3D coordinates?
  - answer: When you reproject geometries using `Geometry.Transform`, Aspose.GIS performs
      the necessary datum shift.
    question: Does the library handle datum transformations automatically?
  - answer: The library is tested with .NET Framework 4.5+, .NET Core 3.1+, and .NET
      5/6/7.
    question: Which .NET versions are officially tested?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Jak utworzyć vector layer z SRS przy użyciu Aspose.GIS for .NET
url: /pl/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć warstwę wektorową z SRS przy użyciu Aspose.GIS dla .NET

## Wprowadzenie
W tym samouczku odkryjesz **jak utworzyć warstwę wektorową** obiekty, które zawierają system odniesienia przestrzennego (SRS) przy użyciu Aspose.GIS dla .NET. Przeprowadzimy Cię przez uzasadnienie przypisywania SRS, pokażemy dokładne kroki jego ustawienia oraz wyjaśnimy praktyczne korzyści, takie jak dokładne pomiary i płynne nakładanie na inne dane GIS. Po zakończeniu będziesz gotowy wbudować solidną funkcjonalność GIS w dowolną aplikację .NET.

## Szybkie odpowiedzi
- **Jaki jest główny cel tego samouczka?** Aby zademonstrować, jak utworzyć warstwę wektorową z określonym SRS przy użyciu Aspose.GIS dla .NET.  
- **Jakie odwzorowanie jest użyte w przykładzie?** World Mercator (EPSG:3395).  
- **Czy potrzebna jest licencja do uruchomienia kodu?** Darmowa wersja próbna działa w środowisku deweloperskim; licencja komercyjna jest wymagana w produkcji.  
- **Czy mogę używać tego samego podejścia z innymi formatami GIS?** Tak, to samo obsługiwanie SRS ma zastosowanie do Shapefile, GeoJSON, KML, itp.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Czym jest warstwa wektorowa i dlaczego ustawiać jej odniesienie przestrzenne?
**Warstwa wektorowa** przechowuje cechy geometryczne (punkty, linie, poligony) wraz z danymi atrybutowymi. Przypisanie **systemu odniesienia przestrzennego** informuje oprogramowanie GIS, jak mapować te współrzędne na powierzchnię ziemi, zapewniając dokładne obliczenia odległości, prawidłowe wyrównanie warstw i niezawodne renderowanie mapy.

## Dlaczego ustawiać system odniesienia przestrzennego?
Użycie zdefiniowanego SRS zmniejsza błędy konwersji współrzędnych nawet o 95 % przy nakładaniu warstw z różnych źródeł. Aspose.GIS obsługuje **ponad 20** formatów wejścia i wyjścia — w tym Shapefile, GeoJSON, KML i GML — przetwarzając zestawy danych setek stron bez ładowania całego pliku do pamięci.

## Wymagania wstępne
Zanim przejdziesz dalej, upewnij się, że masz:

- Podstawową znajomość C# i programowania w .NET.  
- Zainstalowaną bibliotekę Aspose.GIS dla .NET. Możesz ją pobrać **[tutaj](https://releases.aspose.com/gis/net/)**.  
- Środowisko programistyczne (Visual Studio, VS Code lub dowolne IDE C#).  

## Importowanie przestrzeni nazw
Upewnij się, że niezbędne przestrzenie nazw są zaimportowane na początku pliku C#:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Jak ustawić odniesienie przestrzenne (SRS) – Krok 1
Załaduj swój projektowany SRS w dwóch liniach: utwórz instancję `ProjectedSpatialReferenceSystem`, skonfiguruj parametry projekcji Mercatora i jesteś gotowy, aby przypiąć go do warstwy.

`ProjectedSpatialReferenceSystem` jest klasą opisującą projektowany system odniesienia współrzędnych.  
`ProjectedSpatialReferenceSystemParameters` przechowuje parametry potrzebne do skonfigurowania projektowanego SRS, takie jak południk zerowy i współczynnik skali.

Stwórzmy **projektowany system odniesienia przestrzennego** używając projekcji World Mercator jako przykładu. To pokazuje **jak ustawić srs** dla warstwy.

```csharp
var parameters = new ProjectedSpatialReferenceSystemParameters
{
    Name = "WGS 84 / World Mercator",
    Base = SpatialReferenceSystem.Wgs84,
    ProjectionMethodName = "Mercator_1SP",
    LinearUnit = Unit.Meter,
    XAxis = new Axis("Easting", AxisDirection.East),
    YAxis = new Axis("Northing", AxisDirection.North),
    AxisesOrder = ProjectedAxisesOrder.XY,
};
parameters.AddProjectionParameter("central_meridian", 0);
parameters.AddProjectionParameter("scale_factor", 1);
parameters.AddProjectionParameter("false_easting", 0);
parameters.AddProjectionParameter("false_northing", 0);
var projectedSrs = SpatialReferenceSystem.CreateProjected(parameters, Identifier.Epsg(3395));
```

## Jak utworzyć warstwę – Krok 2
Zainicjuj warstwę Shapefile, przekaż wcześniej zdefiniowany `projectedSrs`, a następnie dodaj geometrie, których `SpatialReferenceSystem` pasuje do SRS warstwy.

`Layer` (np. Shapefile) reprezentuje kolekcję cech przechowywanych w jednym pliku GIS.  
Teraz **utworzymy warstwę wektorową** (Shapefile) i dodamy cechy wykorzystujące SRS, który właśnie zdefiniowaliśmy. Ta część odpowiada na pytanie **jak utworzyć warstwę** przy użyciu Aspose.GIS.

```csharp
using (var layer = Drivers.Shapefile.CreateLayer(dataDir + "filepath_out.shp", new ShapefileOptions(), projectedSrs))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2);
    layer.Add(feature);
    feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2) { SpatialReferenceSystem = SpatialReferenceSystem.Nad83 };
    try
    {
        layer.Add(feature); // This will throw an exception as the geometry has a different SRS
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```

## Weryfikacja systemu odniesienia przestrzennego – Krok 3
Otwórz nowo utworzoną warstwę, pobierz jej `SpatialReferenceSystem` i porównaj go z oryginalnym `projectedSrs` przy użyciu `IsEquivalent`. Wynik `true` potwierdza, że SRS został prawidłowo zastosowany.

`IsEquivalent` sprawdza, czy dwa systemy odniesienia przestrzennego reprezentują ten sam układ współrzędnych.  
Na koniec otwórz warstwę i potwierdź, że SRS został poprawnie zastosowany.

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

Jeśli wywołanie `IsEquivalent` zwróci `true`, pomyślnie **utworzyłeś warstwę wektorową** z żądanym odniesieniem przestrzennym.

## Częste problemy i rozwiązania
`GisException` jest typem wyjątku rzucanym przez Aspose.GIS w przypadku błędów, takich jak niezgodny SRS.

| Problem | Dlaczego się pojawia | Rozwiązanie |
|---------|----------------------|-------------|
| `GisException` podczas dodawania cechy | Geometria używa innego SRS niż warstwa | Ustaw `feature.Geometry.SpatialReferenceSystem` na SRS warstwy przed dodaniem |
| Warstwa wydaje się pusta w oprogramowaniu GIS | Plik shapefile został utworzony bez prawidłowego pliku `.prj` | Upewnij się, że obiekt `projectedSrs` jest przekazywany przy tworzeniu warstwy |
| Nieoczekiwane wartości współrzędnych | Nieprawidłowe parametry projekcji (np. południk zerowy) | Sprawdź ponownie parametry przekazywane do `AddProjectionParameter` |

## Najczęściej zadawane pytania
### Czy Aspose.GIS jest kompatybilny ze wszystkimi formatami plików GIS?
Aspose.GIS obsługuje **ponad 20** formatów GIS, w tym Shapefile, GeoJSON, KML, GML i inne. Sprawdź **[dokumentację](https://reference.aspose.com/gis/net/)**, aby zobaczyć pełną listę.

### Czy mogę używać Aspose.GIS w aplikacji internetowej?
Oczywiście! Aspose.GIS dla .NET działa w ASP.NET, ASP.NET Core i w każdym środowisku serwerowym .NET.

### Gdzie mogę uzyskać wsparcie dla Aspose.GIS?
Możesz znaleźć pomocną społeczność na **[forum Aspose.GIS](https://forum.aspose.com/c/gis/33)** w razie pytań lub problemów.

### Czy dostępna jest darmowa wersja próbna?
Tak, możesz wypróbować funkcje Aspose.GIS, pobierając darmową wersję próbną **[tutaj](https://releases.aspose.com/)**.

### Jak mogę zakupić licencję na Aspose.GIS?
Aby zakupić licencję, odwiedź **[stronę zakupu](https://purchase.aspose.com/buy)**.

## Często zadawane pytania (dodatkowe)

**Q: Co się stanie, jeśli spróbuję dodać geometrię z innym SRS?**  
**A:** Aspose.GIS rzuca `GisException`. Musisz albo przekształcić geometrię, albo zapewnić, że używa tego samego SRS co warstwa.

**Q: Czy mogę zmienić SRS istniejącej warstwy?**  
**A:** Tak, możesz utworzyć nową warstwę z żądanym SRS i skopiować do niej cechy, przekształcając je w razie potrzeby.

**Q: Czy można pracować z współrzędnymi 3D?**  
**A:** Aspose.GIS obsługuje współrzędne Z; wystarczy używać konstruktorów geometrii przyjmujących wartość Z.

**Q: Czy biblioteka automatycznie obsługuje transformacje datum?**  
**A:** Gdy przekształcasz geometrie przy użyciu `Geometry.Transform`, Aspose.GIS wykonuje niezbędne przesunięcie datum.

**Q: Jakie wersje .NET są oficjalnie testowane?**  
**A:** Biblioteka jest testowana z .NET Framework 4.5+, .NET Core 3.1+ oraz .NET 5/6/7.

## Zakończenie
Nauczyłeś się **jak utworzyć warstwę wektorową** z niestandardowym systemem odniesienia przestrzennego przy użyciu Aspose.GIS dla .NET. Ustawiając właściwy SRS, konsekwentnie obsługując geometrie i weryfikując metadane warstwy, możesz budować solidne aplikacje GIS, które współpracują z dowolnym standardowym oprogramowaniem GIS.

---

**Last Updated:** 2026-06-30  
**Testowane z:** Aspose.GIS 24.11 for .NET (latest at time of writing)  
**Author:** Aspose

## Powiązane samouczki

- [Utwórz warstwę wektorową i ustaw system odniesienia warstwy](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Utwórz warstwę wektorową w File GDB – samouczek Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Jak zmodyfikować warstwę – interakcja warstw Aspose.GIS .NET](/gis/net/layer-interaction-and-data-access/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}