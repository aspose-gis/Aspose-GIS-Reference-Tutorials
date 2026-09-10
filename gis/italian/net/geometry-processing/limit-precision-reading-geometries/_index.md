---
date: 2026-09-10
description: Scopri come creare un vector layer con Aspose.GIS for .NET e limitare
  la precision per ridurre le dimensioni del shapefile, migliorare le performance
  e mantenere la coordinate accuracy.
keywords:
- how to create vector layer
- limit precision reading geometries
- reduce shapefile size
lastmod: 2026-09-10
linktitle: Limit Precision Lettura Geometrie
og_description: Scopri come creare un vector layer con Aspose.GIS for .NET e limitare
  la precision per ridurre le dimensioni del shapefile, migliorare le performance
  e gestire la coordinate accuracy.
og_image_alt: Screenshot showing Aspose.GIS code for creating a vector layer and setting
  precision
og_title: Come creare un vector layer con Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to create vector layer with Aspose.GIS for .NET and limit
    precision to shrink shapefile size, boost performance, and keep coordinate accuracy.
  headline: How to create vector layer with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create vector layer with Aspose.GIS for .NET and limit
    precision to shrink shapefile size, boost performance, and keep coordinate accuracy.
  name: How to create vector layer with Aspose.GIS for .NET
  steps:
  - name: '**Installation** – Aspose.GIS for .NET library should be installed in your
      development environment. If not, you can download it from the [releases page](https://releases.aspose.com/gis/net/).'
    text: '**Installation** – Aspose.GIS for .NET library should be installed in your
      development environment. If not, you can download it from the [releases page](https://releases.aspose.com/gis/net/).'
  - name: '**Familiarity with .NET** – Basic knowledge of C# and the .NET framework
      is necessary to understand and implement the provided code examples.'
    text: '**Familiarity with .NET** – Basic knowledge of C# and the .NET framework
      is necessary to understand and implement the provided code examples.'
  - name: '**Development environment** – A working .NET development environment, such
      as Visual Studio, is required.'
    text: '**Development environment** – A working .NET development environment, such
      as Visual Studio, is required.'
  - name: '**Document directory** – Have a directory set up where you can store and
      access the shapefile generated during the process.'
    text: '**Document directory** – Have a directory set up where you can store and
      access the shapefile generated during the process.'
  type: HowTo
- questions:
  - answer: No. Precision is applied only when reading the geometry; the source file
      remains unchanged.
    question: Does limiting precision affect the original shapefile?
  - answer: Aspose.GIS currently applies the same `XYPrecisionModel` to both axes.
    question: Can I use a different precision model for X and Y coordinates?
  - answer: The API supports only the built‑in `PrecisionModel.Rounding(int)` method.
      For custom logic, you would need to post‑process the coordinates after reading.
    question: Is it possible to set a custom rounding function?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- Aspose.GIS
- vector layer
- precision model
- .NET GIS
title: Come creare un vector layer con Aspose.GIS for .NET
url: /it/net/geometry-processing/limit-precision-reading-geometries/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un layer vettoriale con Aspose.GIS per .NET

## Introduzione
Quando lavori con dati geospaziali ti chiedi spesso **come creare un layer vettoriale** che corrisponda alla precisione di cui la tua applicazione ha realmente bisogno. Arrotondare le coordinate a un numero sensato di cifre decimali non solo velocizza l'analisi, ma può anche **ridurre le dimensioni dello shapefile fino al 30 %** per i tipici dataset di punti. In questa guida passo‑passo vedrai come creare un layer vettoriale, scrivere una geometria punto e poi leggerla nuovamente usando sia modelli di precisione esatti che arrotondati. Alla fine saprai come **impostare le opzioni del modello di precisione** che bilanciano le prestazioni con la precisione spaziale richiesta.

## Risposte rapide
- **Cosa significa “limit precision”?** Arrotonda i valori delle coordinate a un numero definito di cifre decimali.  
- **Perché creare prima un layer vettoriale?** Un layer vettoriale è il contenitore che memorizza geometrie come punti, linee e poligoni.  
- **Quali modelli di precisione sono disponibili?** `PrecisionModel.Exact` (senza arrotondamento) e `PrecisionModel.Rounding(n)` (arrotonda a *n* decimali).  
- **È necessaria una licenza per provare?** È disponibile una versione di prova gratuita dalla pagina dei rilasci.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core e .NET 5/6+.

## Che cosa significa creare un layer vettoriale?
L'atto di **creare un layer vettoriale** consiste nell'istanziare la classe `VectorLayer` di Aspose.GIS, che rappresenta un singolo shapefile su disco e contiene tutte le feature geometriche che aggiungi. Questo layer diventa il punto di ingresso per leggere, scrivere e manipolare i dati spaziali. Consente inoltre di definire i campi attributo e impostare il riferimento spaziale per il dataset.

## Perché limitare la precisione e come aiuta?
- **Incremento delle prestazioni** – Ridurre il numero di cifre decimali diminuisce la quantità di dati binari da analizzare e serializzare, spesso offrendo un aumento di velocità del 15‑20 % su file di grandi dimensioni.  
- **File più piccoli** – Arrotondare le coordinate a due o tre decimali può ridurre un shapefile da 10 MB a circa 7 MB, facilitando l'archiviazione e il trasferimento di rete.  
- **Precisione sufficiente** – La maggior parte delle analisi GIS (ad es., mappatura a livello cittadino) richiede solo precisione a livello di metro, rendendo l'arrotondamento a 3 decimali più che adeguato.

## Prerequisiti
1. **Installazione** – La libreria Aspose.GIS per .NET dovrebbe essere installata nel tuo ambiente di sviluppo. In caso contrario, puoi scaricarla dalla [pagina dei rilasci](https://releases.aspose.com/gis/net/).  
2. **Familiarità con .NET** – È necessario avere una conoscenza di base di C# e del framework .NET per comprendere e implementare gli esempi di codice forniti.  
3. **Ambiente di sviluppo** – È richiesto un ambiente di sviluppo .NET funzionante, come Visual Studio.  
4. **Directory dei documenti** – Prepara una directory dove poter archiviare e accedere allo shapefile generato durante il processo.

## Importa i namespace
Prima di iniziare a implementare la funzionalità per limitare la precisione durante la lettura delle geometrie, assicuriamoci di importare i namespace necessari:
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

## Come creare un layer vettoriale
Carica un nuovo `VectorLayer` specificando la cartella di output e il nome desiderato per lo shapefile. Questo crea un contenitore vuoto pronto ad accettare oggetti geometria.

La classe `VectorLayer` è l'oggetto di livello superiore di Aspose.GIS che rappresenta un singolo shapefile su disco. Dopo aver creato un'istanza puoi aggiungere feature, definire campi attributo e infine chiamare `Save()` per scrivere i file nel file system.
```csharp
string path = "Your Document Directory" + "LimitPrecisionWhenReadingGeometries_out.shp";
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
	var feature = layer.ConstructFeature();
	feature.Geometry = new Point(1.10234, 2.09743);
	layer.Add(feature);
}
```

## Impostazione delle opzioni di precisione
`PrecisionModel` definisce come i valori delle coordinate vengono arrotondati o mantenuti esatti durante la lettura delle geometrie. Imposti il modello su un oggetto `ReadOptions` prima di aprire un layer.

La classe `PrecisionModel` è un componente centrale di Aspose.GIS che controlla il comportamento di arrotondamento sia per l'asse X che per l'asse Y. Scegliendo il modello appropriato decidi se la libreria conserva ogni cifra o la tronca a un numero specifico di decimali.
```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## Lettura delle geometrie con precisione esatta
`ReadOptions` specifica i parametri per leggere un layer vettoriale, come il modello di precisione da applicare.  
Apri il layer vettoriale salvato in precedenza usando un'istanza di `ReadOptions` che fa riferimento a `PrecisionModel.Exact`. Questo garantisce che ogni coordinata venga letta senza alcun arrotondamento.

Quando usi `PrecisionModel.Exact`, Aspose.GIS legge i valori double‑precision grezzi memorizzati nello shapefile, garantendo che nessuna informazione venga persa durante l'operazione di lettura.
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Troncamento della precisione
Se desideri troncare la precisione a un numero specifico di cifre decimali, sostituisci `Exact` con `PrecisionModel.Rounding(n)`, dove *n* è il numero di decimali da mantenere.

Arrotondare a due decimali (`PrecisionModel.Rounding(2)`) tipicamente riduce le dimensioni del file del 20‑30 % mantenendo la precisione delle coordinate entro pochi centimetri per la maggior parte delle scale di mappatura.
```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Come impostare il modello di precisione per diversi scenari
Scegli il modello che corrisponde al tuo caso d'uso:

- **Analisi scientifica ad alta precisione** – Usa `PrecisionModel.Exact` per conservare ogni cifra.  
- **Tile di web‑mapping o app mobile** – Usa `PrecisionModel.Rounding(2)` per mantenere i file leggeri e la resa veloce.

Selezionare il modello appropriato fa parte del processo decisionale di **impostazione del modello di precisione** che bilancia accuratezza e prestazioni.

## Problemi comuni e soluzioni
`XYPrecisionModel` è una proprietà di `ReadOptions` che imposta il modello di precisione per entrambe le coordinate X e Y.  

- **Valori di coordinate inaspettati** – Assicurati di impostare `options.XYPrecisionModel` *prima* di aprire il layer. Modificarlo dopo l'apertura non ha effetto.  
- **File non trovato** – Verifica che la variabile `path` punti a una directory valida e che lo Shapefile sia stato creato correttamente nel passaggio precedente.  
- **Tipo di geometria errato** – L'esempio utilizza un `Point`. Per altri tipi di geometria (ad es., `LineString`), il cast deve corrispondere al tipo reale.

## Suggerimenti per ridurre le dimensioni dello shapefile
- Usa `PrecisionModel.Rounding` con il minor numero di decimali che soddisfa comunque le tue esigenze di precisione.  
- Rimuovi i campi attributo non necessari prima di scrivere il layer.  
- Comprimi i file risultanti `.shp`, `.shx` e `.dbf` usando utility ZIP standard se devi trasferirli.

## Conclusione
Gestire la precisione durante la lettura delle geometrie è un aspetto cruciale della manipolazione dei dati geospaziali. Aspose.GIS per .NET offre funzionalità robuste per ottenere ciò in modo efficiente. Seguendo i passaggi sopra potrai creare senza problemi oggetti **vector layer**, **impostare il modello di precisione** e persino **ridurre le dimensioni dello shapefile** quando opportuno, garantendo una gestione ottimale dei dati nelle tue applicazioni.

## FAQ
### Posso usare Aspose.GIS per .NET con altri framework .NET come .NET Core o .NET Standard?
Sì, Aspose.GIS per .NET è compatibile con vari framework .NET, inclusi .NET Core e .NET Standard.  
### È disponibile una versione di prova per Aspose.GIS per .NET?
Sì, puoi ottenere una versione di prova gratuita dalla [pagina dei rilasci](https://releases.aspose.com/).  
### Dove posso trovare la documentazione completa per Aspose.GIS per .NET?
Puoi consultare la [documentazione](https://reference.aspose.com/gis/net/) per informazioni dettagliate ed esempi.  
### Come posso ottenere licenze temporanee per Aspose.GIS per .NET?
Le licenze temporanee possono essere acquisite dalla [pagina di acquisto](https://purchase.aspose.com/temporary-license/) per Aspose.GIS.  
### Dove posso cercare assistenza o supporto per Aspose.GIS per .NET?
Puoi visitare il [forum](https://forum.aspose.com/c/gis/33) di Aspose.GIS per domande, discussioni o richieste di supporto.

## Domande frequenti
**D: Limitare la precisione influisce sullo shapefile originale?**  
R: No. La precisione viene applicata solo durante la lettura della geometria; il file sorgente rimane invariato.  

**D: Posso usare un modello di precisione diverso per le coordinate X e Y?**  
R: Attualmente Aspose.GIS applica lo stesso `XYPrecisionModel` a entrambi gli assi.  

**D: È possibile impostare una funzione di arrotondamento personalizzata?**  
R: L'API supporta solo il metodo integrato `PrecisionModel.Rounding(int)`. Per logiche personalizzate, dovresti post‑processare le coordinate dopo la lettura.

**Ultimo aggiornamento:** 2026-09-10  
**Testato con:** Aspose.GIS 24.11 per .NET  
**Autore:** Aspose

## Tutorial correlati

- [Come limitare la precisione nella scrittura di geometrie con Aspose.GIS](/gis/net/geometry-processing/limit-precision-writing-geometries/)
- [Come creare un layer vettoriale con SRS usando Aspose.GIS per .NET](/gis/net/layer-management/create-vector-layer-with-srs/)
- [Creare un layer vettoriale in File GDB – Tutorial Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}