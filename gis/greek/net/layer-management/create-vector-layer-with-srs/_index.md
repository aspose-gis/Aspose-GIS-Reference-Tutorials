---
date: 2026-01-15
description: Εξερευνήστε το Aspose.GIS για .NET για να δημιουργήσετε διανυσματικό
  στρώμα με σύστημα αναφοράς χώρου. Μάθετε πώς να ορίζετε το SRS, να δημιουργείτε
  στρώμα και να διαχειρίζεστε δεδομένα GIS. Κατεβάστε το τώρα!
linktitle: Create Vector Layer with SRS
second_title: Aspose.GIS .NET API
title: Δημιουργία διανυσματικού στρώματος με SRS
url: /el/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία Διανυσματικού Στρώματος με SRS

## Εισαγωγή
Aspose.GIS for .NET είναι μια ισχυρή βιβλιοθήκη που επιτρέπει στους προγραμματιστές να **δημιουργούν διανυσματικά στρώματα** και να εργάζονται με δεδομένα γεωγραφικών πληροφοριών (GIS) απρόσκοπτα σε εφαρμογές .NET. Σε αυτό το σεμινάριο, θα δούμε πώς να δημιουργήσουμε ένα διανυσματικό στρώμα με σύστημα χωρικής αναφοράς (SRS), γιατί είναι σημαντικό να ορίσετε τη χωρική αναφορά και ποια οφέλη προσφέρει σε πραγματικά έργα. Στο τέλος αυτού του οδηγού, θα μπορείτε να ενσωματώσετε δυνατότητες GIS στις .NET λύσεις σας με σιγουριά.

## Γρήγορες Απαντήσεις
- **Ποιος είναι ο κύριος σκοπός αυτού του σεμιναρίου;** Να δείξει πώς να δημιουργήσετε διανυσματικό στρώμα με καθορισμένο SRS χρησιμοποιώντας Aspose.GIS for .NET.  
- **Ποια προβολή χρησιμοποιείται στο παράδειγμα;** World Mercator (EPSG:3395).  
- **Χρειάζομαι άδεια για να εκτελέσω τον κώδικα;** Μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη· απαιτείται εμπορική άδεια για παραγωγή.  
- **Μπορώ να χρησιμοποιήσω την ίδια προσέγγιση με άλλες μορφές GIS;** Ναι, η ίδια διαχείριση SRS ισχύει για Shapefile, GeoJSON, KML κ.λπ.  
- **Ποιες εκδόσεις του .NET υποστηρίζονται;** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Τι είναι ένα διανυσματικό στρώμα και γιατί να ορίσουμε την χωρική του αναφορά;
Ένα **διανυσματικό στρώμα** αποθηκεύει γεωμετρικά χαρακτηριστικά (σημεία, γραμμές, πολύγωνα) μαζί με δεδομένα ιδιοτήτων. Η ανάθεση μιας **χωρικής αναφοράς** (SRS) λέει στο λογισμικό GIS πώς να ερμηνεύσει αυτές τις συντεταγμένες στην επιφάνεια της γης. Η σωστή ρύθμιση του SRS εξασφαλίζει ακριβείς μετρήσεις, σωστή επικάλυψη με άλλα στρώματα και αξιόπιστες οπτικοποιήσεις χαρτών.

## Προαπαιτούμενα
Πριν προχωρήσουμε, βεβαιωθείτε ότι έχετε:

- Βασικές γνώσεις C# και ανάπτυξης .NET.  
- Βιβλιοθήκη Aspose.GIS for .NET εγκατεστημένη. Μπορείτε να τη κατεβάσετε **[εδώ](https://releases.aspose.com/gis/net/)**.  
- Περιβάλλον ανάπτυξης (Visual Studio, VS Code ή οποιοδήποτε IDE για C#).  

## Εισαγωγή χώρων ονομάτων
Βεβαιωθείτε ότι έχετε εισάγει τους απαραίτητους χώρους ονομάτων στην κορυφή του αρχείου C#:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Πώς να ορίσετε χωρική αναφορά (SRS) – Βήμα 1
Ας δημιουργήσουμε ένα **προεξατομικευμένο σύστημα χωρικής αναφοράς** χρησιμοποιώντας την προβολή World Mercator ως παράδειγμα. Αυτό δείχνει **πώς να ορίσετε srs** για ένα στρώμα.

```csharp
var parameters = new ProjectedSpatialReferenceSystemParameters
{
    Name = "WGS 84 / World Mercator",
    Base = SpatialReferenceSystem.Wgs84,
    ProjectionMethodName = "Mercator_1SP",
    LinearUnit = Unit.Meter,
    XAxis = new Axis("Easting", AxisDirection.East),
    YAxis = new Axis("Northing", AxisDirection.North),
    AxisesOrder = ProjectedAxisesOrder.XY,
};
parameters.AddProjectionParameter("central_meridian", 0);
parameters.AddProjectionParameter("scale_factor", 1);
parameters.AddProjectionParameter("false_easting", 0);
parameters.AddProjectionParameter("false_northing", 0);
var projectedSrs = SpatialReferenceSystem.CreateProjected(parameters, Identifier.Epsg(3395));
```

## Πώς να δημιουργήσετε στρώμα – Βήμα 2
Τώρα θα **δημιουργήσουμε ένα διανυσματικό στρώμα** (ένα Shapefile) και θα προσθέσουμε χαρακτηριστικά που χρησιμοποιούν το SRS που μόλις ορίσαμε. Αυτό το τμήμα απαντά στο **πώς να δημιουργήσετε στρώμα** με Aspose.GIS.

```csharp
using (var layer = Drivers.Shapefile.CreateLayer(dataDir + "filepath_out.shp", new ShapefileOptions(), projectedSrs))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2);
    layer.Add(feature);
    feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2) { SpatialReferenceSystem = SpatialReferenceSystem.Nad83 };
    try
    {
        layer.Add(feature); // This will throw an exception as the geometry has a different SRS
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```

> **Συμβουλή:** Πάντα επαληθεύετε ότι το `SpatialReferenceSystem` της γεωμετρίας ταιριάζει με το SRS του στρώματος πριν το προσθέσετε. Μη ταιριαστές τιμές SRS προκαλούν `GisException`, όπως φαίνεται παραπάνω.

## Επαλήθευση Συστήματος Χωρικής Αναφοράς – Βήμα 3
Τέλος, ανοίξτε το στρώμα και επιβεβαιώστε ότι το SRS εφαρμόστηκε σωστά.

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

Αν η κλήση `IsEquivalent` επιστρέψει `true`, έχετε δημιουργήσει επιτυχώς **διανυσματικό στρώμα** με την επιθυμητή χωρική αναφορά.

## Κοινά Προβλήματα & Λύσεις
| Πρόβλημα | Γιατί συμβαίνει | Διόρθωση |
|----------|----------------|----------|
| `GisException` κατά την προσθήκη χαρακτηριστικού | Η γεωμετρία χρησιμοποιεί διαφορετικό SRS από το στρώμα | Ορίστε `feature.Geometry.SpatialReferenceSystem` στο SRS του στρώματος πριν την προσθήκη |
| Το στρώμα εμφανίζεται κενό σε λογισμικό GIS | Το shapefile δημιουργήθηκε χωρίς κατάλληλο αρχείο `.prj` | Βεβαιωθείτε ότι το αντικείμενο `projectedSrs` περνιέται κατά τη δημιουργία του στρώματος |
| Απρόσμενες τιμές συντεταγμένων | Λανθασμένες παράμετροι προβολής (π.χ., κεντρικός μεσημβρινός) | Ελέγξτε ξανά τις παραμέτρους που περνιούνται στο `AddProjectionParameter` |

## Συχνές Ερωτήσεις
### Είναι το Aspose.GIS συμβατό με όλες τις μορφές αρχείων GIS;
Το Aspose.GIS υποστηρίζει διάφορες μορφές GIS, συμπεριλαμβανομένων Shapefile, GeoJSON, KML και άλλων. Δείτε την **[τεκμηρίωση](https://reference.aspose.com/gis/net/)** για την πλήρη λίστα.

### Μπορώ να χρησιμοποιήσω το Aspose.GIS σε εφαρμογή web;
Απολύτως! Το Aspose.GIS for .NET είναι ευέλικτο και μπορεί να χρησιμοποιηθεί σε web εφαρμογές, desktop εφαρμογές και ακόμη και σε κινητές εφαρμογές.

### Πού μπορώ να βρω υποστήριξη για το Aspose.GIS;
Μπορείτε να βρείτε μια βοηθητική κοινότητα στο **[φόρουμ Aspose.GIS](https://forum.aspose.com/c/gis/33)** για τυχόν ερωτήσεις ή προβλήματα που μπορεί να αντιμετωπίσετε.

### Υπάρχει διαθέσιμη δωρεάν δοκιμή;
Ναι, μπορείτε να εξερευνήσετε τις δυνατότητες του Aspose.GIS αποκτώντας δωρεάν δοκιμή **[εδώ](https://releases.aspose.com/)**.

### Πώς μπορώ να αγοράσω άδεια για το Aspose.GIS;
Για να αγοράσετε άδεια, επισκεφθείτε τη **[σελίδα αγοράς](https://purchase.aspose.com/buy)**.

## Συχνές Ερωτήσεις (Πρόσθετες)

**Ε: Τι συμβαίνει αν προσπαθήσω να προσθέσω μια γεωμετρία με διαφορετικό SRS;**  
Α: Το Aspose.GIS ρίχνει `GisException`. Πρέπει είτε να επαναπροβάλετε τη γεωμετρία είτε να διασφαλίσετε ότι μοιράζεται το SRS του στρώματος.

**Ε: Μπορώ να αλλάξω το SRS ενός υπάρχοντος στρώματος;**  
Α: Ναι, μπορείτε να δημιουργήσετε νέο στρώμα με το επιθυμητό SRS και να αντιγράψετε τα χαρακτηριστικά, επαναπροβάλλοντας τα όπως απαιτείται.

**Ε: Είναι δυνατόν να εργαστώ με 3D συντεταγμένες;**  
Α: Το Aspose.GIS υποστηρίζει Z‑συντεταγμένες· απλώς χρησιμοποιήστε κατασκευαστές γεωμετρίας που δέχονται τιμή Z.

**Ε: Η βιβλιοθήκη διαχειρίζεται αυτόματα τις μετασχηματίσεις datum;**  
Α: Όταν επαναπροβάλλετε γεωμετρίες χρησιμοποιώντας `Geometry.Transform`, το Aspose.GIS εκτελεί την απαραίτητη μετατόπιση datum.

**Ε: Ποιες εκδόσεις του .NET δοκιμάζονται επίσημα;**  
Α: Η βιβλιοθήκη δοκιμάζεται με .NET Framework 4.5+, .NET Core 3.1+, και .NET 5/6/7.

## Συμπέρασμα
Τώρα έχετε μάθει πώς να **δημιουργήσετε διανυσματικό στρώμα** με προσαρμοσμένο σύστημα χωρικής αναφοράς χρησιμοποιώντας Aspose.GIS for .NET. Ορίζοντας το σωστό SRS, διαχειριζόμενοι τη γεωμετρία συνεπώς και επαληθεύοντας τα μεταδεδομένα του στρώματος, μπορείτε να δημιουργήσετε ισχυρές εφαρμογές με δυνατότητες GIS που συνεργάζονται με οποιοδήποτε τυπικό λογισμικό GIS.

---

**Τελευταία Ενημέρωση:** 2026-01-15  
**Δοκιμάστηκε Με:** Aspose.GIS 24.11 for .NET (τελευταία έκδοση τη στιγμή της συγγραφής)  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}