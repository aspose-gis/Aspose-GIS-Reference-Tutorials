---
date: 2026-04-30
description: Apprenez à lire l'ObjectID d’une couche File Geodatabase en utilisant
  Aspose.GIS pour .NET. Guide étape par étape, prérequis et conseils de dépannage.
keywords:
- how to read objectid
- Aspose.GIS File GDB
- read object id .NET
linktitle: Lire l’ID d’objet depuis la couche File GDB
second_title: Aspose.GIS .NET API
title: Comment lire l'ObjectID d’une couche File GDB à l’aide d’Aspose.GIS
url: /fr/net/layer-data-operations/read-object-id-from-file-gdb-layer/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment lire l'ObjectID à partir d'une couche File GDB en utilisant Aspose.GIS

## Introduction
Si vous devez extraire les valeurs **ObjectID** d'une couche de géodatabase de fichiers (GDB), ce tutoriel vous montre **comment lire l'ObjectID** rapidement avec Aspose.GIS pour .NET. Nous vous guiderons à travers la configuration requise, le code exact dont vous avez besoin, et des conseils pratiques pour éviter les pièges courants. À la fin, vous serez capable d'intégrer la récupération de l'ObjectID dans n'importe quel flux de travail géospatial .NET.

## Réponses rapides
- **Que représente l'ObjectID ?** Un identifiant unique pour chaque entité d'une couche SIG.  
- **Quel pilote est requis ?** `Drivers.FileGdb` pour les fichiers de géodatabase de fichiers.  
- **Ai-je besoin d'une licence pour ce code ?** Une version d'essai fonctionne pour le développement ; une licence commerciale est requise pour la production.  
- **Puis-je l'utiliser avec .NET Core ?** Oui, Aspose.GIS prend en charge .NET Framework et .NET Core.  
- **Y a-t-il une gestion spéciale pour les grands ensembles de données ?** Itérer avec des instructions `using` pour garantir que les ressources sont libérées rapidement.

## Qu'est-ce que l'ObjectID et pourquoi le lire ?
ObjectID (souvent nommé `OBJECTID` ou `FID`) est la clé primaire qui identifie de façon unique chaque entité dans une couche SIG. Y accéder est essentiel lorsque vous devez :

- Mettre à jour ou supprimer des entités spécifiques.
- Corréler les entités entre plusieurs couches.
- Effectuer des recherches rapides sans parcourir les tables d'attributs.

## Prérequis
Avant de commencer, assurez-vous d'avoir :

1. **Visual Studio** (toute version récente) – pour écrire et exécuter du code C#.
2. **Aspose.GIS for .NET** – téléchargez-le depuis la [page de téléchargement](https://releases.aspose.com/gis/net/).
3. **Connaissances de base en C#** – familiarité avec les boucles et la sortie console.

## Importation des espaces de noms
First, add a reference to the Aspose.GIS library (via NuGet or direct DLL) and import the required namespaces:

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Guide étape par étape

### Étape 1 : Définir le répertoire de données
Spécifiez le dossier qui contient votre fichier `.gdb`.

```csharp
string dataDir = "Your Document Directory";
```

Remplacez `"Your Document Directory"` par le chemin absolu du dossier contenant `test.gdb`.

### Étape 2 : Ouvrir le jeu de données et la couche cible
Créez une instance `Dataset` en utilisant le pilote File GDB, puis ouvrez la couche souhaitée (remplacez `"layer"` par le nom réel de votre couche).

```csharp
string path = dataDir + "test.gdb";
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    // Code to read object IDs goes here
}
```

Les instructions `using` garantissent que les poignées de fichiers sont libérées automatiquement.

### Étape 3 : Parcourir toutes les entités
Bouclez sur chaque entité de la couche. C'est ici que nous extrairons l'ObjectID.

```csharp
foreach (var feature in layer)
{
    // Code to process each feature goes here
}
```

### Étape 4 : Récupérer et afficher l'ObjectID
À l'intérieur de la boucle, appelez `GetValue<int>("OBJECTID")` pour récupérer l'identifiant entier et l'afficher.

```csharp
Console.WriteLine(feature.GetValue<int>("OBJECTID"));
```

L'exécution du programme affichera une liste de valeurs ObjectID dans la console, une par ligne.

## Problèmes courants et dépannage

| Symptôme | Cause probable | Solution |
|----------|----------------|----------|
| **`ArgumentException: No such layer`** | Nom de couche incorrect | Vérifiez le nom exact dans le GDB (sensible à la casse). |
| **`FileNotFoundException`** | Chemin vers le `.gdb` incorrect | Utilisez `Path.Combine(dataDir, "test.gdb")` et revérifiez le dossier. |
| **`InvalidOperationException` when reading OBJECTID** | Le nom de l'attribut diffère (par ex., `FID`) | Inspectez le schéma avec `layer.GetFields()` et ajustez le nom du champ. |
| **Performance slowdown on large layers** | Chargement de toutes les entités en une fois | Traitez les entités par lots ou utilisez une approche basée sur un curseur si prise en charge. |

## FAQ

### Puis-je utiliser Aspose.GIS pour .NET avec d'autres langages de programmation ?
Aspose.GIS pour .NET est spécifiquement conçu pour les applications .NET. Cependant, Aspose propose également des bibliothèques pour Java et d'autres plateformes.

### Existe-t-il une version d'essai gratuite d'Aspose.GIS ?
Oui, vous pouvez télécharger une version d'essai gratuite d'Aspose.GIS pour .NET depuis le [site web](https://releases.aspose.com/gis/net/).

### Comment obtenir le support technique pour Aspose.GIS ?
Si vous rencontrez des problèmes ou avez des questions concernant Aspose.GIS, vous pouvez consulter le [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pour obtenir de l'aide.

### Puis-je acheter une licence temporaire pour Aspose.GIS ?
Oui, vous pouvez obtenir une licence temporaire sur le site d'Aspose à des fins de test et d'évaluation.

### Où puis-je trouver une documentation complète pour Aspose.GIS pour .NET ?
Vous pouvez consulter la [documentation](https://reference.aspose.com/gis/net/) pour des informations détaillées sur l'utilisation des API et des fonctionnalités d'Aspose.GIS.

## Questions fréquentes

**Q : Et si ma couche utilise un nom de champ différent pour l'identifiant unique ?**  
R : Remplacez `"OBJECTID"` dans `GetValue<int>("OBJECTID")` par le nom réel du champ (par ex., `"FID"` ou `"ID"`).

**Q : Est-il possible d'écrire les valeurs ObjectID dans un autre fichier ?**  
R : Oui, vous pouvez créer une nouvelle collection `Feature` ou exporter vers CSV en utilisant les I/O standard de .NET après avoir récupéré les ID.

**Q : Aspose.GIS prend-il en charge la lecture des ObjectID à partir de shapefiles également ?**  
R : Absolument. Utilisez `Drivers.Shapefile` au lieu de `Drivers.FileGdb` et le même modèle `GetValue<int>("OBJECTID")` fonctionne.

**Q : Comment gérer un File GDB protégé par mot de passe ?**  
R : Fournissez le mot de passe lors de l'ouverture du jeu de données : `Dataset.Open(path, Drivers.FileGdb, new OpenOptions { Password = "yourPwd" })`.

**Q : Puis-je exécuter ce code sous Linux ?**  
R : Oui, Aspose.GIS pour .NET est multiplateforme et fonctionne sous Linux avec .NET Core/5+.

---

**Dernière mise à jour :** 2026-04-30  
**Testé avec :** Aspose.GIS for .NET 24.11 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}