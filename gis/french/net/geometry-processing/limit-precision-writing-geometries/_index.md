---
date: 2026-05-31
description: Apprenez comment limiter la precision lors de l'écriture de geometries
  avec Aspose.GIS pour .NET, réduire la taille du GeoJSON et garder le coordinate
  control.
keywords:
- how to limit precision
- reduce geojson size
- Aspose.GIS precision control
linktitle: Limiter la precision writing geometries
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to limit precision when writing geometries with Aspose.GIS
    for .NET, reducing GeoJSON size and keeping coordinate control.
  headline: How to Limit Precision Writing Geometries with Aspose.GIS
  type: TechArticle
- description: Learn how to limit precision when writing geometries with Aspose.GIS
    for .NET, reducing GeoJSON size and keeping coordinate control.
  name: How to Limit Precision Writing Geometries with Aspose.GIS
  steps:
  - name: Define Precision Options
    text: The `GeoJsonOptions` class lets you specify how many fractional digits to
      keep for X/Y and Z coordinates. `PrecisionModel` defines how coordinate values
      are rounded or kept exact during writing.
  - name: Set Output Path
    text: Specify where the resulting GeoJSON file will be saved. `VectorLayer` is
      Aspose.GIS's container for a collection of features that share the same schema;
      it writes to the path you provide using the options set earlier.
  - name: Create and Populate Geometry
    text: Open a new `VectorLayer` with the options defined above, construct a `Point`
      geometry, and add it to the layer. `Point` represents a single coordinate (X,
      Y, optional Z) in a spatial reference system. It is the simplest geometry type
      and is used here to demonstrate precision rounding.
  - name: Read and Verify Precision
    text: Open the file you just created and print the coordinates. You should see
      the X/Y values rounded to three decimal places while the Z value remains exact.
      When you read the file back, Aspose.GIS parses the rounded values directly,
      so the in‑memory `Point` reflects the precision you defined during writ
  type: HowTo
- questions:
  - answer: Yes, it supports **50+** formats—including Shapefile, GeoJSON, KML, GML,
      and CSV—allowing seamless conversion between them.
    question: Is Aspose.GIS for .NET compatible with other GIS formats?
  - answer: Absolutely. A free trial is available from the download page, giving you
      full access to all features for evaluation.
    question: Can I try Aspose.GIS for .NET before purchasing?
  - answer: Temporary evaluation licenses can be generated via the Aspose license
      portal; they are valid for 30 days.
    question: How do I obtain a temporary license for testing?
  - answer: The Aspose.GIS forum and Stack Overflow tag `aspose-gis` are great places
      to ask questions and find community solutions.
    question: Where can I get help if I run into issues?
  - answer: Yes, Aspose.GIS is designed to handle everything from quick prototypes
      to high‑throughput server workloads, processing multi‑gigabyte datasets with
      low memory overhead.
    question: Does the library work for both small scripts and enterprise‑scale applications?
  type: FAQPage
second_title: Aspise.GIS .NET API
title: Comment limiter la precision lors de l'écriture de geometries avec Aspose.GIS
url: /fr/net/geometry-processing/limit-precision-writing-geometries/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment limiter la précision lors de l'écriture de géométries avec Aspose.GIS

Si vous vous demandez **comment limiter la précision** lors de l'écriture de géométries dans une application GIS .NET, Aspose.GIS pour .NET offre une méthode simple et haute performance pour contrôler l'arrondi des coordonnées. Dans ce tutoriel, nous parcourrons l'ensemble du processus — de la configuration de l'environnement à la vérification que la sortie respecte les règles de précision que vous définissez.

## Réponses rapides
- **Que signifie « limiter la précision » ?** Il arrondit les valeurs de coordonnées à un nombre défini de chiffres fractionnaires lors de l'écriture d'un fichier spatial.  
- **Quel format est utilisé dans l'exemple ?** GeoJSON, mais les mêmes options s'appliquent aux autres formats pris en charge.  
- **Ai‑je besoin d'une licence pour essayer cela ?** Un essai gratuit fonctionne pour le développement et les tests ; une licence commerciale est requise pour la production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Puis‑je contrôler séparément la précision de la coordonnée Z ?** Oui — utilisez `ZPrecisionModel` pour définir des valeurs exactes ou arrondies.

## Comment limiter la précision lors de l'écriture de géométries

Chargez votre écrivain GeoJSON avec un objet `GeoJsonOptions` qui spécifie la précision souhaitée pour les coordonnées X/Y et Z, puis écrivez la géométrie et relisez‑la — ce flux complet tient en moins de dix lignes de code et garantit que toutes les coordonnées sont arrondies exactement comme vous l'avez défini.

Limiter la précision est essentiel lorsque vous avez besoin d'une représentation cohérente des coordonnées entre différents outils GIS, de réduire la taille du fichier ou de respecter les normes d'échange de données. Ci‑dessous, nous définirons les options de précision, écrirons une géométrie, puis la relirons pour confirmer l'arrondi.

## Qu'est‑ce que la limitation de précision ?

La limitation de précision est le processus d'arrondir la partie fractionnaire des valeurs de coordonnées à un nombre fixe de chiffres avant de persister la géométrie dans un format de fichier. Cela garantit que chaque consommateur du fichier voit les mêmes valeurs numériques, ce qui aide à éviter de petites discordances pouvant entraîner des erreurs de topologie.

## Pourquoi utiliser Aspose.GIS pour le contrôle de la précision ?

Aspose.GIS prend en charge **plus de 50** formats d'entrée et de sortie — y compris GeoJSON, Shapefile, KML et GML — et peut traiter des fichiers contenant **des centaines de milliers d'entités** sans charger l'ensemble du jeu de données en mémoire. Ses modèles de précision intégrés vous permettent d'arrondir les coordonnées en un seul appel, éliminant ainsi le besoin de scripts de post‑traitement manuels.

## Prérequis

### 1. Téléchargement et installation
Récupérez le dernier package Aspose.GIS pour .NET depuis le site officiel : [download link](https://releases.aspose.com/gis/net/). Suivez le guide d'installation pour ajouter le package NuGet à votre projet.

### 2. Importation d'espace de noms
Ajoutez les espaces de noms requis afin de pouvoir accéder aux classes GIS et aux utilitaires d'aide.

## Guide étape par étape

### Étape 1 : Définir les options de précision
La classe `GeoJsonOptions` vous permet de spécifier le nombre de chiffres fractionnaires à conserver pour les coordonnées X/Y et Z.  
`PrecisionModel` définit comment les valeurs de coordonnées sont arrondies ou conservées exactes lors de l'écriture.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Étape 2 : Définir le chemin de sortie
Spécifiez où le fichier GeoJSON résultant sera enregistré.  
`VectorLayer` est le conteneur d'Aspose.GIS pour une collection d'entités partageant le même schéma ; il écrit vers le chemin que vous fournissez en utilisant les options définies précédemment.  

```csharp
var options = new GeoJsonOptions
{
    // Limit X and Y coordinates to 3 fractional digits.
    XYPrecisionModel = PrecisionModel.Rounding(3),

    // Write all fractional digits of the Z coordinate.
    ZPrecisionModel = PrecisionModel.Exact
};
```

### Étape 3 : Créer et remplir la géométrie
Ouvrez un nouveau `VectorLayer` avec les options définies ci‑dessus, créez une géométrie `Point` et ajoutez‑la à la couche.  
`Point` représente une seule coordonnée (X, Y, Z optionnel) dans un système de référence spatiale. C'est le type de géométrie le plus simple et il est utilisé ici pour démontrer l'arrondi de précision.  

```csharp
var path = "Your Document Directory" + "LimitPrecisionWhenWritingGeometries_out.json";
```

### Étape 4 : Lire et vérifier la précision
Ouvrez le fichier que vous venez de créer et affichez les coordonnées. Vous devriez voir les valeurs X/Y arrondies à trois décimales tandis que la valeur Z reste exacte.  
Lorsque vous relisez le fichier, Aspose.GIS analyse directement les valeurs arrondies, de sorte que le `Point` en mémoire reflète la précision que vous avez définie lors de l'écriture.  

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    var point = new Point();
    point.X = 1.8888888;
    point.Y = 1.00123;
    point.Z = 1.123456789;

    Feature feature = layer.ConstructFeature();
    feature.Geometry = point;
    layer.Add(feature);
}
```

## Problèmes courants et astuces

- **Erreurs de chemin :** Assurez‑vous que le répertoire dans `path` existe ou utilisez `Path.Combine` avec `Environment.CurrentDirectory` pour construire un chemin de fichier sûr.  
- **Précision non appliquée :** Vérifiez que vous transmettez l'objet `GeoJsonOptions` lors de la création de la couche ; sinon la précision par défaut (double complet) est utilisée.  
- **Grands ensembles de données :** Pour les opérations en masse, envisagez de réutiliser une seule instance de `VectorLayer` et d'ajouter les entités par lots pour améliorer les performances.

## Questions fréquemment posées

**Q : Aspose.GIS pour .NET est‑il compatible avec d'autres formats GIS ?**  
A : Oui, il prend en charge **plus de 50** formats — y compris Shapefile, GeoJSON, KML, GML et CSV — permettant une conversion transparente entre eux.

**Q : Puis‑je essayer Aspose.GIS pour .NET avant d'acheter ?**  
A : Absolument. Un essai gratuit est disponible sur la page de téléchargement, vous donnant un accès complet à toutes les fonctionnalités pour l'évaluation.

**Q : Comment obtenir une licence temporaire pour les tests ?**  
A : Des licences d'évaluation temporaires peuvent être générées via le portail de licences Aspose ; elles sont valides pendant 30 jours.

**Q : Où puis‑je obtenir de l'aide en cas de problème ?**  
A : Le forum Aspose.GIS et le tag Stack Overflow `aspose-gis` sont d'excellents endroits pour poser des questions et trouver des solutions communautaires.

**Q : La bibliothèque fonctionne‑t‑elle à la fois pour de petits scripts et des applications à l'échelle d'entreprise ?**  
A : Oui, Aspose.GIS est conçu pour gérer tout, des prototypes rapides aux charges de travail serveur à haut débit, traitant des ensembles de données multi‑gigaoctets avec une faible consommation de mémoire.

---

**Dernière mise à jour :** 2026-05-31  
**Testé avec :** Aspose.GIS 24.11 for .NET  
**Auteur :** Aspose

## Tutoriels associés

- [Créer une couche vectorielle, limiter la précision avec Aspose.GIS pour .NET](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [Comment convertir GeoJSON – Aspose.GIS pour .NET](/gis/net/geo-data-conversion/)
- [Comment vérifier la géométrie avec Aspose.GIS pour .NET](/gis/net/geometry-analysis/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.GeoJson))
{
    var point = (IPoint)layer[0].Geometry;

    // Output: 1.889, 1.001, 1.123456789
    Console.WriteLine("{0}, {1}, {2}", point.X, point.Y, point.Z);
}
```

{{< /blocks/products/pf/main-wrap-class >}}