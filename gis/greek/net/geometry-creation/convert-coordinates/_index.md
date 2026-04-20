---
date: 2026-02-13
description: Μάθετε πώς να μετατρέπετε συντεταγμένες σε DMS με το Aspose.GIS για .NET.
  Αυτός ο βήμα‑προς‑βήμα οδηγός C# δείχνει πώς να μετατρέψετε πλάτος‑μήκος, δεκαδικούς
  βαθμούς σε DMS και άλλα.
linktitle: Convert Coordinates
second_title: Aspose.GIS .NET API
title: Πώς να μετατρέψετε συντεταγμένες σε DMS με το Aspose.GIS για .NET
url: /el/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Μετατρέψετε Συντεταγμένες σε DMS με το Aspose.GIS

## Εισαγωγή
Σε αυτό το εκπαιδευτικό σεμινάριο, θα μάθετε **πώς να μετατρέψετε συντεταγμένες** σε DMS (μοίρες, λεπτά, δευτερόλεπτα) χρησιμοποιώντας τη ισχυρή βιβλιοθήκη Aspose.GIS για .NET. Είτε χρειάζεστε **c# convert lat long**, είτε θέλετε να δημιουργήσετε ανθρώπινα αναγνώσιμες συμβολοσειρές τοποθεσίας, είτε απλώς να εξερευνήσετε διαφορετικές μορφές συντεταγμένων, αυτός ο οδηγός σας καθοδηγεί βήμα‑βήμα με σαφείς εξηγήσεις και έτοιμο κώδικα C#.

## Γρήγορες Απαντήσεις
- **Τι σημαίνει “convert coordinates to DMS”;** Μετατρέπει αριθμητικές τιμές γεωγραφικού πλάτους/μήκους σε παραδοσιακή σημειολογία μοίρες‑λεπτά‑δευτερόλεπτα.  
- **Ποια βιβλιοθήκη διαχειρίζεται τη μετατροπή;** Το Aspose.GIS για .NET παρέχει την κλάση `GeoConvert` με ενσωματωμένη υποστήριξη μορφών.  
- **Χρειάζομαι άδεια για να το δοκιμάσω;** Διατίθεται δωρεάν δοκιμή· απαιτείται εμπορική άδεια για παραγωγική χρήση.  
- **Ποιες εκδόσεις του .NET υποστηρίζονται;** .NET Framework 4.5+, .NET Core 3.1+ και .NET 5/6+.  
- **Μπορώ να χρησιμοποιήσω τον ίδιο κώδικα για άλλες μορφές;** Ναι—απλώς αλλάξτε την τιμή του enum `PointFormats` (π.χ., `DecimalDegrees`, `GeoRef`).  

## Πώς να Μετατρέψετε Συντεταγμένες σε DMS
Πριν βυθιστούμε στον κώδικα, ας διευκρινίσουμε γιατί το DMS παραμένει χρήσιμο. Χαρτογράφοι, πιλότοι και πολλοί πάροχοι δεδομένων GIS βασίζονται στο DMS επειδή είναι φιλικό στον άνθρωπο και ευθυγραμμίζεται με τα παραδοσιακά χάρτες. Το Aspose.GIS αφαιρεί την ανάγκη για χειροκίνητους υπολογισμούς, επιτρέποντάς σας να εστιάσετε στη λογική της εφαρμογής σας.

## Τι είναι η μετατροπή συντεταγμένων σε DMS;
Η μετατροπή συντεταγμένων σε DMS μετατρέπει τις δεκαδικές τιμές γεωγραφικού πλάτους και μήκους σε μορφή όπως `25°30'00"N 45°30'00"E`. Αυτή η αναπαράσταση χρησιμοποιείται ευρέως στην χαρτογραφία, την πλοήγηση και την ανταλλαγή δεδομένων GIS.

## Γιατί να χρησιμοποιήσετε το Aspose.GIS για μετατροπή συντεταγμένων;
- **All‑in‑one API** – Χωρίς εξωτερικές βιβλιοθήκες ή πολύπλοκο μαθηματικό λογισμό· το Aspose.GIS διαχειρίζεται την ανάλυση και τη μορφοποίηση εσωτερικά.  
- **High accuracy** – Ακριβής διαχείριση ειδικών περιπτώσεων όπως αρνητικές τιμές και σχεδιαστές ημισφαιρίων.  
- **Cross‑platform** – Λειτουργεί το ίδιο σε Windows, Linux και macOS .NET runtime.  
- **Extensible** – Εύκολη εναλλαγή μεταξύ DMS, δεκαδικών μοιρών, μοίρες‑δεκαδικά‑λεπτά και μορφών GeoRef.  

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

1. **Βασικές γνώσεις C#** – Εξοικείωση με μεταβλητές, κλήσεις μεθόδων και έξοδο κονσόλας.  
2. **Aspose.GIS εγκατεστημένο** – Κατεβάστε το πιο πρόσφατο πακέτο από την [Ιστοσελίδα Aspose.GIS](https://releases.aspose.com/gis/net/).  

## Εισαγωγή Namespaces
Πρώτα, εισάγετε τα namespaces που απαιτούνται για λειτουργίες GIS:

```csharp
using System;
using Aspose.Gis;
```

## Οδηγός βήμα‑βήμα

### Step 1: Start the conversion process
Εκτυπώνουμε ένα φιλικό μήνυμα ώστε να γνωρίζετε ότι η επίδειξη έχει ξεκινήσει.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### Step 2: Convert to Decimal Degrees  
Αν και ο τελικός στόχος είναι το DMS, ξεκινάμε δείχνοντας την αρχική δεκαδική αναπαράσταση. Αυτό επίσης δείχνει τη διαδρομή **decimal degrees to dms** που θα ακολουθήσετε αργότερα.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Step 3: Convert to Degree Decimal Minutes  
Αυτή η μορφή (`DD°MM.m'`) είναι ένα κοινό ενδιάμεσο βήμα όταν χρειάζεται *convert lat long degree minutes*.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Step 4: Convert to Degree Minutes Seconds (DMS)  
Αυτή είναι η καρδιά του σεμιναρίου μας—**convert coordinates to DMS**.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

### Step 5: Convert to GeoRef  
Για πληρότητα, δείχνουμε επίσης τη μορφή `GeoRef`, χρήσιμη σε ροές εργασίας απομακρυσμένης ανίχνευσης.

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## Συνηθισμένα Προβλήματα και Λύσεις
- **Incorrect hemisphere letters** – Βεβαιωθείτε ότι περνάτε θετικές τιμές για βορρά/ανατολή και αρνητικές για νότο/δυτικά· το API προσθέτει αυτόματα το σωστό επίθημα.  
- **Unexpected blank output** – Επαληθεύστε ότι η συναρμολόγηση `Aspose.Gis` αναφέρεται σωστά και ότι το έργο στοχεύει σε υποστηριζόμενη έκδοση .NET.  
- **License not found** – Τοποθετήστε το αρχείο άδειας στην ρίζα της εφαρμογής ή ορίστε το προγραμματιστικά με `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.  

## Συχνές Ερωτήσεις

**Ε: Είναι το Aspose.GIS συμβατό με άλλες γλώσσες προγραμματισμού;**  
Α: Το Aspose.GIS στοχεύει κυρίως προγραμματιστές .NET, αλλά υπάρχει επίσης διαθέσιμη έκδοση για Java.

**Ε: Μπορώ να δοκιμάσω το Aspose.GIS πριν το αγοράσω;**  
Α: Ναι, μπορείτε να αποκτήσετε δωρεάν δοκιμή του Aspose.GIS από την [ιστοσελίδα](https://releases.aspose.com/).

**Ε: Πώς μπορώ να λάβω υποστήριξη για το Aspose.GIS;**  
Α: Μπορείτε να ζητήσετε βοήθεια από το φόρουμ κοινότητας Aspose.GIS [εδώ](https://forum.aspose.com/c/gis/33).

**Ε: Διατίθενται προσωρινές άδειες για το Aspose.GIS;**  
Α: Ναι, οι προσωρινές άδειες μπορούν να ληφθούν από τη [σελίδα προσωρινής άδειας](https://purchase.aspose.com/temporary-license/).

**Ε: Πού μπορώ να αγοράσω το Aspose.GIS;**  
Α: Μπορείτε να αγοράσετε το Aspose.GIS από τη [σελίδα αγοράς](https://purchase.aspose.com/buy).

## Συμπέρασμα
Ακολουθώντας αυτά τα βήματα, τώρα γνωρίζετε πώς να **convert coordinates to DMS** και άλλες κοινές μορφές GIS χρησιμοποιώντας το Aspose.GIS για .NET. Αυτή η δυνατότητα σας επιτρέπει να ενσωματώσετε απρόσκοπτα ανθρώπινα αναγνώσιμες συμβολοσειρές τοποθεσίας σε εφαρμογές χαρτογράφησης, αναφορές ή οποιαδήποτε ροή εργασίας χωρικών δεδομένων. Μη διστάσετε να πειραματιστείτε με διαφορετικές τιμές γεωγραφικού πλάτους/μήκους και να εξερευνήσετε τις άλλες μορφές που προσφέρει η κλάση `GeoConvert`.

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}