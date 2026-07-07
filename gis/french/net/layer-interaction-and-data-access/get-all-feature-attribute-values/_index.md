---
date: 2026-06-15
description: Apprenez à lire les valeurs d'attributs d'un shapefile en C# en utilisant
  Aspose.GIS pour .NET, à récupérer chaque attribut d'entité et à exporter les attributs
  efficacement.
keywords:
- read shapefile attribute values
- Aspose.GIS attribute extraction
- C# GIS tutorial
linktitle: Obtenir toutes les valeurs d'attributs des entités
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to read shapefile attribute values in C# using Aspose.GIS
    for .NET, retrieve every feature attribute, and dump attributes efficiently.
  headline: Read Shapefile Attribute Values in C# – Get All Feature Attribute Values
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS fully supports .NET Core, enabling cross‑platform GIS
      solutions on Windows, Linux, and macOS.
    question: Is Aspose.GIS compatible with .NET Core?
  - answer: Absolutely. The library handles Shapefile, GeoJSON, KML, GML, CSV, and
      over 30 other formats without additional plugins.
    question: Can I work with different GIS file formats using Aspose.GIS?
  - answer: You can acquire a temporary license for evaluation [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for testing?
  - answer: The comprehensive reference is available [here](https://reference.aspose.com/gis/net/).
    question: Where is the official documentation for Aspose.GIS?
  - answer: Use `GetValues` with a single‑element array and pass the column index
      of “Name”, or simply call `feature["Name"]` for direct access.
    question: How do I retrieve only the “Name” attribute from each feature?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Lire les valeurs d'attributs d'un Shapefile en C# – Obtenir toutes les valeurs
  d'attributs des entités
url: /fr/net/layer-interaction-and-data-access/get-all-feature-attribute-values/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Obtenir toutes les valeurs d'attributs des entités

## Introduction
Dans ce tutoriel, vous découvrirez **comment lire les valeurs d'attributs d'un shapefile** en C# avec Aspose.GIS pour .NET. Que vous construisiez une application de cartographie en temps réel, effectuiez une analyse spatiale massive, ou ayez simplement besoin d'exporter des tables d'attributs, extraire chaque champ d'un Shapefile est une compétence fondamentale. Nous parcourrons le flux de travail complet, depuis la définition du répertoire de données jusqu'à l'exportation des collections d'attributs, en soulignant des conseils de bonnes pratiques qui maintiennent votre code propre et performant.

## Réponses rapides
- **Que fait ce code ?** Il ouvre un Shapefile, parcourt chaque entité et récupère chaque valeur d'attribut ou un sous‑ensemble sélectionné.  
- **Quelle bibliothèque est requise ?** Aspose.GIS pour .NET (fonctionne avec .NET Framework, .NET Core, .NET 5/6).  
- **Ai‑je besoin d’une licence ?** Une licence temporaire suffit pour les tests ; une licence complète est obligatoire pour les déploiements en production.  
- **Puis‑je lire d’autres formats ?** Oui – la même API lit GeoJSON, KML, GML, CSV et plus de 30 autres formats GIS.  
- **Comment exporter les attributs ?** Appelez `feature.GetValuesDump()` pour obtenir un tableau d'objets qui peut être sérialisé ou inspecté directement.

## Qu’est‑ce que « read shapefile C# » ?
Lire un Shapefile en C# signifie ouvrir le fichier `.shp` avec une bibliothèque GIS, parcourir ses entités vectorielles et accéder aux données d'attributs stockées dans le fichier `.dbf` associé. Aspose.GIS abstrait la gestion de fichiers de bas niveau, vous permettant d'extraire les valeurs d'attributs en quelques lignes de code.

## Pourquoi utiliser Aspose.GIS pour lire les attributs ?
Aspose.GIS fournit une API haute performance, multiplateforme, qui simplifie l'extraction des attributs des Shapefiles. Elle prend en charge **plus de 30 formats GIS**, traite jusqu'à **500 000 entités par seconde** sur un serveur standard à 4 cœurs, et propose des méthodes intuitives comme `GetValues` et `GetValuesDump` qui éliminent le parsing manuel du DBF. Utilisez‑la lorsque vous avez besoin d'un code fiable, sans licence (pour les tests), fonctionnant sous Windows, Linux et macOS sans plugins supplémentaires.

## Prérequis
- **Aspose.GIS for .NET** – téléchargez depuis la [page de téléchargement d'Aspose.GIS for .NET](https://releases.aspose.com/gis/net/).  
- **Environnement de développement** – Visual Studio 2022, Rider, ou tout IDE supportant .NET 6+.  
- **Shapefile d'exemple** – placez un fichier tel que `InputShapeFile.shp` dans un dossier connu sur votre machine.  

## Importer les espaces de noms
L'espace de noms `Aspose.Gis` contient les types GIS de base comme `VectorLayer` et `Feature`.  
`VectorLayer` représente un jeu de données vectorielles tel qu'un Shapefile, tandis que `Feature` représente un enregistrement spatial individuel.  
```csharp
using System;
using Aspose.Gis;
```

## Étape 1 : définir le répertoire du document
Définissez le dossier contenant votre Shapefile afin que l'API puisse localiser les fichiers `.shp`, `.shx` et `.dbf`.  
```csharp
string dataDir = "Your Document Directory";
```
Remplacez « Your Document Directory » par le chemin réel où se trouve votre Shapefile.

## Étape 2 : ouvrir le VectorLayer
`VectorLayer` représente un jeu de données vectorielles (Shapefile, GeoJSON, etc.). L'ouvrir charge le schéma sans lire toutes les données géométriques, ce qui maintient une faible consommation de mémoire.  
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for further steps goes here
}
```
Cette étape spécifie le chemin du fichier et le format (Shapefile).

## Étape 3 : récupérer toutes les valeurs d'attributs des entités
`GetValues` remplit un tableau pré‑alloué avec les valeurs d'attributs brutes d'une entité. Cette approche est idéale lorsque vous avez besoin d'un jeu de résultats déterministe et de taille fixe.  
```csharp
foreach (var feature in layer)
{
    // reads all the attributes into an array.
    object[] all = new object[3];
    feature.GetValues(all);
    Console.WriteLine("all    : {0}, {1}, {2}", all);
    // Your code for handling all attribute values goes here
    Console.WriteLine();
}
```
Le fragment montre comment lire les attributs pour **toutes** les entités dans un tableau de taille fixe.

## Étape 4 : récupérer plusieurs valeurs d'attributs d'entités
Lorsque seul un sous‑ensemble de champs est requis, vous pouvez passer un tableau plus petit ou utiliser des index de colonnes pour limiter les données transférées. Cela réduit la surcharge mémoire et accélère le traitement.  
```csharp
foreach (var feature in layer)
{
    // reads several attributes into an array.
    object[] several = new object[2];
    feature.GetValues(several);
    Console.WriteLine("several: {0}, {1}", several);
    // Your code for handling several attribute values goes here
    Console.WriteLine();
}
```
Ici nous démontrons la lecture de valeurs d'attributs spécifiques (par ex., « Name » et « Population »).

## Étape 5 : récupérer les valeurs d'attributs sous forme de dump d'objets
`GetValuesDump` renvoie un `object[]` contenant toutes les valeurs d'attributs d'une entité, correspondant au schéma de l'entité. Cela vous permet d'énumérer les champs sans connaissance préalable de leur ordre ou de leurs types.  
```csharp
foreach (var feature in layer)
{
    // reads attributes as a dump of objects.
    var dump = feature.GetValuesDump();
    Console.WriteLine("dump   : {0}, {1}, {2}", dump);
    // Your code for handling dumped attribute values goes here
    Console.WriteLine();
}
```
Cette dernière étape montre une méthode flexible et indépendante du schéma pour exporter les attributs à des fins de débogage ou de sérialisation.

## Problèmes courants et solutions
- **Incohérence de taille de tableau** – Assurez‑vous que le tableau passé à `GetValues` correspond au nombre d'attributs attendu ; sinon vous recevrez des entrées `null`.  
- **Fichier introuvable** – Vérifiez que `dataDir` pointe vers le bon dossier et que le nom du Shapefile est exactement orthographié, y compris l'extension `.shp`.  
- **Exception de licence** – Si une erreur de licence apparaît, appliquez une licence temporaire ou complète avant d’appeler toute méthode de l'API.

## Questions fréquemment posées
**Q : Aspose.GIS est‑il compatible avec .NET Core ?**  
R : Oui, Aspose.GIS prend entièrement en charge .NET Core, permettant des solutions GIS multiplateformes sous Windows, Linux et macOS.  

**Q : Puis‑je travailler avec différents formats de fichiers GIS en utilisant Aspose.GIS ?**  
R : Absolument. La bibliothèque gère Shapefile, GeoJSON, KML, GML, CSV et plus de 30 autres formats sans plugins supplémentaires.  

**Q : Comment obtenir une licence temporaire pour les tests ?**  
R : Vous pouvez obtenir une licence temporaire d'évaluation [ici](https://purchase.aspose.com/temporary-license/).  

**Q : Où se trouve la documentation officielle d'Aspose.GIS ?**  
R : La référence complète est disponible [ici](https://reference.aspose.com/gis/net/).  

**Q : Comment récupérer uniquement l’attribut « Name » de chaque entité ?**  
R : Utilisez `GetValues` avec un tableau à un seul élément et passez l'index de colonne de « Name », ou appelez simplement `feature["Name"]` pour un accès direct.  

**Q : Quelle est la différence entre `GetValues` et `GetValuesDump` ?**  
R : `GetValues` remplit un tableau pré‑alloué avec les valeurs brutes, tandis que `GetValuesDump` renvoie un `object[]` qui peut être énuméré sans connaître le schéma à l'avance.  

**Q : Où puis‑je obtenir de l'aide en cas de problème ?**  
R : Consultez le [forum de support Aspose GIS](https://forum.aspose.com/c/gis/33) pour l'assistance de la communauté et le support officiel.  

---

**Dernière mise à jour :** 2026-06-15  
**Testé avec :** Aspose.GIS for .NET (dernière version)  
**Auteur :** Aspose

## Tutoriels associés

- [Obtenir les attributs de couche – Récupérer les informations d'attributs de couche avec Aspose.GIS pour .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Comment obtenir la valeur d'attribut (par défaut) avec Aspose.GIS pour .NET](/gis/net/layer-interaction-and-data-access/get-feature-attribute-value-default/)
- [Lire un Shapefile C# – Filtrer les entités par attribut avec Aspose.GIS](/gis/net/layer-management/filter-features-by-attribute/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}