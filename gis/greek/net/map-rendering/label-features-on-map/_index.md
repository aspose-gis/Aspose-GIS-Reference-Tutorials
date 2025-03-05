---
title: Mastering Feature Labeling με το Aspose.GIS για .NET
linktitle: Χαρακτηριστικά ετικέτας στον χάρτη
second_title: Aspose.GIS .NET API
description: Εξερευνήστε το Aspose.GIS για .NET και κατακτήστε την τέχνη της επισήμανσης χαρακτηριστικών σε χάρτες. Βελτιώστε τις γεωχωρικές απεικονίσεις σας χωρίς κόπο. #Αποθέστε #GIS
type: docs
weight: 11
url: /el/net/map-rendering/label-features-on-map/
---
## Εισαγωγή
Στον κόσμο της οπτικοποίησης γεωχωρικών δεδομένων, η επισήμανση χαρακτηριστικών σε έναν χάρτη διαδραματίζει κρίσιμο ρόλο στην αποτελεσματική μετάδοση πληροφοριών. Το Aspose.GIS για .NET παρέχει μια ισχυρή εργαλειοθήκη για την απρόσκοπτη επίτευξη αυτού του στόχου. Σε αυτό το σεμινάριο, θα εξερευνήσουμε διάφορες μεθόδους επισήμανσης σημείων σε έναν χάρτη χρησιμοποιώντας το Aspose.GIS, βελτιώνοντας τις απεικονίσεις του χάρτη σας με ενημερωτικές ετικέτες.
## Προαπαιτούμενα
Πριν ξεκινήσετε το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Γνώση εργασίας της C# και του πλαισίου .NET.
-  Εγκαταστάθηκε το Aspose.GIS για .NET. Μπορείτε να το κατεβάσετε[εδώ](https://releases.aspose.com/gis/net/).
- Ένα αρχείο GeoJSON που περιέχει σημειακά δεδομένα. Εάν δεν έχετε, μπορείτε να χρησιμοποιήσετε ένα δείγμα αρχείου για δοκιμή.
## Εισαγωγή χώρων ονομάτων
Στον κώδικα C#, βεβαιωθείτε ότι εισάγετε τους απαραίτητους χώρους ονομάτων για την εργασία με το Aspose.GIS:
```csharp
using System;
using System.Drawing;
using Aspose.Gis;
using Aspose.Gis.Rendering;
using Aspose.Gis.Rendering.Labelings;
using Aspose.Gis.Rendering.Symbolizers;
using Aspose.GIS.Examples.CSharp;
using FontStyle = Aspose.Gis.Rendering.Labelings.FontStyle;
```
Τώρα, ας αναλύσουμε κάθε παράδειγμα σε πολλά βήματα σε μια μορφή οδηγού βήμα προς βήμα.
##  Επισήμανση σημείων

### Βήμα 1: Ορίστε τη διαδρομή προς τον κατάλογο των εγγράφων σας:
```csharp
string dataDir = "Your Document Directory";
```
### Βήμα 2: Δημιουργήστε έναν χάρτη με ένα απλό σύμβολο δείκτη:
```csharp
using (var map = new Map(500, 200))
{
    var symbol = new SimpleMarker
    {
        FillColor = Color.LightGray,
        StrokeStyle = StrokeStyle.None
    };
    var labeling = new SimpleLabeling(labelAttribute: "name");
    // 3. Προσθέστε ένα διανυσματικό στρώμα και εφαρμόστε ετικέτα
    map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), symbol, labeling);
    map.Padding = 50;
    // 4. Αποδώστε τον χάρτη σε αρχείο SVG
    map.Render(dataDir + "points_labeling_out.svg", Renderers.Svg);
}
```
## Σημεία με στυλ

Ακολουθήστε τα βήματα 1 και 2 από το προηγούμενο παράδειγμα.

### Βήμα 1: Προσαρμόστε το στυλ ετικετών:
```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 2,
    HaloColor = Color.LightGray,
    FontSize = 15,
    FontStyle = FontStyle.Italic,
};
// Τα υπόλοιπα βήματα παραμένουν ίδια
```
## Σημεία τοποθέτησης ετικέτας

Ακολουθήστε τα βήματα 1 και 2 από το πρώτο παράδειγμα.
### Βήμα 2: Προσαρμόστε την τοποθέτηση της ετικέτας:
```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 1,
    Placement = new PointLabelPlacement
    {
        VerticalAnchorPoint = VerticalAnchor.Bottom,
        HorizontalAnchorPoint = HorizontalAnchor.Left,
        HorizontalOffset = 2,
        VerticalOffset = 2,
        Rotation = 10,
    }
};
// Τα υπόλοιπα βήματα παραμένουν ίδια
```
## Βάσει χαρακτηριστικών ετικετών σημείων

Ακολουθήστε τα βήματα 1 και 2 από το πρώτο παράδειγμα.

### Βήμα 1: Εφαρμογή ετικετών βάσει χαρακτηριστικών:
```csharp
var pointLabeling = new SimpleLabeling("name")
{
    HaloSize = 1,
    Placement = new PointLabelPlacement
    {
        VerticalAnchorPoint = VerticalAnchor.Bottom,
        HorizontalAnchorPoint = HorizontalAnchor.Left,
        VerticalOffset = 4,
        HorizontalOffset = 4,
    },
    FeatureBasedConfiguration = (feature, labeling) =>
    {
        // Ανάκτηση πληθυσμού από το χαρακτηριστικό.
        var population = feature.GetValue<int>("population");
        // Το μέγεθος της γραμματοσειράς υπολογίζεται και βασίζεται στον πληθυσμό.
        labeling.FontSize = Math.Min(20, 5 * population / 1000);
        // Η προτεραιότητα της ετικέτας βασίζεται επίσης στον πληθυσμό.
        // Όσο μεγαλύτερη είναι η προτεραιότητα, τόσο πιο πιθανό είναι να εμφανιστεί η ετικέτα στην εικόνα εξόδου.
        labeling.Priority = population;
    }
};
// Τα υπόλοιπα βήματα παραμένουν ίδια
```
## συμπέρασμα
Συγχαρητήρια! Έχετε μάθει πώς να βελτιώνετε τις απεικονίσεις των χαρτών σας προσθέτοντας ετικέτες σε χαρακτηριστικά χρησιμοποιώντας το Aspose.GIS για .NET. Πειραματιστείτε με διαφορετικά στυλ και τοποθετήσεις για να δημιουργήσετε συναρπαστικούς χάρτες προσαρμοσμένους στα δεδομένα σας.
## Συχνές ερωτήσεις
### Μπορώ να προσθέσω ετικέτες σε χαρακτηριστικά χρησιμοποιώντας προσαρμοσμένες γραμματοσειρές;
Ναι, μπορείτε να προσαρμόσετε το στυλ και το μέγεθος γραμματοσειράς στη διαμόρφωση ετικετών.
### Είναι το Aspose.GIS συμβατό με άλλες μορφές δεδομένων GIS;
Το Aspose.GIS υποστηρίζει διάφορες γεωχωρικές μορφές, συμπεριλαμβανομένων των GeoJSON, Shapefile και άλλων.
### Πώς μπορώ να χειριστώ μεγάλα σύνολα δεδομένων για επισήμανση;
Το Aspose.GIS είναι βελτιστοποιημένο για απόδοση, αλλά σκεφτείτε να χρησιμοποιήσετε διαμορφώσεις που βασίζονται σε χαρακτηριστικά για να δώσετε προτεραιότητα στις ετικέτες με βάση τα χαρακτηριστικά δεδομένων.
### Υπάρχουν διαθέσιμες προηγμένες επιλογές τοποθέτησης ετικετών;
Ναι, μπορείτε να ρυθμίσετε την τοποθέτηση ετικετών χρησιμοποιώντας επιλογές όπως περιστροφή, σημεία αγκύρωσης και μετατοπίσεις.
### Μπορώ να αυτοματοποιήσω τη δημιουργία ετικετών σε μια διαδικασία παρτίδας;
Οπωσδήποτε, μπορείτε να ενσωματώσετε το Aspose.GIS στις αυτοματοποιημένες ροές εργασίας σας για τη δημιουργία ετικετών παρτίδας.