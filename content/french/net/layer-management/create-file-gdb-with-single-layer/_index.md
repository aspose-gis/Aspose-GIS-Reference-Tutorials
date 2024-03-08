---
title: Créer un fichier GDB avec une seule couche
linktitle: Créer un fichier GDB avec une seule couche
second_title: API Aspose.GIS .NET
description: Libérez le potentiel de la gestion des données géospatiales dans .NET avec Aspose.GIS. Découvrez comment créer des géodatabases fichier et des couches étape par étape. Télécharger maintenant!
type: docs
weight: 11
url: /fr/net/layer-management/create-file-gdb-with-single-layer/
---
## Introduction
Êtes-vous prêt à élever vos applications géospatiales avec des géodatabases et des couches de fichiers robustes ? Ne cherchez pas plus loin que Aspose.GIS pour .NET. Dans ce didacticiel, nous vous guiderons tout au long du processus de création d'une géodatabase fichier (GDB) avec une seule couche à l'aide d'Aspose.GIS pour .NET. Exploitez sans effort la puissance de la gestion et de la visualisation des données spatiales dans vos applications .NET.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
1.  Aspose.GIS pour .NET : assurez-vous que la bibliothèque Aspose.GIS est installée. Vous pouvez le télécharger depuis le[Page de téléchargement d'Aspose.GIS pour .NET](https://releases.aspose.com/gis/net/).
2. Environnement de développement : configurez un environnement de développement .NET fonctionnel sur votre machine.
3. Répertoire de documents : choisissez ou créez un répertoire sur votre système dans lequel vous stockerez vos fichiers de données géospatiales.
## Importer des espaces de noms
Pour commencer, vous devez importer les espaces de noms nécessaires dans votre projet .NET. Ces espaces de noms donneront accès aux fonctionnalités Aspose.GIS. Ajoutez les lignes suivantes au début de votre fichier de code :
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```
## Étape 1 : Configurez votre répertoire de documents
```csharp
string dataDir = "Your Document Directory";
```
Remplacez « Votre répertoire de documents » par le chemin d'accès au répertoire dans lequel vous souhaitez stocker vos fichiers de données géospatiales.
## Étape 2 : Créer une géodatabase fichier avec une seule couche
```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```
Cet extrait de code crée une géodatabase fichier avec une seule couche et y ajoute une entité linéaire.
## Étape 3 : ouvrir la géodatabase fichier et récupérer les informations sur la couche
```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Sortie : nombre de fonctionnalités : 1
}
```
Au cours de cette étape, nous ouvrons la géodatabase fichier créée, récupérons la couche nommée « couche » et imprimons le nombre d'entités dans la couche.
## Conclusion
Toutes nos félicitations! Vous avez créé avec succès une géodatabase fichier avec une seule couche à l'aide d'Aspose.GIS pour .NET. Explorez facilement les vastes capacités de gestion des données spatiales dans vos applications.
## Questions fréquemment posées
### Puis-je utiliser Aspose.GIS pour .NET dans mes projets .NET existants ?
Oui, Aspose.GIS pour .NET peut être intégré de manière transparente à vos projets .NET existants.
### Existe-t-il une version d'essai disponible pour Aspose.GIS pour .NET ?
 Oui, vous pouvez explorer les fonctionnalités d'Aspose.GIS pour .NET en téléchargeant le[version d'essai gratuite](https://releases.aspose.com/).
### Où puis-je trouver une documentation détaillée pour Aspose.GIS pour .NET ?
 Se référer au[Documentation](https://reference.aspose.com/gis/net/) pour des informations complètes sur Aspose.GIS pour .NET.
### Comment puis-je obtenir de l'assistance pour Aspose.GIS pour .NET ?
 Visiter le[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pour le soutien et l’assistance de la communauté.
### Des licences temporaires sont-elles disponibles pour Aspose.GIS pour .NET ?
 Oui, vous pouvez obtenir un[permis temporaire](https://purchase.aspose.com/temporary-license/) pour Aspose.GIS pour .NET.