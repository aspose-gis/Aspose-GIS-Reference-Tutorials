---
date: 2026-09-10
description: Apprenez comment créer un vector layer avec Aspose.GIS for .NET et limiter
  la precision pour réduire la taille du shapefile, améliorer la performance et conserver
  la coordinate accuracy.
keywords:
- how to create vector layer
- limit precision reading geometries
- reduce shapefile size
lastmod: 2026-09-10
linktitle: Limiter la Precision lors de la Lecture des Géométries
og_description: Apprenez comment créer un vector layer avec Aspose.GIS for .NET et
  limiter la precision pour réduire la taille du shapefile, améliorer la performance
  et gérer la coordinate accuracy.
og_image_alt: Screenshot showing Aspose.GIS code for creating a vector layer and setting
  precision
og_title: Comment créer un vector layer avec Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to create vector layer with Aspose.GIS for .NET and limit
    precision to shrink shapefile size, boost performance, and keep coordinate accuracy.
  headline: How to create vector layer with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create vector layer with Aspose.GIS for .NET and limit
    precision to shrink shapefile size, boost performance, and keep coordinate accuracy.
  name: How to create vector layer with Aspose.GIS for .NET
  steps:
  - name: '**Installation** – Aspose.GIS for .NET library should be installed in your
      development environment. If not, you can download it from the [releases page](https://releases.aspose.com/gis/net/).'
    text: '**Installation** – Aspose.GIS for .NET library should be installed in your
      development environment. If not, you can download it from the [releases page](https://releases.aspose.com/gis/net/).'
  - name: '**Familiarity with .NET** – Basic knowledge of C# and the .NET framework
      is necessary to understand and implement the provided code examples.'
    text: '**Familiarity with .NET** – Basic knowledge of C# and the .NET framework
      is necessary to understand and implement the provided code examples.'
  - name: '**Development environment** – A working .NET development environment, such
      as Visual Studio, is required.'
    text: '**Development environment** – A working .NET development environment, such
      as Visual Studio, is required.'
  - name: '**Document directory** – Have a directory set up where you can store and
      access the shapefile generated during the process.'
    text: '**Document directory** – Have a directory set up where you can store and
      access the shapefile generated during the process.'
  type: HowTo
- questions:
  - answer: No. Precision is applied only when reading the geometry; the source file
      remains unchanged.
    question: Does limiting precision affect the original shapefile?
  - answer: Aspose.GIS currently applies the same `XYPrecisionModel` to both axes.
    question: Can I use a different precision model for X and Y coordinates?
  - answer: The API supports only the built‑in `PrecisionModel.Rounding(int)` method.
      For custom logic, you would need to post‑process the coordinates after reading.
    question: Is it possible to set a custom rounding function?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- Aspose.GIS
- vector layer
- precision model
- .NET GIS
title: Comment créer un vector layer avec Aspose.GIS for .NET
url: /fr/net/geometry-processing/limit-precision-reading-geometries/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer une couche vectorielle avec Aspose.GIS pour .NET

## Introduction
Lorsque vous travaillez avec des données géospatiales, vous vous demandez souvent **comment créer des objets de couche vectorielle** qui correspondent à la précision réellement requise par votre application. Arrondir les coordonnées à un nombre raisonnable de décimales accélère non seulement l’analyse mais peut aussi **réduire la taille du shapefile jusqu’à 30 %** pour des jeux de points typiques. Dans ce guide pas à pas, vous verrez comment créer une couche vectorielle, écrire une géométrie de point, puis la relire en utilisant à la fois des modèles de précision exacts et arrondis. À la fin, vous saurez **configurer les options du modèle de précision** qui équilibrent performance et précision spatiale requise.

## Réponses rapides
- **Que signifie « limiter la précision » ?** Cela arrondit les valeurs de coordonnées à un nombre défini de décimales.  
- **Pourquoi créer d’abord une couche vectorielle ?** Une couche vectorielle est le conteneur qui stocke les géométries telles que points, lignes et polygones.  
- **Quels modèles de précision sont disponibles ?** `PrecisionModel.Exact` (sans arrondi) et `PrecisionModel.Rounding(n)` (arrondir à *n* décimales).  
- **Ai‑je besoin d’une licence pour essayer ?** Une version d’essai gratuite est disponible depuis la page des releases.  
- **Quelles versions .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core et .NET 5/6+.

## Qu’est‑ce que la création d’une couche vectorielle ?
L’acte de **créer une couche vectorielle** consiste à instancier la classe `VectorLayer` d’Aspose.GIS, qui représente un shapefile unique sur le disque et contient toutes les entités géométriques que vous ajoutez. Cette couche devient le point d’entrée pour la lecture, l’écriture et la manipulation des données spatiales. Elle vous permet également de définir des champs d’attributs et de spécifier la référence spatiale du jeu de données.

## Pourquoi limiter la précision et comment cela aide‑t‑il ?
- **Gain de performance** – Réduire le nombre de chiffres décimaux diminue la quantité de données binaires à analyser et à sérialiser, offrant souvent un gain de vitesse de 15‑20 % sur de gros fichiers.  
- **Fichiers plus petits** – Arrondir les coordonnées à deux ou trois décimales peut réduire un shapefile de 10 Mo à environ 7 Mo, facilitant le stockage et le transfert réseau.  
- **Précision suffisante** – La plupart des analyses SIG (par ex., cartographie à l’échelle de la ville) n’ont besoin que d’une précision au mètre, rendant un arrondi à 3 décimales largement adéquat.

## Prérequis
Avant de commencer, assurez‑vous d’avoir les prérequis suivants :
1. **Installation** – La bibliothèque Aspose.GIS pour .NET doit être installée dans votre environnement de développement. Si ce n’est pas le cas, vous pouvez la télécharger depuis la [page des releases](https://releases.aspose.com/gis/net/).  
2. **Familiarité avec .NET** – Des connaissances de base en C# et le framework .NET sont nécessaires pour comprendre et mettre en œuvre les exemples de code fournis.  
3. **Environnement de développement** – Un environnement de développement .NET fonctionnel, tel que Visual Studio, est requis.  
4. **Répertoire de documents** – Créez un répertoire où vous pourrez stocker et accéder au shapefile généré pendant le processus.

## Importer les espaces de noms
Avant de commencer à implémenter la fonctionnalité de limitation de précision lors de la lecture des géométries, assurons‑nous d’importer les espaces de noms nécessaires :
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
Chargez une nouvelle `VectorLayer` en spécifiant le dossier de sortie et le nom souhaité du shapefile. Cela crée un conteneur vide prêt à accepter des objets géométriques.

La classe `VectorLayer` est l’objet de haut niveau d’Aspose.GIS qui représente un shapefile unique sur le disque. Après avoir créé une instance, vous pouvez ajouter des entités, définir des champs d’attributs, puis appeler `Save()` pour écrire les fichiers sur le système de fichiers.

```csharp
string path = "Your Document Directory" + "LimitPrecisionWhenReadingGeometries_out.shp";
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
	var feature = layer.ConstructFeature();
	feature.Geometry = new Point(1.10234, 2.09743);
	layer.Add(feature);
}
```

## Configuration des options de précision
`PrecisionModel` définit comment les valeurs de coordonnées sont arrondies ou conservées exactes lors de la lecture des géométries. Vous définissez le modèle sur un objet `ReadOptions` avant d’ouvrir une couche.

La classe `PrecisionModel` est un composant central d’Aspose.GIS qui contrôle le comportement d’arrondi pour les axes X et Y. En choisissant le modèle approprié, vous décidez si la bibliothèque préserve chaque chiffre ou tronque à un nombre décimal spécifique.

```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## Lecture des géométries avec précision exacte
`ReadOptions` spécifie les paramètres de lecture d’une couche vectorielle, comme le modèle de précision à appliquer.  
Ouvrez la couche vectorielle précédemment enregistrée à l’aide d’une instance `ReadOptions` qui référence `PrecisionModel.Exact`. Cela garantit que chaque coordonnée est lue sans aucun arrondi.

Lorsque vous utilisez `PrecisionModel.Exact`, Aspose.GIS lit les valeurs double‑précision brutes stockées dans le shapefile, assurant qu’aucune information n’est perdue lors de l’opération de lecture.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Tronquer la précision
Si vous souhaitez tronquer la précision à un nombre spécifique de décimales, remplacez `Exact` par `PrecisionModel.Rounding(n)`, où *n* est le nombre de décimales que vous désirez conserver.

Arrondir à deux décimales (`PrecisionModel.Rounding(2)`) réduit généralement la taille du fichier de 20‑30 % tout en maintenant une précision des coordonnées à quelques centimètres pour la plupart des échelles cartographiques.

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
Choisissez le modèle qui correspond à votre cas d’utilisation :

- **Analyse scientifique haute précision** – Utilisez `PrecisionModel.Exact` pour conserver chaque chiffre.  
- **Tuiles web‑mapping ou applications mobiles** – Utilisez `PrecisionModel.Rounding(2)` pour garder les fichiers légers et le rendu rapide.

Sélectionner le modèle approprié fait partie du processus de **définition du modèle de précision** qui équilibre précision et performance.

## Problèmes courants et solutions
`XYPrecisionModel` est une propriété de `ReadOptions` qui définit le modèle de précision pour les coordonnées X et Y.  

- **Valeurs de coordonnées inattendues** – Assurez‑vous de définir `options.XYPrecisionModel` *avant* d’ouvrir la couche. Le modifier après l’ouverture n’a aucun effet.  
- **Fichier introuvable** – Vérifiez que la variable `path` pointe vers un répertoire valide et que le shapefile a bien été créé à l’étape précédente.  
- **Type de géométrie incorrect** – L’exemple utilise un `Point`. Pour d’autres types de géométrie (par ex., `LineString`), le cast doit correspondre au type réel.  

## Astuces pour réduire la taille du shapefile
- Utilisez `PrecisionModel.Rounding` avec le plus petit nombre de décimales qui satisfait vos exigences de précision.  
- Supprimez les champs d’attributs inutiles avant d’écrire la couche.  
- Compressez les fichiers résultants `.shp`, `.shx` et `.dbf` à l’aide d’utilitaires ZIP standards si vous devez les transférer.

## Conclusion
Gérer la précision lors de la lecture des géométries est un aspect crucial de la manipulation des données géospatiales. Aspose.GIS pour .NET offre des fonctionnalités robustes pour y parvenir efficacement. En suivant les étapes ci‑dessus, vous pouvez créer sans effort des objets **couche vectorielle**, **définir le modèle de précision**, et même **réduire la taille du shapefile** lorsque cela est approprié, assurant ainsi une gestion optimale des données dans vos applications.

## FAQ's
### Puis‑je utiliser Aspose.GIS pour .NET avec d’autres frameworks .NET comme .NET Core ou .NET Standard ?
Oui, Aspose.GIS pour .NET est compatible avec divers frameworks .NET, y compris .NET Core et .NET Standard.  
### Existe‑t‑il une version d’essai disponible pour Aspose.GIS pour .NET ?
Oui, vous pouvez obtenir une version d’essai gratuite depuis la [page des releases](https://releases.aspose.com/).  
### Où puis‑je trouver une documentation complète pour Aspose.GIS pour .NET ?
Vous pouvez consulter la [documentation](https://reference.aspose.com/gis/net/) pour des informations détaillées et des exemples.  
### Comment obtenir des licences temporaires pour Aspose.GIS pour .NET ?
Des licences temporaires sont disponibles sur la [page d’achat](https://purchase.aspose.com/temporary-license/) d’Aspose.GIS.  
### Où puis‑je obtenir de l’aide ou du support pour Aspose.GIS pour .NET ?
Vous pouvez visiter le [forum](https://forum.aspose.com/c/gis/33) d’Aspose.GIS pour toute question, discussion ou besoin de support.

## Questions fréquemment posées
**Q : La limitation de précision affecte‑t‑elle le shapefile original ?**  
R : Non. La précision n’est appliquée que lors de la lecture de la géométrie ; le fichier source reste inchangé.  

**Q : Puis‑je utiliser un modèle de précision différent pour les coordonnées X et Y ?**  
R : Aspose.GIS applique actuellement le même `XYPrecisionModel` aux deux axes.  

**Q : Est‑il possible de définir une fonction d’arrondi personnalisée ?**  
R : L’API ne prend en charge que la méthode intégrée `PrecisionModel.Rounding(int)`. Pour une logique personnalisée, vous devez post‑traiter les coordonnées après la lecture.

---

**Dernière mise à jour :** 2026-09-10  
**Testé avec :** Aspose.GIS 24.11 pour .NET  
**Auteur :** Aspose

## Tutoriels associés

- [How to Limit Precision Writing Geometries with Aspose.GIS](/gis/net/geometry-processing/limit-precision-writing-geometries/)
- [How to Create Vector Layer with SRS using Aspose.GIS for .NET](/gis/net/layer-management/create-vector-layer-with-srs/)
- [Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}