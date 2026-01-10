---
date: 2026-01-10
description: Apprenez à créer une couche vectorielle dans une géodatabase de fichiers
  en utilisant Aspose.GIS pour .NET. Gérez les données géospatiales avec la référence
  spatiale WGS84 et les options de fichier gdb.
linktitle: Create File GDB with Single Layer
second_title: Aspose.GIS .NET API
title: Créer une couche vectorielle dans un fichier GDB – Tutoriel Aspose.GIS .NET
url: /fr/net/layer-management/create-file-gdb-with-single-layer/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une couche vectorielle dans un File GDB

## Introduction
Si vous devez **créer une couche vectorielle** à l’intérieur d’une géodatabase de type File (GDB) et gérer les données géospatiales efficacement, Aspose.GIS for .NET vous offre une approche propre, code‑first. Dans ce guide pas à pas, nous vous montrerons comment écrire une entité linéaire, configurer les options du file gdb, et travailler avec le système de référence spatiale WGS84 — le tout en quelques lignes de C#. À la fin, vous pourrez compter les entités d’une couche et intégrer le GDB résultant dans n’importe quel flux de travail de cartographie ou d’analyse .NET.

## Réponses rapides
- **Que signifie « créer une couche vectorielle » ?** Cela consiste à ajouter un nouveau jeu de données vectorielles (points, lignes ou polygones) à un fichier de géodatabase.  
- **Quelle bibliothèque dois‑je utiliser ?** Aspose.GIS for .NET fournit un support complet pour la création et la modification de File GDB.  
- **Ai‑je besoin d’une licence pour le développement ?** Une version d’essai gratuite suffit pour les tests ; une licence commerciale est requise en production.  
- **Puis‑je définir le système de référence spatiale ?** Oui – utilisez `SpatialReferenceSystem.Wgs84` pour le datum WGS84 le plus répandu.  
- **Combien de lignes de code ?** Moins de 30 lignes pour créer le GDB, ajouter une entité linéaire et lire le nombre d’entités.

## Qu’est‑ce qu’une opération « créer une couche vectorielle » ?
Créer une couche vectorielle signifie définir une nouvelle table à l’intérieur d’une géodatabase qui stocke des objets géométriques (points, lignes, polygones) ainsi que leurs attributs. Cette opération constitue la base de toute application SIG nécessitant de **gérer des données géospatiales**.

## Pourquoi utiliser Aspose.GIS pour créer une couche vectorielle ?
- **Aucune dépendance externe** – l’API fonctionne immédiatement sur .NET Framework, .NET Core et .NET 5/6.  
- **Support complet du File GDB** – vous pouvez configurer `FileGdbOptions` pour contrôler la compression, l’indexation spatiale, etc.  
- **Gestion intégrée du système de référence spatiale** – il suffit de passer `SpatialReferenceSystem.Wgs84` pour travailler dans le système de coordonnées global.  
- **API simple** – écrivez une entité linéaire, ajoutez‑la à une couche, et récupérez le nombre d’entités avec seulement quelques appels de méthode.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

1. **Aspose.GIS for .NET** – téléchargez‑le depuis la [page de téléchargement d’Aspose.GIS for .NET](https://releases.aspose.com/gis/net/).  
2. **Un environnement de développement .NET** – Visual Studio, Rider ou le CLI `dotnet`.  
3. **Un dossier** où le File GDB sera créé (nous l’appellerons *Your Document Directory*).

## Importer les espaces de noms
Ajoutez les instructions `using` requises en haut de votre fichier C# :

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```

## Étape 1 : Configurer votre répertoire de documents
```csharp
string dataDir = "Your Document Directory";
```
Remplacez `"Your Document Directory"` par le chemin absolu où vous souhaitez que le File GDB soit créé.

## Étape 2 : Créer un File Geodatabase avec une seule couche
```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```
Cet extrait **crée une couche vectorielle** à l’aide de `FileGdbOptions`, écrit une simple entité linéaire, et la stocke dans un File GDB qui utilise le **système de référence spatiale WGS84**.

## Étape 3 : Ouvrir le File Geodatabase et récupérer les informations de la couche
```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Output: Features count: 1
}
```
Ici nous **comptons les entités de la couche** en ouvrant le jeu de données et en affichant le nombre d’entités – dans ce cas, `1`.

## Problèmes courants et solutions
| Problème | Raison | Solution |
|----------|--------|----------|
| **`File not found`** | Variable `path` incorrecte | Vérifiez que `dataDir` pointe vers un dossier existant et que `path` le combine avec un nom de fichier, par ex. `Path.Combine(dataDir, "MyData.gdb")`. |
| **`Unsupported geometry`** | Type de géométrie non autorisé dans le File GDB | Limitez‑vous aux types `Point`, `LineString` ou `Polygon` pour les couches de base. |
| **`License not set`** | Exécution sans licence valide en production | Enregistrez votre licence avec `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Foire aux questions
### Puis‑je utiliser Aspose.GIS for .NET dans mes projets .NET existants ?
Oui, Aspose.GIS for .NET peut être intégré de façon transparente dans vos projets .NET existants.

### Existe‑t‑il une version d’essai d’Aspose.GIS for .NET ?
Oui, vous pouvez explorer les fonctionnalités d’Aspose.GIS for .NET en téléchargeant la [version d’essai gratuite](https://releases.aspose.com/).

### Où puis‑je trouver la documentation détaillée d’Aspose.GIS for .NET ?
Consultez la [documentation](https://reference.aspose.com/gis/net/) pour obtenir des informations complètes sur Aspose.GIS for .NET.

### Comment obtenir du support pour Aspose.GIS for .NET ?
Visitez le [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pour le support communautaire et l’assistance.

### Des licences temporaires sont‑elles disponibles pour Aspose.GIS for .NET ?
Oui, vous pouvez obtenir une [licence temporaire](https://purchase.aspose.com/temporary-license/) pour Aspose.GIS for .NET.

---

**Dernière mise à jour :** 2026-01-10  
**Testé avec :** Aspose.GIS 24.11 for .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}