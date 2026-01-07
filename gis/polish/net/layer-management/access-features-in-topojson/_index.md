---
date: 2026-01-07
description: Dowiedz się, jak pobierać właściwości obiektów z TopoJSON przy użyciu
  Aspose.GIS dla .NET i efektywnie odczytywać identyfikatory obiektów.
linktitle: Access Features in TopoJSON
second_title: Aspose.GIS .NET API
title: Pobierz właściwości cech z TopoJSON przy użyciu Aspose.GIS dla .NET
url: /pl/net/layer-management/access-features-in-topojson/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pobieranie właściwości obiektów z TopoJSON przy użyciu Aspose.GIS dla .NET

## Wprowadzenie
W tym samouczku dowiesz się, jak **pobierać właściwości obiektów** z pliku TopoJSON przy użyciu Aspose.GIS dla .NET. Niezależnie od tego, czy potrzebujesz odczytać wartości atrybutów, wyodrębnić geometrię, czy po prostu *uzyskać identyfikator obiektu* do dalszego przetwarzania, poniższe kroki poprowadzą Cię przez czyste, kompleksowe rozwiązanie. Po zakończeniu będziesz mógł wyciągnąć dowolną właściwość z danych TopoJSON i wykorzystać ją w aplikacjach .NET.

## Szybkie odpowiedzi
- **Co oznacza „pobieranie właściwości obiektów”?** Odnosi się do odczytywania wartości atrybutów (np. id, name) przypisanych do każdego obiektu geograficznego.  
- **Która biblioteka to obsługuje?** Aspose.GIS dla .NET udostępnia prosty interfejs API do obsługi TopoJSON.  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna wystarczy do testów; licencja komercyjna jest wymagana w środowisku produkcyjnym.  
- **Jakie wersje .NET są wspierane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Jak szybka jest operacja?** Ładowanie i iteracja po obiektach odbywa się w pamięci i jest odpowiednia dla większości średniej wielkości zestawów danych.

## Co to jest „pobieranie właściwości obiektów”?
Pobieranie właściwości obiektów oznacza dostęp do danych atrybutowych przechowywanych razem z każdym obiektem geograficznym w pliku TopoJSON. Właściwości te mogą obejmować identyfikatory, nazwy, klasyfikacje lub dowolne niestandardowe metadane opisujące obiekt.

## Dlaczego pobierać identyfikator obiektu?
Operacja **pobierania identyfikatora obiektu** jest często pierwszym krokiem w przepływach opartych na danych — takich jak filtrowanie, łączenie z zewnętrznymi tabelami czy wizualizacja konkretnych obiektów na mapie. Znając ID, możesz precyzyjnie określić, z którym obiektem pracujesz.

## Wymagania wstępne
Zanim rozpoczniemy, upewnij się, że masz:
- Znajomość C# i .NET.  
- Zainstalowaną bibliotekę Aspose.GIS dla .NET. Możesz ją pobrać [tutaj](https://releases.aspose.com/gis/net/).  
- Przykładowy plik TopoJSON do testów. Jeden znajdziesz w [dokumentacji](https://reference.aspose.com/gis/net/).

## Importowanie przestrzeni nazw
Rozpocznij od zaimportowania niezbędnych przestrzeni nazw do swojego kodu C#:
```csharp
using Aspose.Gis;
using System;
using System.Text;
```

## Krok 1: Konfiguracja projektu
Utwórz nowy projekt C# (Console App, ASP.NET itp.) i dodaj odwołanie do biblioteki Aspose.GIS dla .NET DLL. Upewnij się, że projekt celuje w obsługiwaną wersję .NET.

## Krok 2: Wczytanie danych TopoJSON i pobranie właściwości obiektów
```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
string sampleTopoJsonPath = dataDir + "sample.topojson";
StringBuilder builder = new StringBuilder();
// Open the TopoJSON file
using (VectorLayer layer = VectorLayer.Open(sampleTopoJsonPath, Drivers.TopoJson))
{
    // Iterate through each feature in the layer
    foreach (Feature feature in layer)
    {
        // get id property
        int id = feature.GetValue<int>("id");
        // get name of the object that contains this feature
        string objectName = feature.GetValue<string>("topojson_object_name");
        // get name attribute property, located inside 'properties' object
        string name = feature.GetValue<string>("name");
        // get geometry of the feature.
        string geometry = feature.Geometry.AsText();
        // Build the output string
        builder.AppendFormat("Feature with ID {0}:\n", id);
        builder.AppendFormat("Object Name = {0}\n", objectName);
        builder.AppendFormat("Name        = {0}\n", name);
        builder.AppendFormat("Geometry    = {0}\n", geometry);
    }
}
// Display the output
Console.WriteLine("Output:");
Console.WriteLine(builder.ToString());
```

W powyższym fragmencie kodu **uzyskujemy identyfikator obiektu** (`id`) oraz inne atrybuty (`name`, `topojson_object_name`). To jest sedno „pobierania właściwości obiektów” z źródła TopoJSON.

## Typowe problemy i rozwiązania
- **File not found** – Zweryfikuj, czy `sample.topojson` istnieje w podanym katalogu i czy ścieżka jest prawidłowa.  
- **Missing property** – Jeśli nazwa właściwości jest niepoprawna (np. literówka w `"name"`), `GetValue<T>` zgłosi wyjątek. Użyj `feature.TryGetValue<T>`, aby bezpiecznie obsłużyć opcjonalne właściwości.  
- **Large files** – W przypadku bardzo dużych plików TopoJSON rozważ przetwarzanie obiektów w partiach lub użycie API strumieniowego, aby zmniejszyć zużycie pamięci.

## Najczęściej zadawane pytania

**Q: Gdzie mogę znaleźć więcej dokumentacji?**  
A: Odwiedź [dokumentację Aspose.GIS dla .NET](https://reference.aspose.com/gis/net/).

**Q: Jak mogę pobrać Aspose.GIS dla .NET?**  
A: Pobierz bibliotekę [tutaj](https://releases.aspose.com/gis/net/).

**Q: Gdzie mogę uzyskać wsparcie dla Aspose.GIS?**  
A: Dołącz do [forum Aspose.GIS](https://forum.aspose.com/c/gis/33), aby uzyskać pomoc.

**Q: Czy dostępna jest darmowa wersja próbna?**  
A: Tak, darmową wersję próbną znajdziesz [tutaj](https://releases.aspose.com/).

**Q: Jak mogę zakupić licencję?**  
A: Licencję można nabyć [tutaj](https://purchase.aspose.com/buy).

**Q: Czy mogę używać tego kodu z .NET Core?**  
A: Oczywiście — Aspose.GIS obsługuje .NET Core 3.1 i nowsze wersje.

**Q: Co zrobić, jeśli chcę zapisać wyodrębnione właściwości do pliku CSV?**  
A: Po zbudowaniu obiektu `StringBuilder` możesz zapisać jego zawartość do pliku używając `File.WriteAllText("output.csv", builder.ToString());`.

## Zakończenie
Gratulacje! Nauczyłeś się, jak **pobierać właściwości obiektów** z pliku TopoJSON oraz **uzyskiwać identyfikator obiektu** przy użyciu Aspose.GIS dla .NET. Ta podstawa umożliwia budowanie bardziej zaawansowanych aplikacji geoprzestrzennych, przeprowadzanie analiz danych lub integrację danych GIS w dowolnym rozwiązaniu .NET.

---

**Last Updated:** 2026-01-07  
**Tested With:** Aspose.GIS for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}