---
date: 2026-02-08
description: Impara a creare una linestring in C# con Aspose.GIS per .NET, aggiungere
  punti a una linestring e verificare se un punto è sulla linea usando il metodo covers.
linktitle: Create LineString C# – Check Geometry Covers Another
second_title: Aspose.GIS .NET API
title: Crea LineString C# – Verifica se la geometria copre un'altra
url: /it/net/geometry-analysis/check-geometry-covers-another/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Verifica che la geometria copra un'altra

## Introduzione
In questo tutorial imparerai **come creare linestring c#** usando Aspose.GIS per .NET, aggiungere punti a una linestring e eseguire un affidabile **controllo punto su linea** con i metodi `Covers` e `CoveredBy`. Che tu stia costruendo uno strumento di mappatura, eseguendo analisi spaziali o semplicemente abbia bisogno di verificare le relazioni geometriche, padroneggiare queste operazioni darà alla tua applicazione la precisione necessaria.

## Risposte rapide
- **Cosa significa “create linestring c#”?** Significa istanziare un oggetto geometrico `LineString` e popolarlo con punti di coordinate.  
- **Quale metodo verifica se un punto giace su una linea?** Usa il metodo `Covers` sul `LineString` o `CoveredBy` sul `Point`.  
- **Ho bisogno di una licenza per eseguire l'esempio?** Una licenza temporanea è sufficiente per la valutazione; è necessaria una licenza completa per la produzione.  
- **È possibile usarlo con .NET Core?** Sì, Aspose.GIS supporta .NET Framework e .NET Core.  
- **Quanti punti posso aggiungere a una linestring?** Non c'è un limite rigido; puoi aggiungere tutti i punti necessari per la tua analisi spaziale.

## Cos'è **create linestring c#**?
Una `LineString` è una forma geometrica costituita da un elenco ordinato di punti collegati da segmenti di linea retti. In C# la crei istanziando la classe `LineString` dallo spazio dei nomi `Aspose.Gis.Geometries` e poi **add points to linestring** usando il metodo `AddPoint`.

## Perché usare Aspose.GIS per un controllo punto su linea?
- **Precisione** – Gestisce i calcoli in virgola mobile e i predicati spaziali con precisione, fornendoti un risultato **precision point on line**.  
- **Cross‑platform** – Funziona con .NET Framework, .NET Core e .NET 5/6+.  
- **Rich API** – Fornisce un set completo di metodi per le relazioni spaziali (`Covers`, `CoveredBy`, `Intersects`, ecc.).  

## Prerequisiti
Prima di immergerti nell'uso di Aspose.GIS per .NET, assicurati di avere i seguenti prerequisiti configurati:

### 1. Installa Visual Studio
Assicurati di avere Visual Studio installato sul tuo sistema. Aspose.GIS per .NET si integra perfettamente con Visual Studio, offrendo un'esperienza di sviluppo fluida.

### 2. Ottieni Aspose.GIS per .NET
Scarica la libreria Aspose.GIS per .NET dal [sito web](https://releases.aspose.com/gis/net/). Puoi scaricare direttamente la libreria o utilizzare un gestore di pacchetti come NuGet per installarla nel tuo progetto.

### 3. Familiarità con .NET Framework
Una conoscenza di base del framework .NET e del linguaggio di programmazione C# è essenziale per utilizzare efficacemente Aspose.GIS per .NET.

### 4. Accesso alla Documentazione e al Supporto
Consulta la [documentazione](https://reference.aspose.com/gis/net/) per informazioni dettagliate sulle API e le funzionalità di Aspose.GIS. In caso di problemi o domande, utilizza il [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) per assistenza.

### 5. Opzionale: Licenza Temporanea
Se stai esplorando Aspose.GIS per .NET, puoi ottenere una licenza temporanea da [qui](https://purchase.aspose.com/temporary-license/) per valutare le funzionalità della libreria.

## Importa gli Spazi dei Nomi
Prima di usare Aspose.GIS per .NET nel tuo progetto, devi importare gli spazi dei nomi necessari:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Ora, suddividiamo l'esempio fornito in più passaggi per capire come **check if one geometry covers another** usando Aspose.GIS per .NET.

## Come creare linestring c# – Guida passo‑passo

### Passo 1: Crea un oggetto LineString
```csharp
var line = new LineString();
```
Qui, istanziamo un nuovo oggetto `LineString`, che rappresenta una sequenza di segmenti di linea collegati in uno spazio bidimensionale.

### Passo 2: **Add Points to LineString**
```csharp
line.AddPoint(0, 0);
line.AddPoint(1, 1);
```
Usiamo **add points to linestring** con il metodo `AddPoint`. In questo esempio, aggiungiamo due punti: (0, 0) e (1, 1), formando un semplice segmento diagonale.

### Passo 3: Crea un oggetto Point
```csharp
var point = new Point(0, 0);
```
Istanzia un oggetto `Point` che rappresenta un singolo punto in uno spazio bidimensionale. Qui, creiamo un punto alle coordinate (0, 0).

### Passo 4: Esegui un **point on line check** – La linea copre il punto?
```csharp
Console.WriteLine(line.Covers(point));    // True
```
Usa il metodo `Covers` per verificare se la linea copre il punto. In questo caso, restituisce `True` perché il punto (0, 0) si trova esattamente sulla linea.

### Passo 5: Verifica la relazione inversa – Il punto è coperto dalla linea?
```csharp
Console.WriteLine(point.CoveredBy(line)); // True
```
Allo stesso modo, usa il metodo `CoveredBy` per verificare se il punto è coperto dalla linea. Poiché il punto (0, 0) si trova sulla linea, restituisce anch'esso `True`.

## Problemi comuni e soluzioni
| Problema | Perché accade | Soluzione |
|----------|----------------|-----------|
| `line.Covers(point)` restituisce `False` anche se il punto sembra sulla linea | Le coordinate del punto non sono esattamente le stesse a causa della precisione dei numeri in virgola mobile. | Usa `Math.Round` sulle coordinate o utilizza un controllo basato su tolleranza con `line.Distance(point) < epsilon`. |
| Manca `using Aspose.Gis.Geometries;` | Namespace non importato, causando errori di compilazione. | Assicurati che la dichiarazione di import sia presente (vedi la sezione **Importa gli Spazi dei Nomi**). |
| Eccezione di licenza a runtime | Nessuna licenza valida caricata per la produzione. | Carica una licenza temporanea o completa usando `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Domande frequenti

**Q: Posso usare Aspose.GIS per .NET nei miei progetti commerciali?**  
**A:** Sì, puoi usare Aspose.GIS per .NET sia in progetti commerciali che non commerciali dopo aver ottenuto la licenza appropriata.

**Q: Aspose.GIS per .NET è compatibile con .NET Core?**  
**A:** Sì, Aspose.GIS per .NET è compatibile con entrambi gli ambienti .NET Framework e .NET Core.

**Q: Aspose.GIS per .NET supporta vari formati GIS?**  
**A:** Sì, Aspose.GIS per .NET supporta una vasta gamma di formati GIS tra cui Shapefile, GeoJSON, KML e altri.

**Q: Posso contribuire allo sviluppo di Aspose.GIS per .NET?**  
**A:** Aspose.GIS per .NET è una libreria proprietaria sviluppata da Aspose, quindi i contributi esterni non sono accettati. Tuttavia, puoi fornire feedback e suggerimenti per migliorare la libreria.

**Q: Con quale frequenza vengono rilasciati gli aggiornamenti per Aspose.GIS per .NET?**  
**A:** Gli aggiornamenti per Aspose.GIS per .NET vengono rilasciati regolarmente per introdurre nuove funzionalità, miglioramenti e correzioni di bug. Controlla il [sito web](https://releases.aspose.com/gis/net/) per le ultime versioni.

## Conclusione
Seguendo i passaggi sopra, ora sai come **create linestring c#**, **add points to linestring**, e eseguire un affidabile **point on line check** usando i metodi `Covers` e `CoveredBy`. Questa capacità migliora le funzionalità di analisi spaziale del tuo software e apre la porta a operazioni GIS più avanzate.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ultimo aggiornamento:** 2026-02-08  
**Testato con:** Aspose.GIS for .NET (latest release)  
**Autore:** Aspose