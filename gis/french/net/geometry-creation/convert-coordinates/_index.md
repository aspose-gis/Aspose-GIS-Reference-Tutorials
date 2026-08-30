---
date: 2026-08-18
description: Convertissez des degrés décimaux en DMS avec Aspose.GIS for .NET. Ce
  guide pas à pas en C# montre comment convertir latitude/longitude, degrés décimaux
  en DMS et plus encore.
keywords:
- decimal degrees to dms
- convert coordinates dms
- gis coordinate conversion
- convert lat long dms
- c# convert lat long
lastmod: 2026-08-18
linktitle: Convertir les coordonnées
og_description: Conversion de degrés décimaux en DMS simplifiée avec Aspose.GIS for
  .NET. Apprenez à transformer les valeurs latitude‑longitude en format DMS en minutes.
og_image_alt: Guide showing decimal degrees to DMS conversion using Aspose.GIS in
  C#
og_title: Comment convertir des degrés décimaux en DMS avec Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  headline: How to convert decimal degrees to dms with Aspose.GIS for .NET
  type: TechArticle
- description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  name: How to convert decimal degrees to dms with Aspose.GIS for .NET
  steps:
  - name: start the conversion process
    text: We print a friendly message so you know the demo has begun.
  - name: convert to decimal degrees
    text: Even though the final goal is DMS, we start by showing the original decimal
      representation. This also demonstrates the **decimal degrees to dms** path you’ll
      later follow.
  - name: convert to degree decimal minutes
    text: This format (`DD°MM.m'`) is a common intermediate step when you need to
      **convert lat long degree minutes**.
  - name: convert to degree minutes seconds (dms)
    text: Here’s the core of our tutorial—**convert coordinates to dms**.
  - name: convert to GeoRef
    text: For completeness, we also demonstrate the `GeoRef` format, useful in remote‑sensing
      workflows.
  type: HowTo
- questions:
  - answer: Aspose.GIS primarily targets .NET developers, but a Java version is also
      available.
    question: Is Aspose.GIS compatible with other programming languages?
  - answer: Yes, you can access a free trial of Aspose.GIS from the [website](https://releases.aspose.com/).
    question: Can I try Aspose.GIS before purchasing?
  - answer: You can seek assistance from the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How can I get support for Aspose.GIS?
  - answer: Yes, temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses available for Aspose.GIS?
  - answer: You can purchase Aspose.GIS from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert coordinates
- Aspose.GIS
- .NET GIS processing
title: Comment convertir des degrés décimaux en DMS avec Aspose.GIS for .NET
url: /fr/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment convertir des degrés décimaux en DMS avec Aspose.GIS

## Introduction
Dans ce tutoriel, vous apprendrez **comment convertir des degrés décimaux en DMS** en utilisant la puissante bibliothèque Aspose.GIS pour .NET. Que vous ayez besoin de **c# convert lat long**, de générer des chaînes de localisation lisibles par l'homme pour les rapports, ou simplement d'explorer différents formats de coordonnées, ce guide vous accompagne à chaque étape avec des explications claires et des extraits C# prêts à l'exécution.

## Réponses rapides
- **Que signifie « convert coordinates to dms » ?** Il transforme les valeurs numériques de latitude/longitude en notation traditionnelle degrés‑minutes‑secondes.  
- **Quelle bibliothèque gère la conversion ?** Aspose.GIS pour .NET fournit la classe `GeoConvert` avec prise en charge intégrée des formats.  
- **Ai-je besoin d'une licence pour l'essayer ?** Un essai gratuit est disponible ; une licence commerciale est requise pour une utilisation en production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, et .NET 5/6+.  
- **Puis-je utiliser le même code pour d'autres formats ?** Oui—il suffit de changer la valeur de l'énumération `PointFormats` (par ex., `DecimalDegrees`, `GeoRef`).  

## Qu'est-ce que la conversion de coordonnées en DMS ?
La conversion de coordonnées en DMS réécrit les valeurs décimales de latitude et de longitude dans un format tel que `25°30'00"N 45°30'00"E`. Le processus divise chaque degré décimal en degrés entiers, minutes (un soixantième de degré) et secondes (un soixantième de minute), puis ajoute l'indicateur d'hémisphère approprié (N, S, E, W). Cette forme lisible par l'homme est essentielle pour de nombreux jeux de données hérités et pour communiquer des emplacements précis sans recourir à la notation décimale.

## Pourquoi utiliser Aspose.GIS pour la conversion de coordonnées ?
Aspose.GIS prend en charge **plus de 50 formats d'entrée et de sortie** et peut traiter des fichiers GIS de plusieurs centaines de pages sans charger l'ensemble du jeu de données en mémoire. L'API offre une précision sub‑millimétrique pour les cas limites tels que les valeurs négatives et les désignateurs d'hémisphère, et elle fonctionne de manière cohérente sur les runtimes .NET Windows, Linux et macOS.

## Prérequis
Avant de commencer, assurez‑vous d'avoir :

1. **Basic knowledge of C#** – familiarité avec les variables, les appels de méthodes et la sortie console.  
2. **Aspose.GIS installed** – téléchargez le dernier package depuis le [Aspose.GIS website](https://releases.aspose.com/gis/net/). Vous pouvez également explorer le site principal des versions Aspose à l'adresse du [Aspose releases website](https://releases.aspose.com/).  

## Importer les espaces de noms
Tout d'abord, importez les espaces de noms requis pour les opérations GIS :

Le texte de l'espace réservé Import Namespaces reste inchangé.

## Guide étape par étape

### Qu'est-ce que la classe GeoConvert ?
La classe `GeoConvert` fournit des méthodes statiques pour convertir entre différents formats de coordonnées tels que les degrés décimaux, le DMS et le GeoRef. Elle comprend des surcharges qui acceptent des valeurs numériques brutes ou des objets `Point` et renvoie des chaînes formatées ou de nouvelles instances `Point`. En gérant les cas limites comme les coordonnées négatives et l'arrondi, la classe garantit que la sortie respecte les spécifications GIS standard, simplifiant l'intégration dans toute application de cartographie .NET.

### Étape 1 : démarrer le processus de conversion
Nous affichons un message convivial pour indiquer que la démonstration a commencé.

```csharp
using System;
using Aspose.Gis;
```

### Étape 2 : convertir en degrés décimaux
Même si l'objectif final est le DMS, nous commençons par afficher la représentation décimale originale. Cela montre également le chemin **decimal degrees to dms** que vous suivrez plus tard.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### Étape 3 : convertir en degrés décimaux minutes
Ce format (`DD°MM.m'`) est une étape intermédiaire courante lorsque vous devez **convert lat long degree minutes**.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Étape 4 : convertir en degrés minutes secondes (dms)
Voici le cœur de notre tutoriel — **convert coordinates to dms**.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Étape 5 : convertir en GeoRef
Pour plus de complétude, nous démontrons également le format `GeoRef`, utile dans les flux de travail de télédétection.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

## Problèmes courants et solutions
- **Lettres d'hémisphère incorrectes** – Assurez‑vous de passer des valeurs positives pour le nord/est et négatives pour le sud/ouest ; l'API ajoute automatiquement le suffixe correct.  
- **Sortie vide inattendue** – Vérifiez que l'assembly `Aspose.Gis` est correctement référencé et que le projet cible une version .NET prise en charge.  
- **Licence non trouvée** – Placez votre fichier de licence à la racine de l'application ou définissez‑la programmatique­ment avec `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.

## Questions fréquemment posées

**Q : Aspose.GIS est‑il compatible avec d'autres langages de programmation ?**  
A : Aspose.GIS cible principalement les développeurs .NET, mais une version Java est également disponible.

**Q : Puis‑je essayer Aspose.GIS avant d'acheter ?**  
A : Oui, vous pouvez accéder à un essai gratuit d'Aspose.GIS depuis le [website](https://releases.aspose.com/).

**Q : Comment obtenir du support pour Aspose.GIS ?**  
A : Vous pouvez demander de l'aide sur le forum communautaire Aspose.GIS [here](https://forum.aspose.com/c/gis/33).

**Q : Des licences temporaires sont‑elles disponibles pour Aspose.GIS ?**  
A : Oui, des licences temporaires peuvent être obtenues depuis la [temporary license page](https://purchase.aspose.com/temporary-license/).

**Q : Où puis‑je acheter Aspose.GIS ?**  
A : Vous pouvez acheter Aspose.GIS sur la [purchase page](https://purchase.aspose.com/buy).

## Conclusion
En suivant ces étapes, vous savez maintenant comment **convert decimal degrees to dms** et d'autres formats GIS courants en utilisant Aspose.GIS pour .NET. Cette capacité vous permet d'intégrer de façon transparente des chaînes de localisation lisibles par l'homme dans les applications de cartographie, les rapports ou tout flux de travail de données spatiales. N'hésitez pas à expérimenter avec différentes valeurs de latitude/longitude et à explorer les autres formats proposés par la classe `GeoConvert`.

---

**Dernière mise à jour :** 2026-08-18  
**Testé avec :** Aspose.GIS 24.11 for .NET  
**Auteur :** Aspose  

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## Tutoriels associés

- [Comment créer une géométrie de point et obtenir le type de géométrie avec Aspose.GIS pour .NET](/gis/net/geometry-analysis/get-geometry-type/)
- [Comment convertir GeoJSON – Aspose.GIS pour .NET](/gis/net/geo-data-conversion/)
- [Créer une géométrie MultiPoint .NET avec Aspose.GIS](/gis/net/geometry-creation/create-multipoint-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}