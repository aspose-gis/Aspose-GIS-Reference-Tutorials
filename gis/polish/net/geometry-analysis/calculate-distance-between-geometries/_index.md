---
date: 2025-12-02
description: Dowiedz się, jak obliczać odległość między geometriami przy użyciu Aspose.GIS
  dla .NET. Ten przewodnik krok po kroku pokazuje, jak korzystać z Aspose.GIS, uzyskać
  odległość do geometrii oraz zintegrować obliczenia odległości w swoich aplikacjach.
linktitle: How to Calculate Distance Between Geometries
second_title: Aspose.GIS .NET API
title: Jak obliczyć odległość między geometriami przy użyciu Aspose.GIS
url: /pl/net/geometry-analysis/calculate-distance-between-geometries/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak obliczyć odległość między geometriami przy użyciu Aspose.GIS

## Wprowadzenie
Jeśli kiedykolwiek potrzebowałeś dowiedzieć się **jak obliczyć odległość** między dwoma obiektami przestrzennymi — niezależnie od tego, czy jest to sieć dróg, strefy dostaw, czy elementy środowiskowe — ten przewodnik jest dla Ciebie. W .NET Aspose.GIS sprawia, że obliczenia odległości są proste, dokładne i wydajne. Przeprowadzimy Cię przez realistyczny przykład, który pokazuje **jak używać Aspose.GIS**, tworzyć proste geometrie i wywołać metodę **GetDistanceTo**, aby uzyskać odległość między nimi.

## Szybkie odpowiedzi
- **Co oznacza „obliczanie odległości” w GIS?** Zwraca najkrótszą (euklidesową) odległość między dwiema geometriami.  
- **Która klasa Aspose.GIS zapewnia to obliczenie?** `Geometry.GetDistanceTo(Geometry other)`.  
- **Czy potrzebna jest licencja do programowania?** Darmowa wersja próbna wystarczy do testów; licencja jest wymagana w środowisku produkcyjnym.  
- **Czy mogę obliczać odległość dla geometrii 3‑D?** Tak, Aspose.GIS obsługuje obliczenia 2‑D i 3‑D.  
- **Jakie wersje .NET są wspierane?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.

## Co to jest obliczanie odległości w programowaniu geoprzestrzennym?
Obliczanie odległości mierzy najkrótszą linię łączącą dwie geometrie. Jest to podstawowa operacja przy analizie bliskości, wyznaczaniu tras, grupowaniu i indeksowaniu przestrzennym.

## Dlaczego warto używać Aspose.GIS do obliczania odległości?
- **Wysoka precyzja** – używa arytmetyki podwójnej precyzji.  
- **Zero zależności** – nie wymaga natywnych bibliotek GIS.  
- **Cross‑platform** – działa na Windows, Linux i macOS z .NET Core/5+.  
- **Bogaty model geometrii** – obsługuje punkty, linie, wielokąty i wielogometrie od razu po instalacji.

## Wymagania wstępne
- **Aspose.GIS for .NET** zainstalowany (pobierz ze [strony wydań Aspose.GIS for .NET](https://releases.aspose.com/gis/net/)).  
- Podstawowa znajomość C# i struktury projektu .NET.  
- Środowisko programistyczne, takie jak Visual Studio 2022 lub VS Code.

## Importowanie przestrzeni nazw
Zanim zaczniesz korzystać z Aspose.GIS, dodaj wymagane przestrzenie nazw do swojego pliku C#:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Krok 1: Utwórz geometrię wielokąta
```csharp
var polygon = new Polygon();
```
Zaczynamy od pustego wielokąta, który później będzie reprezentował obszar prostokątny.

### Krok 2: Zdefiniuj zewnętrzny pierścień wielokąta
```csharp
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 1),
    new Point(1, 1),
    new Point(1, 0),
    new Point(0, 0),
});
```
Zewnętrzny pierścień to zamknięta pętla punktów definiująca granicę wielokąta. W tym przykładzie tworzymy kwadrat 1 × 1.

### Krok 3: Utwórz geometrię LineString
```csharp
var line = new LineString();
```
`LineString` to seria połączonych odcinków liniowych. Użyjemy go do reprezentacji drogi lub ścieżki.

### Krok 4: Dodaj punkty do LineString
```csharp
line.AddPoint(2, 0);
line.AddPoint(1, 3);
```
Te dwa punkty nadają linii pochyły kształt, który nie przecina wielokąta, co czyni obliczenie odległości interesującym.

### Krok 5: Oblicz odległość
```csharp
double distance = polygon.GetDistanceTo(line);
```
Tutaj **pobieramy odległość do geometrii** wywołując `GetDistanceTo`. Aspose.GIS oblicza najkrótszą odległość między krawędzią wielokąta a linią.

### Krok 6: Wyświetl wynik
```csharp
Console.WriteLine(distance.ToString("F")); // 0.63
```
Wynik jest wypisywany z dwoma miejscami po przecinku (`0.63`). Wartość ta reprezentuje minimalną odległość euklidesową między kwadratem a linią.

## Typowe przypadki użycia
- **Logistyka:** Znajdź najbliższy depot do trasy dostawy.  
- **Monitorowanie środowiska:** Zmierz, jak daleko plama zanieczyszczenia znajduje się od obszaru chronionego.  
- **Planowanie urbanistyczne:** Określ odległość między proponowaną infrastrukturą a istniejącymi punktami orientacyjnymi.

## Rozwiązywanie problemów i wskazówki
- **System współrzędnych ma znaczenie:** Upewnij się, że obie geometrie używają tego samego CRS (systemu odniesienia współrzędnych) przed obliczeniem odległości.  
- **Wydajność:** Przy dużych zbiorach danych rozważ indeksowanie przestrzenne (R‑tree), aby uniknąć porównań O(N²).  
- **Precyzja:** Jeśli potrzebujesz odległości geodezyjnych (wielkiego koła), najpierw przekształć współrzędne do odpowiedniej projekcji.

## FAQ's
### Czy Aspose.GIS for .NET jest kompatybilny ze wszystkimi frameworkami .NET?
Tak, Aspose.GIS for .NET jest kompatybilny z .NET Framework 4.6 i wyższymi.

### Czy mogę używać Aspose.GIS for .NET do wykonywania złożonych analiz przestrzennych?
Oczywiście! Aspose.GIS for .NET oferuje szeroki zakres funkcjonalności do zaawansowanych zadań analizy przestrzennej.

### Czy Aspose.GIS for .NET obsługuje zarówno geometrie 2D, jak i 3D?
Tak, możesz pracować zarówno z geometriami 2D, jak i 3D przy użyciu Aspose.GIS for .NET.

### Czy mogę integrować Aspose.GIS for .NET z innymi bibliotekami GIS?
Aspose.GIS for .NET zapewnia interoperacyjność z innymi bibliotekami GIS, umożliwiając wykorzystanie dodatkowych funkcjonalności.

### Czy dostępne jest wsparcie techniczne dla użytkowników Aspose.GIS for .NET?
Tak, użytkownicy Aspose.GIS for .NET mogą uzyskać wsparcie techniczne poprzez [fora Aspose](https://forum.aspose.com/c/gis/33).

## Frequently Asked Questions

**Q: Jak dokładna jest odległość zwracana przez `GetDistanceTo`?**  
A: Metoda używa arytmetyki podwójnej precyzji i jest zgodna ze Specyfikacją OGC Simple Features, zapewniając dokładność poniżej metra dla typowych współrzędnych płaskich.

**Q: Czy mogę obliczyć odległość między `Point` a `Polygon`?**  
A: Tak — wystarczy wywołać `point.GetDistanceTo(polygon)` (lub odwrotnie), a Aspose.GIS zwróci najkrótszą odległość od punktu do krawędzi wielokąta.

**Q: Czy API obsługuje masowe obliczenia odległości?**  
A: Chociaż nie ma jednej metody batch, możesz iterować po kolekcjach geometrii i wielokrotnie używać tego samego wywołania `GetDistanceTo` w sposób efektywny.

**Q: Co się stanie, jeśli geometrie się przecinają?**  
A: Metoda zwróci `0.0`, ponieważ najkrótsza odległość między przecinającymi się geometriami wynosi zero.

**Q: Czy istnieje sposób, aby uzyskać najbliższe punkty na każdej geometrii?**  
A: Tak — użyj `Geometry.GetNearestPoints(Geometry other)`, który zwraca krotkę zawierającą najbliższe punkty na obu geometriach.

## Zakończenie
Obliczanie odległości między geometriami jest podstawową operacją w każdej aplikacji .NET z obsługą GIS. Postępując zgodnie z powyższymi krokami, teraz wiesz **jak obliczyć odległość** przy użyciu Aspose.GIS, **jak używać Aspose** do tworzenia i manipulacji geometriami oraz **jak pobrać odległość do geometrii** jednym wywołaniem metody. Eksperymentuj z różnymi kształtami, systemami współrzędnych i większymi zestawami danych, aby zobaczyć, jak ta funkcjonalność może napędzać Twój kolejny projekt analizy przestrzennej.

---

**Ostatnia aktualizacja:** 2025-12-02  
**Testowano z:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}