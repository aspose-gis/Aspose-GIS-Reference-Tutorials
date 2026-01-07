---
date: 2026-01-07
description: Dowiedz się, jak zapisywać plik KML przy użyciu Aspose.GIS dla .NET,
  jak tworzyć KML, dodawać atrybut typu logicznego oraz tworzyć liniowy ciąg w swoich
  aplikacjach.
linktitle: Interact with KML Layer
second_title: Aspose.GIS .NET API
title: Jak zapisać plik KML przy użyciu Aspose.GIS dla .NET
url: /pl/net/layer-interaction-and-data-access/interact-with-kml-layer/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak zapisać plik KML przy użyciu Aspose.GIS dla .NET

## Introduction
W dzisiejszym świecie napędzanym danymi możliwość **zapisu pliku KML** programowo daje Ci moc udostępniania informacji geograficznych na różnych platformach, wizualizacji tras na mapach oraz integracji danych lokalizacyjnych w aplikacjach internetowych lub mobilnych. Aspose.GIS dla .NET upraszcza ten proces, pozwalając skupić się na logice, a nie na zawiłościach formatu pliku. W tym samouczku przejdziemy przez tworzenie warstwy KML, dodawanie atrybutów (w tym atrybutu logicznego) oraz budowanie geometrii linii — wszystko z jasnym, krok po kroku kodem.

## Quick Answers
- **Co oznacza „zapis pliku KML”?** Generowanie dokumentu KML (Keyhole Markup Language), który opisuje elementy geograficzne takie jak punkty, linie i wielokąty.  
- **Która biblioteka jest najlepsza dla .NET?** Aspose.GIS dla .NET zapewnia płynne API do tworzenia i edytowania plików KML.  
- **Czy potrzebna jest licencja do rozwoju?** Darmowa wersja próbna wystarcza do oceny; licencja jest wymagana w środowisku produkcyjnym.  
- **Czy mogę dodać własne atrybuty?** Tak – możesz dodawać atrybuty typu string, integer, boolean i double do każdego obiektu.  
- **Czy obsługiwane jest tworzenie geometrii?** Oczywiście – możesz tworzyć punkty, linie, wielokąty i inne.

## Prerequisites
Zanim wyruszymy w tę podróż, upewnij się, że spełniasz następujące wymagania:
- Aspose.GIS dla .NET: Pobierz i zainstaluj bibliotekę ze [strony pobierania Aspose.GIS dla .NET](https://releases.aspose.com/gis/net/).
- Środowisko programistyczne: Skonfiguruj odpowiednie środowisko, np. Visual Studio, aby płynnie integrować Aspose.GIS z projektami .NET.

## Import Namespaces
Zanim zaczniemy pracę z warstwami KML, upewnij się, że w projekcie zaimportowano niezbędne przestrzenie nazw. Ten krok zapewnia dostęp do klas i metod potrzebnych do manipulacji danymi geoprzestrzennymi.

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Drawing;
using System.Threading;
using Aspose.Gis.Formats.Kml;
using Aspose.Gis.Formats.Kml.Styles;
using Aspose.Gis.Geometries;
using Point = Aspose.Gis.Geometries.Point;
```

## Step 1: Set the Document Directory
Zdefiniuj ścieżkę do katalogu dokumentów, w którym będą przechowywane pliki KML.

```csharp
string dataDir = "Your Document Directory";
```

## Step 2: Create a KML Layer
Zainicjuj warstwę KML przy użyciu Aspose.GIS, podając ścieżkę do pliku KML.

```csharp
using (var layer = Drivers.Kml.CreateLayer(dataDir + "Kml_File_out.kml"))
{
```

## Step 3: Define Attributes (add boolean attribute)
Dodaj atrybuty do warstwy KML, aby reprezentować różne typy danych, takie jak string, integer, **boolean** oraz double. To miejsce, w którym „dodajesz atrybut logiczny” do każdego obiektu.

```csharp
layer.Attributes.Add(new FeatureAttribute("string_data", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("int_data", AttributeDataType.Integer));
layer.Attributes.Add(new FeatureAttribute("bool_data", AttributeDataType.Boolean));
layer.Attributes.Add(new FeatureAttribute("float_data", AttributeDataType.Double));
```

## Step 4: Construct and Populate Features (create line string)
Utwórz obiekty reprezentujące jednostki geoprzestrzenne i ustaw wartości zdefiniowanych atrybutów. Tutaj **tworzymy linię** (line string) geometryczną, aby zilustrować prostą ścieżkę.

```csharp
Feature feature = layer.ConstructFeature();
feature.SetValue("string_data", "string value");
feature.SetValue("int_data", 10);
feature.SetValue("bool_data", true);
feature.SetValue("float_data", 3.14);
feature.Geometry = new LineString(new[] { new Point(0, 0), new Point(1, 1) });
layer.Add(feature);
```

## Step 5: Add Another Feature
Powtórz proces, aby dodać drugi obiekt z innymi wartościami atrybutów oraz z geometrią null.

```csharp
Feature feature2 = layer.ConstructFeature();
feature2.SetValue("string_data", "string value2");
feature2.SetValue("int_data", 100);
feature2.SetValue("bool_data", false);
feature2.SetValue("float_data", 3.1415);
feature2.Geometry = Geometry.Null;
layer.Add(feature2);
```

## How to Write KML File – Putting It All Together
Postępując zgodnie z powyższymi krokami, otrzymujesz w pełni funkcjonalny plik KML zawierający własne atrybuty (w tym flagę logiczną) oraz geometrię linii. Możesz otworzyć powstały `Kml_File_out.kml` w Google Earth, ArcGIS lub dowolnym przeglądarce GIS obsługującej KML.

## Common Issues & Troubleshooting
- **Błędy ścieżki pliku** – Upewnij się, że `dataDir` kończy się separatorem ścieżki (`\` lub `/`) odpowiednim dla Twojego systemu operacyjnego.  
- **Brak licencji** – Wersja próbna działa w celach oceny, ale wersja licencjonowana jest wymagana do nieograniczonego zapisu plików KML.  
- **Geometria null** – Ustawienie `Geometry.Null` jest zamierzone dla obiektów bez danych przestrzennych; pomiń je, jeśli zawsze potrzebujesz geometrii.

## Frequently Asked Questions
### Czy Aspose.GIS jest kompatybilny z innymi formatami GIS?
Tak, Aspose.GIS obsługuje różne formaty GIS, w tym shapefile, GeoJSON i KML.

### Czy mogę wizualizować dane geoprzestrzenne utworzone przy użyciu Aspose.GIS?
Oczywiście! Aspose.GIS płynnie integruje się z bibliotekami mapującymi, umożliwiając wizualizację Twoich danych geoprzestrzennych.

### Czy dostępna jest wersja próbna Aspose.GIS?
Tak, możesz przetestować funkcje Aspose.GIS, pobierając [bezpłatną wersję próbną](https://releases.aspose.com/).

### Jak mogę uzyskać wsparcie dla Aspose.GIS?
Odwiedź [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) w celu uzyskania pomocy społeczności lub zapoznaj się z opcjami wsparcia premium [tutaj](https://purchase.aspose.com/buy).

### Czy dostępne są tymczasowe licencje dla Aspose.GIS?
Tak, możesz uzyskać tymczasową licencję [tutaj](https://purchase.aspose.com/temporary-license/).

## Additional Frequently Asked Questions

**Q: Jak tworzę pliki **how to create KML** z własnym stylem?**  
A: Użyj przestrzeni nazw `Aspose.Gis.Formats.Kml.Styles`, aby zdefiniować ikony, kolory linii i style etykiet przed dodaniem obiektów.

**Q: Czy mogę efektywnie zapisywać duże pliki KML?**  
A: Zapisuj obiekty w partiach i okresowo opróżniaj warstwę, aby utrzymać niskie zużycie pamięci.

**Q: Czy Aspose.GIS obsługuje .NET Core i .NET 6+?**  
A: Tak, biblioteka jest w pełni kompatybilna z .NET Core, .NET 5 i .NET 6.

---

**Last Updated:** 2026-01-07  
**Tested With:** Aspose.GIS 24.10 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}