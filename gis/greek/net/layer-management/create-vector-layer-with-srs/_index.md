---
date: 2026-06-30
description: Μάθετε πώς να δημιουργήσετε διανυσματική στρώση με σύστημα αναφοράς χώρου
  χρησιμοποιώντας το Aspose.GIS για .NET. Οδηγός βήμα προς βήμα, εξηγήσεις χωρίς κώδικα
  και Συχνές Ερωτήσεις.
keywords:
- how to create vector layer
- Aspose.GIS spatial reference
- .NET GIS tutorial
linktitle: Πώς να δημιουργήσετε διανυσματική στρώση με SRS χρησιμοποιώντας το Aspose.GIS
  για .NET
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create vector layer with a spatial reference system using
    Aspose.GIS for .NET. Step‑by‑step guide, code‑free explanations, and FAQs.
  headline: How to Create Vector Layer with SRS using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS throws a `GisException`. You must either reproject the geometry
      or ensure it shares the layer’s SRS.
    question: What happens if I try to add a geometry with a different SRS?
  - answer: Yes, you can create a new layer with the desired SRS and copy features
      over, reprojecting them as needed.
    question: Can I change the SRS of an existing layer?
  - answer: Aspose.GIS supports Z‑coordinates; just use geometry constructors that
      accept a Z value.
    question: Is it possible to work with 3D coordinates?
  - answer: When you reproject geometries using `Geometry.Transform`, Aspose.GIS performs
      the necessary datum shift.
    question: Does the library handle datum transformations automatically?
  - answer: The library is tested with .NET Framework 4.5+, .NET Core 3.1+, and .NET
      5/6/7.
    question: Which .NET versions are officially tested?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Πώς να δημιουργήσετε διανυσματική στρώση με SRS χρησιμοποιώντας το Aspose.GIS
  για .NET
url: /el/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε διανυσματικό στρώμα με SRS χρησιμοποιώντας το Aspose.GIS για .NET

## Εισαγωγή
Σε αυτό το σεμινάριο θα ανακαλύψετε **how to create vector layer** αντικείμενα που περιλαμβάνουν ένα σύστημα αναφοράς χώρου (SRS) με το Aspose.GIS για .NET. Θα περάσουμε από τη λογική πίσω από την ανάθεση ενός SRS, θα δείξουμε τα ακριβή βήματα για τη ρύθμισή του και θα εξηγήσουμε τα πραγματικά πλεονεκτήματα, όπως ακριβείς μετρήσεις και αδιάσπαστη επικάλυψη με άλλα GIS δεδομένα. Στο τέλος, θα είστε έτοιμοι να ενσωματώσετε ισχυρή λειτουργικότητα GIS σε οποιαδήποτε εφαρμογή .NET.

## Γρήγορες Απαντήσεις
- **Ποιος είναι ο κύριος σκοπός αυτού του σεμιναρίου;** Για να δείξει πώς να δημιουργήσετε vector layer με καθορισμένο SRS χρησιμοποιώντας το Aspose.GIS για .NET.  
- **Ποια προβολή χρησιμοποιείται στο παράδειγμα;** World Mercator (EPSG:3395).  
- **Χρειάζομαι άδεια για να εκτελέσω τον κώδικα;** Μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη· απαιτείται εμπορική άδεια για παραγωγή.  
- **Μπορώ να χρησιμοποιήσω την ίδια προσέγγιση με άλλες μορφές GIS;** Ναι, η ίδια διαχείριση SRS ισχύει για Shapefile, GeoJSON, KML, κ.λπ.  
- **Ποιες εκδόσεις .NET υποστηρίζονται;** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Τι είναι ένα διανυσματικό στρώμα και γιατί να ορίσετε την χωρική του αναφορά;
Ένα **vector layer** αποθηκεύει γεωμετρικά χαρακτηριστικά (σημεία, γραμμές, πολύγωνα) μαζί με δεδομένα χαρακτηριστικών. Η ανάθεση ενός **spatial reference system** λέει στο λογισμικό GIS πώς να χαρτογραφήσει αυτές τις συντεταγμένες στην επιφάνεια της γης, εξασφαλίζοντας ακριβείς υπολογισμούς αποστάσεων, σωστή ευθυγράμμιση στρωμάτων και αξιόπιστη απόδοση χάρτη.

## Γιατί να ορίσετε ένα σύστημα χωρικής αναφοράς;
Η χρήση ενός καθορισμένου SRS μειώνει τα σφάλματα μετατροπής συντεταγμένων έως και 95 % όταν επικάλυπται στρώματα από διαφορετικές πηγές. Το Aspose.GIS υποστηρίζει **20+** μορφές εισόδου και εξόδου — συμπεριλαμβανομένων των Shapefile, GeoJSON, KML και GML — ενώ επεξεργάζεται σύνολα δεδομένων πολλών εκατοντάδων σελίδων χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη.

## Προαπαιτούμενα
- Βασικές γνώσεις C# και ανάπτυξης .NET.  
- Η βιβλιοθήκη Aspose.GIS για .NET εγκατεστημένη. Μπορείτε να την κατεβάσετε **[here](https://releases.aspose.com/gis/net/)**.  
- Ένα περιβάλλον ανάπτυξης (Visual Studio, VS Code ή οποιοδήποτε IDE C#).  

## Εισαγωγή Namespaces
Βεβαιωθείτε ότι έχετε εισάγει τους απαραίτητους ονοματοχώρους στην αρχή του αρχείου C# σας:

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
Φορτώστε το προβλεπόμενο SRS σας σε δύο γραμμές: δημιουργήστε ένα αντικείμενο `ProjectedSpatialReferenceSystem`, ρυθμίστε τις παραμέτρους προβολής Mercator και είστε έτοιμοι να το συνδέσετε με ένα στρώμα.

`ProjectedSpatialReferenceSystem` είναι μια κλάση που περιγράφει ένα προβλεπόμενο σύστημα αναφοράς συντεταγμένων.  
`ProjectedSpatialReferenceSystemParameters` περιέχει τις παραμέτρους που απαιτούνται για τη διαμόρφωση ενός προβλεπόμενου SRS, όπως το κεντρικό μεσημβρινό και ο συντελεστής κλίμακας.

Ας δημιουργήσουμε ένα **projected spatial reference system** χρησιμοποιώντας την προβολή World Mercator ως παράδειγμα. Αυτό δείχνει **how to set srs** για ένα στρώμα.

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
Δημιουργήστε ένα στρώμα Shapefile, περάστε το προηγουμένως ορισμένο `projectedSrs` και, στη συνέχεια, προσθέστε γεωμετρίες των οποίων το `SpatialReferenceSystem` ταιριάζει με το SRS του στρώματος.

`Layer` (π.χ., ένα Shapefile) αντιπροσωπεύει μια συλλογή χαρακτηριστικών αποθηκευμένων σε ένα ενιαίο αρχείο GIS.  
Τώρα θα **create a vector layer** (ένα Shapefile) και θα προσθέσουμε χαρακτηριστικά που χρησιμοποιούν το SRS που μόλις ορίσαμε. Αυτό το τμήμα απαντά στο **how to create layer** με το Aspose.GIS.

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

## Επαλήθευση Συστήματος Χωρικής Αναφοράς – Βήμα 3
Ανοίξτε το νεοδημιουργημένο στρώμα, ανακτήστε το `SpatialReferenceSystem` του και συγκρίνετε το με το αρχικό `projectedSrs` χρησιμοποιώντας το `IsEquivalent`. Ένα αποτέλεσμα `true` επιβεβαιώνει ότι το SRS εφαρμόστηκε σωστά.

`IsEquivalent` ελέγχει εάν δύο συστήματα χωρικής αναφοράς αντιπροσωπεύουν το ίδιο σύστημα συντεταγμένων.  
Τέλος, ανοίξτε το στρώμα και επιβεβαιώστε ότι το SRS εφαρμόστηκε σωστά.

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

Αν η κλήση `IsEquivalent` επιστρέψει `true`, έχετε δημιουργήσει επιτυχώς **create vector layer** με την επιθυμητή χωρική αναφορά.

## Κοινά Προβλήματα & Λύσεις
`GisException` είναι ο τύπος εξαίρεσης που ρίχνει το Aspose.GIS για σφάλματα όπως μη ταιριαστό SRS.

| Πρόβλημα | Γιατί συμβαίνει | Διόρθωση |
|----------|----------------|----------|
| `GisException` κατά την προσθήκη χαρακτηριστικού | Η γεωμετρία χρησιμοποιεί διαφορετικό SRS από το στρώμα | Ορίστε `feature.Geometry.SpatialReferenceSystem` στο SRS του στρώματος πριν την προσθήκη |
| Το στρώμα εμφανίζεται κενό στο λογισμικό GIS | Το shapefile δημιουργήθηκε χωρίς σωστό αρχείο `.prj` | Βεβαιωθείτε ότι το αντικείμενο `projectedSrs` περνιέται κατά τη δημιουργία του στρώματος |
| Απρόσμενες τιμές συντεταγμένων | Λάθος παράμετροι προβολής (π.χ., κεντρικό μεσημβρινό) | Ελέγξτε ξανά τις παραμέτρους που περνιούνται στο `AddProjectionParameter` |

## Συχνές Ερωτήσεις
### Είναι το Aspose.GIS συμβατό με όλες τις μορφές αρχείων GIS;
Το Aspose.GIS υποστηρίζει **20+** μορφές GIS, συμπεριλαμβανομένων των Shapefile, GeoJSON, KML, GML και άλλων. Δείτε την **[documentation](https://reference.aspose.com/gis/net/)** για την πλήρη λίστα.

### Μπορώ να χρησιμοποιήσω το Aspose.GIS σε μια web εφαρμογή;
Απολύτως! Το Aspose.GIS για .NET λειτουργεί σε ASP.NET, ASP.NET Core και οποιοδήποτε περιβάλλον .NET στο διακομιστή.

### Πού μπορώ να λάβω υποστήριξη για το Aspose.GIS;
Μπορείτε να βρείτε μια χρήσιμη κοινότητα στο **[Aspose.GIS forum](https://forum.aspose.com/c/gis/33)** για οποιεσδήποτε ερωτήσεις ή προβλήματα αντιμετωπίζετε.

### Υπάρχει διαθέσιμη δωρεάν δοκιμή;
Ναι, μπορείτε να εξερευνήσετε τις δυνατότητες του Aspose.GIS αποκτώντας μια δωρεάν δοκιμή **[here](https://releases.aspose.com/)**.

### Πώς μπορώ να αγοράσω άδεια για το Aspose.GIS;
Για να αγοράσετε άδεια, επισκεφθείτε τη **[purchase page](https://purchase.aspose.com/buy)**.

## Συχνές Ερωτήσεις (Πρόσθετες)

**Q: Τι συμβαίνει αν προσπαθήσω να προσθέσω μια γεωμετρία με διαφορετικό SRS;**  
A: Το Aspose.GIS ρίχνει ένα `GisException`. Πρέπει είτε να επαναπροβάλετε τη γεωμετρία είτε να εξασφαλίσετε ότι μοιράζεται το SRS του στρώματος.

**Q: Μπορώ να αλλάξω το SRS ενός υπάρχοντος στρώματος;**  
A: Ναι, μπορείτε να δημιουργήσετε ένα νέο στρώμα με το επιθυμητό SRS και να αντιγράψετε τα χαρακτηριστικά, επαναπροβάλλοντάς τα όπως απαιτείται.

**Q: Είναι δυνατόν να εργαστώ με 3D συντεταγμένες;**  
A: Το Aspose.GIS υποστηρίζει Z‑συντεταγμένες· απλώς χρησιμοποιήστε κατασκευαστές γεωμετρίας που δέχονται τιμή Z.

**Q: Η βιβλιοθήκη διαχειρίζεται αυτόματα τις μετασχηματισμούς datum;**  
A: Όταν επαναπροβάλλετε γεωμετρίες χρησιμοποιώντας `Geometry.Transform`, το Aspose.GIS εκτελεί την απαραίτητη μετατόπιση datum.

**Q: Ποιες εκδόσεις .NET δοκιμάζονται επίσημα;**  
A: Η βιβλιοθήκη δοκιμάζεται με .NET Framework 4.5+, .NET Core 3.1+, και .NET 5/6/7.

## Συμπέρασμα
Τώρα έχετε μάθει **how to create vector layer** με προσαρμοσμένο σύστημα χωρικής αναφοράς χρησιμοποιώντας το Aspose.GIS για .NET. Ορίζοντας το σωστό SRS, διαχειριζόμενοι τη γεωμετρία σταθερά και επαληθεύοντας τα μεταδεδομένα του στρώματος, μπορείτε να δημιουργήσετε ισχυρές εφαρμογές με δυνατότητα GIS που συνεργάζονται με οποιοδήποτε τυπικό λογισμικό GIS.

---

**Τελευταία Ενημέρωση:** 2026-06-30  
**Δοκιμή Με:** Aspose.GIS 24.11 for .NET (latest at time of writing)  
**Συγγραφέας:** Aspose

## Σχετικά Σεμινάρια

- [Δημιουργία Διανυσματικού Στρώματος και Ορισμός Συστήματος Χωρικής Αναφοράς Στρώματος](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Δημιουργία Διανυσματικού Στρώματος σε File GDB – Σεμινάριο Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Πώς να Τροποποιήσετε Στρώμα – Επικοινωνία Στρωμάτων Aspose.GIS .NET](/gis/net/layer-interaction-and-data-access/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}