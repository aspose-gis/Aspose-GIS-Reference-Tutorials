---
date: 2026-05-31
description: Μάθετε πώς να δημιουργήσετε GeoJSON, να διαμορφώσετε τις επιλογές GeoJSON
  και να προσθέσετε χαρακτηριστικό σε στρώση χρησιμοποιώντας το Aspose.GIS for .NET.
  Ακολουθήστε αυτόν τον οδηγό βήμα‑βήμα.
keywords:
- how to create geojson
- add feature to layer
- configure geojson options
linktitle: Ορισμός Linearization Tolerance
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  headline: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  name: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  steps:
  - name: Configure GeoJSON Options (how to set tolerance)
    text: '`GeoJsonOptions` specifies the serialization settings used when writing
      GeoJSON files. `GeoJsonOptions` defines how Aspose.GIS serializes GeoJSON, including
      linearization tolerance, coordinate precision, and other output settings. We’ll
      create a `GeoJsonOptions` object and tell Aspose.GIS how close '
  - name: Define the Output Path (how to export GeoJSON)
    text: Specify the full file path where the resulting GeoJSON will be saved. Ensure
      the folder exists and the application has write permissions.
  - name: '**Create Vector Layer** with the configured options'
    text: The `VectorLayer` class represents a GIS container that can read and write
      spatial data. `Drivers.GeoJson` is the driver identifier for writing GeoJSON
      format files. Using `VectorLayer.Create` together with the `Drivers.GeoJson`
      driver and the previously configured `GeoJsonOptions` creates a new Geo
  - name: Construct a Geometry (e.g., a circular string)
    text: '`CircularString` is a curved line geometry that Aspose.GIS can linearize
      based on the tolerance you set. You can replace this with any valid WKT representation
      such as `POINT`, `LINESTRING`, or `POLYGON`.'
  - name: '**Add Feature to Layer** and save'
    text: '`Feature` is the object that couples a geometry with attribute data. After
      creating a `Feature` instance, assign the geometry, optionally add attribute
      values, and call `layer.Add(feature)` to persist it. When the `using` block
      ends, the layer is automatically written to the file defined in `path`. '
  type: HowTo
- questions:
  - answer: Yes, it works with .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6/7.
    question: Is Aspose.GIS for .NET compatible with other .NET frameworks?
  - answer: Absolutely. A commercial license removes all evaluation restrictions and
      provides full technical support.
    question: Can I use Aspose.GIS in commercial projects?
  - answer: Yes, it supports over 30 formats—including Shapefile, KML, GML, and CSV—allowing
      seamless conversion between them.
    question: Does Aspose.GIS support other GIS formats besides GeoJSON?
  - answer: You can download a free 30‑day trial from the Aspose website; it includes
      all features.
    question: Is there a trial version available?
  - answer: Use the Aspose forums, the dedicated support portal, or the “Contact Support”
      link in the product dashboard.
    question: Where can I get support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Πώς να δημιουργήσετε GeoJSON με ανοχή Aspose.GIS for .NET
url: /el/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε GeoJSON με ανοχή Aspose.GIS για .NET

## Εισαγωγή
Αν θέλετε να **μάθετε πώς να δημιουργήσετε αρχεία GeoJSON**, να ελέγξετε την ακρίβεια των καμπυλών και να εξάγετε το αποτέλεσμα ως έτοιμο προς χρήση έγγραφο, το Aspose.GIS για .NET το καθιστά απλό. Σε αυτό το tutorial θα ανακαλύψετε πώς να διαμορφώσετε τις επιλογές GeoJSON, να ορίσετε την ανοχή γραμμικοποίησης και να **προσθέσετε χαρακτηριστικό σε στρώση** αντικείμενα, διατηρώντας τον κώδικα καθαρό και έτοιμο για παραγωγή.

## Γρήγορες Απαντήσεις
- **Τι σημαίνει “create vector layer”;** Δημιουργεί ένα νέο σύνολο δεδομένων GIS vector (π.χ., ένα αρχείο GeoJSON) που μπορεί να αποθηκεύσει γεωμετρίες και χαρακτηριστικά.  
- **Πώς ορίζω την ανοχή γραμμικοποίησης;** Ορίστε την ιδιότητα `LinearizationTolerance` σε ένα αντικείμενο `GeoJsonOptions` πριν δημιουργήσετε τη στρώση.  
- **Μπορώ να εξάγω απευθείας ένα αρχείο GeoJSON;** Ναι—χρησιμοποιήστε το `VectorLayer.Create` με τον οδηγό `Drivers.GeoJson` και τις διαμορφωμένες επιλογές.  
- **Χρειάζομαι άδεια;** Μια έγκυρη άδεια Aspose.GIS ξεκλειδώνει όλες τις λειτουργίες· ένα προσωρινό κλειδί αξιολόγησης λειτουργεί για δοκιμές.  
- **Ποιες εκδόσεις .NET υποστηρίζονται;** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Τι είναι το “create vector layer”;
Η δημιουργία μιας vector layer σημαίνει την αρχικοποίηση ενός νέου κοντέινερ GIS (όπως ένα αρχείο GeoJSON) που μπορεί να περιέχει σημεία, γραμμές, πολύγωνα και τα συναφή δεδομένα χαρακτηριστικών. Αυτή η στρώση γίνεται ο στόχος για οποιαδήποτε γεωμετρία δημιουργείτε και για τυχόν χαρακτηριστικά που προσθέτετε.

## Γιατί να διαμορφώσετε τις επιλογές GeoJSON;
Η διαμόρφωση των επιλογών GeoJSON—ιδιαίτερα η **ανοχή γραμμικοποίησης**—εξασφαλίζει ότι οι καμπυλωτές γεωμετρίες (π.χ., `CircularString`) προσεγγίζονται με ακρίβεια που ικανοποιεί τις απαιτήσεις ακρίβειας της εφαρμογής σας. Η σωστή διαμόρφωση μειώνει το μέγεθος του αρχείου διατηρώντας την οπτική πιστότητα, κάτι κρίσιμο όταν το GeoJSON καταναλώνεται από διαδικτυακούς χάρτες ή εργαλεία χωρικής ανάλυσης.

## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε:

1. **Visual Studio** (οποιαδήποτε πρόσφατη έκδοση).  
2. **Άδεια Aspose.GIS** (ή ένα προσωρινό κλειδί αξιολόγησης).  
3. **Βιβλιοθήκη Aspose.GIS for .NET** που αναφέρεται στο έργο σας.  
4. Βασική εξοικείωση με την **C#**.

## Εισαγωγή Namespaces
Πρώτα, εισάγετε τα απαιτούμενα namespaces ώστε ο μεταγλωττιστής να γνωρίζει πού να βρει τις κλάσεις GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Οδηγός βήμα‑βήμα

### Βήμα 1: Διαμόρφωση επιλογών GeoJSON (πώς να ορίσετε την ανοχή)
`GeoJsonOptions` καθορίζει τις ρυθμίσεις σειριοποίησης που χρησιμοποιούνται κατά τη συγγραφή αρχείων GeoJSON.  
`GeoJsonOptions` ορίζει πώς το Aspose.GIS σειριοποιεί GeoJSON, συμπεριλαμβανομένης της ανοχής γραμμικοποίησης, της ακρίβειας συντεταγμένων και άλλων ρυθμίσεων εξόδου.  
Θα δημιουργήσουμε ένα αντικείμενο `GeoJsonOptions` και θα πούμε στο Aspose.GIS πόσο κοντά πρέπει να είναι η γραμμικοποιημένη γεωμετρία στην αρχική καμπύλη.

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### Βήμα 2: Ορισμός διαδρομής εξόδου (πώς να εξάγετε GeoJSON)
Καθορίστε τη πλήρη διαδρομή αρχείου όπου θα αποθηκευτεί το παραγόμενο GeoJSON. Βεβαιωθείτε ότι ο φάκελος υπάρχει και ότι η εφαρμογή έχει δικαιώματα εγγραφής.

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### Βήμα 3: **Create Vector Layer** με τις διαμορφωμένες επιλογές
Η κλάση `VectorLayer` αντιπροσωπεύει ένα κοντέινερ GIS που μπορεί να διαβάζει και να γράφει χωρικά δεδομένα.  
`Drivers.GeoJson` είναι το αναγνωριστικό οδηγού για τη γραφή αρχείων μορφής GeoJSON.  
Χρησιμοποιώντας το `VectorLayer.Create` μαζί με τον οδηγό `Drivers.GeoJson` και τις προηγουμένως διαμορφωμένες `GeoJsonOptions` δημιουργείται ένα νέο αρχείο GeoJSON έτοιμο για εισαγωγή χαρακτηριστικών.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### Βήμα 4: Κατασκευή γεωμετρίας (π.χ., μια κυκλική αλυσίδα)
`CircularString` είναι μια καμπυλωτή γραμμή γεωμετρίας που το Aspose.GIS μπορεί να γραμμικοποιήσει βάσει της ανοχής που ορίζετε. Μπορείτε να το αντικαταστήσετε με οποιαδήποτε έγκυρη αναπαράσταση WKT όπως `POINT`, `LINESTRING` ή `POLYGON`.

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### Βήμα 5: **Add Feature to Layer** και αποθήκευση
`Feature` είναι το αντικείμενο που συνδέει μια γεωμετρία με δεδομένα χαρακτηριστικών. Μετά τη δημιουργία ενός αντικειμένου `Feature`, εκχωρήστε τη γεωμετρία, προαιρετικά προσθέστε τιμές χαρακτηριστικών και καλέστε `layer.Add(feature)` για να το αποθηκεύσετε. Όταν το μπλοκ `using` ολοκληρωθεί, η στρώση γράφεται αυτόματα στο αρχείο που ορίζεται στο `path`.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

Όταν το μπλοκ `using` ολοκληρωθεί, η στρώση γράφεται αυτόματα στο αρχείο που ορίζεται στο `path`, παρέχοντάς σας ένα έτοιμο προς χρήση αρχείο GeoJSON.

## Συχνά Προβλήματα & Συμβουλές
- **Λανθασμένη διαδρομή** – Επαληθεύστε ότι ο φάκελος υπάρχει και ότι έχετε δικαιώματα εγγραφής.  
- **Πολύ μικρή ανοχή** – Ορίζοντας το `LinearizationTolerance` σε πολύ μικρή τιμή μπορεί να αυξήσει δραματικά το μέγεθος του αρχείου· μια ανοχή 0.001 συνήθως ισορροπεί την ακρίβεια και το μέγεθος.  
- **Σφάλματα άδειας** – Εάν βλέπετε προειδοποιήσεις άδειας, βεβαιωθείτε ότι το αρχείο άδειας φορτώνεται πριν από οποιεσδήποτε κλήσεις Aspose.GIS.  
- **Σημείωση απόδοσης** – Το Aspose.GIS υποστηρίζει την επεξεργασία αρχείων έως 2 GB χωρίς να φορτώνει ολόκληρο το έγγραφο στη μνήμη, χάρη στην αρχιτεκτονική ροής του.

## Συχνές Ερωτήσεις

**Q: Είναι το Aspose.GIS για .NET συμβατό με άλλα .NET frameworks;**  
A: Ναι, λειτουργεί με .NET Framework 4.5+, .NET Core 3.1+ και .NET 5/6/7.

**Q: Μπορώ να χρησιμοποιήσω το Aspose.GIS σε εμπορικά έργα;**  
A: Απόλυτα. Μια εμπορική άδεια αφαιρεί όλους τους περιορισμούς αξιολόγησης και παρέχει πλήρη τεχνική υποστήριξη.

**Q: Υποστηρίζει το Aspose.GIS άλλες μορφές GIS εκτός από GeoJSON;**  
A: Ναι, υποστηρίζει πάνω από 30 μορφές—συμπεριλαμβανομένων των Shapefile, KML, GML και CSV—επιτρέποντας αδιάλειπτη μετατροπή μεταξύ τους.

**Q: Υπάρχει διαθέσιμη δοκιμαστική έκδοση;**  
A: Μπορείτε να κατεβάσετε μια δωρεάν δοκιμαστική έκδοση 30 ημερών από τον ιστότοπο της Aspose· περιλαμβάνει όλες τις λειτουργίες.

**Q: Πού μπορώ να λάβω υποστήριξη;**  
A: Χρησιμοποιήστε τα φόρουμ της Aspose, το ειδικό portal υποστήριξης ή τον σύνδεσμο “Contact Support” στον πίνακα ελέγχου του προϊόντος.

## Συμπέρασμα
Ακολουθώντας αυτά τα βήματα, τώρα γνωρίζετε **πώς να δημιουργήσετε GeoJSON**, να διαμορφώσετε την ανοχή γραμμικοποίησης και να **προσθέσετε χαρακτηριστικό σε στρώση** για απρόσκοπτη εξαγωγή GeoJSON. Εξερευνήστε πρόσθετους τύπους γεωμετριών, διαχείριση χαρακτηριστικών και σενάρια μαζικής επεξεργασίας για να αξιοποιήσετε πλήρως το Aspose.GIS στα .NET GIS έργα σας.

---

**Last Updated:** 2026-05-31  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικά Μαθήματα

- [Πώς να μετατρέψετε GeoJSON – Aspose.GIS για .NET](/gis/net/geo-data-conversion/)
- [Δημιουργία Vector Layer, Περιορισμός Ακρίβειας με Aspose.GIS για .NET](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [Δημιουργία Vector Layer σε File GDB – Aspose.GIS .NET Tutorial](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}