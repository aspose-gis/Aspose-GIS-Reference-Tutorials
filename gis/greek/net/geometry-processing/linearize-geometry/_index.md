---
date: 2026-09-10
description: Μάθετε πώς να μετατρέπετε τις καμπύλες σε γραμμές (linearize geometry)
  χρησιμοποιώντας το Aspose.GIS for .NET, επιτρέποντας αποδοτική επεξεργασία και ανάλυση
  γεωχωρικών δεδομένων στις .NET εφαρμογές σας.
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS .NET
lastmod: 2026-09-10
linktitle: Linearize a Geometry
og_description: Μετατρέψτε τις καμπύλες σε γραμμές (linearize geometry) χρησιμοποιώντας
  το Aspose.GIS for .NET. Μάθετε step‑by‑step πώς να simplify geometries για ταχύτερη
  rendering και ευρύτερη compatibility.
og_image_alt: Guide showing how to linearize curved geometries to straight lines using
  Aspose.GIS in a .NET application
og_title: Μετατροπή καμπυλών σε γραμμές με το Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  headline: How to Convert Curves to Lines with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  name: How to Convert Curves to Lines with Aspose.GIS for .NET
  steps:
  - name: Define the output path
    text: '`Path.Combine` builds a platform‑independent file path, handling Windows
      backslashes and Unix forward slashes automatically. Replace `"Your Document
      Directory"` with the folder where you want the KML file saved.'
  - name: Create a layer for the output file
    text: A *layer* groups geographic features of the same type. Here we instantiate
      a new KML layer that will store the linearized geometry.
  - name: Construct a new feature
    text: A *feature* represents a single geographic object (point, line, polygon,
      etc.). We’ll attach our linear geometry to this feature.
  - name: Define the original complex geometry
    text: '`Geometry.FromWkt` parses a Well‑Known Text (WKT) string into a geometry
      object. The sample WKT includes a `LineString`, a `CompoundCurve`, and a `CircularString`
      to showcase curve handling.'
  - name: Convert curves to lines
    text: '`ToLinearGeometry()` tessellates every curve in the source geometry into
      straight‑line segments, returning a new linear geometry that retains any Z‑coordinates.'
  - name: Assign the linear geometry to the feature
    text: The feature’s `Geometry` property now holds the simplified, linear version
      of the original shape.
  - name: Add the feature to the layer
    text: Adding the feature to the KML layer queues it for writing; when the `using`
      block ends, the layer flushes the data to the output file.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS works with .NET Core, enabling cross‑platform applications.
    question: Is Aspose.GIS for .NET compatible with .NET Core?
  - answer: Absolutely! The library supports KML, Shapefile, GeoJSON, and many more
      formats—over 30 in total.
    question: Can I work with different GIS file formats using Aspose.GIS for .NET?
  - answer: Yes, it provides a wide range of spatial functions, from buffering to
      spatial joins.
    question: Does Aspose.GIS offer spatial operations and analysis?
  - answer: Yes, you can download a free trial from the [Aspose.GIS website](https://releases.aspose.com/gis/net/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      and staff support.
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert curves to lines
- Aspose.GIS
- .NET GIS processing
title: Πώς να μετατρέψετε τις καμπύλες σε γραμμές με το Aspose.GIS for .NET
url: /el/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Μετατροπή καμπυλών σε γραμμές (γραμμικοποίηση γεωμετρίας) με Aspose.GIS για .NET

## Εισαγωγή
Αν χρειάζεστε **convert curves to lines** για χαρτογράφηση, χωρική ανάλυση ή εργασίες ανταλλαγής δεδομένων, το Aspose.GIS για .NET σας παρέχει έναν καθαρό, προγραμματιστικό τρόπο για να το κάνετε. Σε αυτό το tutorial θα περάσουμε από ένα πλήρες, πραγματικό παράδειγμα που δείχνει πώς να πάρετε μια σύνθετη γεωμετρία—που περιέχει καμπύλες και σύνθετα σχήματα—και να τη μετατρέψετε σε μια απλή γραμμική αναπαράσταση που λειτουργεί με οποιοδήποτε σύστημα GIS.

## Γρήγορες απαντήσεις
- **Τι σημαίνει “convert curves to lines”;** Μετατρέπει τις καμπυλωτές γεωμετρίες σε ευθείες γραμμές.  
- **Γιατί να επιλέξετε το Aspose.GIS;** Η βιβλιοθήκη υποστηρίζει πάνω από 30 μορφές GIS και διαχειρίζεται τη μετατροπή γεωμετρίας χωρίς εξωτερικά εργαλεία.  
- **Τι χρειάζομαι εκ των προτέρων;** .NET Framework ή .NET Core, Visual Studio (ή οποιοδήποτε IDE C#), και το πακέτο NuGet Aspose.GIS.  
- **Πόσο χρόνο θα χρειαστεί το δείγμα;** Λιγότερο από πέντε λεπτά μόλις εγκατασταθεί η βιβλιοθήκη.  
- **Μπορώ να εξάγω σε άλλες μορφές;** Απόλυτα—αντικαταστήστε τον οδηγό KML με Shapefile, GeoJSON κ.λπ.  
Μπορείτε να κατεβάσετε το πλήρες σύνολο προϊόντων από την [Aspose website](https://releases.aspose.com/).

## Τι σημαίνει η μετατροπή καμπυλών σε γραμμές;
Η μετατροπή καμπυλών σε γραμμές (επίσης γνωστή ως **linearizing geometry**) αντικαθιστά κάθε καμπυλωτό τμήμα με μια σειρά από σύντομα ευθύγραμμα τμήματα, δημιουργώντας μια *γραμμική γεωμετρία*. Αυτό κάνει την απόδοση έως πέντε φορές πιο γρήγορη, μειώνει την κατανάλωση μνήμης και εξασφαλίζει ότι τα δεδομένα μπορούν να χρησιμοποιηθούν από παλαιές υπηρεσίες GIS που δέχονται μόνο γραμμικά χαρακτηριστικά.

## Γιατί να μετατρέψετε τις καμπύλες σε γραμμές;
Οι γραμμικές γεωμετρίες αποδίδουν και ερωτούνται έως **5× πιο γρήγορα** από τις καμπυλωτές τους, και **30+ πλατφόρμες GIS** δέχονται μόνο γραμμικά χαρακτηριστικά. Η απλοποίηση της γεωμετρίας επίσης μειώνει το μέγεθος του αρχείου για προεπισκοπήσεις στο web και ενεργοποιεί αλγόριθμους—όπως η ανάλυση δικτύων ή η ομαδοποίηση—που απαιτούν είσοδο ευθύγραμμων τμημάτων.

## Πώς να γραμμικοποιήσετε τη γεωμετρία;
Χρησιμοποιήστε τη μέθοδο `ToLinearGeometry()` που παρέχεται από το Aspose.GIS. Αυτή αυτόματα τριγωνοποιεί κάθε καμπύλη σε μια γεωμετρία σε ευθύγραμμα τμήματα διατηρώντας τυχόν τιμές Z, ώστε να έχετε μια γραμμική προσέγγιση χωρίς να χάνετε δεδομένα υψομέτρου. Μπορείτε επίσης να ορίσετε μια ανοχή για να ελέγξετε την μέγιστη απόκλιση μεταξύ της αρχικής καμπύλης και των παραγόμενων τμημάτων, επιτρέποντάς σας να ισορροπήσετε την ακρίβεια με το μέγεθος του αρχείου. Η μέθοδος λειτουργεί για γεωμετρίες 2‑Δ και 3‑Δ.

## Προαπαιτούμενα
Πριν βυθιστείτε στον κώδικα, βεβαιωθείτε ότι έχετε:

1. **Aspose.GIS for .NET** – κατεβάστε το από την [Aspose.GIS website](https://releases.aspose.com/gis/net/).  
2. **.NET Framework** (ή .NET Core) εγκατεστημένο στο μηχάνημα ανάπτυξης.  
3. **Visual Studio** (ή οποιοδήποτε IDE συμβατό με C#) για τη συγγραφή και εκτέλεση του δείγματος.

## Εισαγωγή ονομάτων χώρων
Για να ξεκινήσετε να χρησιμοποιείτε τη λειτουργικότητα του Aspose.GIS, εισάγετε τα απαιτούμενα namespaces.

### Κύρια namespaces του Aspose.GIS
Το namespace `Aspose.Gis` περιέχει τις βασικές κλάσεις γεωμετρίας, τους οδηγούς και τα βοηθητικά εργαλεία που απαιτούνται για όλες τις λειτουργίες GIS.
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Οδηγός για τη μορφή προορισμού
`Aspose.Gis.Drivers` παρέχει στατικές εργοστασιακές μεθόδους για κάθε υποστηριζόμενη μορφή αρχείου· `Drivers.Kml` δημιουργεί έναν συγγραφέα KML.
```csharp
using Aspose.GIS.Kml;
```

## Οδηγός βήμα‑βήμα για τη μετατροπή καμπυλών σε γραμμές
Παρακάτω είναι μια λεπτομερής περιγραφή κάθε γραμμής κώδικα, εξηγώντας **πώς να μετατρέψετε τις καμπύλες σε γραμμές** και γιατί κάθε βήμα είναι σημαντικό.

### Βήμα 1: Ορισμός διαδρομής εξόδου
`Path.Combine` δημιουργεί μια ανεξάρτητη από την πλατφόρμα διαδρομή αρχείου, διαχειριζόμενη αυτόματα τις ανάστροφες κάθετες γραμμές των Windows και τις διαγώνιες γραμμές του Unix.
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
Αντικαταστήστε το `"Your Document Directory"` με το φάκελο όπου θέλετε να αποθηκευτεί το αρχείο KML.

### Βήμα 2: Δημιουργία layer για το αρχείο εξόδου
Ένα *layer* ομαδοποιεί γεωγραφικά χαρακτηριστικά του ίδιου τύπου. Εδώ δημιουργούμε ένα νέο KML layer που θα αποθηκεύσει τη γραμμικοποιημένη γεωμετρία.
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```

### Βήμα 3: Κατασκευή νέου feature
Ένα *feature* αντιπροσωπεύει ένα μοναδικό γεωγραφικό αντικείμενο (σημείο, γραμμή, πολύγωνο κ.λπ.). Θα συνδέσουμε τη γραμμική γεωμετρία μας με αυτό το feature.
```csharp
var feature = layer.ConstructFeature();
```

### Βήμα 4: Ορισμός της αρχικής σύνθετης γεωμετρίας
`Geometry.FromWkt` αναλύει μια συμβολοσειρά Well‑Known Text (WKT) σε αντικείμενο γεωμετρίας. Το δείγμα WKT περιλαμβάνει ένα `LineString`, ένα `CompoundCurve` και ένα `CircularString` για να επιδείξει τη διαχείριση καμπυλών.
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```

### Βήμα 5: Μετατροπή καμπυλών σε γραμμές
`ToLinearGeometry()` τριγωνοποιεί κάθε καμπύλη στη γεωμετρία προέλευσης σε ευθύγραμμα τμήματα, επιστρέφοντας μια νέα γραμμική γεωμετρία που διατηρεί τυχόν συντεταγμένες Z.
```csharp
var linear = geometry.ToLinearGeometry();
```

### Βήμα 6: Ανάθεση της γραμμικής γεωμετρίας στο feature
Η ιδιότητα `Geometry` του feature τώρα περιέχει την απλοποιημένη, γραμμική έκδοση του αρχικού σχήματος.
```csharp
feature.Geometry = linear;
```

### Βήμα 7: Προσθήκη του feature στο layer
Η προσθήκη του feature στο KML layer το τοποθετεί στην ουρά για εγγραφή· όταν το μπλοκ `using` ολοκληρωθεί, το layer εκκενώνει τα δεδομένα στο αρχείο εξόδου.
```csharp
layer.Add(feature);
```

## Συνηθισμένα προβλήματα & επαγγελματικές συμβουλές
- **Διαχωριστές διαδρομών:** Χρησιμοποιήστε το `Path.Combine` για να αποφύγετε προβλήματα σε Windows vs. Linux.  
- **Πολύ μεγάλες γεωμετρίες:** Η γραμμικοποίηση πολύπλοκων σχημάτων μπορεί να δημιουργήσει χιλιάδες κορυφές· σκεφτείτε να καλέσετε το `Simplify()` μετά τη γραμμικοποίηση για να μειώσετε τον αριθμό των σημείων.  
- **Επιλογή οδηγού:** Εάν χρειάζεστε διαφορετική μορφή εξόδου, αντικαταστήστε το `Drivers.Kml` με `Drivers.Shapefile`, `Drivers.GeoJson`, κ.λπ., και αλλάξτε την επέκταση του αρχείου αναλόγως.  
- **Διατήρηση τιμών Z:** Το `ToLinearGeometry()` διατηρεί τις 3‑Δ (Z) συντεταγμένες, ώστε να μην χάσετε δεδομένα υψομέτρου.

## Συχνές ερωτήσεις (FAQ)

**Ε: Είναι το Aspose.GIS για .NET συμβατό με .NET Core;**  
Α: Ναι, το Aspose.GIS λειτουργεί με .NET Core, επιτρέποντας εφαρμογές πολλαπλών πλατφορμών.

**Ε: Μπορώ να εργαστώ με διαφορετικές μορφές αρχείων GIS χρησιμοποιώντας το Aspose.GIS για .NET;**  
Α: Απόλυτα! Η βιβλιοθήκη υποστηρίζει KML, Shapefile, GeoJSON και πολλές άλλες μορφές—πάνω από 30 συνολικά.

**Ε: Παρέχει το Aspose.GIS λειτουργίες χωρικών εργασιών και ανάλυσης;**  
Α: Ναι, παρέχει ένα ευρύ φάσμα χωρικών λειτουργιών, από buffering μέχρι spatial joins.

**Ε: Υπάρχει διαθέσιμη δωρεάν δοκιμή;**  
Α: Ναι, μπορείτε να κατεβάσετε μια δωρεάν δοκιμή από την [Aspose.GIS website](https://releases.aspose.com/gis/net/).

**Ε: Πού μπορώ να λάβω βοήθεια αν αντιμετωπίσω προβλήματα;**  
Α: Επισκεφθείτε το [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) για υποστήριξη από την κοινότητα και το προσωπικό.

### Πρόσθετες συνηθισμένες ερωτήσεις

**Ε: Μπορώ να γραμμικοποιήσω γεωμετρίες που περιέχουν 3Δ (Z) συντεταγμένες;**  
Α: Ναι, το `ToLinearGeometry()` λειτουργεί με γεωμετρίες 2Δ και 3Δ· οι τιμές Z διατηρούνται.

**Ε: Πώς η γραμμικοποίηση επηρεάζει το μέγεθος του αρχείου;**  
Α: Η μετατροπή καμπυλών σε πολλά σύντομα ευθύγραμμα τμήματα μπορεί να αυξήσει το μέγεθος του αρχείου· εκτελέστε `Simplify()` μετά τη γραμμικοποίηση αν το μέγεθος είναι πρόβλημα.

**Ε: Μπορώ να ελέγξω το μήκος του τμήματος όταν μετατρέπω καμπύλες σε γραμμές;**  
Α: Η προεπιλεγμένη μέθοδος χρησιμοποιεί μια εσωτερική ανοχή. Για προσαρμοσμένη τμηματοποίηση μπορείτε να τριγωνοποιήσετε χειροκίνητα τις καμπύλες πριν καλέσετε το `ToLinearGeometry()`.

## Συμπέρασμα
Σε αυτό το tutorial καλύψαμε **πώς να μετατρέψετε τις καμπύλες σε γραμμές** (γραμμικοποίηση γεωμετρίας) χρησιμοποιώντας το Aspose.GIS για .NET, από τη ρύθμιση του περιβάλλοντος μέχρι τη γραφή του γραμμικοποιημένου αποτελέσματος σε αρχείο KML. Τώρα μπορείτε να ενσωματώσετε αυτή τη ροή εργασιών σε εφαρμογές χαρτογράφησης, pipelines επεξεργασίας δεδομένων ή οποιοδήποτε έργο GIS που απαιτεί απλοποιημένες γεωμετρίες.

---

**Τελευταία ενημέρωση:** 2026-09-10  
**Δοκιμή με:** Aspose.GIS 24.11 for .NET  
**Συγγραφέας:** Aspose

## Σχετικά μαθήματα

- [Πώς να δημιουργήσετε GeoJSON με ανοχή Aspose.GIS για .NET](/gis/net/geometry-processing/set-linearization-tolerance/)
- [Μετατροπή πολύγωνου σε γραμμή με Aspose.GIS για .NET](/gis/net/geometry-processing/replace-polygons-with-lines/)
- [Μάθετε πώς να δημιουργήσετε γεωμετρία LineString με Aspose.GIS για .NET](/gis/net/geometry-creation/create-linestring-geometry/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}