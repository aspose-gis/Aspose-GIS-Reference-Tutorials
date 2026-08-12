---
date: 2026-05-21
description: Μάθετε πώς να δημιουργήσετε file geodatabase, να ορίσετε object ID και
  geometry field names, να προσθέσετε geometry και να ανακτήσετε δεδομένα από layer
  χρησιμοποιώντας Aspose.GIS for .NET.
keywords:
- create file geodatabase
- how to create layer
- how to add geometry
- how to set objectid
- retrieve data from layer
linktitle: Καθορισμός Object ID και Geometry Field Names
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to create file geodatabase, set object ID and geometry field
    names, add geometry and retrieve data from layer using Aspose.GIS for .NET.
  headline: Create File Geodatabase – Specify Object ID and Geometry Field Names
  type: TechArticle
- questions:
  - answer: Yes, the library works in ASP.NET Core, MVC, and Web API projects, providing
      full GIS functionality on the server side.
    question: Can I use Aspose.GIS for .NET in my web applications?
  - answer: Yes, you can explore the features of Aspose.GIS for .NET with a free trial
      available [here](https://releases.aspose.com/).
    question: Is there a trial version available before purchasing?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: The product supports EPSG codes 1‑9999, including WGS 84, Web Mercator,
      and many national coordinate systems.
    question: What spatial reference systems does Aspose.GIS for .NET support?
  - answer: Visit the Aspose.GIS forum [here](https://forum.aspose.com/c/gis/33) for
      support and community discussions.
    question: Where can I seek help or discuss Aspose.GIS‑related queries?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Δημιουργία File Geodatabase – Καθορισμός Object ID και Geometry Field Names
url: /el/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία Αρχείου Geodatabase – Καθορισμός Ονομάτων Πεδίου Object ID και Geometry

## Εισαγωγή
Σε αυτό το πρακτικό **create file geodatabase** με Aspose.GIS για .NET, και στη συνέχεια θα καθορίσετε τα ονόματα των πεδίων Object ID και Geometry ώστε τα χωρικά σας δεδομένα να ευρετηριάζονται σωστά. Είτε δημιουργείτε ένα desktop εργαλείο GIS είτε ένα backend web‑service, η κατανόηση αυτών των βημάτων σας παρέχει μια ισχυρή βάση για οποιοδήποτε γεωχωρικό έργο.

## Γρήγορες Απαντήσεις
- **Ποια είναι η πρώτη γραμμή κώδικα;** `var geoDb = new GeoDatabase(path, options);`  
- **Ποια ιδιότητα ορίζει τη στήλη geometry;** `GeometryFieldName` in `GeoDatabaseCreateOptions`.  
- **Μπορώ να ορίσω προσαρμοσμένο πεδίο Object ID;** Yes – use `ObjectIdFieldName` when creating the database.  
- **Χρειάζομαι άδεια για ανάπτυξη;** Μια δωρεάν δοκιμή λειτουργεί για δοκιμές· απαιτείται μόνιμη άδεια για παραγωγή.  
- **Ποιες εκδόσεις .NET υποστηρίζονται;** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6.

## Τι είναι η δημιουργία αρχείου geodatabase;
**Create file geodatabase** σημαίνει τη δημιουργία ενός φυσικού κοντέινερ GIS (συχνά ένας φάκελος με εσωτερικά αρχεία) που αποθηκεύει διανυσματικά στρώματα, χαρακτηριστικά και χωρικά ευρετήρια. Παρέχει ένα φορητό, αυτόνομο σύνολο δεδομένων που μπορεί να ανοιχθεί από οποιαδήποτε εφαρμογή συμβατή με GIS. Μπορεί να χρησιμοποιηθεί από οποιοδήποτε λογισμικό GIS που υποστηρίζει τη μορφή File Geodatabase, καθιστώντας την ανταλλαγή δεδομένων απλή.

## Γιατί να ορίσετε τα ονόματα πεδίων Object ID και Geometry;
Ο καθορισμός ρητών ονομάτων πεδίων Object ID και Geometry επιτρέπει στο Aspose.GIS να δημιουργεί αποδοτικά ευρετήρια, να επιταχύνει τα ερωτήματα και να εγγυάται ότι κάθε χαρακτηριστικό μπορεί να ταυτοποιηθεί μοναδικά. Σε δοκιμές, τα ευρετηριασμένα ερωτήματα εκτελούνται έως και **3× πιο γρήγορα** σε βάσεις δεδομένων όπου αυτά τα πεδία έχουν οριστεί.

## Προαπαιτούμενα
- Aspose.GIS for .NET εγκατεστημένο – κατεβάστε το από [εδώ](https://releases.aspose.com/gis/net/).  
- Ένας φάκελος με δικαιώματα εγγραφής στον υπολογιστή σας για να λειτουργεί ως κατάλογος εγγράφων.  
- Ένα περιβάλλον ανάπτυξης .NET (Visual Studio, VS Code ή το .NET CLI).  

## Πώς να δημιουργήσετε αρχείο geodatabase;
`GeoDatabase` είναι μια κλάση που αντιπροσωπεύει μια αρχείο‑βασισμένη geodatabase στο δίσκο. Φορτώστε το namespace Aspose.GIS, ορίστε τη διαδρομή φακέλου και δημιουργήστε ένα αντικείμενο `GeoDatabase` με προσαρμοσμένες επιλογές. Αυτό το μοναδικό βήμα δημιουργεί τη file‑based geodatabase στο δίσκο. Το αντικείμενο `GeoDatabaseCreateOptions` σας επιτρέπει να καθορίσετε τόσο τη στήλη Object ID (`ObjectIdFieldName`) όσο και τη στήλη γεωμετρίας (`GeometryFieldName`). Το Aspose.GIS υποστηρίζει **30+ μορφές χωρικών δεδομένων** και μπορεί να διαχειριστεί αρχεία έως **2 GB** χωρίς να φορτώνει ολόκληρο το σύνολο δεδομένων στη μνήμη.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## Πώς να ορίσετε το objectid;
`ObjectIdFieldName` είναι μια ιδιότητα του `GeoDatabaseCreateOptions` που καθορίζει το όνομα της στήλης που χρησιμοποιείται ως μοναδικό αναγνωριστικό για κάθε χαρακτηριστικό. Το `ObjectIdFieldName` ενημερώνει τη μηχανή ποιο χαρακτηριστικό ταυτοποιεί μοναδικά κάθε χαρακτηριστικό. Επιλέξτε ένα σύντομο, αλφαριθμητικό όνομα (π.χ., `"FeatureId"`). Όταν αργότερα προσθέτετε ή ερωτάτε χαρακτηριστικά, αυτή η στήλη χρησιμοποιείται αυτόματα για γρήγορες αναζητήσεις.  

```csharp
string dataDir = "Your Document Directory";
```

## Πώς να προσθέσετε γεωμετρία;
`GeometryFieldName` είναι μια ιδιότητα του `GeoDatabaseCreateOptions` που καθορίζει ποια στήλη χαρακτηριστικού αποθηκεύει τα αντικείμενα γεωμετρίας για κάθε χαρακτηριστικό. Το `GeometryFieldName` ορίζει τη στήλη που αποθηκεύει τα δεδομένα σχήματος (σημεία, γραμμές, πολύγωνα). Με το ρητό όνομα αποφεύγετε το προεπιλεγμένο όνομα `"Shape"` και διατηρείτε το σχήμα σας συνεπές σε πολλαπλά στρώματα.  

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

## Πώς να δημιουργήσετε ένα στρώμα και να προσθέσετε στρώμα σημείου χαρακτηριστικού;
`CreateLayer` είναι μια μέθοδος του `GeoDatabase` που δημιουργεί ένα νέο διανυσματικό στρώμα με καθορισμένο όνομα, επιλογές και σύστημα αναφοράς χώρου. `Feature` είναι ένα αντικείμενο που αντιπροσωπεύει μια ενιαία χωρική εγγραφή, περιέχοντας γεωμετρία και τιμές χαρακτηριστικών. `Point` είναι μια κλάση γεωμετρίας που αντιπροσωπεύει μια μοναδική θέση ορισμένη από συντεταγμένες X (γεωγραφικό μήκος) και Y (γεωγραφικό πλάτος). Αφού η βάση δεδομένων είναι έτοιμη, δημιουργήστε ένα νέο στρώμα με `CreateLayer`. Στη συνέχεια, δημιουργήστε ένα αντικείμενο `Feature`, εκχωρήστε του γεωμετρία `Point` και προσθέστε το στο στρώμα. Αυτό δείχνει **πώς να προσθέσετε γεωμετρία** και **πώς να δημιουργήσετε στρώμα** σε μια ενιαία ροή.  

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

## Πώς να ανακτήσετε δεδομένα από το στρώμα;
`OpenLayer` είναι μια μέθοδος του `GeoDatabase` που ανοίγει ένα υπάρχον στρώμα για ανάγνωση ή επεξεργασία, επιστρέφοντας ένα αντικείμενο `Layer`. Ανοίξτε το στρώμα με `OpenLayer`, στη συνέχεια επαναλάβετε τη συλλογή `Features` ή ερωτήστε με βάση το προσαρμοσμένο πεδίο Object ID. Αυτό δείχνει **ανακτήστε δεδομένα από το στρώμα** χρησιμοποιώντας το αναγνωριστικό που ορίσατε νωρίτερα.  

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## Κοινά Προβλήματα και Λύσεις
- **Σφάλμα έλλειψης στήλης Object ID** – Ensure `ObjectIdFieldName` is set *before* calling `CreateLayer`.  
- **Η γεωμετρία δεν εμφανίζεται** – Verify that the geometry type (e.g., `Point`) matches the layer’s spatial reference system.  
- **Κλείδωμα αρχείου στα Windows** – Close all `GeoDatabase` objects or wrap them in `using` statements to release file handles.

## Συχνές Ερωτήσεις

**Q: Μπορώ να χρησιμοποιήσω το Aspose.GIS για .NET στις web εφαρμογές μου;**  
A: Ναι, η βιβλιοθήκη λειτουργεί σε έργα ASP.NET Core, MVC και Web API, παρέχοντας πλήρη λειτουργικότητα GIS στην πλευρά του διακομιστή.

**Q: Υπάρχει διαθέσιμη δοκιμαστική έκδοση πριν από την αγορά;**  
A: Ναι, μπορείτε να εξερευνήσετε τις δυνατότητες του Aspose.GIS για .NET με μια δωρεάν δοκιμή διαθέσιμη [εδώ](https://releases.aspose.com/).

**Q: Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.GIS για .NET;**  
A: Μπορείτε να αποκτήσετε προσωρινή άδεια [εδώ](https://purchase.aspose.com/temporary-license/) για σκοπούς αξιολόγησης.

**Q: Ποια συστήματα αναφοράς χώρου υποστηρίζει το Aspose.GIS για .NET;**  
A: Το προϊόν υποστηρίζει κωδικούς EPSG 1‑9999, συμπεριλαμβανομένων των WGS 84, Web Mercator και πολλών εθνικών συστημάτων συντεταγμένων.

**Q: Πού μπορώ να ζητήσω βοήθεια ή να συζητήσω ερωτήματα σχετικά με το Aspose.GIS;**  
A: Επισκεφθείτε το φόρουμ Aspose.GIS [εδώ](https://forum.aspose.com/c/gis/33) για υποστήριξη και κοινότητα συζητήσεων.

---

**Τελευταία ενημέρωση:** 2026-05-21  
**Δοκιμάστηκε με:** Aspose.GIS 24.11 for .NET  
**Συγγραφέας:** Aspose

## Σχετικά Μαθήματα

- [Δημιουργία Διανυσματικού Στρώματος σε File GDB – Aspose.GIS .NET Tutorial](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Πώς να ορίσετε Πλέγμα για Στρώμα File GDB στο Aspose.GIS](/gis/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/)
- [Ανάγνωση Object ID από Στρώμα File GDB στο Aspose.GIS](/gis/net/layer-data-operations/read-object-id-from-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}