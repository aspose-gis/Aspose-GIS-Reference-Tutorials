---
date: 2026-07-05
description: Apprenez comment convertir shapefile en geojson en utilisant Aspose.GIS
  for .NET. Le guide couvre également la copie des attributs entre les layers et la
  génération d'un fichier geojson en c#.
keywords:
- convert shapefile to geojson
- export shapefile as geojson
- aspose gis conversion
- read shapefile c#
- write geojson c#
linktitle: Extraire Features en GeoJSON
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  headline: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  name: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  steps:
  - name: Open Input Shapefile
    text: The `VectorLayer.Open` method reads a Shapefile and returns an enumerable
      collection of `Feature` objects that you can iterate over.
  - name: Create Output GeoJSON
    text: '`VectorLayer.Create` with the `Drivers.GeoJson` driver creates an empty
      GeoJSON file ready to receive features.'
  - name: Copy Attributes Between Layers
    text: '`CopyAttributes` copies the attribute schema (field names and data types)
      from the source Shapefile to the new GeoJSON layer in a single call.'
  - name: Process Features
    text: Iterate through each feature in the Shapefile so you can apply any custom
      logic before writing it out.
  - name: Filter Features by Date
    text: In this example we skip records whose `dob` (date of birth) field is missing
      or earlier than 1 Jan 1982. Adjust the filter to match your own data requirements.
  - name: Construct a New Feature (C# Generate GeoJSON File)
    text: A `Feature` represents a single spatial element containing geometry and
      attribute data. Here we build a new `Feature` for the GeoJSON layer, copy the
      geometry and attribute values, and add it to the output. This is the core of
      *c# generate geojson file*. Congratulations! You’ve successfully **conver
  type: HowTo
- questions:
  - answer: Visit the [Aspose.GIS documentation](https://reference.aspose.com/gis/net/)
      for in‑depth information.
    question: Where can I find more documentation?
  - answer: You can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I get a temporary license?
  - answer: Join the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I seek support?
  - answer: Yes, you can find the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: You can buy the product [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Convertir Shapefile en GeoJSON avec Aspose.GIS for .NET
url: /fr/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertir un Shapefile en GeoJSON avec Aspose.GIS pour .NET

## Introduction
Dans ce tutoriel complet, étape par étape, vous apprendrez **comment convertir un shapefile en geojson** en utilisant la puissante bibliothèque Aspose.GIS pour .NET. Que vous construisiez un service web cartographique, prépariez des données pour une application GIS mobile, ou ayez simplement besoin d’échanger des données entre formats, ce guide vous montre exactement quoi faire, pourquoi chaque étape est importante et comment éviter les pièges courants.

## Réponses rapides
- **Quel est le sujet de ce tutoriel ?** Conversion d’un Shapefile en fichier GeoJSON, copie des attributs entre les couches et génération du résultat avec C#.
- **Quelle bibliothèque est requise ?** Aspose.GIS pour .NET.
- **Ai‑je besoin d’une licence ?** Une licence temporaire ou complète est requise en production ; un essai gratuit suffit pour l’évaluation.
- **Combien de temps prend l’implémentation ?** Environ 10‑15 minutes pour une conversion de base.
- **Puis‑je l’exécuter sur .NET Core/.NET 6 ?** Oui – le code fonctionne sur toutes les versions .NET prises en charge.

## Qu’est‑ce que la conversion d’un shapefile en geojson ?
Convertir un Shapefile en GeoJSON signifie lire les entités vectorielles du format Shapefile classique d’ESRI et les écrire sous forme d’un document GeoJSON moderne, adapté au web. Cette transformation vous permet d’alimenter directement les bibliothèques de cartographie JavaScript telles que Leaflet ou Mapbox GL, et simplifie l’échange de données entre les outils GIS de bureau et les API web.

## Pourquoi utiliser Aspose.GIS pour cette conversion ?
Aspose.GIS abstrait l’analyse binaire de bas niveau, prend en charge plus de 50 formats d’entrée et de sortie, et peut traiter des ensembles de données de plusieurs centaines de pages sans charger le fichier complet en mémoire. La bibliothèque offre également une API propre, orientée objet, qui fonctionne sur .NET Framework, .NET Core et .NET 5/6, vous permettant de vous concentrer sur la logique métier plutôt que sur les particularités des formats.

## Prérequis
- Aspose.GIS pour .NET : assurez‑vous que la bibliothèque est installée. Sinon, vous pouvez la télécharger depuis la [page Aspose.GIS pour .NET](https://releases.aspose.com/gis/net/).
- Données Shapefile : disposez d’un Shapefile prêt à être utilisé. Si vous avez besoin de données d’exemple, vous pouvez les trouver dans la [documentation Aspose.GIS](https://reference.aspose.com/gis/net/).
- Environnement .NET : configurez un environnement .NET pour exécuter le code fourni.
- Répertoire de documents : définissez le chemin vers votre répertoire de documents dans l’extrait de code.

Maintenant que tout est en place, commençons à convertir le shapefile en geojson !

## Comment convertir un Shapefile en GeoJSON
Chargez le Shapefile source, créez une couche GeoJSON cible, copiez le schéma des attributs, filtrez les enregistrements et écrivez les résultats — le tout en quelques étapes concises. Le flux de travail complet tient confortablement dans un seul bloc `using`, garantissant la libération automatique des ressources.

### Étape 1 : Ouvrir le Shapefile d’entrée
La méthode `VectorLayer.Open` lit un Shapefile et renvoie une collection énumérable d’objets `Feature` que vous pouvez parcourir.

```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```

### Étape 2 : Créer le GeoJSON de sortie
`VectorLayer.Create` avec le pilote `Drivers.GeoJson` crée un fichier GeoJSON vide prêt à recevoir des entités.

```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```

### Étape 3 : Copier les attributs entre les couches
`CopyAttributes` copie le schéma des attributs (noms de champs et types de données) du Shapefile source vers la nouvelle couche GeoJSON en un seul appel.

```csharp
outputLayer.CopyAttributes(inputLayer);
```

### Étape 4 : Traiter les entités
Parcourez chaque entité du Shapefile afin d’appliquer une logique personnalisée avant de l’écrire.

```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```

### Étape 5 : Filtrer les entités par date
Dans cet exemple, nous ignorons les enregistrements dont le champ `dob` (date de naissance) est manquant ou antérieur au 1 janv. 1982. Ajustez le filtre selon vos propres exigences de données.

```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```

### Étape 6 : Construire une nouvelle entité (C# Générer un fichier GeoJSON)
Une `Feature` représente un seul élément spatial contenant la géométrie et les données d’attributs.  
Ici, nous construisons une nouvelle `Feature` pour la couche GeoJSON, copions la géométrie et les valeurs d’attributs, puis l’ajoutons à la sortie. C’est le cœur de *c# generate geojson file*.

```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```

Félicitations ! Vous avez réussi à **convertir un shapefile en geojson** et avez appris à **copier les attributs entre les couches** en cours de route.

## Problèmes courants et solutions
| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| Le fichier de sortie est vide | `CopyAttributes` appelé après la fermeture de la couche de sortie | Assurez‑vous que le bloc `using` pour `outputLayer` reste ouvert jusqu’après l’ajout de toutes les entités. |
| Le filtre de date supprime tous les enregistrements | Nom de champ incorrect ou format de date inattendu | Vérifiez le nom de l’attribut (`dob`) et utilisez `GetValue<string>` si les dates sont stockées sous forme de chaînes. |
| Exception de licence | Exécution sans licence Aspose.GIS valide en production | Appliquez une licence temporaire ou complète comme décrit dans la documentation Aspose. |

## Foire aux questions
**Q : Où puis‑je trouver davantage de documentation ?**  
A : Visitez la [documentation Aspose.GIS](https://reference.aspose.com/gis/net/) pour des informations détaillées.

**Q : Comment obtenir une licence temporaire ?**  
A : Vous pouvez obtenir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

**Q : Où puis‑je obtenir du support ?**  
A : Rejoignez le [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pour le support communautaire et les discussions.

**Q : Un essai gratuit est‑il disponible ?**  
A : Oui, vous pouvez trouver l’essai gratuit [ici](https://releases.aspose.com/).

**Q : Où puis‑je acheter Aspose.GIS pour .NET ?**  
A : Vous pouvez acheter le produit [ici](https://purchase.aspose.com/buy).

## Conclusion
Dans ce tutoriel, nous avons exploré le processus complet de **conversion d’un shapefile en geojson** avec Aspose.GIS pour .NET, démontré comment **copier les attributs entre les couches**, et présenté une méthode propre pour *c# generate geojson file*. Expérimentez avec différents filtres, des ensembles de données plus volumineux ou des transformations géométriques supplémentaires afin de tirer pleinement parti des capacités de la bibliothèque.

---

**Last Updated:** 2026-07-05  
**Tested With:** Aspose.GIS for .NET (latest stable release)  
**Author:** Aspose

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Tutoriels associés

- [Comment convertir GeoJSON en File GDB avec Aspose.GIS pour .NET](/gis/net/layer-management/convert-geojson-layer-to-file-gdb/)
- [Comment lire GeoJSON depuis un flux avec Aspose.GIS pour .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Comment convertir GeoJSON en TopoJSON avec Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}