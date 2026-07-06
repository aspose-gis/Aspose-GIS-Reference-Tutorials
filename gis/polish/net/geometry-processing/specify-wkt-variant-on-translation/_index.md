---
date: 2026-04-09
description: Dowiedz się, jak przypisać odniesienie przestrzenne i ustawić precyzję
  dziesiętną przy tworzeniu punktu w C# za pomocą Aspose.GIS dla .NET w swoich aplikacjach
  .NET.
keywords:
- assign spatial reference
- set decimal precision
- create point c#
linktitle: Określ wariant WKT przy tłumaczeniu
second_title: Aspose.GIS .NET API
title: Przypisz odniesienie przestrzenne i ustaw wariant WKT przy użyciu Aspose.GIS
url: /pl/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Przypisanie układu odniesienia przestrzennego i ustawienie wariantu WKT przy użyciu Aspose.GIS

## Wprowadzenie
W tym samouczku nauczysz się, jak **przypisać układ odniesienia przestrzennego** do geometrii i kontrolować dokładny format wyjściowy WKT przy użyciu Aspose.GIS dla .NET. Niezależnie od tego, czy potrzebujesz **tworzyć obiekty point C#** do mapowania, analiz lub wymiany danych, możliwość wyboru odpowiedniego wariantu WKT i precyzji liczbowej sprawia, że Twoje dane przestrzenne są interoperacyjne i łatwe do odczytania. Przejdźmy krok po kroku przez proces.

## Szybkie odpowiedzi
- **Co oznacza „przypisanie układu odniesienia przestrzennego”?** Łączy geometrię z określonym systemem współrzędnych, takim jak WGS‑84.  
- **Jakie warianty WKT są obsługiwane?** Iso, SimpleFeatureAccessOutdated i ExtendedPostGis.  
- **Jak mogę kontrolować precyzję dziesiętną?** Użyj opcji `NumericFormat` takich jak `General`, `RoundTrip` lub `Flat`.  
- **Czy potrzebna jest licencja?** Dostępna jest darmowa wersja próbna; licencja komercyjna jest wymagana w produkcji.  
- **Jakie wersje .NET są kompatybilne?** .NET Framework 4.0+ oraz .NET Core/5/6+.

## Co to jest „przypisanie układu odniesienia przestrzennego”?
Przypisanie układu odniesienia przestrzennego (lub systemu odniesienia przestrzennego, SRS) informuje oprogramowanie GIS, jak interpretować wartości współrzędnych geometrii. Bez SRS liczby szerokości‑i długości geograficznej punktu nie mają rzeczywistego znaczenia.

## Dlaczego kontrolować wariant WKT i format liczbowy?
Różne narzędzia GIS oczekują nieco innych składni WKT. Wybranie właściwego wariantu zapewnia płynną wymianę danych, a ustawienie precyzji dziesiętnej zapobiega błędom zaokrągleń lub zbyt długim liczbom, które zaśmiecają logi i pliki.

## Wymagania wstępne
1. Aspose.GIS dla .NET – pobierz ze [strony pobierania](https://releases.aspose.com/gis/net/).  
2. Środowisko programistyczne .NET (Visual Studio, VS Code lub Rider).  
3. Podstawowa znajomość C# i platformy .NET.

## Importowanie przestrzeni nazw
Przed użyciem jakichkolwiek klas Aspose.GIS, zaimportuj wymagane przestrzenie nazw:

```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```

## Krok 1: Utworzenie obiektu Point (create point C#)
Zaczynamy od skonstruowania obiektu `Point` z szerokością, długością i opcjonalną wartością miary (M):

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Krok 2: Przypisanie systemu odniesienia przestrzennego (SRS)
Teraz **przypisujemy układ odniesienia przestrzennego** do punktu. Tutaj używamy powszechnie wspieranego systemu WGS‑84 (SRID 4326):

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Krok 3: Określenie żądanego wariantu WKT
Wybierz wariant WKT, który pasuje do Twojej aplikacji downstream:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Krok 4: Ustawienie precyzji dziesiętnej dla wyjścia WKT
Kontroluj liczbę cyfr w końcowym ciągu znaków przy użyciu `NumericFormat`:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### Typowe pułapki i wskazówki
- **Pułapka:** Zapomnienie o ustawieniu SRS przed wywołaniem `AsText` może skutkować brakiem informacji o SRID.  
- **Wskazówka:** Użyj `NumericFormat.RoundTrip`, gdy potrzebujesz bezstratnego przenoszenia współrzędnych.  
- **Wskazówka:** Wariant `Iso` jest najbardziej przenośny; wybierz `ExtendedPostGis` tylko wtedy, gdy potrzebujesz wbudowanego SRID.

## Zakończenie
Teraz wiesz, jak **przypisać układ odniesienia przestrzennego**, wybrać odpowiedni wariant WKT i **ustawić precyzję dziesiętną** przy **tworzeniu obiektów point C#** za pomocą Aspose.GIS. Te kontrolki dają Ci elastyczność spełnienia dokładnych wymagań każdego przepływu pracy GIS, od prostej wizualizacji po wysoką precyzję analiz przestrzennych.

## Najczęściej zadawane pytania

**Q:** Czy Aspose.GIS jest kompatybilny ze wszystkimi wersjami .NET?  
**A:** Tak, Aspose.GIS obsługuje .NET Framework 4.0 i wyższe, a także .NET Core/5/6.

**Q:** Czy mogę używać Aspose.GIS w projektach komercyjnych?  
**A:** Oczywiście. Licencja komercyjna jest wymagana w produkcji, ale dostępna jest darmowa wersja próbna do oceny.

**Q:** Czy Aspose.GIS obsługuje inne formaty danych przestrzennych?  
**A:** Tak, współpracuje z ESRI Shapefile, GeoJSON, KML i wieloma innymi formatami.

**Q:** Gdzie mogę pobrać darmową wersję próbną?  
**A:** Darmową wersję próbną Aspose.GIS możesz pobrać [tutaj](https://releases.aspose.com/).

**Q:** Jak uzyskać pomoc w razie problemów?  
**A:** Zadaj pytania na forum społeczności Aspose.GIS [forum](https://forum.aspose.com/c/gis/33), gdzie pomogą zarówno pracownicy Aspose, jak i członkowie społeczności.

---

**Ostatnia aktualizacja:** 2026-04-09  
**Testowano z:** Aspose.GIS dla .NET (najnowsze wydanie)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}