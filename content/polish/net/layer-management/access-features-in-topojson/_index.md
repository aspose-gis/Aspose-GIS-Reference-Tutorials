---
title: Odblokowywanie funkcji TopoJSON za pomocą Aspose.GIS dla .NET
linktitle: Uzyskaj dostęp do funkcji w TopoJSON
second_title: Aspose.GIS .NET API
description: Poznaj Aspose.GIS dla .NET i naucz się krok po kroku uzyskiwać dostęp do funkcji TopoJSON. Zanurz się w dokumentację i bez wysiłku uwolnij możliwości geoprzestrzenne.
type: docs
weight: 15
url: /pl/net/layer-management/access-features-in-topojson/
---
## Wstęp
Aspose.GIS dla .NET to potężna biblioteka, która umożliwia programistom bezproblemową pracę z danymi geoprzestrzennymi. W tym samouczku zajmiemy się uzyskiwaniem dostępu do funkcji w TopoJSON przy użyciu Aspose.GIS dla .NET. TopoJSON to format reprezentujący cechy geograficzne w zwarty i wydajny sposób.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące elementy:
- Praktyczna znajomość C# i .NET.
-  Zainstalowana biblioteka Aspose.GIS dla .NET. Możesz go pobrać[Tutaj](https://releases.aspose.com/gis/net/).
-  Przykładowy plik TopoJSON do testów. Znajdziesz taki w[dokumentacja](https://reference.aspose.com/gis/net/).
## Importuj przestrzenie nazw
Zacznij od zaimportowania niezbędnych przestrzeni nazw do kodu C#:
```csharp
using Aspose.Gis;
using System;
using System.Text;
```
## Krok 1: Skonfiguruj swój projekt
Rozpocznij od utworzenia nowego projektu w C# i dodania Aspose.GIS dla .NET jako odniesienia. Upewnij się, że projekt jest skonfigurowany do korzystania z biblioteki.
## Krok 2: Załaduj dane TopoJSON
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "Your Document Directory";
string sampleTopoJsonPath = dataDir + "sample.topojson";
StringBuilder builder = new StringBuilder();
// Otwórz plik TopoJSON
using (VectorLayer layer = VectorLayer.Open(sampleTopoJsonPath, Drivers.TopoJson))
{
    // Iteruj po każdym obiekcie w warstwie
    foreach (Feature feature in layer)
    {
        // zdobądź własność identyfikacyjną
        int id = feature.GetValue<int>("id");
        // uzyskaj nazwę obiektu zawierającego tę funkcję
        string objectName = feature.GetValue<string>("topojson_object_name");
        // pobierz właściwość atrybutu nazwy, znajdującą się wewnątrz obiektu „właściwości”.
        string name = feature.GetValue<string>("name");
        // uzyskać geometrię elementu.
        string geometry = feature.Geometry.AsText();
        // Zbuduj ciąg wyjściowy
        builder.AppendFormat("Feature with ID {0}:\n", id);
        builder.AppendFormat("Object Name = {0}\n", objectName);
        builder.AppendFormat("Name        = {0}\n", name);
        builder.AppendFormat("Geometry    = {0}\n", geometry);
    }
}
// Wyświetl wynik
Console.WriteLine("Output:");
Console.WriteLine(builder.ToString());
```
## Wniosek
Gratulacje! Pomyślnie uzyskałeś dostęp do funkcji w TopoJSON przy użyciu Aspose.GIS dla .NET. W tym samouczku omówiono podstawowe kroki, od których możesz zacząć, ale dzięki bibliotece możesz odkryć znacznie więcej.
## Często zadawane pytania
### P: Gdzie mogę znaleźć więcej dokumentacji?
 Odwiedzić[Dokumentacja Aspose.GIS dla .NET](https://reference.aspose.com/gis/net/).
### P: Jak mogę pobrać Aspose.GIS dla .NET?
 Pobierz bibliotekę[Tutaj](https://releases.aspose.com/gis/net/).
### P: Gdzie mogę uzyskać wsparcie dla Aspose.GIS?
 Dołącz[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33) do pomocy.
### P: Czy dostępny jest bezpłatny okres próbny?
Tak, możesz uzyskać dostęp do bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).
### P: Jak kupić licencję?
 Kup licencję[Tutaj](https://purchase.aspose.com/buy).