---
date: 2025-12-21
description: Apprenez à créer une couche vectorielle, à définir la tolérance de linéarisation
  et à ajouter une entité à la couche en utilisant Aspose.GIS pour .NET. Suivez ce
  guide étape par étape pour exporter des fichiers GeoJSON.
linktitle: Set Linearization Tolerance
second_title: Aspose.GIS .NET API
title: Créer une couche vectorielle et définir la tolérance de linéarisation avec
  Aspose.GIS pour .NET
url: /fr/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une couche vectorielle et définir la tolérance de linéarisation avec Aspose.GIS pour .NET

## Introduction
Si vous devez **créer une couche vectorielle**, contrôler la précision des courbes et exporter le résultat sous forme de document GeoJSON, Aspose.GIS pour .NET rend cela simple. Dans ce tutoriel, vous apprendrez à configurer les options GeoJSON, à définir la tolérance de linéarisation et à **ajouter une entité à la couche** — le tout en conservant un code propre et prêt pour la production.

## Réponses rapides
- **Que signifie « créer une couche vectorielle » ?** Cela crée un nouveau jeu de données GIS vectoriel (par ex., un fichier GeoJSON) capable de stocker des géométries et des attributs.  
- **Comment définir la tolérance ?** Utilisez la propriété `LinearizationTolerance` de `GeoJsonOptions`.  
- **Puis-je exporter un fichier GeoJSON ?** Oui — créez simplement une `VectorLayer` avec le pilote `Drivers.GeoJson`.  
- **Ai‑je besoin d’une licence ?** Une licence Aspose.GIS valide débloque toutes les fonctionnalités ; une licence temporaire suffit pour l’évaluation.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Qu’est‑ce que « créer une couche vectorielle » ?
Créer une couche vectorielle signifie initialiser un nouveau conteneur GIS (tel qu’un fichier GeoJSON) qui peut contenir des entités géométriques comme des points, des lignes et des polygones. Cette couche devient la cible de toutes les géométries que vous construisez et de tous les attributs que vous y associez.

## Pourquoi configurer les options GeoJSON ?
Configurer les options GeoJSON — en particulier la **tolérance de linéarisation** — garantit que les géométries courbes (par ex., `CircularString`) sont approximées avec une précision répondant aux exigences de votre application. Cette étape est cruciale lorsque vous **exportez un fichier GeoJSON** pour une utilisation dans des cartes web ou des analyses spatiales.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

1. **Visual Studio** installé (toute version récente).  
2. **Licence Aspose.GIS** (ou une clé d’évaluation temporaire).  
3. Bibliothèque **Aspose.GIS pour .NET** téléchargée et référencée dans votre projet.  
4. Une connaissance de base du **C#**.

## Importer les espaces de noms
Tout d’abord, importez les espaces de noms requis afin que le compilateur sache où trouver les classes GIS :

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Guide étape par étape

### Étape 1 : Configurer les options GeoJSON (comment définir la tolérance)
Nous allons créer un objet `GeoJsonOptions` et indiquer à Aspose.GIS à quel point la géométrie linéarisée doit être proche de la courbe d’origine.

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### Étape 2 : Définir le chemin de sortie (comment exporter le GeoJSON)
Spécifiez où le fichier résultant sera enregistré. Remplacez le texte de substitution par votre dossier réel.

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### Étape 3 : **Créer une couche vectorielle** avec les options configurées
Nous créons maintenant réellement la **couche vectorielle** à l’aide de la méthode `VectorLayer.Create`. Le bloc `using` garantit la libération correcte des ressources.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### Étape 4 : Construire une géométrie (par ex., une chaîne circulaire)
Ici nous construisons une géométrie d’exemple — un `CircularString`. Vous pouvez le remplacer par n’importe quel WKT valide.

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### Étape 5 : **Ajouter une entité à la couche** et enregistrer
Enfin, nous créons une entité, lui assignons la géométrie, puis l’ajoutons à la couche. C’est le cœur de l’opération **ajouter une entité à la couche**.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

Lorsque le bloc `using` se termine, la couche est automatiquement écrite dans le fichier défini par `path`, vous donnant un fichier GeoJSON prêt à l’emploi.

## Problèmes courants & conseils
- **Chemin incorrect** – Assurez‑vous que le répertoire existe et que vous avez les droits d’écriture.  
- **Tolérance trop faible** – Fixer `LinearizationTolerance` à une valeur très petite peut augmenter considérablement la taille du fichier. Ajustez selon vos besoins de précision.  
- **Erreurs de licence** – Si vous voyez des avertissements de licence, vérifiez que le fichier de licence est correctement chargé avant tout appel Aspose.GIS.

## Questions fréquentes

**Q : Aspose.GIS pour .NET est‑il compatible avec d’autres frameworks .NET ?**  
R : Oui, il fonctionne avec .NET Framework, .NET Core et .NET 5/6/7.

**Q : Puis‑je utiliser Aspose.GIS dans des projets commerciaux ?**  
R : Absolument. Une licence commerciale supprime toutes les restrictions d’évaluation.

**Q : Aspose.GIS prend‑il en charge d’autres formats GIS que le GeoJSON ?**  
R : Oui, il prend en charge Shapefile, KML, GML et bien d’autres.

**Q : Existe‑t‑il une version d’essai ?**  
R : Vous pouvez télécharger une version d’essai gratuite depuis le site Aspose.

**Q : Où obtenir du support ?**  
R : Utilisez les forums Aspose ou le lien de support dans la section ressources.

## Conclusion
En suivant ces étapes, vous savez maintenant comment **créer une couche vectorielle**, configurer la tolérance de linéarisation et **ajouter une entité à la couche** pour une création fluide de **fichier GeoJSON exporté**. Explorez d’autres types de géométries et la gestion des attributs pour exploiter pleinement Aspose.GIS dans vos projets GIS .NET.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2025-12-21  
**Testé avec :** Aspose.GIS 24.11 pour .NET  
**Auteur :** Aspose  

---