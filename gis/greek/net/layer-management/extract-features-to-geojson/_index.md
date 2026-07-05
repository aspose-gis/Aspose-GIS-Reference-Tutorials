---
date: 2026-07-05
description: Μάθετε πώς να μετατρέψετε shapefile σε geojson χρησιμοποιώντας Aspose.GIS
  για .NET. Ο οδηγός καλύπτει επίσης την αντιγραφή attributes μεταξύ layers και τη
  δημιουργία geojson αρχείου με c#.
keywords:
- convert shapefile to geojson
- export shapefile as geojson
- aspose gis conversion
- read shapefile c#
- write geojson c#
linktitle: Εξαγωγή Features σε GeoJSON
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  headline: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  name: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  steps:
  - name: Open Input Shapefile
    text: The `VectorLayer.Open` method reads a Shapefile and returns an enumerable
      collection of `Feature` objects that you can iterate over.
  - name: Create Output GeoJSON
    text: '`VectorLayer.Create` with the `Drivers.GeoJson` driver creates an empty
      GeoJSON file ready to receive features.'
  - name: Copy Attributes Between Layers
    text: '`CopyAttributes` copies the attribute schema (field names and data types)
      from the source Shapefile to the new GeoJSON layer in a single call.'
  - name: Process Features
    text: Iterate through each feature in the Shapefile so you can apply any custom
      logic before writing it out.
  - name: Filter Features by Date
    text: In this example we skip records whose `dob` (date of birth) field is missing
      or earlier than 1 Jan 1982. Adjust the filter to match your own data requirements.
  - name: Construct a New Feature (C# Generate GeoJSON File)
    text: A `Feature` represents a single spatial element containing geometry and
      attribute data. Here we build a new `Feature` for the GeoJSON layer, copy the
      geometry and attribute values, and add it to the output. This is the core of
      *c# generate geojson file*. Congratulations! You’ve successfully **conver
  type: HowTo
- questions:
  - answer: Visit the [Aspose.GIS documentation](https://reference.aspose.com/gis/net/)
      for in‑depth information.
    question: Where can I find more documentation?
  - answer: You can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I get a temporary license?
  - answer: Join the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I seek support?
  - answer: Yes, you can find the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: You can buy the product [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Μετατροπή Shapefile σε GeoJSON με Aspose.GIS για .NET
url: /el/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Μετατροπή Shapefile σε GeoJSON με Aspose.GIS για .NET

## Εισαγωγή
Σε αυτό το ολοκληρωμένο, βήμα‑βήμα tutorial θα μάθετε **πώς να μετατρέψετε shapefile σε geojson** χρησιμοποιώντας τη δυνατή βιβλιοθήκη Aspose.GIS για .NET. Είτε δημιουργείτε μια υπηρεσία χαρτογράφησης, προετοιμάζετε δεδομένα για μια κινητή GIS εφαρμογή, είτε απλώς χρειάζεστε ανταλλαγή δεδομένων μεταξύ μορφών, αυτός ο οδηγός σας δείχνει ακριβώς τι πρέπει να κάνετε, γιατί κάθε βήμα είναι σημαντικό και πώς να αποφύγετε κοινά προβλήματα.

## Γρήγορες Απαντήσεις
- **Τι καλύπτει αυτό το tutorial;** Μετατροπή ενός Shapefile σε αρχείο GeoJSON, αντιγραφή χαρακτηριστικών μεταξύ επιπέδων, και δημιουργία του αποτελέσματος με C#.
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.GIS for .NET.
- **Χρειάζομαι άδεια;** Απαιτείται προσωρινή ή πλήρης άδεια για παραγωγή· μια δωρεάν δοκιμή λειτουργεί για αξιολόγηση.
- **Πόσο διαρκεί η υλοποίηση;** Περίπου 10‑15 λεπτά για μια βασική μετατροπή.
- **Μπορώ να το τρέξω σε .NET Core/.NET 6;** Ναι – ο κώδικας λειτουργεί σε όλες τις υποστηριζόμενες εκδόσεις του .NET.

## Τι είναι η μετατροπή shapefile σε geojson;
Η μετατροπή ενός Shapefile σε GeoJSON σημαίνει ανάγνωση διανυσματικών χαρακτηριστικών από την κλασική μορφή ESRI Shapefile και εγγραφή τους ως ένα σύγχρονο, φιλικό στο web έγγραφο GeoJSON. Αυτή η μετατροπή σας επιτρέπει να τροφοδοτείτε δεδομένα GIS απευθείας σε βιβλιοθήκες χαρτογράφησης JavaScript όπως Leaflet ή Mapbox GL, και απλοποιεί την ανταλλαγή δεδομένων μεταξύ επιτραπέζιων εργαλείων GIS και web API.

## Γιατί να χρησιμοποιήσετε Aspose.GIS για αυτή τη μετατροπή;
Η Aspose.GIS αφαιρεί την ανάγκη για χαμηλού επιπέδου δυαδική ανάλυση, υποστηρίζει 50+ μορφές εισόδου και εξόδου, και μπορεί να επεξεργαστεί σύνολα δεδομένων εκατοντάδων σελίδων χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη. Η βιβλιοθήκη παρέχει επίσης ένα καθαρό, αντικειμενοστραφές API που λειτουργεί σε .NET Framework, .NET Core και .NET 5/6, ώστε να αφιερώνετε χρόνο στη λογική της επιχείρησης αντί για ιδιαιτερότητες μορφής.

## Προαπαιτούμενα
- Aspose.GIS for .NET: Βεβαιωθείτε ότι έχετε εγκαταστήσει τη βιβλιοθήκη. Αν όχι, μπορείτε να τη κατεβάσετε από τη [Aspose.GIS for .NET page](https://releases.aspose.com/gis/net/).
- Shapefile Data: Έχετε ένα Shapefile έτοιμο για είσοδο. Αν χρειάζεστε δείγμα δεδομένων, μπορείτε να το βρείτε στην [Aspose.GIS documentation](https://reference.aspose.com/gis/net/).
- .NET Environment: Ρυθμίστε ένα περιβάλλον .NET για να εκτελέσετε τον παρεχόμενο κώδικα.
- Document Directory: Ορίστε τη διαδρομή προς τον φάκελο εγγράφων σας στο απόσπασμα κώδικα.

Τώρα που έχετε όλα τα απαραίτητα, ας ξεκινήσουμε τη μετατροπή shapefile σε geojson!

## Πώς να Μετατρέψετε Shapefile σε GeoJSON
Φορτώστε το πηγαίο Shapefile, δημιουργήστε ένα στόχο GeoJSON, αντιγράψτε το σχήμα των χαρακτηριστικών, φιλτράρετε τις εγγραφές και γράψτε τα αποτελέσματα—όλα σε λίγα συνοπτικά βήματα. Η πλήρης ροή εργασίας χωράει άνετα σε ένα ενιαίο μπλοκ `using`, εξασφαλίζοντας την αυτόματη απελευθέρωση πόρων.

### Βήμα 1: Άνοιγμα Εισαγωγικού Shapefile
Η μέθοδος `VectorLayer.Open` διαβάζει ένα Shapefile και επιστρέφει μια συλλογή `Feature` που μπορείτε να διατρέξετε.

```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```

### Βήμα 2: Δημιουργία Εξόδου GeoJSON
`VectorLayer.Create` με τον οδηγό `Drivers.GeoJson` δημιουργεί ένα κενό αρχείο GeoJSON έτοιμο να λάβει χαρακτηριστικά.

```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```

### Βήμα 3: Αντιγραφή Χαρακτηριστικών μεταξύ Επιπέδων
`CopyAttributes` αντιγράφει το σχήμα των χαρακτηριστικών (ονόματα πεδίων και τύπους δεδομένων) από το πηγαίο Shapefile στο νέο επίπεδο GeoJSON με μία κλήση.

```csharp
outputLayer.CopyAttributes(inputLayer);
```

### Βήμα 4: Επεξεργασία Χαρακτηριστικών
Διατρέξτε κάθε χαρακτηριστικό στο Shapefile ώστε να μπορείτε να εφαρμόσετε προσαρμοσμένη λογική πριν το γράψετε.

```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```

### Βήμα 5: Φιλτράρισμα Χαρακτηριστικών κατά Ημερομηνία
Σε αυτό το παράδειγμα παραλείπουμε εγγραφές των οποίων το πεδίο `dob` (ημερομηνία γέννησης) λείπει ή είναι νωρίτερα από 1 Ιαν 1982. Προσαρμόστε το φίλτρο ώστε να ταιριάζει στις δικές σας απαιτήσεις.

```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```

### Βήμα 6: Δημιουργία Νέου Feature (C# Generate GeoJSON File)
Ένα `Feature` αντιπροσωπεύει ένα μοναδικό χωρικό στοιχείο που περιέχει γεωμετρία και δεδομένα χαρακτηριστικών.  
Εδώ δημιουργούμε ένα νέο `Feature` για το επίπεδο GeoJSON, αντιγράφουμε τη γεωμετρία και τις τιμές χαρακτηριστικών, και το προσθέτουμε στην έξοδο. Αυτό αποτελεί τον πυρήνα του *c# generate geojson file*.

```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```

Συγχαρητήρια! Έχετε επιτυχώς **μετατρέψει shapefile σε geojson** και έμαθατε πώς να **αντιγράψετε χαρακτηριστικά μεταξύ επιπέδων** κατά τη διάρκεια.

## Κοινά Προβλήματα και Λύσεις
| Πρόβλημα | Γιατί συμβαίνει | Διόρθωση |
|----------|------------------|----------|
| Το αρχείο εξόδου είναι κενό | Η μέθοδος `CopyAttributes` κλήθηκε μετά το κλείσιμο του επιπέδου εξόδου | Βεβαιωθείτε ότι το μπλοκ `using` για το `outputLayer` παραμένει ανοιχτό μέχρι να προστεθούν όλα τα χαρακτηριστικά. |
| Το φίλτρο ημερομηνίας αφαιρεί όλες τις εγγραφές | Λάθος όνομα πεδίου ή μη αναμενόμενη μορφή ημερομηνίας | Επαληθεύστε το όνομα του χαρακτηριστικού (`dob`) και χρησιμοποιήστε `GetValue<string>` αν οι ημερομηνίες αποθηκεύονται ως συμβολοσειρές. |
| Εξαίρεση άδειας | Εκτέλεση χωρίς έγκυρη άδεια Aspose.GIS σε παραγωγή | Εφαρμόστε προσωρινή ή πλήρη άδεια όπως περιγράφεται στην τεκμηρίωση της Aspose. |

## Συχνές Ερωτήσεις
**Q: Πού μπορώ να βρω περισσότερη τεκμηρίωση;**  
A: Επισκεφθείτε την [Aspose.GIS documentation](https://reference.aspose.com/gis/net/) για λεπτομερείς πληροφορίες.

**Q: Πώς μπορώ να αποκτήσω προσωρινή άδεια;**  
A: Μπορείτε να αποκτήσετε προσωρινή άδεια [εδώ](https://purchase.aspose.com/temporary-license/).

**Q: Πού μπορώ να ζητήσω υποστήριξη;**  
A: Συμμετέχετε στο [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) για υποστήριξη από την κοινότητα και συζητήσεις.

**Q: Υπάρχει διαθέσιμη δωρεάν δοκιμή;**  
A: Ναι, μπορείτε να βρείτε τη δωρεάν δοκιμή [εδώ](https://releases.aspose.com/).

**Q: Πού μπορώ να αγοράσω το Aspose.GIS για .NET;**  
A: Μπορείτε να αγοράσετε το προϊόν [εδώ](https://purchase.aspose.com/buy).

## Συμπέρασμα
Σε αυτό το tutorial εξετάσαμε τη πλήρη διαδικασία **μετατροπής shapefile σε geojson** χρησιμοποιώντας Aspose.GIS για .NET, δείξαμε πώς να **αντιγράψετε χαρακτηριστικά μεταξύ επιπέδων**, και παρουσιάσαμε έναν καθαρό τρόπο για *c# generate geojson file*. Πειραματιστείτε με διαφορετικά φίλτρα, μεγαλύτερα σύνολα δεδομένων ή πρόσθετες μετασχηματισμούς γεωμετρίας για να αξιοποιήσετε πλήρως τις δυνατότητες της βιβλιοθήκης.

---

**Τελευταία ενημέρωση:** 2026-07-05  
**Δοκιμάστηκε με:** Aspose.GIS for .NET (latest stable release)  
**Συγγραφέας:** Aspose

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Σχετικά Μαθήματα

- [Πώς να Μετατρέψετε GeoJSON σε File GDB Χρησιμοποιώντας Aspose.GIS για .NET](/gis/net/layer-management/convert-geojson-layer-to-file-gdb/)
- [Πώς να Διαβάσετε GeoJSON από Stream με Aspose.GIS για .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Πώς να Μετατρέψετε GeoJSON σε TopoJSON με Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}