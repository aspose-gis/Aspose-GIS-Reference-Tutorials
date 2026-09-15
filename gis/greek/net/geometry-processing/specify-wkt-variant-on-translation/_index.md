---
date: 2026-09-15
description: Μάθετε πώς να αναθέσετε σύστημα συντεταγμένων, να ορίσετε την παραλλαγή
  WKT και να ελέγξετε την ακρίβεια δεκαδικών όταν δημιουργείτε γεωμετρία σημείου σε
  C# με Aspose.GIS για .NET.
keywords:
- assign coordinate system
- assign spatial reference
- set decimal precision
- create point geometry
- set numeric format
lastmod: 2026-09-15
linktitle: Καθορισμός παραλλαγής WKT κατά τη μετάφραση
og_description: Μάθετε πώς να αναθέσετε σύστημα συντεταγμένων, να ορίσετε την παραλλαγή
  WKT και να ελέγξετε την ακρίβεια δεκαδικών όταν δημιουργείτε γεωμετρία σημείου σε
  C# με Aspose.GIS για .NET.
og_image_alt: Developer guide showing C# code to assign coordinate system and configure
  WKT output with Aspose.GIS
og_title: Ανάθεση συστήματος συντεταγμένων, ορισμός παραλλαγής WKT χρησιμοποιώντας
  Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-09-15'
  description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  headline: Assign coordinate system, set WKT variant using Aspose.GIS
  type: TechArticle
- description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  name: Assign coordinate system, set WKT variant using Aspose.GIS
  steps:
  - name: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
    text: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
  - name: A .NET development environment (Visual Studio, VS Code, or Rider).
    text: A .NET development environment (Visual Studio, VS Code, or Rider).
  - name: Basic familiarity with C# and the .NET framework.
    text: Basic familiarity with C# and the .NET framework.
  type: HowTo
- questions:
  - answer: It binds a geometry to a specific coordinate reference system such as
      WGS‑84.
    question: What does “assign coordinate system” mean?
  - answer: Iso, SimpleFeatureAccessOutdated, and ExtendedPostGis.
    question: Which WKT variants are supported?
  - answer: Use the `NumericFormat` enum (`General`, `RoundTrip`, `Flat`).
    question: How can I control decimal precision?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license for Aspose.GIS?
  - answer: .NET Framework 4.0+ and .NET Core/5/6+.
    question: What .NET versions are compatible?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- assign coordinate system
- Aspose.GIS
- C# geometry
- WKT variant
title: Ανάθεση συστήματος συντεταγμένων, ορισμός παραλλαγής WKT χρησιμοποιώντας Aspose.GIS
url: /el/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ανάθεση συστήματος συντεταγμένων, ορισμός παραλλαγής WKT χρησιμοποιώντας το Aspose.GIS

## Εισαγωγή
Σε αυτό το σεμινάριο θα μάθετε πώς να **αναθέσετε σύστημα συντεταγμένων**, να επιλέξετε τη σωστή παραλλαγή WKT και να ελέγξετε την ακρίβεια των δεκαδικών όταν **δημιουργείτε γεωμετρία σημείου** σε C# με το Aspose.GIS για .NET. Είτε δημιουργείτε μια υπηρεσία χαρτογράφησης, εκτελείτε χωρική ανάλυση ή ανταλλάσσετε δεδομένα μεταξύ πλατφορμών GIS, αυτές οι ρυθμίσεις εγγυώνται ότι το αποτέλεσμα είναι τόσο διαλειτουργικό όσο και εύκολο στην ανάγνωση. Ας προχωρήσουμε στη διαδικασία βήμα προς βήμα.

## Γρήγορες απαντήσεις
- **Τι σημαίνει “αναθέστε σύστημα συντεταγμένων”;** Συνδέει μια γεωμετρία με ένα συγκεκριμένο σύστημα αναφοράς συντεταγμένων όπως το WGS‑84.  
- **Ποιες παραλλαγές WKT υποστηρίζονται;** Iso, SimpleFeatureAccessOutdated, και ExtendedPostGis.  
- **Πώς μπορώ να ελέγξω την ακρίβεια των δεκαδικών;** Χρησιμοποιήστε το enum `NumericFormat` (`General`, `RoundTrip`, `Flat`).  
- **Χρειάζομαι άδεια για το Aspose.GIS;** Διατίθεται δωρεάν δοκιμαστική έκδοση· απαιτείται εμπορική άδεια για παραγωγική χρήση.  
- **Ποιες εκδόσεις .NET είναι συμβατές;** .NET Framework 4.0+ και .NET Core/5/6+.

## Τι είναι η “ανάθεση συστήματος συντεταγμένων”
Η ανάθεση μιας χωρικής αναφοράς (ή συστήματος χωρικής αναφοράς, SRS) λέει στο λογισμικό GIS πώς να ερμηνεύσει τις τιμές συντεταγμένων μιας γεωμετρίας, συνδέοντας τους αριθμούς με ένα πραγματικό σύστημα συντεταγμένων όπως το WGS‑84. Χωρίς SRS, οι αριθμοί γεωγραφικού πλάτους‑μήκους ενός σημείου δεν έχουν πραγματικό νόημα.

## Γιατί να ελέγχετε την παραλλαγή WKT και τη μορφή αριθμών;
Πάνω από 30 εργαλεία GIS αναμένουν συγκεκριμένες συντακτικές μορφές WKT, έτσι η επιλογή της κατάλληλης παραλλαγής αποτρέπει σφάλματα εισαγωγής. Ο ορισμός της μορφής αριθμών μειώνει το θόρυβο στρογγυλοποίησης και διατηρεί το αποτέλεσμα συνοπτικό, κάτι που είναι ιδιαίτερα σημαντικό όταν τα αρχεία καταγραφής ή τα αρχεία αναλύονται προγραμματιστικά.

## Προαπαιτούμενα
1. Aspose.GIS για .NET – κατεβάστε από τη [σελίδα λήψης](https://releases.aspose.com/gis/net/).  
2. Περιβάλλον ανάπτυξης .NET (Visual Studio, VS Code ή Rider).  
3. Βασική εξοικείωση με C# και το .NET framework.

## Εισαγωγή ονοματοχώρων
Πριν χρησιμοποιήσετε οποιεσδήποτε κλάσεις Aspose.GIS, εισάγετε τους απαιτούμενους ονοματοχώρους:

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

## Πώς να αναθέσετε σύστημα συντεταγμένων σε ένα σημείο;
Φορτώστε ένα αντικείμενο `Point`, στη συνέχεια συνδέστε ένα σύστημα χωρικής αναφοράς (SRS) χρησιμοποιώντας την κλάση `SpatialReference`. Αυτό το μοτίβο δύο βημάτων εξασφαλίζει ότι η γεωμετρία μεταφέρει τα μεταδεδομένα του συστήματος συντεταγμένων κατά την εξαγωγή, επιτρέποντας στα επόμενα εργαλεία να ερμηνεύσουν σωστά τις συντεταγμένες. Η κλάση `Point` αντιπροσωπεύει μια μοναδική θέση που ορίζεται από τις συντεταγμένες X (μήκος) και Y (πλάτος).

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Βήμα 2: ανάθεση συστήματος χωρικής αναφοράς (SRS)
Τώρα **αναθέτουμε χωρική αναφορά** στο σημείο. Η `SpatialReference` αντιπροσωπεύει ένα σύστημα αναφοράς συντεταγμένων που προσδιορίζεται από ένα SRID. Εδώ χρησιμοποιούμε το ευρέως υποστηριζόμενο σύστημα WGS‑84 (SRID 4326):

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Βήμα 3: καθορίστε την επιθυμητή παραλλαγή WKT
Επιλέξτε την παραλλαγή WKT που ταιριάζει στην εφαρμογή σας:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Πώς να ορίσετε την ακρίβεια δεκαδικών για την έξοδο WKT;
Ελέγξτε πόσα ψηφία εμφανίζονται στην τελική συμβολοσειρά χρησιμοποιώντας το enum `NumericFormat`, το οποίο ορίζει κανόνες μορφοποίησης όπως `General`, `RoundTrip` ή `Flat`. Η επιλογή του `RoundTrip` διατηρεί την πλήρη ακρίβεια των συντεταγμένων για σενάρια επαναφοράς, ενώ το `General` παρέχει μια συνοπτική αναπαράσταση κατάλληλη για τις περισσότερες εργασίες οπτικοποίησης. Το enum `NumericFormat` ελέγχει πώς μορφοποιούνται οι αριθμοί συντεταγμένων στην έξοδο WKT.

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### Κοινά προβλήματα & συμβουλές
- **Πρόβλημα:** Η παράλειψη του ορισμού του SRS πριν την κλήση του `AsText` μπορεί να οδηγήσει σε έλλειψη πληροφοριών SRID.  
- **Συμβουλή:** Χρησιμοποιήστε `NumericFormat.RoundTrip` όταν χρειάζεστε απώλεσ-μη-απώλεια επαναφορά των συντεταγμένων.  
- **Συμβουλή:** Η παραλλαγή `Iso` είναι η πιο φορητή· επιλέξτε `ExtendedPostGis` μόνο όταν χρειάζεται ενσωματωμένο SRID.

## Συμπέρασμα
Τώρα γνωρίζετε πώς να **αναθέσετε σύστημα συντεταγμένων**, να επιλέξετε την κατάλληλη παραλλαγή WKT και να **ορίσετε την ακρίβεια δεκαδικών** όταν **δημιουργείτε γεωμετρία σημείου** με το Aspose.GIS. Αυτοί οι έλεγχοι σας δίνουν την ευελιξία να καλύψετε τις ακριβείς απαιτήσεις οποιουδήποτε ροής εργασίας GIS, από απλή οπτικοποίηση έως ανάλυση υψηλής ακρίβειας.

## Συχνές ερωτήσεις

**Q:** Είναι το Aspose.GIS συμβατό με όλες τις εκδόσεις του .NET;  
**A:** Ναι, το Aspose.GIS υποστηρίζει .NET Framework 4.0 και νεότερες, καθώς και .NET Core/5/6.

**Q:** Μπορώ να χρησιμοποιήσω το Aspose.GIS για εμπορικά έργα;  
**A:** Απόλυτα. Απαιτείται εμπορική άδεια για παραγωγική χρήση, αλλά είναι διαθέσιμη δωρεάν δοκιμαστική έκδοση για αξιολόγηση.

**Q:** Υποστηρίζει το Aspose.GIS άλλες μορφές χωρικών δεδομένων;  
**A:** Ναι, λειτουργεί με πάνω από 30 μορφές, συμπεριλαμβανομένων των ESRI Shapefile, GeoJSON, KML, CSV και πολλών άλλων.

**Q:** Πού μπορώ να κατεβάσω μια δωρεάν δοκιμαστική έκδοση;  
**A:** Μπορείτε να κατεβάσετε μια δωρεάν δοκιμαστική έκδοση του Aspose.GIS από τη [σελίδα λήψης δωρεάν δοκιμής Aspose.GIS](https://releases.aspose.com/).

**Q:** Πώς μπορώ να λάβω βοήθεια αν αντιμετωπίσω προβλήματα;  
**A:** Δημοσιεύστε τις ερωτήσεις σας στο [φόρουμ](https://forum.aspose.com/c/gis/33) της κοινότητας Aspose.GIS, όπου τόσο το προσωπικό της Aspose όσο και τα μέλη της κοινότητας μπορούν να βοηθήσουν.

---

**Τελευταία ενημέρωση:** 2026-09-15  
**Δοκιμάστηκε με:** Aspose.GIS for .NET (latest release)  
**Συγγραφέας:** Aspose

## Σχετικά Σεμινάρια

- [Δημιουργία διανυσματικού στρώματος και ορισμός του συστήματος χωρικής αναφοράς](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Πώς να μετατρέψετε γεωμετρία σε WKT με το Aspose.GIS για .NET](/gis/net/geometry-processing/translate-geometry-to-wkt/)
- [Πώς να περιορίσετε την ακρίβεια κατά τη γραφή γεωμετριών με το Aspose.GIS](/gis/net/geometry-processing/limit-precision-writing-geometries/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}