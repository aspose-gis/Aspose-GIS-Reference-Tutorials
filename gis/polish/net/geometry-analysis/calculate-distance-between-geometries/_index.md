---
title: Oblicz odległość między geometriami za pomocą Aspose.GIS
linktitle: Oblicz odległość między geometriami
second_title: Aspose.GIS .NET API
description: Dowiedz się, jak obliczać odległości między geometriami w .NET przy użyciu Aspose.GIS. Przewodnik krok po kroku z przykładami kodu. Ulepsz swoje aplikacje geoprzestrzenne.
weight: 21
url: /pl/net/geometry-analysis/calculate-distance-between-geometries/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Oblicz odległość między geometriami za pomocą Aspose.GIS

## Wstęp
dziedzinie programowania geoprzestrzennego umiejętność obliczania odległości pomiędzy różnymi geometriami jest najważniejsza. Niezależnie od tego, czy masz do czynienia z wielokątami, liniami czy punktami, znajomość odległości między nimi może mieć kluczowe znaczenie w różnych zastosowaniach, od mapowania po planowanie logistyki. Aspose.GIS dla .NET zapewnia potężne narzędzia do wykonywania takich obliczeń z łatwością i precyzją.
## Warunki wstępne
Zanim zaczniesz obliczać odległości pomiędzy geometriami przy użyciu Aspose.GIS dla .NET, upewnij się, że spełnione są następujące wymagania wstępne:
### Zainstaluj Aspose.GIS dla .NET
 Aby rozpocząć, musisz mieć zainstalowany Aspose.GIS for .NET w swoim systemie. Bibliotekę można pobrać ze strony[Strona z wersjami Aspose.GIS dla .NET](https://releases.aspose.com/gis/net/) i postępuj zgodnie z instrukcjami instalacji zawartymi w dokumentacji.
### Znajomość programowania .NET
Konieczne jest zapoznanie się z przykładami zawartymi w tym samouczku, jeśli chodzi o podstawową wiedzę na temat programowania .NET przy użyciu języka C#. Jeśli dopiero zaczynasz programować w środowisku .NET, przed kontynuowaniem rozważ zapoznanie się z podstawami języka C#.

## Importuj przestrzenie nazw
Zanim zaczniesz używać Aspose.GIS dla .NET do obliczania odległości pomiędzy geometriami, musisz zaimportować wymagane przestrzenie nazw do swojego projektu C#. Wykonaj poniższe kroki, aby zaimportować niezbędne przestrzenie nazw:
## Otwórz swój projekt C#
Przejdź do projektu C# w preferowanym zintegrowanym środowisku programistycznym (IDE), takim jak Visual Studio.
## Dodaj odniesienia do przestrzeni nazw
W pliku C#, w którym zamierzasz wykonywać obliczenia odległości, dodaj na początku pliku następujące odniesienia do przestrzeni nazw:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Podzielmy podany przykład na wiele kroków, aby zrozumieć, jak obliczyć odległość między geometriami za pomocą Aspose.GIS dla .NET:
## Krok 1: Utwórz geometrię wielokąta
```csharp
var polygon = new Polygon();
```
Ten krok tworzy nowe wystąpienie geometrii wielokąta.
## Krok 2: Zdefiniuj wielokątny pierścień zewnętrzny
```csharp
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 1),
    new Point(1, 1),
    new Point(1, 0),
    new Point(0, 0),
});
```
Tutaj definiujemy zewnętrzny pierścień wielokąta, określając sekwencję punktów tworzących granicę wielokąta.
## Krok 3: Utwórz geometrię ciągu linii
```csharp
var line = new LineString();
```
Ten krok inicjuje nowe wystąpienie geometrii ciągu linii.
## Krok 4: Dodaj punkty do ciągu linii
```csharp
line.AddPoint(2, 0);
line.AddPoint(1, 3);
```
Do ciągu linii dodajemy dwa punkty, określając jego kształt i trajektorię.
## Krok 5: Oblicz odległość
```csharp
double distance = polygon.GetDistanceTo(line);
```
W tym kroku obliczana jest odległość między wielokątem a ciągiem linii.
## Krok 6: Wynik wyjściowy
```csharp
Console.WriteLine(distance.ToString("F")); // 0,63
```
Na koniec drukujemy obliczoną odległość do konsoli, sformatowaną tak, aby wyświetlała dwa miejsca po przecinku.

## Wniosek
Obliczanie odległości pomiędzy geometriami jest podstawowym zadaniem w programowaniu geoprzestrzennym, a Aspose.GIS dla .NET upraszcza ten proces dzięki intuicyjnemu API. Wykonując kroki opisane w tym samouczku, możesz bez wysiłku obliczać odległości między wielokątami, liniami i punktami w aplikacjach .NET.
## Często zadawane pytania
### Czy Aspose.GIS dla .NET jest kompatybilny ze wszystkimi frameworkami .NET?
Tak, Aspose.GIS dla .NET jest kompatybilny z .NET Framework 4.6 i nowszymi.
### Czy mogę używać Aspose.GIS for .NET do wykonywania złożonych analiz przestrzennych?
Absolutnie! Aspose.GIS dla .NET oferuje szeroką gamę funkcjonalności do zaawansowanych zadań analizy przestrzennej.
### Czy Aspose.GIS dla .NET obsługuje geometrię 2D i 3D?
Tak, możesz pracować zarówno z geometrią 2D, jak i 3D, używając Aspose.GIS dla .NET.
### Czy mogę zintegrować Aspose.GIS dla .NET z innymi bibliotekami GIS?
Aspose.GIS dla .NET zapewnia interoperacyjność z innymi bibliotekami GIS, umożliwiając wykorzystanie dodatkowych funkcjonalności.
### Czy dostępna jest pomoc techniczna dla użytkowników Aspose.GIS dla .NET?
 Tak, użytkownicy Aspose.GIS dla .NET mogą uzyskać dostęp do pomocy technicznej poprzez Aspose[fora](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
