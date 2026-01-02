---
date: 2026-01-02
description: Apprenez à ajouter une entité ponctuelle tout en définissant les noms
  de champs et en lisant l’ID d’objet à l’aide d’Aspose.GIS pour .NET. Guide étape
  par étape pour les développeurs.
linktitle: Specify Object ID and Geometry Field Names
second_title: Aspose.GIS .NET API
title: Ajouter une entité point et spécifier les noms des champs ID d’objet et de
  géométrie
url: /fr/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter une entité ponctuelle et spécifier les noms des champs ID d’objet et Géométrie

## Introduction
Se lancer dans le domaine des systèmes d’information géographique (SIG) avec Aspose.GIS for .NET ouvre un monde de possibilités pour les développeurs et les passionnés. Dans ce tutoriel, **vous apprendrez à ajouter une entité ponctuelle** tout en **définissant les noms des champs** et **en lisant les valeurs d’ID d’objet**, vous offrant ainsi un contrôle complet sur vos données spatiales.

## Réponses rapides
- **Quel est le but principal de ce guide ?** Montrer comment ajouter une entité ponctuelle et configurer les noms des champs ID d’objet et Géométrie.  
- **Quelle bibliothèque est utilisée ?** Aspose.GIS for .NET.  
- **Ai‑je besoin d’une licence ?** Une version d’essai gratuite est disponible ; une licence est requise pour la production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Puis‑je lire l’ID d’objet après l’insertion ?** Oui – le tutoriel montre comment lire l’ID d’objet depuis la couche.

## Prérequis
Avant de plonger dans le tutoriel, assurez‑vous d’avoir les prérequis suivants :
- Aspose.GIS for .NET : téléchargez et installez la bibliothèque depuis [ici](https://releases.aspose.com/gis/net/).
- Répertoire de documents : créez un répertoire pour vos documents afin de stocker les géodatabases.
- Environnement .NET : assurez‑vous d’avoir un environnement .NET fonctionnel.

## Importer les espaces de noms
Pour démarrer, vous devez importer les espaces de noms nécessaires dans votre projet. Ces espaces de noms fournissent les classes et méthodes essentielles pour interagir avec Aspose.GIS for .NET.

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## Étape 1 : Ajouter une entité ponctuelle et spécifier les noms des champs ID d’objet et Géométrie
Dans cette étape, vous apprendrez à configurer les noms des champs ID d’objet et Géométrie pour vos données SIG. Cela est crucial pour une gestion efficace des données et pour pouvoir **lire l’ID d’objet** ultérieurement.

### Étape 1.1 : Définir le répertoire de documents
Commencez par définir le chemin vers votre répertoire de documents :

```csharp
string dataDir = "Your Document Directory";
```

### Étape 1.2 : Créer une GeoDatabase et définir les options
Créez une GeoDatabase avec les **noms de champs** souhaités pour l’ID d’objet et la Géométrie :

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

### Étape 1.3 : Créer et ajouter une couche
Créez une couche au sein de la GeoDatabase et ajoutez une entité représentant une géométrie ponctuelle :

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

### Étape 1.4 : Ouvrir et récupérer les données de la couche
Ouvrez la couche et récupérez l’entité que vous venez d’ajouter. Cela montre comment **lire l’ID d’objet** depuis le jeu de données :

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## Pourquoi définir des noms de champs personnalisés ?
Personnaliser les noms des champs ID d’objet et Géométrie vous offre de la flexibilité lors de l’intégration avec des bases de données existantes ou pour respecter les conventions de nommage requises par les applications en aval. Cela rend également les données plus auto‑descriptives, ce qui simplifie la maintenance et la collaboration.

## Pièges courants et dépannage
- **Répertoire manquant** – Assurez‑vous que `dataDir` pointe vers un dossier existant ; sinon, `Dataset.Create` lèvera une exception.
- **Conflits de noms de champs** – Si un champ portant le même nom existe déjà dans la géodatabase, la création échouera. Choisissez des noms uniques.
- **Incohérence de référence spatiale** – Faites toujours correspondre le système de référence spatiale (par ex., WGS84) avec les données que vous prévoyez de stocker.

## Conclusion
Félicitations ! Vous avez appris à **ajouter une entité ponctuelle**, **définir les noms des champs**, et **lire l’ID d’objet** avec Aspose.GIS for .NET. Cette base vous permet de créer des applications SIG robustes et de gérer les données spatiales en toute confiance.

## Questions fréquentes
### Q : Puis‑je utiliser Aspose.GIS for .NET dans mes applications web ?
R : Oui, Aspose.GIS for .NET convient aux applications de bureau et web, offrant des capacités géospatiales polyvalentes.

### Q : Existe‑t‑il une version d’essai disponible avant l’achat ?
R : Oui, vous pouvez explorer les fonctionnalités d’Aspose.GIS for .NET avec une version d’essai gratuite disponible [ici](https://releases.aspose.com/).

### Q : Comment obtenir une licence temporaire pour Aspose.GIS for .NET ?
R : Vous pouvez obtenir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/) à des fins d’évaluation.

### Q : Quels systèmes de référence spatiale Aspose.GIS for .NET prend‑il en charge ?
R : Aspose.GIS for .NET prend en charge divers systèmes de référence spatiale, offrant une flexibilité pour différents jeux de données géographiques.

### Q : Où puis‑je obtenir de l’aide ou discuter des questions liées à Aspose.GIS ?
R : Visitez le forum Aspose.GIS [ici](https://forum.aspose.com/c/gis/33) pour le support et les discussions.

## Questions fréquentes supplémentaires

**Q : Puis‑je changer le champ ID d’objet après la création de la couche ?**  
R : Non. Le nom du champ est défini lors de la création de la couche ; vous devez recréer la couche avec un nouvel objet `FileGdbOptions` pour le modifier.

**Q : Comment récupérer d’autres valeurs d’attributs en plus de l’ID d’objet ?**  
R : Utilisez `feature.GetValue<T>("FieldName")` où `FieldName` est le nom de l’attribut que vous souhaitez lire.

**Q : Est‑il possible d’ajouter plusieurs entités ponctuelles en une seule fois ?**  
R : Oui. Parcourez vos données, créez une entité pour chaque point, définissez sa géométrie, puis appelez `layer.Add(feature)` dans le même bloc `using`.

**Q : Aspose.GIS prend‑il en charge d’autres types de géométrie ?**  
R : Absolument. Vous pouvez travailler avec `LineString`, `Polygon`, `MultiPoint`, etc., en créant les objets géométriques appropriés.

**Q : Que se passe‑t‑il si j’essaie de lire un ID d’objet qui n’existe pas ?**  
R : Accéder à un indice hors limites (par ex., `layer[10]` alors qu’une seule entité existe) lèvera une `IndexOutOfRangeException`. Vérifiez toujours `layer.Count` au préalable.

---

**Dernière mise à jour :** 2026-01-02  
**Testé avec :** Aspose.GIS for .NET 24.11  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}