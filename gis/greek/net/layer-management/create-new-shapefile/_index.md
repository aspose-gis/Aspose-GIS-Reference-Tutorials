---
date: 2026-01-13
description: Μάθετε πώς να δημιουργήσετε νέο shapefile με το Aspose.GIS για .NET.
  Αυτός ο οδηγός βήμα‑βήμα σας δείχνει πώς να ορίσετε ένα διανυσματικό στρώμα, να
  προσθέσετε χαρακτηριστικό ημερομηνίας και να διαχειριστείτε χωρικά δεδομένα.
linktitle: Create New Shapefile
second_title: Aspose.GIS .NET API
title: Δημιουργία νέου shapefile
url: /el/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία Νέου Shapefile

## Εισαγωγή
Αν εμβαθύνετε στην ανάπτυξη συστημάτων γεωγραφικών πληροφοριών (GIS) με .NET, το Aspose.GIS είναι η λύση που χρειάζεστε. Αυτή η ισχυρή βιβλιοθήκη δίνει τη δυνατότητα στους προγραμματιστές να εργάζονται άψογα με χωρικά δεδομένα, και σε αυτό το tutorial θα σας καθοδηγήσουμε πώς να **δημιουργήσετε νέο shapefile** χρησιμοποιώντας το Aspose.GIS για .NET. Θα δείτε γιατί ο ορισμός ενός vector layer και η προσθήκη μιας ιδιότητας ημερομηνίας είναι απαραίτητα βήματα για αξιόπιστα GIS έργα.

## Γρήγορες Απαντήσεις
- **Τι διδάσκει αυτό το tutorial;** Πώς να δημιουργήσετε ένα νέο shapefile, να ορίσετε ένα vector layer και να προσθέσετε ιδιότητες (συμπεριλαμβανομένου ενός πεδίου ημερομηνίας).  
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.GIS για .NET.  
- **Χρειάζομαι άδεια;** Μια δωρεάν δοκιμή λειτουργεί για εκμάθηση· απαιτείται εμπορική άδεια για παραγωγή.  
- **Ποιο IDE πρέπει να χρησιμοποιήσω;** Visual Studio (οποιαδήποτε πρόσφατη έκδοση).  
- **Πόσο διαρκεί η υλοποίηση;** Περίπου 10‑15 λεπτά για το βασικό παράδειγμα.

## Προαπαιτούμενα
Πριν ξεκινήσουμε το tutorial, βεβαιωθείτε ότι έχετε τα παρακάτω:
- Βασική κατανόηση της γλώσσας προγραμματισμού C#.  
- Visual Studio εγκατεστημένο στον υπολογιστή σας.  
- Βιβλιοθήκη Aspose.GIS για .NET. Μπορείτε να τη κατεβάσετε [εδώ](https://releases.aspose.com/gis/net/).

## Εισαγωγή Namespaces
Ξεκινήστε εισάγοντας τους απαραίτητους namespaces για να αξιοποιήσετε τη λειτουργικότητα του Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Βήμα 1: Ρύθμιση του Έργου σας
Ξεκινήστε δημιουργώντας ένα νέο έργο C# στο Visual Studio και προσθέστε τη βιβλιοθήκη Aspose.GIS.

## Βήμα 2: Ορισμός του Καταλόγου Εγγράφων
```csharp
string dataDir = "Your Document Directory";
```
Αντικαταστήστε *Your Document Directory* με την πραγματική διαδρομή όπου θέλετε να αποθηκεύσετε το νέο shapefile.

## Βήμα 3: Δημιουργία VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
Αυτό το τμήμα κώδικα **ορίζει ένα vector layer** και δηλώνει τρεις ιδιότητες: ένα πεδίο κειμένου (`name`), ένα ακέραιο πεδίο (`age`) και ένα πεδίο ημερομηνίας‑ώρας (`dob`). Η προσθήκη της ιδιότητας ημερομηνίας είναι κρίσιμη για χρονικές GIS αναλύσεις.

## Βήμα 4: Προσθήκη Features
### Περίπτωση 1: Ορισμός Τιμών Ξεχωριστά
```csharp
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
firstFeature.SetValue("dob", new DateTime(1982, 2, 5, 16, 30, 0));
layer.Add(firstFeature);
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
secondFeature.SetValue("dob", new DateTime(1984, 12, 15, 15, 30, 0));
layer.Add(secondFeature);
```
Εδώ δημιουργούμε δύο σημεία, ορίζουμε κάθε ιδιότητα ξεχωριστά και προσθέτουμε τα features στο layer.

### Περίπτωση 2: Ορισμός Νέων Τιμών για Όλες τις Ιδιότητες
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
Σε αυτήν την προσέγγιση γεμίζουμε όλες τις τιμές ιδιοτήτων με μία κλήση χρησιμοποιώντας έναν πίνακα αντικειμένων—χρήσιμο όταν έχετε πολλές ιδιότητες.

## Γιατί Είναι Σημαντικό
Η προγραμματιστική δημιουργία shapefile σας επιτρέπει να αυτοματοποιήσετε pipelines δεδομένων, να δημιουργήσετε δοκιμαστικά σύνολα ή να ενσωματώσετε το GIS αποτέλεσμα απευθείας σε web services. Με την εξοικείωση με **πώς να δημιουργήσετε shapefile** με το Aspose.GIS, αποκτάτε πλήρη έλεγχο της γεωμετρίας των features, του σχήματος των ιδιοτήτων και της συμμόρφωσης με το φορμά αρχείου.

## Συνηθισμένα Πιθανά Σφάλματα & Συμβουλές
- **Διαχωριστές διαδρομών:** Χρησιμοποιήστε `Path.Combine` για συμβατότητα μεταξύ πλατφορμών αντί για συνένωση συμβολοσειρών.  
- **Σειρά ιδιοτήτων:** Η σειρά των τιμών στο `SetValues` πρέπει να ταιριάζει με τη σειρά που προσθέσατε τις ιδιότητες.  
- **Διαχείριση ημερομηνίας:** Χρησιμοποιείτε πάντα `DateTimeKind.Utc` εάν τα GIS δεδομένα σας θα μοιράζονται μεταξύ διαφορετικών ζωνών ώρας.

## Συμπέρασμα
Συγχαρητήρια! Δημιουργήσατε με επιτυχία ένα νέο shapefile χρησιμοποιώντας το Aspose.GIS για .NET. Αυτό το tutorial κάλυψε τα βασικά της ρύθμισης του έργου, του ορισμού ενός vector layer και της προσθήκης features—συμπεριλαμβανομένης μιας ιδιότητας ημερομηνίας. Καθώς προχωράτε, ανατρέξτε στην [τεκμηρίωση](https://reference.aspose.com/gis/net/) για προχωρημένες δυνατότητες και λειτουργίες.

## Συχνές Ερωτήσεις
### Ε: Μπορώ να χρησιμοποιήσω το Aspose.GIS με άλλες γλώσσες προγραμματισμού;
Το Aspose.GIS υποστηρίζει κυρίως .NET, αλλά υπάρχουν εκδόσεις διαθέσιμες και για Java.

### Ε: Υπάρχει διαθέσιμη δωρεάν δοκιμή;
Ναι, μπορείτε να αποκτήσετε τη δωρεάν δοκιμή [εδώ](https://releases.aspose.com/).

### Ε: Πού μπορώ να βρω υποστήριξη για το Aspose.GIS;
Επισκεφθείτε το [φόρουμ Aspose.GIS](https://forum.aspose.com/c/gis/33) για υποστήριξη από την κοινότητα και συζητήσεις.

### Ε: Πώς μπορώ να αποκτήσω προσωρινή άδεια;
Αποκτήστε την προσωρινή άδεια [εδώ](https://purchase.aspose.com/temporary-license/).

### Ε: Πού μπορώ να αγοράσω το Aspose.GIS για .NET;
Μπορείτε να αγοράσετε τη βιβλιοθήκη [εδώ](https://purchase.aspose.com/buy).

---

**Τελευταία Ενημέρωση:** 2026-01-13  
**Δοκιμάστηκε Με:** Aspose.GIS 24.11 for .NET  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}