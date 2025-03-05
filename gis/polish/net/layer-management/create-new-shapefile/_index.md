---
title: Utwórz nowy plik kształtu
linktitle: Utwórz nowy plik kształtu
second_title: Aspose.GIS .NET API
description: Dowiedz się, jak utworzyć nowy plik kształtu przy użyciu Aspose.GIS dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku i odblokuj moc manipulacji danymi przestrzennymi.
type: docs
weight: 12
url: /pl/net/layer-management/create-new-shapefile/
---
## Wstęp
Jeśli zagłębiasz się w rozwój systemów informacji geograficznej (GIS) za pomocą .NET, Aspose.GIS jest rozwiązaniem dla Ciebie. Ta potężna biblioteka umożliwia programistom bezproblemową pracę z danymi przestrzennymi, a w tym samouczku poprowadzimy Cię przez proces tworzenia nowego pliku kształtu przy użyciu Aspose.GIS dla .NET.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Podstawowa znajomość języka programowania C#.
- Program Visual Studio zainstalowany na Twoim komputerze.
-  Biblioteka Aspose.GIS dla .NET. Możesz go pobrać[Tutaj](https://releases.aspose.com/gis/net/).
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
Rozpocznij od utworzenia nowego projektu C# w programie Visual Studio i dołącz bibliotekę Aspose.GIS.
## Krok 2: Zdefiniuj katalog dokumentów
```csharp
string dataDir = "Your Document Directory";
```
Zastąp „Twój katalog dokumentów” rzeczywistą ścieżką, w której chcesz zapisać nowy plik kształtu.
## Krok 3: Utwórz warstwę wektorową
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    //dodaj atrybuty przed dodaniem funkcji
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
Ten segment kodu konfiguruje warstwę wektorową i definiuje atrybuty Twoich funkcji.
## Krok 4: Dodaj funkcje
### Przypadek 1: Ustawia wartości indywidualnie
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
### Przypadek 2: Ustawia nowe wartości dla wszystkich atrybutów
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
## Wniosek
 Gratulacje! Pomyślnie utworzyłeś nowy plik kształtu przy użyciu Aspose.GIS dla .NET. W tym samouczku omówiono podstawy konfigurowania projektu, definiowania atrybutów i dodawania funkcji. W miarę dalszej eksploracji zapoznaj się z[dokumentacja](https://reference.aspose.com/gis/net/) dla zaawansowanych funkcji i funkcjonalności.
## Często Zadawane Pytania
### P: Czy mogę używać Aspose.GIS z innymi językami programowania?
Aspose.GIS obsługuje przede wszystkim .NET, ale dostępne są również wersje dla Java.
### P: Czy dostępny jest bezpłatny okres próbny?
 Tak, możesz uzyskać dostęp do bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).
### P: Gdzie mogę znaleźć wsparcie dla Aspose.GIS?
 Odwiedzić[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33) za wsparcie społeczności i dyskusje.
### P: Jak mogę uzyskać licencję tymczasową?
 Zdobądź tymczasową licencję[Tutaj](https://purchase.aspose.com/temporary-license/).
### P: Gdzie mogę kupić Aspose.GIS dla .NET?
 Można kupić bibliotekę[Tutaj](https://purchase.aspose.com/buy).