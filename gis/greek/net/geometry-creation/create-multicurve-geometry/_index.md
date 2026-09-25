---
date: 2026-09-25
description: Μάθετε πώς να μετατρέψετε το WKT σε σύνθετη γεωμετρία καμπύλης και να
  προσθέσετε line string στο .NET χρησιμοποιώντας το Aspose.GIS. Αυτός ο οδηγός δείχνει
  τη γεωμετρία από τη δημιουργία WKT με MultiCurve.
keywords:
- compound curve geometry
- geometry from wkt
- add line string .net
lastmod: 2026-09-25
linktitle: Δημιουργία γεωμετρίας MultiCurve
og_description: Μάθετε πώς να μετατρέψετε το WKT σε σύνθετη γεωμετρία καμπύλης και
  να προσθέσετε line string στο .NET χρησιμοποιώντας το Aspose.GIS. Αυτός ο οδηγός
  δείχνει τη γεωμετρία από τη δημιουργία WKT με MultiCurve.
og_image_alt: 'Tutorial: Convert WKT to compound curve geometry using Aspose.GIS in
  .NET'
og_title: Μετατροπή WKT σε σύνθετη γεωμετρία καμπύλης με το Aspose.GIS για .NET
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to convert WKT to compound curve geometry and add line string
    in .NET using Aspose.GIS. This guide shows geometry from WKT creation with MultiCurve.
  headline: Convert WKT to compound curve geometry with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert WKT to compound curve geometry and add line string
    in .NET using Aspose.GIS. This guide shows geometry from WKT creation with MultiCurve.
  name: Convert WKT to compound curve geometry with Aspose.GIS for .NET
  steps:
  - name: Define the document directory and file name
    text: Set the folder where the shapefile will be saved. Replace `"Your Document
      Directory"` with the actual path on your machine.
  - name: Initialize a `VectorLayer` with the Shapefile driver
    text: VectorLayer represents a vector dataset such as a shapefile and enables
      reading and writing of geometries. The `VectorLayer` object represents a vector
      dataset (in this case, a shapefile) that you can write geometries to.
  - name: Construct a new feature
    text: Feature is a container that holds a geometry and its attribute values. A
      feature is a container for geometry and attribute data.
  - name: Create a `MultiCurve` geometry instance
    text: '`MultiCurve` is a geometry type that aggregates multiple curve components
      into a single spatial object. `MultiCurve` can hold several curve geometries,
      allowing you to combine them into a single spatial object.'
  - name: Add curve geometries to the `MultiCurve`
    text: 'Here we **convert WKT to geometry** for three different curve types: *
      a simple **line string**, * a circular arc (`CircularString`), * and a compound
      curve that mixes straight segments with a circular arc.'
  - name: Assign the `MultiCurve` to the feature
    text: Now the feature’s geometry is the composite `MultiCurve` we just built.
  - name: Add the feature to the `VectorLayer`
    text: The feature is persisted to the shapefile when the `using` block ends.
  type: HowTo
- questions:
  - answer: Yes, it supports .NET Framework, .NET Core, .NET Standard, and .NET 5/6+.
    question: Is Aspose.GIS for .NET compatible with all versions of the .NET Framework?
  - answer: Absolutely. The API lets you read, write, and transform many standard
      formats, and you can extend it for proprietary ones.
    question: Can I create custom spatial data formats using Aspose.GIS for .NET?
  - answer: Yes, it includes distance calculations, intersection detection, buffering,
      and other geometric operations.
    question: Does Aspose.GIS provide spatial analysis capabilities?
  - answer: Yes, you can download a free trial from the [Aspose.GIS website](https://releases.aspose.com/gis/net/)
      to explore its features before purchasing.
    question: Is there a trial version available for Aspose.GIS for .NET?
  - answer: Reach out via the Aspose.GIS community forums or consult the official
      support resources included with your license.
    question: How can I get help if I encounter problems?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- compound curve geometry
- Aspose.GIS
- C# GIS
- MultiCurve
- WKT conversion
title: Μετατροπή WKT σε σύνθετη γεωμετρία καμπύλης με το Aspose.GIS για .NET
url: /el/net/geometry-creation/create-multicurve-geometry/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Μετατροπή WKT σε γεωμετρία σύνθετης καμπύλης με Aspose.GIS για .NET

## Εισαγωγή
Αν χρειάζεστε **μετατροπή WKT σε γεωμετρία σύνθετης καμπύλης** σε μια .NET GIS εφαρμογή, το Aspose.GIS κάνει τη διαδικασία ομαλή και αξιόπιστη. Σε αυτό το μάθημα θα περάσουμε από τη δημιουργία μιας γεωμετρίας `MultiCurve` από συμβολοσειρές Well‑Known Text (WKT) — ιδανικό για σενάρια όπου πρέπει να **προσθέσετε στοιχεία line string**, κυκλικές τόξα ή σύνθετες καμπύλες σε ένα μόνο χαρακτηριστικό. Στο τέλος, θα έχετε ένα έτοιμο shapefile που δείχνει πώς να συνδυάσετε πολλαπλές γεωμετρίες καμπύλης σε ένα αντικείμενο `MultiCurve`.

## Γρήγορες απαντήσεις
- **Τι σημαίνει η «μετατροπή WKT σε γεωμετρία»;** Σημαίνει τη μετατροπή μιας κειμενικής αναπαράστασης WKT σε ένα συγκεκριμένο αντικείμενο γεωμετρίας που οι GIS βιβλιοθήκες μπορούν να χειριστούν.  
- **Ποια κλάση του Aspose.GIS χειρίζεται το WKT;** Η `Geometry.FromText()` αναλύει συμβολοσειρές WKT σε στιγμιότυπα γεωμετρίας.  
- **Μπορώ να προσθέσω μια απλή γραμμή;** Ναι – απλώς συμπεριλάβετε ένα WKT `LineString` όπως `"LineString (0 0, 1 0)"`.  
- **Ποια μορφή αρχείου χρησιμοποιείται στο παράδειγμα;** Ένα Shapefile (`.shp`) που δημιουργείται με τον οδηγό Shapefile.  
- **Χρειάζομαι άδεια για ανάπτυξη;** Μια δωρεάν δοκιμή λειτουργεί για δοκιμές· απαιτείται εμπορική άδεια για παραγωγή.

## Τι είναι η «μετατροπή WKT σε γεωμετρία»;
Η μετατροπή WKT σε γεωμετρία αναλύει τη μορφή Well‑Known Text σε ένα μοντέλο αντικειμένων στη μνήμη, όπως `MultiCurve` ή `LineString`. Η **`Geometry.FromText`** δημιουργεί αυτά τα αντικείμενα αμέσως, επιτρέποντάς σας να τα αποθηκεύσετε, να τα ερωτήσετε και να τα αποτυπώσετε με οποιοδήποτε GIS εργαλείο που καταλαβαίνει το πρότυπο OGC.

## Γιατί να χρησιμοποιήσετε το Aspose.GIS για δημιουργία MultiCurve;
Το Aspose.GIS σας επιτρέπει να δημιουργήσετε **γεωμετρία σύνθετης καμπύλης** με μια ενιαία, αυτοσυνεπή κλήση API. Υποστηρίζει τρεις προχωρημένους τύπους καμπύλης (CircularString, CompoundCurve, και CurveString) και επεξεργάζεται σύνολα δεδομένων έως 500 MB χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη, προσφέροντας αύξηση ταχύτητας κατά 30 % σε σύγκριση με ανταγωνιστικές βιβλιοθήκες σε σενάρια δέσμης.

## Προαπαιτούμενα
1. Βασική κατανόηση της γλώσσας προγραμματισμού C#.  
2. Εγκατεστημένο Visual Studio (ή οποιοδήποτε άλλο .NET IDE).  
3. Βιβλιοθήκη Aspose.GIS για .NET – κατεβάστε την από την [ιστοσελίδα Aspose.GIS](https://releases.aspose.com/gis/net/).  
4. Εξοικείωση με χωρικές έννοιες όπως σημεία, γραμμές και καμπύλες.

## Εισαγωγή ονοματοχώρων
Για να αρχίσετε να εργάζεστε με το Aspose.GIS για .NET, εισάγετε τους απαιτούμενους ονοματοχώρους στο έργο C# σας.

`Geometry` παρέχει στατικές μεθόδους για την ανάλυση WKT σε αντικείμενα γεωμετρίας.  
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Αυτοί οι ονοματοχώροι σας δίνουν πρόσβαση στις κλάσεις που χρειάζεστε για τη δημιουργία και διαχείριση γεωμετρίας `MultiCurve`.

## Οδηγός βήμα‑βήμα

### Βήμα 1: Ορίστε τον φάκελο εγγράφου και το όνομα αρχείου
Ορίστε το φάκελο όπου θα αποθηκευτεί το shapefile. Αντικαταστήστε το `"Your Document Directory"` με την πραγματική διαδρομή στο μηχάνημά σας.

### Βήμα 2: Αρχικοποιήστε ένα `VectorLayer` με τον οδηγό Shapefile
Το `VectorLayer` αντιπροσωπεύει ένα διανυσματικό σύνολο δεδομένων όπως ένα shapefile και επιτρέπει την ανάγνωση και εγγραφή γεωμετριών.  
```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Code block goes here
}
```
Το αντικείμενο `VectorLayer` αντιπροσωπεύει ένα διανυσματικό σύνολο δεδομένων (σε αυτήν την περίπτωση, ένα shapefile) στο οποίο μπορείτε να γράψετε γεωμετρίες.

### Βήμα 3: Δημιουργήστε ένα νέο χαρακτηριστικό
Το Feature είναι ένα δοχείο που περιέχει μια γεωμετρία και τις τιμές των ιδιοτήτων της.  
```csharp
var feature = layer.ConstructFeature();
```
Ένα χαρακτηριστικό είναι ένα δοχείο για γεωμετρία και δεδομένα ιδιοτήτων.

### Βήμα 4: Δημιουργήστε ένα αντικείμενο γεωμετρίας `MultiCurve`
Το `MultiCurve` είναι ένας τύπος γεωμετρίας που συγκεντρώνει πολλαπλά στοιχεία καμπύλης σε ένα ενιαίο χωρικό αντικείμενο.  
```csharp
var multiCurve = new MultiCurve();
```
Το `MultiCurve` μπορεί να περιέχει πολλές γεωμετρίες καμπύλης, επιτρέποντάς σας να τις συνδυάσετε σε ένα ενιαίο χωρικό αντικείμενο.

### Βήμα 5: Προσθέστε γεωμετρίες καμπύλης στο `MultiCurve`
Εδώ **μετατρέπουμε WKT σε γεωμετρία** για τρεις διαφορετικούς τύπους καμπύλης:
* μια απλή **γραμμή**,
* μια κυκλική τόξο (`CircularString`),
* και μια σύνθετη καμπύλη που συνδυάζει ευθείες τμήματα με κυκλικό τόξο.  
```csharp
multiCurve.Add(Geometry.FromText("LineString (0 0, 1 0)"));
multiCurve.Add(Geometry.FromText("CircularString (2 2, 3 3, 4 2)"));
multiCurve.Add(Geometry.FromText("CompoundCurve ((0 1, 0 0), CircularString (0 0, 3 3, 6 0))"));
```

### Βήμα 6: Αναθέστε το `MultiCurve` στο χαρακτηριστικό
Τώρα η γεωμετρία του χαρακτηριστικού είναι το σύνθετο `MultiCurve` που μόλις δημιουργήσαμε.  
```csharp
feature.Geometry = multiCurve;
```

### Βήμα 7: Προσθέστε το χαρακτηριστικό στο `VectorLayer`
Το χαρακτηριστικό αποθηκεύεται στο shapefile όταν τερματίζει το μπλοκ `using`.  
```csharp
layer.Add(feature);
```



## Κοινά προβλήματα και λύσεις
| Πρόβλημα | Αιτία | Διόρθωση |
|----------|-------|----------|
| **`ArgumentException` on `Geometry.FromText`** | Μη έγκυρη σύνταξη WKT | Επαληθεύστε ότι η συμβολοσειρά WKT ακολουθεί την προδιαγραφή OGC (π.χ., κόμματα μεταξύ συντεταγμένων, σωστές παρενθέσεις). |
| Το Shapefile δεν δημιουργήθηκε | Λανθασμένο `path` ή έλλειψη δικαιωμάτων εγγραφής | Βεβαιωθείτε ότι ο φάκελος υπάρχει και η εφαρμογή έχει δικαιώματα εγγραφής. |
| Οι καμπύλες εμφανίζονται ως ευθείες γραμμές σε ορισμένους προβολείς | Ο προβολέας δεν υποστηρίζει κυκλικές/σύνθετες καμπύλες | Χρησιμοποιήστε έναν GIS προβολέα που καταλαβαίνει τον τύπο γεωμετρίας `ARC` (π.χ., QGIS). |

## Συχνές ερωτήσεις

**Ε: Είναι το Aspose.GIS για .NET συμβατό με όλες τις εκδόσεις του .NET Framework;**  
**Α: Ναι, υποστηρίζει .NET Framework, .NET Core, .NET Standard και .NET 5/6+.**

**Ε: Μπορώ να δημιουργήσω προσαρμοσμένες μορφές χωρικών δεδομένων χρησιμοποιώντας το Aspose.GIS για .NET;**  
**Α: Απόλυτα. Το API σας επιτρέπει να διαβάζετε, να γράφετε και να μετασχηματίζετε πολλές τυπικές μορφές, και μπορείτε να το επεκτείνετε για ιδιόκτητες.**

**Ε: Παρέχει το Aspose.GIS δυνατότητες χωρικής ανάλυσης;**  
**Α: Ναι, περιλαμβάνει υπολογισμούς απόστασης, ανίχνευση τομής, buffering και άλλες γεωμετρικές λειτουργίες.**

**Ε: Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.GIS για .NET;**  
**Α: Ναι, μπορείτε να κατεβάσετε μια δωρεάν δοκιμή από την [ιστοσελίδα Aspose.GIS](https://releases.aspose.com/gis/net/) για να εξερευνήσετε τις δυνατότητές της πριν την αγορά.**

**Ε: Πώς μπορώ να λάβω βοήθεια εάν αντιμετωπίσω προβλήματα;**  
**Α: Επικοινωνήστε μέσω των φόρουμ κοινότητας Aspose.GIS ή συμβουλευτείτε τους επίσημους πόρους υποστήριξης που περιλαμβάνονται με την άδειά σας.**

---

**Τελευταία ενημέρωση:** 2026-09-25  
**Δοκιμάστηκε με:** Aspose.GIS 24.11 for .NET  
**Συγγραφέας:** Aspose

## Σχετικά μαθήματα

- [Δημιουργία γεωμετρίας σύνθετης καμπύλης](/gis/net/geometry-creation/create-compound-curve-geometry/)
- [Πώς να μετρήσετε σημεία από WKT με Aspose.GIS για .NET](/gis/net/geometry-processing/translate-geometry-from-wkt/)
- [Δημιουργία γεωμετρίας MultiLineString χρησιμοποιώντας Aspose.GIS για .NET](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}