---
date: 2026-09-15
description: Μάθετε πώς να μετατρέψετε πολυγώνιο σε γραμμή και να μετασχηματίσετε
  πολυγώνια σε γραμμές χρησιμοποιώντας Aspose.GIS for .NET. Ένας γρήγορος οδηγός για
  προγραμματιστές GIS.
keywords:
- convert polygon to line
- how to replace polygons
- transform polygons to lines
- gis polygon to line
- simplify map visualization
lastmod: 2026-09-15
linktitle: Αντικατάσταση πολυγώνων με γραμμές
og_description: Μετατρέψτε πολυγώνιο σε γραμμή χρησιμοποιώντας Aspose.GIS for .NET.
  Αυτό το εκπαιδευτικό υλικό δείχνει πώς να αντικαταστήσετε πολυγώνια με γραμμές,
  τις υποστηριζόμενες εκδόσεις .NET και κοινά προβλήματα.
og_image_alt: Screenshot of Aspose.GIS converting polygon to line in a .NET console
  app
og_title: Μετατροπή πολυγώνου σε γραμμή με Aspose.GIS for .NET – γρήγορος οδηγός
schemas:
- author: Aspose
  dateModified: '2026-09-15'
  description: Learn how to convert polygon to line and transform polygons to lines
    using Aspose.GIS for .NET. A quick guide for GIS developers.
  headline: Convert polygon to line with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert polygon to line and transform polygons to lines
    using Aspose.GIS for .NET. A quick guide for GIS developers.
  name: Convert polygon to line with Aspose.GIS for .NET
  steps:
  - name: Define the source geometry
    text: The `GeometryCollection` class is a container that can hold any number of
      geometry objects, including polygons, points, and lines. It is the entry point
      for bulk operations like `ReplacePolygonsByLines`. Create a geometry collection
      that includes one or more polygons you want to convert. In this exa
  - name: Convert polygons to lines
    text: The `ReplacePolygonsByLines()` method scans the supplied collection, replaces
      each polygon with a `LineString` that follows its outer ring, and leaves all
      other geometry types untouched. This single call performs the conversion in
      O(n) time, where *n* is the number of geometries in the collection.
  - name: Display the original and converted geometries
    text: Printing both the original and the transformed geometries lets you verify
      that polygons have been replaced while other geometries stay the same. The `ToString()`
      override on each geometry provides a human‑readable WKT representation.
  type: HowTo
- questions:
  - answer: Yes, it supports more than 30 formats—including Shapefile, GeoJSON, KML,
      GML, and CSV—allowing you to read, convert, and write data without external
      tools.
    question: Can Aspose.GIS for .NET work with various GIS file formats?
  - answer: Yes, you can access the free trial of Aspose.GIS for .NET on the Aspose
      releases page ([Aspose releases page](https://releases.aspose.com/)).
    question: Is there a free trial available for Aspose.GIS for .NET?
  - answer: Yes, developers can get support and assistance from the Aspose.GIS community
      forum ([Aspose.GIS community forum](https://forum.aspose.com/c/gis/33)).
    question: Does Aspose.GIS for .NET offer support for developers?
  - answer: Yes, you can acquire a temporary license from Aspose's temporary license
      page ([temporary license page](https://purchase.aspose.com/temporary-license/)).
    question: Can I purchase a temporary license for Aspose.GIS for .NET?
  - answer: Absolutely, it provides comprehensive documentation, code examples, and
      API references for all skill levels.
    question: Is Aspose.GIS for .NET suitable for both beginners and experienced developers?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert polygon to line
- Aspose.GIS
- .NET GIS processing
title: Μετατροπή πολυγώνου σε γραμμή με Aspose.GIS for .NET
url: /el/net/geometry-processing/replace-polygons-with-lines/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Μετατροπή πολυγώνου σε γραμμή με το Aspose.GIS για .NET

## Εισαγωγή
Αν χρειάζεστε **convert polygon to line** σε ένα .NET GIS έργο, το Aspose.GIS κάνει τη διαδικασία απλή. Είτε απλοποιείτε οπτικοποιήσεις χαρτών, προετοιμάζετε δεδομένα για αλγορίθμους δρομολόγησης, είτε απλώς χρειάζεστε μια πιο καθαρή αναπαράσταση γεωμετρίας, αυτό το tutorial σας οδηγεί βήμα‑βήμα στην αντικατάσταση πολυγώνων με γραμμικές γεωμετρίες χρησιμοποιώντας το Aspose.GIS API. Θα δείτε γιατί η βιβλιοθήκη είναι προτιμώμενη επιλογή για GIS προγραμματιστές και πώς να ολοκληρώσετε τη μετατροπή σε λίγες μόνο γραμμές κώδικα.

## Γρήγορες απαντήσεις
- **Τι σημαίνει «convert polygon to line»;** Εξάγει το εξωτερικό δακτύλιο ενός πολυγώνου και δημιουργεί ένα `LineString` που ακολουθεί το ίδιο περίγραμμα.  
- **Γιατί να χρησιμοποιήσετε το Aspose.GIS για αυτήν την εργασία;** Η βιβλιοθήκη προσφέρει μία μέθοδο (`ReplacePolygonsByLines`) που διαχειρίζεται μαζική μετατροπή αποδοτικά, χωρίς χειροκίνητη ανάλυση γεωμετρίας.  
- **Ποιες εκδόσεις .NET υποστηρίζονται;** .NET Framework 4.5+, .NET Core 3.1+, και .NET 5/6+ υποστηρίζονται πλήρως.  
- **Χρειάζομαι άδεια για ανάπτυξη;** Μια δωρεάν δοκιμή λειτουργεί για δοκιμές· απαιτείται εμπορική άδεια για παραγωγικές εγκαταστάσεις.  
- **Πόσο χρόνο διαρκεί η υλοποίηση;** Οι περισσότεροι προγραμματιστές ολοκληρώνουν μια βασική μετατροπή σε λιγότερο από δέκα λεπτά.

## Τι είναι «convert polygon to line»;
Η μετατροπή ενός πολυγώνου σε γραμμή σημαίνει την εξαγωγή του εξωτερικού δακτυλίου (περιγράμματος) του πολυγώνου και την αναπαράστασή του ως `LineString`. Η προκύπτουσα γεωμετρία διατηρεί το ακριβές σχήμα του αρχικού αντικειμένου, αλλά αγνοεί τις πληροφορίες εσωτερικής περιοχής, κάτι που είναι ιδανικό για ανάλυση δικτύων, απόδοση ακμών ή όταν χρειάζεστε ελαφριά αναπαράσταση για διαδικτυακούς χάρτες.

## Γιατί να μετατρέψετε πολυγώνια σε γραμμές με το Aspose.GIS;
Το Aspose.GIS αντικαθιστά κάθε πολύγωνο σε μια συλλογή με τη γραμμή του περιγράμματος σε μία κλήση, διατηρώντας την τοπολογία και εξαλείφοντας την ανάγκη για προσαρμοσμένους βρόχους. Αυτή η προσέγγιση μειώνει την πολυπλοκότητα του κώδικα έως και 80 % και επεξεργάζεται συλλογές 10 000+ χαρακτηριστικών σε λιγότερο από ένα δευτερόλεπτο σε τυπικό εξοπλισμό διακομιστή, χάρη στον εγγενή πυρήνα C++ και τη διαχείριση μνήμης χωρίς αντιγραφή.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα παρακάτω:

### Εγκατάσταση Aspose.GIS για .NET
1. Κατεβάστε το Aspose.GIS για .NET: Επισκεφθείτε τη σελίδα λήψης Aspose.GIS για .NET ([Aspose.GIS for .NET download](https://releases.aspose.com/gis/net/)).  
2. Εγκαταστήστε το Aspose.GIS για .NET: Ακολουθήστε τις οδηγίες εγκατάστασης στο πακέτο ή δείτε την τεκμηρίωση του Aspose.GIS ([Aspose.GIS documentation](https://reference.aspose.com/gis/net/)) για λεπτομερή βήματα.

## Εισαγωγή ονομάτων χώρων
Στο .NET έργο σας, εισάγετε τα απαιτούμενα namespaces ώστε να μπορείτε να εργάζεστε με τις κλάσεις του Aspose.GIS.

Το namespace `Aspose.Gis` περιέχει τους βασικούς τύπους γεωμετρίας, ενώ το `Aspose.Gis.Geometries` παρέχει συγκεκριμένες υλοποιήσεις όπως `Polygon` και `LineString`.

```csharp
using System;
using Aspose.Gis.Geometries;
```

## Οδηγός βήμα‑βήμα

### Βήμα 1: Ορισμός της πηγαίας γεωμετρίας
Η κλάση `GeometryCollection` είναι ένας container που μπορεί να περιέχει οποιονδήποτε αριθμό γεωμετρικών αντικειμένων, συμπεριλαμβανομένων πολυγώνων, σημείων και γραμμών. Είναι το σημείο εισόδου για μαζικές λειτουργίες όπως το `ReplacePolygonsByLines`.

Δημιουργήστε μια συλλογή γεωμετρίας που περιλαμβάνει ένα ή περισσότερα πολύγωνα που θέλετε να μετατρέψετε. Σε αυτό το παράδειγμα προσθέτουμε επίσης ένα σημείο για να δείξουμε ότι τα μη‑πολύγωνα στοιχεία παραμένουν αμετάβλητα.

```csharp
var srcGeometry = Geometry.FromText(@"GeometryCollection (POLYGON((1 2, 1 4, 3 4, 3 2)), Point (5 1))");
```

### Βήμα 2: Μετατροπή πολυγώνων σε γραμμές
Η μέθοδος `ReplacePolygonsByLines()` σαρώνει τη δοθείσα συλλογή, αντικαθιστά κάθε πολύγωνο με ένα `LineString` που ακολουθεί το εξωτερικό του δακτύλιο, και αφήνει όλα τα άλλα είδη γεωμετρίας ανέπαφα. Αυτή η ενιαία κλήση εκτελεί τη μετατροπή σε χρόνο O(n), όπου *n* είναι ο αριθμός των γεωμετριών στη συλλογή.

```csharp
var dstGeometry = srcGeometry.ReplacePolygonsByLines();
```

### Βήμα 3: Εμφάνιση των αρχικών και των μετατρεπόμενων γεωμετριών
Η εκτύπωση τόσο των αρχικών όσο και των μετατρεπόμενων γεωμετριών σας επιτρέπει να επαληθεύσετε ότι τα πολύγωνα έχουν αντικατασταθεί ενώ οι άλλες γεωμετρίες παραμένουν ίδιες. Η υπερφόρτωση `ToString()` σε κάθε γεωμετρία παρέχει μια ανθρώπινα αναγνώσιμη αναπαράσταση WKT.

```csharp
Console.WriteLine($"source: {srcGeometry.AsText()}");
Console.WriteLine($"result: {dstGeometry.AsText()}");
```

## Κοινά προβλήματα και λύσεις
- **Απουσία εξόδου γραμμής:** Βεβαιωθείτε ότι η πηγαία γεωμετρία περιέχει πράγματι πολύγωνα· σημεία ή multipoints θα περάσουν αμετάβλητα.  
- **Προβλήματα σειράς συντεταγμένων:** Το Aspose.GIS αναμένει συντεταγμένες σε σειρά `X Y` (γεωγραφικό μήκος, γεωγραφικό πλάτος). Αντιστραμμένες τιμές μπορούν να δημιουργήσουν απροσδόκητα σχήματα.  
- **Μεγάλες συλλογές:** Για πολύ μεγάλα σύνολα δεδομένων (εκατοντάδες χιλιάδες χαρακτηριστικά), επεξεργαστείτε τις γεωμετρίες σε παρτίδες των 10 000–20 000 αντικειμένων ώστε η χρήση μνήμης να παραμείνει κάτω από 200 MB.

## Συχνές ερωτήσεις

**Q: Μπορεί το Aspose.GIS για .NET να λειτουργήσει με διάφορες μορφές GIS αρχείων;**  
A: Ναι, υποστηρίζει πάνω από 30 μορφές — συμπεριλαμβανομένων Shapefile, GeoJSON, KML, GML, και CSV — επιτρέποντας ανάγνωση, μετατροπή και εγγραφή δεδομένων χωρίς εξωτερικά εργαλεία.

**Q: Υπάρχει δωρεάν δοκιμή διαθέσιμη για το Aspose.GIS για .NET;**  
A: Ναι, μπορείτε να αποκτήσετε τη δωρεάν δοκιμή του Aspose.GIS για .NET από τη σελίδα κυκλοφοριών του Aspose ([Aspose releases page](https://releases.aspose.com/)).

**Q: Παρέχει το Aspose.GIS για .NET υποστήριξη για προγραμματιστές;**  
A: Ναι, οι προγραμματιστές μπορούν να λάβουν υποστήριξη και βοήθεια από το φόρουμ κοινότητας Aspose.GIS ([Aspose.GIS community forum](https://forum.aspose.com/c/gis/33)).

**Q: Μπορώ να αγοράσω προσωρινή άδεια για το Aspose.GIS για .NET;**  
A: Ναι, μπορείτε να αποκτήσετε προσωρινή άδεια από τη σελίδα προσωρινών αδειών του Aspose ([temporary license page](https://purchase.aspose.com/temporary-license/)).

**Q: Είναι το Aspose.GIS για .NET κατάλληλο τόσο για αρχάριους όσο και για έμπειρους προγραμματιστές;**  
A: Απόλυτα, παρέχει πλήρη τεκμηρίωση, παραδείγματα κώδικα και αναφορές API για όλα τα επίπεδα δεξιοτήτων.

## Συμπέρασμα
Ακολουθώντας αυτά τα βήματα, έχετε μάθει πώς να **convert polygon to line** και να **transform polygons to lines** χρησιμοποιώντας το Aspose.GIS για .NET. Αυτή η δυνατότητα ανοίγει το δρόμο για ελαφρύτερες οπτικοποιήσεις, προετοιμασίες δρομολόγησης και πολλές άλλες GIS ροές εργασίας. Μη διστάσετε να εξερευνήσετε πρόσθετες δυνατότητες του Aspose.GIS όπως χωρικά ερωτήματα, επαναπροβολή και μετατροπή μορφών για να επεκτείνετε τις δυνατότητες της εφαρμογής σας.

---

**Last Updated:** 2026-09-15  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose

## Σχετικά Μαθήματα

- [Learn How to Create LineString Geometry with Aspose.GIS for .NET](/gis/net/geometry-creation/create-linestring-geometry/)
- [How to Create GeoJSON with Tolerance Aspose.GIS for .NET](/gis/net/geometry-processing/set-linearization-tolerance/)
- [How to Translate Geometry to WKT with Aspose.GIS for .NET](/gis/net/geometry-processing/translate-geometry-to-wkt/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}