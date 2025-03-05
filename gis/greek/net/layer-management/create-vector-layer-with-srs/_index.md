---
title: Δημιουργήστε διανυσματικό επίπεδο με SRS
linktitle: Δημιουργήστε διανυσματικό επίπεδο με SRS
second_title: Aspose.GIS .NET API
description: Εξερευνήστε το Aspose.GIS για .NET - το κλειδί σας για απρόσκοπτη ενσωμάτωση GIS. Δημιουργήστε διανυσματικά επίπεδα χωρίς κόπο με καθορισμένα χωρικά συστήματα αναφοράς. Κατεβάστε τώρα!
type: docs
weight: 13
url: /el/net/layer-management/create-vector-layer-with-srs/
---
## Εισαγωγή
Το Aspose.GIS για .NET είναι μια ισχυρή βιβλιοθήκη που επιτρέπει στους προγραμματιστές να εργάζονται με δεδομένα συστήματος γεωγραφικών πληροφοριών (GIS) απρόσκοπτα σε εφαρμογές .NET. Σε αυτό το σεμινάριο, θα επικεντρωθούμε στη δημιουργία ενός διανυσματικού επιπέδου με ένα χωρικό σύστημα αναφοράς (SRS). Μέχρι το τέλος αυτού του οδηγού, θα είστε σε θέση να ενσωματώσετε αβίαστα τις δυνατότητες GIS στα έργα σας .NET.
## Προαπαιτούμενα
Πριν ξεκινήσουμε το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Βασικές γνώσεις ανάπτυξης C# και .NET.
-  Εγκαταστάθηκε το Aspose.GIS για τη βιβλιοθήκη .NET. Μπορείτε να το κατεβάσετε[εδώ](https://releases.aspose.com/gis/net/).
- Ένα περιβάλλον ανάπτυξης που έχει δημιουργηθεί και είναι έτοιμο.
## Εισαγωγή χώρων ονομάτων
Βεβαιωθείτε ότι έχετε εισαγάγει τους απαραίτητους χώρους ονομάτων στην αρχή του αρχείου C#:
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
## Βήμα 1: Ρύθμιση του Προβαλλόμενου Συστήματος Χωρικής Αναφοράς
Ας δημιουργήσουμε ένα προβαλλόμενο χωρικό σύστημα αναφοράς (SRS) χρησιμοποιώντας την προβολή World Mercator ως παράδειγμα. Ακολουθήστε αυτά τα βήματα:
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
## Βήμα 2: Δημιουργήστε ένα διανυσματικό επίπεδο και προσθέστε χαρακτηριστικά
Τώρα, ας δημιουργήσουμε ένα αρχείο σχήματος και ας προσθέσουμε χαρακτηριστικά με το καθορισμένο SRS:
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
        layer.Add(feature); // Αυτό θα δημιουργήσει μια εξαίρεση καθώς η γεωμετρία έχει διαφορετικό SRS
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```
## Βήμα 3: Επαλήθευση του συστήματος χωρικής αναφοράς
Τέλος, ας ανοίξουμε το επίπεδο και ας επαληθεύσουμε το χωρικό σύστημα αναφοράς του:
```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Θα πρέπει να επιστρέψει αληθινό
}
```
Ακολουθώντας αυτά τα βήματα, δημιουργήσατε με επιτυχία ένα διανυσματικό επίπεδο με ένα καθορισμένο χωρικό σύστημα αναφοράς χρησιμοποιώντας το Aspose.GIS για .NET.
## συμπέρασμα
Η ενσωμάτωση της λειτουργικότητας GIS στις εφαρμογές σας .NET δεν ήταν ποτέ ευκολότερη, χάρη στο Aspose.GIS. Με τη δυνατότητα να δημιουργείτε αβίαστα διανυσματικά επίπεδα και να διαχειρίζεστε συστήματα χωρικής αναφοράς, μπορείτε να βελτιώσετε τα έργα σας με ισχυρές γεωχωρικές δυνατότητες.
## Συχνές ερωτήσεις
### Είναι το Aspose.GIS συμβατό με όλες τις μορφές αρχείων GIS;
 Το Aspose.GIS υποστηρίζει διάφορες μορφές GIS, συμπεριλαμβανομένων των Shapefile, GeoJSON, KML και άλλων. Ελεγξε το[τεκμηρίωση](https://reference.aspose.com/gis/net/) για την πλήρη λίστα.
### Μπορώ να χρησιμοποιήσω το Aspose.GIS σε μια διαδικτυακή εφαρμογή;
Απολύτως! Το Aspose.GIS για .NET είναι ευέλικτο και μπορεί να χρησιμοποιηθεί σε εφαρμογές web, εφαρμογές επιτραπέζιων υπολογιστών, ακόμη και εφαρμογές για κινητά.
### Πού μπορώ να λάβω υποστήριξη για το Aspose.GIS;
 Μπορείτε να βρείτε μια χρήσιμη κοινότητα στο[Φόρουμ Aspose.GIS](https://forum.aspose.com/c/gis/33) για τυχόν απορίες ή προβλήματα που μπορεί να αντιμετωπίσετε.
### Υπάρχει δωρεάν δοκιμή διαθέσιμη;
 Ναι, μπορείτε να εξερευνήσετε τις δυνατότητες του Aspose.GIS αποκτώντας μια δωρεάν δοκιμή[εδώ](https://releases.aspose.com/).
### Πώς μπορώ να αγοράσω άδεια χρήσης για το Aspose.GIS;
 Για να αγοράσετε μια άδεια, επισκεφτείτε το[σελίδα αγοράς](https://purchase.aspose.com/buy).