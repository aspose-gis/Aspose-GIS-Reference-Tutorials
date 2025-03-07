---
title: Obtenir la valeur de l'attribut de fonctionnalité (par défaut)
linktitle: Obtenir la valeur de l'attribut de fonctionnalité (par défaut)
second_title: API Aspose.GIS .NET
description: Libérez la puissance d’Aspose.GIS pour .NET ! Récupérez et manipulez facilement les valeurs des attributs des caractéristiques grâce à ce guide étape par étape. Téléchargez votre essai maintenant !
weight: 14
url: /fr/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Obtenir la valeur de l'attribut de fonctionnalité (par défaut)

## Introduction
Bienvenue dans le monde d'Aspose.GIS pour .NET ! Dans ce guide complet, nous plongerons dans les subtilités de la récupération des valeurs d'attributs d'entités à l'aide des puissantes fonctionnalités d'Aspose.GIS. Que vous soyez un développeur chevronné ou que vous débutiez tout juste, ce didacticiel vous fournira une procédure pas à pas, vous permettant d'exploiter tout le potentiel de cet outil remarquable.
## Conditions préalables
Avant de vous lancer dans cette aventure de codage, assurez-vous d’avoir les prérequis suivants en place :
- Une connaissance pratique du framework C# et .NET.
-  Aspose.GIS pour .NET installé. Sinon, téléchargez-le depuis[ici](https://releases.aspose.com/gis/net/).
- Un éditeur de code, tel que Visual Studio, pour suivre en toute transparence.
## Importer des espaces de noms
Dans votre projet C#, assurez-vous d'inclure les espaces de noms nécessaires :
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
Maintenant, décomposons chaque exemple en une série d'étapes faciles à suivre.
## Obtenir la valeur de l'attribut de fonctionnalité (par défaut)
### Étape 1 : configurer l'environnement
Commencez par définir le chemin d'accès à votre répertoire de documents :
```csharp
string dataDir = "Your Document Directory";
```
### Étape 2 : Créer une couche GeoJson
Créez une couche GeoJson et définissez un attribut avec des valeurs par défaut :
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```
### Étape 3 : Construire une fonctionnalité
Construisez une entité en utilisant l'attribut défini :
```csharp
    Feature feature = layer.ConstructFeature();
```
### Étape 4 : Récupérer les valeurs
Récupérez les valeurs d'attribut avec différents scénarios :
```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // valeur == nul
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // valeur == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // valeur == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```
## Définition des valeurs par défaut
### Étape 1 : Créer une autre couche GeoJson
Répétez le processus avec une couche GeoJson différente et un double attribut :
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```
### Étape 2 : Construire une fonctionnalité (à nouveau)
```csharp
    Feature feature = layer.ConstructFeature();
```
### Étape 3 : Récupérer et définir les valeurs
Récupérez et définissez les valeurs d'attribut, en affichant les valeurs par défaut :
```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); // valeur == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); // valeur == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); // valeur == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```
Toutes nos félicitations! Vous avez exploité avec succès la puissance d'Aspose.GIS pour .NET pour récupérer et manipuler les valeurs d'attributs d'entités.
## Conclusion
Dans ce didacticiel, nous avons exploré les nuances de la récupération des valeurs d'attributs d'entités à l'aide d'Aspose.GIS pour .NET. Avec son API intuitive et ses capacités robustes, Aspose.GIS ouvre un monde de possibilités pour le développement SIG dans les environnements .NET.
## Questions fréquemment posées
### Aspose.GIS est-il compatible avec .NET Core ?
Oui, Aspose.GIS est entièrement compatible avec .NET Core, offrant une prise en charge multiplateforme.
### Puis-je utiliser Aspose.GIS pour des projets commerciaux ?
Absolument! Aspose.GIS est livré avec une licence commerciale qui vous permet de l'utiliser dans vos applications commerciales sans aucune restriction.
### Où puis-je trouver une assistance et des ressources supplémentaires ?
 Visiter le[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pour obtenir le soutien de la communauté et explorer les[Documentation](https://reference.aspose.com/gis/net/) pour des informations détaillées.
### Existe-t-il un essai gratuit disponible ?
 Oui, vous pouvez explorer Aspose.GIS avec un essai gratuit. Télécharge le[ici](https://releases.aspose.com/).
### Comment puis-je obtenir une licence temporaire à des fins de test ?
 Pour les licences temporaires, visitez[ici](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
