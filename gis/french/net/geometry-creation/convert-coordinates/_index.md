---
date: 2025-12-11
description: Apprenez à convertir des coordonnées en DMS à l'aide d'Aspose.GIS pour
  .NET. Inclut des exemples C#, conversion latitude‑longitude en C# et un guide étape
  par étape.
linktitle: Convert Coordinates
second_title: Aspose.GIS .NET API
title: Convertir des coordonnées en DMS avec Aspose.GIS pour .NET
url: /fr/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertir des coordonnées en DMS avec Aspose.GIS

## Introduction
Dans ce tutoriel, vous découvrirez comment **convertir des coordonnées en DMS** (degrés, minutes, secondes) à l’aide de la puissante bibliothèque Aspose.GIS pour .NET. Que vous deviez c# convertir latitude longitude pour des applications cartographiques, générer des chaînes de localisation lisibles par l’homme, ou simplement explorer différents formats de coordonnées, ce guide vous accompagne pas à pas avec des explications claires et du code C# prêt à l’emploi.

## Réponses rapides
- **Que signifie « convertir des coordonnées en DMS » ?** Cela transforme des valeurs numériques de latitude/longitude en notation traditionnelle degrés‑minutes‑secondes.  
- **Quelle bibliothèque gère la conversion ?** Aspose.GIS pour .NET fournit la classe `GeoConvert` avec prise en charge intégrée des formats.  
- **Ai‑je besoin d’une licence pour l’essayer ?** Un essai gratuit est disponible ; une licence commerciale est requise pour la production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, et .NET 5/6+.  
- **Puis‑je réutiliser le même code pour d’autres formats ?** Oui — il suffit de changer la valeur de l’énumération `PointFormats` (par ex. `DecimalDegrees`, `GeoRef`).  

## Qu’est‑ce que la conversion de coordonnées en DMS ?
Convertir des coordonnées en DMS réécrit les valeurs décimales de latitude et de longitude sous un format tel que `25°30'00"N 45°30'00"E`. Cette représentation est largement utilisée en cartographie, navigation et échange de données SIG.

## Pourquoi utiliser Aspose.GIS pour la conversion de coordonnées ?
- **API tout‑en‑un** – Aucun besoin de bibliothèques externes ou de calculs complexes ; Aspose.GIS gère l’analyse et le formatage en interne.  
- **Haute précision** – Gestion précise des cas limites comme les valeurs négatives et les désignateurs d’hémisphère.  
- **Multiplateforme** – Fonctionne de la même façon sous Windows, Linux et macOS avec les runtimes .NET.  
- **Extensible** – Changez facilement entre DMS, degrés décimaux, degrés‑minutes décimales et formats GeoRef.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

1. **Connaissances de base en C#** – Familiarité avec les variables, les appels de méthodes et la sortie console.  
2. **Aspose.GIS installé** – Téléchargez le dernier package depuis le [site Aspose.GIS](https://releases.aspose.com/gis/net/).  

## Importer les espaces de noms
Tout d’abord, importez les espaces de noms requis pour les opérations SIG :

```csharp
using System;
using Aspose.Gis;
```

## Guide étape par étape

### Étape 1 : Démarrer le processus de conversion
Nous affichons un message convivial afin que vous sachiez que la démonstration a commencé.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### Étape 2 : Convertir en degrés décimaux  
Même si le but final est le DMS, nous commençons par afficher la représentation décimale d’origine.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Étape 3 : Convertir en degrés‑minutes décimales  
Ce format (`DD°MM.m'`) est une étape intermédiaire courante lorsque vous devez *convertir lat long degree minutes*.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Étape 4 : Convertir en degrés‑minutes‑secondes (DMS)  
Voici le cœur de notre tutoriel — **convertir des coordonnées en DMS**.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

### Étape 5 : Convertir en GeoRef  
Pour être complet, nous montrons également le format `GeoRef`, utile dans les flux de travail de télédétection.

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## Problèmes courants et solutions
- **Lettres d’hémisphère incorrectes** – Assurez‑vous de passer des valeurs positives pour le nord/est et négatives pour le sud/ouest ; l’API ajoute automatiquement le suffixe correct.  
- **Sortie vide inattendue** – Vérifiez que l’assembly `Aspose.Gis` est correctement référencé et que le projet cible une version .NET prise en charge.  
- **Licence introuvable** – Placez votre fichier de licence à la racine de l’application ou définissez‑la programmatique avec `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.

## Foire aux questions

**Q : Aspose.GIS est‑il compatible avec d’autres langages de programmation ?**  
R : Aspose.GIS cible principalement les développeurs .NET, mais une version Java est également disponible.

**Q : Puis‑je essayer Aspose.GIS avant d’acheter ?**  
R : Oui, vous pouvez accéder à un essai gratuit d’Aspose.GIS depuis le [site web](https://releases.aspose.com/).

**Q : Comment obtenir du support pour Aspose.GIS ?**  
R : Vous pouvez demander de l’aide sur le forum communautaire Aspose.GIS [ici](https://forum.aspose.com/c/gis/33).

**Q : Des licences temporaires sont‑elles disponibles pour Aspose.GIS ?**  
R : Oui, des licences temporaires peuvent être obtenues sur la [page des licences temporaires](https://purchase.aspose.com/temporary-license/).

**Q : Où puis‑je acheter Aspose.GIS ?**  
R : Vous pouvez acheter Aspose.GIS sur la [page d’achat](https://purchase.aspose.com/buy).

## Conclusion
En suivant ces étapes, vous savez maintenant comment **convertir des coordonnées en DMS** et d’autres formats SIG courants à l’aide d’Aspose.GIS pour .NET. Cette fonctionnalité vous permet d’intégrer facilement des chaînes de localisation lisibles par l’homme dans des applications cartographiques, des rapports ou tout flux de travail de données spatiales. N’hésitez pas à expérimenter avec différentes valeurs de latitude/longitude et à explorer les autres formats offerts par la classe `GeoConvert`.

---

**Dernière mise à jour :** 2025-12-11  
**Testé avec :** Aspose.GIS 24.11 pour .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}