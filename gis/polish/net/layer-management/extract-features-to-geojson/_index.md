---
date: 2026-01-13
description: Dowiedz się, jak konwertować plik shapefile na geojson przy użyciu Aspose.GIS
  dla .NET. Poradnik obejmuje także kopiowanie atrybutów między warstwami oraz generowanie
  pliku geojson w C#.
linktitle: Extract Features to GeoJSON
second_title: Aspose.GIS .NET API
title: Jak przekonwertować plik Shapefile na GeoJSON przy użyciu Aspose.GIS dla .NET
url: /pl/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konwertowanie pliku Shapefile do GeoJSON przy użyciu Aspose.GIS dla .NET

## Wprowadzenie
W tym obszernej, krok po kroku tutorialu nauczysz się **jak konwertować shapefile do geojson** przy użyciu potężnej biblioteki Aspose.GIS dla .NET. Niezależnie od tego, czy tworzysz usługę mapowania w sieci, przygotowujesz dane dla mobilnej aplikacji GIS, czy po prostu potrzebujesz wymienić dane między formatami, ten przewodnik pokaże Ci dokładnie, co zrobić, dlaczego każdy krok ma znaczenie i jak unikać typowych pułapek.

## Szybkie odpowiedzi
- **Co obejmuje ten tutorial?** Konwersja pliku Shapefile do pliku GeoJSON, kopiowanie atrybutów między warstwami oraz generowanie wyniku w C#.
- **Jakiej biblioteki wymaga?** Aspose.GIS dla .NET.
- **Czy potrzebna jest licencja?** Do produkcji wymagana jest tymczasowa lub pełna licencja; darmowa wersja próbna działa w celach oceny.
- **Jak długo trwa implementacja?** Około 10‑15 minut dla podstawowej konwersji.
- **Czy mogę uruchomić to na .NET Core/.NET 6?** Tak – kod działa na wszystkich obsługiwanych wersjach .NET.

## Wymagania wstępne
Zanim przejdziemy dalej, upewnij się, że masz następujące elementy:

- Aspose.GIS for .NET: Upewnij się, że masz zainstalowaną bibliotekę. Jeśli nie, możesz ją pobrać ze [strony Aspose.GIS for .NET](https://releases.aspose.com/gis/net/).
- Dane Shapefile: Przygotuj plik Shapefile jako wejście. Jeśli potrzebujesz przykładowych danych, znajdziesz je w [dokumentacji Aspose.GIS](https://reference.aspose.com/gis/net/).
- Środowisko .NET: Skonfiguruj środowisko .NET, aby uruchomić dostarczony kod.
- Katalog dokumentów: Zdefiniuj ścieżkę do swojego katalogu dokumentów w fragmencie kodu.

Teraz, gdy masz wszystko gotowe, rozpocznijmy konwersję shapefile do geojson!

## Co to jest „convert shapefile to geojson”?
Konwersja pliku Shapefile do GeoJSON oznacza odczytanie cech wektorowych z klasycznego formatu ESRI Shapefile i zapisanie ich jako nowoczesny, przyjazny sieciom dokument GeoJSON. GeoJSON jest szeroko stosowany w bibliotekach mapowania JavaScript (Leaflet, Mapbox GL) oraz w API, co sprawia, że konwersja jest częstym zadaniem w rozwoju GIS.

## Dlaczego używać Aspose.GIS do tej konwersji?
Aspose.GIS ukrywa niskopoziomowe szczegóły formatów plików, umożliwia łatwe kopiowanie tabel atrybutów i zapewnia czyste, obiektowo‑zorientowane API działające na .NET Framework, .NET Core oraz .NET 5/6. Oznacza to, że możesz skupić się na logice biznesowej zamiast parsować pliki binarne.

## Importowanie przestrzeni nazw
Najpierw dołącz niezbędne przestrzenie nazw w swoim kodzie:

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Te przestrzenie nazw są niezbędne do pracy z funkcjami Aspose.GIS.

## Jak konwertować Shapefile do GeoJSON
Poniżej znajduje się pełny przepływ pracy podzielony na przejrzyste kroki. Każdy krok zawiera krótkie wyjaśnienie oraz dokładny fragment kodu, który należy skopiować do projektu.

### Krok 1: Otwórz wejściowy Shapefile
```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```
Otwórz wejściowy Shapefile przy użyciu metody `VectorLayer.Open`. Daje to kolekcję iterowalną obiektów `Feature`.

### Krok 2: Utwórz wyjściowy GeoJSON
```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```
Utwórz plik wyjściowy metodą `VectorLayer.Create`, określając sterownik `Drivers.GeoJson`.

### Krok 3: Kopiuj atrybuty między warstwami
```csharp
outputLayer.CopyAttributes(inputLayer);
```
Ta pojedyncza linia kopiuje schemat atrybutów (nazwy pól, typy) ze źródłowego Shapefile do nowej warstwy GeoJSON — dokładnie to, co opisuje drugorzędne słowo kluczowe *copy attributes between layers*.

### Krok 4: Przetwarzaj cechy
```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```
Iteruj przez każdą cechę w Shapefile, aby móc zastosować dowolną logikę przed zapisaniem jej.

### Krok 5: Filtruj cechy według daty
```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```
W tym przykładzie pomijamy rekordy, w których pole `dob` (data urodzenia) jest brakujące lub wcześniejsze niż 1 sty 1982. Śmiało dostosuj filtr do własnych wymagań dotyczących danych.

### Krok 6: Utwórz nową cechę (C# generowanie pliku GeoJSON)
```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```
Tutaj tworzymy nowy `Feature` dla warstwy GeoJSON, kopiujemy geometrię i wartości atrybutów oraz dodajemy go do wyjścia. To jest sedno *c# generate geojson file*.

Gratulacje! Pomyślnie **przekonwertowałeś shapefile do geojson** i po drodze nauczyłeś się kopiować atrybuty między warstwami.

## Typowe problemy i rozwiązania
| Problem | Dlaczego się pojawia | Rozwiązanie |
|---------|----------------------|-------------|
| Plik wyjściowy jest pusty | `CopyAttributes` wywołane po zamknięciu warstwy wyjściowej | Upewnij się, że blok `using` dla `outputLayer` pozostaje otwarty aż do momentu dodania wszystkich cech. |
| Filtr dat usuwa wszystkie rekordy | Nieprawidłowa nazwa pola lub nieoczekiwany format daty | Sprawdź nazwę atrybutu (`dob`) i użyj `GetValue<string>`, jeśli daty są przechowywane jako ciągi znaków. |
| Wyjątek licencji | Uruchamianie bez ważnej licencji Aspose.GIS w środowisku produkcyjnym | Zastosuj tymczasową lub pełną licencję, jak opisano w dokumentacji Aspose. |

## Najczęściej zadawane pytania
**Q: Gdzie mogę znaleźć więcej dokumentacji?**  
**A:** Odwiedź [dokumentację Aspose.GIS](https://reference.aspose.com/gis/net/) dla szczegółowych informacji.

**Q: Jak mogę uzyskać tymczasową licencję?**  
**A:** Możesz uzyskać tymczasową licencję [tutaj](https://purchase.aspose.com/temporary-license/).

**Q: Gdzie mogę szukać wsparcia?**  
**A:** Dołącz do [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) dla wsparcia społeczności i dyskusji.

**Q: Czy dostępna jest darmowa wersja próbna?**  
**A:** Tak, darmową wersję próbną znajdziesz [tutaj](https://releases.aspose.com/).

**Q: Gdzie mogę kupić Aspose.GIS dla .NET?**  
**A:** Produkt możesz kupić [tutaj](https://purchase.aspose.com/buy).

## Podsumowanie
W tym tutorialu omówiliśmy kompletny proces **convert shapefile to geojson** przy użyciu Aspose.GIS dla .NET, pokazaliśmy, jak kopiować atrybuty między warstwami oraz przedstawiliśmy czysty sposób na *c# generate geojson file*. Eksperymentuj z różnymi filtrami, większymi zestawami danych lub dodatkowymi przekształceniami geometrii, aby w pełni wykorzystać możliwości biblioteki.

---
**Ostatnia aktualizacja:** 2026-01-13  
**Testowano z:** Aspose.GIS for .NET (latest stable release)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}