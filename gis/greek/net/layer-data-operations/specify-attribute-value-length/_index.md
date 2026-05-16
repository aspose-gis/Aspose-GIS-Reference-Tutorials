---
date: 2026-05-16
description: Παράδειγμα διανυσματικού στρώματος που δείχνει πώς να ορίσετε το πλάτος
  του πεδίου, να καθορίσετε το πλάτος του χαρακτηριστικού και να προσθέσετε το μήκος
  του χαρακτηριστικού στο Aspose.GIS για .NET – ένας πλήρης οδηγός βήμα‑βήμα.
keywords:
- vector layer example
- how to set width
- set field width
- define attribute width
- add attribute length
linktitle: Πώς να Ορίσετε το Πλάτος του Πεδίου
schemas:
- author: Aspose
  dateModified: '2026-05-16'
  description: Vector layer example showing how to set field width, define attribute
    width, and add attribute length in Aspose.GIS for .NET – a complete step‑by‑step
    guide.
  headline: Vector Layer Example – How to Set Field Width in Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for peer‑to‑peer
      help and official responses.
    question: Where can I find community support for Aspose.GIS for .NET?
  - answer: Yes, explore the [free trial](https://releases.aspose.com/) to experience
      the full feature set without cost.
    question: Is there a free trial available for Aspose.GIS for .NET?
  - answer: Purchase your license [here](https://purchase.aspose.com/buy).
    question: How do I purchase a license for Aspose.GIS for .NET?
  - answer: Refer to the [documentation](https://reference.aspose.com/gis/net/) for
      comprehensive API details.
    question: Where can I access the documentation for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Παράδειγμα Διανυσματικού Στρώματος – Πώς να Ορίσετε το Πλάτος του Πεδίου στο
  Aspose.GIS για .NET
url: /el/net/layer-data-operations/specify-attribute-value-length/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Παράδειγμα Διάνυσμα Στρώματος – Πώς να Ορίσετε το Πλάτος Πεδίου στο Aspose.GIS για .NET

Σε αυτό το **παράδειγμα διάνυσμα στρώματος** θα μάθετε πώς να ορίσετε το πλάτος πεδίου για ένα χαρακτηριστικό κατά τη δημιουργία ενός Shapefile με το Aspose.GIS για .NET. Θα περάσουμε από κάθε βήμα, από την εισαγωγή των namespaces μέχρι την προσθήκη ενός χαρακτηριστικού, και θα εξηγήσουμε γιατί ο έλεγχος του μήκους του χαρακτηριστικού είναι σημαντικός για την ακεραιότητα των δεδομένων και τη διαλειτουργικότητα με άλλα εργαλεία GIS.

## Γρήγορες Απαντήσεις
- **Ποιος είναι ο κύριος σκοπός αυτού του οδηγού;** Να σας δείξει πώς να ορίσετε το πλάτος πεδίου για ένα χαρακτηριστικό σε shapefile χρησιμοποιώντας το Aspose.GIS για .NET.  
- **Ποια κλάση ορίζει το πλάτος πεδίου;** `FeatureAttribute.Width`.  
- **Χρειάζομαι άδεια για να εκτελέσω τον κώδικα;** Μια προσωρινή άδεια λειτουργεί για αξιολόγηση· απαιτείται πλήρης άδεια για παραγωγή.  
- **Ποια μορφή αρχείου χρησιμοποιείται στο παράδειγμα;** ESRI Shapefile (`.shp`).  
- **Μπορώ να αλλάξω το πλάτος μετά τη δημιουργία του στρώματος;** Όχι – το πλάτος πρέπει να οριστεί πριν την προσθήκη χαρακτηριστικών.

## Τι είναι το Πλάτος Πεδίου και γιατί είναι Σημαντικό;
Το πλάτος πεδίου (επίσης γνωστό ως μήκος χαρακτηριστικού) είναι ο μέγιστος αριθμός χαρακτήρων που μπορεί να αποθηκεύσει ένα πεδίο τύπου string στο στοιχείο DBF ενός Shapefile. Η σωστή ρύθμιση του πλάτους αποτρέπει την σιωπηρή περικοπή, εγγυάται ότι άλλες εφαρμογές GIS διαβάζουν τα δεδομένα ακριβώς όπως τα εισάγατε, και διατηρεί το μέγεθος του αρχείου προβλέψιμο—κάθε επιπλέον χαρακτήρας προσθέτει ένα byte ανά εγγραφή.

## Προαπαιτούμενα
- **Aspose.GIS for .NET Library** – κατεβάστε από το [download link](https://releases.aspose.com/gis/net/).  
- **Development Environment** – Visual Studio 2022, Visual Studio Code ή οποιοδήποτε IDE που υποστηρίζει .NET 6+.  
- **Write Access** – ένας φάκελος στο δίσκο όπου θα αποθηκευτεί το παραγόμενο shapefile.

## Γιατί να Χρησιμοποιήσετε ένα Παράδειγμα Διάνυσμα Στρώματος με Ορισμένο Πλάτος;
Το Aspose.GIS υποστηρίζει **περισσότερα από 30 μορφές αρχείων GIS**, συμπεριλαμβανομένων των Shapefile, GeoJSON, KML και GML. Όταν ορίζετε ρητά το πλάτος πεδίου, αποφεύγετε το προεπιλεγμένο όριο των 255 χαρακτήρων, το οποίο μπορεί να φουσκώσει αχρείαστα το αρχείο `.dbf` έως και 255 × αριθμός_εγγραφών bytes. Σε μεγάλα σύνολα δεδομένων, αυτό μεταφράζεται σε αξιοσημείωτη εξοικονόμηση αποθηκευτικού χώρου.

## Πώς να Ορίσετε το Πλάτος Πεδίου για ένα Χαρακτηριστικό;
Σε αυτήν την ενότητα φορτώνουμε ή δημιουργούμε ένα `VectorLayer` που δείχνει στο στόχο `.shp` αρχείο, ορίζουμε ένα χαρακτηριστικό τύπου string με ακριβές πλάτος, και στη συνέχεια προσθέτουμε χαρακτηριστικά—όλα σε λίγες σύντομες δηλώσεις. Το `VectorLayer` αντιπροσωπεύει ένα διανυσματικό σύνολο δεδομένων όπως ένα Shapefile και παρέχει πρόσβαση στη γεωμετρία και τον πίνακα χαρακτηριστικών του. Παρακάτω είναι η άμεση, εφαρμόσιμη συνταγή που μπορείτε να ακολουθήσετε βήμα‑βήμα:

### Εισαγωγή Namespaces
`FeatureAttribute`, `VectorLayer`, και σχετικοί τύποι βρίσκονται στο namespace `Aspose.Gis`. Εισάγετέ τα στην κορυφή του αρχείου σας:

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Δημιουργία VectorLayer
Η κλάση `VectorLayer` αντιπροσωπεύει μια πηγή διανυσματικών δεδομένων (π.χ., ένα Shapefile). Είναι το δοχείο που κρατά τα χαρακτηριστικά και τα χαρακτηριστικά τους.

Η κλάση `VectorLayer` είναι η αναπαράσταση του Aspose.GIS για ένα διανυσματικό σύνολο δεδομένων, διαχειρίζεται τη γεωμετρία και τους πίνακες χαρακτηριστικών στη μνήμη. Δημιουργήστε μια παρουσία που δείχνει σε ένα νέο ή υπάρχον αρχείο `.shp`.

```csharp
string dataDir = "Your Document Directory";
using (VectorLayer layer = VectorLayer.Create(dataDir + "SpecifyAttributeValueLength_out.shp", Drivers.Shapefile))
{
    // Your code for the next steps will go here.
}
```

### Προσθήκη Χαρακτηριστικού με Συγκεκριμένο Μήκος
Ορίστε ένα χαρακτηριστικό τύπου string που ονομάζεται **wide** και ορίστε την ιδιότητα `Width` σε 120 χαρακτήρες. Αυτό είναι το βασικό βήμα του **παραδείγματος διάνυσμα στρώματος**.

Το αντικείμενο `FeatureAttribute` περιγράφει μια στήλη στον πίνακα χαρακτηριστικών· ορίζοντας `Width = 120` λέει στον συγγραφέα Shapefile να δεσμεύσει ακριβώς 120 bytes για κάθε εγγραφή αυτού του πεδίου.

```csharp
FeatureAttribute attribute = new FeatureAttribute("wide", AttributeDataType.String);
attribute.Width = 120;
layer.Attributes.Add(attribute);
```

> **Συμβουλή:** Η ιδιότητα `Width` εφαρμόζεται μόνο σε χαρακτηριστικά τύπου string. Τα αριθμητικά, ημερομηνίας ή Boolean πεδία αγνοούν το `Width` επειδή το μέγεθός τους καθορίζεται από τον τύπο δεδομένων.

### Δημιουργία και Προσθήκη Χαρακτηριστικού
Δημιουργήστε ένα `Feature`, αναθέστε μια τιμή που χωράει μέσα στο όριο των 120 χαρακτήρων, και προσθέστε το στο στρώμα. Εάν η συμβολοσειρά υπερβαίνει το όριο, το Aspose.GIS την περικόπτει σιωπηρά στο καθορισμένο πλάτος, διατηρώντας την ακεραιότητα των δεδομένων.

Η κλάση `Feature` περιλαμβάνει γεωμετρία και τιμές χαρακτηριστικών· μετά τον ορισμό του χαρακτηριστικού, η κλήση `layer.Add(feature)` γράφει την εγγραφή στο Shapefile.

```csharp
Feature feature = layer.ConstructFeature();
feature.SetValue("wide", "this string can be up to 120 characters long now.");
layer.Add(feature);
```

Αν προσπαθήσετε να αναθέσετε μια μεγαλύτερη συμβολοσειρά, το Aspose.GIS θα την περικόψει στο καθορισμένο πλάτος, διατηρώντας την ακεραιότητα των δεδομένων.

## Κοινά Πιθανά Σφάλματα & Επίλυση Προβλημάτων
- **Ξεχάσατε να ορίσετε το `Width` πριν προσθέσετε το χαρακτηριστικό;** Το προεπιλεγμένο πλάτος είναι 255 χαρακτήρες· η αλλαγή του αργότερα δεν επηρεάζει τα ήδη δημιουργημένα πεδία. Πάντα ορίζετε το πλάτος πρώτα.  
- **Χρησιμοποιείτε τύπο δεδομένων μη‑string;** `Width` αγνοείται για αριθμητικά ή ημερομηνίας πεδία· βεβαιωθείτε ότι το `AttributeDataType` του χαρακτηριστικού είναι `String`.  
- **Σφάλμα “Field not found”;** Τα ονόματα χαρακτηριστικών είναι case‑sensitive. Επαληθεύστε ότι το όνομα που χρησιμοποιείται στο `SetValue` ταιριάζει ακριβώς με το όνομα που ορίστηκε στο σχήμα.  
- **Απρόσμενη αύξηση του μεγέθους του αρχείου;** Μεγαλύτερα πλάτη αυξάνουν το μέγεθος του `.dbf` γραμμικά. Για 10 000 εγγραφές, η αύξηση του πλάτους από 50 σε 120 προσθέτει περίπου 700 KB.

## Συχνές Ερωτήσεις
**Ε: Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.GIS για .NET;**  
Α: Μπορείτε να αποκτήσετε μια προσωρινή άδεια [εδώ](https://purchase.aspose.com/temporary-license/).

**Ε: Πού μπορώ να βρω υποστήριξη κοινότητας για το Aspose.GIS για .NET;**  
Α: Επισκεφθείτε το [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) για βοήθεια από ομότιμους και επίσημες απαντήσεις.

**Ε: Υπάρχει δωρεάν δοκιμή για το Aspose.GIS για .NET;**  
Α: Ναι, εξερευνήστε τη [δωρεάν δοκιμή](https://releases.aspose.com/) για να δοκιμάσετε το πλήρες σύνολο λειτουργιών χωρίς κόστος.

**Ε: Πώς μπορώ να αγοράσω άδεια για το Aspose.GIS για .NET;**  
Α: Αγοράστε την άδειά σας [εδώ](https://purchase.aspose.com/buy).

**Ε: Πού μπορώ να βρω την τεκμηρίωση για το Aspose.GIS για .NET;**  
Α: Ανατρέξτε στην [τεκμηρίωση](https://reference.aspose.com/gis/net/) για λεπτομερείς πληροφορίες API.

**Ε: Μπορώ να αλλάξω το πλάτος πεδίου μετά τη δημιουργία του στρώματος;**  
Α: Όχι. Το πλάτος πεδίου πρέπει να οριστεί πριν προστεθεί το χαρακτηριστικό· για να το τροποποιήσετε, πρέπει να δημιουργήσετε ξανά το στρώμα με το νέο σχήμα.

**Ε: Επηρεάζει η ρύθμιση μεγαλύτερου πλάτους το μέγεθος του αρχείου;**  
Α: Τα Shapefile αποθηκεύουν τα πεδία string με σταθερό μήκος, έτσι η αύξηση του πλάτους αυξάνει άμεσα το μέγεθος του αρχείου `.dbf` ανάλογα με τον αριθμό των εγγραφών.

## Συμπέρασμα
Αυτό το **παράδειγμα διάνυσμα στρώματος** έδειξε πώς να ορίσετε το πλάτος πεδίου για ένα χαρακτηριστικό σε Shapefile χρησιμοποιώντας το Aspose.GIS για .NET, και σας έδειξε πώς να προσθέσετε ένα χαρακτηριστικό με συγκεκριμένο μήκος αποδοτικά. Ελέγχοντας το πλάτος του χαρακτηριστικού αποφεύγετε την περικοπή δεδομένων, διατηρείτε τα μεγέθη των αρχείων βέλτιστα και εξασφαλίζετε αδιάλειπτη διαλειτουργικότητα με άλλες πλατφόρμες GIS. Πειραματιστείτε με διαφορετικά πλάτη, εξερευνήστε την [τεκμηρίωση](https://reference.aspose.com/gis/net/), και αξιοποιήστε πλήρως το δυναμικό της γεωχωρικής ανάπτυξης με το Aspose.GIS.

---

**Τελευταία Ενημέρωση:** 2026-05-16  
**Δοκιμή Με:** Aspose.GIS 24.11 for .NET  
**Συγγραφέας:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικά Μαθήματα

- [Λήψη Χαρακτηριστικών Στρώματος – Ανάκτηση Πληροφοριών Χαρακτηριστικών Στρώματος με Aspose.GIS για .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Πώς να Λάβετε Τιμή Χαρακτηριστικού (Προεπιλογή) με Aspose.GIS για .NET](/gis/net/layer-interaction-and-data-access/get-feature-attribute-value-default/)
- [Δημιουργία Διάνυσμα Στρώματος σε File GDB – Μαθήματα Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}