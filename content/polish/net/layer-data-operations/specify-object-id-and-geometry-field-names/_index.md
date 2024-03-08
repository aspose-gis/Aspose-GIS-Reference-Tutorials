---
title: Określ identyfikator obiektu i nazwy pól geometrii
linktitle: Określ identyfikator obiektu i nazwy pól geometrii
second_title: Aspose.GIS .NET API
description: Odkryj magię GIS z Aspose.GIS dla .NET! Zarządzaj danymi geoprzestrzennymi bez wysiłku. Pobierz teraz i uwolnij moc inteligencji przestrzennej.
type: docs
weight: 20
url: /pl/net/layer-data-operations/specify-object-id-and-geometry-field-names/
---
## Wstęp
Wyruszenie w podróż do krainy systemów informacji geograficznej (GIS) przy użyciu Aspose.GIS dla .NET otwiera świat możliwości zarówno dla programistów, jak i entuzjastów. Ta potężna biblioteka umożliwia bezproblemową obsługę danych geoprzestrzennych. W tym samouczku przeprowadzimy Cię przez proces określania identyfikatora obiektu i nazw pól geometrii, kładąc podwaliny pod działania GIS.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
-  Aspose.GIS dla .NET: Pobierz i zainstaluj bibliotekę z[Tutaj](https://releases.aspose.com/gis/net/).
- Katalog dokumentów: skonfiguruj katalog dla swoich dokumentów, w którym będą przechowywane geobazy.
- Środowisko .NET: Upewnij się, że masz działające środowisko .NET.
## Importuj przestrzenie nazw
Aby rozpocząć, musisz zaimportować niezbędne przestrzenie nazw do swojego projektu. Te przestrzenie nazw zapewniają podstawowe klasy i metody interakcji z Aspose.GIS dla .NET.
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```
## Krok 1: Określ identyfikator obiektu i nazwy pól geometrii
W tym kroku dowiesz się, jak skonfigurować nazwy pól Identyfikator obiektu i Geometria dla danych GIS. Ma to kluczowe znaczenie dla efektywnego zarządzania danymi.
## Krok 1.1: Ustaw katalog dokumentów
Zacznij od zdefiniowania ścieżki do katalogu dokumentów:
```csharp
string dataDir = "Your Document Directory";
```
## Krok 1.2: Utwórz geobazę i zdefiniuj opcje
Utwórz bazę danych GeoDatabase z określonym identyfikatorem obiektu i nazwami pól geometrii:
```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Określ nazwę pola identyfikatora obiektu
        GeometryFieldName = "POINT",       // Określ nazwę pola Geometria
    };
```
## Krok 1.3: Utwórz i dodaj warstwę
Utwórz warstwę w GeoDatabase i dodaj obiekt o określonej geometrii:
```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  //Określ geometrię (w tym przypadku punkt)
    layer.Add(feature);
}
```
## Krok 1.4: Otwórz i pobierz dane z warstwy
Otwórz warstwę i pobierz z niej dane na podstawie podanego ID obiektu:
```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Wyjście: 1
}
```
## Wniosek
Gratulacje! Pomyślnie przeszedłeś przez proces określania identyfikatora obiektu i nazw pól geometrii przy użyciu Aspose.GIS dla .NET. Stanowi to solidną podstawę dla Twoich projektów GIS, umożliwiając łatwe zarządzanie danymi geoprzestrzennymi.
## Często Zadawane Pytania
### P: Czy mogę używać Aspose.GIS dla .NET w moich aplikacjach internetowych?
O: Tak, Aspose.GIS dla .NET jest odpowiedni zarówno dla aplikacji komputerowych, jak i internetowych, zapewniając wszechstronne możliwości geoprzestrzenne.
### P: Czy przed zakupem dostępna jest wersja próbna?
 Odp.: Tak, możesz poznać funkcje Aspose.GIS dla .NET w ramach bezpłatnej wersji próbnej[Tutaj](https://releases.aspose.com/).
### P: Jak mogę uzyskać tymczasową licencję na Aspose.GIS dla .NET?
 Odp.: Możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/) w celach ewaluacyjnych.
### P: Jakie systemy odniesień przestrzennych obsługuje Aspose.GIS dla .NET?
O: Aspose.GIS dla .NET obsługuje różne systemy odniesień przestrzennych, zapewniając elastyczność dla różnych zbiorów danych geograficznych.
### P: Gdzie mogę szukać pomocy lub omówić zapytania związane z Aspose.GIS?
 O: Odwiedź forum Aspose.GIS[Tutaj](https://forum.aspose.com/c/gis/33) za wsparcie i dyskusję.