---
date: 2026-06-05
description: Apprenez comment comparer des geometries dans .NET en utilisant Aspose.GIS,
  détecter les duplicate geometries, et vérifier la geometry equality dans vos applications.
keywords:
- how to compare geometries
- detect duplicate geometries
- Aspose.GIS geometry equality
linktitle: Comment comparer des geometries pour l'égalité
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to compare geometries in .NET using Aspose.GIS, detect duplicate
    geometries, and check geometry equality in your applications.
  headline: How to Compare Geometries for Equality using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS works with .NET Framework, .NET Core, and .NET Standard
      projects.
    question: Can I use Aspose.GIS for .NET with other .NET frameworks?
  - answer: Absolutely. Download a trial from the [Aspose.GIS releases page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Detailed docs are on the [Aspose.GIS documentation page](https://reference.aspose.com/gis/net/).
    question: Where can I find the full API documentation?
  - answer: Post your question on the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How do I get help if I run into an issue?
  - answer: Yes, temporary licenses are available on the [purchase page](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Comment comparer des geometries pour l'égalité en utilisant Aspose.GIS pour
  .NET
url: /fr/net/geometry-analysis/check-geometries-for-equality/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment comparer des géométries pour l'égalité avec Aspose.GIS pour .NET

## Introduction
Dans ce tutoriel, vous apprendrez **comment comparer des géométries** avec Aspose.GIS pour .NET, une tâche essentielle lorsque vous devez détecter des géométries en double, valider des données spatiales ou appliquer des règles topologiques. Que vous construisiez un service de cartographie, exécutiez une analyse spatiale par lots ou simplement vérifiiez que deux formes occupent le même emplacement, ce guide vous accompagne dans la création, la modification et le test de l'égalité des géométries avec du code C# propre et prêt pour la production.

## Réponses rapides
- **Que signifie « comparer des géométries » ?** Cela vérifie si deux objets géométriques occupent le même espace, quel que soit leur mode de construction.  
- **Quelle méthode est utilisée ?** `SpatiallyEquals` de l'API Aspose.GIS.  
- **Ai‑je besoin d’une licence pour le développement ?** Un essai gratuit suffit pour les tests ; une licence commerciale est requise pour la production.  
- **Versions .NET prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Temps d'implémentation typique ?** Environ 5‑10 minutes pour une vérification d'égalité de base.

## Qu'est‑ce que l'égalité des géométries ?
L'égalité des géométries, également appelée égalité spatiale, signifie que deux géométries représentent exactement le même ensemble de points à la surface de la Terre. Même si une géométrie est construite comme un `MultiLineString` et l'autre comme un `LineString` unique, elles sont considérées égales lorsque chaque coordonnée correspond dans la tolérance définie. Cette définition permet aux développeurs de détecter de manière fiable les géométries en double à travers des sources de données hétérogènes.

## Pourquoi utiliser Aspose.GIS pour comparer des géométries ?
Aspose.GIS propose un moteur de géométrie hors ligne à haute performance qui élimine le besoin de services externes. Il **prend en charge plus de 30 formats vectoriels et raster** (y compris WKT, GeoJSON, Shapefile, KML, GML) et peut traiter des fichiers contenant **des centaines de milliers de sommets** tout en maintenant l'utilisation de la mémoire en dessous de 50 Mo. La méthode `SpatiallyEquals` de la bibliothèque est consciente de la précision, offrant des résultats déterministes même avec des coordonnées à virgule flottante.

### Pourquoi cela importe aux développeurs
Lorsque vous devez **détecter des géométries en double** dans des processus par lots, des pipelines de validation en temps réel ou des migrations de données SIG, une bibliothèque éprouvée élimine les approximations et garantit des résultats cohérents entre différents fournisseurs de données.

## Prérequis
- **.NET Framework ou .NET Core installé** – toute version prise en charge par Aspose.GIS.  
- **Bibliothèque Aspose.GIS pour .NET** – téléchargez depuis la [page de téléchargement d'Aspose.GIS](https://releases.aspose.com/gis/net/).  
- **Un IDE de développement** – Visual Studio, Rider ou VS Code avec les extensions C#.

## Importer les espaces de noms
Dans votre projet .NET, ajoutez les instructions `using` requises afin que le compilateur sache où trouver les classes GIS :

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Étape 1 : Définir les géométries
`MultiLineString` représente une collection de composantes linéaires, tandis que `LineString` définit une ligne continue unique. Les deux classes héritent du type de base `Geometry`.

Tout d'abord, nous créons deux géométries que nous comparerons. Dans cet exemple, `geometry1` est un `MultiLineString` composé de deux segments de ligne, tandis que `geometry2` est un `LineString` unique qui couvre les mêmes points de départ et d'arrivée.

```csharp
var geometry1 = new MultiLineString
{
    new LineString(new [] { new Point(0, 0), new Point(1, 1) }),
    new LineString(new [] { new Point(1, 1), new Point(2, 2) }),
};
var geometry2 = new LineString(new[]
{
    new Point(0, 0), new Point(2, 2),
});
```

## Étape 2 : Vérifier l'égalité des géométries
`SpatiallyEquals` évalue si deux géométries occupent le même ensemble de points, en acceptant éventuellement une valeur de tolérance pour l'imprécision des nombres à virgule flottante.

Nous utilisons maintenant la méthode `SpatiallyEquals` pour vérifier si les deux formes sont considérées comme égales par le moteur GIS.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // True
```

La console affiche `True` car, malgré la construction différente, les deux géométries couvrent la même ligne de (0,0) à (2,2).

## Étape 3 : Modifier une géométrie
Pour illustrer comment une modification affecte l'égalité, nous ajoutons un point supplémentaire à `geometry2`.

```csharp
geometry2.AddPoint(3, 3);
```

## Étape 4 : Revérifier l'égalité après modification
Après la modification, les géométries ne sont plus identiques, donc `SpatiallyEquals` renvoie `False`.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // False
```

Le résultat `False` confirme que le point supplémentaire a rompu l'égalité spatiale.

## Comment détecter les géométries en double ?
Chargez chaque géométrie, appelez `SpatiallyEquals` avec une tolérance adaptée, et filtrez celles qui renvoient `True`. Ce modèle s'adapte bien avec LINQ, vous permettant d'identifier les formes en double dans de grandes collections avec seulement quelques lignes de code. Vous pouvez également le combiner avec `GroupBy` pour regrouper les géométries identiques et réduire les coûts de stockage.

## Problèmes courants et astuces
- **Problèmes de précision** – Si vous travaillez avec des coordonnées très précises, envisagez d'arrondir ou d'utiliser la surcharge de tolérance de `SpatiallyEquals`.  
- **SRID différents** – Assurez-vous que les deux géométries partagent le même identifiant de système de référence spatiale (SRID) avant de les comparer.  
- **Performance** – Pour de grandes collections, les comparaisons par lots avec LINQ ou des boucles parallèles peuvent réduire considérablement la surcharge.

## Questions fréquemment posées
**Q : Puis‑je utiliser Aspose.GIS pour .NET avec d'autres frameworks .NET ?**  
R : Oui, Aspose.GIS fonctionne avec les projets .NET Framework, .NET Core et .NET Standard.

**Q : Une version d'essai gratuite est‑elle disponible ?**  
R : Absolument. Téléchargez une version d'essai depuis la [page des versions d'Aspose.GIS](https://releases.aspose.com/).

**Q : Où puis‑je trouver la documentation complète de l'API ?**  
R : La documentation détaillée se trouve sur la [page de documentation d'Aspose.GIS](https://reference.aspose.com/gis/net/).

**Q : Comment obtenir de l'aide en cas de problème ?**  
R : Publiez votre question sur le forum communautaire Aspose.GIS [ici](https://forum.aspose.com/c/gis/33).

**Q : Puis‑je acheter une licence temporaire pour l'évaluation ?**  
R : Oui, des licences temporaires sont disponibles sur la [page d'achat](https://purchase.aspose.com/temporary-license/).

## Conclusion
Vous savez maintenant **comment comparer des géométries** avec Aspose.GIS pour .NET, de la création des objets à la vérification de l'égalité spatiale et à la gestion des modifications. Cette capacité constitue un élément de base pour des analyses spatiales plus avancées telles que la validation topologique, la détection de doublons et le filtrage basé sur les géométries.

---

**Dernière mise à jour :** 2026-06-05  
**Testé avec :** Aspose.GIS pour .NET 24.11  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Créer une géométrie Polygone C# et vérifier l'intersection avec Aspose.GIS pour .NET](/gis/net/geometry-analysis/check-geometries-intersection/)
- [Comment réaliser une analyse de chevauchement spatial des géométries avec Aspose.GIS pour .NET](/gis/net/geometry-analysis/check-geometries-overlap/)
- [Vérification du routage réseau : géométries qui se touchent avec Aspose.GIS](/gis/net/geometry-analysis/check-geometries-touching/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}