---
date: 2025-12-21
description: Dowiedz się, jak tworzyć geometrię typu linestring i konwertować geometrię
  na WKB przy użyciu Aspose.GIS dla .NET w wariancie ExtendedPostGis.
linktitle: Specify WKB Variant on Translation
second_title: Aspose.GIS .NET API
title: Utwórz geometrię Linestring i wariant WKB w Aspose.GIS .NET
url: /pl/net/geometry-processing/specify-wkb-variant-on-translation/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Określ wariant WKB przy translacji w Aspose.GIS dla .NET

## Wprowadzenie
W dziedzinie rozwoju Systemów Informacji Geograficznej (GIS) Aspose.GIS dla .NET wyróżnia się jako potężny zestaw narzędzi. Jeśli potrzebujesz **utworzyć geometrię linestring** i następnie **przekształcić geometrię do WKB**, jesteś we właściwym miejscu. Jego wszechstronność i wydajność czynią go wyborem numer jeden dla programistów, którzy chcą płynnie integrować funkcje GIS w swoich aplikacjach .NET. Ten artykuł służy jako kompleksowy przewodnik po wykorzystaniu Aspose.GIS dla .NET, ze szczególnym uwzględnieniem określania wariantów WKB (Well‑Known Binary) podczas procesów translacji.

## Szybkie odpowiedzi
- **Co oznacza skrót WKB?** Well‑Known Binary, kompaktowa binarna reprezentacja obiektów geometrycznych.  
- **Który wariant WKB pozwala przechowywać informację o SRID?** Wariant `ExtendedPostGis` (EWKB).  
- **Czy potrzebna jest licencja do uruchomienia kodu?** Wymagana jest tymczasowa lub pełna licencja do użytku produkcyjnego.  
- **Jakie wersje .NET są wspierane?** .NET Framework 4.5+, .NET Core 3.1+, oraz .NET 5/6+.  
- **Jak długo trwa implementacja?** Zazwyczaj poniżej 10 minut dla podstawowego przykładu.

## Czym jest geometria Linestring?
Linestring to prosta figura geometryczna składająca się z kolejnych punktów połączonych odcinkami prostych linii. Jest powszechnie używana do reprezentacji dróg, rzek lub dowolnych cech liniowych w danych GIS.

## Dlaczego określić wariant WKB?
Wybranie odpowiedniego wariantu WKB zapewnia zachowanie ważnych metadanych — takich jak identyfikator układu odniesienia przestrzennego (SRID) — podczas przechowywania lub wymiany danych geometrycznych. Wariant `ExtendedPostGis` (EWKB) jest szczególnie przydatny przy pracy z PostgreSQL/PostGIS lub każdym systemem, który oczekuje informacji o SRID osadzonej w binarnej postaci.

## Wymagania wstępne
Zanim przejdziesz do szczegółów określania wariantów WKB w Aspose.GIS dla .NET, upewnij się, że spełniasz poniższe wymagania:

### Instalacja Aspose.GIS dla .NET
1. Pobierz Aspose.GIS: Odwiedź [link do pobrania](https://releases.aspose.com/gis/net/), aby uzyskać pakiet Aspose.GIS dla .NET.  
2. Zainstaluj pakiet: Postępuj zgodnie z instrukcjami instalacji zamieszczonymi w dokumentacji, aby bezproblemowo zintegrować Aspose.GIS ze swoim środowiskiem .NET.

### Znajomość programowania w C#
1. Podstawowa znajomość C#: Upewnij się, że posiadasz podstawową wiedzę na temat składni i koncepcji języka C#.

## Importowanie przestrzeni nazw
Aby rozpocząć pracę z Aspose.GIS dla .NET i efektywnie korzystać z jego funkcjonalności, musisz zaimportować niezbędne przestrzenie nazw do swojego projektu. Oto przewodnik krok po kroku:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Te przestrzenie nazw zapewniają dostęp do funkcji Aspose.GIS, umożliwiając łatwą pracę z danymi geograficznymi.

## Jak utworzyć geometrię linestring?
Rozbijmy podany przykład na kilka kroków, aby dokładnie zrozumieć proces określania wariantów WKB przy translacji.

### Krok 1: Tworzenie obiektu Geometry
```csharp
IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
```
W tym kroku **tworzymy geometrię linestring**, reprezentującą cechę liniową o określonych współrzędnych.

### Krok 2: Generowanie reprezentacji WKB
```csharp
byte[] wkb = geometry.AsBinary(WkbVariant.ExtendedPostGis);
```
Tutaj **konwertujemy geometrię do WKB** używając wariantu `ExtendedPostGis`, który osadza informację o SRID.

### Krok 3: Zapis do pliku
```csharp
File.WriteAllBytes(Path.Combine("Your Document Directory", "EWkbFile.ewkb"), wkb);
```
Na koniec zapisujemy wygenerowane binarne dane WKB do pliku o nazwie `EWkbFile.ewkb` w wybranym katalogu.

## Typowe problemy i rozwiązania
| Problem | Powód | Rozwiązanie |
|-------|--------|----------|
| **Pusty plik** | `Path.Combine` wskazuje na nieistniejący katalog. | Upewnij się, że docelowy katalog istnieje lub utwórz go za pomocą `Directory.CreateDirectory`. |
| **Nieprawidłowy SRID** | Użycie domyślnego `WkbVariant.Standard` powoduje utratę SRID. | Zawsze używaj `WkbVariant.ExtendedPostGis`, gdy wymagana jest zachowanie SRID. |
| **Wyjątek licencyjny** | Uruchamianie bez ważnej licencji w środowisku produkcyjnym. | Zastosuj tymczasową lub pełną licencję przed uruchomieniem kodu w środowisku produkcyjnym. |

## Najczęściej zadawane pytania
### Czy Aspose.GIS dla .NET jest kompatybilny ze wszystkimi wersjami .NET?
Aspose.GIS dla .NET został zaprojektowany tak, aby był kompatybilny z różnymi wersjami .NET, zapewniając elastyczność i dostępność dla programistów.

### Czy mogę poprosić o wsparcie lub pomoc podczas korzystania z Aspose.GIS dla .NET?
Tak, możesz uzyskać wsparcie i pomoc poprzez dedykowane [forum Aspose.GIS](https://forum.aspose.com/c/gis/33), gdzie eksperci i inni programiści odpowiedzą na Twoje pytania.

### Czy Aspose.GIS dla .NET oferuje darmowy trial?
Tak, możesz wypróbować funkcje i możliwości Aspose.GIS dla .NET dzięki darmowemu trialowi dostępnym pod [tym linkiem](https://releases.aspose.com/).

### Jak mogę uzyskać tymczasową licencję dla Aspose.GIS dla .NET?
Możesz uzyskać tymczasową licencję, odwiedzając [stronę tymczasowej licencji](https://purchase.aspose.com/temporary-license/) i postępując zgodnie z podanymi instrukcjami.

### Gdzie mogę kupić licencję na Aspose.GIS dla .NET?
Licencję na Aspose.GIS dla .NET możesz zakupić na stronie zakupu pod [tym linkiem](https://purchase.aspose.com/buy).

## Często zadawane pytania
**P: Czy mogę używać pliku EWKB z PostGIS?**  
O: Tak, wariant `ExtendedPostGis` generuje EWKB, który zawiera SRID i może być bezpośrednio odczytany przez PostGIS.

**P: Czy można odczytać plik WKB z powrotem do obiektu geometrycznego?**  
O: Oczywiście. Użyj `Geometry.FromBinary(byteArray)`, aby odtworzyć geometrię.

**P: Czy biblioteka obsługuje inne typy geometrii, takie jak wielokąty?**  
O: Tak, Aspose.GIS obsługuje punkty, linestringi, wielokąty, multipoligony i wiele innych.

**P: Jak określić inny SRID przy tworzeniu geometrii?**  
O: Ustaw SRID na obiekcie geometrycznym przed wywołaniem `AsBinary`, np. `geometry.SRID = 4326;`.

**P: Czy ten kod będzie działał na .NET Core?**  
O: Tak, to samo API działa zarówno w .NET Framework, .NET Core, jak i .NET 5/6.

---

**Ostatnia aktualizacja:** 2025-12-21  
**Testowano z:** Aspose.GIS for .NET 23.9 (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}