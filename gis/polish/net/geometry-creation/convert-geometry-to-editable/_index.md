---
date: 2025-12-11
description: Dowiedz się, jak dodać punkt do linii i bez wysiłku przekształcić geometrię
  w edytowalny format przy użyciu Aspose.GIS dla .NET. Postępuj zgodnie z tym samouczkiem
  krok po kroku.
linktitle: Convert Geometry to Editable
second_title: Aspose.GIS .NET API
title: Jak dodać punkt do LineString i przekształcić geometrię do edytowalnego formatu
  przy użyciu Aspose.GIS
url: /pl/net/geometry-creation/convert-geometry-to-editable/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dodać punkt do LineString i przekształcić geometrię do formatu edytowalnego przy użyciu Aspose.GIS

## Wprowadzenie
Podczas pracy z danymi geoprzestrzennymi często zachodzi potrzeba **dodania punktu do obiektu linestring** i późniejszej swobodnej edycji. Aspose.GIS dla .NET upraszcza ten proces, oferując przejrzyste API do konwersji geometrii tylko do odczytu na edytowalne. W tym samouczku zobaczysz, jak dodać punkt do `LineString`, uzyskać kopię edytowalną i zweryfikować, że oryginalna geometria pozostaje niezmieniona.

## Szybkie odpowiedzi
- **Co oznacza „add point to linestring”?** Oznacza wstawienie nowej współrzędnej do istniejącej geometrii `LineString`.  
- **Która biblioteka to obsługuje?** Aspose.GIS dla .NET udostępnia metodę `ToEditable()` oraz funkcję `AddPoint()`.  
- **Czy potrzebna jest licencja na tę funkcję?** Darmowa wersja próbna działa w środowisku deweloperskim; licencja komercyjna jest wymagana w produkcji.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.  
- **Jak długo trwa implementacja?** Zazwyczaj mniej niż 10 minut dla podstawowego scenariusza.

## Co to jest „add point to linestring”?
Dodanie punktu do `LineString` wstawia nowy wierzchołek w określonych współrzędnych, wydłużając linię lub tworząc bardziej szczegółową ścieżkę. Operacja ta jest niezbędna przy edycji tras, korekcjach map czy dynamicznym budowaniu geometrii.

## Dlaczego warto używać Aspose.GIS do tego zadania?
- **Brak zewnętrznych zależności** – API obsługuje konwersję geometrii wewnętrznie.  
- **Bezpieczeństwo tylko do odczytu** – oryginalne geometrie pozostają niezmienne, co zapobiega przypadkowym zmianom.  
- **Prosta składnia** – metody takie jak `ToEditable()` i `AddPoint()` są intuicyjne dla programistów C#.  
- **Wieloplatformowość** – działa na Windows, Linux i macOS w środowiskach .NET.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz następujące elementy:

- **Środowisko .NET** – Zainstaluj platformę .NET z [website](https://dotnet.microsoft.com/download).  
- **Biblioteka Aspose.GIS** – Pobierz najnowszy pakiet ze [releases page](https://releases.aspose.com/gis/net/).  
- **Podstawy C#** – Znajomość składni C# oraz aplikacji konsolowych.

### Importowanie przestrzeni nazw
Aby rozpocząć, zaimportuj niezbędne przestrzenie nazw do swojego kodu C#. Dzięki temu będziesz mieć dostęp do funkcjonalności oferowanych przez Aspose.GIS dla .NET.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Teraz przejdźmy przez konkretne kroki konwersji geometrii do formatu edytowalnego i dodania punktu do `LineString`.

## Krok 1: Zdefiniuj geometrię tylko do odczytu
Najpierw utwórz obiekt geometrii tylko do odczytu, który reprezentuje prostą linię. Ten obiekt nie może być modyfikowany bezpośrednio.

```csharp
ILineString readOnlyLine = (ILineString)Geometry.FromText("LINESTRING (1 1, 2 2)");
```

## Krok 2: Uzyskaj kopię edytowalną
Aby edytować geometrię, uzyskaj wersję edytowalną przy użyciu metody `ToEditable()`. Tworzy to zmienną kopię, pozostawiając oryginał nietknięty.

```csharp
LineString editableLine = readOnlyLine.ToEditable();
```

## Krok 3: Dodaj punkt do LineString
Mając już kopię edytowalną, możesz **dodać punkt do linestring**. Metoda `AddPoint` dołącza nowy wierzchołek w podanych współrzędnych.

```csharp
editableLine.AddPoint(3, 3);
```

## Krok 4: Wyświetl zmodyfikowaną geometrię
Wypisz zmodyfikowaną geometrię, aby zweryfikować, że nowy punkt został pomyślnie dodany.

```csharp
Console.WriteLine(editableLine.AsText()); // LINESTRING (1 1, 2 2, 3 3)
```

## Krok 5: Zweryfikuj, że oryginalna geometria pozostała niezmieniona
Dobrą praktyką jest potwierdzenie, że oryginalna geometria tylko do odczytu nie została zmieniona.

```csharp
Console.WriteLine(readOnlyLine.AsText()); // LINESTRING (1 1, 2 2)
```

## Częste pułapki i wskazówki
- **Nie modyfikuj obiektu tylko do odczytu** – zawsze najpierw wywołaj `ToEditable()`.  
- **Kolejność współrzędnych ma znaczenie** – upewnij się, że przekazujesz (X, Y) w właściwej kolejności.  
- **Duże geometrie** – w przypadku bardzo długich obiektów `LineString` rozważ partiowanie edycji w celu poprawy wydajności.

## Najczęściej zadawane pytania

**Q: Czy Aspose.GIS jest kompatybilny z innymi bibliotekami .NET?**  
A: Tak, Aspose.GIS integruje się płynnie z popularnymi bibliotekami GIS dla .NET, takimi jak NetTopologySuite i SharpMap.

**Q: Czy mogę wypróbować Aspose.GIS przed zakupem?**  
A: Oczywiście! Możesz uzyskać darmową wersję próbną ze [releases page](https://releases.aspose.com/), aby zapoznać się z funkcjami.

**Q: Jak mogę uzyskać wsparcie dla Aspose.GIS?**  
A: Odwiedź [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) w celu uzyskania pomocy społeczności i oficjalnego wsparcia.

**Q: Czy dostępna jest tymczasowa licencja do oceny?**  
A: Tak, tymczasową licencję można zamówić poprzez [Aspose.GIS purchase page](https://purchase.aspose.com/temporary-license/).

**Q: Czy mogę kupić Aspose.GIS bezpośrednio?**  
A: Oczywiście! Skorzystaj ze [purchase page](https://purchase.aspose.com/buy), aby nabyć licencję dopasowaną do Twoich potrzeb.

---

**Ostatnia aktualizacja:** 2025-12-11  
**Testowano z:** Aspose.GIS 24.11 dla .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}