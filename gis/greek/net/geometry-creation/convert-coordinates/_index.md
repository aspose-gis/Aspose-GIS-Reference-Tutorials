---
date: 2026-08-18
description: Μετατρέψτε decimal degrees σε dms χρησιμοποιώντας το Aspose.GIS για .NET.
  Αυτός ο οδηγός C# βήμα‑βήμα δείχνει πώς να μετατρέψετε latitude/longitude, decimal
  degrees σε dms και άλλα.
keywords:
- decimal degrees to dms
- convert coordinates dms
- gis coordinate conversion
- convert lat long dms
- c# convert lat long
lastmod: 2026-08-18
linktitle: Μετατροπή Συντεταγμένων
og_description: Η μετατροπή decimal degrees σε dms γίνεται εύκολα με το Aspose.GIS
  για .NET. Μάθετε πώς να μετατρέψετε τιμές latitude‑longitude σε μορφή DMS σε minutes.
og_image_alt: Guide showing decimal degrees to DMS conversion using Aspose.GIS in
  C#
og_title: Πώς να μετατρέψετε decimal degrees σε dms με το Aspose.GIS για .NET
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
title: Πώς να μετατρέψετε decimal degrees σε dms με το Aspose.GIS για .NET
url: /el/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να μετατρέψετε δεκαδικές μοίρες σε dms με το Aspose.GIS

## Εισαγωγή
Σε αυτό το tutorial θα μάθετε **πώς να μετατρέψετε δεκαδικές μοίρες σε dms** χρησιμοποιώντας τη δυνατή βιβλιοθήκη Aspose.GIS για .NET. Είτε χρειάζεστε **c# convert lat long**, είτε θέλετε να δημιουργήσετε αναγνώσιμες αλφαριθμητικές τοποθεσίες για αναφορές, είτε απλώς να εξερευνήσετε διαφορετικές μορφές συντεταγμένων, αυτός ο οδηγός σας καθοδηγεί βήμα προς βήμα με σαφείς εξηγήσεις και έτοιμα αποσπάσματα C#.

## Γρήγορες απαντήσεις
- **Τι σημαίνει “convert coordinates to dms”;** Μετατρέπει αριθμητικές τιμές γεωγραφικού πλάτους/μήκους σε παραδοσιακή σημειολογία μοίρες‑λεπτά‑δευτερόλεπτα.  
- **Ποια βιβλιοθήκη διαχειρίζεται τη μετατροπή;** Aspose.GIS for .NET παρέχει την κλάση `GeoConvert` με ενσωματωμένη υποστήριξη μορφών.  
- **Χρειάζομαι άδεια για να το δοκιμάσω;** Διατίθεται δωρεάν δοκιμή· απαιτείται εμπορική άδεια για παραγωγική χρήση.  
- **Ποιες εκδόσεις .NET υποστηρίζονται;** .NET Framework 4.5+, .NET Core 3.1+, και .NET 5/6+.  
- **Μπορώ να χρησιμοποιήσω τον ίδιο κώδικα για άλλες μορφές;** Ναι—απλώς αλλάξτε την τιμή του enum `PointFormats` (π.χ., `DecimalDegrees`, `GeoRef`).  

## Τι είναι η μετατροπή συντεταγμένων σε dms;
Η μετατροπή συντεταγμένων σε DMS μετατρέπει τις δεκαδικές τιμές γεωγραφικού πλάτους και μήκους σε μορφή όπως `25°30'00"N 45°30'00"E`. Η διαδικασία χωρίζει κάθε δεκαδική μοίρα σε ολόκληρες μοίρες, λεπτά (ένα εξήντα του βαθμού) και δευτερόλεπτα (ένα εξήντα του λεπτού), προσθέτοντας στη συνέχεια τον κατάλληλο δείκτη ημισφαίριου (N, S, E, W). Αυτή η αναγνώσιμη μορφή είναι απαραίτητη για πολλά παλαιά σύνολα δεδομένων και για την επικοινωνία ακριβών τοποθεσιών χωρίς τη χρήση δεκαδικής σημειολογίας.

## Γιατί να χρησιμοποιήσετε το Aspose.GIS για μετατροπή συντεταγμένων;
Το Aspose.GIS υποστηρίζει **πάνω από 50 μορφές εισόδου και εξόδου** και μπορεί να επεξεργαστεί αρχεία GIS πολλαπλών εκατοντάδων σελίδων χωρίς να φορτώνει ολόκληρο το σύνολο δεδομένων στη μνήμη. Το API παρέχει υπο‑χιλιοσυνολική ακρίβεια για ακραίες περιπτώσεις όπως αρνητικές τιμές και δείκτες ημισφαιρίων, και λειτουργεί σταθερά σε Windows, Linux και macOS .NET runtime.

## Προαπαιτούμενα
1. **Βασικές γνώσεις C#** – εξοικείωση με μεταβλητές, κλήσεις μεθόδων και έξοδο κονσόλας.  
2. **Εγκατεστημένο Aspose.GIS** – κατεβάστε το πιο πρόσφατο πακέτο από το [Aspose.GIS website](https://releases.aspose.com/gis/net/). Μπορείτε επίσης να εξερευνήσετε την κύρια σελίδα κυκλοφορίας του Aspose στο [Aspose releases website](https://releases.aspose.com/).  

## Εισαγωγή ονομάτων χώρων
First, import the namespaces required for GIS operations:

Import Namespaces placeholder remains unchanged.

## Οδηγός βήμα‑βήμα

### Τι είναι η κλάση GeoConvert;
Η κλάση `GeoConvert` παρέχει στατικές μεθόδους για μετατροπή μεταξύ μορφών συντεταγμένων όπως δεκαδικές μοίρες, DMS και GeoRef. Περιλαμβάνει υπερφορτώσεις που δέχονται ακατέργαστες αριθμητικές τιμές ή αντικείμενα `Point` και επιστρέφουν μορφοποιημένες συμβολοσειρές ή νέες παρουσίες `Point`. Με την αντιμετώπιση ακραίων περιπτώσεων όπως αρνητικές συντεταγμένες και στρογγυλοποίηση, η κλάση εγγυάται ότι η έξοδος συμμορφώνεται με τα πρότυπα GIS, απλοποιώντας την ενσωμάτωση σε οποιαδήποτε .NET εφαρμογή χαρτογράφησης.

### Βήμα 1: ξεκινήστε τη διαδικασία μετατροπής
Εκτυπώνουμε ένα φιλικό μήνυμα ώστε να γνωρίζετε ότι η παρουσίαση έχει ξεκινήσει.

```csharp
using System;
using Aspose.Gis;
```

### Βήμα 2: μετατροπή σε δεκαδικές μοίρες
Αν και ο τελικός στόχος είναι το DMS, ξεκινάμε εμφανίζοντας την αρχική δεκαδική αναπαράσταση. Αυτό επίσης δείχνει τη διαδρομή **decimal degrees to dms** που θα ακολουθήσετε αργότερα.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### Βήμα 3: μετατροπή σε μοίρες δεκαδικά λεπτά
Αυτή η μορφή (`DD°MM.m'`) είναι ένα κοινό ενδιάμεσο βήμα όταν χρειάζεται να **convert lat long degree minutes**.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Βήμα 4: μετατροπή σε μοίρες λεπτά δευτερόλεπτα (dms)
Αυτή είναι η καρδιά του tutorial μας—**convert coordinates to dms**.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Βήμα 5: μετατροπή σε GeoRef
Για πληρότητα, δείχνουμε επίσης τη μορφή `GeoRef`, χρήσιμη σε ροές εργασίας απομακρυσμένης ανίχνευσης.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

## Συχνά προβλήματα και λύσεις
- **Λανθασμένα γράμματα ημισφαιρίου** – Βεβαιωθείτε ότι περνάτε θετικές τιμές για βορρά/ανατολή και αρνητικές για νότο/δυτικά· το API προσθέτει αυτόματα το σωστό επίθημα.  
- **Απρόσμενη κενή έξοδος** – Επαληθεύστε ότι η συναρμολόγηση `Aspose.Gis` αναφέρεται σωστά και ότι το έργο στοχεύει σε υποστηριζόμενη έκδοση .NET.  
- **Άδεια δεν βρέθηκε** – Τοποθετήστε το αρχείο άδειας στη ρίζα της εφαρμογής ή ορίστε το προγραμματιστικά με `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.

## Συχνές ερωτήσεις

**Q: Είναι το Aspose.GIS συμβατό με άλλες γλώσσες προγραμματισμού;**  
A: Το Aspose.GIS στοχεύει κυρίως προγραμματιστές .NET, αλλά υπάρχει επίσης έκδοση για Java.

**Q: Μπορώ να δοκιμάσω το Aspose.GIS πριν το αγοράσω;**  
A: Ναι, μπορείτε να αποκτήσετε δωρεάν δοκιμή του Aspose.GIS από το [website](https://releases.aspose.com/).

**Q: Πώς μπορώ να λάβω υποστήριξη για το Aspose.GIS;**  
A: Μπορείτε να ζητήσετε βοήθεια από το φόρουμ κοινότητας Aspose.GIS [εδώ](https://forum.aspose.com/c/gis/33).

**Q: Διατίθενται προσωρινές άδειες για το Aspose.GIS;**  
A: Ναι, οι προσωρινές άδειες μπορούν να ληφθούν από τη [temporary license page](https://purchase.aspose.com/temporary-license/).

**Q: Πού μπορώ να αγοράσω το Aspose.GIS;**  
A: Μπορείτε να αγοράσετε το Aspose.GIS από τη [purchase page](https://purchase.aspose.com/buy).

## Συμπέρασμα
Ακολουθώντας αυτά τα βήματα, τώρα γνωρίζετε πώς να **convert decimal degrees to dms** και άλλες κοινές μορφές GIS χρησιμοποιώντας το Aspose.GIS για .NET. Αυτή η δυνατότητα σας επιτρέπει να ενσωματώσετε άψογα αναγνώσιμες αλφαριθμητικές τοποθεσίες σε εφαρμογές χαρτογράφησης, αναφορές ή οποιαδήποτε ροή εργασίας χωρικών δεδομένων. Μη διστάσετε να πειραματιστείτε με διαφορετικές τιμές γεωγραφικού πλάτους/μήκους και να εξερευνήσετε τις άλλες μορφές που προσφέρει η κλάση `GeoConvert`.

---

**Last Updated:** 2026-08-18  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## Σχετικά μαθήματα

- [How to Create Point Geometry and Get Geometry Type with Aspose.GIS for .NET](/gis/net/geometry-analysis/get-geometry-type/)
- [How to Convert GeoJSON – Aspose.GIS for .NET](/gis/net/geo-data-conversion/)
- [Create MultiPoint Geometry .NET with Aspose.GIS](/gis/net/geometry-creation/create-multipoint-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}