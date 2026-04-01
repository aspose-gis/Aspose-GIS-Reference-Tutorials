---
date: 2026-01-05
description: Apprenez comment obtenir les valeurs d’attributs et définir des valeurs
  par défaut dans Aspose.GIS pour .NET. Ce guide étape par étape montre la création
  de couches GeoJSON et la construction de fonctionnalités GIS.
linktitle: How to Get Attribute Value (Default)
second_title: Aspose.GIS .NET API
title: Comment obtenir la valeur d'attribut (par défaut) avec Aspose.GIS pour .NET
url: /fr/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment obtenir la valeur d'un attribut (par défaut) avec Aspose.GIS pour .NET

## Introduction
Dans ce tutoriel complet, vous découvrirez **comment obtenir des valeurs d'attribut** à partir d'une entité SIG en utilisant Aspose.GIS pour .NET, et comment travailler avec des valeurs par défaut lorsqu'un attribut est manquant. Que vous construisiez un moteur d'analyse spatiale ou un simple visualiseur de cartes, maîtrisez la récupération d'attributs et la gestion des valeurs par défaut est essentielle pour des applications SIG fiables.

## Réponses rapides
- **Quelle est la méthode principale ?** `Feature.GetValueOrDefault<T>()`
- **Puis-je définir une valeur par défaut personnalisée ?** Oui, via la surcharge qui accepte une valeur par défaut ou en définissant `DefaultValue` sur l'attribut.
- **Ai‑je besoin d'une licence pour le développement ?** Un essai gratuit suffit pour les tests; une licence commerciale est requise pour la production.
- **Formats de géométrie pris en charge ?** GeoJSON, Shapefile, GML, et bien d'autres via les drivers Aspose.GIS.
- **Fonctionne avec .NET Core/.NET 6+ ?** Absolument—la bibliothèque est multiplateforme.

## Prérequis
Avant de commencer, assurez-vous d’avoir :

- Familiarité de base avec C# et l'écosystème .NET.
- Aspose.GIS pour .NET installé. Si vous ne l'avez pas encore fait, téléchargez‑le depuis [ici](https://releases.aspose.com/gis/net/).
- Un éditeur de code tel que Visual Studio ou VisualStudioCode.

## Importer des espaces de noms
Ajoutez les déclarations `using` requises à votre fichier C# afin que les types de l'API soient disponibles :

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Passons maintenant en revue chaque exemple étape par étape.

## Comment obtenir la valeur de l'attribut (par défaut)
### Étape 1 : Configurer l'environnement
Définissez le chemin du dossier contenant vos documents de test :

```csharp
string dataDir = "Your Document Directory";
```

### Étape 2 : Créer une couche GeoJSON
Nous allons **créer une couche GeoJSON** — le premier endroit où nous définissons un attribut pouvant être nul ou non défini :

```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```

### Étape 3 : Créer une entité SIG
Nous **construisons maintenant une entité GIS** — cela nous fournit une nouvelle instance d'entité qui respecte le schéma d'attributs que nous venons de définir :

```csharp
    Feature feature = layer.ConstructFeature();
```

### Étape 4 : Récupérer les valeurs
Enfin, nous **obtenons les valeurs d'attributs de l'entité** en utilisant plusieurs scénarios, démontrant le fonctionnement des valeurs par défaut :

```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // value == null
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // value == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // value == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```

## Comment définir des valeurs par défaut
### Étape 1 : Créer une autre couche GeoJSON
Cette fois, nous **définirons la valeur par défaut d'un attribut** directement sur le schéma :

```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```

### Étape 2 : Créer une nouvelle entité SIG
```csharp
    Feature feature = layer.ConstructFeature();
```

### Étape 3 : Récupérer et définir les valeurs
Nous récupérons la valeur par défaut, puis la modifions pour voir l'effet de **la définition d'une valeur par défaut** à l'exécution :

```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); // value == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); // value == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); // value == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```

## Pièges et astuces courants
- **N'oubliez jamais de fermer le bloc `using`.** La couche est automatiquement libérée, ce qui libère les poignées de fichiers.
- **Lorsque `CanBeNull` est false, `GetValueOrDefault` renverra toujours une valeur** (soit la valeur stockée, soit la valeur par défaut définie).
- **Utilisez la surcharge générique** (`GetValueOrDefault<T>`) pour éviter le boxing/unboxing des types valeur.
- **Astuce pro :** Si vous devez vérifier si un attribut est réellement défini, utilisez `feature.IsAttributeSet("attribute")` avant d'appeler `GetValueOrDefault`.

## Questions fréquemment posées
### Aspose.GIS est-il compatible avec .NET Core ?
Oui, Aspose.GIS est entièrement compatible avec .NET Core, offrant un support multiplateforme.

### Puis-je utiliser Aspose.GIS pour des projets commerciaux ?
Absolument ! Aspose.GIS est fourni avec une licence commerciale qui vous permet de l'utiliser dans vos applications commerciales sans aucune restriction.

### Où puis-je trouver une assistance et des ressources supplémentaires ?
Visitez le [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pour le support communautaire et explorez la [documentation](https://reference.aspose.com/gis/net/) pour des informations détaillées.

### Existe-t-il un essai gratuit disponible ?
Oui, vous pouvez explorer Aspose.GIS avec un essai gratuit. Téléchargez‑le [ici](https://releases.aspose.com/).

### Comment puis-je obtenir une licence temporaire à des fins de test ?
Pour obtenir une licence temporaire, rendez-vous [ici](https://purchase.aspose.com/temporary-license/).

## FAQ supplémentaire
**Q : Que se passe‑t‑il si j'appelle `GetValueOrDefault` sur un attribut qui n'existe pas ?**
R : La méthode lève une `ArgumentException`. Vérifiez toujours le nom de l'attribut ou utilisez `feature.HasAttribute("name")` au préalable.

**Q : Puis‑je modifier la valeur par défaut après la création de la couche ?**
R : Oui, vous pouvez modifier `attribute.DefaultValue` puis appeler `layer.UpdateAttribute(attribute)` pour persister le changement.

**Q : Aspose.GIS prend‑il en charge les mises à jour en masse des valeurs d'attributs ?**
R: Vous pouvez parcourir une collection d'entités et appeler `SetValue` sur chaque entité; pour de grands ensembles de données, envisagez d'utiliser l'API `FeatureCursor` pour de meilleures performances.

## Conclusion
Dans ce guide, nous avons couvert **comment obtenir des valeurs d'attribut**, comment définir et remplacer les valeurs par défaut, et comment **créer des schémas de couche GeoJSON** adaptés à vos besoins applicatifs. Avec ces techniques, vous pouvez construire des solutions SIG robustes qui gèrent élégamment les données manquantes ou optionnelles.

---

**Dernière mise à jour :** 2026-01-05
**Testé avec :** Aspose.GIS 24.11 pour .NET
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}