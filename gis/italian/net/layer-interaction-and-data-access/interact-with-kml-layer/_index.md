---
date: 2026-01-07
description: Scopri come scrivere file KML usando Aspose.GIS per .NET, come creare
  KML, aggiungere un attributo booleano e creare una LineString nelle tue applicazioni.
linktitle: Interact with KML Layer
second_title: Aspose.GIS .NET API
title: Come scrivere un file KML con Aspose.GIS per .NET
url: /it/net/layer-interaction-and-data-access/interact-with-kml-layer/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come scrivere un file KML con Aspose.GIS per .NET

## Introduzione
Nel mondo odierno guidato dai dati, la capacità di **scrivere file KML** in modo programmatico ti consente di condividere informazioni geografiche tra piattaforme, visualizzare percorsi su mappe e integrare dati di posizione in app web o mobile. Aspose.GIS per .NET rende questo processo semplice, permettendoti di concentrarti sulla logica anziché sulle complessità del formato file. In questo tutorial vedremo come creare un layer KML, aggiungere attributi (incluso un attributo booleano) e costruire una geometria line string—tutto con codice chiaro passo‑per‑passo.

## Risposte rapide
- **Cosa significa “scrivere file KML”?** Generare un documento KML (Keyhole Markup Language) che descrive caratteristiche geografiche come punti, linee e poligoni.  
- **Quale libreria è la migliore per .NET?** Aspose.GIS per .NET fornisce un'API fluida per creare e modificare file KML.  
- **È necessaria una licenza per lo sviluppo?** Una versione di prova gratuita è sufficiente per la valutazione; è richiesta una licenza per l'uso in produzione.  
- **Posso aggiungere attributi personalizzati?** Sì – è possibile aggiungere attributi di tipo stringa, intero, booleano e double a ciascuna feature.  
- **È supportata la creazione di geometrie?** Assolutamente sì – è possibile creare punti, line string, poligoni e molto altro.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
- Aspose.GIS per .NET: scarica e installa la libreria dalla [pagina di download di Aspose.GIS per .NET](https://releases.aspose.com/gis/net/).
- Ambiente di sviluppo: configura un ambiente di sviluppo adeguato, ad esempio Visual Studio, per integrare Aspose.GIS nei tuoi progetti .NET.

## Importare gli spazi dei nomi
Prima di interagire con i layer KML, includi gli spazi dei nomi necessari nel tuo progetto. Questo passaggio garantisce l'accesso alle classi e ai metodi richiesti per la manipolazione dei dati geospaziali.

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Drawing;
using System.Threading;
using Aspose.Gis.Formats.Kml;
using Aspose.Gis.Formats.Kml.Styles;
using Aspose.Gis.Geometries;
using Point = Aspose.Gis.Geometries.Point;
```

## Passo 1: Impostare la directory del documento
Definisci il percorso della directory in cui verranno salvati i file KML.

```csharp
string dataDir = "Your Document Directory";
```

## Passo 2: Creare un layer KML
Inizializza un layer KML usando Aspose.GIS, specificando il percorso del file KML.

```csharp
using (var layer = Drivers.Kml.CreateLayer(dataDir + "Kml_File_out.kml"))
{
```

## Passo 3: Definire gli attributi (aggiungere attributo booleano)
Aggiungi attributi al layer KML per rappresentare diversi tipi di dati come stringa, intero, **booleano** e double. Qui è dove “aggiungi attributo booleano” a ciascuna feature.

```csharp
layer.Attributes.Add(new FeatureAttribute("string_data", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("int_data", AttributeDataType.Integer));
layer.Attributes.Add(new FeatureAttribute("bool_data", AttributeDataType.Boolean));
layer.Attributes.Add(new FeatureAttribute("float_data", AttributeDataType.Double));
```

## Passo 4: Costruire e popolare le feature (creare line string)
Costruisci le feature che rappresentano entità geospaziali e imposta i valori per gli attributi definiti. Qui **creiamo una line string** per illustrare un percorso semplice.

```csharp
Feature feature = layer.ConstructFeature();
feature.SetValue("string_data", "string value");
feature.SetValue("int_data", 10);
feature.SetValue("bool_data", true);
feature.SetValue("float_data", 3.14);
feature.Geometry = new LineString(new[] { new Point(0, 0), new Point(1, 1) });
layer.Add(feature);
```

## Passo 5: Aggiungere un'altra feature
Ripeti il processo per aggiungere una seconda feature con valori di attributi diversi e una geometria nulla.

```csharp
Feature feature2 = layer.ConstructFeature();
feature2.SetValue("string_data", "string value2");
feature2.SetValue("int_data", 100);
feature2.SetValue("bool_data", false);
feature2.SetValue("float_data", 3.1415);
feature2.Geometry = Geometry.Null;
layer.Add(feature2);
```

## Come scrivere un file KML – Tutto insieme
Seguendo i passaggi sopra, ora disponi di un file KML completamente funzionale che contiene attributi personalizzati (incluso un flag booleano) e una geometria line string. Puoi aprire il risultato `Kml_File_out.kml` in Google Earth, ArcGIS o qualsiasi visualizzatore GIS che supporti KML.

## Problemi comuni e risoluzione
- **Errori di percorso file** – Assicurati che `dataDir` termini con un separatore di percorso (`\` o `/`) appropriato per il tuo OS.  
- **Licenza mancante** – La versione di prova è valida per la valutazione, ma è necessaria una licenza per scrivere file KML senza limitazioni.  
- **Geometria nulla** – Impostare `Geometry.Null` è intenzionale per le feature senza dati spaziali; rimuovilo se hai sempre bisogno di una geometria.

## Domande frequenti
### Aspose.GIS è compatibile con altri formati GIS?
Sì, Aspose.GIS supporta vari formati GIS, inclusi shapefile, GeoJSON e KML.

### Posso visualizzare i dati geospaziali creati con Aspose.GIS?
Assolutamente! Aspose.GIS si integra perfettamente con librerie di mapping, consentendoti di visualizzare i tuoi dati geospaziali.

### È disponibile una versione di prova per Aspose.GIS?
Sì, puoi esplorare le funzionalità di Aspose.GIS scaricando la [versione di prova gratuita](https://releases.aspose.com/).

### Come posso ottenere supporto per Aspose.GIS?
Visita il [forum di Aspose.GIS](https://forum.aspose.com/c/gis/33) per il supporto della community o scopri le opzioni di supporto premium [qui](https://purchase.aspose.com/buy).

### Sono disponibili licenze temporanee per Aspose.GIS?
Sì, puoi ottenere una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

## Altre domande frequenti

**D: Come **creare file KML** con stile personalizzato?**  
R: Usa lo spazio dei nomi `Aspose.Gis.Formats.Kml.Styles` per definire icone, colori delle linee e stili delle etichette prima di aggiungere le feature.

**D: Posso scrivere file KML di grandi dimensioni in modo efficiente?**  
R: Scrivi le feature in batch e svuota periodicamente il layer per mantenere basso l'uso della memoria.

**D: Aspose.GIS supporta .NET Core e .NET 6+?**  
R: Sì, la libreria è pienamente compatibile con .NET Core, .NET 5 e .NET 6.

---

**Ultimo aggiornamento:** 2026-01-07  
**Testato con:** Aspose.GIS 24.10 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}