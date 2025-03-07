---
title: Utwórz nowy zbiór danych pliku GDB
linktitle: Utwórz nowy zbiór danych pliku GDB
second_title: Aspose.GIS .NET API
description: Poznaj Aspose.GIS dla .NET, aby bez wysiłku tworzyć zestawy danych GIS i zarządzać nimi. Pobierz teraz, aby zapewnić płynny rozwój geoprzestrzenny. #Aspose #GIS
weight: 10
url: /pl/net/layer-management/create-new-file-gdb-dataset/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz nowy zbiór danych pliku GDB

## Wstęp
dziedzinie rozwoju geoprzestrzennego Aspose.GIS dla .NET wyróżnia się jako potężny zestaw narzędzi do zarządzania danymi Systemu Informacji Geograficznej (GIS) i manipulowania nimi. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz swoją przygodę z GIS, ten samouczek przeprowadzi Cię przez proces tworzenia nowego zbioru danych geobazy plików (GDB) przy użyciu Aspose.GIS dla .NET.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
-  Aspose.GIS dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.GIS dla .NET. Można go pobrać z[Strona pobierania Aspose.GIS dla .NET](https://releases.aspose.com/gis/net/).
- Środowisko programistyczne: Skonfiguruj środowisko programistyczne za pomocą kompatybilnego środowiska IDE, takiego jak Visual Studio, i miej podstawową wiedzę o programowaniu .NET.
- Katalog dokumentów: Zastąp „Twój katalog dokumentów” we fragmencie kodu odpowiednią ścieżką, w której chcesz przechowywać zbiór danych GDB.
- Znajomość języka C#: W tym samouczku założono, że znasz język programowania C#.
## Importuj przestrzenie nazw
pierwszych krokach zaimportuj niezbędne przestrzenie nazw, aby wykorzystać funkcjonalność Aspose.GIS w aplikacji .NET:
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
## Krok 1: Utwórz nowy zbiór danych GDB pliku
```csharp
string dataDir = "Your Document Directory";
using (var dataset = Dataset.Create(dataDir, Drivers.FileGdb))
{
    Console.WriteLine(dataset.LayersCount); // Wyjście: 0
    // Kontynuuj kolejne kroki...
}
```
 Objaśnienie: W tym kroku tworzymy nowy zbiór danych GDB przy użyciu`Dataset.Create` metoda. Podajemy ścieżkę i sterownik (FileGdb), aby utworzyć Geobazę Plikową. Dane wyjściowe konsoli wyświetlają początkową liczbę warstw, która w tym momencie wynosi zero.
## Krok 2: Utwórz i wypełnij warstwę_1
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
Objaśnienie: Ten krok polega na utworzeniu warstwy o nazwie „warstwa_1” w zestawie danych. Definiuje atrybut o nazwie „wartość” typu całkowitego i wypełnia warstwę dziesięcioma obiektami, z których każdy ma geometrię punktową.
## Krok 3: Utwórz i wypełnij warstwę_2
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
Objaśnienie: Tutaj tworzymy drugą warstwę o nazwie „warstwa_2” i dodajemy pojedynczy obiekt z geometrią ciągu linii.
## Krok 4: Sprawdź zaktualizowaną liczbę warstw
```csharp
Console.WriteLine(dataset.LayersCount); // Wyjście: 2
```
Wyjaśnienie: Na koniec sprawdzamy zaktualizowaną liczbę warstw po dodaniu dwóch warstw. W takim przypadku wynik powinien wynosić 2.
## Wniosek
Gratulacje! Pomyślnie utworzyłeś nowy zbiór danych File GDB i wypełniłeś go warstwami przy użyciu Aspose.GIS dla .NET. Ten samouczek zapewnia podstawową wiedzę na temat pracy z danymi geoprzestrzennymi w środowisku .NET.
## Często Zadawane Pytania
### P: Czy mogę używać Aspose.GIS dla .NET z innymi bibliotekami GIS?
Aspose.GIS dla .NET to samodzielny zestaw narzędzi; można ją jednak zintegrować z innymi bibliotekami .NET w celu zwiększenia funkcjonalności.
### P: Czy istnieje forum społecznościowe dotyczące wsparcia Aspose.GIS?
 Tak, możesz znaleźć wsparcie i dyskusje na stronie[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33).
### P: Jak mogę uzyskać tymczasową licencję na Aspose.GIS?
 Odwiedzić[Licencja tymczasowa](https://purchase.aspose.com/temporary-license/) stronę zawierającą informacje dotyczące uzyskania licencji tymczasowej.
### P: Czy dostępne są dodatkowe przykłady i dokumentacja?
 Poznaj[Dokumentacja Aspose.GIS](https://reference.aspose.com/gis/net/) aby uzyskać więcej przykładów i szczegółowych informacji.
### P: Gdzie mogę kupić Aspose.GIS dla .NET?
 Możesz kupić Aspose.GIS dla .NET na stronie[strona zakupu](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
