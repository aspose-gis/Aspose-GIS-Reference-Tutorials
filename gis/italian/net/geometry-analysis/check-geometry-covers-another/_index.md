---
date: 2026-08-03
description: Scopri come creare linestring c# con Aspose.GIS per .NET, aggiungere
  punti a una linestring e eseguire un controllo punto su linea usando il metodo covers.
keywords:
- create linestring c#
- point on line check
- add points to linestring
- use covers method
lastmod: 2026-08-03
linktitle: Crea linestring c# – Verifica che la geometria copra un'altra
og_description: Crea linestring c# e verifica il punto su linea usando il metodo covers
  di Aspose.GIS. Scopri controlli geometrici precisi per applicazioni .NET. (150‑160
  caratteri)
og_image_alt: Developer guide showing linestring creation and covers check in C# with
  Aspose.GIS
og_title: Crea linestring c# – Verifica che la geometria copra un'altra (50‑60 caratteri)
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to create linestring c# with Aspose.GIS for .NET, add points
    to a linestring, and perform a point on line check using the covers method.
  headline: Create linestring c# – Check geometry covers another
  type: TechArticle
- description: Learn how to create linestring c# with Aspose.GIS for .NET, add points
    to a linestring, and perform a point on line check using the covers method.
  name: Create linestring c# – Check geometry covers another
  steps:
  - name: create a linestring object
    text: The `LineString` class represents a sequence of points connected by straight
      line segments in a two‑dimensional plane. Here, we instantiate a new `LineString`
      object, which represents a sequence of connected line segments in a two‑dimensional
      space.
  - name: add points to linestring
    text: '`AddPoint` appends a coordinate pair to the end of the `LineString` collection,
      preserving the order of insertion. We **add points to linestring** using the
      `AddPoint` method. In this example, we add two points: (0, 0) and (1, 1), forming
      a simple diagonal line segment.'
  - name: create a point object
    text: The `Point` class models a single location in a two‑dimensional coordinate
      system. Instantiate a `Point` object representing a single point in a two‑dimensional
      space. Here, we create a point at coordinates (0, 0).
  - name: perform a point on line check – does the line cover the point?
    text: '`Covers` determines whether the first geometry completely contains the
      second geometry, returning true only when every point of the second geometry
      lies inside the first. Use the `Covers` method to check if the line covers the
      point. In this case, it returns `True` because the point (0, 0) lies exac'
  - name: verify the reverse relationship – is the point covered by the line?
    text: '`CoveredBy` is the inverse of `Covers`; it returns true when the invoking
      geometry is entirely inside the target geometry. Similarly, use the `CoveredBy`
      method to check if the point is covered by the line. Since the point (0, 0)
      lies on the line, it also returns `True`.'
  type: HowTo
- questions:
  - answer: Yes, you can use Aspose.GIS for .NET in both commercial and non‑commercial
      projects after obtaining the appropriate license.
    question: Can I use Aspose.GIS for .NET in my commercial projects?
  - answer: Yes, Aspose.GIS for .NET is compatible with both .NET Framework and .NET
      Core environments.
    question: Is Aspose.GIS for .NET compatible with .NET Core?
  - answer: Yes, Aspose.GIS for .NET supports a wide range of GIS formats including
      Shapefile, GeoJSON, KML, and more.
    question: Does Aspose.GIS for .NET support various GIS formats?
  - answer: Aspose.GIS for .NET is a proprietary library developed by Aspose, so external
      contributions are not accepted. However, you can provide feedback and suggestions
      to improve the library.
    question: Can I contribute to the development of Aspose.GIS for .NET?
  - answer: Updates for Aspose.GIS for .NET are released regularly to introduce new
      features, enhancements, and bug fixes. Check the [website](https://releases.aspose.com/gis/net/)
      for the latest releases.
    question: How often are updates released for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- create linestring
- Aspose.GIS
- C# geometry analysis
title: Crea linestring c# – Verifica che la geometria copra un'altra
url: /it/net/geometry-analysis/check-geometry-covers-another/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Verifica che la geometria copra un'altra

## Introduzione
In questo tutorial imparerai **come creare linestring c#** usando Aspose.GIS per .NET, aggiungere punti a una linestring e eseguire un affidabile **controllo punto su linea** con i metodi `Covers` e `CoveredBy`. Che tu stia costruendo uno strumento di mappatura, eseguendo analisi spaziali o semplicemente abbia bisogno di verificare relazioni geometriche, padroneggiare queste operazioni darà alla tua applicazione la precisione necessaria.

## Risposte rapide
- **Cosa significa “create linestring c#”?** Significa istanziare un oggetto geometrico `LineString` e popolarlo con punti di coordinate.  
- **Quale metodo verifica se un punto si trova su una linea?** Usa il metodo `Covers` sul `LineString` o `CoveredBy` sul `Point`.  
- **Ho bisogno di una licenza per eseguire il campione?** Una licenza temporanea funziona per la valutazione; è necessaria una licenza completa per la produzione.  
- **È possibile utilizzare questo con .NET Core?** Sì, Aspose.GIS supporta .NET Framework e .NET Core.  
- **Quanti punti posso aggiungere a un linestring?** Non c'è un limite rigido; è possibile aggiungere tutti i punti necessari per la tua analisi spaziale.

## Che cos'è create linestring c#?
`LineString` è una forma geometrica costituita da un elenco ordinato di punti collegati da segmenti di linea retti. In C# lo crei istanziando la classe `LineString` dallo spazio dei nomi `Aspose.Gis.Geometries` e poi **add points to linestring** usando il metodo `AddPoint`. Questo oggetto funge da base per qualsiasi analisi spaziale lineare, come la mappatura di percorsi o il tracciamento di reti.

## Perché utilizzare Aspose.GIS per un controllo punto su linea?
`Covers` è un metodo predicato spaziale che restituisce true quando la prima geometria contiene completamente la seconda geometria.  
Aspose.GIS fornisce un'implementazione deterministica ad alta precisione dei predicati spaziali. Supporta oltre 50 formati GIS di input e output, può gestire reti lineari di centinaia di chilometri senza caricare l'intero dataset in memoria, ed è eseguibile su .NET Framework, .NET Core e .NET 5/6+. L'uso del metodo `Covers` garantisce che gli errori di arrotondamento dei floating‑point siano considerati, fornendo risultati affidabili di punto‑su‑linea anche in scenari aziendali esigenti.

## Prerequisiti
Prima di immergerti nell'uso di Aspose.GIS per .NET, assicurati di aver configurato i seguenti prerequisiti:

### 1. Installa Visual Studio
Assicurati di avere Visual Studio installato sul tuo sistema. Aspose.GIS per .NET si integra perfettamente con Visual Studio, offrendo un'esperienza di sviluppo fluida.

### 2. Ottieni Aspose.GIS per .NET
Scarica la libreria Aspose.GIS per .NET dal [website](https://releases.aspose.com/gis/net/). Puoi scaricare direttamente la libreria o utilizzare un gestore di pacchetti come NuGet per installarla nel tuo progetto.

### 3. Familiarità con .NET Framework
Una conoscenza di base del framework .NET e del linguaggio di programmazione C# è essenziale per utilizzare efficacemente Aspose.GIS per .NET.

### 4. Accesso alla documentazione e al supporto
Consulta la [documentation](https://reference.aspose.com/gis/net/) per informazioni dettagliate sulle API e le funzionalità di Aspose.GIS. In caso di problemi o domande, utilizza il [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) per assistenza.

### 5. Opzionale: licenza temporanea
Se stai esplorando Aspose.GIS per .NET, puoi ottenere una licenza temporanea dalla [temporary license page](https://purchase.aspose.com/temporary-license/) per valutare le funzionalità della libreria.

## Importa namespace
Prima di utilizzare Aspose.GIS per .NET nel tuo progetto, devi importare gli spazi dei nomi necessari:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Ora, analizziamo l'esempio fornito in più passaggi per capire come **check if one geometry covers another** usando Aspose.GIS per .NET.

## Come creare linestring c# – guida passo‑passo
Carica il tuo progetto, importa i namespace richiesti, e poi segui i cinque passaggi concisi di seguito. In poche righe di codice avrai un oggetto `LineString`, un oggetto `Point` e due controlli booleani che indicano se la linea copre il punto e se il punto è coperto dalla linea.

### Passo 1: crea un oggetto linestring
La classe `LineString` rappresenta una sequenza di punti collegati da segmenti di linea retti in un piano bidimensionale.  
```csharp
var line = new LineString();
```
Qui, istanziamo un nuovo oggetto `LineString`, che rappresenta una sequenza di segmenti di linea collegati in uno spazio bidimensionale.

### Passo 2: aggiungi punti a linestring
`AddPoint` aggiunge una coppia di coordinate alla fine della collezione `LineString`, preservando l'ordine di inserimento.  
```csharp
line.AddPoint(0, 0);
line.AddPoint(1, 1);
```
We **add points to linestring** using the `AddPoint` method. In this example, we add two points: (0, 0) and (1, 1), forming a simple diagonal line segment.

### Passo 3: crea un oggetto point
La classe `Point` modella una singola posizione in un sistema di coordinate bidimensionale.  
```csharp
var point = new Point(0, 0);
```
Instanzia un oggetto `Point` che rappresenta un singolo punto in uno spazio bidimensionale. Qui, creiamo un punto alle coordinate (0, 0).

### Passo 4: esegui un controllo punto su linea – la linea copre il punto?
`Covers` determina se la prima geometria contiene completamente la seconda geometria, restituendo true solo quando ogni punto della seconda geometria è all'interno della prima.  
```csharp
Console.WriteLine(line.Covers(point));    // True
```
Usa il metodo `Covers` per verificare se la linea copre il punto. In questo caso, restituisce `True` perché il punto (0, 0) si trova esattamente sulla linea.

### Passo 5: verifica la relazione inversa – il punto è coperto dalla linea?
`CoveredBy` è l'inverso di `Covers`; restituisce true quando la geometria invocante è interamente all'interno della geometria target.  
```csharp
Console.WriteLine(point.CoveredBy(line)); // True
```
Allo stesso modo, usa il metodo `CoveredBy` per verificare se il punto è coperto dalla linea. Poiché il punto (0, 0) è sulla linea, restituisce anch'esso `True`.

## Problemi comuni e soluzioni
| Problema | Perché succede | Soluzione |
|----------|----------------|-----------|
| `line.Covers(point)` restituisce `False` anche se il punto sembra sulla linea | Le coordinate del punto non sono esattamente le stesse a causa della precisione dei numeri floating‑point. | Usa `Math.Round` sulle coordinate o utilizza un controllo basato su tolleranza con `line.Distance(point) < epsilon`. |
| Manca `using Aspose.Gis.Geometries;` | Namespace non importato, causando errori di compilazione. | Assicurati che l'istruzione di import sia presente (vedi la sezione **Importa namespace**). |
| Eccezione di licenza a runtime | Nessuna licenza valida caricata per la produzione. | Carica una licenza temporanea o completa usando `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Domande frequenti

**Q: Posso usare Aspose.GIS per .NET nei miei progetti commerciali?**  
A: Sì, puoi usare Aspose.GIS per .NET sia in progetti commerciali che non‑commerciali dopo aver ottenuto la licenza appropriata.

**Q: Aspose.GIS per .NET è compatibile con .NET Core?**  
A: Sì, Aspose.GIS per .NET è compatibile sia con .NET Framework sia con ambienti .NET Core.

**Q: Aspose.GIS per .NET supporta vari formati GIS?**  
A: Sì, Aspose.GIS per .NET supporta un'ampia gamma di formati GIS includendo Shapefile, GeoJSON, KML e molti altri.

**Q: Posso contribuire allo sviluppo di Aspose.GIS per .NET?**  
A: Aspose.GIS per .NET è una libreria proprietaria sviluppata da Aspose, quindi i contributi esterni non sono accettati. Tuttavia, puoi fornire feedback e suggerimenti per migliorare la libreria.

**Q: Quanto spesso vengono rilasciati aggiornamenti per Aspose.GIS per .NET?**  
A: Gli aggiornamenti per Aspose.GIS per .NET vengono rilasciati regolarmente per introdurre nuove funzionalità, miglioramenti e correzioni di bug. Controlla il [website](https://releases.aspose.com/gis/net/) per le ultime versioni.

## Conclusione
Seguendo i passaggi sopra, ora sai come **create linestring c#**, **add points to linestring**, e eseguire un affidabile **point on line check** usando i metodi `Covers` e `CoveredBy`. Questa capacità potenzia le funzionalità di analisi spaziale del tuo software e apre la porta a operazioni GIS più avanzate come la validazione di percorsi, controlli di topologia di rete e query di prossimità.

---

**Ultimo aggiornamento:** 2026-08-03  
**Testato con:** Aspose.GIS per .NET (ultima release)  
**Autore:** Aspose

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Impara a creare la geometria LineString con Aspose.GIS per .NET](/gis/net/geometry-creation/create-linestring-geometry/)
- [Come aggiungere un punto a LineString e convertire la geometria in formato modificabile con Aspose.GIS](/gis/net/geometry-creation/convert-geometry-to-editable/)
- [punto dentro poligono c# – Verifica che la geometria contenga un'altra](/gis/net/geometry-analysis/check-geometry-contains-another/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}