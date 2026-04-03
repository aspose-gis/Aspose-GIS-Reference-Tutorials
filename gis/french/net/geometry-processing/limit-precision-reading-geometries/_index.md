---
date: 2026-04-03
description: Apprenez à créer une couche vectorielle et à limiter la précision lors
  de la lecture des géométries avec Aspose.GIS pour .NET. Guide étape par étape pour
  une gestion optimale des données géospatiales.
keywords:
- create vector layer
- reduce shapefile size
- set precision model
linktitle: Limiter la précision de lecture des géométries
second_title: Aspose.GIS .NET API
title: Créer une couche vectorielle, limiter la précision avec Aspose.GIS pour .NET
url: /fr/net/geometry-processing/limit-precision-reading-geometries/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une couche vectorielle, limiter la précision avec Aspose.GIS pour .NET

## Introduction
Lorsque vous travaillez avec des données géospatiales, vous devez souvent **create vector layer** objets et décider combien de décimales de détail des coordonnées vous avez réellement besoin. Limiter la précision accélère non seulement le traitement mais peut également **reduce shapefile size**, rendant le stockage et le transfert plus efficaces. Dans ce tutoriel, nous allons parcourir la création d’une couche vectorielle, l’écriture d’une géométrie point simple, puis la lecture de celle‑ci en utilisant à la fois des modèles de précision exacts et arrondis. À la fin, vous comprendrez comment **set precision model** les options qui correspondent aux exigences de précision de votre application.

## Réponses rapides
- **What does “limit precision” mean?** Qu’est‑ce que « limit precision » signifie ? Il arrondit les valeurs de coordonnées à un nombre défini de décimales.  
- **Why create a vector layer first?** Pourquoi créer d’abord une couche vectorielle ? Une couche vectorielle est le conteneur qui stocke les géométries telles que les points, les lignes et les polygones.  
- **Which precision models are available?** Quels modèles de précision sont disponibles ? `PrecisionModel.Exact` (pas d’arrondi) et `PrecisionModel.Rounding(n)` (arrondir à *n* décimales).  
- **Do I need a license to try this?** Ai‑je besoin d’une licence pour essayer cela ? Une version d’essai gratuite est disponible sur la page des releases.  
- **Which .NET versions are supported?** Quelles versions de .NET sont prises en charge ? .NET Framework 4.5+, .NET Core, et .NET 5/6+.

## Pourquoi limiter la précision et comment cela aide‑t‑il ?
- **Performance boost** – Moins de chiffres signifie moins de données à analyser et à sérialiser.  
- **Smaller files** – L’arrondi des coordonnées peut réduire sensiblement la taille d’un shapefile, surtout pour les grands ensembles de données.  
- **Sufficient accuracy** – De nombreuses analyses SIG n’exigent pas une précision sub‑millimétrique, donc arrondir à 2‑3 décimales suffit souvent.

## Prérequis
Avant de commencer ce parcours, assurez‑vous que vous avez les prérequis suivants en place :
1. **Installation** – La bibliothèque Aspose.GIS for .NET doit être installée dans votre environnement de développement. Sinon, vous pouvez la télécharger depuis la [releases page](https://releases.aspose.com/gis/net/).
2. **Familiarity with .NET** – Familiarité avec .NET – Des connaissances de base en C# et le framework .NET sont nécessaires pour comprendre et mettre en œuvre les exemples de code fournis.
3. **Development Environment** – Environnement de développement – Un environnement de développement .NET fonctionnel, tel que Visual Studio, est requis.
4. **Document Directory** – Répertoire de documents – Disposez d’un répertoire configuré où vous pouvez stocker et accéder au shapefile généré pendant le processus.

## Importer les espaces de noms
Avant de commencer à implémenter la fonctionnalité de limitation de précision lors de la lecture des géométries, assurons‑nous d’importer les espaces de noms nécessaires :
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Comment créer une couche vectorielle
La première étape consiste à **create vector layer** qui contiendra notre géométrie. Cette couche sera enregistrée sous forme de Shapefile afin que nous puissions la rouvrir plus tard avec différents paramètres de précision.
```csharp
string path = "Your Document Directory" + "LimitPrecisionWhenReadingGeometries_out.shp";
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
	var feature = layer.ConstructFeature();
	feature.Geometry = new Point(1.10234, 2.09743);
	layer.Add(feature);
}
```

## Définir les options de précision
Ensuite, nous devons définir les options de lecture des géométries, en spécifiant le modèle de précision souhaité. Nous pouvons commencer avec une précision exacte :
```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## Lire les géométries avec une précision exacte
Maintenant, ouvrons la couche vectorielle avec les options spécifiées pour lire les géométries avec une précision exacte :
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Tronquer la précision
Si nous voulons tronquer la précision à un nombre spécifique de décimales, nous pouvons ajuster le modèle de précision en conséquence :
```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Comment définir le modèle de précision pour différents scénarios
Vous vous demandez peut‑être quand utiliser `Exact` versus `Rounding`. Voici deux scénarios courants :

| Scénario | Modèle recommandé | Raison |
|----------|-------------------|--------|
| Analyse scientifique haute précision | `PrecisionModel.Exact` | Aucun perte de détail des coordonnées |
| Tuiles de cartographie web ou applications mobiles | `PrecisionModel.Rounding(2)` | Réduit la taille du fichier et accélère le rendu |

Choisir le bon modèle fait partie du processus de prise de décision **set precision model** qui équilibre précision et performance.

## Problèmes courants et solutions
- **Unexpected coordinate values** – Valeurs de coordonnées inattendues – Assurez‑vous de définir `options.XYPrecisionModel` *avant* d’ouvrir la couche. Le modifier après l’ouverture n’a aucun effet.  
- **File not found** – Fichier non trouvé – Vérifiez que la variable `path` pointe vers un répertoire valide et que le Shapefile a été créé avec succès à l’étape précédente.  
- **Incorrect geometry type** – Type de géométrie incorrect – L’exemple utilise un `Point`. Pour d’autres types de géométrie (par ex., `LineString`), le cast doit correspondre au type réel.  

## Conseils pour réduire la taille du Shapefile
- Utilisez `PrecisionModel.Rounding` avec le plus petit nombre de décimales qui répond toujours à vos besoins de précision.  
- Supprimez les champs d’attributs inutiles avant d’écrire la couche.  
- Compressez les fichiers `.shp`, `.shx` et `.dbf` résultants à l’aide d’utilitaires ZIP standards si vous devez les transférer.

## Conclusion
En conclusion, gérer la précision lors de la lecture des géométries est un aspect crucial de la manipulation des données géospatiales. Aspose.GIS for .NET offre des fonctionnalités robustes pour y parvenir efficacement. En suivant les étapes ci‑dessus, vous pouvez créer sans effort des objets **create vector layer**, **set precision model**, et même **reduce shapefile size** lorsque cela est approprié, assurant une gestion optimale des données dans vos applications.

## FAQ
### Puis‑je utiliser Aspose.GIS for .NET avec d’autres frameworks .NET comme .NET Core ou .NET Standard ?
Oui, Aspose.GIS for .NET est compatible avec divers frameworks .NET, y compris .NET Core et .NET Standard.  
### Existe‑t‑il une version d’essai disponible pour Aspose.GIS for .NET ?
Oui, vous pouvez obtenir une version d’essai gratuite depuis la [releases page](https://releases.aspose.com/).  
### Où puis‑je trouver une documentation complète pour Aspose.GIS for .NET ?
Vous pouvez consulter la [documentation](https://reference.aspose.com/gis/net/) pour des informations détaillées et des exemples.  
### Comment puis‑je obtenir des licences temporaires pour Aspose.GIS for .NET ?
Des licences temporaires peuvent être obtenues depuis la [purchase page](https://purchase.aspose.com/temporary-license/) pour Aspose.GIS.  
### Où puis‑je obtenir de l’aide ou du support pour Aspose.GIS for .NET ?
Vous pouvez visiter le [forum](https://forum.aspose.com/c/gis/33) Aspose.GIS pour toute question, discussion ou besoin de support.

## Questions fréquemment posées
**Q : Limiter la précision affecte‑t‑il le shapefile original ?**  
R : Non. La précision n’est appliquée que lors de la lecture de la géométrie ; le fichier source reste inchangé.  

**Q : Puis‑je utiliser un modèle de précision différent pour les coordonnées X et Y ?**  
R : Aspose.GIS applique actuellement le même `XYPrecisionModel` aux deux axes.  

**Q : Est‑il possible de définir une fonction d’arrondi personnalisée ?**  
R : L’API ne prend en charge que la méthode intégrée `PrecisionModel.Rounding(int)`. Pour une logique personnalisée, vous devrez post‑traiter les coordonnées après lecture.

---

**Dernière mise à jour :** 2026-04-03  
**Testé avec :** Aspose.GIS 24.11 for .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}