---
date: 2026-04-24
description: Dowiedz się, jak utworzyć bazę danych plików geograficznych i ustawić
  siatkę precyzji dla warstwy File GDB przy użyciu Aspose.GIS dla .NET, w tym dodawanie
  obiektów do warstwy oraz weryfikację zakresu współrzędnych.
keywords:
- create file geodatabase
- handle out of range
- add features layer
- configure coordinate grid
- validate coordinate range
linktitle: Zdefiniuj siatkę precyzji dla warstwy File GDB
second_title: Aspose.GIS .NET API
title: Utwórz plikową bazę danych geograficznych i ustaw siatkę dla warstwy GDB (Aspose.GIS)
url: /pl/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak ustawić siatkę dla warstwy File GDB w Aspose.GIS

## Wprowadzenie
W tym samouczku **utworzysz obiekty bazy plikowej geodatabase** i dowiesz się, jak **ustawić siatkę** dla warstwy File Geodatabase (GDB) przy użyciu Aspose.GIS dla .NET. Definiowanie siatki precyzji pozwala **zweryfikować zakres współrzędnych**, zapobiega błędom poza zakresem i gwarantuje, że każda operacja **dodawania obiektów do warstwy** zapisuje dane dokładnie. Przejdziemy przez każdy krok, wyjaśnimy, dlaczego każde ustawienie ma znaczenie, i pokażemy, jak **radzić sobie z sytuacjami poza zakresem** w elegancki sposób.

## Szybkie odpowiedzi
- **Co oznacza „ustaw siatkę”?** Definiuje precyzję współrzędnych i prawidłowy zakres dla warstwy GIS.  
- **Dlaczego używać siatki precyzji?** Chroni dane przed nieprawidłowymi współrzędnymi i zwiększa efektywność przechowywania.  
- **Która biblioteka udostępnia tę funkcję?** Aspose.GIS dla .NET.  
- **Czy potrzebna jest licencja?** Dostępna jest wersja próbna; licencja komercyjna jest wymagana w środowisku produkcyjnym.  
- **Czy mogę używać tego z .NET Core?** Tak, Aspose.GIS obsługuje .NET Framework i .NET Core.

## Co to jest siatka precyzji i dlaczego ją ustawiać?
Siatka precyzji to zestaw parametrów (pochodna, skala itp.), które informują silnik GIS, jak zaokrąglać i przechowywać wartości współrzędnych. Konfigurując siatkę, **automatycznie weryfikujesz zakres współrzędnych**, a każda próba wstawienia punktu poza siatką spowoduje wyrzucenie wyjątku — co pomaga **radzić sobie z sytuacjami poza zakresem** już na etapie rozwoju.

## Dlaczego tworzyć bazę plikową geodatabase z siatką precyzji?
Utworzenie bazy plikowej geodatabase zapewnia przenośny, wysokowydajny kontener dla danych wektorowych. Dodanie siatki precyzji w momencie tworzenia zapewnia:

- **Spójną jakość danych** – każdy obiekt zachowuje tę samą precyzję liczbową.  
- **Szybsze indeksowanie** – silnik może przechowywać współrzędne bardziej efektywnie.  
- **Wczesne wykrywanie błędów** – współrzędne poza zakresem są wykrywane, zanim uszkodzą zestaw danych.

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz zainstalowane:

1. **Visual Studio** – dowolna aktualna wersja (Community, Professional lub Enterprise).  
2. **Aspose.GIS dla .NET** – pobierz ją ze [strony internetowej](https://releases.aspose.com/gis/net/).  
3. **Podstawowa znajomość C#** – powinieneś być pewny w tworzeniu projektów konsolowych .NET.

## Typowe przypadki użycia
- **Zbieranie danych w terenie**, gdzie urządzenia GPS mogą generować współrzędne nieco poza zamierzonym zakresem.  
- **Migracja danych** z systemów legacy, które używały innych precyzji współrzędnych.  
- **Zautomatyzowane potoki ETL**, które muszą wymusić integralność przestrzenną przed załadowaniem danych do bazy GIS.

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

## Jak skonfigurować siatkę współrzędnych w warstwie File GDB
Poniżej znajdziesz przewodnik krok po kroku, który pokazuje dokładnie, jak skonfigurować siatkę, utworzyć warstwę i bezpiecznie **dodawać obiekty do warstwy**.

### Krok 1: Utwórz zestaw danych
Zaczynamy od utworzenia nowego zestawu danych File Geodatabase. To miejsce, w którym będzie znajdować się warstwa.

```csharp
var path = "Your Document Directory" + "PrecisionGrid_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

### Krok 2: Zdefiniuj opcje siatki precyzji
Tutaj określamy parametry siatki. Dostosuj pochodne i skale, aby pasowały do układu współrzędnych Twojego projektu.

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

*Flaga `EnsureValidCoordinatesRange = true` instruuje Aspose.GIS, aby **weryfikował zakres współrzędnych** dla każdego dodawanego obiektu.*

### Krok 3: Utwórz warstwę z siatką
Teraz tworzymy nową warstwę wewnątrz zestawu danych, stosując właśnie zdefiniowane opcje siatki. Użyjemy układu odniesienia przestrzennego WGS84.

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
```

### Krok 4: Dodaj obiekty do warstwy
Tworzymy dwa obiekty punktowe. Pierwszy punkt znajduje się wewnątrz siatki, natomiast drugi celowo leży poza nią, aby zademonstrować **jak radzić sobie z błędami poza zakresem**.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(10, 20) { M = 10.1282 };
layer.Add(feature);
feature = layer.ConstructFeature();
feature.Geometry = new Point(-410, 0) { M = 20.2343 };
```

### Krok 5: Obsłuż wyjątki przy dodawaniu obiektów poza zakresem
Próba dodania drugiego obiektu spowoduje wyrzucenie wyjątku, ponieważ jego współrzędna X (`-410`) znajduje się poza zdefiniowaną siatką. Przechwytujemy wyjątek i wyświetlamy czytelną wiadomość.

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

### Krok 6: Sprzątanie
Instrukcje `using` automatycznie zamykają i zwalniają zasoby zestawu danych oraz warstwy, zapewniając zwolnienie wszystkich zasobów.

## Typowe problemy i rozwiązania
| Problem | Dlaczego się pojawia | Rozwiązanie |
|-------|----------------|-----|
| **Exception: “X value … is out of valid range.”** | Współrzędne znajdują się poza siatką precyzji. | Dostosuj `XOrigin`, `YOrigin` lub `XYScale`, aby objąć Twoje dane, lub upewnij się, że dane wejściowe mieszczą się w określonym zakresie. |
| **Features not appearing in GIS viewer** | Warstwa nie została zapisana lub użyto niewłaściwego układu odniesienia. | Sprawdź, czy `SpatialReferenceSystem.Wgs84` odpowiada układowi odniesienia przeglądarki oraz czy `Dataset.Create` zakończyło się sukcesem. |
| **M values ignored** | `MScale` ustawiony na 0 lub zbyt niski. | Ustaw rozsądny `MScale` (np. `1e4`), aby przechowywać wartości miar. |

## Wskazówki dotyczące rozwiązywania problemów
- **Sprawdź dokładnie rozmiary siatki** przed wczytywaniem dużych partii danych; mała literówka w `XOrigin` może spowodować odrzucenie wielu wierszy.  
- **Zaloguj komunikat wyjątku** (jak pokazano w bloku try‑catch) do pliku podczas przetwarzania automatycznych importów; ułatwia to wykrywanie wzorców w danych poza zakresem.  
- **Używaj `EnsureValidCoordinatesRange = false` tylko dla zaufanych źródeł danych** – wyłączenie tej opcji pomija walidację i może prowadzić do uszkodzonych geometrii.

## Najczęściej zadawane pytania

**P: Czy mogę używać Aspose.GIS dla .NET z innymi formatami plików GIS?**  
O: Tak, Aspose.GIS obsługuje Shapefile, GeoJSON, KML i wiele innych formatów.

**P: Czy Aspose.GIS dla .NET jest kompatybilny z .NET Core?**  
O: Absolutnie. Biblioteka działa z .NET Framework, .NET Core oraz .NET 5/6+.

**P: Czy mogę wykonywać operacje przestrzenne, takie jak buforowanie lub przecięcie?**  
O: Tak, API zawiera metody do buforowania, przecięcia i obliczania odległości.

**P: Czy Aspose.GIS zapewnia możliwości transformacji współrzędnych?**  
O: Tak, możesz przekształcać geometrie między różnymi układami odniesienia przy użyciu wbudowanych narzędzi reprojekcji.

**P: Czy dostępna jest wersja próbna?**  
O: Tak, możesz pobrać darmową wersję próbną ze [strony internetowej](https://releases.aspose.com/gis/net/).

---

**Last Updated:** 2026-04-24  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}