---
date: 2025-12-20
description: Apprenez à créer une couche vectorielle et à limiter la précision lors
  de la lecture des géométries avec Aspose.GIS pour .NET. Guide étape par étape pour
  une gestion optimale des données géospatiales.
linktitle: Limit Precision Reading Geometries
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
Lorsque vous travaillez avec des données géospatiales, vous devez souvent **créer des objets de couche vectorielle** et contrôler la quantité de détail numérique conservée lors de leur lecture. Aspose.GIS pour .NET rend simple la limitation de la précision, ce qui peut améliorer les performances et réduire la taille du stockage lorsqu'une précision ultra‑élevée n'est pas requise. Dans ce tutoriel, vous verrez exactement comment créer une couche vectorielle, écrire une géométrie point simple, puis la lire avec une précision exacte et tronquée.

## Quick Answers
- **Que signifie « limiter la précision » ?** Elle arrondit les valeurs de coordonnées à un nombre défini de décimales.  
- **Pourquoi créer d'abord une couche vectorielle ?** Une couche vectorielle est le conteneur qui stocke les géométries telles que les points, les lignes et les polygones.  
- **Quels modèles de précision sont disponibles ?** `PrecisionModel.Exact` (pas d'arrondi) et `PrecisionModel.Rounding(n)` (arrondir à *n* décimales).  
- **Ai-je besoin d'une licence pour essayer cela ?** Un essai gratuit est disponible depuis la page des releases.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core et .NET 5/6+.

## Prerequisites
Avant de commencer ce voyage, assurez‑vous que vous avez les prérequis suivants en place :

1. **Installation** – La bibliothèque Aspose.GIS pour .NET doit être installée dans votre environnement de développement. Sinon, vous pouvez la télécharger depuis la [page des releases](https://releases.aspose.com/gis/net/).
2. **Familiarité avec .NET** – Des connaissances de base en C# et le framework .NET sont nécessaires pour comprendre et implémenter les exemples de code fournis.
3. **Environnement de développement** – Un environnement de développement .NET fonctionnel, tel que Visual Studio, est requis.
4. **Répertoire de documents** – Disposez d'un répertoire configuré où vous pouvez stocker et accéder au shapefile généré pendant le processus.

## Import Namespaces
Avant de commencer à implémenter la fonctionnalité de limitation de la précision lors de la lecture des géométries, assurons‑nous d'importer les espaces de noms nécessaires :
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

## How to Create Vector Layer
Le premier pas est de **créer une couche vectorielle** qui contiendra notre géométrie. Cette couche sera enregistrée sous forme de Shapefile afin que nous puissions la rouvrir plus tard avec différents paramètres de précision.
```csharp
string path = "Your Document Directory" + "LimitPrecisionWhenReadingGeometries_out.shp";
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
	var feature = layer.ConstructFeature();
	feature.Geometry = new Point(1.10234, 2.09743);
	layer.Add(feature);
}
```

## Setting Precision Options
Ensuite, nous devons définir les options de lecture des géométries, en spécifiant le modèle de précision souhaité. Nous pouvons commencer avec une précision exacte :
```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## Reading Geometries with Exact Precision
Maintenant, ouvrons la couche vectorielle avec les options spécifiées pour lire les géométries avec une précision exacte :
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Truncating Precision
Si nous voulons tronquer la précision à un nombre spécifique de décimales, nous pouvons ajuster le modèle de précision en conséquence :
```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Common Issues and Solutions
- **Valeurs de coordonnées inattendues** – Assurez‑vous de définir `options.XYPrecisionModel` *avant* d'ouvrir la couche. Le modifier après l'ouverture n'a aucun effet.
- **Fichier non trouvé** – Vérifiez que la variable `path` pointe vers un répertoire valide et que le Shapefile a été créé avec succès à l'étape précédente.
- **Type de géométrie incorrect** – L'exemple utilise un `Point`. Pour d'autres types de géométrie (par ex., `LineString`), le cast doit correspondre au type réel.

## Conclusion
En conclusion, gérer la précision lors de la lecture des géométries est un aspect crucial de la manipulation des données géospatiales. Aspose.GIS pour .NET offre des fonctionnalités robustes pour y parvenir efficacement. En suivant les étapes décrites dans ce tutoriel, vous pouvez créer sans effort des objets **de couche vectorielle** et limiter la précision selon vos besoins, assurant ainsi une manipulation optimale des données dans vos applications.

## FAQ's
### Can I use Aspose.GIS for .NET with other .NET frameworks like .NET Core or .NET Standard?
Oui, Aspose.GIS pour .NET est compatible avec divers frameworks .NET, y compris .NET Core et .NET Standard.  
### Is there a trial version available for Aspose.GIS for .NET?
Oui, vous pouvez obtenir une version d'essai gratuite depuis la [page des releases](https://releases.aspose.com/).  
### Where can I find comprehensive documentation for Aspose.GIS for .NET?
Vous pouvez consulter la [documentation](https://reference.aspose.com/gis/net/) pour des informations détaillées et des exemples.  
### How can I obtain temporary licenses for Aspose.GIS for .NET?
Des licences temporaires peuvent être obtenues depuis la [page d'achat](https://purchase.aspose.com/temporary-license/) pour Aspose.GIS.  
### Where can I seek assistance or support for Aspose.GIS for .NET?
Vous pouvez visiter le [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pour toute question, discussion ou besoin d'assistance.

## Frequently Asked Questions
**Q : La limitation de la précision affecte‑t‑elle le shapefile original ?**  
R : Non. La précision n'est appliquée que lors de la lecture de la géométrie ; le fichier source reste inchangé.  

**Q : Puis‑je utiliser un modèle de précision différent pour les coordonnées X et Y ?**  
R : Aspose.GIS applique actuellement le même `XYPrecisionModel` aux deux axes.  

**Q : Est‑il possible de définir une fonction d'arrondi personnalisée ?**  
R : L'API ne prend en charge que la méthode intégrée `PrecisionModel.Rounding(int)`. Pour une logique personnalisée, vous devrez post‑traiter les coordonnées après la lecture.

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}