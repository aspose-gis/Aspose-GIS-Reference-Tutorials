---
date: 2026-06-30
description: Μάθετε πώς να προσθέσετε στρώση σε σύνολο δεδομένων File GDB χρησιμοποιώντας
  το Aspose.GIS με αναφορά χώρου WGS84. Ακολουθήστε αυτόν τον οδηγό βήμα‑βήμα για
  να προσθέσετε μια στρώση σε .NET.
keywords:
- how to add layer
- spatial reference wgs84
- Aspose.GIS .NET
- File GDB dataset
linktitle: Προσθήκη στρώσης σε σύνολο δεδομένων File GDB
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to add layer to a File GDB dataset using Aspose.GIS with
    spatial reference WGS84. Follow this step‑by‑step guide to add a layer in .NET.
  headline: How to Add Layer to File GDB Dataset with spatial reference WGS84 using
    Aspose.GIS
  type: TechArticle
- questions:
  - answer: spatial reference wgs84 (WGS 84)
    question: What is the primary coordinate system used?
  - answer: Aspose.GIS for .NET
    question: Which library provides the API?
  - answer: Yes – a temporary Aspose license is available.
    question: Do I need a license for testing?
  - answer: Absolutely, you can define any number of feature attributes.
    question: Can I add attributes to the new layer?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Πώς να προσθέσετε στρώση σε σύνολο δεδομένων File GDB με αναφορά χώρου WGS84
  χρησιμοποιώντας το Aspose.GIS
url: /el/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# πώς να προσθέσετε στρώση – αναφορά χώρου wgs84 με Aspose.GIS

## Εισαγωγή
Έτοιμοι να ενισχύσετε τη ροή εργασίας GIS με το Aspose.GIS για .NET; Σε αυτό το tutorial θα μάθετε **πώς να προσθέσετε στρώση** σε ένα σύνολο δεδομένων File GDB ενώ εργάζεστε με το σύστημα συντεταγμένων **spatial reference WGS84**. Θα περάσουμε βήμα-βήμα, από την προετοιμασία του φακέλου δεδομένων σας μέχρι την επικύρωση της νέας στρώσης, ώστε να μπορείτε να χειρίζεστε γεωγραφικά δεδομένα με σιγουριά και αποδοτικότητα.

## Σύντομες Απαντήσεις
- **Ποιο είναι το κύριο σύστημα συντεταγμένων που χρησιμοποιείται;** spatial reference wgs84 (WGS 84)  
- **Ποια βιβλιοθήκη παρέχει το API;** Aspose.GIS for .NET  
- **Χρειάζομαι άδεια για δοκιμή;** Ναι – a temporary Aspose license is available.  
- **Μπορώ να προσθέσω χαρακτηριστικά στη νέα στρώση;** Απόλυτα, you can define any number of feature attributes.  
- **Ποιες εκδόσεις .NET υποστηρίζονται;** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## Τι είναι η αναφορά χώρου wgs84;
Η αναφορά χώρου wgs84 (World Geodetic System 1984) είναι το πιο ευρέως χρησιμοποιούμενο γεωγραφικό σύστημα συντεταγμένων. Ορίζει το πλάτος και το μήκος σε μοίρες και λειτουργεί ως το προεπιλεγμένο CRS για πολλά σύνολα δεδομένων GIS, συμπεριλαμβανομένου αυτού που θα δημιουργήσουμε σε αυτόν τον οδηγό.

## Γιατί να χρησιμοποιήσετε το Aspose.GIS για την προσθήκη στρώσης;
Φορτώστε τα GIS δεδομένα σας χωρίς εξωτερικά binaries και διατηρήστε πλήρη έλεγχο πάνω στον ορισμό του σχήματος. Το Aspose.GIS υποστηρίζει **40+ spatial reference systems**, μπορεί να επεξεργαστεί αρχεία μεγαλύτερα από **2 GB** χωρίς να φορτώνει ολόκληρο το σύνολο δεδομένων στη μνήμη, και λειτουργεί σε Windows, Linux και macOS. Αυτό το καθιστά μια αξιόπιστη, διαπλατφορμική λύση για αυτοματοποίηση GIS επιπέδου επιχείρησης.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

- Aspose.GIS for .NET Library: Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη από την [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/).  
- Document Directory: Δημιουργήστε έναν αφιερωμένο φάκελο στον υπολογιστή σας για την αποθήκευση αρχείων GIS.  
- Μια προσωρινή άδεια Aspose (προαιρετική για αξιολόγηση) – δείτε το FAQ παρακάτω για τον σύνδεσμο λήψης.

## Εισαγωγή Namespaces
Προσθέστε τις απαιτούμενες δηλώσεις `using` στο έργο C# ώστε να μπορείτε να έχετε πρόσβαση στις κλάσεις Aspose.GIS:

*Δεν απαιτείται μπλοκ κώδικα εδώ· απλώς προσθέστε τις παρακάτω γραμμές στην αρχή του αρχείου σας:*

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.Geometries.Collections;
using Aspose.Gis.SpatialReference;
```

## Βήμα 1: Αντιγραφή Καταλόγου
**Definition anchor:** Ένα σύνολο δεδομένων File GDB είναι μια βάση δεδομένων ESRI βασισμένη σε φάκελο που αποθηκεύει χωρικά δεδομένα σε ένα σύνολο αρχείων.  
Πρώτα, αντιγράψτε τον φάκελο που περιέχει το αρχικό σύνολο δεδομένων GDB. Η διατήρηση ενός αντιγράφου προστατεύει τα αρχικά δεδομένα ενώ πειραματίζεστε.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Βήμα 2: Άνοιγμα Συνόλου Δεδομένων και Επαλήθευση Δυνατότητας Δημιουργίας
`Dataset` αντιπροσωπεύει μια συλλογή GIS στρώσεων αποθηκευμένων σε ένα File GDB. Ανοίξτε το πρόσφατα αντιγραμμένο σύνολο δεδομένων και επιβεβαιώστε ότι μπορεί να δημιουργήσει νέες στρώσεις. Η ιδιότητα `CanCreateLayers` πρέπει να επιστρέφει **True**. **`CanCreateLayers` είναι μια boolean ιδιότητα που υποδεικνύει εάν το σύνολο δεδομένων υποστηρίζει τη δημιουργία νέων στρώσεων.**

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Βήμα 3: Δημιουργία και Συμπλήρωση Νέας Στρώσης με αναφορά χώρου wgs84
Τώρα δημιουργούμε μια στρώση με όνομα **data** και ορίζουμε ρητά την αναφορά χώρου της σε **Wgs84**. Προσθέτουμε επίσης ένα απλό χαρακτηριστικό με όνομα **Name** και εισάγουμε ένα σημείο χαρακτηριστικό. **`CreateLayer` creates a new layer in the dataset with the specified name and spatial reference.** **`SpatialReference` represents the coordinate system used by a layer.** **`Feature` is an individual geographic object (point, line, or polygon) stored in a layer.**

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Βήμα 4: Άνοιγμα και Επικύρωση της Προστιθέμενης Στρώσης
Τέλος, ανοίξτε τη στρώση που μόλις δημιουργήσατε και επαληθεύστε το περιεχόμενό της. Η κονσόλα θα εμφανίσει ότι η στρώση περιέχει ένα χαρακτηριστικό και ότι το χαρακτηριστικό **Name** ταιριάζει με αυτό που ορίσαμε. **`Layer.Open` opens an existing layer for reading or editing.** Αυτό επιβεβαιώνει ότι η στρώση προστέθηκε σωστά και ότι η αναφορά χώρου είναι WGS84.

```csharp
using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
{
    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
    var feature = layer.ConstructFeature();
    feature.SetValue("Name", "Name_1");
    feature.Geometry = new Point(12.21, 23.123, 20, -200);
    layer.Add(feature);
}
```

## Πώς να προσθέσετε στρώση σε σύνολο δεδομένων File GDB;
Φορτώστε το σύνολο δεδομένων, καλέστε `CreateLayer` με το επιθυμητό όνομα και την αναφορά χώρου, ορίστε το σχήμα των χαρακτηριστικών και, στη συνέχεια, εισάγετε χαρακτηριστικά. Όλα αυτά μπορούν να γίνουν με λίγες κλήσεις μεθόδων του Aspose.GIS, και το API διαχειρίζεται αυτόματα το κλείδωμα αρχείων και την επικύρωση του σχήματος. Η διαδικασία εξασφαλίζει ότι η νέα στρώση συμμορφώνεται με την αναφορά χώρου του συνόλου δεδομένων, ότι οι ορισμοί χαρακτηριστικών αποθηκεύονται στο σχήμα της στρώσης, και ότι τα δεδομένα μπορούν να προσπελαστούν από οποιοδήποτε λογισμικό GIS που υποστηρίζει File GDB.

## Συχνά Προβλήματα & Συμβουλές
- **Λάθος διαδρομή:** Ensure `dataDir` ends with a path separator (`/` or `\`) so the concatenated strings form valid file paths.  
- **Σφάλματα άδειας:** If you see licensing warnings, apply a temporary license from the Aspose portal before running the code.  
- **Ασυμφωνία CRS:** When opening the layer later in another GIS tool, confirm that the tool recognizes WGS 84 (EPSG:4326) as the coordinate system.  
- **Μεγάλα σύνολα δεδομένων:** For datasets exceeding 1 GB, consider using `Dataset.OpenReadOnly` to reduce memory consumption.

## Συχνές Ερωτήσεις
### Q: Μπορώ να χρησιμοποιήσω το Aspose.GIS για .NET με άλλες βιβλιοθήκες GIS;
A: Ναι, Aspose.GIS works independently but can be combined with libraries such as GDAL or NetTopologySuite for advanced processing.

### Q: Διατίθεται προσωρινή άδεια για δοκιμαστικούς σκοπούς;
A: Ναι, you can obtain a temporary license from [here](https://purchase.aspose.com/temporary-license/) for testing and evaluation.

### Q: Ποια συστήματα αναφοράς χώρου υποστηρίζει το Aspose.GIS για .NET;
A: Aspose.GIS supports over **40 EPSG codes**, including popular systems like WGS84 (EPSG:4326), Web Mercator (EPSG:3857), and NAD83 (EPSG:4269). Explore the comprehensive documentation [here](https://reference.aspose.com/gis/net/).

### Q: Μπορώ να συνεισφέρω στην κοινότητα Aspose.GIS;
A: Absolutely! Join the discussions and share your experiences on the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).

### Q: Πού μπορώ να βρω λεπτομερή τεκμηρίωση για το Aspose.GIS για .NET;
A: Explore the comprehensive documentation [here](https://reference.aspose.com/gis/net/) for in‑depth information on all classes, methods, and best practices.

---

**Τελευταία ενημέρωση:** 2026-06-30  
**Δοκιμή με:** Aspose.GIS for .NET (latest stable version)  
**Συγγραφέας:** Aspose

{{< blocks/products/products-backtop-button >}}

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Σχετικά Μαθήματα

- [Δημιουργία File Geodatabase .NET Dataset με Aspose.GIS](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Δημιουργία διανυσματικής στρώσης σε File GDB – Aspose.GIS .NET Οδηγός](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Δημιουργία File GDB Dataset και ορισμός ανοχών για μια στρώση](/gis/net/layer-data-operations/set-tolerances-for-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}