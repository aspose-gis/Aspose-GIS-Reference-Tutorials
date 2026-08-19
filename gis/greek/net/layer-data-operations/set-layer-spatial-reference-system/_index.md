---
date: 2026-06-15
description: Μάθετε πώς να δημιουργήσετε διανυσματικό στρώμα και να ορίσετε το σύστημα
  αναφοράς χώρου του στρώματος με το Aspose.GIS για .NET. Κατακτήστε τον ορισμό του
  συστήματος αναφοράς, την προσθήκη σημειακού χαρακτηριστικού και την ανάκτηση του
  κώδικα EPSG.
keywords:
- create vector layer
- add point feature
- set layer coordinate system
- define epsg code
- how to set crs
linktitle: Ορισμός συστήματος αναφοράς χώρου του στρώματος
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  headline: Create Vector Layer and Set Layer Spatial Reference System
  type: TechArticle
- description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  name: Create Vector Layer and Set Layer Spatial Reference System
  steps:
  - name: Specify the Document Directory
    text: Begin by specifying the path to your document directory. This will be the
      location where your spatial data files are stored.
  - name: Define Spatial Reference and Set Shapefile Coordinate System
    text: SpatialReferenceSystem represents the CRS of a layer, identified by an EPSG
      code. Define the path for the Shapefile, and **define spatial reference** using
      the EPSG code (26918 in this example). This step **sets the shapefile coordinate
      system** for the layer.
  - name: Create Vector Layer
    text: '`ConstructFeature` creates a new feature object that can hold geometry
      and attribute data. Now **create vector layer** with the specified Shapefile
      path, driver type (Shapefile), and the spatial reference system you just defined.'
  - name: Add Point Feature to the Layer
    text: Construct a new feature and **add point feature** by setting its geometry
      (a `Point` with coordinates 60, 24). Then add the feature to the vector layer.
  - name: Retrieve Spatial Reference System Information (Retrieve EPSG Code)
    text: Open the Vector Layer and retrieve information about the spatial reference
      system, such as the EPSG code and the human‑readable name. This demonstrates
      how to **retrieve EPSG code** and **set layer CRS**.
  type: HowTo
- questions:
  - answer: Open the layer, create a new `SpatialReferenceSystem` with the desired
      EPSG code, assign it to `layer.SpatialReferenceSystem`, then save the layer.
    question: How do I change the CRS of an existing Shapefile?
  - answer: Yes—replace `new Point(x, y)` with `new Polygon(...)` or `new LineString(...)`
      as needed.
    question: Can I add other geometry types (e.g., polygons) using the same approach?
  - answer: Use streaming APIs (`VectorLayer.Create` with `FeatureCollection`) and
      dispose layers promptly to free resources.
    question: Is it possible to work with large datasets efficiently?
  - answer: Yes—use `Geometry.Transform(targetSrs)` to reproject geometries between
      different spatial references.
    question: Does Aspose.GIS support coordinate transformation?
  - answer: Aspose.GIS works with .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Δημιουργία διανυσματικού στρώματος και ορισμός του συστήματος αναφοράς χώρου
  του στρώματος
url: /el/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία Διανυσματικού Στρώματος και Ορισμός Συστήματος Χωρικής Αναφοράς Στρώματος

## Εισαγωγή
Στο εκτεταμένο τοπίο των Γεωγραφικών Συστημάτων Πληροφοριών (GIS), το **Aspose.GIS for .NET** ξεχωρίζει ως μια ισχυρή, υψηλής απόδοσης βιβλιοθήκη που υποστηρίζει **70+** διανυσματικές και ραστερικές μορφές και μπορεί να επεξεργαστεί αρχεία μεγαλύτερα από **10 GB** χωρίς να φορτώνει ολόκληρο το σύνολο δεδομένων στη μνήμη. Σε αυτό το σεμινάριο θα **δημιουργήσετε διανυσματικό στρώμα**, θα ορίσετε την χωρική του αναφορά, θα **προσθέσετε χαρακτηριστικό σημείου** και θα ανακτήσετε τον κώδικα EPSG — όλα με σαφή, βήμα‑βήμα καθοδήγηση. Είτε δημιουργείτε μια υπηρεσία χαρτογράφησης, ένα pipeline μετατροπής δεδομένων ή μια μηχανή χωρικής ανάλυσης, η κατανόηση αυτών των θεμελιωδών εννοιών θα διασφαλίσει ότι το σύστημα συντεταγμένων του shapefile σας είναι ακριβές και η ροή εργασίας GIS αξιόπιστη.

## Γρήγορες Απαντήσεις
- **Τι σημαίνει η «δημιουργία διανυσματικού στρώματος»;** Δημιουργεί ένα νέο στρώμα GIS (π.χ., ένα Shapefile) που μπορεί να αποθηκεύσει γεωμετρίες όπως σημεία, γραμμές ή πολύγωνα.  
- **Ποιος κώδικας EPSG χρησιμοποιείται στο παράδειγμα;** EPSG 26918 (NAD83 / UTM ζώνη 18N).  
- **Μπορώ να προσθέσω χαρακτηριστικό σημείου μετά τη δημιουργία του στρώματος;** Ναι — χρησιμοποιήστε `ConstructFeature()` και εκχωρήστε μια γεωμετρία `Point`.  
- **Πώς μπορώ να ανακτήσω το CRS του στρώματος;** Διαβάστε `layer.SpatialReferenceSystem.EpsgCode` ή `.Name`.  
- **Χρειάζομαι άδεια για το Aspose.GIS;** Διατίθεται δωρεάν δοκιμαστική έκδοση· απαιτείται άδεια για παραγωγική χρήση.

## Τι είναι η δημιουργία διανυσματικού στρώματος;
Η λειτουργία **create vector layer** δημιουργεί ένα νέο διανυσματικό σύνολο δεδομένων (όπως ένα Shapefile) που μπορεί να περιέχει γεωμετρικά χαρακτηριστικά και δεδομένα ιδιοτήτων. Στο Aspose.GIS, αυτό γίνεται με τη δημιουργία ενός αντικειμένου `VectorLayer` με έναν οδηγό και ένα σύστημα χωρικής αναφοράς.

## Γιατί είναι σημαντικό να ορίζετε σωστά το σύστημα συντεταγμένων (CRS) του στρώματος;
Ο ορισμός του σωστού συστήματος αναφοράς συντεταγμένων (CRS) εξασφαλίζει ότι κάθε γεωμετρία που αποθηκεύετε ευθυγραμμίζεται με άλλα χωρικά σύνολα δεδομένων. Με το Aspose.GIS μπορείτε να ορίσετε το CRS χρησιμοποιώντας έναν τυπικό κώδικα EPSG, που εγγυάται τη διαλειτουργικότητα με λογισμικό GIS παγκοσμίως. Για παράδειγμα, το EPSG 26918 ορίζει το NAD83 / UTM ζώνη 18N, μια κοινή προβολή για δεδομένα στην ανατολική περιοχή των ΗΠΑ.

## Προαπαιτούμενα
- Εμπειρία ανάπτυξης .NET (C# ή VB.NET).  
- Visual Studio 2022 ή νεότερη έκδοση.  
- Βιβλιοθήκη Aspose.GIS for .NET – κατεβάστε την **[εδώ](https://releases.aspose.com/gis/net/)**.  
- Βασική εξοικείωση με συστήματα χωρικής αναφοράς (CRS/EPSG).

## Εισαγωγή Χώρων Ονομάτων
Ο χώρος ονομάτων `Aspose.Gis` παρέχει τις βασικές κλάσεις GIS, ενώ το `Aspose.Gis.Geometries` προσφέρει τύπους γεωμετρίας όπως το `Point`.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## Πώς δημιουργείτε ένα διανυσματικό στρώμα στο Aspose.GIS for .NET;
Το `VectorLayer` αντιπροσωπεύει ένα διανυσματικό σύνολο δεδομένων όπως ένα Shapefile και παρέχει μεθόδους για δημιουργία, ανάγνωση και επεξεργασία χαρακτηριστικών.  
Το `SpatialReferenceSystem` ορίζει το σύστημα αναφοράς συντεταγμένων χρησιμοποιώντας έναν κώδικα EPSG.  

Φορτώστε το φάκελο προορισμού, ορίστε ένα `SpatialReferenceSystem` με κωδικό EPSG και καλέστε το `VectorLayer.Create` με τον οδηγό Shapefile. Αυτή η ενιαία κλήση δημιουργεί ένα νέο αρχείο `.shp`, γράφει τα συνοδευτικά αρχεία `.shx` και `.dbf`, και ενσωματώνει τα μεταδεδομένα CRS, έτοιμο για αποδοτική εισαγωγή χαρακτηριστικών.

### Βήμα 1: Καθορίστε τον Κατάλογο Εγγράφων
Ξεκινήστε καθορίζοντας τη διαδρομή προς τον κατάλογο εγγράφων σας. Αυτή θα είναι η θέση όπου αποθηκεύονται τα αρχεία χωρικών δεδομένων σας.

```csharp
string dataDir = "Your Document Directory";
```

### Βήμα 2: Ορίστε τη Χωρική Αναφορά και Ορίστε το Σύστημα Συντεταγμένων του Shapefile
Το `SpatialReferenceSystem` αντιπροσωπεύει το CRS ενός στρώματος, που προσδιορίζεται από έναν κώδικα EPSG.  

Ορίστε τη διαδρομή για το Shapefile και **ορίστε τη χωρική αναφορά** χρησιμοποιώντας τον κώδικα EPSG (26918 σε αυτό το παράδειγμα). Αυτό το βήμα **ορίζει το σύστημα συντεταγμένων του shapefile** για το στρώμα.

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## Πώς μπορείτε να προσθέσετε χαρακτηριστικό σημείου σε ένα διανυσματικό στρώμα;
`Point` είναι ένας τύπος γεωμετρίας που αντιπροσωπεύει ένα ζεύγος συντεταγμένων X/Y.  

Δημιουργήστε ένα νέο χαρακτηριστικό, εκχωρήστε μια γεωμετρία `Point` με τις επιθυμητές συντεταγμένες X/Y, και προσθέστε το χαρακτηριστικό στο ανοιχτό `VectorLayer`. Η λειτουργία γράφει τη γεωμετρία στο αρχείο `.shp` και την εγγραφή ιδιοτήτων στο αρχείο `.dbf` σε μια ενιαία συναλλαγή.

### Βήμα 3: Δημιουργία Διανυσματικού Στρώματος
`ConstructFeature` δημιουργεί ένα νέο αντικείμενο χαρακτηριστικού που μπορεί να περιέχει γεωμετρία και δεδομένα ιδιοτήτων.  

Τώρα **δημιουργήστε διανυσματικό στρώμα** με τη συγκεκριμένη διαδρομή Shapefile, τύπο οδηγού (Shapefile) και το σύστημα χωρικής αναφοράς που μόλις ορίσατε.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

### Βήμα 4: Προσθήκη Χαρακτηριστικού Σημείου στο Στρώμα
Δημιουργήστε ένα νέο χαρακτηριστικό και **προσθέστε χαρακτηριστικό σημείου** ορίζοντας τη γεωμετρία του (ένα `Point` με συντεταγμένες 60, 24). Στη συνέχεια προσθέστε το χαρακτηριστικό στο διανυσματικό στρώμα.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

### Βήμα 5: Ανάκτηση Πληροφοριών Συστήματος Χωρικής Αναφοράς (Ανάκτηση Κώδικα EPSG)
Ανοίξτε το Vector Layer και ανακτήστε πληροφορίες για το σύστημα χωρικής αναφοράς, όπως ο κώδικας EPSG και το ανθρώπινα αναγνώσιμο όνομα. Αυτό δείχνει πώς να **ανακτήσετε τον κώδικα EPSG** και να **ορίσετε το CRS του στρώματος**.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

## Συχνά Προβλήματα και Λύσεις
| Πρόβλημα | Γιατί συμβαίνει | Διόρθωση |
|----------|------------------|----------|
| **Αποτυχία ανοίγματος του στρώματος** | Λάθος οδηγός ή κατεστραμμένη διαδρομή αρχείου | Επαληθεύστε το `Drivers.Shapefile` και βεβαιωθείτε ότι το `path` δείχνει σε υπάρχον αρχείο `.shp`. |
| **Εμφανίζεται λανθασμένο CRS** | Χρήση λανθασμένου κώδικα EPSG | Ελέγξτε ξανά τον κώδικα EPSG με αξιόπιστη πηγή (π.χ., EPSG.io). |
| **Το χαρακτηριστικό δεν αποθηκεύεται** | Μη κλήση του `layer.Add(feature)` μέσα στο μπλοκ `using` | Βεβαιωθείτε ότι η μέθοδος `Add` εκτελείται πριν το στρώμα διαγραφεί. |

## Συχνές Ερωτήσεις
**Ε: Πώς αλλάζω το CRS ενός υπάρχοντος Shapefile;**  
Α: Ανοίξτε το στρώμα, δημιουργήστε ένα νέο `SpatialReferenceSystem` με τον επιθυμητό κώδικα EPSG, εκχωρήστε το στο `layer.SpatialReferenceSystem`, και στη συνέχεια αποθηκεύστε το στρώμα.

**Ε: Μπορώ να προσθέσω άλλους τύπους γεωμετρίας (π.χ., πολύγωνα) με την ίδια προσέγγιση;**  
Α: Ναι — αντικαταστήστε το `new Point(x, y)` με `new Polygon(...)` ή `new LineString(...)` ανάλογα με τις ανάγκες.

**Ε: Είναι δυνατόν να εργαστώ με μεγάλα σύνολα δεδομένων αποδοτικά;**  
Α: Χρησιμοποιήστε τις streaming APIs (`VectorLayer.Create` με `FeatureCollection`) και απελευθερώστε τα στρώματα άμεσα για να ελευθερώσετε πόρους.

**Ε: Υποστηρίζει το Aspose.GIS μετασχηματισμό συντεταγμένων;**  
Α: Ναι — χρησιμοποιήστε το `Geometry.Transform(targetSrs)` για να επαναπροσαρμόσετε γεωμετρίες μεταξύ διαφορετικών χωρικών αναφορών.

**Ε: Ποιες εκδόσεις .NET υποστηρίζονται;**  
Α: Το Aspose.GIS λειτουργεί με .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.

---

**Τελευταία ενημέρωση:** 2026-06-15  
**Δοκιμή με:** Aspose.GIS 24.11 for .NET  
**Συγγραφέας:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικά Σεμινάρια

- [Δημιουργία Διανυσματικού Στρώματος και Ορισμός Αντοχής Γραμμικοποίησης χρησιμοποιώντας Aspose.GIS for .NET](/gis/net/geometry-processing/set-linearization-tolerance/)
- [Δημιουργία Διανυσματικού Στρώματος σε File GDB – Σεμινάριο Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [spatial reference wgs84 – Προσθήκη Στρώματος σε GDB χρησιμοποιώντας Aspose.GIS](/gis/net/layer-management/add-layer-to-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}