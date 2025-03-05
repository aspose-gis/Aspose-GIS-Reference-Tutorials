---
title: Utwórz warstwę wektorową za pomocą SRS
linktitle: Utwórz warstwę wektorową za pomocą SRS
second_title: Aspose.GIS .NET API
description: Poznaj Aspose.GIS dla .NET - Twój klucz do płynnej integracji GIS. Twórz warstwy wektorowe bez wysiłku, korzystając z określonych systemów odniesień przestrzennych. Pobierz teraz!
type: docs
weight: 13
url: /pl/net/layer-management/create-vector-layer-with-srs/
---
## Wstęp
Aspose.GIS dla .NET to potężna biblioteka, która umożliwia programistom płynną pracę z danymi systemu informacji geograficznej (GIS) w aplikacjach .NET. W tym samouczku skupimy się na tworzeniu warstwy wektorowej z systemem odniesień przestrzennych (SRS). Pod koniec tego przewodnika będziesz w stanie bez wysiłku zintegrować możliwości GIS ze swoimi projektami .NET.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Podstawowa znajomość programowania w C# i .NET.
-  Zainstalowana biblioteka Aspose.GIS dla .NET. Możesz go pobrać[Tutaj](https://releases.aspose.com/gis/net/).
- Skonfigurowane i gotowe środowisko programistyczne.
## Importuj przestrzenie nazw
Upewnij się, że na początku pliku C# zaimportowano niezbędne przestrzenie nazw:
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
## Krok 1: Skonfiguruj projektowany system odniesień przestrzennych
Stwórzmy rzutowany układ odniesień przestrzennych (SRS) na przykładzie projekcji World Mercator. Wykonaj następujące kroki:
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
## Krok 2: Utwórz warstwę wektorową i dodaj funkcje
Utwórzmy teraz plik kształtu i dodajmy funkcje z określonym SRS:
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
        layer.Add(feature); // Spowoduje to wyjątek, ponieważ geometria ma inny SRS
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```
## Krok 3: Zweryfikuj przestrzenny system odniesienia
Na koniec otwórzmy warstwę i zweryfikujmy jej układ odniesień przestrzennych:
```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // „WGS 84 / Światowy Mercator”
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Powinno zwrócić wartość true
}
```
Wykonując poniższe kroki, pomyślnie utworzyłeś warstwę wektorową z określonym systemem odniesień przestrzennych przy użyciu Aspose.GIS dla .NET.
## Wniosek
Integracja funkcjonalności GIS z aplikacjami .NET nigdy nie była łatwiejsza dzięki Aspose.GIS. Dzięki możliwości łatwego tworzenia warstw wektorowych i zarządzania przestrzennymi systemami odniesień, możesz wzbogacić swoje projekty o zaawansowane możliwości geoprzestrzenne.
## Często zadawane pytania
### Czy Aspose.GIS jest kompatybilny ze wszystkimi formatami plików GIS?
 Aspose.GIS obsługuje różne formaty GIS, w tym Shapefile, GeoJSON, KML i inne. Sprawdź[dokumentacja](https://reference.aspose.com/gis/net/) dla pełnej listy.
### Czy mogę używać Aspose.GIS w aplikacji internetowej?
Absolutnie! Aspose.GIS dla .NET jest wszechstronny i może być używany w aplikacjach internetowych, aplikacjach komputerowych, a nawet aplikacjach mobilnych.
### Gdzie mogę uzyskać wsparcie dla Aspose.GIS?
 Pomocną społeczność znajdziesz na stronie[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33) w przypadku jakichkolwiek pytań lub problemów, które możesz napotkać.
### Czy dostępny jest bezpłatny okres próbny?
 Tak, możesz poznać funkcje Aspose.GIS, uzyskując bezpłatną wersję próbną[Tutaj](https://releases.aspose.com/).
### Jak mogę kupić licencję na Aspose.GIS?
 Aby kupić licencję, odwiedź stronę[strona zakupu](https://purchase.aspose.com/buy).