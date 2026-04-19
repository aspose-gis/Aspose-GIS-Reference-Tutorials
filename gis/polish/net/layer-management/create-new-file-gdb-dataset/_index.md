---
date: 2026-01-10
description: Dowiedz się, jak tworzyć zestawy danych .NET w plikowej bazie geodezyjnej
  przy użyciu Aspose.GIS dla .NET. Przewodnik krok po kroku, umożliwiający łatwe zarządzanie
  danymi GIS.
linktitle: Create New File GDB Dataset
second_title: Aspose.GIS .NET API
title: Utwórz zestaw danych .NET w plikowej bazie geograficznej przy użyciu Aspose.GIS
url: /pl/net/layer-management/create-new-file-gdb-dataset/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz zestaw danych File Geodatabase .NET przy użyciu Aspose.GIS

## Wprowadzenie
W tym samouczku **create file geodatabase .NET** zestawy danych zostaną utworzone od podstaw przy użyciu Aspose.GIS dla .NET. Niezależnie od tego, czy tworzysz narzędzie GIS na pulpit, usługę sieciową przechowującą dane przestrzenne, czy po prostu potrzebujesz niezawodnego sposobu na programowe generowanie File Geodatabases, ten przewodnik przeprowadzi Cię przez każdy krok z jasnymi wyjaśnieniami i praktycznym kontekstem.

## Szybkie odpowiedzi
- **Co obejmuje ten samouczek?** Tworzenie nowego File Geodatabase, dodanie dwóch warstw i weryfikacja zestawu danych przy użyciu Aspose.GIS dla .NET.  
- **Jak długo to trwa?** Około 10‑15 minut dla programisty zaznajomionego z C#.  
- **Wymagania wstępne?** Środowisko programistyczne .NET, biblioteka Aspose.GIS dla .NET oraz ścieżka do zapisywalnego folderu.  
- **Czy mogę używać tego w .NET Core / .NET 6+?** Tak – API jest w pełni kompatybilne z nowoczesnymi środowiskami .NET.  
- **Czy potrzebna jest licencja?** Wymagana jest tymczasowa lub stała licencja Aspose.GIS do użytku produkcyjnego.

## Co to jest File Geodatabase?
File Geodatabase (File GDB) to magazyn danych oparty na folderze, który przechowuje klasy obiektów GIS, zestawy danych rastrowych oraz powiązane metadane. Oferuje szybkie działanie odczytu/zapisu, obsługuje duże zestawy danych i jest szeroko stosowany w ekosystemie ArcGIS firmy Esri. Korzystając z Aspose.GIS, możesz tworzyć i manipulować tymi bazami bezpośrednio z kodu .NET, bez potrzeby zewnętrznego oprogramowania GIS.

## Dlaczego tworzyć file geodatabase .NET przy użyciu Aspose.GIS?
- **Brak zewnętrznych zależności** – biblioteka obsługuje wszystkie szczegóły formatu pliku.  
- **Cross‑platform** – działa na środowiskach .NET w Windows, Linux i macOS.  
- **Bogate wsparcie geometrii** – punkty, linie, wielokąty i inne.  
- **Pełna kontrola** – sam decydujesz o schemacie, atrybutach i odniesieniu przestrzennym.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz następujące elementy:

- Aspose.GIS for .NET zainstalowane. Możesz pobrać go ze [strony pobierania Aspose.GIS for .NET](https://releases.aspose.com/gis/net/).  
- Środowisko programistyczne, takie jak Visual Studio 2022 (lub dowolne IDE obsługujące .NET).  
- Zapisywalny folder na twoim komputerze, w którym zostanie utworzony nowy GDB – zamień `"Your Document Directory"` w kodzie na tę ścieżkę.  
- Podstawowa znajomość C# i struktury projektu .NET.

## Importowanie przestrzeni nazw
Najpierw zaimportuj przestrzenie nazw, które dają dostęp do klas Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Przewodnik krok po kroku

### Krok 1: Utwórz nowy zestaw danych File GDB
Poniższy fragment tworzy pustą File Geodatabase. To jest sedno **create file geodatabase .net**.

```csharp
string dataDir = "Your Document Directory";
using (var dataset = Dataset.Create(dataDir, Drivers.FileGdb))
{
    Console.WriteLine(dataset.LayersCount); // Output: 0
    // Continue with subsequent steps...
}
```

**Wyjaśnienie:** `Dataset.Create` inicjalizuje GDB w podanej ścieżce przy użyciu sterownika `FileGdb`. W tym momencie zestaw danych nie zawiera warstw, więc liczba warstw wynosi zero.

### Krok 2: Utwórz i wypełnij `layer_1`
Teraz dodajemy pierwszą warstwę, która przechowuje atrybuty całkowite i geometrie punktowe.

```csharp
using (var layer = dataset.CreateLayer("layer_1"))
{
    layer.Attributes.Add(new FeatureAttribute("value", AttributeDataType.Integer));
    for (int i = 0; i < 10; ++i)
    {
        var feature = layer.ConstructFeature();
        feature.SetValue("value", i);
        feature.Geometry = new Point(i, i);
        layer.Add(feature);
    }
}
```

**Wyjaśnienie:**  
- `CreateLayer` tworzy nową klasę obiektów o nazwie **layer_1**.  
- Definiowany jest atrybut całkowitoliczbowy o nazwie **value**.  
- Pętla dodaje dziesięć obiektów, każdy z unikalną liczbą całkowitą i punktem o współrzędnych *(i, i)*.

### Krok 3: Utwórz i wypełnij `layer_2`
Następnie dodajemy drugą warstwę, która demonstruje obsługę geometrii linii.

```csharp
using (var layer = dataset.CreateLayer("layer_2"))
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

**Wyjaśnienie:** To tworzy **layer_2** i wstawia pojedynczy obiekt, którego geometria to `LineString` łączący dwa punkty.

### Krok 4: Zweryfikuj zaktualizowaną liczbę warstw
Na koniec potwierdź, że obie warstwy zostały dodane pomyślnie.

```csharp
Console.WriteLine(dataset.LayersCount); // Output: 2
```

**Wyjaśnienie:** Zestaw danych raportuje teraz dwie warstwy, co potwierdza, że proces **create file geodatabase .net** zakończył się pomyślnie.

## Typowe problemy i rozwiązania
| Problem | Dlaczego się pojawia | Rozwiązanie |
|-------|----------------|-----|
| **`UnauthorizedAccessException`** when creating the dataset | Ścieżka folderu jest tylko do odczytu lub nie masz uprawnień. | Wybierz zapisywalny katalog lub uruchom Visual Studio jako administrator. |
| **`ArgumentException` for driver** | Nazwa sterownika jest błędnie napisana lub wersja biblioteki jej nie obsługuje. | Użyj dokładnie `Drivers.FileGdb` jak pokazano; upewnij się, że masz najnowszy pakiet Aspose.GIS. |
| **Features not appearing in ArcGIS** | Brak odniesienia przestrzennego lub niekompatybilna geometria. | Ustaw odniesienie przestrzenne na warstwie, jeśli jest wymagane, i upewnij się, że geometrie są prawidłowe. |

## Najczęściej zadawane pytania
### Q: Czy mogę używać Aspose.GIS for .NET z innymi bibliotekami GIS?
Aspose.GIS for .NET jest samodzielnym zestawem narzędzi; jednak możesz go integrować z innymi bibliotekami .NET w celu zwiększenia funkcjonalności.

### Q: Czy istnieje forum społecznościowe wsparcia Aspose.GIS?
Tak, wsparcie i dyskusje znajdziesz na [forum Aspose.GIS](https://forum.aspose.com/c/gis/33).

### Q: Jak mogę uzyskać tymczasową licencję dla Aspose.GIS?
Odwiedź stronę [Temporary License](https://purchase.aspose.com/temporary-license/) po informacje o uzyskaniu tymczasowej licencji.

### Q: Czy dostępne są dodatkowe przykłady i dokumentacja?
Przeglądaj [dokumentację Aspose.GIS](https://reference.aspose.com/gis/net/) po więcej przykładów i szczegółowych informacji.

### Q: Gdzie mogę kupić Aspose.GIS for .NET?
Możesz zakupić Aspose.GIS for .NET na [stronie zakupu](https://purchase.aspose.com/buy).

## Podsumowanie
Udało Ci się teraz **create file geodatabase .NET** zestawy danych, dodać dwie odrębne warstwy i zweryfikować wynik przy użyciu Aspose.GIS. Ta podstawa pozwala budować bardziej rozbudowane aplikacje GIS — dodawać kolejne warstwy, definiować złożone schematy lub integrować się z usługami sieciowymi. Zagłęb się dalej w API Aspose.GIS, aby pracować z danymi rastrowymi, zapytaniami przestrzennymi i zaawansowanymi operacjami na geometriach.

---

**Ostatnia aktualizacja:** 2026-01-10  
**Testowano z:** Aspose.GIS for .NET 24.11 (lub najnowsza)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}