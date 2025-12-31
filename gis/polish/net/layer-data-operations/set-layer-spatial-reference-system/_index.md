---
date: 2025-12-31
description: Dowiedz się, jak utworzyć warstwę wektorową i ustawić system odniesienia
  przestrzennego warstwy przy użyciu Aspose.GIS dla .NET. Opanuj definiowanie odniesienia
  przestrzennego, dodawanie obiektu punktowego i pobieranie kodu EPSG.
linktitle: Set Layer Spatial Reference System
second_title: Aspose.GIS .NET API
title: Utwórz warstwę wektorową i ustaw układ odniesienia przestrzennego warstwy
url: /pl/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz warstwę wektorową i ustaw układ odniesienia przestrzennego warstwy

## Wprowadzenie
W rozległym krajobrazie Systemów Informacji Geograficznej (GIS) **Aspose.GIS for .NET** wyróżnia się jako solidne i wszechstronne narzędzie dla programistów. W tym samouczku **create vector layer**, zdefiniujesz jego odniesienie przestrzenne, dodasz obiekt punktowy i odczytasz kod EPSG — wszystko przy jasnych, krok po kroku wskazówkach. Niezależnie od tego, czy jesteś doświadczonym inżynierem GIS, czy dopiero zaczynasz, te techniki pomogą Ci poprawnie ustawić układ współrzędnych shapefile i zwiększyć niezawodność przepływów pracy z danymi przestrzennymi.

## Szybkie odpowiedzi
- **Co oznacza „create vector layer”?** Tworzy nową warstwę GIS (np. Shapefile), która może przechowywać geometrie takie jak punkty, linie lub wielokąty.  
- **Jaki kod EPSG jest użyty w przykładzie?** EPSG 26918 (NAD83 / UTM zone 18N).  
- **Czy mogę dodać obiekt punktowy po utworzeniu warstwy?** Tak — użyj `ConstructFeature()` i przypisz geometrię `Point`.  
- **Jak odczytać CRS warstwy?** Odczytaj `layer.SpatialReferenceSystem.EpsgCode` lub `.Name`.  
- **Czy potrzebna jest licencja na Aspose.GIS?** Dostępna jest bezpłatna wersja próbna; licencja jest wymagana do użytku produkcyjnego.

## Wymagania wstępne
- Praktyczna znajomość programowania w .NET.  
- Zainstalowane Visual Studio na Twoim komputerze.  
- Biblioteka Aspose.GIS for .NET, którą możesz pobrać [here](https://releases.aspose.com/gis/net/).  
- Podstawowa znajomość systemów odniesień przestrzennych w GIS.

## Importowanie przestrzeni nazw
W swoim projekcie .NET rozpocznij od zaimportowania niezbędnych przestrzeni nazw, aby uzyskać dostęp do funkcjonalności oferowanych przez Aspose.GIS. Użyj poniższego fragmentu kodu:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## Krok 1: Określ katalog dokumentów
Rozpocznij od określenia ścieżki do katalogu dokumentów. Będzie to miejsce, w którym przechowywane są pliki danych przestrzennych.

```csharp
string dataDir = "Your Document Directory";
```

## Krok 2: Zdefiniuj odniesienie przestrzenne i ustaw układ współrzędnych Shapefile
Zdefiniuj ścieżkę do Shapefile i **define spatial reference** przy użyciu kodu EPSG (26918 w tym przykładzie). Ten krok **sets the shapefile coordinate system** dla warstwy.

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## Krok 3: Utwórz warstwę wektorową
Teraz **create vector layer** z określoną ścieżką Shapefile, typem sterownika (Shapefile) oraz systemem odniesień przestrzennych, który właśnie zdefiniowałeś.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

## Krok 4: Dodaj obiekt punktowy do warstwy
Utwórz nowy obiekt i **add point feature** ustawiając jego geometrię (obiekt `Point` o współrzędnych 60, 24). Następnie dodaj obiekt do warstwy wektorowej.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

## Krok 5: Odczytaj informacje o systemie odniesień przestrzennych (odczytaj kod EPSG)
Otwórz warstwę wektorową i odczytaj informacje o systemie odniesień przestrzennych, takie jak kod EPSG oraz czytelna nazwa. To pokazuje, jak **retrieve EPSG code** i **set layer CRS**.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

Powtarzaj te kroki zgodnie ze swoim konkretnym przypadkiem użycia, a będziesz na dobrej drodze do opanowania sztuki **create vector layer** oraz zarządzania odniesieniami przestrzennymi przy użyciu Aspose.GIS for .NET.

## Typowe problemy i rozwiązania
| Problem | Dlaczego się pojawia | Rozwiązanie |
|---------|----------------------|-------------|
| **Nie udało się otworzyć warstwy** | Nieprawidłowy sterownik lub uszkodzona ścieżka pliku | Sprawdź `Drivers.Shapefile` i upewnij się, że `path` wskazuje istniejący plik `.shp`. |
| **Wyświetlany nieprawidłowy CRS** | Użycie niewłaściwego kodu EPSG | Sprawdź ponownie kod EPSG w autorytatywnym źródle (np. EPSG.io). |
| **Obiekt nie został zapisany** | Nie wywołano `layer.Add(feature)` wewnątrz bloku `using` | Upewnij się, że metoda `Add` jest wywołana przed zwolnieniem warstwy. |

## Najczęściej zadawane pytania
### Czy Aspose.GIS jest kompatybilny z innymi bibliotekami GIS?
Tak, Aspose.GIS integruje się dobrze z innymi bibliotekami GIS i może być używany w ich połączeniu.

### Czy mogę używać Aspose.GIS zarówno w aplikacjach desktopowych, jak i webowych?
Oczywiście! Aspose.GIS jest wszechstronny i może być wykorzystywany zarówno w aplikacjach desktopowych, jak i web‑opartych.

### Czy dostępne są opcje licencjonowania Aspose.GIS?
Tak, możesz zapoznać się z opcjami licencjonowania i dokonać zakupu [here](https://purchase.aspose.com/buy).

### Czy dostępna jest bezpłatna wersja próbna Aspose.GIS?
Oczywiście! Możesz pobrać bezpłatną wersję próbną [here](https://releases.aspose.com/).

### Gdzie mogę uzyskać wsparcie w sprawach związanych z Aspose.GIS?
W razie potrzeby wsparcia lub pytań, odwiedź [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).

## Dodatkowe często zadawane pytania
**Q: Jak zmienić CRS istniejącego Shapefile?**  
A: Otwórz warstwę, utwórz nowy `SpatialReferenceSystem` z żądanym kodem EPSG i przypisz go do `layer.SpatialReferenceSystem` przed zapisaniem.

**Q: Czy mogę dodać inne typy geometrii (np. wielokąty) używając tego samego podejścia?**  
A: Tak — zamień `new Point(x, y)` na `new Polygon(...)` lub `new LineString(...)` w zależności od potrzeb.

**Q: Czy można efektywnie pracować z dużymi zestawami danych?**  
A: Używaj API strumieniowego (`VectorLayer.Create` z `FeatureCollection`) i niezwłocznie zwalniaj warstwy, aby zwolnić zasoby.

**Q: Czy Aspose.GIS obsługuje transformację współrzędnych?**  
A: Tak — użyj `Geometry.Transform(targetSrs)`, aby przekształcić geometrie pomiędzy różnymi systemami odniesień.

**Q: Jakie wersje .NET są obsługiwane?**  
A: Aspose.GIS działa z .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.

## Podsumowanie
W tym samouczku omówiliśmy, jak **create vector layer**, zdefiniować jego odniesienie przestrzenne, **add point feature** oraz **retrieve EPSG code** przy użyciu Aspose.GIS for .NET. Opanowując te kroki, możesz pewnie ustawiać układ współrzędnych shapefile, zarządzać CRS warstwy i budować niezawodne aplikacje GIS.

---

**Ostatnia aktualizacja:** 2025-12-31  
**Testowano z:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}