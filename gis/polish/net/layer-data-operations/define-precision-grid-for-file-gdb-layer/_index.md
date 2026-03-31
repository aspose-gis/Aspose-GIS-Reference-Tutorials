---
date: 2025-12-28
description: Dowiedz się, jak ustawić siatkę dla warstwy File GDB przy użyciu Aspose.GIS
  dla .NET, w tym jak dodać obiekty do warstwy i zweryfikować zakres współrzędnych.
linktitle: Define Precision Grid for File GDB Layer
second_title: Aspose.GIS .NET API
title: Jak ustawić siatkę dla warstwy File GDB w Aspose.GIS
url: /pl/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak ustawić siatkę dla warstwy File GDB w Aspose.GIS

## Wprowadzenie
W tym samouczku dowiesz się **jak ustawić siatkę** dla warstwy File Geodatabase (GDB) przy użyciu Aspose.GIS dla .NET. Ustawienie siatki precyzji pomaga **zweryfikować zakres współrzędnych**, zapobiega błędom poza zakresem i zapewnia, że dane, które **dodajesz elementy do warstwy**, pozostają dokładne i wiarygodne. Przejdziemy krok po kroku, wyjaśnimy, dlaczego ustawienia są ważne, i pokażemy, jak radzić sobie z typowymi pułapkami.

## Szybkie odpowiedzi
- **Co oznacza „ustawienie siatki”?** Definiuje precyzję współrzędnych i prawidłowy zakres dla warstwy GIS.  
- **Dlaczego używać siatki precyzji?** Chroni dane przed nieprawidłowymi współrzędnymi i zwiększa efektywność przechowywania.  
- **Która biblioteka udostępnia tę funkcję?** Aspose.GIS dla .NET.  
- **Czy potrzebna jest licencja?** Dostępna jest wersja próbna; licencja komercyjna jest wymagana w produkcji.  
- **Czy mogę używać tego z .NET Core?** Tak, Aspose.GIS obsługuje .NET Framework i .NET Core.

## Czym jest siatka precyzji i dlaczego ją ustawiać?
Siatka precyzji to zestaw parametrów (pochodzenie, skala itp.), które informują silnik GIS, jak zaokrąglać i przechowywać wartości współrzędnych. Definiując siatkę, automatycznie **weryfikujesz zakres współrzędnych**, a każda próba wstawienia punktu poza siatką spowoduje wyrzucenie wyjątku — co pomaga **radzić sobie z sytuacjami poza zakresem** już na wczesnym etapie tworzenia.

## Wymagania wstępne
1. **Visual Studio** – dowolna aktualna wersja (Community, Professional lub Enterprise).  
2. **Aspose.GIS dla .NET** – pobierz go ze [strony internetowej](https://releases.aspose.com/gis/net/).  
3. **Podstawowa znajomość C#** – powinieneś być zaznajomiony z tworzeniem projektów konsolowych .NET.

## Importowanie przestrzeni nazw
Najpierw zaimportuj przestrzenie nazw wymagane do pracy z Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Text;
```

## Jak ustawić siatkę w warstwie File GDB
Poniżej znajduje się przewodnik krok po kroku, który dokładnie pokazuje, jak skonfigurować siatkę, utworzyć warstwę i bezpiecznie **dodawać elementy do warstwy**.

### Krok 1: Utwórz zestaw danych
Zaczynamy od utworzenia nowego zestawu danych File Geodatabase. To miejsce, w którym będzie znajdować się warstwa.

```csharp
var path = "Your Document Directory" + "PrecisionGrid_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

### Krok 2: Zdefiniuj opcje siatki precyzji
Tutaj określamy parametry siatki. Dostosuj pochodzenie i skale, aby pasowały do układu współrzędnych Twojego projektu.

```csharp
var options = new FileGdbOptions
{
    CoordinatePrecisionGrid = new FileGdbCoordinatePrecisionGrid
    {
        XOrigin = -400,
        YOrigin = -400,
        XYScale = 1e10,
        MOrigin = 0,
        MScale = 1e4,
    },
    EnsureValidCoordinatesRange = true,
};
```

*Flaga `EnsureValidCoordinatesRange = true` informuje Aspose.GIS, aby **weryfikował zakres współrzędnych** dla każdego elementu, który dodajesz.*

### Krok 3: Utwórz warstwę z siatką
Teraz tworzymy nową warstwę w zestawie danych, stosując właśnie zdefiniowane opcje siatki. Użyjemy układu odniesienia przestrzennego WGS84.

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
```

### Krok 4: Dodaj elementy do warstwy
Tworzymy dwa elementy punktowe. Pierwszy punkt znajduje się wewnątrz siatki, natomiast drugi celowo leży poza nią, aby zademonstrować **jak radzić sobie z błędami poza zakresem**.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(10, 20) { M = 10.1282 };
layer.Add(feature);
feature = layer.ConstructFeature();
feature.Geometry = new Point(-410, 0) { M = 20.2343 };
```

### Krok 5: Obsłuż wyjątki przy dodawaniu elementów poza zakresem
Próba dodania drugiego elementu spowoduje wyrzucenie wyjątku, ponieważ jego współrzędna X (`-410`) znajduje się poza zdefiniowaną siatką. Przechwytujemy wyjątek i wyświetlamy czytelną wiadomość.

```csharp
try
{
    layer.Add(feature);
}
catch (GisException e)
{
    Console.WriteLine(e.Message); // X value -410 is out of valid range.
}
```

### Krok 6: Sprzątanie
Instrukcje `using` automatycznie zamykają i zwalniają zestaw danych oraz warstwę, zapewniając zwolnienie wszystkich zasobów.

## Typowe problemy i rozwiązania
| Problem | Dlaczego się pojawia | Rozwiązanie |
|---------|----------------------|-------------|
| **Exception: “X value … is out of valid range.”** | Współrzędne leżą poza siatką precyzji. | Dostosuj `XOrigin`, `YOrigin` lub `XYScale`, aby objąć Twoje dane, lub upewnij się, że dane wejściowe mieszczą się w zdefiniowanym zakresie. |
| **Features not appearing in GIS viewer** | Warstwa nie została zapisana lub użyto niewłaściwego układu odniesienia. | Sprawdź, czy `SpatialReferenceSystem.Wgs84` odpowiada CRS przeglądarki i czy `Dataset.Create` zakończyło się sukcesem. |
| **M values ignored** | `MScale` ustawiony na 0 lub zbyt niski. | Ustaw rozsądną wartość `MScale` (np. `1e4`), aby przechowywać wartości miary. |

## Najczęściej zadawane pytania

**P:** Czy mogę używać Aspose.GIS dla .NET z innymi formatami plików GIS?  
**O:** Tak, Aspose.GIS obsługuje Shapefile, GeoJSON, KML i wiele innych formatów.

**P:** Czy Aspose.GIS dla .NET jest kompatybilny z .NET Core?  
**O:** Zdecydowanie. Biblioteka działa z .NET Framework, .NET Core oraz .NET 5/6+.

**P:** Czy mogę wykonywać operacje przestrzenne, takie jak buforowanie lub przecięcie?  
**O:** Tak, API zawiera metody do buforowania, przecięcia i obliczania odległości.

**P:** Czy Aspose.GIS zapewnia możliwości transformacji współrzędnych?  
**O:** Tak, możesz przekształcać geometrie pomiędzy różnymi układami odniesienia przestrzennego przy użyciu wbudowanych narzędzi reprojekcji.

**P:** Czy dostępna jest wersja próbna?  
**O:** Tak, możesz pobrać darmową wersję próbną ze [strony internetowej](https://releases.aspose.com/gis/net/).

**Ostatnia aktualizacja:** 2025-12-28  
**Testowano z:** Aspose.GIS 24.11 dla .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}