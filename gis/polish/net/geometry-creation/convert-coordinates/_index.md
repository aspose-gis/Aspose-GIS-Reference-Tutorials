---
date: 2026-08-18
description: Konwertuj stopnie dziesiętne na DMS przy użyciu Aspose.GIS for .NET.
  Ten szczegółowy przewodnik w C# pokazuje, jak przekształcić współrzędne latitude/longitude,
  stopnie dziesiętne na DMS i nie tylko.
keywords:
- decimal degrees to dms
- convert coordinates dms
- gis coordinate conversion
- convert lat long dms
- c# convert lat long
lastmod: 2026-08-18
linktitle: Konwertuj współrzędne
og_description: Konwersja stopni dziesiętnych na DMS jest prosta dzięki Aspose.GIS
  for .NET. Dowiedz się, jak przekształcić wartości latitude‑longitude do formatu
  DMS w minutach.
og_image_alt: Guide showing decimal degrees to DMS conversion using Aspose.GIS in
  C#
og_title: Jak przekonwertować stopnie dziesiętne na DMS przy użyciu Aspose.GIS for
  .NET
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  headline: How to convert decimal degrees to dms with Aspose.GIS for .NET
  type: TechArticle
- description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  name: How to convert decimal degrees to dms with Aspose.GIS for .NET
  steps:
  - name: start the conversion process
    text: We print a friendly message so you know the demo has begun.
  - name: convert to decimal degrees
    text: Even though the final goal is DMS, we start by showing the original decimal
      representation. This also demonstrates the **decimal degrees to dms** path you’ll
      later follow.
  - name: convert to degree decimal minutes
    text: This format (`DD°MM.m'`) is a common intermediate step when you need to
      **convert lat long degree minutes**.
  - name: convert to degree minutes seconds (dms)
    text: Here’s the core of our tutorial—**convert coordinates to dms**.
  - name: convert to GeoRef
    text: For completeness, we also demonstrate the `GeoRef` format, useful in remote‑sensing
      workflows.
  type: HowTo
- questions:
  - answer: Aspose.GIS primarily targets .NET developers, but a Java version is also
      available.
    question: Is Aspose.GIS compatible with other programming languages?
  - answer: Yes, you can access a free trial of Aspose.GIS from the [website](https://releases.aspose.com/).
    question: Can I try Aspose.GIS before purchasing?
  - answer: You can seek assistance from the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How can I get support for Aspose.GIS?
  - answer: Yes, temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses available for Aspose.GIS?
  - answer: You can purchase Aspose.GIS from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert coordinates
- Aspose.GIS
- .NET GIS processing
title: Jak przekonwertować stopnie dziesiętne na DMS przy użyciu Aspose.GIS for .NET
url: /pl/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak przekonwertować stopnie dziesiętne na dms przy użyciu Aspose.GIS

## Wprowadzenie
W tym samouczku nauczysz się **jak przekonwertować stopnie dziesiętne na dms** przy użyciu potężnej biblioteki Aspose.GIS dla .NET. Niezależnie od tego, czy potrzebujesz **c# convert lat long**, generować czytelne dla człowieka ciągi lokalizacji do raportów, czy po prostu badać różne formaty współrzędnych, ten przewodnik przeprowadzi Cię przez każdy krok z jasnymi wyjaśnieniami i gotowymi do uruchomienia fragmentami C#.

## Szybkie odpowiedzi
- **Co oznacza „convert coordinates to dms”?** Przekształca numeryczne wartości szerokości/długości geograficznej na tradycyjny zapis stopnie‑minuty‑sekundy.  
- **Która biblioteka obsługuje konwersję?** Aspose.GIS dla .NET udostępnia klasę `GeoConvert` z wbudowaną obsługą formatów.  
- **Czy potrzebna jest licencja, aby wypróbować?** Dostępna jest darmowa wersja próbna; licencja komercyjna jest wymagana do użytku produkcyjnego.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+ oraz .NET 5/6+.  
- **Czy mogę używać tego samego kodu dla innych formatów?** Tak — wystarczy zmienić wartość wyliczenia `PointFormats` (np. `DecimalDegrees`, `GeoRef`).  

## Co to jest konwersja współrzędnych do dms?
Konwersja współrzędnych do DMS przepisuje wartości szerokości i długości geograficznej w formacie dziesiętnym na format taki jak `25°30'00"N 45°30'00"E`. Proces dzieli każdą stopnię dziesiętną na całe stopnie, minuty (jedna sześćdziesiąta stopnia) i sekundy (jedna sześćdziesiąta minuty), a następnie dodaje odpowiedni wskaźnik półkuli (N, S, E, W). Ten czytelny dla człowieka format jest niezbędny w wielu starszych zestawach danych oraz do komunikowania precyzyjnych lokalizacji bez użycia notacji dziesiętnej.

## Dlaczego używać Aspose.GIS do konwersji współrzędnych?
Aspose.GIS obsługuje **ponad 50 formatów wejścia i wyjścia** i może przetwarzać wielostronicowe pliki GIS bez ładowania całego zestawu danych do pamięci. API zapewnia podmilimetrową dokładność w przypadkach brzegowych, takich jak wartości ujemne i oznaczenia półkul, i działa konsekwentnie na środowiskach .NET w systemach Windows, Linux i macOS.

## Wymagania wstępne
Przed rozpoczęciem upewnij się, że masz:

1. **Podstawową znajomość C#** – znajomość zmiennych, wywołań metod i wyjścia w konsoli.  
2. **Zainstalowany Aspose.GIS** – pobierz najnowszy pakiet ze [strony Aspose.GIS](https://releases.aspose.com/gis/net/). Możesz także przeglądać główną stronę wydań Aspose pod adresem [strona wydań Aspose](https://releases.aspose.com/).  

## Importowanie przestrzeni nazw
Najpierw zaimportuj przestrzenie nazw wymagane do operacji GIS:

Placeholder importu przestrzeni nazw pozostaje niezmieniony.

## Przewodnik krok po kroku

### Co to jest klasa GeoConvert?
Klasa `GeoConvert` udostępnia statyczne metody do konwersji między formatami współrzędnych, takimi jak stopnie dziesiętne, DMS i GeoRef. Zawiera przeciążenia przyjmujące surowe wartości liczbowe lub obiekty `Point` i zwracające sformatowane ciągi znaków lub nowe instancje `Point`. Obsługując przypadki brzegowe, takie jak współrzędne ujemne i zaokrąglanie, klasa zapewnia, że wynik spełnia standardowe specyfikacje GIS, upraszczając integrację w dowolnej aplikacji mapującej .NET.

### Krok 1: rozpocznij proces konwersji
Wypisujemy przyjazny komunikat, abyś wiedział, że demo się rozpoczęło.

```csharp
using System;
using Aspose.Gis;
```

### Krok 2: konwersja na stopnie dziesiętne
Choć ostatecznym celem jest DMS, najpierw pokazujemy oryginalną reprezentację dziesiętną. To także demonstruje ścieżkę **decimal degrees to dms**, którą później podążysz.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### Krok 3: konwersja na stopnie i minuty dziesiętne
Ten format (`DD°MM.m'`) jest powszechnym krokiem pośrednim, gdy potrzebujesz **convert lat long degree minutes**.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Krok 4: konwersja na stopnie, minuty, sekundy (DMS)
Oto sedno naszego samouczka — **convert coordinates to dms**.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Krok 5: konwersja na GeoRef
Dla pełności demonstracji pokazujemy także format `GeoRef`, przydatny w przepływach pracy zdalnego przetwarzania danych.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

## Typowe problemy i rozwiązania
- **Nieprawidłowe litery półkuli** – Upewnij się, że podajesz dodatnie wartości dla północny/wschód i ujemne dla południe/zachód; API automatycznie dodaje właściwy przyrostek.  
- **Nieoczekiwany pusty wynik** – Sprawdź, czy zestaw `Aspose.Gis` jest poprawnie odwołany i czy projekt celuje w obsługiwaną wersję .NET.  
- **Nie znaleziono licencji** – Umieść plik licencji w katalogu głównym aplikacji lub ustaw go programowo za pomocą `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.

## Najczęściej zadawane pytania

**Q: Czy Aspose.GIS jest kompatybilny z innymi językami programowania?**  
A: Aspose.GIS jest przeznaczony głównie dla programistów .NET, ale dostępna jest także wersja Java.

**Q: Czy mogę wypróbować Aspose.GIS przed zakupem?**  
A: Tak, możesz uzyskać dostęp do darmowej wersji próbnej Aspose.GIS ze [strony internetowej](https://releases.aspose.com/).

**Q: Jak mogę uzyskać wsparcie dla Aspose.GIS?**  
A: Możesz szukać pomocy na forum społeczności Aspose.GIS [tutaj](https://forum.aspose.com/c/gis/33).

**Q: Czy dostępne są tymczasowe licencje dla Aspose.GIS?**  
A: Tak, tymczasowe licencje można uzyskać na [stronie tymczasowych licencji](https://purchase.aspose.com/temporary-license/).

**Q: Gdzie mogę kupić Aspose.GIS?**  
A: Aspose.GIS można zakupić na [stronie zakupu](https://purchase.aspose.com/buy).

## Podsumowanie
Postępując zgodnie z tymi krokami, teraz wiesz, jak **przekonwertować stopnie dziesiętne na dms** oraz inne popularne formaty GIS przy użyciu Aspose.GIS dla .NET. Ta możliwość pozwala płynnie integrować czytelne dla człowieka ciągi lokalizacji w aplikacjach mapujących, raportach lub dowolnym przepływie pracy danych przestrzennych. Śmiało eksperymentuj z różnymi wartościami szerokości/długości i odkrywaj inne formaty oferowane przez klasę `GeoConvert`.

---

**Last Updated:** 2026-08-18  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## Powiązane samouczki

- [Jak utworzyć geometrię punktu i uzyskać typ geometrii przy użyciu Aspose.GIS dla .NET](/gis/net/geometry-analysis/get-geometry-type/)
- [Jak przekonwertować GeoJSON – Aspose.GIS dla .NET](/gis/net/geo-data-conversion/)
- [Utwórz geometrię MultiPoint .NET przy użyciu Aspose.GIS](/gis/net/geometry-creation/create-multipoint-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}