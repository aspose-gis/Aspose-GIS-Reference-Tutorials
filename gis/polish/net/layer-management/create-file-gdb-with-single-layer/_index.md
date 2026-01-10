---
date: 2026-01-10
description: Dowiedz się, jak utworzyć warstwę wektorową w bazie danych plikowych
  (File Geodatabase) przy użyciu Aspose.GIS dla .NET. Zarządzaj danymi geoprzestrzennymi
  z odniesieniem przestrzennym WGS84 i opcjami pliku gdb.
linktitle: Create File GDB with Single Layer
second_title: Aspose.GIS .NET API
title: Tworzenie warstwy wektorowej w pliku GDB – samouczek Aspose.GIS .NET
url: /pl/net/layer-management/create-file-gdb-with-single-layer/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz warstwę wektorową w File GDB

## Wprowadzenie
Jeśli potrzebujesz **create vector layer** wewnątrz File Geodatabase (GDB) i chcesz efektywnie zarządzać danymi geoprzestrzennymi, Aspose.GIS for .NET zapewnia czyste podejście code‑first. W tym przewodniku krok po kroku pokażemy, jak zapisać cechę linii, skonfigurować opcje file gdb i pracować z odniesieniem przestrzennym WGS84 — wszystko w kilku liniach C#. Po zakończeniu będziesz mógł zliczyć cechy w warstwie i zintegrować powstały GDB z dowolnym przepływem pracy .NET związanym z mapowaniem lub analizą.

## Szybkie odpowiedzi
- **What does “create vector layer” mean?** Oznacza to dodanie nowego zestawu danych wektorowych (punktów, linii lub wielokątów) do pliku geobazy.  
- **Which library should I use?** Aspose.GIS for .NET zapewnia pełne wsparcie dla tworzenia i edycji File GDB.  
- **Do I need a license for development?** Darmowa wersja próbna działa do testów; licencja komercyjna jest wymagana w produkcji.  
- **Can I set the spatial reference?** Tak – użyj `SpatialReferenceSystem.Wgs84` dla powszechnego datumu WGS84.  
- **How many lines of code?** Mniej niż 30 linii kodu, aby utworzyć GDB, dodać cechę linii i odczytać liczbę cech.

## Czym jest operacja „create vector layer”?
Tworzenie warstwy wektorowej oznacza zdefiniowanie nowej tabeli w geobazie, która przechowuje obiekty geometryczne (punkty, linie, wielokąty) wraz z ich atrybutami. Ta operacja jest podstawą każdej aplikacji opartej na GIS, która musi **manage geospatial data**.

## Dlaczego używać Aspose.GIS do tworzenia warstwy wektorowej?
- **Zero external dependencies** – API działa od razu na .NET Framework, .NET Core oraz .NET 5/6.  
- **Full support for File GDB** – możesz skonfigurować `FileGdbOptions`, aby kontrolować kompresję, indeksowanie przestrzenne i inne.  
- **Built‑in spatial reference handling** – po prostu przekaż `SpatialReferenceSystem.Wgs84`, aby pracować w globalnym układzie współrzędnych.  
- **Straightforward API** – zapisz cechę linii, dodaj ją do warstwy i pobierz liczbę cech przy użyciu kilku wywołań metod.

## Prerequisites
Zanim rozpoczniesz, upewnij się, że masz:

1. **Aspose.GIS for .NET** – pobierz go ze [strony pobierania Aspose.GIS for .NET](https://releases.aspose.com/gis/net/).  
2. **A .NET development environment** – Visual Studio, Rider lub `dotnet` CLI.  
3. **A folder** gdzie zostanie utworzony File GDB (nazwijmy go *Your Document Directory*).

## Importowanie przestrzeni nazw
Dodaj wymagane instrukcje `using` na początku swojego pliku C#:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```

## Krok 1: Skonfiguruj swój katalog dokumentów
```csharp
string dataDir = "Your Document Directory";
```
Zastąp `"Your Document Directory"` bezwzględną ścieżką, w której ma znajdować się File GDB.

## Krok 2: Utwórz File Geodatabase z jedną warstwą
```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```
Ten fragment **creates a vector layer** przy użyciu `FileGdbOptions`, zapisuje prostą cechę linii i przechowuje ją w File GDB, który używa **spatial reference WGS84**.

## Krok 3: Otwórz File Geodatabase i pobierz informacje o warstwie
```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Output: Features count: 1
}
```
Tutaj **count features layer** otwierając zestaw danych i wypisując liczbę cech – w tym przypadku `1`.

## Common Issues and Solutions
| Problem | Powód | Rozwiązanie |
|---------|-------|-------------|
| **`File not found`** | Niepoprawna zmienna `path` | Sprawdź, czy `dataDir` wskazuje istniejący folder oraz czy `path` łączy go z nazwą pliku, np., `Path.Combine(dataDir, "MyData.gdb")`. |
| **`Unsupported geometry`** | Użycie typu geometrii niedozwolonego w File GDB | Używaj `Point`, `LineString` lub `Polygon` dla podstawowych warstw. |
| **`License not set`** | Uruchamianie bez ważnej licencji w środowisku produkcyjnym | Zarejestruj licencję przy użyciu `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Najczęściej zadawane pytania
### Can I use Aspose.GIS for .NET in my existing .NET projects?
Tak, Aspose.GIS for .NET może być płynnie zintegrowany z istniejącymi projektami .NET.

### Is there a trial version available for Aspose.GIS for .NET?
Tak, możesz zapoznać się z funkcjami Aspose.GIS for .NET, pobierając [bezpłatną wersję próbną](https://releases.aspose.com/).

### Where can I find detailed documentation for Aspose.GIS for .NET?
Zapoznaj się z [dokumentacją](https://reference.aspose.com/gis/net/), aby uzyskać pełne informacje o Aspose.GIS for .NET.

### How can I get support for Aspose.GIS for .NET?
Odwiedź [forum Aspose.GIS](https://forum.aspose.com/c/gis/33), aby uzyskać wsparcie społeczności i pomoc.

### Are temporary licenses available for Aspose.GIS for .NET?
Tak, możesz uzyskać [tymczasową licencję](https://purchase.aspose.com/temporary-license/) dla Aspose.GIS for .NET.

---

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}