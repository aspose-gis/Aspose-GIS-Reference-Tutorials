---
title: Créer un polygone avec une géométrie de trou à l'aide d'Aspose.GIS
linktitle: Créer un polygone avec une géométrie de trou
second_title: API Aspose.GIS .NET
description: Découvrez comment créer un polygone avec une géométrie de trou à l'aide d'Aspose.GIS pour .NET. Tutoriel étape par étape avec des exemples de code.
type: docs
weight: 13
url: /fr/net/geometry-creation/create-polygon-with-hole-geometry/
---
## Introduction
Dans ce didacticiel, nous allons parcourir le processus de création d'un polygone avec une géométrie de trou à l'aide d'Aspose.GIS pour .NET. Aspose.GIS est une bibliothèque puissante qui permet aux développeurs de travailler avec des données géospatiales dans leurs applications .NET. 
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les prérequis suivants :
1. Aspose.GIS pour la bibliothèque .NET : vous pouvez le télécharger depuis[ici](https://releases.aspose.com/gis/net/).
2. Environnement de développement : assurez-vous d'avoir un environnement de développement configuré avec Visual Studio ou tout autre IDE .NET installé.
## Importer des espaces de noms
Tout d'abord, vous devez importer les espaces de noms nécessaires pour travailler avec les fonctionnalités d'Aspose.GIS. Voici comment procéder :

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Passons maintenant à la création d'un polygone avec une géométrie de trou à l'aide d'Aspose.GIS pour .NET.
## Étape 1 : Créer un objet polygone
```csharp
Polygon polygon = new Polygon();
```
## Étape 2 : Définir l'anneau extérieur
```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```
## Étape 3 : Définir l'anneau intérieur (trou)
```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```
## Étape 4 : attribuer un anneau extérieur et ajouter un anneau intérieur au polygone
```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```
## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment créer un polygone avec une géométrie de trou à l'aide d'Aspose.GIS pour .NET. Ces connaissances seront bénéfiques pour diverses applications géospatiales où de telles géométries sont essentielles.
## FAQ
### 1. Qu'est-ce qu'Aspose.GIS ?
Aspose.GIS est une bibliothèque .NET qui permet aux développeurs de travailler avec des données géospatiales, leur permettant de créer, lire et manipuler divers formats de fichiers géospatiaux.
### 2. Puis-je utiliser Aspose.GIS pour des projets commerciaux ?
 Oui, vous pouvez utiliser Aspose.GIS pour des projets personnels et commerciaux en achetant une licence. Visite[ici](https://purchase.aspose.com/buy) pour plus de détails.
### 3. Existe-t-il un essai gratuit disponible pour Aspose.GIS ?
 Oui, vous pouvez bénéficier d'un essai gratuit d'Aspose.GIS à partir de[ici](https://releases.aspose.com/).
### 4. Où puis-je trouver de l'aide pour Aspose.GIS ?
 Vous pouvez trouver du support pour Aspose.GIS sur le[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33).
### 5. Comment puis-je obtenir une licence temporaire pour Aspose.GIS ?
 Vous pouvez obtenir une licence temporaire pour Aspose.GIS auprès de[ici](https://purchase.aspose.com/temporary-license/).