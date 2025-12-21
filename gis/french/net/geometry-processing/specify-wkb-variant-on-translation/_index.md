---
date: 2025-12-21
description: Apprenez à créer une géométrie linestring et à convertir la géométrie
  en WKB avec Aspose.GIS pour .NET en utilisant la variante ExtendedPostGis.
linktitle: Specify WKB Variant on Translation
second_title: Aspose.GIS .NET API
title: Créer une géométrie Linestring et une variante WKB dans Aspose.GIS .NET
url: /fr/net/geometry-processing/specify-wkb-variant-on-translation/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Spécifier la variante WKB lors de la traduction dans Aspose.GIS pour .NET

## Introduction
Dans le domaine du développement de systèmes d'information géographique (SIG), Aspose.GIS pour .NET se démarque comme un ensemble d'outils puissant. Si vous devez **créer une géométrie linestring** puis **convertir la géométrie en WKB**, vous êtes au bon endroit. Sa polyvalence et son efficacité en font un choix privilégié pour les développeurs souhaitant intégrer des fonctionnalités SIG dans leurs applications .NET de manière fluide. Cet article sert de guide complet pour exploiter Aspose.GIS pour .NET, en se concentrant spécifiquement sur la spécification des variantes WKB (Well‑Known Binary) lors des processus de traduction.

## Réponses rapides
- **Que signifie WKB ?** Well‑Known Binary, une représentation binaire compacte des objets géométriques.  
- **Quelle variante WKB me permet de stocker les informations SRID ?** La variante `ExtendedPostGis` (EWKB).  
- **Ai-je besoin d'une licence pour exécuter le code ?** Une licence temporaire ou complète est requise pour une utilisation en production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, et .NET 5/6+.  
- **Combien de temps prend l'implémentation ?** Généralement moins de 10 minutes pour un exemple de base.

## Qu'est‑ce qu'une géométrie Linestring ?
Une linestring est une forme géométrique simple composée d'une séquence de points reliés par des segments de ligne droite. Elle est couramment utilisée pour représenter des routes, des rivières ou toute caractéristique linéaire dans les données SIG.

## Pourquoi spécifier une variante WKB ?
Choisir la bonne variante WKB garantit que les métadonnées importantes — telles que l'identifiant du système de référence spatiale (SRID) — sont préservées lors du stockage ou de l'échange de données géométriques. La variante `ExtendedPostGis` (EWKB) est particulièrement utile lorsqu'on travaille avec PostgreSQL/PostGIS ou tout système qui attend des informations SRID intégrées dans le binaire.

## Prérequis
Avant d'entrer dans les détails de la spécification des variantes WKB dans Aspose.GIS pour .NET, assurez‑vous que les prérequis suivants sont en place :

### Installation d'Aspose.GIS pour .NET
1. Téléchargez Aspose.GIS : Visitez le [lien de téléchargement](https://releases.aspose.com/gis/net/) pour obtenir le package Aspose.GIS pour .NET.  
2. Installez le package : Suivez les instructions d'installation fournies dans la documentation pour intégrer Aspose.GIS à votre environnement .NET sans problème.

### Familiarité avec la programmation C#
1. Connaissances de base en C# : Assurez‑vous de posséder une compréhension fondamentale de la syntaxe et des concepts du langage C#.

## Importer les espaces de noms
Pour démarrer votre parcours avec Aspose.GIS pour .NET et exploiter ses fonctionnalités efficacement, vous devez importer les espaces de noms nécessaires dans votre projet. Voici un guide étape par étape :

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Ces espaces de noms donnent accès aux fonctionnalités Aspose.GIS, vous permettant de travailler avec des données géographiques en toute simplicité.

## Comment créer une géométrie linestring ?
Décomposons l'exemple fourni en plusieurs étapes afin de bien comprendre le processus de spécification des variantes WKB lors de la traduction.

### Étape 1 : Création d'un objet Géométrie
```csharp
IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
```
Dans cette étape, nous **créons une géométrie linestring** représentant une caractéristique linéaire avec les coordonnées spécifiées.

### Étape 2 : Génération de la représentation WKB
```csharp
byte[] wkb = geometry.AsBinary(WkbVariant.ExtendedPostGis);
```
Ici, nous **convertissons la géométrie en WKB** en utilisant la variante `ExtendedPostGis`, qui intègre les informations SRID.

### Étape 3 : Écriture dans un fichier
```csharp
File.WriteAllBytes(Path.Combine("Your Document Directory", "EWkbFile.ewkb"), wkb);
```
Enfin, nous écrivons les données binaires WKB générées dans un fichier nommé `EWkbFile.ewkb` dans le répertoire de votre choix.

## Problèmes courants et solutions
| Problème | Raison | Solution |
|----------|--------|----------|
| **Fichier vide** | `Path.Combine` pointe vers un répertoire inexistant. | Assurez‑vous que le répertoire cible existe ou créez‑le avec `Directory.CreateDirectory`. |
| **SRID incorrect** | Utiliser le `WkbVariant.Standard` par défaut perd le SRID. | Utilisez toujours `WkbVariant.ExtendedPostGis` lorsque la préservation du SRID est requise. |
| **Exception de licence** | Exécution sans licence valide en production. | Appliquez une licence temporaire ou complète avant d'exécuter le code en environnement de production. |

## FAQ
### Aspose.GIS pour .NET est‑il compatible avec toutes les versions de .NET ?
Aspose.GIS pour .NET est conçu pour être compatible avec diverses versions de .NET, assurant flexibilité et accessibilité aux développeurs.

### Puis‑je demander du support ou de l'aide lors de l'utilisation d'Aspose.GIS pour .NET ?
Oui, vous pouvez solliciter du support et de l'aide via le forum dédié [Aspose.GIS](https://forum.aspose.com/c/gis/33), où des experts et d'autres développeurs peuvent répondre à vos questions.

### Aspose.GIS pour .NET propose‑t‑il un essai gratuit ?
Oui, vous pouvez explorer les fonctionnalités d'Aspose.GIS pour .NET grâce à un essai gratuit disponible à [ce lien](https://releases.aspose.com/).

### Comment obtenir une licence temporaire pour Aspose.GIS pour .NET ?
Vous pouvez obtenir une licence temporaire en visitant la [page de licence temporaire](https://purchase.aspose.com/temporary-license/) et en suivant les instructions fournies.

### Où puis‑je acheter une licence pour Aspose.GIS pour .NET ?
Vous pouvez acheter une licence pour Aspose.GIS pour .NET depuis la page d'achat à [ce lien](https://purchase.aspose.com/buy).

## Questions fréquentes
**Q : Puis‑je utiliser le fichier EWKB avec PostGIS ?**  
R : Oui, la variante `ExtendedPostGis` produit un EWKB qui inclut le SRID, lisible directement par PostGIS.

**Q : Est‑il possible de lire un fichier WKB et de le reconvertir en objet géométrique ?**  
R : Absolument. Utilisez `Geometry.FromBinary(byteArray)` pour reconstruire la géométrie.

**Q : La bibliothèque prend‑elle en charge d’autres types de géométrie comme les polygones ?**  
R : Oui, Aspose.GIS gère les points, linestrings, polygones, multipolygones, et bien plus encore.

**Q : Comment spécifier un SRID différent lors de la création de la géométrie ?**  
R : Définissez le SRID sur l’objet géométrique avant d’appeler `AsBinary`, par ex. `geometry.SRID = 4326;`.

**Q : Ce code fonctionnera‑t‑il sur .NET Core ?**  
R : Oui, la même API fonctionne sur .NET Framework, .NET Core et .NET 5/6.

---

**Dernière mise à jour :** 2025-12-21  
**Testé avec :** Aspose.GIS pour .NET 23.9 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}