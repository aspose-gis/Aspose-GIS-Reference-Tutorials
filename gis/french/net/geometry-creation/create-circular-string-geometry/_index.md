---
date: 2025-12-12
description: Apprenez à créer une couche vectorielle et à ajouter une géométrie de
  chaîne circulaire en utilisant Aspose.GIS pour .NET – une façon rapide de créer
  des applications SIG.
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
Si vous développez une application SIG sur la plateforme .NET, la première étape consiste souvent **à créer des objets de couche vectorielle** qui stockent vos entités spatiales. Aspose.GIS pour .NET rend ce processus simple et vous permet d’enrichir ces couches avec des géométries avancées telles que les chaînes circulaires. Dans ce tutoriel, vous apprendrez exactement comment créer une couche vectorielle, ajouter une géométrie de chaîne circulaire et enregistrer le résultat sous forme de Shapefile — le tout avec du code C# propre et prêt pour la production.

## Réponses rapides
- **Que signifie « créer une couche vectorielle » ?** Cela crée un nouveau conteneur (couche) pouvant contenir des entités spatiales comme des points, des lignes ou des polygones.  
- **Quelle classe représente une chaîne circulaire ?** `CircularString` provenant de `Aspose.Gis.Geometries`.  
- **Puis‑je enregistrer la couche au format Shapefile ?** Oui – utilisez `Drivers.Shapefile` lors de la création de la couche.  
- **Ai‑je besoin d’une licence pour le développement ?** Une licence temporaire suffit pour l’évaluation ; une licence complète est requise en production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Qu’est‑ce que « créer une couche vectorielle » ?
Une couche vectorielle est un regroupement logique d’entités vectorielles (points, lignes, polygones) stockées dans une même source de données. Dans Aspose.GIS, vous créez une couche en appelant `VectorLayer.Create`, en indiquant le chemin du fichier cible et le pilote souhaité (par ex., Shapefile). Une fois la couche créée, vous pouvez y ajouter des entités, leur assigner des géométries et effectuer des opérations spatiales.

## Pourquoi ajouter une chaîne circulaire ?
Les chaînes circulaires sont un type de **géométrie linéaire** qui approxime des arcs à l’aide d’une séquence de points. Elles sont utiles pour représenter des routes courbées, des méandres de rivière ou toute entité nécessitant une courbe lisse sans recourir à de nombreux petits segments de ligne.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

- **.NET Framework ou .NET Core** installé sur votre machine.  
- **Aspose.GIS pour .NET** – téléchargez‑le depuis le site officiel **[ici](https://releases.aspose.com/gis/net/)**.  
- Un IDE tel que **Visual Studio** ou **JetBrains Rider**.  
- Une connaissance de base de la programmation **C#**.

## Importer les espaces de noms
Ajoutez les espaces de noms requis à votre fichier C# :

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Guide étape par étape

### Étape 1 : Définir le chemin du fichier de sortie
Indiquez l’emplacement où le Shapefile sera écrit.

```csharp
string path = "Your Document Directory" + "CreateCircularString_out.shp";
```

Remplacez `"Your Document Directory"` par le chemin réel du dossier sur votre système.

### Étape 2 : **Créer une couche vectorielle**
Ouvrez un `VectorLayer` en utilisant la méthode `Create`. C’est le cœur de l’opération **créer une couche vectorielle**.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
```

### Étape 3 : Construire une nouvelle entité
Une entité représente un enregistrement spatial unique au sein de la couche.

```csharp
    var feature = layer.ConstructFeature();
```

### Étape 4 : Construire la géométrie de chaîne circulaire
Ajoutez les points qui définissent la forme courbée. La séquence de points crée un arc qui commence et se termine au même emplacement, formant ainsi une chaîne circulaire fermée.

```csharp
    var circularString = new CircularString();
    circularString.AddPoint(0, 0);
    circularString.AddPoint(1, 1);
    circularString.AddPoint(2, 0);
    circularString.AddPoint(1, -1);
    circularString.AddPoint(0, 0);
```

### Étape 5 : Assigner la géométrie et ajouter l’entité à la couche
Liez la géométrie à l’entité et stockez‑la dans la couche.

```csharp
    feature.Geometry = circularString;
    layer.Add(feature);
}
```

Lorsque le bloc `using` se termine, la couche est automatiquement écrite dans le Shapefile sur le disque.

## Problèmes courants & solutions
| Problème | Solution |
|----------|----------|
| **Chemin de fichier invalide** | Vérifiez que le répertoire existe et que vous disposez des droits d’écriture. |
| **CircularString apparaît comme une ligne droite** | Assurez‑vous que les points sont ajoutés dans le bon ordre ; le premier et le dernier point doivent être identiques pour une forme fermée. |
| **Exception de licence** | Appliquez une licence temporaire pendant le développement ou achetez une licence complète pour la production. |

## Questions fréquentes

### Aspose.GIS pour .NET est‑il compatible avec toutes les versions du .NET Framework ?
Oui, Aspose.GIS pour .NET est conçu pour fonctionner avec un large éventail de versions de .NET, du Framework 4.5 aux dernières versions .NET 8.

### Puis‑je intégrer Aspose.GIS pour .NET avec d’autres bibliothèques SIG ?
Absolument ! Vous pouvez lire des données avec d’autres bibliothèques, les manipuler avec Aspose.GIS, puis les réécrire, grâce à son API flexible.

### Aspose.GIS pour .NET prend‑il en charge la visualisation de données spatiales ?
Oui, la bibliothèque inclut des utilitaires de rendu qui vous permettent de générer des cartes et des représentations visuelles de vos géométries.

### Existe‑t‑il un forum communautaire où je peux obtenir de l’aide sur Aspose.GIS pour .NET ?
Oui, vous pouvez visiter le forum Aspose.GIS **[ici](https://forum.aspose.com/c/gis/33)** pour poser des questions et partager vos expériences.

### Puis‑je obtenir une licence temporaire pour évaluer Aspose.GIS pour .NET ?
Bien sûr ! Une licence d’évaluation temporaire est disponible **[ici](https://purchase.aspose.com/temporary-license/)**.

### Comment ajouter des géométries plus complexes (par ex., MultiLineString) à la même couche ?
Créez l’objet géométrique approprié (par ex., `MultiLineString`), remplissez‑le avec des objets `LineString` individuels, assignez‑le à `feature.Geometry`, puis ajoutez l’entité comme nous l’avons fait avec la chaîne circulaire.

## Conclusion
En suivant ces étapes, vous savez maintenant comment **créer des couches vectorielles** et les enrichir avec une géométrie de chaîne circulaire à l’aide d’Aspose.GIS pour .NET. Cette base vous permet de développer des solutions SIG plus riches—que vous cartographiiez des réseaux de transport, visualisiez des données environnementales ou créiez des outils d’analyse spatiale personnalisés.

---

**Dernière mise à jour :** 2025-12-12  
**Testé avec :** Aspose.GIS 24.11 pour .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}