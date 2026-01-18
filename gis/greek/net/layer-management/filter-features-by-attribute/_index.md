---
date: 2026-01-18
description: Μάθετε πώς να διαβάζετε shapefile σε C# και να φιλτράρετε τα χαρακτηριστικά
  κατά ημερομηνία χρησιμοποιώντας το Aspose.GIS για .NET. Οδηγός βήμα‑βήμα για την
  αποτελεσματική φιλτράριση των ιδιοτήτων του shapefile.
linktitle: Read Shapefile C# – Filter Features by Attribute
second_title: Aspose.GIS .NET API
title: Ανάγνωση Shapefile C# – Φιλτράρισμα χαρακτηριστικών βάσει ιδιότητας με το Aspose.GIS
url: /el/net/layer-management/filter-features-by-attribute/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ανάγνωση Shapefile C# – Φιλτράρισμα Χαρακτηριστικών κατά Attribute με Aspose.GIS

## Εισαγωγή
Αν χρειάζεστε **read shapefile C#** και θέλετε γρήγορα να απομονώσετε εγγραφές που ταιριάζουν σε συγκεκριμένα κριτήρια, το Aspose.GIS for .NET σας παρέχει ένα καθαρό, ευέλικτο API. Σε αυτό το tutorial θα δούμε πώς να φορτώσουμε ένα Shapefile, **filtering features by date**, και να εξάγουμε τιμές attribute — ιδανικό για όποιον θέλει να **filter shapefile attribute** δεδομένα ή **iterate GIS features** σε μια εφαρμογή .NET.

## Γρήγορες Απαντήσεις
- **Τι καλύπτει αυτό το tutorial;** Reading a shapefile in C# and filtering features by a date attribute.  
- **Ποια βιβλιοθήκη χρησιμοποιείται;** Aspose.GIS for .NET.  
- **Πόσες γραμμές κώδικα;** Λιγότερες από 20 γραμμές για τη βασική λογική φιλτραρίσματος.  
- **Χρειάζομαι άδεια;** Μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη· απαιτείται άδεια για παραγωγή.  
- **Υποστηριζόμενες πλατφόρμες;** .NET Framework, .NET Core, και .NET 5/6+.

## Τι είναι το “read shapefile C#”;
Η ανάγνωση ενός shapefile σε C# σημαίνει τη φόρτωση των διανυσματικών δεδομένων που αποθηκεύονται στο αρχείο *.shp* (και στα συνοδευτικά του αρχεία) στη μνήμη, ώστε να μπορείτε να τα ερωτήσετε, να τα επεξεργαστείτε ή να τα εξάγετε προγραμματιστικά. Το Aspose.GIS αφαιρεί τις λεπτομέρειες της μορφής αρχείου, επιτρέποντάς σας να εστιάσετε στη χωρική λογική.

## Γιατί να φιλτράρετε χαρακτηριστικά κατά ημερομηνία με το Aspose.GIS;
- **Απόδοση:** Η βιβλιοθήκη εφαρμόζει το φίλτρο απευθείας στην πηγή δεδομένων, αποφεύγοντας πλήρεις σαρώσεις.  
- **Απλότητα:** Μεθόδους σε στυλ Fluent LINQ όπως `WhereGreater` κάνουν τον κώδικα αυτοεξηγηματικό.  
- **Ευελιξία:** Μπορείτε να συνδυάσετε φίλτρα ημερομηνίας με οποιαδήποτε άλλα φίλτρα attribute, επιτρέποντας ισχυρές αναλύσεις GIS.

## Προαπαιτούμενα
- Εγκατάσταση Aspose.GIS: Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη Aspose.GIS από το [download link](https://releases.aspose.com/gis/net/).  
- Περιβάλλον Ανάπτυξης: Ένα .NET IDE (Visual Studio, Rider ή VS Code) εγκατεστημένο στον υπολογιστή σας.  
- Δεδομένα Χώρου: Ένα shapefile εισόδου (π.χ., **InputShapeFile.shp**) που περιέχει ένα attribute **dob** (ημερομηνία γέννησης) που θέλετε να φιλτράρετε.  
- Βασικές Γνώσεις C#: Εξοικείωση με τη σύνταξη C# και τη δομή έργου .NET.

## Εισαγωγή Namespaces
Στο αρχείο πηγαίου κώδικα C#, εισάγετε τα namespaces που απαιτούνται για λειτουργίες GIS:

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Βήμα 1: Ορισμός Καταλόγου Εγγράφου
Ορίστε το φάκελο που περιέχει το shapefile σας. Αντικαταστήστε το placeholder με την πραγματική διαδρομή στον υπολογιστή σας.

```csharp
string dataDir = "Your Document Directory";
```

## Βήμα 2: Άνοιγμα του Vector Layer
Χρησιμοποιήστε το Aspose.GIS για να ανοίξετε το shapefile ως vector layer. Αυτό το βήμα **reads the shapefile C#** και το προετοιμάζει για ερωτήματα.

```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
```

## Βήμα 3: Επανάληψη GIS Features και Φιλτράρισμα κατά Ημερομηνία
Τώρα **iterate GIS features** και εφαρμόζουμε μια συνθήκη **filter features by date** στο attribute **dob**. Μόνο οι εγγραφές με ημερομηνία γέννησης μετά την 1 Ιανουαρίου 1982 θα εκτυπωθούν.

```csharp
foreach (Feature feature in layer.WhereGreater("dob", new DateTime(1982, 1, 1, 0, 0, 0)))
{
    Console.WriteLine(feature.GetValue<DateTime>("dob").ToShortDateString());
}
```

Το απόσπασμα δείχνει έναν σύντομο τρόπο για **filter shapefile attribute** δεδομένα χωρίς να φορτώνετε ολόκληρο το σύνολο δεδομένων στη μνήμη.

## Συχνά Προβλήματα & Συμβουλές
- **Ασυμφωνία μορφής ημερομηνίας:** Βεβαιωθείτε ότι το πεδίο **dob** στο shapefile είναι αποθηκευμένο ως τύπος ημερομηνίας· διαφορετικά, η μετατροπή μπορεί να αποτύχει.  
- **Σφάλματα διαδρομής:** Χρησιμοποιήστε `Path.Combine(dataDir, "InputShapeFile.shp")` για να αποφύγετε ελλείψεις διαχωριστών διαδρομής σε διαφορετικά λειτουργικά συστήματα.  
- **Απόδοση:** Για πολύ μεγάλα shapefiles, σκεφτείτε να εφαρμόσετε επιπλέον φίλτρα attribute για να μειώσετε το σύνολο αποτελεσμάτων νωρίς.

## Συμπέρασμα
Το Aspose.GIS for .NET καθιστά απλό το **read shapefile C#**, **filter features by date**, και **iterate GIS features** αποδοτικά. Με μόνο μερικές γραμμές κώδικα μπορείτε να ανοίξετε ισχυρά χωρικά ερωτήματα, θέτοντας τη βάση για πιο προχωρημένες αναλύσεις GIS.

## Συχνές Ερωτήσεις
### Είναι το Aspose.GIS συμβατό με όλες τις μορφές αρχείων GIS;
Το Aspose.GIS υποστηρίζει διάφορες μορφές αρχείων GIS, συμπεριλαμβανομένων Shapefile, GeoJSON και KML. Ελέγξτε την [documentation](https://reference.aspose.com/gis/net/) για μια πλήρη λίστα.

### Μπορώ να δοκιμάσω το Aspose.GIS πριν την αγορά;
Ναι, μπορείτε να εξερευνήσετε μια δωρεάν δοκιμή του Aspose.GIS επισκεπτόμενοι [here](https://releases.aspose.com/).

### Πού μπορώ να βρω υποστήριξη για το Aspose.GIS;
Για οποιεσδήποτε ερωτήσεις ή βοήθεια, επισκεφθείτε το [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).

### Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.GIS;
Αποκτήστε προσωρινή άδεια [here](https://purchase.aspose.com/temporary-license/).

### Υπάρχει tutorial βήμα‑βήμα για άλλα χαρακτηριστικά του Aspose.GIS;
Ναι, μπορείτε να βρείτε περισσότερα tutorials και τεκμηρίωση στο [Aspose.GIS reference](https://reference.aspose.com/gis/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Τελευταία ενημέρωση:** 2026‑01‑18  
**Δοκιμή με:** Aspose.GIS for .NET (τελευταία έκδοση)  
**Συγγραφέας:** Aspose