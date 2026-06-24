---
date: 2026-05-31
description: Apprenez à créer un polygone avec Aspose.GIS pour .NET. Guide étape par
  étape destiné aux développeurs .NET pour construire une géométrie de polygone et
  exporter le shapefile de polygone.
keywords:
- how to create polygon
- export polygon shapefile
- add vertices polygon
- build polygon coordinates
linktitle: Créer une géométrie de polygone
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to create polygon using Aspose.GIS for .NET. Step‑by‑step
    guide for .NET developers to build polygon geometry and export polygon shapefile.
  headline: How to Create Polygon Geometry with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create polygon using Aspose.GIS for .NET. Step‑by‑step
    guide for .NET developers to build polygon geometry and export polygon shapefile.
  name: How to Create Polygon Geometry with Aspose.GIS for .NET
  steps:
  - name: Create a Polygon Object
    text: The `Polygon` class is the top‑level container that represents a single
      polygon geometry. **The `Polygon` class represents a closed geometric shape
      consisting of an exterior ring and optional interior rings.**
  - name: Define Exterior Ring
    text: A `LinearRing` holds the sequence of points that form the outer boundary.
      **The `LinearRing` class stores an ordered list of coordinate pairs that must
      form a closed loop.**
  - name: Add Points to the Exterior Ring
    text: Now we **add vertices polygon** by feeding latitude‑longitude pairs (or
      any coordinate system you prefer) into the ring. The points must form a closed
      loop, so the first and last coordinates are identical. **`LinearRing.AddPoint(x,
      y)` adds a single vertex to the ring; repeat for each coordinate.**
  - name: Set Exterior Ring on the Polygon
    text: Finally, assign the prepared ring to the polygon’s `ExteriorRing` property.
      The polygon is now a complete, valid geometry object. **The `ExteriorRing` property
      links the constructed `LinearRing` to the `Polygon` instance, finalizing the
      shape.** Congratulations! You have just **created polygon geome
  type: HowTo
- questions:
  - answer: Yes – simply iterate through your coordinate collection and call `ring.AddPoint(x,
      y)` for each item.
    question: Can I create a polygon from an existing list of coordinates?
  - answer: Create another `LinearRing`, add points, and assign it to `polygon.InteriorRings.Add(yourRing);`.
    question: How do I add an interior ring (hole) to the polygon?
  - answer: Use `polygon.IsValid` property; it returns `true` if the geometry complies
      with OGC standards.
    question: Is there a way to validate the polygon after creation?
  - answer: Absolutely. Use `FeatureWriter` with `GeoJson` format to write the polygon
      to a file, or choose `Shapefile` to **export polygon shapefile**.
    question: Can I export the polygon directly to GeoJSON?
  - answer: The library currently focuses on 2‑D geometries; for 3‑D you’ll need to
      manage Z‑values manually or use another specialized library.
    question: Does Aspose.GIS support 3‑D polygons?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Comment créer une géométrie de polygone avec Aspose.GIS pour .NET
url: /fr/net/geometry-creation/create-polygon-geometry/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer une géométrie de polygone avec Aspose.GIS pour .NET

## Introduction  
Si vous recherchez un guide clair et pratique sur **comment créer un polygone** en .NET, vous êtes au bon endroit. Dans ce tutoriel, nous parcourrons l’ensemble du processus en utilisant Aspose.GIS pour .NET – de la configuration du projet à l’ajout de points et à la finalisation du polygone. À la fin, vous comprendrez pourquoi cette bibliothèque est un excellent choix pour travailler avec des structures de données spatiales de type polygone et vous disposerez d’un **exemple de géométrie de polygone** réutilisable pour vos propres applications SIG. Vous verrez également comment **exporter un shapefile de polygone** et d’autres formats courants.

## Réponses rapides
`Polygon` est la classe représentant les géométries de polygone dans Aspose.GIS. `LinearRing.AddPoint` ajoute un sommet à un anneau linéaire.  

- **Quelle est la classe principale pour les polygones ?** `Polygon` de `Aspose.Gis.Geometries`.  
- **Quelle méthode ajoute des sommets ?** `LinearRing.AddPoint(x, y)` – elle ajoute les sommets du polygone un par un.  
- **Ai-je besoin d’une licence pour le développement ?** Un essai gratuit suffit pour les tests ; une licence est requise pour la production.  
- **Versions .NET prises en charge ?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6+.  
- **Puis-je exporter le polygone vers un fichier ?** Oui – utilisez `FeatureWriter` pour écrire Shapefile, GeoJSON, etc., et **exporter le shapefile de polygone** facilement.

## Qu’est‑ce qu’une géométrie de polygone ?
Un polygone est une forme fermée composée d’un anneau extérieur (la frontière extérieure) et éventuellement d’un ou plusieurs anneaux intérieurs (trous). En SIG, les polygones modélisent des zones du monde réel telles que des lacs, des parcelles ou des limites administratives. Aspose.GIS fournit un modèle d’objet clair qui vous permet de **construire les coordonnées du polygone** en quelques lignes de C#.

## Pourquoi utiliser Aspose.GIS pour créer une géométrie de polygone ?
Aspose.GIS vous permet de créer rapidement des géométries de polygone tout en offrant des performances de niveau entreprise. Il prend en charge **plus de 50 formats d’entrée et de sortie**, peut traiter des ensembles de données de plusieurs centaines de pages sans charger le fichier complet en mémoire, et fonctionne sur .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6+. Cela signifie que vous pouvez **exporter le shapefile de polygone**, GeoJSON, KML, et de nombreux autres formats directement depuis le code, éliminant ainsi le besoin de convertisseurs tiers.

## Prérequis
1. **Connaissances en programmation C#** – familiarité de base avec les classes et les méthodes.  
2. **Installation d’Aspose.GIS pour .NET** – vous pouvez le télécharger depuis [here](https://releases.aspose.com/gis/net/).  
3. **Configuration de l’environnement de développement** – Visual Studio, Rider, ou tout IDE supportant .NET.  

## Importer les espaces de noms
Nous devons importer les classes GIS dans le scope. Les directives `using` ci‑dessous sont tout ce dont vous avez besoin pour cet exemple.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Comment créer une géométrie de polygone dans Aspose.GIS  

Chargez votre projet, ajoutez les espaces de noms requis, créez une instance d’un objet `Polygon`, construisez son anneau extérieur, ajoutez les sommets du polygone, puis affectez l’anneau – le tout en quelques étapes simples. Cette approche fonctionne sur tous les runtimes .NET pris en charge et produit un polygone conforme aux spécifications OGC prêt à être exporté.

### Étape 1 : Créer un objet Polygon  
La classe `Polygon` est le conteneur de niveau supérieur qui représente une géométrie de polygone unique.  
**La classe `Polygon` représente une forme géométrique fermée composée d’un anneau extérieur et d’éventuels anneaux intérieurs.**  
```csharp
Polygon polygon = new Polygon();
```

### Étape 2 : Définir l’anneau extérieur  
Un `LinearRing` contient la séquence de points qui forment la frontière extérieure.  
**La classe `LinearRing` stocke une liste ordonnée de paires de coordonnées qui doivent former une boucle fermée.**  
```csharp
LinearRing ring = new LinearRing();
```

### Étape 3 : Ajouter des points à l’anneau extérieur  
Nous **ajoutons les sommets du polygone** en injectant des paires latitude‑longitude (ou tout autre système de coordonnées de votre choix) dans l’anneau. Les points doivent former une boucle fermée, donc les premières et dernières coordonnées sont identiques.  
**`LinearRing.AddPoint(x, y)` ajoute un seul sommet à l’anneau ; répétez pour chaque coordonnée.**  
```csharp
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

### Étape 4 : Définir l’anneau extérieur sur le polygone  
Enfin, affectez l’anneau préparé à la propriété `ExteriorRing` du polygone. Le polygone est maintenant un objet géométrique complet et valide.  
**La propriété `ExteriorRing` lie le `LinearRing` construit à l’instance `Polygon`, finalisant ainsi la forme.**  
```csharp
polygon.ExteriorRing = ring;
```

Félicitations ! Vous venez de **créer une géométrie de polygone** avec Aspose.GIS pour .NET. À partir de là, vous pouvez associer le polygone à une entité, l’écrire dans un fichier ou effectuer une analyse spatiale.

## Problèmes courants et astuces  

| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| **Anneau non fermé** | Les premiers et derniers points diffèrent, rendant la géométrie invalide. | Répétez la première coordonnée comme dernière point (comme indiqué ci‑dessus). |
| **Ordre de coordonnées incorrect** | Les bibliothèques SIG attendent X (longitude) puis Y (latitude). | Assurez‑vous de passer `(longitude, latitude)` à `AddPoint`. |
| **Licence manquante** | Le mode d’essai peut limiter certaines opérations. | Appliquez une licence d’essai gratuite pour les tests ; utilisez une licence payante pour la production. |

## Questions fréquentes  

**Q : Puis‑je créer un polygone à partir d’une liste existante de coordonnées ?**  
R : Oui – il suffit d’itérer votre collection de coordonnées et d’appeler `ring.AddPoint(x, y)` pour chaque élément.

**Q : Comment ajouter un anneau intérieur (trou) au polygone ?**  
R : Créez un autre `LinearRing`, ajoutez des points, puis affectez‑le à `polygon.InteriorRings.Add(yourRing);`.

**Q : Existe‑t‑il un moyen de valider le polygone après sa création ?**  
R : Utilisez la propriété `polygon.IsValid` ; elle renvoie `true` si la géométrie respecte les normes OGC.

**Q : Puis‑je exporter le polygone directement en GeoJSON ?**  
R : Absolument. Utilisez `FeatureWriter` avec le format `GeoJson` pour écrire le polygone dans un fichier, ou choisissez `Shapefile` pour **exporter le shapefile de polygone**.

**Q : Aspose.GIS prend‑il en charge les polygones 3‑D ?**  
R : La bibliothèque se concentre actuellement sur les géométries 2‑D ; pour le 3‑D, vous devrez gérer les valeurs Z manuellement ou utiliser une autre bibliothèque spécialisée.

---

**Dernière mise à jour :** 2026-05-31  
**Testé avec :** Aspose.GIS 24.11 for .NET  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Créer un polygone avec trou géométrique en utilisant Aspose.GIS](/gis/net/geometry-creation/create-polygon-with-hole-geometry/)
- [Créer une géométrie de polygone C# et vérifier l’intersection avec Aspose.GIS pour .NET](/gis/net/geometry-analysis/check-geometries-intersection/)
- [Comment créer un tampon avec Aspose.GIS pour .NET](/gis/net/geometry-analysis/create-geometry-buffer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}