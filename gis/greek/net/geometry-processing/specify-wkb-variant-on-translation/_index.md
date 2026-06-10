---
date: 2026-06-10
description: Μάθετε πώς να δημιουργήσετε γεωμετρία linestring στο .NET και να μετατρέψετε
  τη γεωμετρία σε WKB χρησιμοποιώντας το Aspose.GIS για .NET με την παραλλαγή ExtendedPostGis.
keywords:
- create linestring geometry .net
- WKB variant Aspose GIS
- EWKB conversion .NET
linktitle: Καθορίστε την παραλλαγή WKB κατά τη μετάφραση
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  headline: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  name: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  steps:
  - name: Creating a Geometry Object
    text: The `Geometry` class is Aspose.GIS's base type that represents any spatial
      object in memory. Linestring represents a series of connected points forming
      a linear geometry. In this step we instantiate a `Linestring` with a collection
      of coordinate pairs that model a simple road segment.
  - name: Generating WKB Representation
    text: '`WkbVariant.ExtendedPostGis` is the enum value that tells Aspose.GIS to
      include SRID in the output binary. Here we call the `AsBinary` method, passing
      the EWKB variant, which returns a `byte[]` containing the full binary representation.'
  - name: Writing to File
    text: '`File.WriteAllBytes` writes the binary array to disk. The resulting file
      (`EWkbFile.ewkb`) can be imported directly into a PostGIS table using the `ST_GeomFromEWKB`
      function.'
  type: HowTo
- questions:
  - answer: Yes, the `ExtendedPostGis` variant produces EWKB that includes SRID, which
      PostGIS reads directly via `ST_GeomFromEWKB`.
    question: Can I use the EWKB file with PostGIS?
  - answer: Absolutely. Use `Geometry.FromBinary(byteArray)` to reconstruct the geometry
      from its binary form.
    question: Is it possible to read a WKB file back into a geometry object?
  - answer: Yes, Aspose.GIS handles points, linestrings, polygons, multipolygons,
      and many more spatial types.
    question: Does the library support other geometry types like polygons?
  - answer: Set the `SRID` property on the geometry object before calling `AsBinary`,
      e.g., `linestring.SRID = 4326;`.
    question: How do I specify a different SRID when creating the geometry?
  - answer: Yes, the same API works across .NET Framework, .NET Core, and .NET 5/6
      without modification.
    question: Will this code work on .NET Core?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Δημιουργία γεωμετρίας Linestring & παραλλαγής WKB στο Aspose.GIS για .NET
url: /el/net/geometry-processing/specify-wkb-variant-on-translation/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία Γεωμετρίας Linestring & Παραλλαγής WKB στο Aspose.GIS για .NET

## Εισαγωγή
Αν χρειάζεστε **δημιουργία γεωμετρίας linestring .NET** και στη συνέχεια να μετατρέψετε αυτή τη γεωμετρία σε δυαδική μορφή, το Aspose.GIS για .NET σας προσφέρει ένα καθαρό, υψηλής απόδοσης API που λειτουργεί σε .NET Framework, .NET Core και .NET 5/6+. Σε αυτό το tutorial θα περάσουμε βήμα‑βήμα από την εισαγωγή χώρων ονομάτων μέχρι τη δημιουργία αρχείου EWKB—ώστε να διατηρήσετε τις πληροφορίες SRID και να ενσωματώσετε δεδομένα GIS σε PostgreSQL/PostGIS ή οποιαδήποτε ροή εργασίας βασισμένη σε δυαδικά δεδομένα χωρίς προβλήματα.

## Γρήγορες Απαντήσεις
- **What does WKB stand for?** Well‑Known Binary, a compact binary representation of geometric objects.  
- **Which WKB variant stores SRID?** The `ExtendedPostGis` (EWKB) variant embeds SRID directly in the binary.  
- **Do I need a license?** A temporary or full Aspose.GIS license is required for production deployments.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6+.  
- **How long does the implementation take?** Typically under 10 minutes for a basic example.

## Τι είναι η Γεωμετρία Linestring;
Μια γεωμετρία linestring είναι ένα απλό σχήμα που αποτελείται από μια διατεταγμένη λίστα σημείων συνδεδεμένων με ευθείες γραμμές. Είναι η προτιμώμενη αναπαράσταση για γραμμικά χαρακτηριστικά όπως δρόμοι, αγωγοί ή ποτάμια σε χωρικές βάσεις δεδομένων.

## Γιατί να Καθορίσετε μια Παραλλαγή WKB;
Η χρήση της σωστής παραλλαγής WKB εγγυάται ότι κρίσιμα μεταδεδομένα—ιδιαίτερα ο Αναγνωριστικός Σύστημα Χωρικής Αναφοράς (SRID)—συνοδεύουν τη γεωμετρία σας. Η παραλλαγή `ExtendedPostGis` (EWKB) αποθηκεύει το SRID μέσα στο δυαδικό φορτίο, επιτρέποντας αδιάλειπτη ανταλλαγή με PostGIS, Oracle Spatial ή οποιοδήποτε σύστημα που απαιτεί δυαδικά με SRID.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα εξής:

### Εγκατάσταση Aspose.GIS για .NET
1. Κατεβάστε το Aspose.GIS: Επισκεφθείτε το [download link](https://releases.aspose.com/gis/net/) για να αποκτήσετε το τελευταίο πακέτο.  
2. Προσθέστε το πακέτο NuGet στο έργο σας (π.χ., `Install-Package Aspose.GIS`).  

### Εξοικείωση με τον Προγραμματισμό C#
- Βασική κατανόηση της σύνταξης C# και της δομής του έργου.  
- Δυνατότητα εκτέλεσης μιας εφαρμογής .NET console ή class‑library.

## Εισαγωγή Χώρων Ονομάτων
Ο χώρος ονομάτων `Aspose.GIS` σας δίνει πρόσβαση σε όλες τις κλάσεις σχετικές με γεωμετρίες.  

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Αυτοί οι χώροι ονομάτων παρέχουν τη βασική λειτουργικότητα GIS, συμπεριλαμβανομένης της δημιουργίας γεωμετρίας, μετασχηματισμού και δυαδικής σειριοποίησης.

## Πώς να δημιουργήσετε γεωμετρία linestring;
Για να δημιουργήσετε ένα linestring, δημιουργήστε ένα αντικείμενο `Linestring` με μια διατεταγμένη λίστα ζευγών συντεταγμένων, ορίστε το SRID αν χρειάζεται, και στη συνέχεια σειριοποιήστε το στην επιθυμητή παραλλαγή WKB. Η διαδικασία περιλαμβάνει τρία βήματα: δημιουργία της γεωμετρίας, επιλογή της παραλλαγής `ExtendedPostGis` για διατήρηση του SRID, και εγγραφή του παραγόμενου πίνακα bytes σε αρχείο.

### Βήμα 1: Δημιουργία Αντικειμένου Γεωμετρίας
Η κλάση `Geometry` είναι ο βασικός τύπος του Aspose.GIS που αντιπροσωπεύει οποιοδήποτε χωρικό αντικείμενο στη μνήμη.  
Linestring αντιπροσωπεύει μια σειρά συνδεδεμένων σημείων που σχηματίζουν μια γραμμική γεωμετρία.  

```csharp
IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
```
Σε αυτό το βήμα δημιουργούμε ένα `Linestring` με μια συλλογή ζευγών συντεταγμένων που μοντελοποιούν ένα απλό τμήμα δρόμου.

### Βήμα 2: Δημιουργία Αναπαράστασης WKB
`WkbVariant.ExtendedPostGis` είναι η τιμή enum που λέει στο Aspose.GIS να συμπεριλάβει το SRID στο δυαδικό αποτέλεσμα.  

```csharp
byte[] wkb = geometry.AsBinary(WkbVariant.ExtendedPostGis);
```
Εδώ καλούμε τη μέθοδο `AsBinary`, περνώντας την παραλλαγή EWKB, η οποία επιστρέφει ένα `byte[]` που περιέχει την πλήρη δυαδική αναπαράσταση.

### Βήμα 3: Εγγραφή σε Αρχείο
`File.WriteAllBytes` γράφει τον δυαδικό πίνακα στο δίσκο.  

```csharp
File.WriteAllBytes(Path.Combine("Your Document Directory", "EWkbFile.ewkb"), wkb);
```
Το παραγόμενο αρχείο (`EWkbFile.ewkb`) μπορεί να εισαχθεί απευθείας σε πίνακα PostGIS χρησιμοποιώντας τη συνάρτηση `ST_GeomFromEWKB`.

## Συχνά Προβλήματα και Λύσεις
| Πρόβλημα | Αιτία | Λύση |
|----------|-------|------|
| **Κενό αρχείο** | `Path.Combine` δείχνει σε έναν μη‑υπάρχοντα φάκελο. | Βεβαιωθείτε ότι ο φάκελος προορισμού υπάρχει ή δημιουργήστε τον με `Directory.CreateDirectory`. |
| **Λανθασμένο SRID** | Η χρήση του προεπιλεγμένου `WkbVariant.Standard` αφαιρεί το SRID. | Πάντα χρησιμοποιείτε `WkbVariant.ExtendedPostGis` όταν απαιτείται διατήρηση του SRID. |
| **Εξαίρεση άδειας** | Εκτέλεση χωρίς έγκυρη άδεια σε παραγωγικό περιβάλλον. | Εφαρμόστε προσωρινή ή πλήρη άδεια πριν εκτελέσετε τον κώδικα σε παραγωγική χρήση. |

## Συχνές Ερωτήσεις
**Q: Μπορώ να χρησιμοποιήσω το αρχείο EWKB με το PostGIS;**  
A: Ναι, η παραλλαγή `ExtendedPostGis` παράγει EWKB που περιλαμβάνει SRID, το οποίο το PostGIS διαβάζει απευθείας μέσω της `ST_GeomFromEWKB`.  

**Q: Είναι δυνατόν να διαβάσω ένα αρχείο WKB ξανά σε αντικείμενο γεωμετρίας;**  
A: Απολύτως. Χρησιμοποιήστε `Geometry.FromBinary(byteArray)` για να ανακατασκευάσετε τη γεωμετρία από τη δυαδική της μορφή.  

**Q: Υποστηρίζει η βιβλιοθήκη άλλους τύπους γεωμετρίας όπως πολύγωνα;**  
A: Ναι, το Aspose.GIS διαχειρίζεται σημεία, linestrings, πολύγωνα, multipolygons και πολλούς άλλους χωρικούς τύπους.  

**Q: Πώς ορίζω διαφορετικό SRID κατά τη δημιουργία της γεωμετρίας;**  
A: Ορίστε την ιδιότητα `SRID` στο αντικείμενο γεωμετρίας πριν καλέσετε το `AsBinary`, π.χ., `linestring.SRID = 4326;`.  

**Q: Θα λειτουργήσει αυτός ο κώδικας σε .NET Core;**  
A: Ναι, το ίδιο API λειτουργεί σε .NET Framework, .NET Core και .NET 5/6 χωρίς τροποποίηση.

**Τελευταία ενημέρωση:** 2026-06-10  
**Δοκιμάστηκε με:** Aspose.GIS for .NET 23.9 (latest at time of writing)  
**Συγγραφέας:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικά Μαθήματα

- [Μετατροπή Γεωμετρίας σε Μορφή WKB με Aspose.GIS για .NET](/gis/net/geometry-processing/translate-geometry-to-wkb/)
- [Καθορισμός Παραλλαγής WKT κατά τη Μετάφραση χρησιμοποιώντας Aspose.GIS](/gis/net/geometry-processing/specify-wkt-variant-on-translation/)
- [Δημιουργία Γεωμετρίας MultiLineString χρησιμοποιώντας Aspose.GIS για .NET](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}