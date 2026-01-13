---
date: 2026-01-13
description: Μάθετε πώς να προσθέσετε ένα επίπεδο σε ένα σύνολο δεδομένων File GDB
  χρησιμοποιώντας το Aspose.GIS, με υποστήριξη χωρικής αναφοράς WGS84. Ακολουθήστε
  αυτόν τον οδηγό βήμα‑βήμα για να προσθέσετε επίπεδο στο GDB σε .NET.
linktitle: Add Layer to File GDB Dataset
second_title: Aspose.GIS .NET API
title: χωρική αναφορά wgs84 – Προσθήκη στρώματος σε GDB χρησιμοποιώντας το Aspose.GIS
url: /el/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# spatial reference wgs84 – Προσθήκη Layer σε GDB χρησιμοποιώντας Aspose.GIS

## Εισαγωγή
Έτοιμοι να ενισχύσετε τη ροή εργασίας GIS με το Aspose.GIS για .NET; Σε αυτό το tutorial θα μάθετε **πώς να προσθέσετε ένα layer σε ένα File GDB dataset** ενώ εργάζεστε με το **spatial reference wgs84** σύστημα συντεταγμένων. Θα περάσουμε βήμα‑βήμα από την προετοιμασία του φακέλου δεδομένων μέχρι την επικύρωση του νέου layer, ώστε να μπορείτε να χειρίζεστε γεωγραφικά δεδομένα με σιγουριά.

## Γρήγορες Απαντήσεις
- **Ποιο είναι το κύριο σύστημα συντεταγμένων που χρησιμοποιείται;** spatial reference wgs84 (WGS 84)  
- **Ποια βιβλιοθήκη παρέχει το API;** Aspose.GIS for .NET  
- **Χρειάζομαι άδεια για δοκιμές;** Ναι – υπάρχει προσωρινή άδεια Aspose.  
- **Μπορώ να προσθέσω ιδιότητες στο νέο layer;** Απόλυτα, μπορείτε να ορίσετε οποιονδήποτε αριθμό ιδιοτήτων χαρακτηριστικών.  
- **Ποιες εκδόσεις .NET υποστηρίζονται;** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## Τι είναι το spatial reference wgs84;
Το spatial reference wgs84 (World Geodetic System 1984) είναι το πιο ευρέως χρησιμοποιούμενο γεωγραφικό σύστημα συντεταγμένων. Ορίζει το πλάτος και το μήκος σε μοίρες και λειτουργεί ως προεπιλεγμένο CRS για πολλά GIS datasets, συμπεριλαμβανομένου του που θα δημιουργήσουμε σε αυτόν τον οδηγό.

## Γιατί να χρησιμοποιήσετε Aspose.GIS για την προσθήκη layer;
- **Χωρίς εξωτερικές εξαρτήσεις:** Λειτουργεί αμέσως με καθαρό κώδικα .NET.  
- **Πλήρης έλεγχος σχήματος:** Μπορείτε να ορίσετε προσαρμοσμένες ιδιότητες και τύπους γεωμετρίας.  
- **Διασυστημικό:** Συμβατό με Windows, Linux και macOS.  
- **Αξιόπιστη άδεια:** Οι προσωρινές άδειες επιτρέπουν γρήγορη αξιολόγηση πριν από τη δέσμευση.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

- Aspose.GIS for .NET Library: Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη από την [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/).  
- Κατάλογος Εγγράφων: Δημιουργήστε έναν αφιερωμένο φάκελο στον υπολογιστή σας για την αποθήκευση αρχείων GIS.

## Εισαγωγή Namespaces
Προσθέστε τις απαιτούμενες δηλώσεις `using` στο έργο C# ώστε να έχετε πρόσβαση στις κλάσεις Aspose.GIS:

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

## Βήμα 1: Αντιγραφή Καταλόγου
Αρχικά, αντιγράψτε τον φάκελο που περιέχει το αρχικό GDB dataset. Η δημιουργία αντιγράφου προστατεύει τα αρχικά δεδομένα ενώ πειραματίζεστε.

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Βήμα 2: Άνοιγμα Dataset και Επαλήθευση Δυνατότητας Δημιουργίας Layer
Ανοίξτε το νέο αντίγραφο του dataset και επιβεβαιώστε ότι μπορεί να δημιουργήσει νέα layers. Η ιδιότητα `CanCreateLayers` θα πρέπει να επιστρέφει **True**.

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Βήμα 3: Δημιουργία και Συμπλήρωση Νέου Layer με spatial reference wgs84
Τώρα δημιουργούμε ένα layer με όνομα **data** και ορίζουμε ρητά το spatial reference του σε **Wgs84**. Προσθέτουμε επίσης μια απλή ιδιότητα **Name** και εισάγουμε ένα σημειακό χαρακτηριστικό.

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

## Βήμα 4: Άνοιγμα και Επικύρωση του Προστιθέμενου Layer
Τέλος, ανοίξτε το layer που μόλις δημιουργήσατε και επαληθεύστε τα περιεχόμενά του. Η κονσόλα θα εμφανίσει ότι το layer περιέχει ένα χαρακτηριστικό και ότι η ιδιότητα **Name** ταιριάζει με αυτή που ορίσαμε.

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Συνηθισμένα Προβλήματα & Συμβουλές
- **Λάθος διαδρομή:** Βεβαιωθείτε ότι το `dataDir` λήγει με διαχωριστικό διαδρομής (`/` ή `\`) ώστε οι συνενωμένες συμβολοσειρές να σχηματίζουν έγκυρες διαδρομές αρχείων.  
- **Σφάλματα άδειας:** Αν εμφανιστούν προειδοποιήσεις άδειας, εφαρμόστε μια προσωρινή άδεια από το portal του Aspose πριν τρέξετε τον κώδικα.  
- **Ασυμφωνία CRS:** Όταν ανοίγετε το layer αργότερα σε άλλο GIS εργαλείο, βεβαιωθείτε ότι το εργαλείο αναγνωρίζει το WGS 84 (EPSG:4326) ως σύστημα συντεταγμένων.

## Συχνές Ερωτήσεις
### Ε: Μπορώ να χρησιμοποιήσω το Aspose.GIS για .NET μαζί με άλλες βιβλιοθήκες GIS;
Το Aspose.GIS for .NET σχεδιάστηκε για ανεξάρτητη λειτουργία, αλλά μπορεί να ενσωματωθεί με άλλες βιβλιοθήκες για ενισχυμένη λειτουργικότητα.  

### Ε: Διατίθεται προσωρινή άδεια για δοκιμαστικούς σκοπούς;
Ναι, μπορείτε να αποκτήσετε μια προσωρινή άδεια από [εδώ](https://purchase.aspose.com/temporary-license/) για δοκιμές και αξιολόγηση.  

### Ε: Ποια συστήματα spatial reference υποστηρίζει το Aspose.GIS for .NET;
Το Aspose.GIS for .NET υποστηρίζει ένα ευρύ φάσμα συστημάτων spatial reference, προσφέροντας ευελιξία στη διαχείριση γεωγραφικών δεδομένων.  

### Ε: Μπορώ να συνεισφέρω στην κοινότητα Aspose.GIS;
Απόλυτα! Συμμετέχετε στις συζητήσεις και μοιραστείτε τις εμπειρίες σας στο [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).  

### Ε: Πού μπορώ να βρω λεπτομερή τεκμηρίωση για το Aspose.GIS for .NET;
Εξερευνήστε την πλήρη τεκμηρίωση [εδώ](https://reference.aspose.com/gis/net/) για εκτενείς πληροφορίες σχετικά με το Aspose.GIS for .NET.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Τελευταία Ενημέρωση:** 2026-01-13  
**Δοκιμάστηκε Με:** Aspose.GIS for .NET (τελευταία σταθερή έκδοση)  
**Συγγραφέας:** Aspose