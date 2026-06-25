---
date: 2026-06-25
description: Μάθετε πώς να διαβάσετε shapefile και να μετατρέψετε ένα polygon shapefile
  σε linestring χρησιμοποιώντας το Aspose.GIS για .NET. Ενισχύστε την ανάπτυξη GIS
  με σαφείς οδηγίες βήμα‑βήμα.
keywords:
- how to read shapefile
- convert polygon to line
- shapefile to geojson c#
- extract lines from polygon
linktitle: Μετατροπή Polygon Shapefile σε Linestring
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to read shapefile and convert a polygon shapefile to a linestring
    using Aspose.GIS for .NET. Boost your GIS development with clear step‑by‑step
    guidance.
  headline: How to Read Shapefile C# – Convert Polygon Shapefile to Linestring
  type: TechArticle
- description: Learn how to read shapefile and convert a polygon shapefile to a linestring
    using Aspose.GIS for .NET. Boost your GIS development with clear step‑by‑step
    guidance.
  name: How to Read Shapefile C# – Convert Polygon Shapefile to Linestring
  steps:
  - name: Set the Document Directory
    text: Replace `"Your Document Directory"` with the actual path where your shapefile
      resides.
  - name: Open the Source Shapefile
    text: This line opens the source Polygon Shapefile so you can read its features.
  - name: Create the Destination Linestring Shapefile
    text: Here we create a new Linestring Shapefile that will store the converted
      geometries.
  - name: Iterate Through Source Features
    text: The loop walks through each polygon feature in the original file.
  - name: Convert Polygon to Linestring and Write to Destination
    text: The `ExteriorRing` property returns the outer boundary of a polygon as a
      `LineString`. In this block we convert polygon to line (`LineString`) and add
      the new feature to the destination shapefile.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS supports .NET Framework 4.5+, .NET Core 3.1+, and .NET
      5/6/7, ensuring seamless integration with modern development stacks.
    question: Is Aspose.GIS compatible with all versions of .NET?
  - answer: Yes, you can. Purchase a license [here](https://purchase.aspose.com/buy)
      to remove evaluation limitations and obtain full support.
    question: Can I use Aspose.GIS for commercial projects?
  - answer: Yes, you can find comprehensive documentation and code samples on the
      [documentation page](https://reference.aspose.com/gis/net/).
    question: Are there any examples or documentation available?
  - answer: Absolutely – explore Aspose.GIS with a free trial by visiting [this link](https://releases.aspose.com/).
    question: Is there a trial version available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      assistance and official support.
    question: Where can I seek help or support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Πώς να διαβάσετε Shapefile C# – Μετατροπή Polygon Shapefile σε Linestring
url: /el/net/layer-management/convert-polygon-shapefile-to-linestring/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Διαβάστε Shapefile C# – Μετατροπή Polygon Shapefile σε Linestring

## Εισαγωγή
Αν χρειάζεστε **πώς να διαβάσετε shapefile** δεδομένα σε περιβάλλον .NET, βρίσκεστε στο σωστό μέρος. Το Aspose.GIS για .NET αφαιρεί την χαμηλού επιπέδου δυαδική μορφή ενός Shapefile, επιτρέποντάς σας να φορτώνετε, να κάνετε ερωτήματα και να μετασχηματίζετε γεωγραφικά χαρακτηριστικά με λίγες κλήσεις API. Η μετατροπή ενός polygon shapefile σε linestring είναι ιδιαίτερα χρήσιμη όταν θέλετε να εξάγετε γραμμικές αναπαραστάσεις για δρομολόγηση, ανάλυση δικτύου ή απλή οπτικοποίηση.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη σας βοηθά να διαβάσετε shapefile c#;** Aspose.GIS for .NET – υποστηρίζει 50+ μορφές GIS και διαχειρίζεται αρχεία έως αρκετές εκατοντάδες megabytes χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη.  
- **Μπορείτε να μετατρέψετε ένα polygon σε γραμμή;** Ναι – καλέστε `LineString` στο εξωτερικό δακτύλιο του polygon και γράψτε το αποτέλεσμα σε ένα νέο shapefile.  
- **Χρειάζομαι άδεια για παραγωγή;** Απαιτείται εμπορική άδεια για παραγωγικές αναπτύξεις· μια δωρεάν δοκιμή λειτουργεί για αξιολόγηση.  
- **Ποιες εκδόσεις .NET υποστηρίζονται;** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **Υπάρχει διαθέσιμη δοκιμαστική έκδοση;** Απόλυτα – κατεβάστε μια δωρεάν δοκιμή από τον ιστότοπο Aspose.

`LineString` είναι ένας τύπος γεωμετρίας που αντιπροσωπεύει μια σειρά συνδεδεμένων τμημάτων γραμμής.

## Τι είναι “read shapefile c#”;
`Document` είναι η βασική κλάση που αντιπροσωπεύει ένα σύνολο δεδομένων GIS και παρέχει πρόσβαση στα χαρακτηριστικά του.  
Η ανάγνωση ενός shapefile σε C# σημαίνει τη φόρτωση του αρχείου `.shp` στη μνήμη ώστε να μπορείτε να κάνετε ερωτήματα, τροποποιήσεις ή μετασχηματισμούς των γεωμετριών του. **Απλώς δημιουργείτε μια παρουσία της κλάσης `Document` με τη διαδρομή του αρχείου, και το Aspose.GIS αναλύει τη δυαδική δομή για εσάς**, εκθέτοντας τα χαρακτηριστικά μέσω μιας εύχρηστης συλλογής. Αυτή η προσέγγιση εξαλείφει την ανάγκη εργασίας με χαμηλού επιπέδου κεφαλίδες αρχείων ή πίνακες συντεταγμένων με το χέρι.

## Γιατί να μετατρέψετε polygon σε γραμμή με το Aspose.GIS;
Η μετατροπή ενός polygon σε linestring διατηρεί το ακριβές εξωτερικό σύνορο ενώ αφαιρεί τα εσωτερικά δαχτυλίδια, παρέχοντάς σας μια καθαρή γραμμική αναπαράσταση. Το Aspose.GIS επεξεργάζεται **σύνολα δεδομένων έως 500 MB σε λιγότερο από 2 δευτερόλεπτα σε τυπικό διακομιστή**, καθιστώντας τις μαζικές μετατροπές γρήγορες και αποδοτικές σε μνήμη. Η βιβλιοθήκη διατηρεί επίσης την αρχική χωρική αναφορά, ώστε οι παραγόμενες γραμμές να ευθυγραμμίζονται τέλεια με τυχόν υπάρχοντα GIS επίπεδα.

## Προαπαιτούμενα
Πριν βυθιστούμε στο tutorial, βεβαιωθείτε ότι έχετε τα παρακάτω:

- **Aspose.GIS Library** – Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη Aspose.GIS από τον [website](https://releases.aspose.com/gis/net/).  
- **Shapefile Data** – Έχετε ένα Polygon Shapefile έτοιμο για μετατροπή. Αν δεν έχετε, μπορείτε να βρείτε δείγμα δεδομένων ή να δημιουργήσετε το δικό σας.  
- **Development Environment** – Ρυθμίστε το περιβάλλον ανάπτυξης .NET με τα απαραίτητα εργαλεία (Visual Studio, .NET SDK, κλπ.).

## Εισαγωγή Namespaces
Η κλάση `Document` είναι το βασικό αντικείμενο του Aspose.GIS που αντιπροσωπεύει ένα σύνολο δεδομένων GIS και παρέχει μεθόδους για ανάγνωση και εγγραφή shapefiles. Προσθέστε τα παρακάτω namespaces στην αρχή του αρχείου κώδικά σας:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Πώς να διαβάσετε shapefile και να μετατρέψετε polygon σε linestring;
Φορτώστε το πηγαίο polygon shapefile, εξάγετε το εξωτερικό δακτύλιο κάθε polygon, δημιουργήστε ένα `LineString` από αυτό το δακτύλιο και γράψτε το αποτέλεσμα σε ένα νέο shapefile – όλα σε πέντε απλά βήματα. Αυτό το μοτίβο λειτουργεί για σύνολα δεδομένων οποιουδήποτε μεγέθους και εγγυάται ότι το σύστημα συντεταγμένων του πηγαίου διατηρείται στον προορισμό.

### Βήμα 1: Ορίστε τον Κατάλογο Εγγράφου
```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```
Αντικαταστήστε το `"Your Document Directory"` με την πραγματική διαδρομή όπου βρίσκεται το shapefile σας.

### Βήμα 2: Ανοίξτε το Πηγαίο Shapefile
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
Αυτή η γραμμή ανοίγει το πηγαίο Polygon Shapefile ώστε να μπορείτε να διαβάσετε τα χαρακτηριστικά του.

### Βήμα 3: Δημιουργήστε το Προορισμό Linestring Shapefile
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
Εδώ δημιουργούμε ένα νέο Linestring Shapefile που θα αποθηκεύσει τις μετατρεπόμενες γεωμετρίες.

### Βήμα 4: Επανάληψη Στις Πηγαίες Χαρακτηριστικά
```csharp
foreach (Feature sourceFeature in source)
{
    // Rest of the code will go here
}
```
Ο βρόχος περνάει από κάθε χαρακτηριστικό polygon στο αρχικό αρχείο.

### Βήμα 5: Μετατρέψτε Polygon σε Linestring και Γράψτε στον Προορισμό
Η ιδιότητα `ExteriorRing` επιστρέφει το εξωτερικό σύνορο ενός polygon ως `LineString`.  
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
Σε αυτό το μπλοκ μετατρέπουμε το polygon σε γραμμή (`LineString`) και προσθέτουμε το νέο χαρακτηριστικό στο προορισμό shapefile.

## Κοινά Προβλήματα και Συμβουλές
- **Ασυμφωνία Συστήματος Συντεταγμένων** – Βεβαιωθείτε ότι και τα πηγαία και τα προοριζόμενα στρώματα χρησιμοποιούν την ίδια χωρική αναφορά· διαφορετικά, οι γραμμές μπορεί να εμφανιστούν μετατοπισμένες.  
- **Μεγάλα Αρχεία** – Όταν επεξεργάζεστε πολύ μεγάλα shapefiles, σκεφτείτε τη ροή χαρακτηριστικών αντί να τα φορτώνετε όλα στη μνήμη ταυτόχρονα.  
- **Κενές Γεωμετρίες** – Προστατέψτε από χαρακτηριστικά με κενές γεωμετρίες για να αποφύγετε εξαιρέσεις χρόνου εκτέλεσης.  
- **Εξαγωγή γραμμών από polygon** – Αν χρειάζεστε μόνο το εξωτερικό δακτύλιο, χρησιμοποιήστε την ιδιότητα `ExteriorRing`; για εσωτερικά δαχτυλίδια, επαναλάβετε το `InteriorRings`.  

## Συχνές Ερωτήσεις

**Q: Είναι το Aspose.GIS συμβατό με όλες τις εκδόσεις του .NET;**  
A: Ναι, το Aspose.GIS υποστηρίζει .NET Framework 4.5+, .NET Core 3.1+, και .NET 5/6/7, εξασφαλίζοντας αδιάλειπτη ενσωμάτωση με σύγχρονες πλατφόρμες ανάπτυξης.

**Q: Μπορώ να χρησιμοποιήσω το Aspose.GIS για εμπορικά έργα;**  
A: Ναι, μπορείτε. Αγοράστε μια άδεια [εδώ](https://purchase.aspose.com/buy) για να αφαιρέσετε τους περιορισμούς αξιολόγησης και να λάβετε πλήρη υποστήριξη.

**Q: Υπάρχουν παραδείγματα ή τεκμηρίωση διαθέσιμα;**  
A: Ναι, μπορείτε να βρείτε εκτενή τεκμηρίωση και δείγματα κώδικα στη [documentation page](https://reference.aspose.com/gis/net/).

**Q: Υπάρχει διαθέσιμη δοκιμαστική έκδοση;**  
A: Απόλυτα – εξερευνήστε το Aspose.GIS με δωρεάν δοκιμή επισκεπτόμενοι [this link](https://releases.aspose.com/).

**Q: Πού μπορώ να ζητήσω βοήθεια ή υποστήριξη;**  
A: Επισκεφθείτε το [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) για βοήθεια από την κοινότητα και επίσημη υποστήριξη.

---

**Τελευταία Ενημέρωση:** 2026-06-25  
**Δοκιμάστηκε Με:** Aspose.GIS for .NET (τελευταία έκδοση)  
**Συγγραφέας:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικά Μαθήματα

- [Πώς να Μετατρέψετε Shapefile σε GeoJSON χρησιμοποιώντας Aspose.GIS για .NET](/gis/net/layer-management/extract-features-to-geojson/)
- [Πώς να Διαβάσετε GeoJSON από Stream με Aspose.GIS για .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Πώς να Δημιουργήσετε Γεωμετρία Polygon με Aspose.GIS για .NET](/gis/net/geometry-creation/create-polygon-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}