---
date: 2026-05-31
description: Apprenez comment créer du GeoJSON, configurer les options GeoJSON et
  ajouter une entité à une couche en utilisant Aspose.GIS pour .NET. Suivez ce guide
  étape par étape.
keywords:
- how to create geojson
- add feature to layer
- configure geojson options
linktitle: Définir Linearization Tolerance
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  headline: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  name: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  steps:
  - name: Configure GeoJSON Options (how to set tolerance)
    text: '`GeoJsonOptions` specifies the serialization settings used when writing
      GeoJSON files. `GeoJsonOptions` defines how Aspose.GIS serializes GeoJSON, including
      linearization tolerance, coordinate precision, and other output settings. We’ll
      create a `GeoJsonOptions` object and tell Aspose.GIS how close '
  - name: Define the Output Path (how to export GeoJSON)
    text: Specify the full file path where the resulting GeoJSON will be saved. Ensure
      the folder exists and the application has write permissions.
  - name: '**Create Vector Layer** with the configured options'
    text: The `VectorLayer` class represents a GIS container that can read and write
      spatial data. `Drivers.GeoJson` is the driver identifier for writing GeoJSON
      format files. Using `VectorLayer.Create` together with the `Drivers.GeoJson`
      driver and the previously configured `GeoJsonOptions` creates a new Geo
  - name: Construct a Geometry (e.g., a circular string)
    text: '`CircularString` is a curved line geometry that Aspose.GIS can linearize
      based on the tolerance you set. You can replace this with any valid WKT representation
      such as `POINT`, `LINESTRING`, or `POLYGON`.'
  - name: '**Add Feature to Layer** and save'
    text: '`Feature` is the object that couples a geometry with attribute data. After
      creating a `Feature` instance, assign the geometry, optionally add attribute
      values, and call `layer.Add(feature)` to persist it. When the `using` block
      ends, the layer is automatically written to the file defined in `path`. '
  type: HowTo
- questions:
  - answer: Yes, it works with .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6/7.
    question: Is Aspose.GIS for .NET compatible with other .NET frameworks?
  - answer: Absolutely. A commercial license removes all evaluation restrictions and
      provides full technical support.
    question: Can I use Aspose.GIS in commercial projects?
  - answer: Yes, it supports over 30 formats—including Shapefile, KML, GML, and CSV—allowing
      seamless conversion between them.
    question: Does Aspose.GIS support other GIS formats besides GeoJSON?
  - answer: You can download a free 30‑day trial from the Aspose website; it includes
      all features.
    question: Is there a trial version available?
  - answer: Use the Aspose forums, the dedicated support portal, or the “Contact Support”
      link in the product dashboard.
    question: Where can I get support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Comment créer du GeoJSON avec Tolerance Aspose.GIS pour .NET
url: /fr/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer du GeoJSON avec tolérance Aspose.GIS pour .NET

## Introduction
Si vous souhaitez **apprendre à créer des fichiers GeoJSON**, contrôler la précision des courbes et exporter le résultat sous forme de document prêt à l’emploi, Aspose.GIS pour .NET rend cela simple. Dans ce tutoriel, vous découvrirez comment configurer les options GeoJSON, définir la tolérance de linéarisation et **add feature to layer** tout en conservant un code propre et prêt pour la production.

## Réponses rapides
- **Que signifie « create vector layer » ?** Elle crée un nouveau jeu de données vectorielles GIS (par ex., un fichier GeoJSON) qui peut stocker des géométries et des attributs.  
- **Comment définir la tolérance de linéarisation ?** Définissez la propriété `LinearizationTolerance` sur une instance de `GeoJsonOptions` avant de créer la couche.  
- **Puis-je exporter directement un fichier GeoJSON ?** Oui—utilisez `VectorLayer.Create` avec le pilote `Drivers.GeoJson` et les options configurées.  
- **Ai‑je besoin d’une licence ?** Une licence Aspose.GIS valide débloque toutes les fonctionnalités ; une clé d’évaluation temporaire fonctionne pour les tests.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Qu’est‑ce que « create vector layer » ?
Créer une couche vectorielle signifie initialiser un nouveau conteneur GIS (tel qu’un fichier GeoJSON) capable de contenir des points, des lignes, des polygones et les données d’attributs associées. Cette couche devient la cible de toute géométrie que vous créez et de tous les attributs que vous ajoutez.

## Pourquoi configurer les options GeoJSON ?
Configurer les options GeoJSON—en particulier la **tolérance de linéarisation**—garante que les géométries courbes (par ex., `CircularString`) sont approximées avec une précision répondant aux exigences de précision de votre application. Une configuration adéquate réduit la taille du fichier tout en préservant la fidélité visuelle, ce qui est essentiel lorsque le GeoJSON est utilisé par des cartes web ou des outils d’analyse spatiale.

## Prérequis
1. **Visual Studio** (toute version récente).  
2. **Licence Aspose.GIS** (ou une clé d’évaluation temporaire).  
3. **Bibliothèque Aspose.GIS pour .NET** référencée dans votre projet.  
4. Familiarité de base avec **C#**.

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
`GeoJsonOptions` spécifie les paramètres de sérialisation utilisés lors de l’écriture de fichiers GeoJSON.  
`GeoJsonOptions` définit la façon dont Aspose.GIS sérialise le GeoJSON, y compris la tolérance de linéarisation, la précision des coordonnées et d’autres paramètres de sortie.  
Nous créerons un objet `GeoJsonOptions` et indiquerons à Aspose.GIS à quel point la géométrie linéarisée doit être proche de la courbe originale.

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### Étape 2 : Définir le chemin de sortie (comment exporter le GeoJSON)
Spécifiez le chemin complet du fichier où le GeoJSON résultant sera enregistré. Assurez‑vous que le dossier existe et que l’application dispose des permissions d’écriture.

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### Étape 3 : **Create Vector Layer** avec les options configurées
La classe `VectorLayer` représente un conteneur GIS capable de lire et d’écrire des données spatiales.  
`Drivers.GeoJson` est l’identifiant du pilote pour écrire des fichiers au format GeoJSON.  
Utiliser `VectorLayer.Create` avec le pilote `Drivers.GeoJson` et les `GeoJsonOptions` préalablement configurés crée un nouveau fichier GeoJSON prêt à l’insertion de fonctionnalités.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### Étape 4 : Construire une géométrie (par ex., une chaîne circulaire)
`CircularString` est une géométrie de ligne courbe qu’Aspose.GIS peut linéariser en fonction de la tolérance que vous définissez. Vous pouvez remplacer cela par toute représentation WKT valide telle que `POINT`, `LINESTRING` ou `POLYGON`.

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### Étape 5 : **Add Feature to Layer** et enregistrer
`Feature` est l’objet qui associe une géométrie à des données d’attributs. Après avoir créé une instance de `Feature`, assignez la géométrie, ajoutez éventuellement des valeurs d’attributs, puis appelez `layer.Add(feature)` pour la persister. Lorsque le bloc `using` se termine, la couche est automatiquement écrite dans le fichier défini par `path`.

Lorsque le bloc `using` se termine, la couche est automatiquement écrite dans le fichier défini par `path`, vous fournissant un fichier GeoJSON prêt à l’emploi.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

## Problèmes courants et astuces
- **Chemin incorrect** – Vérifiez que le répertoire existe et que vous avez les permissions d’écriture.  
- **Tolérance trop basse** – Définir `LinearizationTolerance` à une valeur très petite peut augmenter considérablement la taille du fichier ; une tolérance de 0,001 équilibre généralement précision et taille.  
- **Erreurs de licence** – Si vous voyez des avertissements de licence, assurez‑vous que le fichier de licence est chargé avant tout appel à Aspose.GIS.  
- **Note de performance** – Aspose.GIS prend en charge le traitement de fichiers jusqu’à 2 Go sans charger le document complet en mémoire, grâce à son architecture de streaming.

## Questions fréquemment posées

**Q : Aspose.GIS pour .NET est‑il compatible avec d’autres frameworks .NET ?**  
R : Oui, il fonctionne avec .NET Framework 4.5+, .NET Core 3.1+ et .NET 5/6/7.

**Q : Puis‑je utiliser Aspose.GIS dans des projets commerciaux ?**  
R : Absolument. Une licence commerciale supprime toutes les restrictions d’évaluation et fournit un support technique complet.

**Q : Aspose.GIS prend‑il en charge d’autres formats GIS en plus du GeoJSON ?**  
R : Oui, il prend en charge plus de 30 formats—y compris Shapefile, KML, GML et CSV—permettant une conversion fluide entre eux.

**Q : Existe‑t‑il une version d’essai disponible ?**  
R : Vous pouvez télécharger un essai gratuit de 30 jours depuis le site Aspose ; il comprend toutes les fonctionnalités.

**Q : Où puis‑je obtenir du support ?**  
R : Utilisez les forums Aspose, le portail de support dédié, ou le lien « Contact Support » dans le tableau de bord du produit.

## Conclusion
En suivant ces étapes, vous savez maintenant **comment créer du GeoJSON**, configurer la tolérance de linéarisation et **add feature to layer** pour une exportation fluide du GeoJSON. Explorez d’autres types de géométrie, la gestion des attributs et les scénarios de traitement en masse pour exploiter pleinement Aspose.GIS dans vos projets GIS .NET.

---

**Last Updated:** 2026-05-31  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [How to Convert GeoJSON – Aspose.GIS for .NET](/gis/net/geo-data-conversion/)
- [Create Vector Layer, Limit Precision with Aspose.GIS for .NET](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}