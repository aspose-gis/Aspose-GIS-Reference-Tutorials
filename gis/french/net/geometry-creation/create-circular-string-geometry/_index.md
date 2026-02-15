---
date: 2026-02-15
description: Apprenez à créer une couche vectorielle et à ajouter une géométrie de
  chaîne circulaire avec Aspose.GIS pour .NET – une façon rapide de développer des
  applications SIG.
linktitle: Create Circular String Geometry
second_title: Aspose.GIS .NET API
title: Créer une couche vectorielle et une chaîne circulaire dans Aspose.GIS pour
  .NET
url: /fr/net/geometry-creation/create-circular-string-geometry/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une couche vectorielle et une géométrie de chaîne circulaire avec Aspose.GIS pour .NET

## Introduction
Si vous développez une application GIS sur la plateforme .NET, la première étape consiste souvent **à créer des objets de couche vectorielle** qui stockent vos entités spatiales. Aspose.GIS pour .NET rend ce processus simple et vous permet d'enrichir ces couches avec des géométries avancées telles que les chaînes circulaires. Dans ce tutoriel, vous apprendrez exactement comment **créer une couche vectorielle**, **ajouter une géométrie de chaîne circulaire**, et enregistrer le résultat sous forme de Shapefile — le tout avec du code C# propre et prêt pour la production.

## Quick Answers
- **Que signifie « créer une couche vectorielle » ?** Cela crée un nouveau conteneur (couche) pouvant contenir des entités spatiales telles que des points, des lignes ou des polygones.  
- **Quelle classe représente une chaîne circulaire ?** `CircularString` de `Aspose.Gis.Geometries`.  
- **Puis-je enregistrer la couche en tant que Shapefile ?** Oui – utilisez `Drivers.Shapefile` lors de la création de la couche.  
- **Ai-je besoin d'une licence pour le développement ?** Une licence temporaire suffit pour l'évaluation ; une licence complète est requise pour la production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## What is “create vector layer”?
Une couche vectorielle est un regroupement logique d'entités vectorielles (points, lignes, polygones) stockées dans une source de données unique. Dans Aspose.GIS, vous créez une couche en appelant `VectorLayer.Create`, en passant le chemin du fichier cible et le driver souhaité (par ex., Shapefile). Une fois la couche créée, vous pouvez ajouter des entités, attribuer des géométries et effectuer des opérations spatiales.

## Why add a circular string?
Les chaînes circulaires sont un type de **géométrie linéaire** qui approxime les arcs à l'aide d'une séquence de points. Elles sont utiles pour représenter des routes courbées, des méandres de rivière ou toute entité nécessitant une courbe lisse sans recourir à de nombreux petits segments de ligne.

## Prerequisites
- **.NET Framework ou .NET Core** installé sur votre machine.  
- Bibliothèque **Aspose.GIS for .NET** – téléchargez‑la depuis le site officiel **[here](https://releases.aspose.com/gis/net/)**.  
- Un IDE tel que **Visual Studio** ou **JetBrains Rider**.  
- Une connaissance de base de la programmation **C#**.

## Import Namespaces
Add the required namespaces to your C# file:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Step‑by‑Step Guide

### Step 1: Define the output file path
Set the location where the Shapefile will be written.

```csharp
string path = "Your Document Directory" + "CreateCircularString_out.shp";
```

Replace `"Your Document Directory"` with the actual folder path on your system.

### Step 2: **Create vector layer**
Open a `VectorLayer` using the `Create` method. This is the core of the **create vector layer** operation.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
```

### Step 3: Construct a new feature
A feature represents a single spatial record inside the layer.

```csharp
    var feature = layer.ConstructFeature();
```

### Step 4: Build the circular string geometry
Add the points that define the curved shape. The sequence of points creates an arc that starts and ends at the same location, forming a closed circular string.

```csharp
    var circularString = new CircularString();
    circularString.AddPoint(0, 0);
    circularString.AddPoint(1, 1);
    circularString.AddPoint(2, 0);
    circularString.AddPoint(1, -1);
    circularString.AddPoint(0, 0);
```

### Step 5: Assign geometry and add the feature to the layer
Link the geometry to the feature and store it in the layer.

```csharp
    feature.Geometry = circularString;
    layer.Add(feature);
}
```

When the `using` block ends, the layer is automatically flushed to the Shapefile on disk.

## Common Issues & Solutions
| Problème | Solution |
|----------|----------|
| **Chemin du fichier invalide** | Assurez‑vous que le répertoire existe et que vous avez les permissions d'écriture. |
| **CircularString apparaît comme une ligne droite** | Vérifiez que les points sont ajoutés dans le bon ordre ; le premier et le dernier point doivent être identiques pour une forme fermée. |
| **Exception de licence** | Appliquez une licence temporaire pendant le développement ou achetez une licence complète pour une utilisation en production. |

## Frequently Asked Questions

### Aspose.GIS pour .NET est‑il compatible avec toutes les versions du .NET Framework ?
Oui, Aspose.GIS pour .NET est conçu pour fonctionner avec une large gamme de versions .NET, du Framework 4.5 jusqu'aux dernières versions .NET 8.

### Puis‑je intégrer Aspose.GIS pour .NET avec d'autres bibliothèques GIS ?
Absolument ! Vous pouvez lire des données avec d'autres bibliothèques, les manipuler avec Aspose.GIS, puis les réécrire, grâce à son API flexible.

### Aspose.GIS pour .NET prend‑il en charge la visualisation de données spatiales ?
Oui, la bibliothèque inclut des utilitaires de rendu qui vous permettent de générer des cartes et des représentations visuelles de vos géométries.

### Existe‑t‑il un forum communautaire où je peux demander de l'aide concernant Aspose.GIS pour .NET ?
Oui, vous pouvez visiter le forum Aspose.GIS **[here](https://forum.aspose.com/c/gis/33)** pour poser des questions et partager vos expériences.

### Puis‑je obtenir une licence temporaire pour évaluer Aspose.GIS pour .NET ?
Bien sûr ! Une licence d'évaluation temporaire est disponible **[here](https://purchase.aspose.com/temporary-license/)**.

### Comment ajouter des géométries plus complexes (par ex., MultiLineString) à la même couche ?
Créez l'objet de géométrie approprié (par ex., `MultiLineString`), remplissez‑le avec des objets `LineString` individuels, assignez‑le à `feature.Geometry`, et ajoutez l'entité de la même manière que nous l'avons fait avec la chaîne circulaire.

## FAQ (Quick‑Reference)

**Q:** How do I **create vector layer** programmatically?  
**A:** Call `VectorLayer.Create(path, Drivers.Shapefile)` (or another driver) inside a `using` block.  
**Q:** What method adds points to a circular string?  
**A:** Use `circularString.AddPoint(x, y)` for each coordinate.  
**Q:** Can I store multiple geometries in the same layer?  
**A:** Yes, construct a new feature for each geometry and add it with `layer.Add(feature)`.  
**Q:** What should I do if the Shapefile is not created?  
**A:** Verify that the output directory exists, you have write permissions, and the driver (`Drivers.Shapefile`) is correctly referenced.  
**Q:** Is a license required for the evaluation build?  
**A:** A temporary license is sufficient for development and testing; a full license is needed for production deployments.

## Conclusion
En suivant ces étapes, vous savez maintenant comment **créer des objets de couche vectorielle** et les enrichir avec une géométrie de **chaîne circulaire** à l'aide d'Aspose.GIS pour .NET. Cette base vous permet de construire des solutions GIS plus riches — que vous cartographiiez des réseaux de transport, visualisiez des données environnementales ou développiez des outils d'analyse spatiale personnalisés.

---

**Dernière mise à jour :** 2026-02-15  
**Testé avec :** Aspose.GIS 24.11 for .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}