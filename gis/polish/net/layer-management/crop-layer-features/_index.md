---
date: 2026-01-13
description: Dowiedz się, jak przycinać elementy warstwy za pomocą Aspose.GIS dla
  .NET, w tym jak przycinać rastry przy użyciu wielokąta, wyodrębniać rozmiar komórki
  rastra oraz uzyskiwać zakres rastra. Pobierz bezpłatną wersję próbną już teraz.
linktitle: How to Crop Layer Features
second_title: Aspose.GIS .NET API
title: Jak przyciąć obiekty warstwy przy użyciu Aspose.GIS dla .NET
url: /pl/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak przyciąć warstwę funkcji

## Introduction
W tym samouczku nauczysz się **how to crop layer** funkcji przy użyciu Aspose.GIS dla .NET, potężnego podejścia, które pozwala **crop raster with polygon**, **extract raster cell size** oraz **retrieve raster extent** w celu precyzyjnej analizy geoprzestrzennej. Niezależnie od tego, czy przygotowujesz dane do mapy internetowej, przycinasz zdjęcia satelitarne, czy izolujesz obszar zainteresowania, ten przewodnik krok po kroku pokaże Ci dokładnie, jak wykonać zadanie.

## Quick Answers
- **Co oznacza „crop layer”?** Przycina warstwę rastrową lub wektorową do granic dostarczonej geometrii.  
- **Jaką geometrię użyto w tym przykładzie?** Poligon zdefiniowany w formacie WKT.  
- **Czy mogę wyodrębnić rozmiar komórki po przycięciu?** Tak – właściwość `CellSize` dostarcza tę informację.  
- **Czy potrzebuję licencji do uruchomienia kodu?** Licencja tymczasowa wystarcza do oceny; pełna licencja jest wymagana w produkcji.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## What is “how to crop layer”?
Przycinanie warstwy oznacza ograniczenie zestawu danych do określonego obszaru geograficznego, odrzucając wszystko poza zdefiniowanym kształtem. Redukuje to rozmiar pliku, przyspiesza przetwarzanie i skupia analizę na interesującym Cię regionie.

## Why use Aspose.GIS for cropping?
- **High‑performance raster handling** – idealne dla dużych plików GeoTiff.  
- **Simple API** – jednowierszowe wywołanie `Crop` z dowolną geometrią.  
- **Full .NET compatibility** – działa w aplikacjach desktop, serwerowych i chmurowych.  
- **Accurate spatial reference handling** – automatycznie zachowuje informacje o CRS.

## Prerequisites
Zanim zagłębisz się w magię manipulacji geoprzestrzennej, upewnij się, że spełniasz następujące wymagania:

- Aspose.GIS for .NET Library: Upewnij się, że biblioteka Aspose.GIS jest zainstalowana w Twoim projekcie .NET. Możesz ją pobrać [tutaj](https://releases.aspose.com/gis/net/).  
- Document Directory: Utwórz katalog do przechowywania dokumentów. Zastąp `"Your Document Directory"` w podanym kodzie rzeczywistą ścieżką do swojego katalogu dokumentów.

Teraz przejdźmy do przewodnika krok po kroku.

## Import Namespaces
Rozpocznij od zaimportowania niezbędnych przestrzeni nazw, aby w pełni wykorzystać możliwości Aspose.GIS:

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Step 1: Open and Crop the Layer (crop raster with polygon)
Rozpocznij od otwarcia warstwy GeoTiff i przycięcia jej na podstawie zdefiniowanego poligonu. Zapewnia to, że Twoje dane geoprzestrzenne są ograniczone do określonego obszaru zainteresowania.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## Step 2: Retrieve Raster Information (extract raster cell size & retrieve raster extent)
Po przycięciu warstwy wyodrębnij kluczowe informacje o danych rastrowych, takie jak rozmiar komórki, system odniesień przestrzennych oraz granice.

```csharp
// read and print raster
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
```

## Step 3: Display Information
Wydrukuj wyodrębnione informacje, aby zrozumieć wpływ procesu przycinania na Twoje dane geoprzestrzenne.

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"source extent: {layer.GetExtent()}");
Console.WriteLine($"target extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
```

Powtarzaj te kroki w razie potrzeby, aby dopracować i dostosować dane geoprzestrzenne do konkretnych wymagań projektu.

## Common Issues and Solutions
| Issue | Solution |
|-------|----------|
| **Incorrect polygon orientation** | Upewnij się, że poligon WKT spełnia regułę prawej ręki (przeciwnie do ruchu wskazówek zegara dla pierścieni zewnętrznych). |
| **Missing spatial reference** | Zweryfikuj, czy źródłowy GeoTiff zawiera CRS; w przeciwnym razie ustaw go ręcznie przed przycięciem. |
| **Performance slowdown on huge rasters** | Użyj `layer.Crop` na kopii o niższej rozdzielczości lub przetwarzaj raster w kafelkach. |

## Frequently Asked Questions
### Q: Is a temporary license available for Aspose.GIS for .NET?
A: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).

### Q: Where can I find comprehensive documentation for Aspose.GIS for .NET?
A: The documentation is available [here](https://reference.aspose.com/gis/net/).

### Q: How can I seek support or connect with the community for Aspose.GIS for .NET?
A: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for support and community engagement.

### Q: Can I download a free trial of Aspose.GIS for .NET?
A: Yes, you can download a free trial [here](https://releases.aspose.com/).

### Q: Where can I purchase Aspose.GIS for .NET?
A: You can purchase the library [here](https://purchase.aspose.com/buy).

### Q: Can I crop multiple layers in a single run?
A: Yes—loop over each layer and apply the same `Crop` call with the desired geometry.

### Q: Does the API support other raster formats (e.g., JPEG2000)?
A: Aspose.GIS supports all formats that the underlying GDAL drivers expose, including JPEG2000, PNG, and more.

## Conclusion
Postępując zgodnie z tym przewodnikiem, teraz wiesz **how to crop layer** funkcje efektywnie przy użyciu Aspose.GIS dla .NET. Możesz łatwo **crop raster with polygon**, **extract raster cell size** oraz **retrieve raster extent**, aby dopasować je do potrzeb każdego projektu. Poznaj dalsze API do reprojekcji, stylizacji rastra i analizy wektorowej, aby odblokować pełny potencjał swoich przepływów pracy geoprzestrzennej.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ostatnia aktualizacja:** 2026-01-13  
**Testowano z:** Aspose.GIS 24.10 for .NET  
**Autor:** Aspose