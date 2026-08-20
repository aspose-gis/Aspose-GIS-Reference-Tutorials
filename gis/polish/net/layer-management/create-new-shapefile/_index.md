---
date: 2026-06-30
description: Dowiedz się, jak utworzyć shapefile przy użyciu Aspose.GIS dla .NET.
  Ten przewodnik krok po kroku pokazuje, jak zdefiniować warstwę wektorową, dodać
  atrybut daty i efektywnie zarządzać danymi przestrzennymi.
keywords:
- how to create shapefile
- temporal gis shapefile
- Aspose.GIS vector layer
- GIS data automation
linktitle: Utwórz nowy shapefile
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create shapefile using Aspose.GIS for .NET. This step‑by‑step
    guide shows you how to define a vector layer, add a date attribute, and manage
    spatial data efficiently.
  headline: How to Create Shapefile with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS primarily supports .NET, but there are versions available for
      Java as well.
    question: Can I use Aspose.GIS with other programming languages?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I find support for Aspose.GIS?
  - answer: Get your temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license?
  - answer: You can buy the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Jak utworzyć plik shapefile przy użyciu Aspose.GIS dla .NET
url: /pl/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz nowy shapefile

## Wprowadzenie
Jeśli zagłębiasz się w rozwój systemów informacji geograficznej (GIS) w .NET, Aspose.GIS jest Twoim rozwiązaniem numer jeden do **tworzenia shapefile** programowo. Biblioteka ta daje pełną kontrolę nad warstwami wektorowymi, schematami atrybutów i zgodnością formatu pliku, dzięki czemu możesz automatyzować przepływy danych lub generować zestawy testowe w kilka minut.

## Szybkie odpowiedzi
- **Co uczy ten samouczek?** Jak utworzyć nowy plik shapefile, zdefiniować warstwę wektorową i dodać atrybuty (w tym pole daty).  
- **Jakiej biblioteki wymaga?** Aspose.GIS for .NET.  
- **Czy potrzebuję licencji?** Darmowa wersja próbna wystarczy do nauki; licencja komercyjna jest wymagana w produkcji.  
- **Jakiego IDE powinienem używać?** Visual Studio (dowolna nowsza wersja).  
- **Jak długo trwa implementacja?** Około 10‑15 minut dla podstawowego przykładu.

## Jak utworzyć shapefile przy użyciu Aspose.GIS dla .NET?
Załaduj bibliotekę Aspose.GIS, ustaw folder wyjściowy, utwórz `VectorLayer`, zdefiniuj atrybuty i dodaj obiekty — cały ten przepływ pracy można zapisać w mniej niż 30 liniach C#. Biblioteka automatycznie obsługuje tworzenie geometrii, typowanie atrybutów i zapisywanie pliku, więc nie musisz samodzielnie zarządzać niskopoziomowymi specyfikacjami Shapefile.

## Wymagania wstępne
Zanim przejdziemy do samouczka, upewnij się, że masz spełnione następujące wymagania:
- Podstawowa znajomość języka programowania C#.  
- Zainstalowane Visual Studio na komputerze.  
- Biblioteka Aspose.GIS for .NET. Możesz ją pobrać [tutaj](https://releases.aspose.com/gis/net/).

## Importuj przestrzenie nazw
Zacznij od zaimportowania niezbędnych przestrzeni nazw, aby wykorzystać funkcjonalność Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Krok 1: Skonfiguruj swój projekt
Rozpocznij od utworzenia nowego projektu C# w Visual Studio i dodania biblioteki Aspose.GIS.

## Krok 2: Zdefiniuj katalog dokumentu
```csharp
string dataDir = "Your Document Directory";
```
Zastąp *Your Document Directory* rzeczywistą ścieżką, w której chcesz zapisać nowy plik shapefile.

## Krok 3: Utwórz VectorLayer
Klasa `VectorLayer` reprezentuje pojedynczą warstwę shapefile, która przechowuje dane geometryczne i atrybuty.  
W tym kroku definiujemy warstwę wektorową i deklarujemy trzy atrybuty: pole tekstowe (`name`), pole liczbowe (`age`) oraz pole daty i czasu (`dob`). Dodanie atrybutu daty jest kluczowe dla analiz **czasowych GIS shapefile**.

```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```

## Krok 4: Dodaj obiekty
### Przypadek 1: Ustawia wartości indywidualnie
Metoda `SetValues` przypisuje wartości atrybutów do obiektu w kolejności, w jakiej zostały zdefiniowane.  
```csharp
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
firstFeature.SetValue("dob", new DateTime(1982, 2, 5, 16, 30, 0));
layer.Add(firstFeature);
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
secondFeature.SetValue("dob", new DateTime(1984, 12, 15, 15, 30, 0));
layer.Add(secondFeature);
```
Tutaj tworzymy dwa punkty, ustawiamy każdy atrybut osobno i dodajemy obiekty do warstwy.

### Przypadek 2: Ustawia nowe wartości dla wszystkich atrybutów
Alternatywnie możesz podać wszystkie wartości atrybutów jednocześnie, używając `SetValues` z tablicą obiektów.  
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
W tym podejściu wypełniamy wszystkie wartości atrybutów w jednym wywołaniu przy użyciu tablicy obiektów — przydatne, gdy masz wiele atrybutów.

## Dlaczego to jest ważne?
Programowe tworzenie shapefile pozwala automatyzować przepływy danych, generować zestawy testowe lub osadzać wyniki GIS bezpośrednio w usługach internetowych. Aspose.GIS obsługuje **ponad 30 formatów wektorowych i rastrowych** i może zapisywać shapefile o setkach stron bez wczytywania całego pliku do pamięci, zapewniając zarówno szybkość, jak i skalowalność.

## Częste pułapki i wskazówki
- **Separatory ścieżek:** Używaj `Path.Combine` dla kompatybilności międzyplatformowej zamiast konkatenacji łańcuchów.  
- **Kolejność atrybutów:** Kolejność wartości w `SetValues` musi odpowiadać kolejności, w której dodałeś atrybuty.  
- **Obsługa dat:** Zawsze używaj `DateTimeKind.Utc`, jeśli Twoje dane GIS będą udostępniane w różnych strefach czasowych.

## Zakończenie
Gratulacje! Pomyślnie utworzyłeś nowy plik shapefile przy użyciu Aspose.GIS dla .NET. Ten samouczek omówił podstawy konfigurowania projektu, definiowania warstwy wektorowej i dodawania obiektów — w tym atrybutu daty. W miarę dalszej eksploracji odwołuj się do [dokumentacji](https://reference.aspose.com/gis/net/) w celu poznania zaawansowanych funkcji i możliwości.

## Najczęściej zadawane pytania
**Q: Czy mogę używać Aspose.GIS z innymi językami programowania?**  
A: Aspose.GIS głównie obsługuje .NET, ale dostępne są także wersje dla Javy.  

**Q: Czy dostępna jest darmowa wersja próbna?**  
A: Tak, darmową wersję próbną możesz uzyskać [tutaj](https://releases.aspose.com/).  

**Q: Gdzie mogę znaleźć wsparcie dla Aspose.GIS?**  
A: Odwiedź [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) w celu uzyskania wsparcia społeczności i dyskusji.  

**Q: Jak mogę uzyskać tymczasową licencję?**  
A: Uzyskaj tymczasową licencję [tutaj](https://purchase.aspose.com/temporary-license/).  

**Q: Gdzie mogę kupić Aspose.GIS dla .NET?**  
A: Bibliotekę możesz kupić [tutaj](https://purchase.aspose.com/buy).  

---

**Ostatnia aktualizacja:** 2026-06-30  
**Testowano z:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose

## Powiązane samouczki

- [Pobierz atrybuty warstwy – Uzyskaj informacje o atrybutach warstwy przy użyciu Aspose.GIS dla .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Utwórz warstwę wektorową i ustaw system odniesienia przestrzennego warstwy](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Utwórz warstwę wektorową w pliku GDB – Samouczek Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}