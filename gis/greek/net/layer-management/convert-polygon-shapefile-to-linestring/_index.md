---
title: Μετατρέψτε το Polygon Shapefile σε Linestring
linktitle: Μετατρέψτε το Polygon Shapefile σε Linestring
second_title: Aspose.GIS .NET API
description: Εξερευνήστε τη δύναμη του Aspose.GIS για .NET και μετατρέψτε αβίαστα τα Polygon Shapefiles σε Linestrings. Ενισχύστε την ανάπτυξη GIS σας σήμερα!
weight: 18
url: /el/net/layer-management/convert-polygon-shapefile-to-linestring/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Μετατρέψτε το Polygon Shapefile σε Linestring

## Εισαγωγή
Εάν εργάζεστε με συστήματα γεωγραφικών πληροφοριών (GIS) στο .NET, το Aspose.GIS είναι μια ισχυρή βιβλιοθήκη που μπορεί να απλοποιήσει τις εργασίες σας. Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία μετατροπής ενός αρχείου σχήματος Polygon σε Linestring χρησιμοποιώντας το Aspose.GIS. Αυτό μπορεί να είναι ιδιαίτερα χρήσιμο όταν χρειάζεται να εξαγάγετε γραμμικά χαρακτηριστικά από πολυγωνικά δεδομένα για διάφορες εφαρμογές, όπως ο σχεδιασμός διαδρομής ή η ανάλυση δικτύου.
## Προαπαιτούμενα
Πριν ξεκινήσουμε τον οδηγό, βεβαιωθείτε ότι έχετε τα εξής:
-  Aspose.GIS Library: Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη Aspose.GIS από το[δικτυακός τόπος](https://releases.aspose.com/gis/net/).
- Δεδομένα Shapefile: Έχετε ένα Polygon Shapefile έτοιμο για μετατροπή. Εάν δεν έχετε, μπορείτε να βρείτε δείγματα δεδομένων ή να δημιουργήσετε τα δικά σας.
- Περιβάλλον ανάπτυξης: Ρυθμίστε το περιβάλλον ανάπτυξης .NET με τα απαραίτητα εργαλεία.
## Εισαγωγή χώρων ονομάτων
Στον κώδικα C#, πρέπει να εισαγάγετε τους χώρους ονομάτων Aspose.GIS για πρόσβαση στις απαιτούμενες κλάσεις και μεθόδους. Προσθέστε τους ακόλουθους χώρους ονομάτων στην αρχή του αρχείου κώδικα:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Βήμα 1: Ορίστε τον Κατάλογο εγγράφων
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "Your Document Directory";
```
Αντικαταστήστε το "Your Document Directory" με τη διαδρομή προς τον κατάλογο όπου βρίσκεται το Shapefile σας.
## Βήμα 2: Ανοίξτε το Source Shapefile
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Ο υπόλοιπος κώδικας θα πάει εδώ
}
```
Αυτό το βήμα ανοίγει το αρχείο προέλευσης Polygon Shapefile για ανάγνωση.
## Βήμα 3: Δημιουργήστε το Destination Linestring Shapefile
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Ο υπόλοιπος κώδικας θα πάει εδώ
}
```
Εδώ, δημιουργούμε ένα νέο Linestring Shapefile για την εγγραφή των δεδομένων που έχουν μετατραπεί.
## Βήμα 4: Επανάληψη δυνατοτήτων μέσω πηγής
```csharp
foreach (Feature sourceFeature in source)
{
    // Ο υπόλοιπος κώδικας θα πάει εδώ
}
```
Αυτός ο βρόχος επαναλαμβάνεται μέσω κάθε δυνατότητας στο αρχείο προέλευσης Polygon Shapefile.
## Βήμα 5: Μετατρέψτε το Polygon σε Linestring και το Write to Destination
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
Σε αυτό το βήμα, κάθε χαρακτηριστικό Polygon μετατρέπεται σε Linestring και το χαρακτηριστικό Linestring που προκύπτει εγγράφεται στο Shapefile προορισμού.
## συμπέρασμα
Ακολουθώντας αυτά τα βήματα, μπορείτε εύκολα να μετατρέψετε ένα Polygon Shapefile σε Linestring χρησιμοποιώντας το Aspose.GIS για .NET. Αυτή η διαδικασία ανοίγει νέες δυνατότητες για ανάλυση και οπτικοποίηση δεδομένων σε εφαρμογές GIS.

## Συχνές ερωτήσεις
### Είναι το Aspose.GIS συμβατό με όλες τις εκδόσεις του .NET;
Ναι, το Aspose.GIS υποστηρίζει διάφορες εκδόσεις του .NET, διασφαλίζοντας τη συμβατότητα με το περιβάλλον ανάπτυξής σας.
### Μπορώ να χρησιμοποιήσω το Aspose.GIS για εμπορικά έργα;
 Ναι μπορείς. Για να χρησιμοποιήσετε το Aspose.GIS σε εμπορικά έργα, σκεφτείτε να αγοράσετε μια άδεια[εδώ](https://purchase.aspose.com/buy).
### Υπάρχουν διαθέσιμα παραδείγματα ή τεκμηρίωση;
 Ναι, μπορείτε να βρείτε ολοκληρωμένη τεκμηρίωση και παραδείγματα στο[σελίδα τεκμηρίωσης](https://reference.aspose.com/gis/net/).
### Υπάρχει διαθέσιμη δοκιμαστική έκδοση;
 Ναι, μπορείτε να εξερευνήσετε το Aspose.GIS με μια δωρεάν δοκιμή με μια επίσκεψη[αυτός ο σύνδεσμος](https://releases.aspose.com/).
### Πού μπορώ να αναζητήσω βοήθεια ή υποστήριξη;
 Επισκέψου το[Φόρουμ Aspose.GIS](https://forum.aspose.com/c/gis/33) για οποιαδήποτε βοήθεια ή απορία σχετικά με την υποστήριξη.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
