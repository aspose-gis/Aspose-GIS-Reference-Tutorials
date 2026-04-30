---
date: 2026-04-30
description: Dowiedz się, jak odczytać ObjectID z warstwy File Geodatabase przy użyciu
  Aspose.GIS dla .NET. Przewodnik krok po kroku, wymagania wstępne i wskazówki rozwiązywania
  problemów.
keywords:
- how to read objectid
- Aspose.GIS File GDB
- read object id .NET
linktitle: Odczytaj ID obiektu z warstwy File GDB
second_title: Aspose.GIS .NET API
title: Jak odczytać ObjectID z warstwy File GDB przy użyciu Aspose.GIS
url: /pl/net/layer-data-operations/read-object-id-from-file-gdb-layer/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak odczytać ObjectID z warstwy File GDB przy użyciu Aspose.GIS

## Wprowadzenie
Jeśli potrzebujesz wyodrębnić wartości **ObjectID** z warstwy File Geodatabase (GDB), ten samouczek pokaże Ci **jak odczytać ObjectID** szybko przy użyciu Aspose.GIS dla .NET. Przeprowadzimy Cię przez niezbędną konfigurację, dokładny kod, którego potrzebujesz, oraz praktyczne wskazówki, aby uniknąć typowych pułapek. Po zakończeniu będziesz mógł zintegrować pobieranie ObjectID z dowolnym przepływem pracy geoprzestrzennej w .NET.

## Szybkie odpowiedzi
- **Co reprezentuje ObjectID?** Unikalny identyfikator dla każdego obiektu w warstwie GIS.  
- **Jaki sterownik jest wymagany?** `Drivers.FileGdb` dla plików File Geodatabase.  
- **Czy potrzebna jest licencja na ten kod?** Wersja próbna działa w środowisku deweloperskim; licencja komercyjna jest wymagana w produkcji.  
- **Czy mogę używać tego z .NET Core?** Tak, Aspose.GIS obsługuje .NET Framework i .NET Core.  
- **Czy istnieje specjalne postępowanie przy dużych zestawach danych?** Iteruj przy użyciu instrukcji `using`, aby zapewnić szybkie zwalnianie zasobów.

## Co to jest ObjectID i dlaczego go odczytywać?
ObjectID (często nazywany `OBJECTID` lub `FID`) jest kluczem podstawowym, który jednoznacznie identyfikuje każdy obiekt w warstwie GIS. Dostęp do niego jest niezbędny, gdy trzeba:

- Zaktualizować lub usunąć konkretne obiekty.  
- Powiązać obiekty pomiędzy wieloma warstwami.  
- Wykonać szybkie wyszukiwania bez skanowania tabel atrybutów.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

1. **Visual Studio** (dowolna aktualna wersja) – do pisania i uruchamiania kodu C#.  
2. **Aspose.GIS for .NET** – pobierz go ze [strony pobierania](https://releases.aspose.com/gis/net/).  
3. **Podstawową znajomość C#** – znajomość pętli i wyjścia konsoli.

## Importowanie przestrzeni nazw
Najpierw dodaj odwołanie do biblioteki Aspose.GIS (przez NuGet lub bezpośredni plik DLL) i zaimportuj wymagane przestrzenie nazw:

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Przewodnik krok po kroku

### Krok 1: Zdefiniuj katalog danych
Określ folder, w którym znajduje się plik `.gdb`.

```csharp
string dataDir = "Your Document Directory";
```

Zastąp `"Your Document Directory"` bezwzględną ścieżką do folderu zawierającego `test.gdb`.

### Krok 2: Otwórz zestaw danych i docelową warstwę
Utwórz instancję `Dataset` przy użyciu sterownika File GDB, a następnie otwórz żądaną warstwę (zastąp `"layer"` nazwą swojej warstwy).

```csharp
string path = dataDir + "test.gdb";
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    // Code to read object IDs goes here
}
```

Instrukcje `using` zapewniają automatyczne zwalnianie uchwytów plików.

### Krok 3: Iteruj przez wszystkie obiekty
Iteruj po każdym obiekcie w warstwie. To tutaj wyodrębnimy ObjectID.

```csharp
foreach (var feature in layer)
{
    // Code to process each feature goes here
}
```

### Krok 4: Pobierz i wyświetl ObjectID
Wewnątrz pętli wywołaj `GetValue<int>("OBJECTID")`, aby pobrać identyfikator całkowitoliczbowy i wypisać go.

```csharp
Console.WriteLine(feature.GetValue<int>("OBJECTID"));
```

Uruchomienie programu wypisze listę wartości ObjectID w konsoli, po jednej w każdej linii.

## Typowe problemy i rozwiązywanie

| Objaw | Prawdopodobna przyczyna | Rozwiązanie |
|-------|--------------------------|------------|
| **`ArgumentException: No such layer`** | Nieprawidłowa nazwa warstwy | Sprawdź dokładną nazwę w GDB (uwzględniając wielkość liter). |
| **`FileNotFoundException`** | Nieprawidłowa ścieżka do `.gdb` | Użyj `Path.Combine(dataDir, "test.gdb")` i dokładnie sprawdź folder. |
| **`InvalidOperationException` when reading OBJECTID** | Nazwa atrybutu różni się (np. `FID`) | Sprawdź schemat za pomocą `layer.GetFields()` i dostosuj nazwę pola. |
| **Performance slowdown on large layers** | Ładowanie wszystkich obiektów jednocześnie | Przetwarzaj obiekty partiami lub użyj podejścia opartego na kursorze, jeśli jest wspierane. |

## FAQ

### Czy mogę używać Aspose.GIS dla .NET z innymi językami programowania?
Aspose.GIS dla .NET jest specjalnie zaprojektowany dla aplikacji .NET. Jednak Aspose oferuje także biblioteki dla Javy i innych platform.

### Czy dostępna jest darmowa wersja próbna Aspose.GIS?
Tak, możesz pobrać darmową wersję próbną Aspose.GIS dla .NET ze [strony internetowej](https://releases.aspose.com/gis/net/).

### Jak mogę uzyskać wsparcie techniczne dla Aspose.GIS?
Jeśli napotkasz jakiekolwiek problemy lub masz pytania dotyczące Aspose.GIS, możesz odwiedzić [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) w celu uzyskania pomocy.

### Czy mogę zakupić tymczasową licencję na Aspose.GIS?
Tak, możesz uzyskać tymczasową licencję na stronie Aspose w celu testowania i oceny.

### Gdzie mogę znaleźć pełną dokumentację Aspose.GIS dla .NET?
Możesz odwołać się do [dokumentacji](https://reference.aspose.com/gis/net/) po szczegółowe informacje na temat korzystania z API i funkcji Aspose.GIS.

## Najczęściej zadawane pytania

**Q: Co zrobić, jeśli moja warstwa używa innej nazwy pola dla unikalnego identyfikatora?**  
A: Zastąp `"OBJECTID"` w `GetValue<int>("OBJECTID")` rzeczywistą nazwą pola (np. `"FID"` lub `"ID"`).

**Q: Czy można zapisać wartości ObjectID z powrotem do innego pliku?**  
A: Tak, możesz utworzyć nową kolekcję `Feature` lub wyeksportować do CSV używając standardowego I/O .NET po pobraniu identyfikatorów.

**Q: Czy Aspose.GIS obsługuje odczyt ObjectID z plików shapefile?**  
A: Oczywiście. Użyj `Drivers.Shapefile` zamiast `Drivers.FileGdb`, a ten sam wzorzec `GetValue<int>("OBJECTID")` działa.

**Q: Jak obsłużyć hasłem zabezpieczoną bazę File GDB?**  
A: Podaj hasło przy otwieraniu zestawu danych: `Dataset.Open(path, Drivers.FileGdb, new OpenOptions { Password = "yourPwd" })`.

**Q: Czy mogę uruchomić ten kod na Linuksie?**  
A: Tak, Aspose.GIS dla .NET jest wieloplatformowy i działa na Linuksie z .NET Core/5+.

**Ostatnia aktualizacja:** 2026-04-30  
**Testowano z:** Aspose.GIS for .NET 24.11 (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}