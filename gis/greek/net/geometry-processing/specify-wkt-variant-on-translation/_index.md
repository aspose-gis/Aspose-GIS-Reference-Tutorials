---
title: Καθορίστε την παραλλαγή WKT στη μετάφραση χρησιμοποιώντας το Aspose.GIS
linktitle: Καθορίστε την παραλλαγή WKT στη μετάφραση
second_title: Aspose.GIS .NET API
description: Μάθετε πώς να προσδιορίζετε παραλλαγές WKT στο Aspose.GIS για .NET για να ελέγχετε αποτελεσματικά τη μορφή και την ακρίβεια αναπαράστασης χωρικών δεδομένων.
weight: 19
url: /el/net/geometry-processing/specify-wkt-variant-on-translation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Καθορίστε την παραλλαγή WKT στη μετάφραση χρησιμοποιώντας το Aspose.GIS

## Εισαγωγή
Το Aspose.GIS για .NET είναι μια ισχυρή βιβλιοθήκη που επιτρέπει στους προγραμματιστές να εργάζονται με δεδομένα συστήματος γεωγραφικών πληροφοριών (GIS) στις εφαρμογές τους .NET χωρίς κόπο. Ένα από τα βασικά χαρακτηριστικά που παρέχει το Aspose.GIS είναι η δυνατότητα καθορισμού της παραλλαγής Γνωστό Κείμενο (WKT) κατά τη μετάφραση, επιτρέποντας στους χρήστες να ελέγχουν τη μορφή και την ακρίβεια των αναπαραστάσεων χωρικών δεδομένων. Σε αυτό το σεμινάριο, θα διερευνήσουμε πώς να καθορίσετε παραλλαγές WKT βήμα προς βήμα χρησιμοποιώντας το Aspose.GIS για .NET.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1. Aspose.GIS για .NET: Κατεβάστε και εγκαταστήστε το Aspose.GIS για .NET από το[σελίδα λήψης](https://releases.aspose.com/gis/net/).
2. Περιβάλλον ανάπτυξης: Βεβαιωθείτε ότι έχετε ρυθμίσει ένα περιβάλλον ανάπτυξης .NET.
3. Βασικές Γνώσεις: Εξοικείωση με τη γλώσσα προγραμματισμού C# και το .NET Framework.

## Εισαγωγή χώρων ονομάτων
Πριν χρησιμοποιήσετε τη λειτουργία Aspose.GIS στον κώδικά σας, εισαγάγετε τους απαραίτητους χώρους ονομάτων:
```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```
## Βήμα 1: Δημιουργήστε ένα αντικείμενο σημείου
 Πρώτα, δημιουργήστε ένα`Point` αντικείμενο με τιμές γεωγραφικού πλάτους, γεωγραφικού μήκους και προαιρετικού μέτρου (M):
```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```
## Βήμα 2: Ρύθμιση χωρικού συστήματος αναφοράς (SRS)
Εκχωρήστε ένα σύστημα χωρικής αναφοράς (SRS) στο σημείο αντικείμενο. Σε αυτό το παράδειγμα, χρησιμοποιούμε το χωρικό σύστημα αναφοράς WGS84:
```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```
## Βήμα 3: Καθορίστε την παραλλαγή WKT
 Τώρα, καθορίστε την παραλλαγή WKT για μετάφραση. Το Aspose.GIS υποστηρίζει διάφορες παραλλαγές WKT, μεταξύ των οποίων`Iso`, `SimpleFeatureAccessOutdated` , και`ExtendedPostGis`. Επιλέξτε την κατάλληλη παραλλαγή με βάση τις απαιτήσεις σας:
```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // ΣΗΜΕΙΟ M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```
## Βήμα 4: Έλεγχος αριθμητικής μορφής
Μπορείτε να ελέγξετε την αριθμητική μορφή των συντεταγμένων στην αναπαράσταση WKT. Το Aspose.GIS παρέχει επιλογές για τον καθορισμό της δεκαδικής ακρίβειας:
```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // ΣΗΜΕΙΟ Μ (23,6 25,3 40,3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // ΣΗΜΕΙΟ Μ (23.573 25.342 40.3)
```

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να καθορίζουμε παραλλαγές WKT στη μετάφραση χρησιμοποιώντας το Aspose.GIS για .NET. Ακολουθώντας τα βήματα που περιγράφονται παραπάνω, οι προγραμματιστές μπορούν να ελέγχουν αποτελεσματικά τη μορφή και την ακρίβεια των αναπαραστάσεων χωρικών δεδομένων στις εφαρμογές τους .NET, ενισχύοντας την ευελιξία και τη χρηστικότητα των συστημάτων γεωγραφικών πληροφοριών.
## Συχνές ερωτήσεις
### Είναι το Aspose.GIS συμβατό με όλες τις εκδόσεις του .NET;
Ναι, το Aspose.GIS υποστηρίζει .NET Framework 4.0 και νεότερη έκδοση.
### Μπορώ να χρησιμοποιήσω το Aspose.GIS για εμπορικά έργα;
Ναι, το Aspose.GIS μπορεί να χρησιμοποιηθεί τόσο για προσωπικά όσο και για εμπορικά έργα.
### Το Aspose.GIS παρέχει υποστήριξη για άλλες μορφές χωρικών δεδομένων;
Ναι, το Aspose.GIS υποστηρίζει ένα ευρύ φάσμα μορφών χωρικών δεδομένων, συμπεριλαμβανομένων των ESRI Shapefile, GeoJSON και KML.
### Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.GIS;
 Ναι, μπορείτε να κάνετε λήψη μιας δωρεάν δοκιμαστικής έκδοσης του Aspose.GIS από[εδώ](https://releases.aspose.com/).
### Πού μπορώ να λάβω βοήθεια ή υποστήριξη για το Aspose.GIS;
 Μπορείτε να δημοσιεύσετε τα ερωτήματά σας ή να ζητήσετε βοήθεια από την κοινότητα Aspose.GIS στη διεύθυνση[δικαστήριο](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
