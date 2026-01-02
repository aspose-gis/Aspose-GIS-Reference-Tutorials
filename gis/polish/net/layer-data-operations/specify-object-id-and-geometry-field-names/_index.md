---
date: 2026-01-02
description: Dowiedz się, jak dodać punktową cechę, ustawiając nazwy pól i odczytując
  identyfikator obiektu przy użyciu Aspose.GIS dla .NET. Przewodnik krok po kroku
  dla programistów.
linktitle: Specify Object ID and Geometry Field Names
second_title: Aspose.GIS .NET API
title: Dodaj obiekt punktowy i określ nazwy pól Object ID i Geometry
url: /pl/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj cechę punktową i określ nazwy pól Object ID i Geometry

## Wprowadzenie
Rozpoczęcie podróży w świecie Systemów Informacji Geograficznej (GIS) przy użyciu Aspose.GIS for .NET otwiera przed programistami i entuzjastami wiele możliwości. W tym samouczku **dowiesz się, jak dodać cechę punktową**, a także **ustawić nazwy pól** i **odczytać wartości Object ID**, dając pełną kontrolę nad danymi przestrzennymi.

## Szybkie odpowiedzi
- **Jaki jest główny cel tego przewodnika?** Pokazać, jak dodać cechę punktową i skonfigurować nazwy pól Object ID i Geometry.  
- **Jakiej biblioteki użyto?** Aspose.GIS for .NET.  
- **Czy potrzebna jest licencja?** Dostępna jest bezpłatna wersja próbna; licencja jest wymagana w środowisku produkcyjnym.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Czy mogę odczytać Object ID po wstawieniu?** Tak – samouczek pokazuje, jak odczytać Object ID z warstwy.

## Wymagania wstępne
Zanim zagłębisz się w samouczek, upewnij się, że spełniasz następujące wymagania:
- Aspose.GIS for .NET: Pobierz i zainstaluj bibliotekę z [tutaj](https://releases.aspose.com/gis/net/).
- Katalog dokumentów: Utwórz katalog dla swoich dokumentów, aby przechowywać bazy geodanych.
- Środowisko .NET: Upewnij się, że masz działające środowisko .NET.

## Importowanie przestrzeni nazw
Aby rozpocząć, musisz zaimportować niezbędne przestrzenie nazw do swojego projektu. Przestrzenie nazw dostarczają niezbędnych klas i metod do interakcji z Aspose.GIS for .NET.

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## Krok 1: Dodaj cechę punktową i określ nazwy pól Object ID i Geometry
W tym kroku dowiesz się, jak skonfigurować nazwy pól Object ID i Geometry dla swoich danych GIS. Jest to kluczowe dla efektywnego zarządzania danymi oraz umożliwia późniejsze **odczytanie Object ID**.

### Krok 1.1: Ustaw katalog dokumentów
Zacznij od określenia ścieżki do katalogu dokumentów:

```csharp
string dataDir = "Your Document Directory";
```

### Krok 1.2: Utwórz bazę GeoDatabase i zdefiniuj opcje
Utwórz bazę GeoDatabase z żądanymi **nazwami pól** dla Object ID i Geometry:

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

### Krok 1.3: Utwórz i dodaj warstwę
Utwórz warstwę w bazie GeoDatabase i dodaj cechę reprezentującą geometrię punktu:

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

### Krok 1.4: Otwórz i pobierz dane z warstwy
Otwórz warstwę i pobierz cechę, którą właśnie dodałeś. To pokazuje, jak **odczytać Object ID** z zestawu danych:

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## Dlaczego ustawiać własne nazwy pól?
Dostosowanie nazw pól Object ID i Geometry daje elastyczność przy integracji z istniejącymi bazami danych lub przy przestrzeganiu konwencji nazewnictwa wymaganych przez aplikacje downstream. Dzięki temu dane są bardziej samowyjaśniające, co upraszcza utrzymanie i współpracę.

## Typowe pułapki i rozwiązywanie problemów
- **Brakujący katalog** – Upewnij się, że `dataDir` wskazuje istniejący folder; w przeciwnym razie `Dataset.Create` zgłosi wyjątek.
- **Konflikty nazw pól** – Jeśli pole o tej samej nazwie już istnieje w bazie geodanych, tworzenie zakończy się niepowodzeniem. Wybierz unikalne nazwy.
- **Niezgodność układu odniesienia przestrzennego** – Zawsze dopasowuj system odniesienia przestrzennego (np. WGS84) do danych, które zamierzasz przechowywać.

## Zakończenie
Gratulacje! Pomyślnie nauczyłeś się **dodawać cechę punktową**, **ustawiać nazwy pól** oraz **odczytywać Object ID** przy użyciu Aspose.GIS for .NET. Ta podstawa umożliwia tworzenie solidnych aplikacji GIS i zarządzanie danymi przestrzennymi z pewnością.

## Najczęściej zadawane pytania
### Q: Czy mogę używać Aspose.GIS for .NET w aplikacjach internetowych?
A: Tak, Aspose.GIS for .NET jest odpowiedni zarówno dla aplikacji desktopowych, jak i internetowych, oferując wszechstronne możliwości geoprzestrzenne.

### Q: Czy dostępna jest wersja próbna przed zakupem?
A: Tak, możesz zapoznać się z funkcjami Aspose.GIS for .NET, korzystając z bezpłatnej wersji próbnej dostępnej [tutaj](https://releases.aspose.com/).

### Q: Jak mogę uzyskać tymczasową licencję dla Aspose.GIS for .NET?
A: Tymczasową licencję możesz uzyskać [tutaj](https://purchase.aspose.com/temporary-license/) w celu oceny.

### Q: Jakie systemy odniesienia przestrzennego obsługuje Aspose.GIS for .NET?
A: Aspose.GIS for .NET obsługuje różne systemy odniesienia przestrzennego, zapewniając elastyczność dla różnych zestawów danych geograficznych.

### Q: Gdzie mogę uzyskać pomoc lub dyskutować o zapytaniach związanych z Aspose.GIS?
A: Odwiedź forum Aspose.GIS [tutaj](https://forum.aspose.com/c/gis/33) w celu uzyskania wsparcia i dyskusji.

## Dodatkowe często zadawane pytania

**Q: Czy mogę zmienić pole Object ID po utworzeniu warstwy?**  
A: Nie. Nazwa pola jest definiowana w momencie tworzenia warstwy; aby ją zmienić, musisz odtworzyć warstwę z nowym obiektem `FileGdbOptions`.

**Q: Jak pobrać inne wartości atrybutów oprócz Object ID?**  
A: Użyj `feature.GetValue<T>("FieldName")`, gdzie `FieldName` jest nazwą atrybutu, który chcesz odczytać.

**Q: Czy można dodać wiele cech punktowych w jednej partii?**  
A: Tak. Przejdź w pętli po swoich danych, utwórz cechę dla każdego punktu, ustaw jej geometrię i wywołaj `layer.Add(feature)` w tym samym bloku `using`.

**Q: Czy Aspose.GIS obsługuje inne typy geometrii?**  
A: Absolutnie. Możesz pracować z `LineString`, `Polygon`, `MultiPoint` i innymi, tworząc odpowiednie obiekty geometrii.

**Q: Co się stanie, jeśli spróbuję odczytać Object ID, które nie istnieje?**  
A: Dostęp do indeksu poza zakresem (np. `layer[10]`, gdy istnieje tylko jedna cecha) spowoduje wyrzucenie `IndexOutOfRangeException`. Zawsze najpierw sprawdzaj `layer.Count`.

---

**Ostatnia aktualizacja:** 2026-01-02  
**Testowano z:** Aspose.GIS for .NET 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}