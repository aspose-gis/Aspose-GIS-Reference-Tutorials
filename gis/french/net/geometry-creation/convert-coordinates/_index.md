---
title: Coordonner la conversion avec Aspose.GIS
linktitle: Convertir les coordonnées
second_title: API Aspose.GIS .NET
description: Découvrez comment convertir des coordonnées avec Aspose.GIS pour .NET. Guide étape par étape, prérequis et FAQ fournis.
weight: 25
url: /fr/net/geometry-creation/convert-coordinates/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Coordonner la conversion avec Aspose.GIS

## Introduction
Dans ce didacticiel, nous plongerons dans le monde des systèmes d'information géographique (SIG) à l'aide de la puissante bibliothèque Aspose.GIS pour .NET. Aspose.GIS est une boîte à outils complète qui permet aux développeurs de travailler sans effort avec des données spatiales. Que vous soyez un développeur chevronné ou débutant, ce didacticiel vous guidera tout au long du processus d'utilisation d'Aspose.GIS pour convertir efficacement les coordonnées.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous d'avoir les prérequis suivants :
1. Connaissance de base de C# : La connaissance du langage de programmation C# est essentielle pour comprendre et mettre en œuvre les exemples de code fournis.
  
2.  Installation d'Aspose.GIS : assurez-vous d'avoir téléchargé et installé la bibliothèque Aspose.GIS pour .NET. Vous pouvez le télécharger depuis le[Site Web Aspose.GIS](https://releases.aspose.com/gis/net/).

## Importer des espaces de noms
Avant de commencer, importons les espaces de noms nécessaires pour accéder aux fonctionnalités d'Aspose.GIS :
```csharp
using System;
using Aspose.Gis;
```

Décomposons l'exemple fourni en plusieurs étapes pour une compréhension claire :
## Étape 1 : démarrer le processus de conversion
```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```
Cette ligne affiche simplement un message indiquant le début du processus de conversion des coordonnées.
## Étape 2 : Convertir en degrés décimaux
```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```
 Ici, nous convertissons les coordonnées (25,5, 45,5) au format degrés décimaux en utilisant le`AsPointText` méthode avec le`PointFormats.DecimalDegrees` paramètre. Le résultat est ensuite imprimé sur la console.
## Étape 3 : Convertir en degrés-minutes décimales
```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```
Cette étape convertit les coordonnées au format degrés décimaux minutes et imprime le résultat.
## Étape 4 : Convertir en degrés minutes secondes
```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```
De même, nous convertissons les coordonnées au format degrés minutes secondes et affichons le résultat.
## Étape 5 : Convertir en GeoRef
```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```
Enfin, nous convertissons les coordonnées au format GeoRef et imprimons le résultat.

## Conclusion
Dans ce didacticiel, nous avons exploré le processus de conversion des coordonnées à l'aide d'Aspose.GIS pour .NET. En suivant le guide étape par étape et en utilisant la bibliothèque Aspose.GIS, vous pouvez manipuler efficacement les données spatiales dans vos applications .NET.
## FAQ
### Aspose.GIS est-il compatible avec d’autres langages de programmation ?
Aspose.GIS cible principalement les développeurs .NET, mais il offre une interopérabilité avec Java via Aspose.GIS pour Java.
### Puis-je essayer Aspose.GIS avant d'acheter ?
 Oui, vous pouvez accéder à un essai gratuit d'Aspose.GIS à partir du[site web](https://releases.aspose.com/).
### Comment puis-je obtenir de l'aide pour Aspose.GIS ?
 Vous pouvez demander de l'aide sur le forum de la communauté Aspose.GIS[ici](https://forum.aspose.com/c/gis/33).
### Des licences temporaires sont-elles disponibles pour Aspose.GIS ?
 Oui, des licences temporaires peuvent être obtenues auprès du[page de licence temporaire](https://purchase.aspose.com/temporary-license/).
### Où puis-je acheter Aspose.GIS ?
 Vous pouvez acheter Aspose.GIS auprès du[page d'achat](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
