---
date: 2025-12-20
description: Apprenez à limiter la précision lors de l’écriture de géométries avec
  Aspose.GIS pour .NET. Ce guide étape par étape vous aide à gérer les données spatiales
  avec un contrôle exact des coordonnées.
linktitle: Limit Precision Writing Geometries
second_title: Aspose.GIS .NET API
title: Comment limiter la précision lors de l'écriture de géométries avec Aspose.GIS
url: /fr/net/geometry-processing/limit-precision-writing-geometries/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment limiter la précision lors de l'écriture de géométries avec Aspose.GIS

Si vous vous demandez **comment limiter la précision** lors de l'écriture de géométries dans une application GIS .NET, Aspose.GIS pour .NET offre une méthode simple et haute performance pour contrôler l’arrondi des coordonnées. Dans ce tutoriel, nous parcourrons l’ensemble du processus — de la configuration de l’environnement à la vérification que la sortie respecte les règles de précision que vous avez définies.

## Réponses rapides
- **Que signifie « limiter la précision » ?** Cela arrondit les valeurs de coordonnées à un nombre défini de chiffres fractionnaires lors de l’écriture d’un fichier spatial.  
- **Quel format est utilisé dans l’exemple ?** GeoJSON, mais les mêmes options s’appliquent aux autres formats pris en charge.  
- **Ai‑je besoin d’une licence pour essayer cela ?** Un essai gratuit fonctionne pour le développement et les tests ; une licence commerciale est requise pour la production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Puis‑je contrôler séparément la précision de la coordonnée Z ?** Oui — utilisez `ZPrecisionModel` pour définir des valeurs exactes ou arrondies.

## Comment limiter la précision lors de l'écriture de géométries
Limiter la précision est essentiel lorsque vous avez besoin d’une représentation cohérente des coordonnées entre différents outils GIS, de réduire la taille du fichier ou de respecter des normes d’échange de données. Ci‑dessous, nous définirons les options de précision, écrirons une géométrie, puis la relirons pour confirmer l’arrondi.

## Prérequis

### 1. Téléchargement et installation
Téléchargez le dernier package Aspose.GIS pour .NET depuis le site officiel : [download link](https://releases.aspose.com/gis/net/). Suivez le guide d’installation pour ajouter le package NuGet à votre projet.

### 2. Importation d’espace de noms
Ajoutez les espaces de noms requis afin de pouvoir accéder aux classes GIS et aux utilitaires d’aide.

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

## Guide étape par étape

### Étape 1 : Définir les options de précision
Créez une instance de `GeoJsonOptions` et indiquez à Aspose.GIS le nombre de chiffres fractionnaires souhaité pour les coordonnées X/Y et Z.

```csharp
var options = new GeoJsonOptions
{
    // Limit X and Y coordinates to 3 fractional digits.
    XYPrecisionModel = PrecisionModel.Rounding(3),

    // Write all fractional digits of the Z coordinate.
    ZPrecisionModel = PrecisionModel.Exact
};
```

### Étape 2 : Définir le chemin de sortie
Spécifiez où le fichier GeoJSON résultant sera enregistré.

```csharp
var path = "Your Document Directory" + "LimitPrecisionWhenWritingGeometries_out.json";
```

### Étape 3 : Créer et remplir la géométrie
Ouvrez un nouveau `VectorLayer` avec les options définies ci‑dessus, construisez une géométrie `Point` et ajoutez‑la à la couche.

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

### Étape 4 : Lire et vérifier la précision
Ouvrez le fichier que vous venez de créer et affichez les coordonnées. Vous devriez voir les valeurs X/Y arrondies à trois décimales tandis que la valeur Z reste exacte.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.GeoJson))
{
    var point = (IPoint)layer[0].Geometry;

    // Output: 1.889, 1.001, 1.123456789
    Console.WriteLine("{0}, {1}, {2}", point.X, point.Y, point.Z);
}
```

## Problèmes courants & astuces

- **Erreurs de chemin :** Assurez‑vous que le répertoire indiqué dans `path` existe ou utilisez `Path.Combine` avec `Environment.CurrentDirectory` pour construire un chemin de fichier sûr.  
- **Précision non appliquée :** Vérifiez que vous transmettez l’objet `GeoJsonOptions` lors de la création de la couche ; sinon la précision par défaut (double complet) est utilisée.  
- **Grandes ensembles de données :** Pour les opérations en masse, envisagez de réutiliser une seule instance de `VectorLayer` et d’ajouter les entités par lots afin d’améliorer les performances.

## Foire aux questions

**Q : Aspose.GIS pour .NET est‑il compatible avec d’autres formats GIS ?**  
R : Oui, il prend en charge Shapefile, GeoJSON, KML, GML et bien d’autres, permettant une conversion fluide entre les formats.

**Q : Puis‑je essayer Aspose.GIS pour .NET avant d’acheter ?**  
R : Absolument. Un essai gratuit est disponible depuis la page de téléchargement, vous donnant un accès complet à toutes les fonctionnalités pour évaluation.

**Q : Comment obtenir une licence temporaire pour les tests ?**  
R : Les licences d’évaluation temporaires peuvent être générées via le portail de licences Aspose ; elles sont valables 30 jours.

**Q : Où puis‑je obtenir de l’aide en cas de problème ?**  
R : Le forum Aspose.GIS et le tag Stack Overflow `aspose-gis` sont d’excellents endroits pour poser des questions et trouver des solutions communautaires.

**Q : La bibliothèque fonctionne‑t‑elle aussi bien pour de petits scripts que pour des applications à l’échelle d’entreprise ?**  
R : Oui, Aspose.GIS est conçu pour gérer tout, des prototypes rapides aux applications serveur à haut débit.

## Conclusion
En suivant les étapes ci‑dessus, vous savez maintenant **comment limiter la précision** lors de l’écriture de géométries avec Aspose.GIS pour .NET. Contrôler l’arrondi des coordonnées permet de garder vos données spatiales propres, interopérables et économes en stockage — des avantages clés pour tout projet centré sur le GIS.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2025-12-20  
**Testé avec :** Aspose.GIS 24.11 pour .NET  
**Auteur :** Aspose