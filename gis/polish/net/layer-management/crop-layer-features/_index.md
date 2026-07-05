---
date: 2026-07-05
description: Dowiedz się, jak przyciąć cechy warstwy przy użyciu Aspose.GIS dla .NET,
  w tym jak przyciąć raster za pomocą wielokąta, wyodrębnić rozmiar komórki rastra
  oraz uzyskać zakres rastra. Pobierz bezpłatną wersję próbną już teraz.
keywords:
- how to crop layer
- extract raster extent
- get raster cell size
- crop raster layer
- crop raster with polygon
linktitle: Jak przyciąć cechy warstwy
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to crop layer features with Aspose.GIS for .NET, including
    how to crop raster with polygon, extract raster cell size, and retrieve raster
    extent. Download your free trial now.
  headline: How to Crop Layer Features with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Is a temporary license available for Aspose.GIS for .NET?
  - answer: The documentation is available [here](https://reference.aspose.com/gis/net/).
    question: Where can I find comprehensive documentation for Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for support
      and community engagement.
    question: How can I seek support or connect with the community for Aspose.GIS
      for .NET?
  - answer: Yes, you can download a free trial [here](https://releases.aspose.com/).
    question: Can I download a free trial of Aspose.GIS for .NET?
  - answer: You can purchase the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Jak przyciąć cechy warstwy przy użyciu Aspose.GIS dla .NET
url: /pl/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak przyciąć cechy warstwy

## Wprowadzenie
W tym samouczku nauczysz się **jak przyciąć warstwę** przy użyciu Aspose.GIS dla .NET, potężnej biblioteki, która umożliwia **przycinanie rastra za pomocą wielokąta**, **wyodrębnianie rozmiaru komórki rastra** oraz **pobieranie zakresu rastra** dla precyzyjnej analizy geoprzestrzennej. Niezależnie od tego, czy przygotowujesz dane do mapy internetowej, przycinasz zdjęcia satelitarne, czy izolujesz obszar zainteresowania, ten przewodnik krok po kroku pokaże Ci dokładnie, jak szybko i niezawodnie wykonać zadanie.

## Szybkie odpowiedzi
- **Co oznacza „przycięcie warstwy”?** Przycina raster lub warstwę wektorową do granic podanej geometrii, odrzucając wszystko poza nią.  
- **Jaką geometrię użyto w tym przykładzie?** Wielokąt zdefiniowany w formacie WKT (Well‑Known Text).  
- **Czy mogę wyodrębnić rozmiar komórki po przycięciu?** Tak – właściwość `CellSize` zwraca szerokość i wysokość komórki rastra.  
- **Czy potrzebna jest licencja do uruchomienia kodu?** Licencja tymczasowa wystarcza do oceny; pełna licencja jest wymagana w środowisku produkcyjnym.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Co to jest „przycięcie warstwy”?
**Przycięcie warstwy oznacza ograniczenie zestawu danych do określonego obszaru geograficznego, odrzucając wszystko poza nim.** Operacja ta zmniejsza rozmiar pliku, przyspiesza dalsze przetwarzanie i skupia analizę na interesującym Cię regionie. Ograniczając dane do obszaru zainteresowania, upraszcza się także późniejsze procesy, takie jak stylizacja, analiza i publikacja, jednocześnie zachowując pierwotny układ współrzędnych i metadane.

## Dlaczego warto używać Aspose.GIS do przycinania?
**Aspose.GIS przetwarza pliki rastrowe do 2 GB bez ładowania całego obrazu do pamięci i obsługuje ponad 30 formatów rastrowych, w tym GeoTIFF, JPEG2000 i PNG.** Biblioteka oferuje jednowierszowe wywołanie `Crop`, automatyczną obsługę CRS oraz wielowątkową wydajność, dzięki czemu może przyciąć 500‑MB GeoTIFF w mniej niż sekundę na typowym serwerze.

## Wymagania wstępne
Zanim zagłębisz się w magię manipulacji geoprzestrzennej, upewnij się, że spełniasz następujące wymagania:

- Biblioteka Aspose.GIS dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.GIS w swoim projekcie .NET. Możesz ją pobrać [tutaj](https://releases.aspose.com/gis/net/).  
- Katalog dokumentów: Utwórz katalog do przechowywania dokumentów. Zastąp `"Your Document Directory"` w podanym kodzie rzeczywistą ścieżką do swojego katalogu dokumentów.

Teraz przejdźmy do przewodnika krok po kroku.

## Importowanie przestrzeni nazw
Przestrzeń nazw `Aspose.Gis` zawiera wszystkie podstawowe typy do obsługi rastra i wektorów. Zaimportuj ją, aby uzyskać dostęp do klas `Layer`, `Geometry` i powiązanych.

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Jak przyciąć warstwę za pomocą wielokąta?
`Crop` jest metodą klasy `Layer`, która wyodrębnia podzbiór rastra zdefiniowany przez geometrię.  
Wczytaj źródłowy raster, zdefiniuj geometrię wielokąta i wywołaj metodę `Crop` – cała operacja odbywa się w jednej linii kodu. Metoda zwraca nowy raster zawierający tylko piksele wewnątrz wielokąta, automatycznie zachowując pierwotny układ współrzędnych.

## Krok 1: Otwórz i przytnij warstwę (przytnij raster za pomocą wielokąta)
`Layer` reprezentuje zestaw danych rastrowych, który można otworzyć, zapytać i edytować.  
Klasa `Layer` reprezentuje zestaw danych rastrowych, który można otworzyć, zapytać i edytować. Otwieranie pliku GeoTIFF i przycinanie go za pomocą wielokąta izoluje obszar zainteresowania w kilku prostych instrukcjach.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## Krok 2: Pobierz informacje o rastrze (wyodrębnij rozmiar komórki rastra i pobierz zakres rastra)
`CellSize` podaje szerokość i wysokość każdej komórki rastra w jednostkach współrzędnych.  
`Extent` zwraca geograficzne ograniczenie (bounding box) rastra.  
Właściwość `CellSize` podaje szerokość i wysokość każdej komórki rastra w jednostkach współrzędnych, natomiast właściwość `Extent` zwraca geograficzne ograniczenie przyciętego rastra. Obie informacje są niezbędne do dalszych obliczeń, takich jak pomiar powierzchni czy reprojekcja.

```csharp
// read and print raster
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
```

## Krok 3: Wyświetlenie informacji
Wydrukuj wyodrębnione informacje, aby zrozumieć wpływ procesu przycinania na Twoje dane geoprzestrzenne.

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"source extent: {layer.GetExtent()}");
Console.WriteLine($"target extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
```

Powtarzaj te kroki w razie potrzeby, aby dopracować i dostosować dane geoprzestrzenne do konkretnych wymagań projektu.

## Typowe problemy i rozwiązania
| Problem | Rozwiązanie |
|-------|----------|
| **Nieprawidłowa orientacja wielokąta** | Upewnij się, że wielokąt WKT spełnia regułę prawej ręki (przeciwnie do ruchu wskazówek zegara dla pierścieni zewnętrznych). |
| **Brak odniesienia przestrzennego** | Sprawdź, czy źródłowy GeoTiff zawiera CRS; w przeciwnym razie ustaw je ręcznie przed przycięciem. |
| **Spowolnienie wydajności przy dużych rastrach** | Użyj `layer.Crop` na zredukowanej kopii lub przetwarzaj raster w kafelkach. |

## Najczęściej zadawane pytania
**P: Czy dostępna jest tymczasowa licencja dla Aspose.GIS dla .NET?**  
O: Tak, tymczasową licencję można uzyskać [tutaj](https://purchase.aspose.com/temporary-license/).

**P: Gdzie mogę znaleźć pełną dokumentację Aspose.GIS dla .NET?**  
O: Dokumentacja jest dostępna [tutaj](https://reference.aspose.com/gis/net/).

**P: Jak mogę uzyskać wsparcie lub połączyć się ze społecznością Aspose.GIS dla .NET?**  
O: Odwiedź [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) w celu uzyskania wsparcia i kontaktu ze społecznością.

**P: Czy mogę pobrać darmową wersję próbną Aspose.GIS dla .NET?**  
O: Tak, darmową wersję próbną można pobrać [tutaj](https://releases.aspose.com/).

**P: Gdzie mogę kupić Aspose.GIS dla .NET?**  
O: Bibliotekę można zakupić [tutaj](https://purchase.aspose.com/buy).

**P: Czy mogę przyciąć wiele warstw w jednym uruchomieniu?**  
O: Tak — iteruj po każdej warstwie i zastosuj to samo wywołanie `Crop` z żądaną geometrią.

**P: Czy API obsługuje inne formaty rastrowe (np. JPEG2000)?**  
O: Aspose.GIS obsługuje wszystkie formaty udostępniane przez podległe sterowniki GDAL, w tym JPEG2000, PNG i inne.

## Zakończenie
Korzystając z tego przewodnika, teraz wiesz **jak przyciąć warstwę** efektywnie przy użyciu Aspose.GIS dla .NET. Możesz łatwo **przyciąć raster za pomocą wielokąta**, **wyodrębnić rozmiar komórki rastra** oraz **pobrać zakres rastra**, aby dopasować je do potrzeb każdego projektu. Zapoznaj się z dalszymi API do reprojekcji, stylizacji rastra i analizy wektorowej, aby odblokować pełny potencjał swoich przepływów pracy geoprzestrzennej.

---

**Last Updated:** 2026-07-05  
**Tested With:** Aspose.GIS 24.10 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Jak utworzyć geometrię wielokąta przy użyciu Aspose.GIS dla .NET](/gis/net/geometry-creation/create-polygon-geometry/)
- [Pobierz atrybuty warstwy – Uzyskaj informacje o atrybutach warstwy przy użyciu Aspose.GIS dla .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Utwórz geometrię wielokąta w C# i sprawdź przecięcie przy użyciu Aspose.GIS dla .NET](/gis/net/geometry-analysis/check-geometries-intersection/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}