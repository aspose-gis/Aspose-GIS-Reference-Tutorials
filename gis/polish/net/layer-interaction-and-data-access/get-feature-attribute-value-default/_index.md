---
title: Uzyskaj wartość atrybutu funkcji (domyślnie)
linktitle: Uzyskaj wartość atrybutu funkcji (domyślnie)
second_title: Aspose.GIS .NET API
description: Odblokuj moc Aspose.GIS dla .NET! Dzięki temu przewodnikowi krok po kroku możesz łatwo pobierać wartości atrybutów funkcji i nimi manipulować. Pobierz teraz wersję próbną!
type: docs
weight: 14
url: /pl/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
---
## Wstęp
Witamy w świecie Aspose.GIS dla .NET! W tym obszernym przewodniku zagłębimy się w zawiłości pobierania wartości atrybutów obiektów przy użyciu potężnych możliwości Aspose.GIS. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz, ten samouczek przeprowadzi Cię krok po kroku, dzięki czemu wykorzystasz pełny potencjał tego niezwykłego narzędzia.
## Warunki wstępne
Zanim rozpoczniemy tę przygodę z kodowaniem, upewnij się, że spełniasz następujące wymagania wstępne:
- Praktyczna znajomość C# i .NET Framework.
-  Zainstalowany Aspose.GIS dla .NET. Jeśli nie, pobierz go z[Tutaj](https://releases.aspose.com/gis/net/).
- Edytor kodu, taki jak Visual Studio, do płynnego działania.
## Importuj przestrzenie nazw
W projekcie C# pamiętaj o uwzględnieniu niezbędnych przestrzeni nazw:
```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
Podzielmy teraz każdy przykład na serię łatwych do wykonania kroków.
## Uzyskaj wartość atrybutu funkcji (domyślnie)
### Krok 1: Skonfiguruj środowisko
Rozpocznij od zdefiniowania ścieżki do katalogu dokumentów:
```csharp
string dataDir = "Your Document Directory";
```
### Krok 2: Utwórz warstwę GeoJson
Utwórz warstwę GeoJson i zdefiniuj atrybut z wartościami domyślnymi:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```
### Krok 3: Skonstruuj funkcję
Skonstruuj funkcję, korzystając ze zdefiniowanego atrybutu:
```csharp
    Feature feature = layer.ConstructFeature();
```
### Krok 4: Pobierz wartości
Pobierz wartości atrybutów w różnych scenariuszach:
```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // wartość == zero
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // wartość == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // wartość == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```
## Ustawianie wartości domyślnych
### Krok 1: Utwórz kolejną warstwę GeoJson
Powtórz proces z inną warstwą GeoJsona i podwójnym atrybutem:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```
### Krok 2: Skonstruuj funkcję (ponownie)
```csharp
    Feature feature = layer.ConstructFeature();
```
### Krok 3: Pobierz i ustaw wartości
Pobierz i ustaw wartości atrybutów, pokazując wartości domyślne:
```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); // wartość == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); // wartość == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); // wartość == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```
Gratulacje! Udało Ci się wykorzystać moc Aspose.GIS dla .NET w pobieraniu i manipulowaniu wartościami atrybutów obiektów.
## Wniosek
W tym samouczku zbadaliśmy niuanse pobierania wartości atrybutów obiektów przy użyciu Aspose.GIS dla .NET. Dzięki intuicyjnemu API i solidnym możliwościom Aspose.GIS otwiera świat możliwości rozwoju GIS w środowiskach .NET.
## Często Zadawane Pytania
### Czy Aspose.GIS jest kompatybilny z .NET Core?
Tak, Aspose.GIS jest w pełni kompatybilny z .NET Core, zapewniając obsługę wielu platform.
### Czy mogę używać Aspose.GIS w projektach komercyjnych?
Absolutnie! Aspose.GIS jest dostarczany z licencją komercyjną, która pozwala na używanie go w aplikacjach komercyjnych bez żadnych ograniczeń.
### Gdzie mogę znaleźć dodatkowe wsparcie i zasoby?
 Odwiedzić[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33) o wsparcie społeczności i poznaj[dokumentacja](https://reference.aspose.com/gis/net/) w celu uzyskania szczegółowych informacji.
### Czy dostępny jest bezpłatny okres próbny?
 Tak, możesz eksplorować Aspose.GIS w ramach bezpłatnej wersji próbnej. Pobierz to[Tutaj](https://releases.aspose.com/).
### Jak uzyskać tymczasową licencję do celów testowych?
 Informacje o licencjach tymczasowych można znaleźć na stronie[Tutaj](https://purchase.aspose.com/temporary-license/).