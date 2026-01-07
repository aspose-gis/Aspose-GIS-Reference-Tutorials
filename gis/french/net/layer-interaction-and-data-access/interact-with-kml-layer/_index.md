---
date: 2026-01-07
description: Apprenez à créer un fichier KML avec Aspose.GIS pour .NET, à générer
  du KML, à ajouter un attribut booléen et à créer une ligne de type LineString dans
  vos applications.
linktitle: Interact with KML Layer
second_title: Aspose.GIS .NET API
title: Comment écrire un fichier KML avec Aspose.GIS pour .NET
url: /fr/net/layer-interaction-and-data-access/interact-with-kml-layer/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment écrire un fichier KML avec Aspose.GIS pour .NET

## Introduction
Dans le monde actuel axé sur les données, la capacité à **write KML file** de façon programmatique vous donne le pouvoir de partager des informations géographiques entre plateformes, de visualiser des itinéraires sur des cartes et d’intégrer des données de localisation dans des applications web ou mobiles. Aspose.GIS pour .NET rend ce processus simple, vous permettant de vous concentrer sur la logique plutôt que sur les subtilités du format de fichier. Dans ce tutoriel, nous parcourrons la création d’une couche KML, l’ajout d’attributs (y compris un attribut booléen) et la construction d’une géométrie line string — le tout avec du code clair, étape par étape.

## Réponses rapides
- **Que signifie « write KML file » ?** Générer un document KML (Keyhole Markup Language) qui décrit des entités géographiques telles que des points, des lignes et des polygones.  
- **Quelle bibliothèque est la meilleure pour .NET ?** Aspose.GIS pour .NET offre une API fluide pour créer et modifier des fichiers KML.  
- **Ai‑je besoin d’une licence pour le développement ?** Une version d’essai gratuite suffit pour l’évaluation ; une licence est requise pour une utilisation en production.  
- **Puis‑je ajouter des attributs personnalisés ?** Oui – vous pouvez ajouter des attributs de type chaîne, entier, **boolean**, et double à chaque entité.  
- **La création de géométrie est‑elle prise en charge ?** Absolument – vous pouvez créer des points, des line strings, des polygones, et plus encore.

## Prérequis
Avant de commencer, assurez‑vous d’avoir les éléments suivants :
- Aspose.GIS pour .NET : téléchargez et installez la bibliothèque depuis la [page de téléchargement Aspose.GIS pour .NET](https://releases.aspose.com/gis/net/).
- Environnement de développement : configurez un environnement adapté, tel que Visual Studio, pour intégrer Aspose.GIS sans problème dans vos projets .NET.

## Importer les espaces de noms
Avant d’interagir avec les couches KML, assurez‑vous d’inclure les espaces de noms nécessaires dans votre projet. Cette étape garantit l’accès aux classes et méthodes requises pour la manipulation de données géospatiales.

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

## Étape 1 : définir le répertoire du document
Définissez le chemin vers votre répertoire de documents où les fichiers KML seront stockés.

```csharp
string dataDir = "Your Document Directory";
```

## Étape 2 : créer une couche KML
Initialisez une couche KML à l’aide d’Aspose.GIS, en spécifiant le chemin du fichier KML.

```csharp
using (var layer = Drivers.Kml.CreateLayer(dataDir + "Kml_File_out.kml"))
{
```

## Étape 3 : définir les attributs (ajouter un attribut booléen)
Ajoutez des attributs à la couche KML pour représenter différents types de données tels que chaîne, entier, **boolean**, et double. C’est ici que vous « add boolean attribute » à chaque entité.

```csharp
layer.Attributes.Add(new FeatureAttribute("string_data", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("int_data", AttributeDataType.Integer));
layer.Attributes.Add(new FeatureAttribute("bool_data", AttributeDataType.Boolean));
layer.Attributes.Add(new FeatureAttribute("float_data", AttributeDataType.Double));
```

## Étape 4 : construire et remplir les entités (créer line string)
Construisez des entités représentant des objets géospatiaux et définissez les valeurs des attributs définis. Ici nous **create line string** pour illustrer un chemin simple.

```csharp
Feature feature = layer.ConstructFeature();
feature.SetValue("string_data", "string value");
feature.SetValue("int_data", 10);
feature.SetValue("bool_data", true);
feature.SetValue("float_data", 3.14);
feature.Geometry = new LineString(new[] { new Point(0, 0), new Point(1, 1) });
layer.Add(feature);
```

## Étape 5 : ajouter une autre entité
Répétez le processus pour ajouter une seconde entité avec des valeurs d’attribut différentes et une géométrie nulle.

```csharp
Feature feature2 = layer.ConstructFeature();
feature2.SetValue("string_data", "string value2");
feature2.SetValue("int_data", 100);
feature2.SetValue("bool_data", false);
feature2.SetValue("float_data", 3.1415);
feature2.Geometry = Geometry.Null;
layer.Add(feature2);
```

## Comment écrire un fichier KML – mise en pratique
En suivant les étapes ci‑dessus, vous disposez maintenant d’un fichier KML pleinement fonctionnel contenant des attributs personnalisés (y compris un drapeau booléen) et une géométrie line string. Vous pouvez ouvrir le `Kml_File_out.kml` résultant dans Google Earth, ArcGIS ou tout visualiseur GIS supportant le KML.

## Problèmes courants et dépannage
- **Erreurs de chemin de fichier** – Assurez‑vous que `dataDir` se termine par un séparateur de chemin (`\` ou `/`) adapté à votre OS.  
- **Licence manquante** – L’essai fonctionne pour l’évaluation, mais une version sous licence est nécessaire pour écrire des fichiers KML sans restriction.  
- **Géométrie nulle** – L’affectation de `Geometry.Null` est intentionnelle pour les entités sans données spatiales ; omettez‑la si vous avez toujours besoin d’une géométrie.

## FAQ
### Aspose.GIS est‑il compatible avec d’autres formats GIS ?
Oui, Aspose.GIS prend en charge divers formats GIS, notamment shapefile, GeoJSON et KML.

### Puis‑je visualiser les données géospatiales créées avec Aspose.GIS ?
Absolument ! Aspose.GIS s’intègre parfaitement aux bibliothèques de cartographie, vous permettant de visualiser vos données géospatiales.

### Existe‑t‑il une version d’essai disponible pour Aspose.GIS ?
Oui, vous pouvez explorer les fonctionnalités d’Aspose.GIS en téléchargeant la [version d’essai gratuite](https://releases.aspose.com/).

### Comment obtenir du support pour Aspose.GIS ?
Visitez le [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pour le support communautaire ou explorez les options de support premium [ici](https://purchase.aspose.com/buy).

### Des licences temporaires sont‑elles disponibles pour Aspose.GIS ?
Oui, vous pouvez obtenir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

## Questions fréquentes supplémentaires

**Q : Comment **how to create KML** des fichiers avec un style personnalisé ?**  
R : Utilisez l’espace de noms `Aspose.Gis.Formats.Kml.Styles` pour définir des icônes, des couleurs de ligne et des styles d’étiquette avant d’ajouter des entités.

**Q : Puis‑je écrire de gros fichiers KML de façon efficace ?**  
R : Écrivez les entités par lots et videz la couche périodiquement afin de maintenir une faible consommation de mémoire.

**Q : Aspose.GIS prend‑il en charge .NET Core et .NET 6+ ?**  
R : Oui, la bibliothèque est entièrement compatible avec .NET Core, .NET 5 et .NET 6.

---

**Dernière mise à jour :** 2026-01-07  
**Testé avec :** Aspose.GIS 24.10 pour .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}