---
date: 2026-01-02
description: Apprenez à écrire du GeoJSON dans un flux en C# en utilisant Aspose.GIS
  pour .NET. Affichez des exemples de GeoJSON en C# et boostez vos applications géospatiales.
linktitle: Write GeoJSON to Stream
second_title: Aspose.GIS .NET API
title: Comment écrire du GeoJSON dans un flux avec Aspose.GIS pour .NET
url: /fr/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment écrire du GeoJSON dans un flux

## Introduction
Si vous devez **how to write geojson** directement dans un flux mémoire ou fichier dans une application .NET, vous êtes au bon endroit. Dans ce tutoriel, nous passerons en revue les étapes exactes pour écrire du GeoJSON dans un flux en utilisant la bibliothèque Aspose.GIS pour .NET, et nous vous montrerons également comment **display GeoJSON C#** dans la console. À la fin, vous disposerez d’un modèle réutilisable que vous pourrez intégrer à n’importe quel projet géospatial.

## Réponses rapides
- **Que signifie « write GeoJSON to stream » ?** Cela signifie sérialiser une couche vectorielle au format GeoJSON et envoyer les octets à un objet `Stream` (par ex., `MemoryStream`).  
- **Quelle bibliothèque gère cela ?** Aspose.GIS pour .NET fournit un pilote GeoJSON intégré.  
- **Ai‑je besoin d’une licence pour le développement ?** Un essai gratuit fonctionne pour le développement ; une licence commerciale est requise pour la production.  
- **Puis‑je exécuter cela sous Linux ?** Oui – Aspose.GIS est multiplateforme et fonctionne sous Windows, Linux et macOS.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Qu’est‑ce que « how to write geojson » dans .NET ?
Aspose.GIS vous permet de créer un `VectorLayer`, d’ajouter des entités, puis de sérialiser la couche à l’aide du pilote `Drivers.GeoJson`. Le pilote écrit le texte GeoJSON directement dans n’importe quel `Stream`, vous donnant un contrôle total sur l’endroit où les données sont envoyées (mémoire, fichier, réseau, etc.).

## Pourquoi utiliser Aspose.GIS pour cette tâche ?
- **Zero‑dependency serialization** – aucune bibliothèque JSON externe requise.  
- **Full GeoJSON spec compliance** – prend en charge les FeatureCollections, les propriétés et la précision des coordonnées.  
- **Cross‑platform** – fonctionne de la même manière sous Windows, Linux et macOS.  
- **Performance‑optimized** – écrit directement dans le flux sans chaînes intermédiaires.

## Prérequis
1. **Aspose.GIS for .NET** – téléchargez‑le [here](https://releases.aspose.com/gis/net/).  
2. **Document directory** – décidez où vous souhaitez conserver les fichiers temporaires ou les flux de sortie.

## Importer les espaces de noms
Tout d’abord, incluez les espaces de noms qui vous donnent accès aux classes Aspose.GIS et aux utilitaires d’E/S standard de .NET :

```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Étape 1 : Configurer le répertoire de documents
Définissez le dossier qui hébergera les fichiers temporaires dont vous pourriez avoir besoin.

```csharp
string dataDir = "Your Document Directory";
```

Remplacez `"Your Document Directory"` par le chemin réel sur votre machine.

## Étape 2 : Créer un MemoryStream
Un `MemoryStream` vous permet de garder le GeoJSON en mémoire, ce qui est idéal pour les API ou lorsque vous souhaitez renvoyer les données directement à un client.

```csharp
using (var memoryStream = new MemoryStream())
{
    // Subsequent steps will be placed inside this block
}
```

## Étape 3 : Créer une couche vectorielle avec le pilote GeoJSON
À l’intérieur du bloc MemoryStream, créez un `VectorLayer` qui utilise le pilote GeoJSON. Cela indique à Aspose.GIS de sérialiser la couche en GeoJSON.

```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Feature creation goes here
}
```

## Étape 4 : Définir les attributs des entités
Ajoutez des définitions d’attributs qui apparaîtront comme propriétés dans la sortie GeoJSON finale.

```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## Étape 5 : Construire et ajouter des entités
Créez deux points d’exemple, attribuez‑leur des valeurs d’attributs, puis ajoutez‑les à la couche.

```csharp
// First Feature
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);

// Second Feature
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```

## Étape 6 : Afficher la sortie GeoJSON C#
Après avoir peuplé la couche, convertissez les octets du flux en chaîne UTF‑8 et écrivez‑les dans la console. Cela montre comment **display GeoJSON C#** les résultats.

```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

Vous devriez voir une FeatureCollection GeoJSON valide affichée dans le terminal.

## Problèmes courants et solutions
| Problème | Cause | Solution |
|----------|-------|----------|
| Sortie vide | La position du flux est à la fin lors de la lecture | Appelez `memoryStream.Position = 0;` avant de convertir en chaîne. |
| Géométrie invalide | Les coordonnées sont hors des plages valides | Vérifiez que la latitude est comprise entre -90 et 90, la longitude entre -180 et 180. |
| Exception de licence | Exécution sans licence valide en production | Appliquez une licence temporaire ou complète avec `License license = new License(); license.SetLicense("Aspose.GIS.lic");` |

## Questions fréquentes
### Puis‑je utiliser Aspose.GIS pour .NET à la fois sous Windows et Linux ?
Oui, Aspose.GIS pour .NET est compatible avec les systèmes Windows et Linux.

### Une version d’essai gratuite est‑elle disponible ?
Absolument ! Vous pouvez explorer un essai gratuit [here](https://releases.aspose.com/).

### Où puis‑je trouver la documentation détaillée ?
Consultez la documentation [here](https://reference.aspose.com/gis/net/).

### Comment obtenir une licence temporaire ?
Des licences temporaires sont disponibles [here](https://purchase.aspose.com/temporary-license/).

### Besoin d’assistance ou avez‑vous d’autres questions ?
Visitez notre forum de support [here](https://forum.aspose.com/c/gis/33).

## FAQ
**Q : Puis‑je écrire du GeoJSON directement dans un fichier au lieu d’un MemoryStream ?**  
R : Oui – remplacez `MemoryStream` par `FileStream` et fournissez un chemin de fichier. Le même pilote fonctionne.

**Q : Comment contrôler l’indentation ou le formatage du GeoJSON généré ?**  
R : Aspose.GIS écrit du JSON compact par défaut. Pour un affichage « pretty‑printed », post‑traitez la chaîne avec `JsonSerializerOptions { WriteIndented = true }`.

**Q : Est‑il possible d’ajouter des géométries plus complexes (par ex., des polygones) à la couche ?**  
R : Absolument. Créez un objet `Polygon` ou `LineString`, assignez‑le à `Feature.Geometry`, puis ajoutez l’entité comme indiqué ci‑dessus.

**Q : Les grands ensembles de données tiendront‑ils dans un `MemoryStream` ?**  
R : Pour des collections très volumineuses, envisagez de streamer directement vers un fichier ou d’utiliser un `BufferedStream` afin d’éviter une consommation excessive de mémoire.

**Q : Le pilote GeoJSON prend‑il en charge les définitions CRS (Coordinate Reference System) ?**  
R : Oui – définissez la propriété `SpatialReferenceSystem` de la couche avant d’ajouter des entités si vous avez besoin d’un CRS autre que WGS84.

## Conclusion
Vous disposez maintenant d’un modèle complet, prêt pour la production, pour **how to write geojson** vers n’importe quel flux .NET en utilisant Aspose.GIS. Que vous ayez besoin de renvoyer du GeoJSON depuis une API web, de l’enregistrer dans un fichier ou simplement de l’afficher dans la console, les étapes ci‑dessus couvrent l’ensemble du flux de travail. Explorez davantage la bibliothèque pour travailler avec d’autres formats comme Shapefile, KML ou GML, et continuez à créer des applications géospatiales plus riches.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2026-01-02  
**Testé avec :** Aspose.GIS 24.11 for .NET  
**Auteur :** Aspose