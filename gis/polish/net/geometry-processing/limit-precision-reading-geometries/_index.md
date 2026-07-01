---
date: 2026-04-03
description: Dowiedz się, jak utworzyć warstwę wektorową i ograniczyć precyzję przy
  odczytywaniu geometrii przy użyciu Aspose.GIS dla .NET. Przewodnik krok po kroku
  dla optymalnego przetwarzania danych geoprzestrzennych.
keywords:
- create vector layer
- reduce shapefile size
- set precision model
linktitle: Ogranicz precyzję odczytu geometrii
second_title: Aspose.GIS .NET API
title: Utwórz warstwę wektorową, ogranicz precyzję przy użyciu Aspose.GIS dla .NET
url: /pl/net/geometry-processing/limit-precision-reading-geometries/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz warstwę wektorową, ogranicz precyzję przy użyciu Aspose.GIS dla .NET

## Wprowadzenie
Podczas pracy z danymi geoprzestrzennymi często musisz **utworzyć warstwę wektorową** i zdecydować, ile miejsc po przecinku szczegółowości współrzędnych naprawdę potrzebujesz. Ograniczenie precyzji nie tylko przyspiesza przetwarzanie, ale może także **zmniejszyć rozmiar pliku shapefile**, co sprawia, że przechowywanie i transfer są bardziej efektywne. W tym samouczku przeprowadzimy Cię przez tworzenie warstwy wektorowej, zapisywanie prostej geometrii punktu oraz odczytanie jej z powrotem przy użyciu zarówno dokładnych, jak i zaokrąglonych modeli precyzji. Na koniec zrozumiesz, jak **ustawić model precyzji** opcje dopasowane do wymagań dokładności Twojej aplikacji.

## Szybkie odpowiedzi
- **Co oznacza „ograniczenie precyzji”?** Zaokrągla wartości współrzędnych do określonej liczby miejsc po przecinku.  
- **Dlaczego najpierw tworzyć warstwę wektorową?** Warstwa wektorowa jest kontenerem przechowującym geometrie, takie jak punkty, linie i wielokąty.  
- **Jakie modele precyzji są dostępne?** `PrecisionModel.Exact` (bez zaokrągleń) oraz `PrecisionModel.Rounding(n)` (zaokrągla do *n* miejsc po przecinku).  
- **Czy potrzebna jest licencja, aby to wypróbować?** Dostępna jest darmowa wersja próbna na stronie wydań.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core oraz .NET 5/6+.

## Dlaczego ograniczyć precyzję i jak to pomaga?
- **Zwiększenie wydajności** – Mniej cyfr oznacza mniej danych do parsowania i serializacji.  
- **Mniejsze pliki** – Zaokrąglanie współrzędnych może zauważalnie zmniejszyć rozmiar pliku shapefile, szczególnie w dużych zestawach danych.  
- **Wystarczająca dokładność** – Wiele analiz GIS nie wymaga precyzji podmilimetrowej, więc zaokrąglenie do 2‑3 miejsc po przecinku jest często wystarczające.

## Wymagania wstępne
Zanim wyruszymy w tę podróż, upewnij się, że spełniasz następujące wymagania:
1. **Instalacja** – Biblioteka Aspose.GIS dla .NET powinna być zainstalowana w Twoim środowisku programistycznym. Jeśli nie, możesz ją pobrać ze [strony wydań](https://releases.aspose.com/gis/net/).
2. **Znajomość .NET** – Podstawowa wiedza o C# i frameworku .NET jest niezbędna do zrozumienia i implementacji dostarczonych przykładów kodu.
3. **Środowisko programistyczne** – Wymagane jest działające środowisko programistyczne .NET, takie jak Visual Studio.
4. **Katalog dokumentów** – Przygotuj katalog, w którym będziesz przechowywać i uzyskiwać dostęp do pliku shapefile generowanego w trakcie procesu.

## Importowanie przestrzeni nazw
Zanim zaczniemy implementować funkcjonalność ograniczania precyzji przy odczycie geometrii, upewnijmy się, że importujemy niezbędne przestrzenie nazw:
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Jak utworzyć warstwę wektorową
Pierwszym krokiem jest **utworzenie warstwy wektorowej**, która będzie przechowywać naszą geometrię. Warstwa ta zostanie zapisana jako Shapefile, aby później móc otworzyć ją z innymi ustawieniami precyzji.
```csharp
string path = "Your Document Directory" + "LimitPrecisionWhenReadingGeometries_out.shp";
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
	var feature = layer.ConstructFeature();
	feature.Geometry = new Point(1.10234, 2.09743);
	layer.Add(feature);
}
```

## Ustawianie opcji precyzji
Następnie musimy zdefiniować opcje odczytu geometrii, określając żądany model precyzji. Możemy rozpocząć od dokładnej precyzji:
```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## Odczytywanie geometrii z dokładną precyzją
Teraz otwórzmy warstwę wektorową z określonymi opcjami, aby odczytać geometrie z dokładną precyzją:
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Obcinanie precyzji
Jeśli chcemy obciąć precyzję do określonej liczby miejsc po przecinku, możemy odpowiednio dostosować model precyzji:
```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Jak ustawić model precyzji dla różnych scenariuszy
Możesz się zastanawiać, kiedy używać `Exact`, a kiedy `Rounding`. Oto dwa typowe scenariusze:

| Scenariusz | Zalecany model | Powód |
|------------|----------------|-------|
| Analiza naukowa wysokiej precyzji | `PrecisionModel.Exact` | Brak utraty szczegółowości współrzędnych |
| Kafelki map internetowych lub aplikacje mobilne | `PrecisionModel.Rounding(2)` | Zmniejsza rozmiar pliku i przyspiesza renderowanie |

Wybór odpowiedniego modelu jest częścią procesu podejmowania decyzji o **ustawieniu modelu precyzji**, który równoważy dokładność z wydajnością.

## Typowe problemy i rozwiązania
- **Nieoczekiwane wartości współrzędnych** – Upewnij się, że ustawiasz `options.XYPrecisionModel` *przed* otwarciem warstwy. Zmiana po otwarciu nie ma efektu.  
- **Plik nie znaleziony** – Sprawdź, czy zmienna `path` wskazuje prawidłowy katalog i czy plik Shapefile został pomyślnie utworzony w poprzednim kroku.  
- **Nieprawidłowy typ geometrii** – Przykład używa `Point`. Dla innych typów geometrii (np. `LineString`) rzutowanie powinno odpowiadać rzeczywistemu typowi.  

## Wskazówki dotyczące zmniejszania rozmiaru pliku Shapefile
- Używaj `PrecisionModel.Rounding` z najmniejszą liczbą miejsc po przecinku, która nadal spełnia Twoje wymagania dotyczące dokładności.  
- Usuń niepotrzebne pola atrybutów przed zapisem warstwy.  
- Skompresuj powstałe pliki `.shp`, `.shx` i `.dbf` przy użyciu standardowych narzędzi ZIP, jeśli musisz je przesłać.

## Podsumowanie
Podsumowując, zarządzanie precyzją przy odczycie geometrii jest kluczowym aspektem manipulacji danymi geoprzestrzennymi. Aspose.GIS dla .NET oferuje solidne funkcje umożliwiające efektywne osiągnięcie tego celu. Postępując zgodnie z powyższymi krokami, możesz płynnie **utworzyć warstwę wektorową**, **ustawić model precyzji**, a także **zmniejszyć rozmiar pliku shapefile**, gdy jest to odpowiednie, zapewniając optymalne przetwarzanie danych w Twoich aplikacjach.

## FAQ
### Czy mogę używać Aspose.GIS dla .NET z innymi frameworkami .NET, takimi jak .NET Core lub .NET Standard?
Tak, Aspose.GIS dla .NET jest kompatybilny z różnymi frameworkami .NET, w tym .NET Core i .NET Standard.  
### Czy dostępna jest wersja próbna Aspose.GIS dla .NET?
Tak, możesz uzyskać darmową wersję próbną ze [strony wydań](https://releases.aspose.com/).  
### Gdzie mogę znaleźć pełną dokumentację Aspose.GIS dla .NET?
Możesz odwołać się do [dokumentacji](https://reference.aspose.com/gis/net/) po szczegółowe informacje i przykłady.  
### Jak mogę uzyskać tymczasowe licencje dla Aspose.GIS dla .NET?
Tymczasowe licencje można nabyć na [stronie zakupu](https://purchase.aspose.com/temporary-license/) dla Aspose.GIS.  
### Gdzie mogę uzyskać pomoc lub wsparcie dla Aspose.GIS dla .NET?
Możesz odwiedzić forum Aspose.GIS [forum](https://forum.aspose.com/c/gis/33) w celu zadawania pytań, dyskusji lub uzyskania wsparcia.

## Często zadawane pytania
**Q: Czy ograniczenie precyzji wpływa na oryginalny plik shapefile?**  
**A:** Nie. Precyzja jest stosowana tylko podczas odczytu geometrii; plik źródłowy pozostaje niezmieniony.  

**Q: Czy mogę używać innego modelu precyzji dla współrzędnych X i Y?**  
**A:** Aspose.GIS obecnie stosuje ten sam XYPrecisionModel dla obu osi.  

**Q: Czy można ustawić własną funkcję zaokrąglania?**  
**A:** API obsługuje tylko wbudowaną metodę PrecisionModel.Rounding(int). Aby zastosować własną logikę, należy przetworzyć współrzędne po odczycie.  

---

**Ostatnia aktualizacja:** 2026-04-03  
**Testowano z:** Aspose.GIS 24.11 dla .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}