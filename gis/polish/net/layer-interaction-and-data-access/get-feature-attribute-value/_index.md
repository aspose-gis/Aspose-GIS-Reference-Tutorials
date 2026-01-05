---
description: Dowiedz się, jak używać dynamicznego rzutowania typów w Aspose.GIS dla
  .NET, aby pobierać wartości atrybutów z pliku shapefile. Zawiera przykłady jawnego
  rzutowania typów.
linktitle: Get Feature Attribute Value using Dynamic Type Casting
second_title: Aspose.GIS .NET API
title: Pobierz wartość atrybutu cechy przy użyciu dynamicznego rzutowania typów
url: /pl/net/layer-interaction-and-data-access/get-feature-attribute-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pobieranie wartości atrybutu obiektu przy użyciu dynamicznego rzutowania typów

## Wprowadzenie
Witamy w świecie Aspose.GIS dla .NET, potężnej biblioteki, która umożliwia programistom .NET płynną pracę z danymi systemu informacji geograficznej (GIS). W tym samouczku odkryjesz, jak **dynamiczne rzutowanie typów** upraszcza proces pobierania wartości atrybutów obiektów z pliku shapefile, jednocześnie omawiając klasyczne podejście **jawnego rzutowania typów**. Niezależnie od tego, czy odczytujesz plik shapefile w aplikacji .NET, czy potrzebujesz **pobrać wartości atrybutów** do analiz, te techniki sprawią, że Twój kod będzie czystszy i bardziej elastyczny.

## Szybkie odpowiedzi
- **Co to jest dynamiczne rzutowanie typów?** Sposób w czasie wykonywania umożliwiający pobranie wartości atrybutów bez wcześniejszego określania docelowego typu.  
- **Dlaczego warto używać Aspose.GIS?** Udostępnia jednolite API do odczytu danych shapefile .NET i obsługuje oba sposoby rzutowania.  
- **Czy potrzebna jest licencja?** Dostępna jest bezpłatna wersja próbna; licencja komercyjna jest wymagana w środowisku produkcyjnym.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6 i nowsze.  
- **Czy mogę pobierać wartości atrybutów z dużych plików?** Tak — iteruj po obiektach efektywnie, jak pokazano w przykładach.

## Wymagania wstępne
Before we dive into the tutorial, make sure you have the following prerequisites in place:
- Podstawowa znajomość programowania w .NET.  
- Zainstalowane Visual Studio na komputerze.  
- Biblioteka Aspose.GIS dla .NET, którą możesz pobrać z [linku do pobrania](https://releases.aspose.com/gis/net/).  
- Znajomość pojęć i terminologii GIS.

## Importowanie przestrzeni nazw
To kickstart your project, ensure that you import the necessary namespaces. This step is crucial for accessing the functionality provided by Aspose.GIS for .NET. Include the following namespaces in your code:
```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Jak używać dynamicznego rzutowania typów do pobierania wartości atrybutów
Below is a step‑by‑step guide that walks you through setting up the project, opening a shapefile, and retrieving attribute values using both **explicit type casting** and **dynamic type casting**.

### Krok 1: Konfiguracja projektu
Create a new .NET project in Visual and reference the Aspose.GIS library.

### Krok 2: Definiowanie katalogu dokumentów
Set the path to your documents directory. This is where your shapefile (`InputShapeFile.shp`) is located.
```csharp
string dataDir = "Your Document Directory";
```

### Krok 3: Otwieranie warstwy wektorowej
Open the vector layer using Aspose.GIS. Make sure to specify the driver, in this case, the Shapefile driver.
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the vector layer goes here
}
```

### Krok 4: Pobieranie wartości atrybutów obiektów
Now, loop through each feature in the layer and retrieve attribute values. Aspose.GIS provides different ways to fetch attribute values.

#### Przypadek 1: Jawne rzutowanie typów
```csharp
for (int i = 0; i < layer.Count; i++)
{
    Feature feature = layer[i];
    Console.WriteLine("Entry {0} information\n ========================", i);
    string nameValue = feature.GetValue<string>("name"); // attribute name is case-sensitive
    int ageValue = feature.GetValue<int>("age");
    string dobValue = feature.GetValue<DateTime>("dob").ToString();
    Console.WriteLine("Attribute value for feature #{0} is: {1}, {2}", nameValue, ageValue, dobValue);
}
```

#### Przypadek 2: Dynamiczne rzutowanie typów
```csharp
for (int i = 0; i < layer.Count; i++)
{
    Feature feature = layer[i];
    Console.WriteLine("Entry {0} information\n ========================", i);
    var objName = feature.GetValue("name"); // attribute name is case-sensitive
    var objAge = feature.GetValue("age");
    var objDob = feature.GetValue("dob");
    Console.WriteLine("Attribute object for feature #{0} is: {1}, {2}", objName, objAge, objDob);
}
```

> **Porada:** Używaj dynamicznego rzutowania typów, gdy nie jesteś pewien dokładnego typu danych atrybutu lub gdy chcesz napisać kod generyczny działający na wielu shapefile'ach. Przejdź do jawnego rzutowania typów, gdy potrzebujesz bezpieczeństwa typów w czasie kompilacji.

## Typowe problemy i rozwiązania
- **Niezgodność nazwy atrybutu:** Nazwy atrybutów GIS są rozróżniane pod względem wielkości liter. Sprawdź dokładną pisownię w schemacie shapefile.  
- **Wartości null:** `GetValue` zwraca `null` dla brakujących atrybutów; obsłuż to odpowiednio, aby uniknąć `NullReferenceException`.  
- **Duże zestawy danych:** Iteruj przy użyciu `foreach` lub stronicowania, aby zmniejszyć zużycie pamięci.

## Najczęściej zadawane pytania
### P: Czy Aspose.GIS jest odpowiedni zarówno dla początkujących, jak i doświadczonych programistów?
O: Zdecydowanie! Aspose.GIS jest przeznaczony dla programistów o różnym poziomie umiejętności, oferując intuicyjne API do manipulacji danymi GIS.

### P: Czy mogę używać Aspose.GIS w moich projektach komercyjnych?
O: Tak, Aspose.GIS jest produktem komercyjnym. Szczegóły licencjonowania znajdziesz na [stronie zakupu](https://purchase.aspose.com/buy).

### P: Czy dostępne są tymczasowe licencje do celów testowych?
O: Tak, tymczasową licencję do testów możesz uzyskać [tutaj](https://purchase.aspose.com/temporary-license/).

### P: Gdzie mogę znaleźć wsparcie społeczności dla Aspose.GIS?
O: Dołącz do dyskusji na [forum Aspose.GIS](https://forum.aspose.com/c/gis/33), aby uzyskać pomoc i połączyć się z innymi użytkownikami.

### P: Czy istnieje bezpłatna wersja próbna Aspose.GIS?
O: Oczywiście! Możesz zapoznać się z funkcjami Aspose.GIS, pobierając bezpłatną wersję próbną [tutaj](https://releases.aspose.com/).

### P: Jak uzyskać wartości atrybutów shapefile bez znajomości ich typów?
O: Użyj podejścia dynamicznego rzutowania typów (`feature.GetValue("attributeName")`), które zwraca wartość jako `object`, którą możesz rzutować w czasie wykonywania.

### P: Czy mogę odczytać dane shapefile .NET w aplikacji .NET Core?
O: Tak, Aspose.GIS dla .NET w pełni obsługuje .NET Core, .NET 5 i nowsze wersje.

## Zakończenie
Gratulacje! Pomyślnie nauczyłeś się, jak używać Aspose.GIS dla .NET do pobierania wartości atrybutów obiektów przy użyciu zarówno **jawnego rzutowania typów**, jak i **dynamicznego rzutowania typów**. Te techniki umożliwiają efektywne **pobieranie danych atrybutów shapefile**, niezależnie od tego, czy tworzysz narzędzie GIS na pulpit, czy integrujesz analizy przestrzenne w usłudze internetowej.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ostatnia aktualizacja:** 2026-01-05  
**Testowano z:** Aspose.GIS for .NET (latest)  
**Autor:** Aspose