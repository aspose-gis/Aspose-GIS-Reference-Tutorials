---
title: Wyodrębnij funkcje do GeoJSON
linktitle: Wyodrębnij funkcje do GeoJSON
second_title: Aspose.GIS .NET API
description: Zapoznaj się z przewodnikiem krok po kroku dotyczącym używania Aspose.GIS dla .NET do wyodrębniania funkcji do GeoJSON. Z łatwością wykorzystaj moc GIS! #Aspose #GIS
weight: 23
url: /pl/net/layer-management/extract-features-to-geojson/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wyodrębnij funkcje do GeoJSON

## Wstęp
Witamy w naszym samouczku krok po kroku dotyczącym wyodrębniania funkcji do GeoJSON przy użyciu Aspose.GIS dla .NET! Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz swoją przygodę z programowaniem GIS, ten przewodnik przeprowadzi Cię przez proces, upewniając się, że wykorzystasz pełną moc Aspose.GIS dla .NET.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
-  Aspose.GIS dla .NET: Upewnij się, że masz zainstalowaną bibliotekę. Jeśli nie, możesz pobrać go ze strony[Strona Aspose.GIS dla .NET](https://releases.aspose.com/gis/net/).
-  Dane pliku kształtu: Przygotuj plik kształtu do wprowadzenia. Jeżeli potrzebujesz przykładowych danych, znajdziesz je w pliku[Dokumentacja Aspose.GIS](https://reference.aspose.com/gis/net/).
- Środowisko .NET: skonfiguruj środowisko .NET, aby uruchomić dostarczony kod.
- Katalog dokumentów: zdefiniuj ścieżkę do katalogu dokumentów we fragmencie kodu.
Teraz, gdy już wszystko masz na swoim miejscu, zacznijmy wyodrębniać funkcje do GeoJSON!
## Importuj przestrzenie nazw
Po pierwsze, uwzględnij w swoim kodzie niezbędne przestrzenie nazw:
```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
Te przestrzenie nazw są niezbędne do pracy z funkcjonalnościami Aspose.GIS.
## Krok 1: Otwórz wejściowy plik kształtu
```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Twój kod do przetwarzania wejściowego pliku kształtu znajduje się tutaj
}
```
 Otwórz wejściowy plik Shapefile za pomocą`VectorLayer.Open` metoda.
## Krok 2: Utwórz wyjściowy GeoJSON
```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Twój kod do tworzenia wyjściowego GeoJSON znajduje się tutaj
}
```
 Utwórz wynik GeoJSON za pomocą`VectorLayer.Create` metoda.
## Krok 3: Skopiuj atrybuty
```csharp
outputLayer.CopyAttributes(inputLayer);
```
 Skopiuj atrybuty z warstwy wejściowej do warstwy wyjściowej za pomocą`CopyAttributes` metoda.
## Krok 4: Cechy procesu
```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Twój kod do przetwarzania każdej funkcji wejściowej znajduje się tutaj
}
```
Iteruj po każdej funkcji w warstwie wejściowej i przetwarzaj ją indywidualnie.
## Krok 5: Filtruj funkcje według daty
```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```
Filtruj funkcje na podstawie warunku daty. W tym przykładzie pomija obiekty z datą urodzenia przed 1982 rokiem.
## Krok 6: Skonstruuj nową funkcję
```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```
Skonstruuj nowy obiekt dla warstwy wyjściowej, kopiując geometrię i wartości z obiektu wejściowego.
Gratulacje! Pomyślnie wyodrębniłeś funkcje do GeoJSON przy użyciu Aspose.GIS dla .NET.
## Wniosek
W tym samouczku omówiliśmy proces wyodrębniania funkcji do GeoJSON przy użyciu Aspose.GIS dla .NET. Ta potężna biblioteka otwiera świat możliwości rozwoju GIS. Eksperymentuj z różnymi zbiorami danych i funkcjonalnościami, aby uwolnić pełny potencjał Aspose.GIS.
## Często zadawane pytania
### P: Gdzie mogę znaleźć więcej dokumentacji?
 Odwiedzić[Dokumentacja Aspose.GIS](https://reference.aspose.com/gis/net/) w celu uzyskania szczegółowych informacji.
### P: Jak mogę uzyskać licencję tymczasową?
 Możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).
### P: Gdzie mogę szukać wsparcia?
 Dołącz[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33) za wsparcie społeczności i dyskusje.
### P: Czy dostępny jest bezpłatny okres próbny?
 Tak, możesz znaleźć bezpłatną wersję próbną[Tutaj](https://releases.aspose.com/).
### P: Gdzie mogę kupić Aspose.GIS dla .NET?
 Możesz kupić produkt[Tutaj](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
