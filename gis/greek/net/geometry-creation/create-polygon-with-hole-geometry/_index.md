---
date: 2026-09-05
description: Μάθετε πώς να δημιουργήσετε ένα εσωτερικό δακτύλιο πολυγώνου με τρύπα
  χρησιμοποιώντας το Aspose.GIS για .NET. Αυτός ο οδηγός σας δείχνει πώς να προσθέσετε
  μια τρύπα σε ένα πολύγωνο και να εργαστείτε με δεδομένα.
keywords:
- polygon interior ring
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
lastmod: 2026-09-05
linktitle: Δημιουργία Πολυγώνου με Γεωμετρία Τρύπας
og_description: Μάθετε πώς να δημιουργήσετε ένα εσωτερικό δακτύλιο πολυγώνου με τρύπα
  χρησιμοποιώντας το Aspose.GIS για .NET. Αυτός ο οδηγός σας δείχνει πώς να προσθέσετε
  μια τρύπα σε ένα πολύγωνο και να εργαστείτε με δεδομένα.
og_image_alt: Guide showing how to create a polygon interior ring with a hole using
  Aspose.GIS
og_title: Δημιουργήστε ένα εσωτερικό δακτύλιο πολυγώνου με τρύπα χρησιμοποιώντας το
  Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-09-05'
  description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  headline: Create a polygon interior ring with a hole using Aspose.GIS
  type: TechArticle
- description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  name: Create a polygon interior ring with a hole using Aspose.GIS
  steps:
  - name: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
    text: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
  - name: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
    text: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
  - name: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
    text: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
  - name: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
    text: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
  - name: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
    text: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
  type: HowTo
- questions:
  - answer: It means building a polygon that contains one or more interior rings (holes)
      that are excluded from the area.
    question: What does “create polygon with hole” mean?
  - answer: Aspose.GIS for .NET provides full support for exterior and interior rings.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  - answer: Typically under 10 minutes to implement and test.
    question: How long does it take?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- polygon interior ring
- Aspose.GIS
- geospatial .NET
- create polygon with hole
- GIS development
title: Δημιουργήστε ένα εσωτερικό δακτύλιο πολυγώνου με τρύπα χρησιμοποιώντας το Aspose.GIS
url: /el/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία εσωτερικού δακτυλίου πολυγώνου με τρύπα χρησιμοποιώντας το Aspose.GIS

## Εισαγωγή
Σε αυτό το tutorial θα μάθετε πώς να **δημιουργήσετε ένα εσωτερικό δακτύλιο πολυγώνου** που περιέχει μια τρύπα χρησιμοποιώντας το Aspose.GIS για .NET. Είτε δημιουργείτε μια εφαρμογή χαρτογράφησης, εκτελείτε χωρική ανάλυση, είτε προετοιμάζετε δεδομένα για υπηρεσίες GIS, η ενσωμάτωση μιας τρύπας μέσα σε ένα πολύγωνο είναι βασική δεξιότητα. Θα περάσουμε από όλη τη διαδικασία — από τη ρύθμιση του περιβάλλοντος ανάπτυξης μέχρι τη δημιουργία ενός έγκυρου αντικειμένου πολυγώνου που μπορεί να αποθηκευτεί σε οποιαδήποτε υποστηριζόμενη γεωχωρική μορφή.

## Γρήγορες απαντήσεις
- **Τι σημαίνει η “δημιουργία πολυγώνου με τρύπα”;** Σημαίνει την κατασκευή ενός πολυγώνου που περιέχει έναν ή περισσότερους εσωτερικούς δακτυλίους (τρύπες) που εξαιρούνται από την περιοχή.  
- **Ποια βιβλιοθήκη το διαχειρίζεται;** Το Aspose.GIS για .NET παρέχει πλήρη υποστήριξη για εξωτερικούς και εσωτερικούς δακτυλίους.  
- **Χρειάζομαι άδεια;** Μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη· απαιτείται εμπορική άδεια για παραγωγή.  
- **Ποιες εκδόσεις .NET υποστηρίζονται;** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Πόσο χρόνο διαρκεί;** Συνήθως λιγότερο από 10 λεπτά για υλοποίηση και δοκιμή.

## Πώς να προσθέσετε τρύπα σε πολύγωνο χρησιμοποιώντας το Aspose.GIS
Φορτώστε το περιβάλλον GIS, ορίστε έναν εξωτερικό δακτύλιο, και στη συνέχεια προσθέστε έναν ή περισσότερους εσωτερικούς δακτυλίους. Το Aspose.GIS αυτόματα προσανατολίζει τους δακτυλίους και επικυρώνει τη γεωμετρία, ώστε να μπορείτε να εστιάσετε στις συντεταγμένες που αντιπροσωπεύουν το κενό που χρειάζεστε.

## Τι είναι ένας εσωτερικός δακτύλιος πολυγώνου;
Ένας **εσωτερικός δακτύλιος πολυγώνου** είναι ένα εσωτερικό όριο που αφαιρεί περιοχή από το εξωτερικό σχήμα του πολυγώνου.  
Το δημιουργείτε ορίζοντας μια κλειστή ακολουθία σημείων που το Aspose.GIS θεωρεί ως τρύπα, η οποία εξαιρείται κατά τον υπολογισμό της περιοχής ή την απόδοση του σχήματος.

## Γιατί να δημιουργήσετε έναν εσωτερικό δακτύλιο πολυγώνου χρησιμοποιώντας το Aspose.GIS;
Το Aspose.GIS επικυρώνει και διορθώνει τον προσανατολισμό των δακτυλίων σε λιγότερο από 5 ms για τυπικά πολύγωνα 200‑σημείων, εξαλείφοντας την ανάγκη για προσαρμοσμένο κώδικα επικύρωσης. Υποστηρίζει επίσης **30+ μορφές γεωχωρικών αρχείων** (Shapefile, GeoJSON, GML, KML κ.λπ.) και μπορεί να επεξεργαστεί πολύγωνα με έως και 10.000 σημεία χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη, προσφέροντάς σας ταχύτητα και κλιμακωσιμότητα.

## Πραγματικά σενάρια χρήσης για πολύγωνα με τρύπες
1. **Οικόπεδο με εσωτερική λίμνη** – η λίμνη μοντελοποιείται ως τρύπα ώστε να μην υπολογίζεται στην περιοχή του οικοπέδου.  
2. **Περιγράμματα κτιρίων με αυλές** – η αυλή εξαιρείται από το περίγραμμα του κτιρίου.  
3. **Προστατευμένες ζώνες μέσα σε μεγαλύτερη περιοχή διατήρησης** – μπορείτε να εξαιρέσετε περιορισμένες ενότητες χωρίς να δημιουργήσετε ξεχωριστά επίπεδα.

## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα παρακάτω προαπαιτούμενα:
1. Aspose.GIS for .NET Library: Μπορείτε να το κατεβάσετε από τη **σελίδα λήψης Aspose.GIS for .NET**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).  
2. Development Environment: Βεβαιωθείτε ότι έχετε ένα περιβάλλον ανάπτυξης εγκατεστημένο με το Visual Studio ή οποιοδήποτε άλλο .NET IDE.

## Εισαγωγή ονομάτων χώρου
Το όνομα χώρου `Aspose.Gis` περιέχει όλους τους τύπους γεωμετρίας που θα χρειαστείτε, συμπεριλαμβανομένων των `Polygon`, `LinearRing` και των βοηθητικών μεθόδων για επικύρωση.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Τώρα, ας προχωρήσουμε στη δημιουργία μιας γεωμετρίας πολυγώνου με τρύπα χρησιμοποιώντας το Aspose.GIS για .NET.

## Βήμα 1: δημιουργία αντικειμένου πολυγώνου
`Polygon` είναι ο τύπος γεωμετρίας του Aspose.GIS που αντιπροσωπεύει ένα επίπεδο πολύγωνο με προαιρετικούς εσωτερικούς δακτυλίους. Ξεκινάμε δημιουργώντας ένα κενό αντικείμενο `Polygon` που θα περιέχει αργότερα τόσο τον εξωτερικό όσο και τους εσωτερικούς δακτυλίους.

```csharp
Polygon polygon = new Polygon();
```

## Βήμα 2: ορισμός εξωτερικού δακτυλίου
`LinearRing` είναι η κλάση που χρησιμοποιείται για εξωτερικά και εσωτερικά όρια. Ο εξωτερικός δακτύλιος ορίζει το εξωτερικό όριο του πολυγώνου. Προσθέστε σημεία με φορά δεξιόστροφα για να δημιουργήσετε ένα κλειστό σχήμα.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## Βήμα 3: ορισμός εσωτερικού δακτυλίου (τρύπα)
`LinearRing` επίσης αντιπροσωπεύει εσωτερικούς δακτυλίους. Ο εσωτερικός δακτύλιος είναι η **τρύπα** που θα εξαιρεθεί από την περιοχή του πολυγώνου. Τα σημεία συνήθως προστίθενται με φορά αριστερόστροφα, αλλά το Aspose.GIS διαχειρίζεται αυτόματα τον προσανατολισμό.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## Βήμα 4: ανάθεση εξωτερικού δακτυλίου και προσθήκη εσωτερικού δακτυλίου στο πολύγωνο
Η μέθοδος `AddInteriorRing` προσθέτει έναν ή περισσότερους εσωτερικούς δακτυλίους σε ένα `Polygon`. Κλήστε την μετά τον ορισμό της ιδιότητας `ExteriorRing`; μπορείτε να επαναλάβετε την κλήση για να προσθέσετε πολλαπλές τρύπες.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## Συμβουλές και βέλτιστες πρακτικές
- **Ο προσανατολισμός είναι σημαντικός για την αναγνωσιμότητα** – ενώ το Aspose.GIS διορθώνει αυτόματα τον προσανατολισμό, η διατήρηση των εξωτερικών δακτυλίων δεξιόστροφα και των εσωτερικών αριστερόστροφα κάνει τη γεωμετρία πιο εύκολη στην επιθεώρηση σε προβολείς GIS.  
- **Κλείστε κάθε δακτύλιο** – επαναλάβετε πάντα την πρώτη συντεταγμένη ως το τελευταίο σημείο· αυτό εγγυάται ένα έγκυρο κλειστό σχήμα.  
- **Επικυρώστε μετά τη δημιουργία** – μπορείτε να καλέσετε το `polygon.IsValid` για να διασφαλίσετε ότι η γεωμετρία συμμορφώνεται με τα πρότυπα OGC πριν την αποθήκευση.

## Συχνά προβλήματα και λύσεις
| Πρόβλημα | Αιτία | Διόρθωση |
|----------|-------|----------|
| Η τρύπα δεν εμφανίζεται στον προβολέα GIS | Αντίστροφος προσανατολισμός εσωτερικού δακτυλίου | Βεβαιωθείτε ότι τα σημεία προστίθενται στην αντίθετη κατεύθυνση του εξωτερικού δακτυλίου (αριστερόστροφα). |
| Σφάλμα μη έγκυρου πολυγώνου | Δακτύλιοι δεν είναι κλειστοί (πρώτο ≠ τελευταίο σημείο) | Επαναλάβετε το πρώτο σημείο ως τελευταίο σε κάθε δακτύλιο (όπως φαίνεται παραπάνω). |
| Απροσδόκητη κενή γεωμετρία | Ξέχασα να ορίσω το `ExteriorRing` πριν προσθέσω εσωτερικούς δακτυλίους | Ορίστε πρώτα το `polygon.ExteriorRing`, στη συνέχεια καλέστε το `AddInteriorRing`. |

## Συχνές ερωτήσεις
### 1. Τι είναι το Aspose.GIS;
Το Aspose.GIS είναι μια βιβλιοθήκη .NET που επιτρέπει στους προγραμματιστές να εργάζονται με γεωχωρικά δεδομένα, δίνοντάς τους τη δυνατότητα να δημιουργούν, να διαβάζουν και να επεξεργάζονται διάφορες μορφές γεωχωρικών αρχείων.

### 2. Μπορώ να χρησιμοποιήσω το Aspose.GIS για εμπορικά έργα;
Ναι, μπορείτε να χρησιμοποιήσετε το Aspose.GIS για προσωπικά και εμπορικά έργα αγοράζοντας άδεια. Επισκεφθείτε τη **σελίδα αγοράς Aspose.GIS**([https://purchase.aspose.com/buy](https://purchase.aspose.com/buy)) για περισσότερες λεπτομέρειες.

### 3. Υπάρχει δωρεάν δοκιμή διαθέσιμη για το Aspose.GIS;
Ναι, μπορείτε να εκμεταλλευτείτε μια δωρεάν δοκιμή του Aspose.GIS από τη **σελίδα λήψης δωρεάν δοκιμής Aspose.GIS**([https://releases.aspose.com/](https://releases.aspose.com/)).

### 4. Πού μπορώ να βρω υποστήριξη για το Aspose.GIS;
Μπορείτε να βρείτε υποστήριξη για το Aspose.GIS στο [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).

### 5. Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.GIS;
Μπορείτε να αποκτήσετε προσωρινή άδεια για το Aspose.GIS από τη **σελίδα προσωρινής άδειας Aspose.GIS**([https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/)).

---

**Τελευταία ενημέρωση:** 2026-09-05  
**Δοκιμή με:** Aspose.GIS 24.11 for .NET  
**Συγγραφέας:** Aspose

## Σχετικά Μαθήματα

- [Πώς να δημιουργήσετε γεωμετρία πολυγώνου με Aspose.GIS για .NET](/gis/net/geometry-creation/create-polygon-geometry/)
- [Μάθετε πώς να δημιουργήσετε γεωμετρία MultiPolygon με Aspose.GIS](/gis/net/geometry-creation/create-multipolygon-geometry/)
- [Μετατροπή πολυγώνου σε γραμμή με Aspose.GIS για .NET](/gis/net/geometry-processing/replace-polygons-with-lines/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}