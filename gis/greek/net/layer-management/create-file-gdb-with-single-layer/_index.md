---
date: 2026-06-30
description: Μάθετε πώς να δημιουργήσετε διανυσματικό στρώμα σε File Geodatabase χρησιμοποιώντας
  το Aspose.GIS για .NET. Διαχειριστείτε γεωχωρικά δεδομένα με αναφορά χώρου WGS84
  και επιλογές file gdb.
keywords:
- create vector layer
- add line feature
- manage geospatial data
- feature count example
- file gdb compression
linktitle: Δημιουργία File GDB με ένα μόνο στρώμα
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create vector layer in a File Geodatabase using Aspose.GIS
    for .NET. Manage geospatial data with spatial reference WGS84 and file gdb options.
  headline: Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial
  type: TechArticle
- description: Learn how to create vector layer in a File Geodatabase using Aspose.GIS
    for .NET. Manage geospatial data with spatial reference WGS84 and file gdb options.
  name: Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial
  steps:
  - name: '**Aspose.GIS for .NET** – download it from the [Aspose.GIS for .NET download
      page](https://releases.aspose.com/gis/net/).'
    text: '**Aspose.GIS for .NET** – download it from the [Aspose.GIS for .NET download
      page](https://releases.aspose.com/gis/net/).'
  - name: '**A .NET development environment** – Visual Studio, Rider, or the `dotnet`
      CLI.'
    text: '**A .NET development environment** – Visual Studio, Rider, or the `dotnet`
      CLI.'
  - name: '**A folder** where the File GDB will be created (we’ll call it *Your Document
      Directory*).'
    text: '**A folder** where the File GDB will be created (we’ll call it *Your Document
      Directory*).'
  type: HowTo
- questions:
  - answer: It means adding a new vector dataset (points, lines, or polygons) to a
      geodatabase file.
    question: What does “create vector layer” mean?
  - answer: Aspose.GIS for .NET provides full support for File GDB creation and editing.
    question: Which library should I use?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license for development?
  - answer: Yes – use `SpatialReferenceSystem.Wgs84` for the common WGS84 datum.
    question: Can I set the spatial reference?
  - answer: Less than 30 lines to create the GDB, add a line feature, and read back
      the feature count.
    question: How many lines of code?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Δημιουργία διανυσματικού στρώματος σε File GDB – Aspose.GIS .NET Tutorial
url: /el/net/layer-management/create-file-gdb-with-single-layer/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία Διανυσματικού Στρώματος σε File GDB

## Εισαγωγή
Αν χρειάζεστε **create vector layer** μέσα σε ένα File Geodatabase (GDB) και να διαχειρίζεστε γεωχωρικά δεδομένα αποδοτικά, το Aspose.GIS for .NET σας παρέχει μια καθαρή, προσέγγιση code‑first. Σε αυτόν τον οδηγό βήμα‑βήμα θα σας δείξουμε πώς να γράψετε ένα χαρακτηριστικό γραμμής, να διαμορφώσετε τις επιλογές του file GDB και να εργαστείτε με την αναφορά χώρου WGS84 — όλα σε λίγες γραμμές C#. Στο τέλος θα μπορείτε να μετρήσετε τα χαρακτηριστικά σε ένα στρώμα και να ενσωματώσετε το προκύπτον GDB σε οποιαδήποτε ροή εργασίας χαρτογράφησης ή ανάλυσης .NET.

## Γρήγορες Απαντήσεις
- **Τι σημαίνει το “create vector layer”;** Σημαίνει την προσθήκη ενός νέου διανυσματικού συνόλου δεδομένων (σημεία, γραμμές ή πολύγωνα) σε ένα αρχείο γεωβάσης.  
- **Ποια βιβλιοθήκη πρέπει να χρησιμοποιήσω;** Το Aspose.GIS for .NET παρέχει πλήρη υποστήριξη για δημιουργία και επεξεργασία File GDB.  
- **Χρειάζομαι άδεια για ανάπτυξη;** Μια δωρεάν δοκιμή λειτουργεί για δοκιμές· απαιτείται εμπορική άδεια για παραγωγή.  
- **Μπορώ να ορίσω την χωρική αναφορά;** Ναι – χρησιμοποιήστε `SpatialReferenceSystem.Wgs84` για το κοινό datum WGS84.  
- **Πόσες γραμμές κώδικα;** Λιγότερες από 30 γραμμές για τη δημιουργία του GDB, την προσθήκη ενός χαρακτηριστικού γραμμής και την ανάγνωση του αριθμού χαρακτηριστικών.

## Τι είναι η λειτουργία “create vector layer”;
Η δημιουργία ενός διανυσματικού στρώματος ορίζει έναν νέο πίνακα σε μια γεωβάση που αποθηκεύει γεωμετρικά αντικείμενα (σημεία, γραμμές, πολύγωνα) και τα χαρακτηριστικά τους. Κάθε γραμμή αντιπροσωπεύει ένα χαρακτηριστικό, και η στήλη γεωμετρίας περιέχει το σχήμα του. Στο Aspose.GIS το δημιουργείτε δημιουργώντας ένα αντικείμενο `FeatureClass` μέσα σε ένα `FileGdbDataSource` και καθορίζοντας τον τύπο γεωμετρίας.

## Γιατί να χρησιμοποιήσετε το Aspose.GIS για τη δημιουργία διανυσματικού στρώματος;
Το Aspose.GIS εξαλείφει εξωτερικές εξαρτήσεις και υποστηρίζει **50+** μορφές GIS, καθιστώντας το μια ολοκληρωμένη λύση για προγραμματιστές .NET.  
Παρέχει ενσωματωμένη συμπίεση file GDB (μέχρι 70 % μείωση για τυπικά διανυσματικά δεδομένα), χωρική ευρετηρίαση και πλήρη διαχείριση WGS84 έτοιμη προς χρήση. Η βιβλιοθήκη λειτουργεί σε .NET Framework 4.6+, .NET Core 2.0+, και .NET 5/6, ώστε να μπορείτε να στοχεύσετε οποιοδήποτε σύγχρονο περιβάλλον Windows ή cross‑platform χωρίς πρόσθετες εγγενείς βιβλιοθήκες.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

1. **Aspose.GIS for .NET** – κατεβάστε το από τη [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/).  
2. **Ένα .NET περιβάλλον ανάπτυξης** – Visual Studio, Rider ή το `dotnet` CLI.  
3. **Έναν φάκελο** όπου θα δημιουργηθεί το File GDB (θα τον ονομάσουμε *Your Document Directory*).

## Εισαγωγή Ονοματοχώρων
Οι δηλώσεις `using` φέρνουν τους απαιτούμενους τύπους στο πεδίο ορατότητας.  

Ο χώρος ονομάτων `Document` παρέχει τα βασικά GIS αντικείμενα, ενώ το `System.IO` διαχειρίζεται τις διαδρομές αρχείων.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```

## Βήμα 1: Ρύθμιση του Φακέλου Εγγράφου σας
Αντικαταστήστε το `"Your Document Directory"` με την απόλυτη διαδρομή όπου θέλετε να βρίσκεται το File GDB.  
Η δημιουργία του φακέλου εκ των προτέρων αποτρέπει το σφάλμα “File not found” που συχνά αντιμετωπίζουν οι νέοι χρήστες.

```csharp
string dataDir = "Your Document Directory";
```

## Βήμα 2: Δημιουργία File Geodatabase με Ένα Στρώμα
Η κλάση FileGdbOptions είναι μια κλάση που σας επιτρέπει να διαμορφώσετε τη συμπίεση, τη χωρική ευρετηρίαση και άλλες ρυθμίσεις για ένα File Geodatabase.  
Αυτό το απόσπασμα **δημιουργεί ένα διανυσματικό στρώμα** χρησιμοποιώντας `FileGdbOptions`, γράφει ένα απλό χαρακτηριστικό γραμμής και το αποθηκεύει σε ένα File GDB που χρησιμοποιεί την **αναφορά χώρου WGS84**.

```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```

## Βήμα 3: Άνοιγμα του File Geodatabase και Ανάκτηση Πληροφοριών Στρώματος
`FileGdbDataSource` είναι το σημείο εισόδου για τη δημιουργία και το άνοιγμα File Geodatabases.  
`FeatureClass` αντιπροσωπεύει ένα διανυσματικό στρώμα μέσα σε μια γεωβάση και παρέχει πρόσβαση στα χαρακτηριστικά του.  
Εδώ **μετράμε τα χαρακτηριστικά στο στρώμα** ανοίγοντας το σύνολο δεδομένων και εκτυπώνοντας τον αριθμό των χαρακτηριστικών – σε αυτήν την περίπτωση, `1`.

```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Output: Features count: 1
}
```

## Πώς επαληθεύετε ότι το στρώμα δημιουργήθηκε σωστά;
Ανοίξτε τη γεωβάση με `FileGdbDataSource.Open` και ερωτήστε το `FeatureClass`. Η ιδιότητα `Count` επιστρέφει το συνολικό αριθμό χαρακτηριστικών, επιβεβαιώνοντας ότι η γραμμή αποθηκεύτηκε. Αυτό το γρήγορο βήμα επαλήθευσης σας βοηθά να εντοπίσετε προβλήματα νωρίς, ειδικά όταν αυτοματοποιείτε μαζικές εισαγωγές.

## Συχνά Προβλήματα και Λύσεις

| Πρόβλημα | Αιτία | Διόρθωση |
|----------|-------|----------|
| **`File not found`** | Λανθασμένη μεταβλητή `path` | Επαληθεύστε ότι το `dataDir` δείχνει σε έναν υπάρχον φάκελο και ότι το `path` το συνδυάζει με ένα όνομα αρχείου, π.χ., `Path.Combine(dataDir, "MyData.gdb")`. |
| **`Unsupported geometry`** | Χρήση τύπου γεωμετρίας που δεν επιτρέπεται στο File GDB | Χρησιμοποιήστε `Point`, `LineString` ή `Polygon` για βασικά στρώματα. |
| **`License not set`** | Εκτέλεση χωρίς έγκυρη άδεια σε παραγωγή | Καταχωρίστε την άδειά σας με `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Συχνές Ερωτήσεις
### Μπορώ να χρησιμοποιήσω το Aspose.GIS for .NET στα υπάρχοντα .NET έργα μου;
Ναι, το Aspose.GIS for .NET μπορεί να ενσωματωθεί άψογα στα υπάρχοντα .NET έργα σας.

### Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.GIS for .NET;
Ναι, μπορείτε να εξερευνήσετε τις δυνατότητες του Aspose.GIS for .NET κατεβάζοντας τη [free trial version](https://releases.aspose.com/).

### Πού μπορώ να βρω λεπτομερή τεκμηρίωση για το Aspose.GIS for .NET;
Ανατρέξτε στην [documentation](https://reference.aspose.com/gis/net/) για πλήρεις πληροφορίες σχετικά με το Aspose.GIS for .NET.

### Πώς μπορώ να λάβω υποστήριξη για το Aspose.GIS for .NET;
Επισκεφθείτε το [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) για υποστήριξη και βοήθεια από την κοινότητα.

### Διατίθενται προσωρινές άδειες για το Aspose.GIS for .NET;
Ναι, μπορείτε να αποκτήσετε μια [temporary license](https://purchase.aspose.com/temporary-license/) για το Aspose.GIS for .NET.

---

**Τελευταία Ενημέρωση:** 2026-06-30  
**Δοκιμή με:** Aspose.GIS 24.11 for .NET  
**Συγγραφέας:** Aspose

## Σχετικά Μαθήματα

- [Δημιουργία File Geodatabase .NET Dataset με Aspose.GIS](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Δημιουργία Διανυσματικού Στρώματος και Ορισμός Συστήματος Χωρικής Αναφοράς Στρώματος](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Πώς να Διαγράψετε Στρώμα από File GDB Dataset με Aspose.GIS](/gis/net/layer-data-operations/remove-layers-from-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}