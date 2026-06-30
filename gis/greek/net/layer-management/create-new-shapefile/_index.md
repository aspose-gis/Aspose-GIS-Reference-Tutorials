---
date: 2026-06-30
description: Μάθετε πώς να δημιουργήσετε shapefile χρησιμοποιώντας Aspose.GIS for
  .NET. Αυτός ο οδηγός βήμα‑βήμα σας δείχνει πώς να ορίσετε ένα vector layer, να προσθέσετε
  ένα date attribute και να διαχειριστείτε spatial data αποδοτικά.
keywords:
- how to create shapefile
- temporal gis shapefile
- Aspose.GIS vector layer
- GIS data automation
linktitle: Δημιουργία Νέου Shapefile
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create shapefile using Aspose.GIS for .NET. This step‑by‑step
    guide shows you how to define a vector layer, add a date attribute, and manage
    spatial data efficiently.
  headline: How to Create Shapefile with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS primarily supports .NET, but there are versions available for
      Java as well.
    question: Can I use Aspose.GIS with other programming languages?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I find support for Aspose.GIS?
  - answer: Get your temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license?
  - answer: You can buy the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Πώς να δημιουργήσετε Shapefile με Aspose.GIS for .NET
url: /el/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία Νέου Shapefile

## Εισαγωγή
Αν εμβαθύνετε στην ανάπτυξη συστημάτων γεωγραφικών πληροφοριών (GIS) με .NET, το Aspose.GIS είναι η λύση σας για **πώς να δημιουργήσετε shapefile** προγραμματιστικά. Αυτή η βιβλιοθήκη σας δίνει πλήρη έλεγχο πάνω σε vector layers, attribute schemas και τη συμμόρφωση με το format αρχείων, ώστε να μπορείτε να αυτοματοποιήσετε pipelines δεδομένων ή να δημιουργήσετε σύνολα δοκιμαστικών δεδομένων σε λίγα λεπτά.

## Γρήγορες Απαντήσεις
- **What does this tutorial teach?** Πώς να δημιουργήσετε ένα νέο shapefile, να ορίσετε ένα vector layer και να προσθέσετε attributes (συμπεριλαμβανομένου ενός πεδίου ημερομηνίας).  
- **Which library is required?** Aspose.GIS for .NET.  
- **Do I need a license?** Μια δωρεάν δοκιμή λειτουργεί για μάθηση· απαιτείται εμπορική άδεια για παραγωγή.  
- **What IDE should I use?** Visual Studio (οποιαδήποτε πρόσφατη έκδοση).  
- **How long does the implementation take?** Περίπου 10‑15 λεπτά για το βασικό παράδειγμα.

## Πώς να δημιουργήσετε shapefile με Aspose.GIS για .NET;
Φορτώστε τη βιβλιοθήκη Aspose.GIS, ορίστε το φάκελο εξόδου, δημιουργήστε ένα `VectorLayer`, ορίστε attributes και προσθέστε features—όλη αυτή η ροή εργασίας μπορεί να γραφτεί σε λιγότερες από 30 γραμμές C#. Η βιβλιοθήκη διαχειρίζεται αυτόματα τη δημιουργία geometry, τον τύπο των attributes και τη γραφή του αρχείου, ώστε να μην χρειάζεται να διαχειρίζεστε τις λεπτομερείς προδιαγραφές Shapefile.

## Προαπαιτούμενα
Πριν ξεκινήσουμε το tutorial, βεβαιωθείτε ότι έχετε τα παρακάτω προαπαιτούμενα:
- Βασική κατανόηση της γλώσσας προγραμματισμού C#.
- Visual Studio εγκατεστημένο στον υπολογιστή σας.
- Βιβλιοθήκη Aspose.GIS for .NET. Μπορείτε να τη κατεβάσετε [εδώ](https://releases.aspose.com/gis/net/).

## Εισαγωγή Namespaces
Ξεκινήστε εισάγοντας τα απαραίτητα namespaces για να αξιοποιήσετε τη λειτουργικότητα του Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Βήμα 1: Ρύθμιση του Έργου Σας
Ξεκινήστε δημιουργώντας ένα νέο έργο C# στο Visual Studio και συμπεριλάβετε τη βιβλιοθήκη Aspose.GIS.

## Βήμα 2: Ορισμός του Καταλόγου Εγγράφου
```csharp
string dataDir = "Your Document Directory";
```
Αντικαταστήστε το *Your Document Directory* με το πραγματικό μονοπάτι όπου θέλετε να αποθηκεύσετε το νέο σας shapefile.

## Βήμα 3: Δημιουργία VectorLayer
Η κλάση `VectorLayer` αντιπροσωπεύει ένα μοναδικό shapefile layer που αποθηκεύει geometry και δεδομένα attribute.  
Σε αυτό το βήμα ορίζουμε ένα vector layer και δηλώνουμε τρία attributes: ένα πεδίο κειμένου (`name`), ένα ακέραιο πεδίο (`age`) και ένα πεδίο ημερομηνίας‑ώρας (`dob`). Η προσθήκη του attribute ημερομηνίας είναι κρίσιμη για αναλύσεις **temporal GIS shapefile**.

```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```

## Βήμα 4: Προσθήκη Features
### Περίπτωση 1: Ορισμός Τιμών Ξεχωριστά
Η μέθοδος `SetValues` εκχωρεί τιμές attribute σε ένα feature με τη σειρά που ορίστηκαν.

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
Εδώ δημιουργούμε δύο σημεία, ορίζουμε κάθε attribute ξεχωριστά και προσθέτουμε τα features στο layer.

### Περίπτωση 2: Ορισμός Νέων Τιμών για Όλα τα Attributes
Εναλλακτικά, μπορείτε να παρέχετε όλες τις τιμές attribute μονομιάς χρησιμοποιώντας το `SetValues` με έναν πίνακα αντικειμένων.

```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
Σε αυτή την προσέγγιση γεμίζουμε όλες τις τιμές attribute με μία κλήση χρησιμοποιώντας έναν πίνακα αντικειμένων—χρήσιμο όταν έχετε πολλά attributes.

## Γιατί Είναι Σημαντικό;
Η δημιουργία shapefile προγραμματιστικά σας επιτρέπει να αυτοματοποιήσετε pipelines δεδομένων, να δημιουργήσετε σύνολα δοκιμαστικών δεδομένων ή να ενσωματώσετε το αποτέλεσμα GIS απευθείας σε web services. Το Aspose.GIS υποστηρίζει **30+ vector και raster formats** και μπορεί να γράψει shapefiles πολλών εκατοντάδων σελίδων χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη, προσφέροντας ταχύτητα και κλιμακωσιμότητα.

## Συνηθισμένα Πιθανά Σφάλματα & Συμβουλές
- **Path separators:** Χρησιμοποιήστε `Path.Combine` για συμβατότητα μεταξύ πλατφορμών αντί για συνένωση συμβολοσειρών.  
- **Attribute order:** Η σειρά των τιμών στο `SetValues` πρέπει να ταιριάζει με τη σειρά που προσθέσατε τα attributes.  
- **Date handling:** Πάντα χρησιμοποιείτε `DateTimeKind.Utc` εάν τα GIS δεδομένα σας θα μοιράζονται μεταξύ ζωνών ώρας.

## Συμπέρασμα
Συγχαρητήρια! Δημιουργήσατε με επιτυχία ένα νέο shapefile χρησιμοποιώντας το Aspose.GIS για .NET. Αυτό το tutorial κάλυψε τα βασικά της ρύθμισης του έργου σας, του ορισμού ενός vector layer και της προσθήκης features—συμπεριλαμβανομένου ενός attribute ημερομηνίας. Καθώς προχωράτε, ανατρέξτε στην [τεκμηρίωση](https://reference.aspose.com/gis/net/) για προχωρημένες λειτουργίες και δυνατότητες.

## Συχνές Ερωτήσεις
**Q: Μπορώ να χρησιμοποιήσω το Aspose.GIS με άλλες γλώσσες προγραμματισμού;**  
A: Το Aspose.GIS υποστηρίζει κυρίως .NET, αλλά υπάρχουν εκδόσεις διαθέσιμες και για Java.

**Q: Υπάρχει διαθέσιμη δωρεάν δοκιμή;**  
A: Ναι, μπορείτε να αποκτήσετε τη δωρεάν δοκιμή [εδώ](https://releases.aspose.com/).

**Q: Πού μπορώ να βρω υποστήριξη για το Aspose.GIS;**  
A: Επισκεφθείτε το [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) για υποστήριξη κοινότητας και συζητήσεις.

**Q: Πώς μπορώ να αποκτήσω προσωρινή άδεια;**  
A: Λάβετε την προσωρινή άδεια σας [εδώ](https://purchase.aspose.com/temporary-license/).

**Q: Πού μπορώ να αγοράσω το Aspose.GIS για .NET;**  
A: Μπορείτε να αγοράσετε τη βιβλιοθήκη [εδώ](https://purchase.aspose.com/buy).

---

**Last Updated:** 2026-06-30  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose

## Σχετικά Tutorials

- [Λήψη Layer Attributes – Retrieve Layer Attribute Information with Aspose.GIS for .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Create Vector Layer and Set Layer Spatial Reference System](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}