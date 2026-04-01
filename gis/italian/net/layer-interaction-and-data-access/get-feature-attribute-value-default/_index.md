---
date: 2026-01-05
description: Scopri come ottenere i valori degli attributi e impostare i valori predefiniti
  in Aspose.GIS per .NET. Questa guida passo‑passo mostra come creare layer GeoJSON
  e costruire feature GIS.
linktitle: How to Get Attribute Value (Default)
second_title: Aspose.GIS .NET API
title: Come ottenere il valore dell'attributo (predefinito) con Aspose.GIS per .NET
url: /it/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come ottenere il valore dell'attributo (predefinito) con Aspose.GIS per .NET

## Introduzione
In questo tutorial completo scoprirai **come ottenere l'attributo** valori da una feature GIS usando Aspose.GIS per .NET, e come gestire i valori predefiniti quando un attributo è mancante. Che tu stia costruendo un motore di analisi spaziale o un semplice visualizzatore di mappe, padroneggiare il recupero degli attributi e la gestione dei valori predefiniti è essenziale per applicazioni GIS affidabili.

## Risposte rapide
- **Qual è il metodo principale?** `Feature.GetValueOrDefault<T>()`  
- **Posso impostare un valore predefinito personalizzato?** Sì, tramite la sovraccico che accetta un valore predefinito o definendo `DefaultValue` sull'attributo.  
- **Ho bisogno di una licenza per lo sviluppo?** Una versione di prova gratuita funziona per i test; è necessaria una licenza commerciale per la produzione.  
- **Formati di geometria supportati?** GeoJSON, Shapefile, GML e molti altri tramite i driver di Aspose.GIS.  
- **Funziona con .NET Core/.NET 6+?** Assolutamente – la libreria è cross‑platform.

## Prerequisiti
Prima di iniziare, assicurati di avere:

- Familiarità di base con C# e l'ecosistema .NET.  
- Aspose.GIS per .NET installato. Se non lo hai ancora fatto, scaricalo da [here](https://releases.aspose.com/gis/net/).  
- Un editor di codice come Visual Studio o Visual Studio Code.

## Importare gli spazi dei nomi
Aggiungi le istruzioni `using` richieste al tuo file C# in modo che i tipi API siano disponibili:

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Ora esaminiamo ogni esempio passo‑per‑passo.

## Come ottenere il valore dell'attributo (predefinito)

### Passo 1: Configurare l'ambiente
Definisci il percorso della cartella che contiene i tuoi documenti di test:

```csharp
string dataDir = "Your Document Directory";
```

### Passo 2: Creare un layer GeoJSON
Creeremo **creare il layer geojson** — il primo luogo dove definiamo un attributo che può essere nullo o non impostato:

```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```

### Passo 3: Costruire una feature GIS
Ora **costruiamo la feature GIS** — questo ci fornisce una nuova istanza di feature che rispetta lo schema di attributi appena definito:

```csharp
    Feature feature = layer.ConstructFeature();
```

### Passo 4: Recuperare i valori
Infine, **otteniamo i valori dell'attributo della feature** usando diversi scenari, dimostrando come funzionano i valori predefiniti:

```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // value == null
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // value == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // value == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```

## Come impostare i valori predefiniti

### Passo 1: Creare un altro layer GeoJSON
Questa volta **imposteremo il valore predefinito dell'attributo** direttamente sullo schema:

```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```

### Passo 2: Costruire una feature GIS (di nuovo)
```csharp
    Feature feature = layer.ConstructFeature();
```

### Passo 3: Recuperare e impostare i valori
Recuperiamo il valore predefinito, poi lo modifichiamo per vedere l'effetto di **come impostare il valore predefinito** a runtime:

```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); // value == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); // value == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); // value == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```

## Problemi comuni e consigli
- **Non dimenticare mai di chiudere il blocco `using`.** Il layer viene automaticamente eliminato, liberando i handle dei file.  
- **Quando `CanBeNull` è false, `GetValueOrDefault` restituirà sempre un valore** (sia quello memorizzato sia quello definito come predefinito).  
- **Usa la sovraccarico generica** (`GetValueOrDefault<T>`) per evitare boxing/unboxing per i tipi valore.  
- **Consiglio professionale:** Se hai bisogno di verificare se un attributo è effettivamente impostato, usa `feature.IsAttributeSet("attribute")` prima di chiamare `GetValueOrDefault`.

## Domande frequenti
### Aspose.GIS è compatibile con .NET Core?
Sì, Aspose.GIS è pienamente compatibile con .NET Core, offrendo supporto cross‑platform.

### Posso usare Aspose.GIS per progetti commerciali?
Assolutamente! Aspose.GIS viene fornito con una licenza commerciale che ti permette di usarlo nelle tue applicazioni commerciali senza alcuna restrizione.

### Dove posso trovare supporto e risorse aggiuntive?
Visita il [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) per il supporto della community ed esplora la [documentazione](https://reference.aspose.com/gis/net/) per informazioni approfondite.

### È disponibile una versione di prova gratuita?
Sì, puoi provare Aspose.GIS con una versione di prova gratuita. Scaricala [qui](https://releases.aspose.com/).

### Come posso ottenere una licenza temporanea per scopi di test?
Per licenze temporanee, visita [qui](https://purchase.aspose.com/temporary-license/).

## FAQ aggiuntive
**Q: Cosa succede se chiamo `GetValueOrDefault` su un attributo che non esiste?**  
A: Il metodo lancia un `ArgumentException`. Verifica sempre il nome dell'attributo o usa prima `feature.HasAttribute("name")`.

**Q: Posso cambiare il valore predefinito dopo che il layer è stato creato?**  
A: Sì, puoi modificare `attribute.DefaultValue` e poi chiamare `layer.UpdateAttribute(attribute)` per persistere la modifica.

**Q: Aspose.GIS supporta aggiornamenti massivi dei valori degli attributi?**  
A: Puoi iterare su una collezione di feature e chiamare `SetValue` su ciascuna feature; per dataset di grandi dimensioni, considera l'uso dell'API `FeatureCursor` per migliori prestazioni.

## Conclusione
In questa guida abbiamo coperto **come ottenere l'attributo** valori, come definire e sovrascrivere i valori predefiniti, e come **creare schemi di layer GeoJSON** che soddisfano le esigenze della tua applicazione. Con queste tecniche puoi costruire soluzioni GIS robuste che gestiscono elegantemente dati mancanti o opzionali.

---

**Ultimo aggiornamento:** 2026-01-05  
**Testato con:** Aspose.GIS 24.11 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}