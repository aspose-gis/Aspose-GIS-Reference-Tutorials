---
title: Ottieni valore attributo caratteristica (predefinito)
linktitle: Ottieni valore attributo caratteristica (predefinito)
second_title: API Aspose.GIS .NET
description: Sblocca la potenza di Aspose.GIS per .NET! Recupera e manipola facilmente i valori degli attributi delle caratteristiche con questa guida passo passo. Scarica subito la tua versione di prova!
type: docs
weight: 14
url: /it/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
---
## introduzione
Benvenuti nel mondo di Aspose.GIS per .NET! In questa guida completa, approfondiremo le complessità del recupero dei valori degli attributi delle caratteristiche utilizzando le potenti funzionalità di Aspose.GIS. Che tu sia uno sviluppatore esperto o che tu abbia appena iniziato, questo tutorial ti fornirà una procedura dettagliata, assicurandoti di sfruttare tutto il potenziale di questo straordinario strumento.
## Prerequisiti
Prima di intraprendere questa avventura di codifica, assicurati di disporre dei seguenti prerequisiti:
- Una conoscenza pratica di C# e .NET framework.
-  Aspose.GIS per .NET installato. In caso contrario, scaricalo da[Qui](https://releases.aspose.com/gis/net/).
- Un editor di codice, come Visual Studio, da seguire senza problemi.
## Importa spazi dei nomi
Nel tuo progetto C#, assicurati di includere gli spazi dei nomi necessari:
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
Ora suddividiamo ciascun esempio in una serie di passaggi facili da seguire.
## Ottieni valore attributo caratteristica (predefinito)
### Passaggio 1: impostare l'ambiente
Inizia definendo il percorso della directory dei documenti:
```csharp
string dataDir = "Your Document Directory";
```
### Passaggio 2: crea un livello GeoJson
Crea un layer GeoJson e definisci un attributo con valori predefiniti:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```
### Passaggio 3: costruire una caratteristica
Costruisci una feature utilizzando l'attributo definito:
```csharp
    Feature feature = layer.ConstructFeature();
```
### Passaggio 4: recuperare i valori
Recupera i valori degli attributi con vari scenari:
```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // valore == nullo
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // valore == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // valore == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```
## Impostazione dei valori predefiniti
### Passaggio 1: crea un altro livello GeoJson
Ripeti il processo con un layer GeoJson diverso e un doppio attributo:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```
### Passaggio 2: costruire una funzione (di nuovo)
```csharp
    Feature feature = layer.ConstructFeature();
```
### Passaggio 3: recuperare e impostare i valori
Recupera e imposta i valori degli attributi, mostrando le impostazioni predefinite:
```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); // valore == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); // valore == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); // valore == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```
Congratulazioni! Hai sfruttato con successo la potenza di Aspose.GIS per .NET nel recuperare e manipolare i valori degli attributi delle caratteristiche.
## Conclusione
In questo tutorial, abbiamo esplorato le sfumature del recupero dei valori degli attributi delle caratteristiche utilizzando Aspose.GIS per .NET. Con la sua API intuitiva e robuste funzionalità, Aspose.GIS apre un mondo di possibilità per lo sviluppo GIS in ambienti .NET.
## Domande frequenti
### Aspose.GIS è compatibile con .NET Core?
Sì, Aspose.GIS è completamente compatibile con .NET Core e fornisce supporto multipiattaforma.
### Posso utilizzare Aspose.GIS per progetti commerciali?
Assolutamente! Aspose.GIS viene fornito con una licenza commerciale che ti consente di utilizzarlo nelle tue applicazioni commerciali senza alcuna restrizione.
### Dove posso trovare ulteriore supporto e risorse?
 Visitare il[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33) per il supporto della comunità ed esplorare il[documentazione](https://reference.aspose.com/gis/net/) per informazioni approfondite.
### È disponibile una prova gratuita?
 Sì, puoi esplorare Aspose.GIS con una prova gratuita. Scaricalo[Qui](https://releases.aspose.com/).
### Come posso ottenere una licenza temporanea a scopo di test?
 Per le licenze temporanee, visitare[Qui](https://purchase.aspose.com/temporary-license/).