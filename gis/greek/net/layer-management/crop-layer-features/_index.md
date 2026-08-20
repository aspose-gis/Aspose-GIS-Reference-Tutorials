---
date: 2026-07-05
description: Μάθετε πώς να περικόψετε χαρακτηριστικά στρώματος με Aspose.GIS for .NET,
  συμπεριλαμβανομένου του πώς να περικόψετε raster με polygon, να εξάγετε το cell
  size του raster και να ανακτήσετε το extent του raster. Κατεβάστε τη δωρεάν δοκιμή
  σας τώρα.
keywords:
- how to crop layer
- extract raster extent
- get raster cell size
- crop raster layer
- crop raster with polygon
linktitle: Πώς να περικόψετε χαρακτηριστικά στρώματος
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to crop layer features with Aspose.GIS for .NET, including
    how to crop raster with polygon, extract raster cell size, and retrieve raster
    extent. Download your free trial now.
  headline: How to Crop Layer Features with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Is a temporary license available for Aspose.GIS for .NET?
  - answer: The documentation is available [here](https://reference.aspose.com/gis/net/).
    question: Where can I find comprehensive documentation for Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for support
      and community engagement.
    question: How can I seek support or connect with the community for Aspose.GIS
      for .NET?
  - answer: Yes, you can download a free trial [here](https://releases.aspose.com/).
    question: Can I download a free trial of Aspose.GIS for .NET?
  - answer: You can purchase the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Πώς να περικόψετε χαρακτηριστικά στρώματος με Aspose.GIS for .NET
url: /el/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Κόψετε Χαρακτηριστικά Στρώματος

## Εισαγωγή
Σε αυτό το σεμινάριο θα μάθετε **πώς να κόψετε στρώμα** χαρακτηριστικά χρησιμοποιώντας το Aspose.GIS for .NET, μια ισχυρή βιβλιοθήκη που σας επιτρέπει να **κόψετε raster με πολύγωνο**, **εξάγετε το μέγεθος κελιού raster**, και **ανακτήσετε το εύρος raster** για ακριβή γεωχωρική ανάλυση. Είτε προετοιμάζετε δεδομένα για έναν διαδικτυακό χάρτη, είτε περικόπτετε δορυφορικές εικόνες, είτε απομονώνετε μια περιοχή ενδιαφέροντος, αυτός ο οδηγός βήμα‑βήμα σας δείχνει ακριβώς πώς να ολοκληρώσετε τη δουλειά γρήγορα και αξιόπιστα.

## Γρήγορες Απαντήσεις
- **Τι σημαίνει “crop layer”;** Κόβει ένα raster ή vector στρώμα στα όρια μιας παρεχόμενης γεωμετρίας, απορρίπτοντας ό,τι βρίσκεται εκτός.  
- **Ποια γεωμετρία χρησιμοποιείται σε αυτό το παράδειγμα;** Ένα πολύγωνο ορισμένο σε μορφή WKT (Well‑Known Text).  
- **Μπορώ να εξάγω το μέγεθος κελιού μετά το κόψιμο;** Ναι – η ιδιότητα `CellSize` επιστρέφει το πλάτος και το ύψος ενός κελιού raster.  
- **Χρειάζομαι άδεια για να εκτελέσω τον κώδικα;** Μια προσωρινή άδεια λειτουργεί για αξιολόγηση· απαιτείται πλήρης άδεια για παραγωγική χρήση.  
- **Ποιες εκδόσεις .NET υποστηρίζονται;** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Τι είναι το “πώς να κόψετε στρώμα”;
**Το κόψιμο ενός στρώματος σημαίνει περιορισμό του συνόλου δεδομένων σε μια συγκεκριμένη γεωγραφική περιοχή, απορρίπτοντας ό,τι βρίσκεται εκτός.** Αυτή η λειτουργία μειώνει το μέγεθος του αρχείου, επιταχύνει την επακόλουθη επεξεργασία και εστιάζει την ανάλυση στην περιοχή που σας ενδιαφέρει. Περιορίζοντας τα δεδομένα στην περιοχή ενδιαφέροντος, απλοποιείτε επίσης τις επόμενες ροές εργασίας όπως το styling, η ανάλυση και η δημοσίευση, διατηρώντας το αρχικό σύστημα αναφοράς συντεταγμένων και τα μεταδεδομένα.

## Γιατί να χρησιμοποιήσετε το Aspose.GIS για κόψιμο;
**Το Aspose.GIS επεξεργάζεται αρχεία raster έως 2 GB χωρίς να φορτώνει ολόκληρη την εικόνα στη μνήμη και υποστηρίζει περισσότερα από 30 μορφές raster, συμπεριλαμβανομένων των GeoTIFF, JPEG2000 και PNG.** Η βιβλιοθήκη προσφέρει μια κλήση `Crop` σε μία γραμμή, αυτόματη διαχείριση CRS και πολυνηματική απόδοση που μπορεί να περικόψει ένα GeoTIFF 500 MB σε λιγότερο από ένα δευτερόλεπτο σε έναν τυπικό διακομιστή.

## Προαπαιτούμενα
Πριν εμβαθύνετε στη μαγεία της γεωχωρικής επεξεργασίας, βεβαιωθείτε ότι έχετε τα παρακάτω προαπαιτούμενα:

- Aspose.GIS for .NET Library: Βεβαιωθείτε ότι έχετε εγκαταστήσει τη βιβλιοθήκη Aspose.GIS στο .NET έργο σας. Μπορείτε να την κατεβάσετε από [here](https://releases.aspose.com/gis/net/).  
- Document Directory: Δημιουργήστε έναν φάκελο για την αποθήκευση των εγγράφων σας. Αντικαταστήστε το `"Your Document Directory"` στον παρεχόμενο κώδικα με την πραγματική διαδρομή του φακέλου εγγράφων σας.

Τώρα, ας βουτήξουμε στον οδηγό βήμα‑βήμα.

## Εισαγωγή Namespaces
Το namespace `Aspose.Gis` περιέχει όλους τους βασικούς τύπους για τη διαχείριση raster και vector. Εισάγετέ το για να αποκτήσετε πρόσβαση στις κλάσεις `Layer`, `Geometry` και σχετικές.

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Πώς να κόψω ένα στρώμα με πολύγωνο;
`Crop` είναι μια μέθοδος της κλάσης `Layer` που εξάγει ένα υποσύνολο raster ορισμένο από μια γεωμετρία.  
Φορτώστε το πηγαίο raster, ορίστε μια γεωμετρία πολυγώνου και καλέστε τη μέθοδο `Crop` – όλη η λειτουργία εκτελείται σε μία γραμμή κώδικα. Η μέθοδος επιστρέφει ένα νέο raster που περιέχει μόνο τα pixel μέσα στο πολύγωνο, διατηρώντας αυτόματα την αρχική χωρική αναφορά.

## Βήμα 1: Άνοιγμα και Κόψιμο του Στρώματος (crop raster with polygon)
`Layer` αντιπροσωπεύει ένα raster σύνολο δεδομένων που μπορεί να ανοιχθεί, να ερωτηθεί και να επεξεργαστεί.  
Η κλάση `Layer` αντιπροσωπεύει ένα raster σύνολο δεδομένων που μπορεί να ανοιχθεί, να ερωτηθεί και να επεξεργαστεί. Το άνοιγμα ενός GeoTIFF και το κόψιμό του με ένα πολύγωνο απομονώνει την περιοχή ενδιαφέροντος σε λίγες μόνο δηλώσεις.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## Βήμα 2: Ανάκτηση Πληροφοριών Raster (extract raster cell size & retrieve raster extent)
`CellSize` παρέχει το πλάτος και το ύψος κάθε κελιού raster σε μονάδες συντεταγμένων.  
`Extent` επιστρέφει το γεωγραφικό πλαίσιο περιορισμού του raster.  
Η ιδιότητα `CellSize` παρέχει το πλάτος και το ύψος κάθε κελιού raster σε μονάδες συντεταγμένων, ενώ η ιδιότητα `Extent` επιστρέφει το γεωγραφικό πλαίσιο περιορισμού του περικομμένου raster. Και τα δύο στοιχεία είναι απαραίτητα για επόμενους υπολογισμούς όπως η μέτρηση εμβαδού ή η επαναπροβολή.

```csharp
// read and print raster
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
```

## Βήμα 3: Εμφάνιση Πληροφοριών
Εκτυπώστε τις εξαγόμενες πληροφορίες για να κατανοήσετε την επίδραση της διαδικασίας κοπής στα γεωχωρικά σας δεδομένα.

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"source extent: {layer.GetExtent()}");
Console.WriteLine($"target extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
```

Επαναλάβετε αυτά τα βήματα όπως χρειάζεται για να βελτιώσετε και να προσαρμόσετε τα γεωχωρικά σας δεδομένα ώστε να καλύψουν συγκεκριμένες απαιτήσεις του έργου.

## Συχνά Προβλήματα και Λύσεις
| Πρόβλημα | Λύση |
|----------|------|
| **Λανθασμένος προσανατολισμός πολυγώνου** | Βεβαιωθείτε ότι το πολύγωνο WKT ακολουθεί τον κανόνα του δεξιού χεριού (αντίστροφη φορά για τα εξωτερικά δαχτυλίδια). |
| **Απουσία χωρικής αναφοράς** | Επαληθεύστε ότι το πηγαίο GeoTiff περιέχει CRS· διαφορετικά, ορίστε το χειροκίνητα πριν το κόψιμο. |
| **Μείωση απόδοσης σε τεράστια rasters** | Χρησιμοποιήστε `layer.Crop` σε ένα υποδειγματοληπτικό αντίγραφο ή επεξεργαστείτε το raster σε πλακίδια. |

## Συχνές Ερωτήσεις
**Ε: Είναι διαθέσιμη προσωρινή άδεια για το Aspose.GIS for .NET;**  
Α: Ναι, μπορείτε να αποκτήσετε μια προσωρινή άδεια [here](https://purchase.aspose.com/temporary-license/).

**Ε: Πού μπορώ να βρω ολοκληρωμένη τεκμηρίωση για το Aspose.GIS for .NET;**  
Α: Η τεκμηρίωση είναι διαθέσιμη [here](https://reference.aspose.com/gis/net/).

**Ε: Πώς μπορώ να ζητήσω υποστήριξη ή να συνδεθώ με την κοινότητα για το Aspose.GIS for .NET;**  
Α: Επισκεφθείτε το [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) για υποστήριξη και συμμετοχή στην κοινότητα.

**Ε: Μπορώ να κατεβάσω δωρεάν δοκιμαστική έκδοση του Aspose.GIS for .NET;**  
Α: Ναι, μπορείτε να κατεβάσετε μια δωρεάν δοκιμαστική έκδοση [here](https://releases.aspose.com/).

**Ε: Πού μπορώ να αγοράσω το Aspose.GIS for .NET;**  
Α: Μπορείτε να αγοράσετε τη βιβλιοθήκη [here](https://purchase.aspose.com/buy).

**Ε: Μπορώ να κόψω πολλαπλά στρώματα σε μία εκτέλεση;**  
Α: Ναι—επαναλάβετε τη διαδικασία για κάθε στρώμα και εφαρμόστε την ίδια κλήση `Crop` με τη ζητούμενη γεωμετρία.

**Ε: Υποστηρίζει το API άλλες μορφές raster (π.χ., JPEG2000);**  
Α: Το Aspose.GIS υποστηρίζει όλες τις μορφές που εκτίθενται από τους υποκείμενους οδηγούς GDAL, συμπεριλαμβανομένων των JPEG2000, PNG και άλλων.

## Συμπέρασμα
Ακολουθώντας αυτόν τον οδηγό, τώρα γνωρίζετε **πώς να κόψετε στρώμα** χαρακτηριστικά αποδοτικά με το Aspose.GIS for .NET. Μπορείτε εύκολα να **κόψετε raster με πολύγωνο**, **εξάγετε το μέγεθος κελιού raster**, και **ανακτήσετε το εύρος raster** ώστε να ταιριάζει σε οποιεσδήποτε ανάγκες του έργου. Εξερευνήστε περαιτέρω APIs για επαναπροβολή, στυλ raster και ανάλυση vector για να αξιοποιήσετε πλήρως το δυναμικό των γεωχωρικών ροών εργασίας σας.

---

**Last Updated:** 2026-07-05  
**Tested With:** Aspose.GIS 24.10 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικά Μαθήματα

- [Πώς να Δημιουργήσετε Γεωμετρία Πολυγώνου με Aspose.GIS for .NET](/gis/net/geometry-creation/create-polygon-geometry/)
- [Ανάκτηση Χαρακτηριστικών Στρώματος – Λήψη Πληροφοριών Χαρακτηριστικών Στρώματος με Aspose.GIS for .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Δημιουργία Γεωμετρίας Πολυγώνου C# και Έλεγχος Τομής με Aspose.GIS for .NET](/gis/net/geometry-analysis/check-geometries-intersection/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}