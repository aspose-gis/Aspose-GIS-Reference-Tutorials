---
date: 2026-08-30
description: Μάθετε πώς να διαβάζετε shapefile C# και να φιλτράρετε τα χαρακτηριστικά
  κατά ημερομηνία χρησιμοποιώντας το Aspose.GIS για .NET. Οδηγός βήμα‑βήμα για αποδοτικό
  φιλτράρισμα ιδιοτήτων shapefile.
keywords:
- read shapefile c#
- filter shapefile attribute
- iterate gis features
lastmod: 2026-08-30
linktitle: Ανάγνωση Shapefile C# – Φιλτράρισμα Χαρακτηριστικών κατά Ιδιότητα
og_description: Ανάγνωση shapefile c# και φιλτράρισμα χαρακτηριστικών κατά ημερομηνία
  με Aspose.GIS για .NET. Αυτός ο οδηγός σας δείχνει πώς να φορτώσετε ένα shapefile,
  να εφαρμόσετε φίλτρα ιδιοτήτων και να επεξεργαστείτε τα GIS χαρακτηριστικά αποδοτικά.
og_image_alt: Screenshot of Aspose.GIS code filtering shapefile attributes in C#
og_title: Ανάγνωση shapefile c# – φιλτράρισμα χαρακτηριστικών με Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-08-30'
  description: Learn how to read shapefile C# and filter features by date using Aspose.GIS
    for .NET. Step‑by‑step guide to filter shapefile attribute efficiently.
  headline: Read shapefile c# – filter attributes with Aspose.GIS
  type: TechArticle
- questions:
  - answer: Reading a shapefile in C# and filtering features by a date attribute.
    question: What does this tutorial cover?
  - answer: Aspose.GIS for .NET.
    question: Which library is used?
  - answer: Less than 20 lines for the core filtering logic.
    question: How many lines of code?
  - answer: A free trial works for development; a license is required for production.
    question: Do I need a license?
  - answer: .NET Framework, .NET Core, and .NET 5/6+.
    question: Supported platforms?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- shapefile
- Aspose.GIS
- .NET GIS processing
title: Ανάγνωση shapefile c# – φιλτράρισμα χαρακτηριστικών με Aspose.GIS
url: /el/net/layer-management/filter-features-by-attribute/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ανάγνωση shapefile c# – φιλτράρισμα χαρακτηριστικών με Aspose.GIS

## Εισαγωγή
Αν χρειάζεστε **read shapefile c#** και θέλετε γρήγορα να απομονώσετε εγγραφές που ταιριάζουν σε συγκεκριμένα κριτήρια, το Aspose.GIS for .NET σας προσφέρει ένα καθαρό, ευανάγνωστο API. Σε αυτό το tutorial θα δούμε πώς να φορτώσουμε ένα Shapefile, **filtering features by date**, και να εξάγουμε τιμές χαρακτηριστικών — ιδανικό για όποιον θέλει **filter shapefile attribute** δεδομένα ή **iterate GIS features** σε εφαρμογή .NET.

## Γρήγορες απαντήσεις
- **Τι καλύπτει αυτό το tutorial;** Ανάγνωση shapefile σε C# και φιλτράρισμα χαρακτηριστικών με βάση ένα πεδίο ημερομηνίας.  
- **Ποια βιβλιοθήκη χρησιμοποιείται;** Aspose.GIS for .NET.  
- **Πόσες γραμμές κώδικα;** Λιγότερες από 20 γραμμές για τη βασική λογική φιλτραρίσματος.  
- **Χρειάζεται άδεια;** Μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη· απαιτείται άδεια για παραγωγή.  
- **Υποστηριζόμενες πλατφόρμες;** .NET Framework, .NET Core, και .NET 5/6+.

## Τι είναι το “read shapefile c#”;
Η ανάγνωση shapefile σε C# σημαίνει φόρτωση των διανυσματικών δεδομένων που αποθηκεύονται στο αρχείο *.shp* (και στα συνοδευτικά του αρχεία) στη μνήμη ώστε να μπορείτε να τα ερωτήσετε, να τα επεξεργαστείτε ή να τα εξάγετε προγραμματιστικά. Το Aspose.GIS αφαιρεί τις λεπτομέρειες της μορφής αρχείου, επιτρέποντάς σας να εστιάσετε στη χωρική λογική.

## Πώς να διαβάσετε shapefile c#;
Φορτώστε το αρχείο με `VectorLayer.Open` και αφήστε το Aspose.GIS να διαχειριστεί την υποκείμενη δυαδική ανάλυση. Η βιβλιοθήκη διαβάζει μόνο τις απαιτούμενες εγγραφές, πράγμα που σημαίνει ότι αποφεύγετε τη φόρτωση ολόκληρου του συνόλου δεδομένων στη μνήμη — ένα κρίσιμο όφελος όταν εργάζεστε με shapefiles πολλών εκατοντάδων σελίδων.

## Γιατί να φιλτράρετε χαρακτηριστικά shapefile κατά ημερομηνία με Aspose.GIS;
Το Aspose.GIS σπρώχνει το φίλτρο προς την πηγή δεδομένων, έτσι σαρώνει μόνο τις αντίστοιχες γραμμές. Αυτή η προσέγγιση είναι έως **10× πιο γρήγορη** από το να επαναλαμβάνετε κάθε χαρακτηριστικό σε μεγάλα σύνολα δεδομένων. Οι μεθόδοι τύπου LINQ όπως `WhereGreater` κάνουν τον κώδικα αυτοεξηγηματικό, και μπορείτε να συνδυάσετε φίλτρα ημερομηνίας με οποιαδήποτε άλλα φίλτρα χαρακτηριστικών για σύνθετες χωρικές αναλύσεις.

## Προαπαιτούμενα
Πριν βυθιστείτε στα πρακτικά παραδείγματα, βεβαιωθείτε ότι έχετε:

- **Εγκατάσταση Aspose.GIS** – Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη Aspose.GIS από το [download link](https://releases.aspose.com/gis/net/).  
- **Περιβάλλον ανάπτυξης** – Ένα IDE .NET (Visual Studio, Rider ή VS Code) ρυθμισμένο στον υπολογιστή σας.  
- **Χωρικά δεδομένα** – Ένα shapefile εισόδου (π.χ. **InputShapeFile.shp**) που περιέχει ένα χαρακτηριστικό **dob** (ημερομηνία γέννησης) που θέλετε να φιλτράρετε.  
- **Βασικές γνώσεις C#** – Εξοικείωση με τη σύνταξη C# και τη δομή έργου .NET.

## Εισαγωγή ονομάτων χώρου
`Aspose.Gis` παρέχει τους βασικούς τύπους GIS, ενώ το `System.IO` βοηθά στη διαχείριση διαδρομών.

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Βήμα 1: ορισμός καταλόγου εγγράφου
Ορίστε το φάκελο που περιέχει το shapefile σας. Αντικαταστήστε το placeholder με την πραγματική διαδρομή στον υπολογιστή σας.

```csharp
string dataDir = "Your Document Directory";
```

## Βήμα 2: άνοιγμα του διανυσματικού επιπέδου
Χρησιμοποιήστε το Aspose.GIS για να ανοίξετε το shapefile ως διανυσματικό επίπεδο. Αυτό το βήμα **reads the shapefile c#** και το προετοιμάζει για ερωτήματα.

Το `VectorLayer.Open` φορτώνει ένα διανυσματικό σύνολο δεδομένων από αρχείο και επιστρέφει ένα αντικείμενο `VectorLayer`.

```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
```

## Βήμα 3: επανάληψη χαρακτηριστικών GIS και φιλτράρισμα κατά ημερομηνία
Τώρα **iterate GIS features** και εφαρμόζουμε μια συνθήκη **filter features by date** στο χαρακτηριστικό **dob**. Μόνο οι εγγραφές με ημερομηνία γέννησης μετά την 1 Ιανουαρίου 1982 θα εκτυπωθούν.

`WhereGreater` φιλτράρει χαρακτηριστικά όπου η τιμή ενός συγκεκριμένου χαρακτηριστικού είναι μεγαλύτερη από την δοσμένη τιμή.

```csharp
foreach (Feature feature in layer.WhereGreater("dob", new DateTime(1982, 1, 1, 0, 0, 0)))
{
    Console.WriteLine(feature.GetValue<DateTime>("dob").ToShortDateString());
}
```

Το απόσπασμα δείχνει έναν σύντομο τρόπο για **filter shapefile attribute** δεδομένα χωρίς να φορτώνετε ολόκληρο το σύνολο δεδομένων στη μνήμη.

## Συνηθισμένα προβλήματα & συμβουλές
- **Ασυμφωνία μορφής ημερομηνίας:** Βεβαιωθείτε ότι το πεδίο **dob** στο shapefile είναι αποθηκευμένο ως τύπος ημερομηνίας· διαφορετικά η μετατροπή μπορεί να αποτύχει.  
- **Σφάλματα διαδρομής:** Χρησιμοποιήστε `Path.Combine(dataDir, "InputShapeFile.shp")` για να αποφύγετε ελλείψεις διαχωριστών διαδρομής σε διαφορετικά λειτουργικά συστήματα.  
- **Απόδοση:** Για πολύ μεγάλα shapefiles, εξετάστε το ενδεχόμενο να εφαρμόσετε επιπλέον φίλτρα χαρακτηριστικών ώστε να μειώσετε το σύνολο αποτελεσμάτων νωρίς.

## Συχνές ερωτήσεις
### Είναι το Aspose.GIS συμβατό με όλα τα GIS φορμά;
Το Aspose.GIS υποστηρίζει 30+ μορφές GIS — συμπεριλαμβανομένων Shapefile, GeoJSON, KML και GML — επιτρέποντάς σας να διαβάζετε και να γράφετε σε ένα ευρύ οικοσύστημα. Δείτε την [documentation](https://reference.aspose.com/gis/net/) για την πλήρη λίστα.

### Μπορώ να δοκιμάσω το Aspose.GIS πριν το αγοράσω;
Ναι, μπορείτε να εξερευνήσετε μια δωρεάν δοκιμή του Aspose.GIS επισκεπτόμενοι τη σελίδα δοκιμής Aspose.GIS: [Aspose.GIS trial page](https://releases.aspose.com/).

### Πού μπορώ να βρω υποστήριξη για το Aspose.GIS;
Για οποιεσδήποτε ερωτήσεις ή βοήθεια, επισκεφθείτε το [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).

### Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.GIS;
Αποκτήστε μια προσωρινή άδεια από τη σελίδα προσωρινών αδειών Aspose: [temporary license page](https://purchase.aspose.com/temporary-license/).

### Υπάρχει βήμα‑βήμα tutorial για άλλα χαρακτηριστικά του Aspose.GIS;
Ναι, μπορείτε να βρείτε περισσότερα tutorials και τεκμηρίωση στο [Aspose.GIS reference](https://reference.aspose.com/gis/net/).

---

**Last Updated:** 2026-08-30  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose

## Σχετικά Tutorials

- [Learn to Retrieve and Update Layer Attributes with Aspose.GIS for .NET](/gis/net/layer-interaction-and-data-access/)
- [Get All Feature Attribute Values from a Shapefile in C# using Aspose.GIS for .NET](/gis/net/layer-interaction-and-data-access/get-all-feature-attribute-values/)
- [Create New Shapefile and Modify Layer Features – Aspose.GIS](/gis/net/layer-interaction-and-data-access/modify-layer-features/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}