---
date: 2026-06-05
description: Scopri come confrontare le geometrie in .NET usando Aspose.GIS, rilevare
  geometrie duplicate e verificare l'uguaglianza delle geometrie nelle tue applicazioni.
keywords:
- how to compare geometries
- detect duplicate geometries
- Aspose.GIS geometry equality
linktitle: Come confrontare le geometrie per uguaglianza
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to compare geometries in .NET using Aspose.GIS, detect duplicate
    geometries, and check geometry equality in your applications.
  headline: How to Compare Geometries for Equality using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS works with .NET Framework, .NET Core, and .NET Standard
      projects.
    question: Can I use Aspose.GIS for .NET with other .NET frameworks?
  - answer: Absolutely. Download a trial from the [Aspose.GIS releases page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Detailed docs are on the [Aspose.GIS documentation page](https://reference.aspose.com/gis/net/).
    question: Where can I find the full API documentation?
  - answer: Post your question on the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How do I get help if I run into an issue?
  - answer: Yes, temporary licenses are available on the [purchase page](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Come confrontare le geometrie per uguaglianza usando Aspose.GIS per .NET
url: /it/net/geometry-analysis/check-geometries-for-equality/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come confrontare le geometrie per uguaglianza usando Aspose.GIS per .NET

## Introduzione
In questo tutorial imparerai **come confrontare le geometrie** con Aspose.GIS per .NET, un compito fondamentale quando è necessario rilevare geometrie duplicate, convalidare dati spaziali o applicare regole topologiche. Che tu stia creando un servizio di mappatura, eseguendo analisi spaziali batch o semplicemente verificando che due forme occupino la stessa posizione, questa guida ti accompagna nella creazione, modifica e test dell’uguaglianza geometrica con codice C# pulito e pronto per la produzione.

## Risposte rapide
- **Cosa significa “confrontare le geometrie”?** Verifica se due oggetti geometrici occupano lo stesso spazio, indipendentemente da come sono costruiti.  
- **Quale metodo viene usato?** `SpatiallyEquals` dall'API Aspose.GIS.  
- **Ho bisogno di una licenza per lo sviluppo?** Una versione di prova gratuita è sufficiente per i test; è necessaria una licenza commerciale per la produzione.  
- **Versioni .NET supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Tempo tipico di implementazione?** Circa 5‑10 minuti per un controllo di uguaglianza di base.

## Che cos'è l'uguaglianza geometrica?
L'uguaglianza geometrica, chiamata anche uguaglianza spaziale, significa che due geometrie rappresentano esattamente lo stesso insieme di punti sulla superficie terrestre. Anche se una geometria è costruita come `MultiLineString` e l'altra come `LineString` singola, sono considerate uguali quando ogni coordinata corrisponde entro la tolleranza definita. Questa definizione consente agli sviluppatori di rilevare in modo affidabile geometrie duplicate attraverso fonti di dati eterogenee.

## Perché usare Aspose.GIS per confrontare le geometrie?
Aspose.GIS offre un motore geometrico offline ad alte prestazioni che elimina la necessità di servizi esterni. **Supporta più di 30 formati vettoriali e raster** (inclusi WKT, GeoJSON, Shapefile, KML, GML) e può elaborare file con **centinaia di migliaia di vertici** mantenendo l'uso della memoria sotto i 50 MB. Il metodo `SpatiallyEquals` della libreria è consapevole della precisione, fornendo risultati deterministici anche con coordinate a virgola mobile.

### Perché questo è importante per gli sviluppatori
Quando è necessario **rilevare geometrie duplicate** nei processi batch, nelle pipeline di validazione in tempo reale o nelle migrazioni di dati GIS, una libreria collaudata elimina le ipotesi e garantisce risultati coerenti tra diversi fornitori di dati.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

- **.NET Framework o .NET Core installati** – qualsiasi versione supportata da Aspose.GIS.  
- **Libreria Aspose.GIS per .NET** – scarica dalla [pagina di download di Aspose.GIS](https://releases.aspose.com/gis/net/).  
- **Un IDE di sviluppo** – Visual Studio, Rider o VS Code con estensioni C#.

## Importare gli spazi dei nomi
Nel tuo progetto .NET, aggiungi le dichiarazioni `using` necessarie affinché il compilatore sappia dove trovare le classi GIS:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Passo 1: Definire le geometrie
`MultiLineString` rappresenta una collezione di componenti lineari, mentre `LineString` definisce una singola linea continua. Entrambe le classi ereditano dal tipo base `Geometry`.

Prima, creiamo due geometrie da confrontare. In questo esempio `geometry1` è un `MultiLineString` composto da due segmenti di linea, mentre `geometry2` è un singolo `LineString` che copre gli stessi punti di inizio e fine.

```csharp
var geometry1 = new MultiLineString
{
    new LineString(new [] { new Point(0, 0), new Point(1, 1) }),
    new LineString(new [] { new Point(1, 1), new Point(2, 2) }),
};
var geometry2 = new LineString(new[]
{
    new Point(0, 0), new Point(2, 2),
});
```

## Passo 2: Verificare l'uguaglianza delle geometrie
`SpatiallyEquals` valuta se due geometrie occupano lo stesso insieme di punti, accettando facoltativamente un valore di tolleranza per l'imprecisione dei numeri a virgola mobile.

Ora utilizziamo il metodo `SpatiallyEquals` per verificare se le due forme sono considerate uguali dal motore GIS.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // True
```

La console stampa `True` perché, nonostante la costruzione diversa, entrambe le geometrie coprono la stessa linea da (0,0) a (2,2).

## Passo 3: Modificare una geometria
Per illustrare come una modifica influisce sull'uguaglianza, aggiungiamo un punto extra a `geometry2`.

```csharp
geometry2.AddPoint(3, 3);
```

## Passo 4: Ricontrollare l'uguaglianza dopo la modifica
Dopo la modifica, le geometrie non sono più identiche, quindi `SpatiallyEquals` restituisce `False`.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // False
```

L'output `False` conferma che il punto aggiuntivo ha rotto l'uguaglianza spaziale.

## Come rilevare geometrie duplicate?
Carica ogni geometria, chiama `SpatiallyEquals` con una tolleranza adeguata e filtra quelle che restituiscono `True`. Questo schema scala bene con LINQ, consentendo di identificare forme duplicate in grandi collezioni con poche righe di codice. Puoi anche combinarlo con `GroupBy` per aggregare geometrie identiche e ridurre i costi di archiviazione.

## Problemi comuni e consigli
- **Problemi di precisione** – Se lavori con coordinate ad altissima precisione, considera l'arrotondamento o l'uso della versione con tolleranza di `SpatiallyEquals`.  
- **SRID diversi** – Assicurati che entrambe le geometrie condividano lo stesso Identificatore del Sistema di Riferimento Spaziale (SRID) prima del confronto.  
- **Prestazioni** – Per grandi collezioni, i confronti batch usando LINQ o loop paralleli possono ridurre notevolmente il carico.

## Domande frequenti
**Q: Posso usare Aspose.GIS per .NET con altri framework .NET?**  
A: Sì, Aspose.GIS funziona con progetti .NET Framework, .NET Core e .NET Standard.

**Q: È disponibile una versione di prova gratuita?**  
A: Assolutamente. Scarica una versione di prova dalla [pagina di rilascio di Aspose.GIS](https://releases.aspose.com/).

**Q: Dove posso trovare la documentazione completa dell'API?**  
A: La documentazione dettagliata è disponibile sulla [pagina di documentazione di Aspose.GIS](https://reference.aspose.com/gis/net/).

**Q: Come posso ottenere aiuto se incontro un problema?**  
A: Pubblica la tua domanda sul forum della community di Aspose.GIS [qui](https://forum.aspose.com/c/gis/33).

**Q: Posso acquistare una licenza temporanea per la valutazione?**  
A: Sì, le licenze temporanee sono disponibili sulla [pagina di acquisto](https://purchase.aspose.com/temporary-license/).

## Conclusione
Ora sai **come confrontare le geometrie** usando Aspose.GIS per .NET, dalla creazione degli oggetti al controllo dell'uguaglianza spaziale e alla gestione delle modifiche. Questa capacità è un elemento fondamentale per analisi spaziali più avanzate come la validazione della topologia, il rilevamento di duplicati e il filtraggio basato su geometrie.

---

**Ultimo aggiornamento:** 2026-06-05  
**Testato con:** Aspose.GIS for .NET 24.11  
**Autore:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Crea geometria poligonale C# e verifica l'intersezione con Aspose.GIS per .NET](/gis/net/geometry-analysis/check-geometries-intersection/)
- [Come eseguire l'analisi di sovrapposizione spaziale delle geometrie con Aspose.GIS per .NET](/gis/net/geometry-analysis/check-geometries-overlap/)
- [Controllo routing di rete: geometrie che si toccano con Aspose.GIS](/gis/net/geometry-analysis/check-geometries-touching/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}