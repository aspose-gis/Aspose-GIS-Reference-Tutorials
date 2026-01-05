---
date: 2026-01-05
description: Μάθετε πώς να διαβάζετε shapefile σε C# χρησιμοποιώντας το Aspose.GIS
  για .NET, να ανακτήσετε όλες τις τιμές των χαρακτηριστικών και να εξάγετε τα χαρακτηριστικά
  αποδοτικά.
linktitle: Get All Feature Attribute Values
second_title: Aspose.GIS .NET API
title: Ανάγνωση Shapefile C# – Λήψη όλων των τιμών χαρακτηριστικών
url: /el/net/layer-interaction-and-data-access/get-all-feature-attribute-values/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ανάκτηση Όλων των Τιμών Χαρακτηριστικών του Feature

## Εισαγωγή
Καλώς ήρθατε στον κόσμο της γεωχωρικής ανάπτυξης με το Aspose.GIS για .NET! Σε αυτό το σεμινάριο θα μάθετε **how to read shapefile C#** και θα ανακτήσετε κάθε τιμή χαρακτηριστικού από τα στοιχεία του. Είτε δημιουργείτε μια εφαρμογή χαρτογράφησης είτε επεξεργάζεστε χωρικά δεδομένα σε παρτίδες, η εξοικείωση με την εξαγωγή χαρακτηριστικών είναι απαραίτητη. Ας βουτήξουμε και δούμε τον κώδικα σε δράση.

## Γρήγορες Απαντήσεις
- **Τι κάνει αυτός ο κώδικας;** Ανοίγει ένα Shapefile και διαβάζει όλες, μερικές ή αποτυπωμένες τιμές χαρακτηριστικών από κάθε στοιχείο.  
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.GIS for .NET (συμβατό με .NET Framework και .NET Core).  
- **Χρειάζομαι άδεια;** Μια προσωρινή άδεια λειτουργεί για δοκιμές· απαιτείται πλήρης άδεια για παραγωγή.  
- **Μπορώ να διαβάσω άλλες μορφές;** Ναι – το ίδιο API υποστηρίζει GeoJSON, KML και πολλές άλλες.  
- **Πώς να αποτυπώσετε τα χαρακτηριστικά;** Χρησιμοποιήστε `feature.GetValuesDump()` για να λάβετε έναν ευέλικτο πίνακα αντικειμένων.

## Τι είναι το “read shapefile C#”;
Η ανάγνωση ενός Shapefile σε C# σημαίνει το άνοιγμα του αρχείου .shp με μια βιβλιοθήκη GIS, η επανάληψη πάνω στα διανυσματικά του στοιχεία και η πρόσβαση στα δεδομένα χαρακτηριστικών που αποθηκεύονται στο συνοδευτικό αρχείο .dbf. Το Aspose.GIS αφαιρεί τη χαμηλού επιπέδου διαχείριση αρχείων, επιτρέποντάς σας να εστιάσετε στις τιμές χαρακτηριστικών που χρειάζεστε.

## Γιατί να χρησιμοποιήσετε το Aspose.GIS για την ανάγνωση χαρακτηριστικών;
- **Απλό API** – διαισθητικές μεθόδους όπως `GetValues` και `GetValuesDump`.  
- **Διαπλατφορμικό** – λειτουργεί σε Windows, Linux και macOS με .NET Core.  
- **Πλούσια υποστήριξη μορφών** – διαχειρίζεται Shapefile, GeoJSON, GML και άλλα χωρίς πρόσθετα plugins.  
- **Βελτιστοποιημένη απόδοση** – γρήγορη επανάληψη σε μεγάλα σύνολα δεδομένων.

## Προαπαιτούμενα
Πριν ξεκινήσουμε αυτό το συναρπαστικό ταξίδι, βεβαιωθείτε ότι έχετε τα παρακάτω προαπαιτούμενα:
- Aspose.GIS for .NET: Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη από τη [σελίδα λήψης Aspose.GIS for .NET](https://releases.aspose.com/gis/net/).  
- Περιβάλλον Ανάπτυξης: Ρυθμίστε ένα περιβάλλον ανάπτυξης .NET, όπως το Visual Studio.  
- Shapefile: Έχετε ένα δείγμα Shapefile (π.χ., "InputShapeFile.shp") έτοιμο στον φάκελο εγγράφων σας.

## Εισαγωγή Namespaces
Στον κώδικα C# σας, ξεκινήστε εισάγοντας τα απαραίτητα namespaces για να αξιοποιήσετε τις δυνατότητες του Aspose.GIS:
```csharp
using System;
using Aspose.Gis;
```

## Βήμα 1: Ορισμός του Φακέλου Εγγράφων
Αντικαταστήστε το "Your Document Directory" με την πραγματική διαδρομή όπου βρίσκεται το Shapefile σας.
```csharp
string dataDir = "Your Document Directory";
```

## Βήμα 2: Άνοιγμα του VectorLayer
Αυτό το βήμα περιλαμβάνει το άνοιγμα του Shapefile χρησιμοποιώντας το Aspose.GIS, καθορίζοντας τη διαδρομή του αρχείου και τη μορφή (σε αυτήν την περίπτωση, Shapefile).
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for further steps goes here
}
```

## Βήμα 3: Ανάκτηση Όλων των Τιμών Χαρακτηριστικών του Feature
Το απόσπασμα δείχνει **how to read attributes** για κάθε feature φορτώνοντάς τα σε έναν πίνακα σταθερού μεγέθους.
```csharp
foreach (var feature in layer)
{
    // reads all the attributes into an array.
    object[] all = new object[3];
    feature.GetValues(all);
    Console.WriteLine("all    : {0}, {1}, {2}", all);
    // Your code for handling all attribute values goes here
    Console.WriteLine();
}
```

## Βήμα 4: Ανάκτηση Πολλών Τιμών Χαρακτηριστικών του Feature
Εδώ δείχνουμε **how to read specific attribute values** όταν χρειάζεστε μόνο ένα υποσύνολο πεδίων.
```csharp
foreach (var feature in layer)
{
    // reads several attributes into an array.
    object[] several = new object[2];
    feature.GetValues(several);
    Console.WriteLine("several: {0}, {1}", several);
    // Your code for handling several attribute values goes here
    Console.WriteLine();
}
```

## Βήμα 5: Ανάκτηση Τιμών Χαρακτηριστικών ως Dump Αντικειμένων
Αυτό το τελικό βήμα παρουσιάζει **how to dump attributes** χρησιμοποιώντας το `GetValuesDump()`, το οποίο επιστρέφει μια ευέλικτη συλλογή που μπορείτε να ελέγξετε ή να σειριοποιήσετε.
```csharp
foreach (var feature in layer)
{
    // reads attributes as a dump of objects.
    var dump = feature.GetValuesDump();
    Console.WriteLine("dump   : {0}, {1}, {2}", dump);
    // Your code for handling dumped attribute values goes here
    Console.WriteLine();
}
```

## Κοινά Προβλήματα και Λύσεις
- **Ασυμφωνία μεγέθους πίνακα** – Βεβαιωθείτε ότι ο πίνακας που περνάτε στο `GetValues` ταιριάζει με τον αριθμό των χαρακτηριστικών που αναμένετε· διαφορετικά θα λάβετε καταχωρήσεις `null`.  
- **Αρχείο δεν βρέθηκε** – Επαληθεύστε ότι το `dataDir` δείχνει στο σωστό φάκελο και ότι το όνομα του Shapefile είναι ακριβώς σωστό.  
- **Εξαίρεση άδειας** – Εάν δείτε σφάλμα άδειας, εφαρμόστε προσωρινή ή πλήρη άδεια πριν καλέσετε οποιεσδήποτε μεθόδους API.

## Συχνές Ερωτήσεις
### Είναι το Aspose.GIS συμβατό με .NET Core;
Ναι, το Aspose.GIS είναι πλήρως συμβατό με .NET Core, επιτρέποντάς σας να δημιουργείτε διαπλατφορμικές εφαρμογές.

### Μπορώ να δουλέψω με διαφορετικές μορφές αρχείων GIS χρησιμοποιώντας το Aspose.GIS;
Απόλυτα! Το Aspose.GIS υποστηρίζει διάφορες μορφές, συμπεριλαμβανομένων Shapefile, GeoJSON και άλλων.

### Υπάρχει φόρουμ κοινότητας για υποστήριξη Aspose.GIS;
Ναι, μπορείτε να βρείτε βοήθεια και να συμμετέχετε στην κοινότητα Aspose.GIS στο [φόρουμ υποστήριξης](https://forum.aspose.com/c/gis/33).

### Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.GIS;
Μπορείτε να αποκτήσετε προσωρινή άδεια για δοκιμές [εδώ](https://purchase.aspose.com/temporary-license/).

### Πού μπορώ να βρω λεπτομερή τεκμηρίωση για το Aspose.GIS;
Η πλήρης τεκμηρίωση είναι διαθέσιμη [εδώ](https://reference.aspose.com/gis/net/).

### Πώς να ανακτήσω μόνο το χαρακτηριστικό “Name” από κάθε feature;
Χρησιμοποιήστε `GetValues` με έναν πίνακα μεγέθους ενός στοιχείου και περάστε το δείκτη του πεδίου “Name”, ή καλέστε απευθείας `feature["Name"]`.

### Ποια είναι η διαφορά μεταξύ `GetValues` και `GetValuesDump`;
`GetValues` γεμίζει έναν προ‑καθορισμένο πίνακα με ακατέργαστες τιμές, ενώ `GetValuesDump` επιστρέφει έναν πίνακα αντικειμένων που μπορεί να διαβαστεί χωρίς προ‑γνώση του σχήματος.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Τελευταία Ενημέρωση:** 2026-01-05  
**Δοκιμή με:** Aspose.GIS for .NET (latest release)  
**Συγγραφέας:** Aspose  

---