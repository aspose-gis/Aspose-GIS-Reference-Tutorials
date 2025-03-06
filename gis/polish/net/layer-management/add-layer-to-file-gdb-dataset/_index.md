---
title: GIS Mastery — dodawaj warstwy do GDB za pomocą Aspose.GIS dla .NET
linktitle: Dodaj warstwę do zbioru danych GDB pliku
second_title: Aspose.GIS .NET API
description: Odblokuj moc GIS z Aspose.GIS dla .NET! Z tego samouczka krok po kroku dowiesz się, jak dodawać warstwy do zestawów danych File GDB. #dane geograficzne #Aspose #GIS
weight: 16
url: /pl/net/layer-management/add-layer-to-file-gdb-dataset/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GIS Mastery — dodawaj warstwy do GDB za pomocą Aspose.GIS dla .NET

## Wstęp
Czy jesteś gotowy na zwiększenie swoich możliwości GIS przy użyciu Aspose.GIS dla .NET? W tym przewodniku krok po kroku przeprowadzimy Cię przez proces dodawania warstwy do zbioru danych Geobazy Plikowej (GDB). Aspose.GIS dla .NET zapewnia zaawansowane funkcje do manipulowania informacjami geograficznymi, a dzięki temu samouczkowi będziesz w stanie bezproblemowo zintegrować dodatkowe warstwy ze swoimi zbiorami danych.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
-  Biblioteka Aspose.GIS dla .NET: Pobierz i zainstaluj bibliotekę z[Dokumentacja Aspose.GIS dla .NET](https://reference.aspose.com/gis/net/).
- Katalog dokumentów: Utwórz na swoim komputerze dedykowany katalog dokumentów do przechowywania i zarządzania plikami związanymi z GIS.
## Importuj przestrzenie nazw
W projekcie .NET pamiętaj o zaimportowaniu niezbędnych przestrzeni nazw, aby uzyskać dostęp do funkcjonalności Aspose.GIS. Użyj następującego fragmentu kodu:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Krok 1: Skopiuj katalog
Przed kontynuowaniem zduplikuj katalog zawierający zbiór danych GDB. Ten krok gwarantuje, że oryginalny zestaw danych pozostanie nienaruszony. Użyj dostarczonego fragmentu kodu:
```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```
## Krok 2: Otwórz zbiór danych i sprawdź możliwości tworzenia
 Otwórz zduplikowany zbiór danych i sprawdź, czy może tworzyć warstwy. Potwierdza to obecność`True` na wyjściu konsoli.
```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // PRAWDA
```
## Krok 3: Utwórz i wypełnij nową warstwę
Utwórz nową warstwę w zestawie danych, definiując jej system odniesień przestrzennych, atrybuty i przykładowy obiekt. Ten fragment kodu demonstruje proces:
```csharp
using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
{
    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
    var feature = layer.ConstructFeature();
    feature.SetValue("Name", "Name_1");
    feature.Geometry = new Point(12.21, 23.123, 20, -200);
    layer.Add(feature);
}
```
## Krok 4: Otwórz i zatwierdź dodaną warstwę
Otwórz właśnie utworzoną warstwę i sprawdź jej zawartość. Sprawdź liczbę i pobierz wartości atrybutów, używając następującego kodu:
```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // „Nazwa_1”
}
```
## Wniosek
Gratulacje! Pomyślnie nauczyłeś się, jak dodać warstwę do zbioru danych File GDB przy użyciu Aspose.GIS dla .NET. Dzięki tym nowo odkrytym umiejętnościom możesz efektywnie manipulować danymi geograficznymi w swoich projektach GIS.
## Często Zadawane Pytania
### P: Czy mogę używać Aspose.GIS dla .NET z innymi bibliotekami GIS?
Aspose.GIS dla .NET został zaprojektowany do niezależnej pracy, ale można go zintegrować z innymi bibliotekami w celu zwiększenia funkcjonalności.
### P: Czy dostępna jest licencja tymczasowa do celów testowych?
 Tak, możesz uzyskać licencję tymczasową od[Tutaj](https://purchase.aspose.com/temporary-license/) do testowania i oceny.
### P: Jakie systemy odniesień przestrzennych obsługuje Aspose.GIS dla .NET?
Aspose.GIS dla .NET obsługuje szeroką gamę systemów odniesień przestrzennych, zapewniając elastyczność w obsłudze danych geograficznych.
### P: Czy mogę przyczynić się do społeczności Aspose.GIS?
 Absolutnie! Dołącz do dyskusji i podziel się swoimi doświadczeniami na stronie[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33).
### P: Gdzie mogę znaleźć szczegółową dokumentację Aspose.GIS dla .NET?
 Zapoznaj się z obszerną dokumentacją[Tutaj](https://reference.aspose.com/gis/net/) aby uzyskać szczegółowe informacje na temat Aspose.GIS dla .NET.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
