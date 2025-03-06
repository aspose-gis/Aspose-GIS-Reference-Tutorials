---
title: Napisz GeoJSON do Stream
linktitle: Napisz GeoJSON do Stream
second_title: Aspose.GIS .NET API
description: Poznaj moc Aspose.GIS dla .NET! Napisz GeoJSON, aby przesyłać strumieniowo bez wysiłku. Pobierz teraz, aby uzyskać płynną integrację geoprzestrzenną.
weight: 25
url: /pl/net/layer-data-operations/write-geojson-to-stream/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Napisz GeoJSON do Stream

## Wstęp
Czy chcesz wykorzystać moc GeoJSON w swojej aplikacji .NET przy użyciu Aspose.GIS? Cóż, jesteś we właściwym miejscu! Ten przewodnik krok po kroku przeprowadzi Cię przez proces zapisywania GeoJSON do strumienia, wykorzystując niezawodne możliwości Aspose.GIS dla .NET.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
1. Biblioteka Aspose.GIS dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.GIS dla .NET. Możesz go pobrać[Tutaj](https://releases.aspose.com/gis/net/).
2. Katalog dokumentów: Ustaw katalog dokumentów w swoim projekcie i zanotuj jego ścieżkę.
Teraz zacznijmy od samouczka!
## Importuj przestrzenie nazw
Po pierwsze, pamiętaj o uwzględnieniu w kodzie niezbędnych przestrzeni nazw, aby uzyskać dostęp do funkcjonalności Aspose.GIS:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```
## Krok 1: Skonfiguruj katalog dokumentów
```csharp
string dataDir = "Your Document Directory";
```
Zastąp „Twój katalog dokumentów” rzeczywistą ścieżką do katalogu dokumentów.
## Krok 2: Utwórz strumień pamięci
```csharp
using (var memoryStream = new MemoryStream())
{
    // Kod kolejnych kroków znajduje się tutaj
}
```
## Krok 3: Utwórz warstwę wektorową za pomocą sterownika GeoJSON
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Kod kolejnych kroków znajduje się tutaj
}
```
## Krok 4: Zdefiniuj atrybuty funkcji
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```
## Krok 5: Skonstruuj i dodaj funkcje
```csharp
// Pierwsza funkcja
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);
// Druga funkcja
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```
## Krok 6: Wyświetl wyjście GeoJSON
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```
Gratulacje! Pomyślnie zapisałeś GeoJSON do strumienia przy użyciu Aspose.GIS dla .NET.
## Wniosek
tym samouczku omówiliśmy podstawowe kroki integracji Aspose.GIS dla .NET z projektem, skupiając się szczególnie na pisaniu GeoJSON do strumienia. Dzięki tym prostym, ale skutecznym krokom możesz zwiększyć możliwości geoprzestrzenne swojej aplikacji.
## Często Zadawane Pytania
### Czy mogę używać Aspose.GIS dla .NET zarówno w środowisku Windows, jak i Linux?
Tak, Aspose.GIS dla .NET jest kompatybilny zarówno z systemami Windows, jak i Linux.
### Czy dostępny jest bezpłatny okres próbny?
 Absolutnie! Możesz skorzystać z bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).
### Gdzie mogę znaleźć szczegółową dokumentację?
 Sprawdź dokumentację[Tutaj](https://reference.aspose.com/gis/net/).
### Jak mogę uzyskać licencję tymczasową?
 Dostępne są licencje tymczasowe[Tutaj](https://purchase.aspose.com/temporary-license/).
### Potrzebujesz pomocy lub masz więcej pytań?
 Odwiedź nasze forum pomocy[Tutaj](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
