---
date: 2026-08-08
description: Μάθετε την ανάλυση επικάλυψης GIS με συμμετρική διαφορά χρησιμοποιώντας
  Aspose.GIS for .NET. Αυτό το σεμινάριο δείχνει πώς να εκτελέσετε overlay, polygon
  intersection, union, difference και symmetric difference σε C#.
keywords:
- symmetric difference gis
- calculate polygon intersection
- how to perform overlay
lastmod: 2026-08-08
linktitle: Βρείτε Geometry Overlays
og_description: Ανακαλύψτε πώς να εκτελέσετε ανάλυση επικάλυψης GIS με συμμετρική
  διαφορά χρησιμοποιώντας Aspose.GIS for .NET. Ο οδηγός βήμα‑βήμα καλύπτει intersection,
  union, difference και άλλα.
og_image_alt: Screenshot of Aspose.GIS overlay operations in a .NET console app
og_title: Επικάλυψη GIS με συμμετρική διαφορά χρησιμοποιώντας Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn symmetric difference GIS overlay analysis using Aspose.GIS for
    .NET. This tutorial shows how to perform overlay, polygon intersection, union,
    difference, and symmetric difference in C#.
  headline: Symmetric difference GIS overlay with Aspose.GIS for .NET
  type: TechArticle
- description: Learn symmetric difference GIS overlay analysis using Aspose.GIS for
    .NET. This tutorial shows how to perform overlay, polygon intersection, union,
    difference, and symmetric difference in C#.
  name: Symmetric difference GIS overlay with Aspose.GIS for .NET
  steps:
  - name: create polygon objects
    text: A `Polygon` represents a closed shape defined by a series of coordinate
      points.
  - name: perform intersection operation
    text: '`Intersection` computes the common area shared by two polygons.'
  - name: print intersection points
    text: '`PrintRing` is a helper that prints each coordinate of a polygon’s exterior
      ring.'
  - name: perform union operation
    text: '`Union` merges two polygons into a single geometry covering all areas.'
  - name: print union points
    text: Output the coordinates of the united geometry.
  - name: perform difference operation
    text: '`Difference` subtracts the second polygon from the first, leaving the non‑overlapping
      portion.'
  - name: print difference points
    text: Show the remaining vertices after the subtraction.
  - name: perform symmetric difference operation
    text: '`SymmetricDifference` returns the parts belonging to either polygon but
      not both, producing a `MultiPolygon`.'
  - name: print symmetric difference polygons
    text: Iterate through each polygon in the `MultiPolygon` and print its points.
  type: HowTo
- questions:
  - answer: Yes, a valid commercial license permits unrestricted use in production
      applications.
    question: Can I use Aspose.GIS for .NET in my commercial projects?
  - answer: Yes, you can download a free trial from the [Aspose releases page](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.GIS for .NET?
  - answer: Support is available through the Aspose GIS forum [Aspose GIS forum](https://forum.aspose.com/c/gis/33).
    question: How can I get support for Aspose.GIS for .NET?
  - answer: Yes, temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses offered for testing?
  - answer: You can buy a license directly from the website [Aspose purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase a full license for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- gis overlay
- Aspose.GIS
- .NET geometry analysis
title: Επικάλυψη GIS με συμμετρική διαφορά χρησιμοποιώντας Aspose.GIS for .NET
url: /el/net/geometry-analysis/find-geometry-overlays/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Συμμετρική διαφορά GIS: εκτέλεση λειτουργιών επικάλυψης με το Aspose.GIS για .NET

Η ανάλυση επικάλυψης είναι μια βασική τεχνική σε οποιοδήποτε **spatial overlay tutorial**—σας επιτρέπει να συνδυάζετε, να συγκρίνετε και να εξάγετε πληροφορίες από πολλαπλά γεωγραφικά επίπεδα. Σε αυτόν τον οδηγό θα μάθετε **πώς να εκτελείτε επικάλυψη** λειτουργίες όπως Intersection, Union, Difference και Symmetric Difference χρησιμοποιώντας τη δυνατή βιβλιοθήκη Aspose.GIS για .NET. Στο τέλος του οδηγού θα μπορείτε να εφαρμόζετε αυτές τις μεθόδους σε πραγματικά προβλήματα GIS όπως προγραμματισμός χρήσης γης, μελέτες περιβαλλοντικών επιπτώσεων και βελτιστοποίηση διαδρομών.

## Γρήγορες απαντήσεις
- **Τι είναι μια λειτουργία επικάλυψης;** Μια επικάλυψη συνδυάζει δύο γεωμετρίες για να παράγει ένα νέο σχήμα—intersection, union, difference ή symmetric difference.  
- **Ποια βιβλιοθήκη .NET διαχειρίζεται τις επα覆πτικές λειτουργίες;** Η Aspose.GIS για .NET παρέχει ένα πλήρως διαχειριζόμενο API για όλες τις λειτουργίες γεωμετρίας θεωρίας συνόλων.  
- **Πόσο διαρκεί μια βασική υλοποίηση;** Περίπου 10‑15 λεπτά για να γράψετε, να μεταγλωττίσετε και να εκτελέσετε το δείγμα κώδικα.  
- **Χρειάζομαι άδεια για παραγωγή;** Ναι—απαιτείται εμπορική άδεια για παραγωγικές εγκαταστάσεις· διατίθεται δωρεάν δοκιμή για αξιολόγηση.  
- **Μπορώ να το τρέξω σε .NET 6+;** Απόλυτα—η Aspose.GIS υποστηρίζει .NET Core, .NET 5, .NET 6 και μεταγενέστερες εκδόσεις.

## Τι είναι μια λειτουργία επικάλυψης;

Οι λειτουργίες επικάλυψης υπολογίζουν μια νέα γεωμετρία βάσει της χωρικής σχέσης δύο εισαγόμενων σχημάτων. **Intersection** επιστρέφει την κοινή περιοχή, **Union** συγχωνεύει τις περιοχές, **Difference** αφαιρεί ένα σχήμα από το άλλο, και **Symmetric Difference** αποδίδει τα τμήματα που ανήκουν σε οποιοδήποτε σχήμα αλλά όχι και στα δύο. Αυτές οι συναρτήσεις θεωρίας συνόλων αποτελούν το μαθηματικό θεμέλιο της ανάλυσης GIS, επιτρέποντάς σας να απαντήσετε σε ερωτήσεις όπως «πού επικαλύπτονται δύο οικόπεδα;» ή «ποια περιοχή παραμένει μετά την αφαίρεση μιας προστατευμένης ζώνης».

## Γιατί να χρησιμοποιήσετε το Aspose.GIS για επικάλυψη;

Η Aspose.GIS υποστηρίζει **πάνω από 50 μορφές διανυσματικών και ραστερικών δεδομένων**, μπορεί να επεξεργαστεί **σύνολα δεδομένων πολλαπλών εκατοντάδων σελίδων χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη**, και λειτουργεί σε Windows, Linux και macOS. Το διαχειριζόμενο API της εξαλείφει την ανάγκη για εγγενείς βιβλιοθήκες GIS, μειώνοντας την πολυπλοκότητα της ανάπτυξης και επιτρέποντάς σας να διατηρείτε όλη τη λογική μέσα σε μια ενιαία λύση .NET.

## Συνηθισμένες περιπτώσεις χρήσης
- **Προγραμματισμός χρήσης γης:** Εντοπισμός επικαλυπτόμενων ζωνών μεταξύ προτεινόμενων αναπτύξεων και προστατευμένων περιοχών.  
- **Περιβαλλοντική ανάλυση:** Υπολογισμός της τομής των οικοτόπων με πηγές ρύπανσης.  
- **Δρομολόγηση υποδομών:** Προσδιορισμός των σημείων όπου νέοι δρόμοι τέμνουν υπάρχοντες διαδρόμους υποδομών.  
- **Αστική ανάλυση:** Συγχώνευση πολλαπλών δημοτικών συνόρων για δημιουργία περιφερειακής εικόνας.

## Προαπαιτούμενα
- Ένα λειτουργικό περιβάλλον ανάπτυξης .NET (Visual Studio, VS Code ή το .NET CLI).  
- Βιβλιοθήκη Aspose.GIS για .NET – κατεβάστε την τελευταία έκδοση από το [official site](https://releases.aspose.com/gis/net/).  

### Εισαγωγή ονομάτων χώρων
Πριν ξεκινήσετε τη χρήση του Aspose.GIS για .NET, πρέπει να εισάγετε τα απαραίτητα ονόματα χώρων στο έργο σας.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Πώς να εκτελέσετε λειτουργίες επικάλυψης σε .NET

Ένα `Polygon` αντιπροσωπεύει ένα κλειστό επίπεδο σχήμα που ορίζεται από έναν εξωτερικό δακτύλιο και προαιρετικούς εσωτερικούς δακτυλίους. Κάθε μέθοδος επικάλυψης (`Intersection`, `Union`, `Difference`, `SymmetricDifference`) υπολογίζει μια συγκεκριμένη λειτουργία θεωρίας συνόλων σε δύο γεωμετρίες.

Φορτώστε δύο αντικείμενα πολυγώνου, στη συνέχεια καλέστε τη σχετική μέθοδο επικάλυψης—Intersection, Union, Difference ή SymmetricDifference. Η πλήρης ροή εργασίας χωράει σε λίγες σύντομες γραμμές κώδικα, και κάθε μέθοδος επιστρέφει μια γεωμετρία που μπορείτε να ερωτήσετε ή να εξάγετε περαιτέρω.

**Direct answer:** Για να εκτελέσετε μια επικάλυψη στο Aspose.GIS, δημιουργήστε δύο αντικείμενα `Polygon`, στη συνέχεια καλέστε τη ζητούμενη μέθοδο (`Intersection`, `Union`, `Difference` ή `SymmetricDifference`). Κάθε κλήση επιστρέφει μια νέα γεωμετρία που αντιπροσωπεύει το αποτέλεσμα, το οποίο μπορείτε να σειριοποιήσετε σε WKT, GeoJSON ή οποιαδήποτε υποστηριζόμενη μορφή.

### Βήμα 1: δημιουργία αντικειμένων πολυγώνου
Ένα `Polygon` αντιπροσωπεύει ένα κλειστό σχήμα που ορίζεται από μια σειρά σημείων συντεταγμένων.

```csharp
var polygon1 = new Polygon();
polygon1.ExteriorRing = new LinearRing(new[]
{
	 new Point(0, 0),
	 new Point(0, 2),
	 new Point(2, 2),
	 new Point(2, 0),
	 new Point(0, 0),
 });
var polygon2 = new Polygon();
polygon2.ExteriorRing = new LinearRing(new[]
{
	new Point(1, 1),
	new Point(1, 3),
	new Point(3, 3),
	new Point(3, 1),
	new Point(1, 1),
});
```

### Βήμα 2: εκτέλεση λειτουργίας intersection
`Intersection` υπολογίζει την κοινή περιοχή που μοιράζονται δύο πολύγωνα.

```csharp
var intersection = polygon1.Intersection(polygon2);
Console.WriteLine("Intersection type is {0}", intersection.GeometryType); // Polygon
```

### Βήμα 3: εκτύπωση σημείων intersection
`PrintRing` είναι μια βοηθητική συνάρτηση που εκτυπώνει κάθε συντεταγμένη του εξωτερικού δακτυλίου ενός πολυγώνου.

```csharp
PrintRing(((IPolygon)intersection).ExteriorRing);
```

### Βήμα 4: εκτέλεση λειτουργίας union
`Union` συγχωνεύει δύο πολύγωνα σε μία ενιαία γεωμετρία που καλύπτει όλες τις περιοχές.

```csharp
var union = polygon1.Union(polygon2);
Console.WriteLine("Union type is {0}", union.GeometryType); // Polygon
```

### Βήμα 5: εκτύπωση σημείων union
Εξάγετε τις συντεταγμένες της ενοποιημένης γεωμετρίας.

```csharp
PrintRing(((IPolygon)union).ExteriorRing);
```

### Βήμα 6: εκτέλεση λειτουργίας difference
`Difference` αφαιρεί το δεύτερο πολύγωνο από το πρώτο, αφήνοντας το μη επικαλυπτόμενο τμήμα.

```csharp
var difference = polygon1.Difference(polygon2);
Console.WriteLine("Difference type is {0}", difference.GeometryType); // Polygon
```

### Βήμα 7: εκτύπωση σημείων difference
Εμφανίστε τις υπόλοιπες κορυφές μετά την αφαίρεση.

```csharp
PrintRing(((IPolygon)difference).ExteriorRing);
```

### Βήμα 8: εκτέλεση λειτουργίας symmetric difference
`SymmetricDifference` επιστρέφει τα τμήματα που ανήκουν σε οποιοδήποτε πολύγωνο αλλά όχι και στα δύο, παράγοντας ένα `MultiPolygon`.

```csharp
var symDifference = polygon1.SymDifference(polygon2);
Console.WriteLine("Symmetric Difference type is {0}", symDifference.GeometryType); // MultiPolygon
```

### Βήμα 9: εκτύπωση πολυγώνων symmetric difference
Διέλθετε κάθε πολύγωνο στο `MultiPolygon` και εκτυπώστε τα σημεία του.

```csharp
var multiPolygon = (IMultiPolygon)symDifference;
Console.WriteLine("Polygons count is {0}", multiPolygon.Count); // 2
PrintRing(((IPolygon)multiPolygon[0]).ExteriorRing);
PrintRing(((IPolygon)multiPolygon[1]).ExteriorRing);
```

## Συνηθισμένα προβλήματα και λύσεις
| Issue | Why it happens | Fix |
|-------|----------------|-----|
| `null` result from `Intersection` | Τα πολύγωνα δεν επικαλύπτονται στην πραγματικότητα. | Επαληθεύστε τις συντεταγμένες ή χρησιμοποιήστε έλεγχο `Intersects` πριν καλέσετε `Intersection`. |
| Unexpected `MultiPolygon` from `SymDifference` | Η συμμετρική διαφορά μπορεί να παράγει διασπαστά στοιχεία. | Κάντε cast σε `IMultiPolygon` και επαναλάβετε όπως φαίνεται. |
| Performance slowdown on large datasets | Κάθε λειτουργία επαναϋπολογίζει τη γεωμετρία από την αρχή. | Επαναχρησιμοποιήστε ενδιάμεσα αποτελέσματα ή απλοποιήστε τις γεωμετρίες με `Simplify()` πριν την επικάλυψη. |

## Συχνές ερωτήσεις

**Q: Μπορώ να χρησιμοποιήσω το Aspose.GIS για .NET στα εμπορικά μου έργα;**  
A: Ναι, μια έγκυρη εμπορική άδεια επιτρέπει απεριόριστη χρήση σε παραγωγικές εφαρμογές.

**Q: Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.GIS για .NET;**  
A: Ναι, μπορείτε να κατεβάσετε δωρεάν δοκιμή από τη [Aspose releases page](https://releases.aspose.com/).

**Q: Πώς μπορώ να λάβω υποστήριξη για το Aspose.GIS για .NET;**  
A: Η υποστήριξη είναι διαθέσιμη μέσω του φόρουμ Aspose GIS [Aspose GIS forum](https://forum.aspose.com/c/gis/33).

**Q: Προσφέρονται προσωρινές άδειες για δοκιμή;**  
A: Ναι, οι προσωρινές άδειες μπορούν να ληφθούν από τη [temporary license page](https://purchase.aspose.com/temporary-license/).

**Q: Πού μπορώ να αγοράσω πλήρη άδεια για το Aspose.GIS για .NET;**  
A: Μπορείτε να αγοράσετε άδεια απευθείας από τον ιστότοπο [Aspose purchase page](https://purchase.aspose.com/buy).

---

**Τελευταία ενημέρωση:** 2026-08-08  
**Δοκιμή με:** Aspose.GIS 24.11 for .NET  
**Συγγραφέας:** Aspose

## Σχετικά Μαθήματα

- [Δημιουργία Πολυγώνου Geometry C# και Έλεγχος Intersection με Aspose.GIS για .NET](/gis/net/geometry-analysis/check-geometries-intersection/)
- [Πώς να εκτελέσετε Ανάλυση Χωρικής Επικάλυψης Γεωμετριών με Aspose.GIS για .NET](/gis/net/geometry-analysis/check-geometries-overlap/)
- [Δημιουργία Buffer Γεωμετρίας χρησιμοποιώντας Aspose.GIS για .NET](/gis/net/geometry-analysis/create-geometry-buffer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}