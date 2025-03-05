---
title: Απομυθοποιήθηκε η μετατροπή GeoJSON σε αρχείο GDB
linktitle: Μετατρέψτε το επίπεδο GeoJSON σε αρχείο GDB
second_title: Aspose.GIS .NET API
description: Ξεκλειδώστε τα γεωχωρικά θαύματα με το Aspose.GIS για .NET! Μετατρέψτε εύκολα τα επίπεδα GeoJSON σε βάσεις δεδομένων αρχείων. Δοκίμασέ το τώρα! #Αποθέστε #GIS
type: docs
weight: 17
url: /el/net/layer-management/convert-geojson-layer-to-file-gdb/
---
## Εισαγωγή
Στη δυναμική σφαίρα των Συστημάτων Γεωγραφικών Πληροφοριών (GIS), η δυνατότητα απρόσκοπτης μετατροπής δεδομένων μεταξύ διαφορετικών μορφών είναι ζωτικής σημασίας. Το Aspose.GIS για το .NET αναδεικνύεται ως ένας ισχυρός σύμμαχος, προσφέροντας μια ολοκληρωμένη σειρά εργαλείων για τον αβίαστο χειρισμό γεωχωρικών δεδομένων. Σε αυτό το σεμινάριο, θα εμβαθύνουμε στη διαδικασία μετατροπής ενός επιπέδου GeoJSON σε μια βάση δεδομένων αρχείου (File GDB) χρησιμοποιώντας το Aspose.GIS για .NET.
## Προαπαιτούμενα
Πριν ξεκινήσετε αυτό το γεωχωρικό ταξίδι, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Γνώση προγραμματισμού .NET.
-  Εγκαταστάθηκε το Aspose.GIS για .NET. Αν όχι, κατεβάστε το από[εδώ](https://releases.aspose.com/gis/net/) και ακολουθήστε τις οδηγίες εγκατάστασης.
## Εισαγωγή χώρων ονομάτων
Για να ξεκινήσετε τη διαδικασία μετατροπής, ξεκινήστε εισάγοντας τους απαραίτητους χώρους ονομάτων:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
Τώρα, ας αναλύσουμε τη διαδικασία σε έναν οδηγό βήμα προς βήμα:
## Βήμα 1: Ρυθμίστε το επίπεδο GeoJSON
Ξεκινήστε δημιουργώντας ένα επίπεδο GeoJSON με σχετικά χαρακτηριστικά και χαρακτηριστικά. Ακολουθεί ένα απόσπασμα που θα σας καθοδηγήσει:
```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    // Προσθήκη χαρακτηριστικών
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    //Κατασκευάστε και προσθέστε χαρακτηριστικά
    Feature firstFeature = layer.ConstructFeature();
    firstFeature.Geometry = new Point(33.97, -118.25);
    firstFeature.SetValue("name", "John");
    firstFeature.SetValue("age", 23);
    layer.Add(firstFeature);
    Feature secondFeature = layer.ConstructFeature();
    secondFeature.Geometry = new Point(35.81, -96.28);
    secondFeature.SetValue("name", "Mary");
    secondFeature.SetValue("age", 54);
    layer.Add(secondFeature);
}
```
## Βήμα 2: Αντιγραφή συνόλου δεδομένων δοκιμής
Για να διατηρήσετε την ακεραιότητα των δεδομένων δοκιμής σας, δημιουργήστε ένα αντίγραφο του συνόλου δεδομένων. Χρησιμοποιήστε το ακόλουθο απόσπασμα κώδικα:
```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```
## Βήμα 3: Μετατρέψτε το GeoJSON σε Αρχείο GDB
Τώρα, ήρθε η ώρα να εκτελέσετε τη μετατροπή. Χρησιμοποιήστε τον παρακάτω κώδικα:
```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        // Αντιγραφή χαρακτηριστικών
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        // Προσθέστε χαρακτηριστικά
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```
## συμπέρασμα
Σε αυτό το σεμινάριο, περιηγηθήκαμε στο ενδιαφέρον έδαφος της μετατροπής ενός επιπέδου GeoJSON σε μια βάση δεδομένων αρχείου χρησιμοποιώντας το Aspose.GIS για .NET. Οπλισμένοι με αυτή τη γνώση, είστε πλέον εξοπλισμένοι για να χειρίζεστε απρόσκοπτα τα γεωχωρικά δεδομένα στις εφαρμογές σας .NET.
## Συχνές ερωτήσεις
### Είναι το Aspose.GIS συμβατό με το πιο πρόσφατο πλαίσιο .NET;
Ναι, το Aspose.GIS είναι συμβατό με τις πιο πρόσφατες εκδόσεις πλαισίου .NET.
### Μπορώ να μετατρέψω άλλες γεωχωρικές μορφές χρησιμοποιώντας το Aspose.GIS;
Απολύτως! Το Aspose.GIS υποστηρίζει ένα ευρύ φάσμα γεωχωρικών μορφών για ευέλικτο χειρισμό δεδομένων.
### Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.GIS;
 Ναι, μπορείτε να εξερευνήσετε τις λειτουργίες του Aspose.GIS κατεβάζοντας τη δοκιμαστική έκδοση[εδώ](https://releases.aspose.com/).
### Πώς μπορώ να λάβω υποστήριξη για ερωτήματα που σχετίζονται με το Aspose.GIS;
 Μεταβείτε στο Aspose.GIS[δικαστήριο](https://forum.aspose.com/c/gis/33) για αποκλειστική υποστήριξη.
### Μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.GIS;
 Ναι, μπορείτε να εξασφαλίσετε μια προσωρινή άδεια[εδώ](https://purchase.aspose.com/temporary-license/).