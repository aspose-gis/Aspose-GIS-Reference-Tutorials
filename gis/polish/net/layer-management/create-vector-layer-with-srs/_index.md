---
date: 2026-01-15
description: Poznaj Aspose.GIS dla .NET, aby tworzyć warstwę wektorową z systemem
  odniesienia przestrzennego. Dowiedz się, jak ustawić SRS, tworzyć warstwę i zarządzać
  danymi GIS. Pobierz teraz!
linktitle: Create Vector Layer with SRS
second_title: Aspose.GIS .NET API
title: Utwórz warstwę wektorową z SRS
url: /pl/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz warstwę wektorową z SRS

## Wstęp
Aspose.GIS for .NET to potężna biblioteka, która umożliwia programistom **tworzenie warstwy wektorowej** oraz płynną pracę z danymi systemu informacji geograficznej (GIS) w aplikacjach .NET. W tym samouczku przeprowadzimy Cię krok po kroku przez proces tworzenia warstwy wektorowej z systemem odniesienia przestrzennego (SRS), wyjaśnimy, dlaczego warto ustawić odniesienie przestrzenne oraz jakie korzyści przynosi to w rzeczywistych projektach. Po zakończeniu tego przewodnika będziesz w stanie z pewnością integrować możliwości GIS w swoich rozwiązaniach .NET.

## Szybkie odpowiedzi
- **Jaki jest główny cel tego samouczka?** Aby pokazać, jak utworzyć warstwę wektorową z określonym SRS przy użyciu Aspose.GIS for .NET.  
- **Jakie odwzorowanie jest użyte w przykładzie?** World Mercator (EPSG:3395).  
- **Czy potrzebna jest licencja do uruchomienia kodu?** Darmowa wersja próbna wystarcza do rozwoju; licencja komercyjna jest wymagana w produkcji.  
- **Czy mogę używać tego samego podejścia z innymi formatami GIS?** Tak, obsługa SRS jest taka sama dla Shapefile, GeoJSON, KML itp.  
- **Jakie wersje .NET są wspierane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Czym jest warstwa wektorowa i dlaczego ustawiać jej odniesienie przestrzenne?
Warstwa **wektorowa** przechowuje elementy geometryczne (punkty, linie, wielokąty) wraz z danymi atrybutowymi. Przypisanie **odniesienia przestrzennego** (SRS) informuje oprogramowanie GIS, jak interpretować te współrzędne na powierzchni Ziemi. Ustawienie prawidłowego SRS zapewnia dokładne pomiary, prawidłowe nakładanie się warstw oraz wiarygodne wizualizacje map.

## Wymagania wstępne
- Podstawowa znajomość C# i programowania w .NET.  
- Biblioteka Aspose.GIS for .NET zainstalowana. Możesz ją pobrać **[tutaj](https://releases.aspose.com/gis/net/)**.  
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
Utwórzmy **projekcyjny system odniesienia przestrzennego** przy użyciu projekcji World Mercator jako przykładu. To pokazuje **jak ustawić srs** dla warstwy.

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
Teraz **utworzymy warstwę wektorową** (plik Shapefile) i dodamy elementy, które używają właśnie zdefiniowanego SRS. Ta część odpowiada na pytanie **jak utworzyć warstwę** przy użyciu Aspose.GIS.

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

> **Wskazówka:** Zawsze sprawdzaj, czy `SpatialReferenceSystem` geometrii odpowiada SRS warstwy przed jej dodaniem. Niepasujące wartości SRS wywołują `GisException`, jak pokazano powyżej.

## Sprawdzenie systemu odniesienia przestrzennego – Krok 3
Na koniec otwórz warstwę i potwierdź, że SRS został poprawnie zastosowany.

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

Jeśli wywołanie `IsEquivalent` zwróci `true`, udało Ci się pomyślnie **utworzyć warstwę wektorową** z żądanym odniesieniem przestrzennym.

## Typowe problemy i rozwiązania
| Problem | Dlaczego się pojawia | Rozwiązanie |
|-------|----------------|-----|
| `GisException` przy dodawaniu elementu | Geometria używa innego SRS niż warstwa | Ustaw `feature.Geometry.SpatialReferenceSystem` na SRS warstwy przed dodaniem |
| Warstwa wydaje się pusta w oprogramowaniu GIS | Plik shapefile został utworzony bez prawidłowego pliku `.prj` | Upewnij się, że obiekt `projectedSrs` jest przekazywany przy tworzeniu warstwy |
| Nieoczekiwane wartości współrzędnych | Nieprawidłowe parametry projekcji (np. południk zerowy) | Sprawdź ponownie parametry przekazywane do `AddProjectionParameter` |

## FAQ
### Czy Aspose.GIS jest kompatybilny ze wszystkimi formatami plików GIS?
Aspose.GIS obsługuje różne formaty GIS, w tym Shapefile, GeoJSON, KML i inne. Sprawdź **[dokumentację](https://reference.aspose.com/gis/net/)**, aby zobaczyć pełną listę.

### Czy mogę używać Aspose.GIS w aplikacji webowej?
Oczywiście! Aspose.GIS for .NET jest wszechstronny i może być używany w aplikacjach webowych, aplikacjach desktopowych, a nawet w aplikacjach mobilnych.

### Gdzie mogę uzyskać wsparcie dla Aspose.GIS?
Możesz znaleźć pomocną społeczność na **[forum Aspose.GIS](https://forum.aspose.com/c/gis/33)** w przypadku pytań lub problemów.

### Czy dostępna jest darmowa wersja próbna?
Tak, możesz wypróbować funkcje Aspose.GIS, uzyskując darmową wersję próbną **[tutaj](https://releases.aspose.com/)**.

### Jak mogę zakupić licencję na Aspose.GIS?
Aby zakupić licencję, odwiedź **[stronę zakupu](https://purchase.aspose.com/buy)**.

## Często zadawane pytania (dodatkowe)

**P: Co się stanie, jeśli spróbuję dodać geometrię z innym SRS?**  
O: Aspose.GIS zgłasza `GisException`. Musisz albo przekształcić geometrię, albo zapewnić, że używa tego samego SRS co warstwa.

**P: Czy mogę zmienić SRS istniejącej warstwy?**  
O: Tak, możesz utworzyć nową warstwę z żądanym SRS i skopiować do niej elementy, przekształcając je w razie potrzeby.

**P: Czy można pracować z współrzędnymi 3D?**  
O: Aspose.GIS obsługuje współrzędne Z; wystarczy używać konstruktorów geometrii, które przyjmują wartość Z.

**P: Czy biblioteka automatycznie obsługuje transformacje datum?**  
O: Gdy przekształcasz geometrie przy użyciu `Geometry.Transform`, Aspose.GIS wykonuje niezbędne przesunięcie datum.

**P: Jakie wersje .NET są oficjalnie testowane?**  
O: Biblioteka jest testowana z .NET Framework 4.5+, .NET Core 3.1+ oraz .NET 5/6/7.

## Podsumowanie
Teraz wiesz, jak **utworzyć warstwę wektorową** z niestandardowym systemem odniesienia przestrzennego przy użyciu Aspose.GIS for .NET. Ustawiając prawidłowy SRS, konsekwentnie obsługując geometrie i weryfikując metadane warstwy, możesz tworzyć solidne aplikacje z obsługą GIS, które współpracują z dowolnym standardowym oprogramowaniem GIS.

---

**Ostatnia aktualizacja:** 2026-01-15  
**Testowano z:** Aspose.GIS 24.11 for .NET (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}