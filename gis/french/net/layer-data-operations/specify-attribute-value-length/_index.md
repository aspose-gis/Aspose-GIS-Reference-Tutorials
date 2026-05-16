---
date: 2026-05-16
description: Exemple de couche vectorielle montrant comment définir le Field Width,
  le Attribute Width et le Attribute Length dans Aspose.GIS pour .NET – un guide complet
  étape par étape.
keywords:
- vector layer example
- how to set width
- set field width
- define attribute width
- add attribute length
linktitle: Comment définir le Field Width
schemas:
- author: Aspose
  dateModified: '2026-05-16'
  description: Vector layer example showing how to set field width, define attribute
    width, and add attribute length in Aspose.GIS for .NET – a complete step‑by‑step
    guide.
  headline: Vector Layer Example – How to Set Field Width in Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for peer‑to‑peer
      help and official responses.
    question: Where can I find community support for Aspose.GIS for .NET?
  - answer: Yes, explore the [free trial](https://releases.aspose.com/) to experience
      the full feature set without cost.
    question: Is there a free trial available for Aspose.GIS for .NET?
  - answer: Purchase your license [here](https://purchase.aspose.com/buy).
    question: How do I purchase a license for Aspose.GIS for .NET?
  - answer: Refer to the [documentation](https://reference.aspose.com/gis/net/) for
      comprehensive API details.
    question: Where can I access the documentation for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Exemple de couche vectorielle – Comment définir le Field Width dans Aspose.GIS
  pour .NET
url: /fr/net/layer-data-operations/specify-attribute-value-length/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Exemple de couche vectorielle – Comment définir la largeur d'un champ dans Aspose.GIS pour .NET

Dans cet **exemple de couche vectorielle** vous apprendrez comment définir la largeur d'un champ pour un attribut lors de la création d'un Shapefile avec Aspose.GIS pour .NET. Nous parcourrons chaque étape, de l'importation des espaces de noms à l'ajout d'une entité, et expliquerons pourquoi le contrôle de la longueur des attributs est important pour l'intégrité des données et l'interopérabilité avec d'autres outils SIG.

## Réponses rapides
- **Quel est le but principal de ce guide ?** Pour vous montrer comment définir la largeur d'un champ pour un attribut dans un shapefile à l'aide d'Aspose.GIS pour .NET.  
- **Quelle classe définit la largeur du champ ?** `FeatureAttribute.Width`.  
- **Ai-je besoin d'une licence pour exécuter le code ?** Une licence temporaire suffit pour l'évaluation ; une licence complète est requise pour la production.  
- **Quel format de fichier est utilisé dans l'exemple ?** ESRI Shapefile (`.shp`).  
- **Puis-je modifier la largeur après la création de la couche ?** Non – la largeur doit être définie avant d'ajouter des entités.

## Qu'est-ce que la largeur d'un champ et pourquoi est‑elle importante ?
La largeur d'un champ (également appelée longueur d'attribut) correspond au nombre maximal de caractères qu'un champ de type chaîne peut contenir dans le composant DBF d'un Shapefile. Définir la largeur correcte empêche la troncature silencieuse, garantit que les autres applications SIG lisent les données exactement comme vous les avez saisies, et maintient la taille du fichier prévisible — chaque caractère supplémentaire ajoute un octet par enregistrement.

## Prérequis
- **Bibliothèque Aspose.GIS pour .NET** – téléchargez depuis le [lien de téléchargement](https://releases.aspose.com/gis/net/).  
- **Environnement de développement** – Visual Studio 2022, Visual Studio Code, ou tout IDE supportant .NET 6+.  
- **Accès en écriture** – un dossier sur le disque où le shapefile généré sera enregistré.

## Pourquoi utiliser un exemple de couche vectorielle avec largeur définie ?
Aspose.GIS prend en charge **plus de 30 formats de fichiers SIG**, dont Shapefile, GeoJSON, KML et GML. Lorsque vous définissez explicitement la largeur d'un champ, vous évitez la limite par défaut de 255 caractères, qui peut gonfler inutilement le fichier `.dbf` jusqu'à 255 × nombreEnregistrements octets. Dans les grands jeux de données, cela se traduit par des économies de stockage notables.

## Comment définir la largeur d'un champ pour un attribut ?
Dans cette section, nous chargeons ou créons un `VectorLayer` qui pointe vers le fichier `.shp` cible, définissons un attribut de type chaîne avec une largeur précise, puis ajoutons des entités — le tout en quelques instructions concises. `VectorLayer` représente un jeu de données vectorielles tel qu'un Shapefile et fournit l'accès à sa géométrie et à sa table d'attributs. Vous trouverez ci‑dessous la procédure directe et exploitable que vous pouvez suivre étape par étape :

Chargez ou créez un `VectorLayer` qui pointe vers le fichier `.shp` cible, déclarez un attribut de type chaîne nommé **wide** avec `Width = 120`, puis ajoutez une entité dont la valeur respecte cette limite de 120 caractères. Aspose.GIS tronquera automatiquement toute chaîne plus longue à la largeur définie, préservant la cohérence des données sans lever d'exception.

### Importer les espaces de noms
`FeatureAttribute`, `VectorLayer` et les types associés se trouvent dans l'espace de noms `Aspose.Gis`. Importez‑les en haut de votre fichier :

L'espace de noms `Aspose.Gis` fournit les objets SIG de base avec lesquels vous travaillerez, tels que `VectorLayer`, `Feature` et `FeatureAttribute`. L'importer rend les classes disponibles sans noms entièrement qualifiés.

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Créer un VectorLayer
La classe `VectorLayer` représente une source de données vectorielles (par ex., un Shapefile). C'est le conteneur qui contient les entités et leurs attributs.

La classe `VectorLayer` est la représentation par Aspose.GIS d'un jeu de données vectorielles, gérant la géométrie et les tables d'attributs en mémoire. Créez une instance qui pointe vers un fichier `.shp` nouveau ou existant.

```csharp
string dataDir = "Your Document Directory";
using (VectorLayer layer = VectorLayer.Create(dataDir + "SpecifyAttributeValueLength_out.shp", Drivers.Shapefile))
{
    // Your code for the next steps will go here.
}
```

### Ajouter un attribut avec une longueur spécifique
Définissez un attribut de type chaîne appelé **wide** et définissez sa propriété `Width` à 120 caractères. C'est l'étape centrale de l'**exemple de couche vectorielle**.

L'objet `FeatureAttribute` décrit une colonne de la table d'attributs ; définir `Width = 120` indique au rédacteur de Shapefile d'allouer exactement 120 octets pour chaque enregistrement de ce champ.

```csharp
FeatureAttribute attribute = new FeatureAttribute("wide", AttributeDataType.String);
attribute.Width = 120;
layer.Attributes.Add(attribute);
```

> **Astuce :** La propriété `Width` ne s'applique qu'aux attributs de type chaîne. Les champs numériques, de date ou booléens ignorent `Width` car leur taille est fixée par le type de données.

### Construire et ajouter une entité
Créez une `Feature`, attribuez une valeur qui respecte la limite de 120 caractères, puis ajoutez‑la à la couche. Si la chaîne dépasse la limite, Aspose.GIS la tronque silencieusement à la largeur définie, préservant l'intégrité des données.

La classe `Feature` encapsule la géométrie et les valeurs d'attributs ; après avoir défini l'attribut, appeler `layer.Add(feature)` écrit l'enregistrement dans le Shapefile.

```csharp
Feature feature = layer.ConstructFeature();
feature.SetValue("wide", "this string can be up to 120 characters long now.");
layer.Add(feature);
```

Si vous essayez d'assigner une chaîne plus longue, Aspose.GIS la tronquera à la largeur définie, préservant l'intégrité des données.

## Pièges courants et dépannage
- **Oublié de définir `Width` avant d'ajouter l'attribut ?** La largeur par défaut est de 255 caractères ; la modifier plus tard n'affecte pas les champs déjà créés. Définissez toujours la largeur en premier.  
- **Utilisation d'un type de données non chaîne ?** `Width` est ignoré pour les champs numériques ou de date ; assurez‑vous que `AttributeDataType` de l'attribut est `String`.  
- **Erreur « Field not found » ?** Les noms d'attributs sont sensibles à la casse. Vérifiez que le nom utilisé dans `SetValue` correspond exactement au nom défini dans le schéma.  
- **Augmentation inattendue de la taille du fichier ?** Des largeurs plus grandes augmentent la taille du `.dbf` de façon linéaire. Pour 10 000 enregistrements, une augmentation de largeur de 50 à 120 ajoute environ 700 KB.

## Questions fréquentes
**Q : Comment obtenir une licence temporaire pour Aspose.GIS pour .NET ?**  
R : Vous pouvez obtenir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

**Q : Où puis‑je trouver du support communautaire pour Aspose.GIS pour .NET ?**  
R : Consultez le [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pour obtenir de l'aide entre pairs et des réponses officielles.

**Q : Existe‑t‑il un essai gratuit pour Aspose.GIS pour .NET ?**  
R : Oui, explorez l'[essai gratuit](https://releases.aspose.com/) pour découvrir l'ensemble complet des fonctionnalités sans frais.

**Q : Comment acheter une licence pour Aspose.GIS pour .NET ?**  
R : Achetez votre licence [ici](https://purchase.aspose.com/buy).

**Q : Où puis‑je accéder à la documentation d'Aspose.GIS pour .NET ?**  
R : Consultez la [documentation](https://reference.aspose.com/gis/net/) pour des détails complets sur l'API.

**Q : Puis‑je modifier la largeur du champ après la création de la couche ?**  
R : Non. La largeur du champ doit être définie avant l'ajout de l'attribut ; pour la modifier, vous devez recréer la couche avec le nouveau schéma.

**Q : Le fait d'augmenter la largeur affecte‑t‑il la taille du fichier ?**  
R : Les Shapefiles stockent les champs de type chaîne avec une longueur fixe, ainsi augmenter la largeur augmente directement la taille du fichier `.dbf` proportionnellement au nombre d'enregistrements.

## Conclusion
Cet **exemple de couche vectorielle** a démontré comment définir la largeur d'un champ pour un attribut dans un Shapefile à l'aide d'Aspose.GIS pour .NET, et vous a montré comment ajouter efficacement un attribut avec une longueur spécifique. En contrôlant la largeur des attributs, vous évitez la troncature des données, maintenez des tailles de fichiers optimales et assurez une interopérabilité fluide avec d'autres plateformes SIG. Expérimentez différentes largeurs, explorez la [documentation](https://reference.aspose.com/gis/net/), et libérez tout le potentiel du développement géospatial avec Aspose.GIS.

---

**Dernière mise à jour :** 2026-05-16  
**Testé avec :** Aspose.GIS 24.11 for .NET  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Obtenir les attributs de couche – Récupérer les informations d'attribut de couche avec Aspose.GIS pour .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Comment obtenir la valeur d'un attribut (par défaut) avec Aspose.GIS pour .NET](/gis/net/layer-interaction-and-data-access/get-feature-attribute-value-default/)
- [Créer une couche vectorielle dans File GDB – Tutoriel Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}