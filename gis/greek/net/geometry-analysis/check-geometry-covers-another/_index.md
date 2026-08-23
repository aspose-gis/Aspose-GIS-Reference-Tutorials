---
date: 2026-08-03
description: Μάθετε πώς να δημιουργήσετε linestring c# με Aspose.GIS για .NET, προσθέστε
  σημεία σε ένα linestring και εκτελέστε έλεγχο point on line χρησιμοποιώντας τη μέθοδο
  covers.
keywords:
- create linestring c#
- point on line check
- add points to linestring
- use covers method
lastmod: 2026-08-03
linktitle: Δημιουργία linestring c# – Έλεγχος geometry καλύπτει άλλη
og_description: Δημιουργήστε linestring c# και επαληθεύστε point on line χρησιμοποιώντας
  τη μέθοδο Aspose.GIS covers. Μάθετε ακριβείς ελέγχους geometry για εφαρμογές .NET.
  (150‑160 χαρακτήρες)
og_image_alt: Developer guide showing linestring creation and covers check in C# with
  Aspose.GIS
og_title: Δημιουργία linestring c# – Έλεγχος geometry καλύπτει άλλη (50‑60 χαρακτήρες)
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to create linestring c# with Aspose.GIS for .NET, add points
    to a linestring, and perform a point on line check using the covers method.
  headline: Create linestring c# – Check geometry covers another
  type: TechArticle
- description: Learn how to create linestring c# with Aspose.GIS for .NET, add points
    to a linestring, and perform a point on line check using the covers method.
  name: Create linestring c# – Check geometry covers another
  steps:
  - name: create a linestring object
    text: The `LineString` class represents a sequence of points connected by straight
      line segments in a two‑dimensional plane. Here, we instantiate a new `LineString`
      object, which represents a sequence of connected line segments in a two‑dimensional
      space.
  - name: add points to linestring
    text: '`AddPoint` appends a coordinate pair to the end of the `LineString` collection,
      preserving the order of insertion. We **add points to linestring** using the
      `AddPoint` method. In this example, we add two points: (0, 0) and (1, 1), forming
      a simple diagonal line segment.'
  - name: create a point object
    text: The `Point` class models a single location in a two‑dimensional coordinate
      system. Instantiate a `Point` object representing a single point in a two‑dimensional
      space. Here, we create a point at coordinates (0, 0).
  - name: perform a point on line check – does the line cover the point?
    text: '`Covers` determines whether the first geometry completely contains the
      second geometry, returning true only when every point of the second geometry
      lies inside the first. Use the `Covers` method to check if the line covers the
      point. In this case, it returns `True` because the point (0, 0) lies exac'
  - name: verify the reverse relationship – is the point covered by the line?
    text: '`CoveredBy` is the inverse of `Covers`; it returns true when the invoking
      geometry is entirely inside the target geometry. Similarly, use the `CoveredBy`
      method to check if the point is covered by the line. Since the point (0, 0)
      lies on the line, it also returns `True`.'
  type: HowTo
- questions:
  - answer: Yes, you can use Aspose.GIS for .NET in both commercial and non‑commercial
      projects after obtaining the appropriate license.
    question: Can I use Aspose.GIS for .NET in my commercial projects?
  - answer: Yes, Aspose.GIS for .NET is compatible with both .NET Framework and .NET
      Core environments.
    question: Is Aspose.GIS for .NET compatible with .NET Core?
  - answer: Yes, Aspose.GIS for .NET supports a wide range of GIS formats including
      Shapefile, GeoJSON, KML, and more.
    question: Does Aspose.GIS for .NET support various GIS formats?
  - answer: Aspose.GIS for .NET is a proprietary library developed by Aspose, so external
      contributions are not accepted. However, you can provide feedback and suggestions
      to improve the library.
    question: Can I contribute to the development of Aspose.GIS for .NET?
  - answer: Updates for Aspose.GIS for .NET are released regularly to introduce new
      features, enhancements, and bug fixes. Check the [website](https://releases.aspose.com/gis/net/)
      for the latest releases.
    question: How often are updates released for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- create linestring
- Aspose.GIS
- C# geometry analysis
title: Δημιουργία linestring c# – Έλεγχος geometry καλύπτει άλλη
url: /el/net/geometry-analysis/check-geometry-covers-another/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Έλεγχος γεωμετρίας που καλύπτει άλλη

## Εισαγωγή
Σε αυτό το tutorial θα μάθετε **πώς να δημιουργήσετε linestring c#** χρησιμοποιώντας το Aspose.GIS για .NET, να προσθέτετε σημεία σε ένα linestring και να εκτελείτε έναν αξιόπιστο **έλεγχο σημείου πάνω σε γραμμή** με τις μεθόδους `Covers` και `CoveredBy`. Είτε δημιουργείτε ένα εργαλείο χαρτογράφησης, εκτελείτε χωρική ανάλυση, είτε απλώς χρειάζεστε επαλήθευση γεωμετρικών σχέσεων, η κατανόηση αυτών των λειτουργιών θα δώσει στην εφαρμογή σας την απαιτούμενη ακρίβεια.

## Γρήγορες απαντήσεις
- **Τι σημαίνει “create linestring c#”;** Σημαίνει τη δημιουργία ενός αντικειμένου γεωμετρίας `LineString` και την πληρότητά του με σημεία συντεταγμένων.  
- **Ποια μέθοδος ελέγχει αν ένα σημείο βρίσκεται πάνω σε γραμμή;** Χρησιμοποιήστε τη μέθοδο `Covers` στο `LineString` ή `CoveredBy` στο `Point`.  
- **Χρειάζομαι άδεια για να εκτελέσω το παράδειγμα;** Μια προσωρινή άδεια λειτουργεί για αξιολόγηση· απαιτείται πλήρης άδεια για παραγωγή.  
- **Μπορεί να χρησιμοποιηθεί με .NET Core;** Ναι, το Aspose.GIS υποστηρίζει .NET Framework και .NET Core.  
- **Πόσα σημεία μπορώ να προσθέσω σε ένα linestring;** Δεν υπάρχει σκληρός περιορισμός· μπορείτε να προσθέσετε όσα σημεία χρειάζεστε για την χωρική ανάλυση.

## Τι είναι η δημιουργία linestring c#;
Ένα `LineString` είναι ένα γεωμετρικό σχήμα που αποτελείται από μια διατεταγμένη λίστα σημείων συνδεδεμένων με ευθείες γραμμές. Στην C# το δημιουργείτε δημιουργώντας μια παρουσία της κλάσης `LineString` από το namespace `Aspose.Gis.Geometries` και στη συνέχεια **προσθέτετε σημεία στο linestring** χρησιμοποιώντας τη μέθοδο `AddPoint`. Αυτό το αντικείμενο λειτουργεί ως βάση για οποιαδήποτε γραμμική χωρική ανάλυση, όπως χαρτογράφηση διαδρομών ή εντοπισμός δικτύου.

## Γιατί να χρησιμοποιήσετε Aspose.GIS για έλεγχο σημείου πάνω σε γραμμή;
`Covers` είναι μια μέθοδος χωρικού προδιαγραφέα που επιστρέφει true όταν η πρώτη γεωμετρία περιέχει πλήρως τη δεύτερη γεωμετρία.  
Το Aspose.GIS παρέχει μια ντετερμινιστική, υψηλής ακρίβειας υλοποίηση των χωρικών προδιαγραφέων. Υποστηρίζει πάνω από 50 μορφές GIS εισόδου και εξόδου, μπορεί να διαχειριστεί δίκτυα γραμμών εκατοντάδων χιλιομέτρων χωρίς να φορτώνει ολόκληρο το σύνολο δεδομένων στη μνήμη, και λειτουργεί σε .NET Framework, .NET Core και .NET 5/6+. Η χρήση της μεθόδου `Covers` εγγυάται ότι λαμβάνονται υπόψη τα σφάλματα στρογγυλοποίησης κινητής υποδιαστολής, παρέχοντας αξιόπιστα αποτελέσματα σημείου‑πάνω‑σε‑γραμμή ακόμη και σε απαιτητικά επιχειρηματικά σενάρια.

## Προαπαιτούμενα
Πριν ξεκινήσετε τη χρήση του Aspose.GIS για .NET, βεβαιωθείτε ότι έχετε ρυθμίσει τα παρακάτω προαπαιτούμενα:

### 1. Εγκατάσταση Visual Studio
Βεβαιωθείτε ότι έχετε εγκαταστήσει το Visual Studio στο σύστημά σας. Το Aspose.GIS για .NET ενσωματώνεται άψογα με το Visual Studio, παρέχοντας μια ομαλή εμπειρία ανάπτυξης.

### 2. Απόκτηση Aspose.GIS για .NET
Κατεβάστε τη βιβλιοθήκη Aspose.GIS για .NET από την [ιστοσελίδα](https://releases.aspose.com/gis/net/). Μπορείτε είτε να κατεβάσετε τη βιβλιοθήκη απευθείας είτε να χρησιμοποιήσετε έναν διαχειριστή πακέτων όπως το NuGet για να την εγκαταστήσετε στο έργο σας.

### 3. Εξοικείωση με .NET Framework
Βασικές γνώσεις του .NET framework και της γλώσσας προγραμματισμού C# είναι απαραίτητες για την αποτελεσματική χρήση του Aspose.GIS για .NET.

### 4. Πρόσβαση σε τεκμηρίωση και υποστήριξη
Ανατρέξτε στην [τεκμηρίωση](https://reference.aspose.com/gis/net/) για λεπτομερείς πληροφορίες σχετικά με τα APIs και τις λειτουργίες του Aspose.GIS. Σε περίπτωση που αντιμετωπίσετε προβλήματα ή έχετε ερωτήσεις, χρησιμοποιήστε το [φόρουμ Aspose.GIS](https://forum.aspose.com/c/gis/33) για βοήθεια.

### 5. Προαιρετικό: προσωρινή άδεια
Αν εξερευνάτε το Aspose.GIS για .NET, μπορείτε να αποκτήσετε μια προσωρινή άδεια από τη [σελίδα προσωρινής άδειας](https://purchase.aspose.com/temporary-license/) για να αξιολογήσετε τις δυνατότητες της βιβλιοθήκης.

## Εισαγωγή ονομάτων χώρων
Πριν χρησιμοποιήσετε το Aspose.GIS για .NET στο έργο σας, πρέπει να εισάγετε τα απαραίτητα namespaces:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Τώρα, ας αναλύσουμε το παράδειγμα σε πολλαπλά βήματα για να κατανοήσουμε πώς να **ελέγξετε αν μια γεωμετρία καλύπτει άλλη** χρησιμοποιώντας το Aspose.GIS για .NET.

## Πώς να δημιουργήσετε linestring c# – οδηγός βήμα‑βήμα
Φορτώστε το έργο σας, εισάγετε τα απαιτούμενα namespaces και, στη συνέχεια, ακολουθήστε τα πέντε σύντομα βήματα παρακάτω. Σε λίγες μόνο γραμμές κώδικα θα έχετε ένα αντικείμενο `LineString`, ένα αντικείμενο `Point` και δύο ελέγχους boolean που θα σας δείξουν αν η γραμμή καλύπτει το σημείο και αν το σημείο καλύπτεται από τη γραμμή.

### Βήμα 1: δημιουργία αντικειμένου linestring
Η κλάση `LineString` αντιπροσωπεύει μια ακολουθία σημείων συνδεδεμένων με ευθείες γραμμές σε ένα δισδιάστατο επίπεδο.  
```csharp
var line = new LineString();
```
Εδώ, δημιουργούμε μια νέα αντικείμενο `LineString`, το οποίο αντιπροσωπεύει μια ακολουθία συνδεδεμένων τμημάτων γραμμής σε δισδιάστατο χώρο.

### Βήμα 2: προσθήκη σημείων στο linestring
`AddPoint` προσθέτει ένα ζεύγος συντεταγμένων στο τέλος της συλλογής `LineString`, διατηρώντας τη σειρά εισαγωγής.  
```csharp
line.AddPoint(0, 0);
line.AddPoint(1, 1);
```
**Προσθέτουμε σημεία στο linestring** χρησιμοποιώντας τη μέθοδο `AddPoint`. Σε αυτό το παράδειγμα, προσθέτουμε δύο σημεία: (0, 0) και (1, 1), σχηματίζοντας ένα απλό διαγώνιο τμήμα γραμμής.

### Βήμα 3: δημιουργία αντικειμένου point
Η κλάση `Point` μοντελοποιεί μια μοναδική θέση σε ένα δισδιάστατο σύστημα συντεταγμένων.  
```csharp
var point = new Point(0, 0);
```
Δημιουργήστε ένα αντικείμενο `Point` που αντιπροσωπεύει ένα μοναδικό σημείο σε δισδιάστατο χώρο. Εδώ, δημιουργούμε ένα σημείο στις συντεταγμένες (0, 0).

### Βήμα 4: εκτέλεση ελέγχου σημείου πάνω σε γραμμή – καλύπτει η γραμμή το σημείο;
`Covers` καθορίζει αν η πρώτη γεωμετρία περιέχει πλήρως τη δεύτερη γεωμετρία, επιστρέφοντας true μόνο όταν κάθε σημείο της δεύτερης γεωμετρίας βρίσκεται μέσα στην πρώτη.  
```csharp
Console.WriteLine(line.Covers(point));    // True
```
Χρησιμοποιήστε τη μέθοδο `Covers` για να ελέγξετε αν η γραμμή καλύπτει το σημείο. Σε αυτήν την περίπτωση, επιστρέφει `True` επειδή το σημείο (0, 0) βρίσκεται ακριβώς πάνω στη γραμμή.

### Βήμα 5: επαλήθευση της αντίστροφης σχέσης – καλύπτεται το σημείο από τη γραμμή;
`CoveredBy` είναι το αντίστροφο του `Covers`; επιστρέφει true όταν η κλήση γεωμετρία βρίσκεται εντελώς μέσα στη στοχευόμενη γεωμετρία.  
```csharp
Console.WriteLine(point.CoveredBy(line)); // True
```
Ανάλογα, χρησιμοποιήστε τη μέθοδο `CoveredBy` για να ελέγξετε αν το σημείο καλύπτεται από τη γραμμή. Δεδομένου ότι το σημείο (0, 0) βρίσκεται πάνω στη γραμμή, επιστρέφει επίσης `True`.

## Συνηθισμένα προβλήματα και λύσεις
| Πρόβλημα | Γιατί συμβαίνει | Διόρθωση |
|----------|-----------------|----------|
| `line.Covers(point)` επιστρέφει `False` παρόλο που το σημείο φαίνεται πάνω στη γραμμή | Οι συντεταγμένες του σημείου δεν είναι ακριβώς ίδιες λόγω ακρίβειας κινητής υποδιαστολής. | Χρησιμοποιήστε `Math.Round` στις συντεταγμένες ή εφαρμόστε έλεγχο βασισμένο σε ανοχή με `line.Distance(point) < epsilon`. |
| Λείπει `using Aspose.Gis.Geometries;` | Το namespace δεν έχει εισαχθεί, προκαλώντας σφάλματα μεταγλώττισης. | Βεβαιωθείτε ότι η δήλωση εισαγωγής υπάρχει (δείτε την ενότητα **Εισαγωγή ονομάτων χώρων**). |
| Εξαίρεση άδειας κατά την εκτέλεση | Δεν έχει φορτωθεί έγκυρη άδεια για παραγωγή. | Φορτώστε μια προσωρινή ή πλήρη άδεια χρησιμοποιώντας `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Συχνές ερωτήσεις

**Q: Μπορώ να χρησιμοποιήσω το Aspose.GIS για .NET στα εμπορικά μου έργα;**  
A: Ναι, μπορείτε να χρησιμοποιήσετε το Aspose.GIS για .NET τόσο σε εμπορικά όσο και σε μη εμπορικά έργα μετά την απόκτηση της κατάλληλης άδειας.

**Q: Είναι το Aspose.GIS για .NET συμβατό με .NET Core;**  
A: Ναι, το Aspose.GIS για .NET είναι συμβατό με περιβάλλοντα τόσο .NET Framework όσο και .NET Core.

**Q: Υποστηρίζει το Aspose.GIS για .NET διάφορες μορφές GIS;**  
A: Ναι, το Aspose.GIS για .NET υποστηρίζει ένα ευρύ φάσμα μορφών GIS, συμπεριλαμβανομένων των Shapefile, GeoJSON, KML και άλλων.

**Q: Μπορώ να συνεισφέρω στην ανάπτυξη του Aspose.GIS για .NET;**  
A: Το Aspose.GIS για .NET είναι μια ιδιόκτητη βιβλιοθήκη που αναπτύσσεται από την Aspose, επομένως δεν γίνονται δεκτές εξωτερικές συνεισφορές. Ωστόσο, μπορείτε να παρέχετε σχόλια και προτάσεις για τη βελτίωση της βιβλιοθήκης.

**Q: Πόσο συχνά κυκλοφορούν ενημερώσεις για το Aspose.GIS για .NET;**  
A: Οι ενημερώσεις για το Aspose.GIS για .NET κυκλοφορούν τακτικά για την εισαγωγή νέων λειτουργιών, βελτιώσεων και διορθώσεων σφαλμάτων. Ελέγξτε την [ιστοσελίδα](https://releases.aspose.com/gis/net/) για τις τελευταίες εκδόσεις.

## Συμπέρασμα
Ακολουθώντας τα παραπάνω βήματα, τώρα ξέρετε πώς να **δημιουργήσετε linestring c#**, **προσθέσετε σημεία στο linestring**, και να εκτελέσετε έναν αξιόπιστο **έλεγχο σημείου πάνω σε γραμμή** χρησιμοποιώντας τις μεθόδους `Covers` και `CoveredBy`. Αυτή η δυνατότητα ενισχύει τις λειτουργίες χωρικής ανάλυσης του λογισμικού σας και ανοίγει το δρόμο για πιο προχωρημένες λειτουργίες GIS, όπως η επαλήθευση διαδρομών, έλεγχοι τοπολογίας δικτύου και ερωτήματα εγγύτητας.

---

**Τελευταία ενημέρωση:** 2026-08-03  
**Δοκιμή με:** Aspose.GIS for .NET (τελευταία έκδοση)  
**Συγγραφέας:** Aspose

{{< blocks/products/products-backtop-button >}}

## Σχετικά Μαθήματα

- [Μάθετε πώς να δημιουργήσετε γεωμετρία LineString με Aspose.GIS για .NET](/gis/net/geometry-creation/create-linestring-geometry/)
- [Πώς να προσθέσετε σημείο σε LineString και να μετατρέψετε τη γεωμετρία σε επεξεργάσιμη μορφή με Aspose.GIS](/gis/net/geometry-creation/convert-geometry-to-editable/)
- [point inside polygon c# – Έλεγχος αν η γεωμετρία περιέχει άλλη](/gis/net/geometry-analysis/check-geometry-contains-another/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}