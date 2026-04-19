---
date: 2026-01-10
description: Μάθετε πώς να δημιουργήσετε διανυσματικό στρώμα σε μια Γεωβάση αρχείου
  χρησιμοποιώντας το Aspose.GIS για .NET. Διαχειριστείτε γεωχωρικά δεδομένα με αναφορά
  χώρου WGS84 και επιλογές αρχείου gdb.
linktitle: Create File GDB with Single Layer
second_title: Aspose.GIS .NET API
title: Δημιουργία διανυσματικού στρώματος σε αρχείο GDB – Οδηγός Aspose.GIS .NET
url: /el/net/layer-management/create-file-gdb-with-single-layer/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία Διανυσματικού Στρώματος σε File GDB

## Εισαγωγή
Αν χρειάζεστε **create vector layer** μέσα σε File Geodatabase (GDB) και θέλετε να διαχειρίζεστε γεωχωρικά δεδομένα αποδοτικά, το Aspose.GIS for .NET σας προσφέρει μια καθαρή, code‑first προσέγγιση. Σε αυτόν τον οδηγό βήμα‑βήμα θα σας δείξουμε πώς να γράψετε ένα χαρακτηριστικό γραμμής, να ρυθμίσετε τις επιλογές του file gdb και να εργαστείτε με την αναφορά χώρου WGS84 — όλα σε λίγες γραμμές C#. Στο τέλος θα μπορείτε να μετρήσετε τα χαρακτηριστικά σε ένα στρώμα και να ενσωματώσετε το παραγόμενο GDB σε οποιαδήποτε .NET ροή χαρτογράφησης ή ανάλυσης.

## Γρήγορες Απαντήσεις
- **Τι σημαίνει “create vector layer”;** Σημαίνει την προσθήκη ενός νέου διανυσματικού συνόλου δεδομένων (σημεία, γραμμές ή πολύγωνα) σε ένα αρχείο γεωβάσης.  
- **Ποια βιβλιοθήκη πρέπει να χρησιμοποιήσω;** Το Aspose.GIS for .NET παρέχει πλήρη υποστήριξη για δημιουργία και επεξεργασία File GDB.  
- **Χρειάζομαι άδεια για ανάπτυξη;** Μια δωρεάν δοκιμή λειτουργεί για δοκιμές· απαιτείται εμπορική άδεια για παραγωγή.  
- **Μπορώ να ορίσω την αναφορά χώρου;** Ναι – χρησιμοποιήστε `SpatialReferenceSystem.Wgs84` για το κοινό datum WGS84.  
- **Πόσες γραμμές κώδικα;** Λιγότερες από 30 γραμμές για τη δημιουργία του GDB, την προσθήκη ενός χαρακτηριστικού γραμμής και την ανάγνωση του αριθμού χαρακτηριστικών.

## Τι είναι η λειτουργία “create vector layer”;
Η δημιουργία διανυσματικού στρώματος σημαίνει τον ορισμό ενός νέου πίνακα μέσα σε μια γεωβάση που αποθηκεύει γεωμετρικά αντικείμενα (σημεία, γραμμές, πολύγωνα) μαζί με τα χαρακτηριστικά τους. Αυτή η λειτουργία αποτελεί τη βάση για οποιαδήποτε GIS‑εφαρμογή που χρειάζεται **διαχείριση γεωχωρικών δεδομένων**.

## Γιατί να χρησιμοποιήσετε το Aspose.GIS για τη δημιουργία διανυσματικού στρώματος;
- **Καμία εξωτερική εξάρτηση** – το API λειτουργεί αμέσως σε .NET Framework, .NET Core και .NET 5/6.  
- **Πλήρης υποστήριξη για File GDB** – μπορείτε να ρυθμίσετε `FileGdbOptions` για έλεγχο συμπίεσης, χωρικής ευρετηρίασης κ.λπ.  
- **Ενσωματωμένη διαχείριση αναφοράς χώρου** – απλώς περάστε `SpatialReferenceSystem.Wgs84` για εργασία στο παγκόσμιο σύστημα συντεταγμένων.  
- **Απλό API** – γράψτε χαρακτηριστικό γραμμής, προσθέστε το σε στρώμα και ανακτήστε τον αριθμό χαρακτηριστικών με λίγες κλήσεις μεθόδων.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

1. **Aspose.GIS for .NET** – κατεβάστε το από τη [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/).  
2. **Περιβάλλον ανάπτυξης .NET** – Visual Studio, Rider ή το `dotnet` CLI.  
3. **Φάκελο** όπου θα δημιουργηθεί το File GDB (θα τον ονομάσουμε *Your Document Directory*).

## Εισαγωγή Namespaces
Προσθέστε τις απαιτούμενες δηλώσεις `using` στην αρχή του αρχείου C#:

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

## Βήμα 1: Ρύθμιση του Καταλόγου Εγγράφων σας
```csharp
string dataDir = "Your Document Directory";
```
Αντικαταστήστε `"Your Document Directory"` με την απόλυτη διαδρομή όπου θέλετε να αποθηκευτεί το File GDB.

## Βήμα 2: Δημιουργία File Geodatabase με Ένα Στρώμα
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
Αυτό το απόσπασμα **creates a vector layer** χρησιμοποιώντας `FileGdbOptions`, γράφει ένα απλό χαρακτηριστικό γραμμής και το αποθηκεύει σε File GDB που χρησιμοποιεί την **αναφορά χώρου WGS84**.

## Βήμα 3: Άνοιγμα του File Geodatabase και Ανάκτηση Πληροφοριών Στρώματος
```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Output: Features count: 1
}
```
Εδώ **count features layer** ανοίγοντας το σύνολο δεδομένων και εκτυπώνοντας τον αριθμό χαρακτηριστικών – στην περίπτωση αυτή, `1`.

## Συχνά Προβλήματα και Λύσεις
| Πρόβλημα | Αιτία | Διόρθωση |
|----------|-------|----------|
| **`File not found`** | Λανθασμένη μεταβλητή `path` | Επαληθεύστε ότι το `dataDir` δείχνει σε υπάρχον φάκελο και ότι το `path` το συνδυάζει με όνομα αρχείου, π.χ., `Path.Combine(dataDir, "MyData.gdb")`. |
| **`Unsupported geometry`** | Χρήση τύπου γεωμετρίας που δεν επιτρέπεται σε File GDB | Περιοριστείτε σε `Point`, `LineString` ή `Polygon` για βασικά στρώματα. |
| **`License not set`** | Εκτέλεση χωρίς έγκυρη άδεια σε παραγωγή | Καταχωρίστε την άδειά σας με `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Συχνές Ερωτήσεις
### Μπορώ να χρησιμοποιήσω το Aspose.GIS for .NET στα υπάρχοντα .NET projects μου;
Ναι, το Aspose.GIS for .NET μπορεί να ενσωματωθεί άψογα στα υπάρχοντα .NET projects σας.

### Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.GIS for .NET;
Ναι, μπορείτε να εξερευνήσετε τις δυνατότητες του Aspose.GIS for .NET κατεβάζοντας τη [free trial version](https://releases.aspose.com/).

### Πού μπορώ να βρω λεπτομερή τεκμηρίωση για το Aspose.GIS for .NET;
Ανατρέξτε στην [documentation](https://reference.aspose.com/gis/net/) για πλήρεις πληροφορίες σχετικά με το Aspose.GIS for .NET.

### Πώς μπορώ να λάβω υποστήριξη για το Aspose.GIS for .NET;
Επισκεφθείτε το [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) για υποστήριξη από την κοινότητα και βοήθεια.

### Διατίθενται προσωρινές άδειες για το Aspose.GIS for .NET;
Ναι, μπορείτε να αποκτήσετε μια [temporary license](https://purchase.aspose.com/temporary-license/) για το Aspose.GIS for .NET.

---

**Τελευταία ενημέρωση:** 2026-01-10  
**Δοκιμή με:** Aspose.GIS 24.11 for .NET  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}