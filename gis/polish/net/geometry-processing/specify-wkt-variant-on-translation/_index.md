---
date: 2026-09-15
description: Dowiedz się, jak przypisać coordinate system, ustawić WKT variant i kontrolować
  decimal precision przy tworzeniu point geometry w C# z Aspose.GIS dla .NET.
keywords:
- assign coordinate system
- assign spatial reference
- set decimal precision
- create point geometry
- set numeric format
lastmod: 2026-09-15
linktitle: Określ WKT Variant przy tłumaczeniu
og_description: Dowiedz się, jak przypisać coordinate system, ustawić WKT variant
  i kontrolować decimal precision przy tworzeniu point geometry w C# z Aspose.GIS
  dla .NET.
og_image_alt: Developer guide showing C# code to assign coordinate system and configure
  WKT output with Aspose.GIS
og_title: Przypisz coordinate system, ustaw WKT variant przy użyciu Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-09-15'
  description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  headline: Assign coordinate system, set WKT variant using Aspose.GIS
  type: TechArticle
- description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  name: Assign coordinate system, set WKT variant using Aspose.GIS
  steps:
  - name: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
    text: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
  - name: A .NET development environment (Visual Studio, VS Code, or Rider).
    text: A .NET development environment (Visual Studio, VS Code, or Rider).
  - name: Basic familiarity with C# and the .NET framework.
    text: Basic familiarity with C# and the .NET framework.
  type: HowTo
- questions:
  - answer: It binds a geometry to a specific coordinate reference system such as
      WGS‑84.
    question: What does “assign coordinate system” mean?
  - answer: Iso, SimpleFeatureAccessOutdated, and ExtendedPostGis.
    question: Which WKT variants are supported?
  - answer: Use the `NumericFormat` enum (`General`, `RoundTrip`, `Flat`).
    question: How can I control decimal precision?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license for Aspose.GIS?
  - answer: .NET Framework 4.0+ and .NET Core/5/6+.
    question: What .NET versions are compatible?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- assign coordinate system
- Aspose.GIS
- C# geometry
- WKT variant
title: Przypisz coordinate system, ustaw WKT variant przy użyciu Aspose.GIS
url: /pl/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Przypisz układ współrzędnych, ustaw wariant WKT przy użyciu Aspose.GIS

## Wprowadzenie
W tym samouczku nauczysz się, jak **przypisać układ współrzędnych**, wybrać odpowiedni wariant WKT oraz kontrolować precyzję dziesiętną podczas **tworzenia geometrii punktu** w C# przy użyciu Aspose.GIS dla .NET. Niezależnie od tego, czy tworzysz usługę mapowania, wykonujesz analizy przestrzenne, czy wymieniasz dane między platformami GIS, te ustawienia zapewniają, że Twój wynik jest zarówno interoperacyjny, jak i łatwy do odczytania. Przejdźmy krok po kroku przez proces.

## Szybkie odpowiedzi
- **Co oznacza „przypisanie układu współrzędnych”?** Łączy geometrię z określonym systemem odniesienia współrzędnych, takim jak WGS‑84.  
- **Jakie warianty WKT są obsługiwane?** Iso, SimpleFeatureAccessOutdated i ExtendedPostGis.  
- **Jak mogę kontrolować precyzję dziesiętną?** Użyj wyliczenia `NumericFormat` (`General`, `RoundTrip`, `Flat`).  
- **Czy potrzebuję licencji na Aspose.GIS?** Dostępna jest darmowa wersja próbna; licencja komercyjna jest wymagana do użytku produkcyjnego.  
- **Jakie wersje .NET są kompatybilne?** .NET Framework 4.0+ oraz .NET Core/5/6+.

## Co to jest „przypisanie układu współrzędnych”?
Przypisanie odniesienia przestrzennego (lub systemu odniesienia przestrzennego, SRS) informuje oprogramowanie GIS, jak interpretować wartości współrzędnych geometrii, łącząc liczby z rzeczywistym systemem współrzędnych, takim jak WGS‑84. Bez SRS liczby szerokości‑i‑długości geograficznej punktu nie mają rzeczywistego znaczenia.

## Dlaczego kontrolować wariant WKT i format liczbowy?
Ponad 30 narzędzi GIS oczekuje określonych składni WKT, więc wybór właściwego wariantu zapobiega błędom importu. Ustawienie formatu liczbowego redukuje szumy zaokrągleń i utrzymuje wyjście zwięzłe, co jest szczególnie ważne, gdy logi lub pliki są przetwarzane programowo.

## Wymagania wstępne
1. Aspose.GIS dla .NET – pobierz ze [download page](https://releases.aspose.com/gis/net/).  
2. Środowisko programistyczne .NET (Visual Studio, VS Code lub Rider).  
3. Podstawowa znajomość C# i platformy .NET.

## Importowanie przestrzeni nazw
Przed użyciem jakichkolwiek klas Aspose.GIS zaimportuj wymagane przestrzenie nazw:

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

## Jak przypisać układ współrzędnych do punktu?
Wczytaj instancję `Point`, a następnie dołącz system odniesienia przestrzennego (SRS) przy użyciu klasy `SpatialReference`. Ten dwustopniowy wzorzec zapewnia, że geometria zawiera metadane układu współrzędnych przy eksporcie, umożliwiając narzędziom downstream poprawną interpretację współrzędnych. Klasa `Point` reprezentuje pojedynczą lokalizację określoną współrzędnymi X (długość) i Y (szerokość).

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Krok 2: przypisz system odniesienia przestrzennego (SRS)
Teraz **przypisujemy odniesienie przestrzenne** do punktu. `SpatialReference` reprezentuje system odniesienia współrzędnych zidentyfikowany przez SRID. Tutaj używamy powszechnie wspieranego systemu WGS‑84 (SRID 4326):

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Krok 3: określ żądany wariant WKT
Wybierz wariant WKT, który odpowiada Twojej aplikacji downstream:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Jak ustawić precyzję dziesiętną dla wyjścia WKT?
Kontroluj liczbę cyfr pojawiających się w końcowym ciągu znaków przy użyciu wyliczenia `NumericFormat`, które definiuje zasady formatowania, takie jak `General`, `RoundTrip` lub `Flat`. Wybranie `RoundTrip` zachowuje pełną wierność współrzędnych w scenariuszach round‑tripping, podczas gdy `General` zapewnia zwięzłą reprezentację odpowiednią dla większości zadań wizualizacyjnych. Wyliczenie `NumericFormat` kontroluje sposób formatowania liczb współrzędnych w wyjściu WKT.

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### Typowe pułapki i wskazówki
- **Pułapka:** Zapomnienie o ustawieniu SRS przed wywołaniem `AsText` może spowodować brak informacji o SRID.  
- **Wskazówka:** Użyj `NumericFormat.RoundTrip`, gdy potrzebujesz bezstratnego round‑trippingu współrzędnych.  
- **Wskazówka:** Wariant `Iso` jest najbardziej przenośny; wybierz `ExtendedPostGis` tylko wtedy, gdy potrzebujesz wbudowanego SRID.

## Podsumowanie
Teraz wiesz, jak **przypisać układ współrzędnych**, wybrać odpowiedni wariant WKT oraz **ustawić precyzję dziesiętną**, gdy **tworzysz geometrię punktu** przy użyciu Aspose.GIS. Te ustawienia dają Ci elastyczność potrzebną do spełnienia dokładnych wymagań dowolnego przepływu pracy GIS, od prostej wizualizacji po wysokiej precyzji analizę przestrzenną.

## Najczęściej zadawane pytania

**Q:** Czy Aspose.GIS jest kompatybilny ze wszystkimi wersjami .NET?  
**A:** Tak, Aspose.GIS obsługuje .NET Framework 4.0 i wyższe, a także .NET Core/5/6.

**Q:** Czy mogę używać Aspose.GIS w projektach komercyjnych?  
**A:** Oczywiście. Licencja komercyjna jest wymagana do użytku produkcyjnego, ale dostępna jest darmowa wersja próbna do oceny.

**Q:** Czy Aspose.GIS obsługuje inne formaty danych przestrzennych?  
**A:** Tak, współpracuje z ponad 30 formatami, w tym ESRI Shapefile, GeoJSON, KML, CSV i wieloma innymi.

**Q:** Gdzie mogę pobrać darmową wersję próbną?  
**A:** Darmową wersję próbną Aspose.GIS można pobrać ze [Aspose.GIS free trial download page](https://releases.aspose.com/).

**Q:** Jak uzyskać pomoc, jeśli napotkam problemy?  
**A:** Zamieść swoje pytania na forum społeczności Aspose.GIS [forum](https://forum.aspose.com/c/gis/33), gdzie zarówno pracownicy Aspose, jak i członkowie społeczności mogą pomóc.

---

**Ostatnia aktualizacja:** 2026-09-15  
**Testowano z:** Aspose.GIS for .NET (latest release)  
**Autor:** Aspose

## Powiązane samouczki

- [Create a Vector Layer and Set Its Spatial Reference System](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [How to Translate Geometry to WKT with Aspose.GIS for .NET](/gis/net/geometry-processing/translate-geometry-to-wkt/)
- [How to Limit Precision Writing Geometries with Aspose.GIS](/gis/net/geometry-processing/limit-precision-writing-geometries/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}