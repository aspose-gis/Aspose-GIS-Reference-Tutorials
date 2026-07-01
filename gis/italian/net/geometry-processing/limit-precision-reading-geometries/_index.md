---
date: 2026-04-03
description: Scopri come creare un layer vettoriale e limitare la precisione durante
  la lettura delle geometrie usando Aspose.GIS per .NET. Guida passo‑passo per una
  gestione ottimale dei dati geospaziali.
keywords:
- create vector layer
- reduce shapefile size
- set precision model
linktitle: Limita precisione nella lettura delle geometrie
second_title: Aspose.GIS .NET API
title: Crea livello vettoriale, limita la precisione con Aspose.GIS per .NET
url: /it/net/geometry-processing/limit-precision-reading-geometries/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea Layer Vettoriale, Limita la Precisione con Aspose.GIS per .NET

## Introduzione
Quando si lavora con dati geospaziali, è spesso necessario **creare layer vettoriali** e decidere quante cifre decimali di dettaglio delle coordinate siano realmente necessarie. Limitare la precisione non solo velocizza l'elaborazione, ma può anche **ridurre le dimensioni del file shapefile**, rendendo più efficienti l'archiviazione e il trasferimento. In questo tutorial vedremo come creare un layer vettoriale, scrivere una semplice geometria di tipo punto e poi leggerla nuovamente utilizzando sia modelli di precisione esatti che arrotondati. Alla fine comprenderete come **impostare le opzioni del modello di precisione** che si adattano ai requisiti di accuratezza della vostra applicazione.

## Risposte Rapide
- **Cosa significa “limitare la precisione”?** Arrotonda i valori delle coordinate a un numero definito di cifre decimali.  
- **Perché creare prima un layer vettoriale?** Un layer vettoriale è il contenitore che memorizza geometrie come punti, linee e poligoni.  
- **Quali modelli di precisione sono disponibili?** `PrecisionModel.Exact` (senza arrotondamento) e `PrecisionModel.Rounding(n)` (arrotonda a *n* decimali).  
- **È necessaria una licenza per provare?** È disponibile una versione di prova gratuita dalla pagina dei rilasci.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core e .NET 5/6+.

## Perché limitare la precisione e come aiuta?
- **Incremento delle prestazioni** – Meno cifre significano meno dati da analizzare e serializzare.  
- **File più piccoli** – Arrotondare le coordinate può ridurre notevolmente le dimensioni di uno shapefile, soprattutto per grandi set di dati.  
- **Accuratezza sufficiente** – Molte analisi GIS non richiedono precisione sub‑millimetrica, quindi arrotondare a 2‑3 decimali è spesso sufficiente.

## Prerequisiti
Prima di intraprendere questo percorso, assicuratevi di avere i seguenti prerequisiti:
1. **Installazione** – La libreria Aspose.GIS per .NET dovrebbe essere installata nel vostro ambiente di sviluppo. In caso contrario, potete scaricarla dalla [pagina dei rilasci](https://releases.aspose.com/gis/net/).
2. **Familiarità con .NET** – È necessario avere conoscenze di base di C# e del framework .NET per comprendere e implementare gli esempi di codice forniti.
3. **Ambiente di sviluppo** – È richiesto un ambiente di sviluppo .NET funzionante, come Visual Studio.
4. **Directory dei documenti** – Preparate una cartella dove poter memorizzare e accedere allo shapefile generato durante il processo.

## Importa Namespace
Prima di iniziare a implementare la funzionalità per limitare la precisione nella lettura delle geometrie, assicuriamoci di importare i namespace necessari:
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Come Creare un Layer Vettoriale
Il primo passo è **creare un layer vettoriale** che conterrà la nostra geometria. Questo layer verrà salvato come Shapefile così potremo riaprirlo in seguito con impostazioni di precisione diverse.
```csharp
string path = "Your Document Directory" + "LimitPrecisionWhenReadingGeometries_out.shp";
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
	var feature = layer.ConstructFeature();
	feature.Geometry = new Point(1.10234, 2.09743);
	layer.Add(feature);
}
```

## Impostazione delle Opzioni di Precisione
Successivamente, dobbiamo definire le opzioni per la lettura delle geometrie, specificando il modello di precisione desiderato. Possiamo iniziare con precisione esatta:
```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## Lettura delle Geometrie con Precisione Esatta
Ora, apriamo il layer vettoriale con le opzioni specificate per leggere le geometrie con precisione esatta:
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Troncamento della Precisione
Se desideriamo troncare la precisione a un numero specifico di cifre decimali, possiamo regolare il modello di precisione di conseguenza:
```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Come Impostare il Modello di Precisione per Diversi Scenari
Vi potreste chiedere quando usare `Exact` rispetto a `Rounding`. Ecco due scenari comuni:

| Scenario | Modello Consigliato | Motivo |
|----------|---------------------|--------|
| Analisi scientifica ad alta precisione | `PrecisionModel.Exact` | Nessuna perdita di dettaglio delle coordinate |
| Tile per web‑mapping o app mobili | `PrecisionModel.Rounding(2)` | Riduce le dimensioni del file e velocizza il rendering |

Scegliere il modello giusto fa parte del processo decisionale di **impostazione del modello di precisione** che bilancia accuratezza e prestazioni.

## Problemi Comuni e Soluzioni
- **Valori di coordinate inaspettati** – Assicurati di impostare `options.XYPrecisionModel` *prima* di aprire il layer. Modificarlo dopo l'apertura non ha effetto.  
- **File non trovato** – Verifica che la variabile `path` punti a una directory valida e che lo Shapefile sia stato creato correttamente nel passaggio precedente.  
- **Tipo di geometria errato** – L'esempio utilizza un `Point`. Per altri tipi di geometria (ad esempio `LineString`), il cast dovrebbe corrispondere al tipo reale.  

## Suggerimenti per Ridurre le Dimensioni dello Shapefile
- Usa `PrecisionModel.Rounding` con il minor numero di decimali che soddisfi comunque le tue esigenze di accuratezza.  
- Rimuovi i campi attributo non necessari prima di scrivere il layer.  
- Comprimi i file risultanti `.shp`, `.shx` e `.dbf` usando utility ZIP standard se devi trasferirli.

## Conclusione
In conclusione, gestire la precisione nella lettura delle geometrie è un aspetto cruciale della manipolazione dei dati geospaziali. Aspose.GIS per .NET offre funzionalità robuste per realizzare ciò in modo efficiente. Seguendo i passaggi sopra indicati è possibile creare senza problemi oggetti **vector layer**, **impostare il modello di precisione** e persino **ridurre le dimensioni dello shapefile** quando opportuno, garantendo una gestione ottimale dei dati nelle vostre applicazioni.

## FAQ
### Posso usare Aspose.GIS per .NET con altri framework .NET come .NET Core o .NET Standard?
Sì, Aspose.GIS per .NET è compatibile con vari framework .NET, inclusi .NET Core e .NET Standard.  
### È disponibile una versione di prova per Aspose.GIS per .NET?
Sì, è possibile ottenere una versione di prova gratuita dalla [pagina dei rilasci](https://releases.aspose.com/).  
### Dove posso trovare la documentazione completa per Aspose.GIS per .NET?
Potete consultare la [documentazione](https://reference.aspose.com/gis/net/) per informazioni dettagliate ed esempi.  
### Come posso ottenere licenze temporanee per Aspose.GIS per .NET?
Le licenze temporanee possono essere ottenute dalla [pagina di acquisto](https://purchase.aspose.com/temporary-license/) per Aspose.GIS.  
### Dove posso cercare assistenza o supporto per Aspose.GIS per .NET?
Potete visitare il [forum](https://forum.aspose.com/c/gis/33) di Aspose.GIS per domande, discussioni o necessità di supporto.

## Domande Frequenti
**Q: Limitare la precisione influisce sullo shapefile originale?**  
**A:** No. La precisione viene applicata solo durante la lettura della geometria; il file sorgente rimane invariato.  

**Q: Posso usare un modello di precisione diverso per le coordinate X e Y?**  
**A:** Attualmente Aspose.GIS applica lo stesso `XYPrecisionModel` a entrambi gli assi.  

**Q: È possibile impostare una funzione di arrotondamento personalizzata?**  
**A:** L'API supporta solo il metodo integrato `PrecisionModel.Rounding(int)`. Per una logica personalizzata, dovreste post‑processare le coordinate dopo la lettura.

---

**Last Updated:** 2026-04-03  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}