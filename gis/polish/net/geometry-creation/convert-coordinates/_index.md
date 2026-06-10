---
date: 2026-02-13
description: Dowiedz się, jak konwertować współrzędne na DMS za pomocą Aspose.GIS
  dla .NET. Ten krok po kroku przewodnik w C# pokazuje, jak w C# konwertować szerokość
  i długość geograficzną, stopnie dziesiętne na DMS i wiele więcej.
linktitle: Convert Coordinates
second_title: Aspose.GIS .NET API
title: Jak konwertować współrzędne na DMS przy użyciu Aspose.GIS dla .NET
url: /pl/net/geometry-creation/convert-coordinates/
weight: 25
---

-button >}}

Make sure to keep all shortcodes exactly.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak konwertować współrzędne na DMS przy użyciu Aspose.GIS

## Wprowadzenie
W tym samouczku dowiesz się **jak konwertować współrzędne** na DMS (stopnie, minuty, sekundy) przy użyciu potężnej biblioteki Aspose.GIS dla .NET. Niezależnie od tego, czy potrzebujesz **c# convert lat long**, generować czytelne dla człowieka ciągi lokalizacji, czy po prostu eksplorować różne formaty współrzędnych, ten przewodnik przeprowadzi Cię przez każdy krok z jasnymi wyjaśnieniami i gotowym do uruchomienia kodem C#.

## Szybkie odpowiedzi
- **Co oznacza „convert coordinates to DMS”?** Przekształca numeryczne wartości szerokości/długości geograficznej na tradycyjny zapis stopnie‑minuty‑sekundy.  
- **Która biblioteka obsługuje konwersję?** Aspose.GIS dla .NET udostępnia klasę `GeoConvert` z wbudowaną obsługą formatów.  
- **Czy potrzebna jest licencja, aby wypróbować?** Dostępna jest darmowa wersja próbna; licencja komercyjna jest wymagana do użytku produkcyjnego.  
- **Jakie wersje .NET są wspierane?** .NET Framework 4.5+, .NET Core 3.1+ oraz .NET 5/6+.  
- **Czy mogę używać tego samego kodu dla innych formatów?** Tak — wystarczy zmienić wartość wyliczenia `PointFormats` (np. `DecimalDegrees`, `GeoRef`).  

## Jak konwertować współrzędne na DMS
Zanim przejdziemy do kodu, wyjaśnijmy, dlaczego DMS wciąż jest przydatny. Kartografowie, piloci i wielu dostawców danych GIS polegają na DMS, ponieważ jest przyjazny dla człowieka i zgodny z tradycyjnymi mapami. Aspose.GIS eliminuje potrzebę ręcznych obliczeń, pozwalając skupić się na logice aplikacji.

## Czym jest konwersja współrzędnych na DMS?
Konwersja współrzędnych na DMS przekształca dziesiętne wartości szerokości i długości geograficznej do formatu takiego jak `25°30'00"N 45°30'00"E`. Ta reprezentacja jest szeroko stosowana w kartografii, nawigacji i wymianie danych GIS.

## Dlaczego warto używać Aspose.GIS do konwersji współrzędnych?
- **All‑in‑one API** – Brak zewnętrznych bibliotek i skomplikowanych obliczeń; Aspose.GIS obsługuje parsowanie i formatowanie wewnętrznie.  
- **Wysoka dokładność** – Precyzyjne radzenie sobie z przypadkami brzegowymi, takimi jak wartości ujemne i oznaczenia półkul.  
- **Cross‑platform** – Działa tak samo na środowiskach .NET w Windows, Linux i macOS.  
- **Rozszerzalny** – Łatwo przełączać się między formatami DMS, stopnie dziesiętne, stopnie‑minuty‑dziesiętne oraz GeoRef.  

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

1. **Podstawową znajomość C#** – Znajomość zmiennych, wywołań metod i wyjścia konsoli.  
2. **Zainstalowany Aspose.GIS** – Pobierz najnowszy pakiet ze [strony Aspose.GIS](https://releases.aspose.com/gis/net/).  

## Importowanie przestrzeni nazw
Najpierw zaimportuj przestrzenie nazw wymagane do operacji GIS:

```csharp
using System;
using Aspose.Gis;
```

## Przewodnik krok po kroku

### Krok 1: Rozpocznij proces konwersji
Wypisujemy przyjazny komunikat, abyś wiedział, że demo się rozpoczęło.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### Krok 2: Konwersja na stopnie dziesiętne  
Mimo że ostatecznym celem jest DMS, zaczynamy od pokazania pierwotnej reprezentacji dziesiętnej. To także demonstruje ścieżkę **decimal degrees to dms**, którą później zastosujesz.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Krok 3: Konwersja na stopnie‑minuty‑dziesiętne  
Ten format (`DD°MM.m'`) jest powszechnym krokiem pośrednim, gdy potrzebujesz *convert lat long degree minutes*.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Krok 4: Konwersja na stopnie‑minuty‑sekundy (DMS)  
Oto sedno naszego samouczka — **convert coordinates to DMS**.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

### Krok 5: Konwersja na GeoRef  
Dla pełności, demonstrujemy również format `GeoRef`, przydatny w przepływach pracy zdalnego wykrywania.

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## Typowe problemy i rozwiązania
- **Nieprawidłowe litery półkuli** – Upewnij się, że podajesz dodatnie wartości dla północny/wschód i ujemne dla południe/zachód; API automatycznie dodaje właściwy sufiks.  
- **Nieoczekiwany pusty wynik** – Sprawdź, czy zestaw `Aspose.Gis` jest poprawnie odwołany i czy projekt celuje w obsługiwaną wersję .NET.  
- **Nie znaleziono licencji** – Umieść plik licencji w katalogu głównym aplikacji lub ustaw go programowo za pomocą `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.  

## Najczęściej zadawane pytania

**Q: Czy Aspose.GIS jest kompatybilny z innymi językami programowania?**  
A: Aspose.GIS jest głównie skierowany do programistów .NET, ale dostępna jest również wersja Java.

**Q: Czy mogę wypróbować Aspose.GIS przed zakupem?**  
A: Tak, możesz uzyskać dostęp do darmowej wersji próbnej Aspose.GIS ze [strony internetowej](https://releases.aspose.com/).

**Q: Jak mogę uzyskać wsparcie dla Aspose.GIS?**  
A: Możesz szukać pomocy na forum społeczności Aspose.GIS [tutaj](https://forum.aspose.com/c/gis/33).

**Q: Czy dostępne są tymczasowe licencje dla Aspose.GIS?**  
A: Tak, tymczasowe licencje można uzyskać ze [strony tymczasowych licencji](https://purchase.aspose.com/temporary-license/).

**Q: Gdzie mogę kupić Aspose.GIS?**  
A: Możesz zakupić Aspose.GIS na [stronie zakupu](https://purchase.aspose.com/buy).

## Podsumowanie
Postępując zgodnie z tymi krokami, teraz wiesz, jak **convert coordinates to DMS** i inne popularne formaty GIS przy użyciu Aspose.GIS dla .NET. Ta funkcjonalność pozwala płynnie integrować czytelne dla człowieka ciągi lokalizacji w aplikacjach mapowych, raportach lub dowolnym przepływie pracy z danymi przestrzennymi. Śmiało eksperymentuj z różnymi wartościami szerokości/długości i odkrywaj inne formaty oferowane przez klasę `GeoConvert`.

---

**Ostatnia aktualizacja:** 2026-02-13  
**Testowano z:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}