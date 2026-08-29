---
date: 2026-08-13
description: Μάθετε πώς να υπολογίζετε το μήκος γεωμετρίας .NET χρησιμοποιώντας το
  Aspose.GIS για αποδοτική διαχείριση χωρικών δεδομένων. Περιλαμβάνει παραδείγματα
  get line length C# και calculate line length C#.
keywords:
- calculate geometry length .net
- Aspose.GIS length calculation
- C# geometry length
lastmod: 2026-08-13
linktitle: Λήψη μήκους γεωμετρίας
og_description: Υπολογίστε το μήκος γεωμετρίας .NET χρησιμοποιώντας το Aspose.GIS.
  Παραδείγματα get line length C# και polygon perimeter σε έναν σύντομο, υψηλής απόδοσης
  οδηγό για προγραμματιστές .NET.
og_image_alt: Developer guide showing how to calculate geometry length in .NET with
  Aspose.GIS
og_title: Υπολογίστε το μήκος γεωμετρίας .NET με Aspose.GIS – Γρήγορες χωρικές μετρήσεις
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to calculate geometry length .NET using Aspose.GIS for efficient
    spatial data handling. Includes get line length C# and calculate line length C#
    examples.
  headline: How to Calculate Geometry Length .NET with Aspose.GIS
  type: TechArticle
- description: Learn how to calculate geometry length .NET using Aspose.GIS for efficient
    spatial data handling. Includes get line length C# and calculate line length C#
    examples.
  name: How to Calculate Geometry Length .NET with Aspose.GIS
  steps:
  - name: Create geometry objects
    text: To begin with, create the geometry objects representing the shapes for which
      you want to calculate the length. This can include lines, polygons, or any other
      geometrical shapes.
  - name: Calculate line length in C#
    text: Once you have created the line geometry, you can calculate its length using
      the `GetLength()` method. This demonstrates **calculate line length c#** in
      a single line of code.
  - name: Create polygon geometry
    text: Similarly, you can create polygon geometry objects using the `Polygon` and
      `LinearRing` classes.
  - name: Get length of a polygon
    text: For polygons, the `GetLength()` method returns the perimeter, which is effectively
      the **how to get length** of the shape.
  type: HowTo
- questions:
  - answer: Aspose.GIS for .NET is compatible with .NET Framework 4.6.1 or later versions,
      as well as .NET 5/6/7.
    question: Is Aspose.GIS for .NET compatible with all .NET frameworks?
  - answer: Yes, you can avail of a free trial of Aspose.GIS for .NET from [here](https://releases.aspose.com/).
    question: Can I try Aspose.GIS for .NET before purchasing?
  - answer: You can find support and assistance from the Aspose.GIS community forum
      [here](https://forum.aspose.com/c/gis/33).
    question: Where can I find support for Aspose.GIS for .NET?
  - answer: You can acquire a temporary license from [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: Yes, Aspose.GIS for .NET provides various formatting options to customize
      the output format as per your requirements.
    question: Can I customize the output format for geometry length calculations?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geometry length
- Aspose.GIS
- C# GIS
- spatial calculations
- line length
title: Πώς να υπολογίσετε το μήκος γεωμετρίας .NET με Aspose.GIS
url: /el/net/geometry-analysis/get-geometry-length/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να υπολογίσετε το μήκος γεωμετρίας .NET με το Aspose.GIS

## Εισαγωγή
Αν ψάχνετε για έναν σαφή, πρακτικό τρόπο να **calculate geometry length .NET**, βρίσκεστε στο σωστό μέρος. Το Aspose.GIS για .NET σας παρέχει ένα πλούσιο σύνολο API προσανατολισμένων σε GIS που κάνουν τους χωρικούς υπολογισμούς—όπως η μέτρηση του μήκους γραμμής ή του περιγράμματος πολύγωνου—απλούς και αποδοτικούς. Σε αυτό το tutorial θα περάσουμε από όλη τη διαδικασία, από τη ρύθμιση του περιβάλλοντος μέχρι τη συγγραφή του κώδικα C# που επιστρέφει ακριβείς τιμές μήκους.

## Γρήγορες Απαντήσεις
- **Τι επιστρέφει η “GetLength()”;** Για γραμμές επιστρέφει το μήκος της γραμμής· για πολύγωνα επιστρέφει το περίμετρο.  
- **Ποιο namespace απαιτείται;** `Aspose.Gis.Geometries`.  
- **Μπορώ να το χρησιμοποιήσω με .NET 6;** Ναι, το Aspose.GIS υποστηρίζει .NET 5, .NET 6 και νεότερες εκδόσεις.  
- **Χρειάζομαι άδεια για ανάπτυξη;** Μια δωρεάν δοκιμή λειτουργεί για αξιολόγηση· απαιτείται άδεια για παραγωγή.  
- **Είναι ο υπολογισμός ενσυνείδητος των μονάδων;** Το μήκος επιστρέφεται στις μονάδες του συστήματος συντεταγμένων (π.χ., μέτρα για προβλεπόμενο CRS).

## Τι είναι το μήκος γεωμετρίας;
Η μέθοδος Geometry.GetLength() υπολογίζει τη συνολική γραμμική απόσταση ενός αντικειμένου γεωμετρίας βάσει των τιμών των συντεταγμένων του. Για ένα LineString αθροίζει τις αποστάσεις μεταξύ διαδοχικών κορυφών, επιστρέφοντας το μήκος της γραμμής. Όταν εφαρμόζεται σε Polygon προσθέτει τα μήκη όλων των ακμών, παρέχοντας ουσιαστικά το περίμετρο του σχήματος.

## Γιατί να χρησιμοποιήσετε το Aspose.GIS για υπολογισμούς μήκους;
Το Aspose.GIS προσφέρει μια πλήρως διαχειριζόμενη βιβλιοθήκη .NET που εκτελεί χωρικούς υπολογισμούς χωρίς την ανάγκη εγγενών δυαδικών αρχείων, καθιστώντας την ανάπτυξη απλή σε Windows, Linux και macOS. Υποστηρίζει πάνω από πενήντα συστήματα αναφοράς συντεταγμένων, παρέχοντας αποτελέσματα υψηλής ακρίβειας double‑precision ακόμη και για γραμμές εκατοντάδων χιλιομέτρων, και ενσωματώνεται άψογα σε έργα .NET 5/6/7, εξασφαλίζοντας συνεπή απόδοση και ακρίβεια.

## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα παρακάτω:

### 1. Βιβλιοθήκη Aspose.GIS για .NET
Αρχικά, πρέπει να έχετε εγκατεστημένη τη βιβλιοθήκη Aspose.GIS για .NET στο περιβάλλον ανάπτυξής σας. Αν δεν το έχετε κάνει ακόμη, μπορείτε να τη κατεβάσετε από τη σελίδα [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/).

### 2. Περιβάλλον ανάπτυξης .NET
Βεβαιωθείτε ότι έχετε ρυθμίσει ένα περιβάλλον ανάπτυξης .NET στον υπολογιστή σας. Αυτό περιλαμβάνει την εγκατάσταση του Visual Studio ή οποιουδήποτε άλλου συμβατού IDE.

### 3. Βασική κατανόηση της C#
Μια βασική κατανόηση της γλώσσας προγραμματισμού C# είναι απαραίτητη για να ακολουθήσετε αυτό το tutorial.

## Εισαγωγή ονομάτων χώρου
Για να αξιοποιήσετε τις λειτουργίες που παρέχει το Aspose.GIS για .NET, πρέπει να εισάγετε τα απαραίτητα namespaces στο έργο C# σας.

### Εισαγωγή ονομάτων χώρου Aspose.GIS
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Πώς να υπολογίσετε το μήκος γραμμής C#
Ένα `LineString` στο Aspose.GIS αντιπροσωπεύει μια σειρά από δύο ή περισσότερα σημεία συνδεδεμένα με ευθείες γραμμές, μοντελοποιώντας γραμμικά χαρακτηριστικά όπως δρόμους, ποτάμια ή γραμμές υποδομών μέσα σε ένα συγκεκριμένο σύστημα αναφοράς συντεταγμένων.  
Αφού δημιουργήσετε το `LineString` με τις επιθυμητές κορυφές, η κλήση της μεθόδου `GetLength()` επιστρέφει τη συνολική απόσταση μετρημένη στις μονάδες CRS της γεωμετρίας, επιτρέποντάς σας να αποκτήσετε γρήγορα ακριβείς μετρήσεις γραμμής για δρομολόγηση, ανάλυση βάσει απόστασης ή αναφορές, και μπορεί να επεξεργαστεί ή αποθηκευτεί περαιτέρω όπως χρειάζεται.

### Βήμα 1: Δημιουργία αντικειμένων γεωμετρίας
Για αρχή, δημιουργήστε τα αντικείμενα γεωμετρίας που αντιπροσωπεύουν τα σχήματα για τα οποία θέλετε να υπολογίσετε το μήκος. Αυτό μπορεί να περιλαμβάνει γραμμές, πολύγωνα ή οποιαδήποτε άλλα γεωμετρικά σχήματα.

```csharp
var line = new LineString();
line.AddPoint(0, 0);
line.AddPoint(2, 2);
line.AddPoint(2, 0);
```

### Βήμα 2: Υπολογισμός μήκους γραμμής σε C#
Αφού δημιουργήσετε τη γεωμετρία της γραμμής, μπορείτε να υπολογίσετε το μήκος της χρησιμοποιώντας τη μέθοδο `GetLength()`. Αυτό δείχνει **calculate line length c#** σε μια μόνο γραμμή κώδικα.

```csharp
Console.WriteLine("{0:F}", line.GetLength()); // Output: 4.83
```

## Πώς να υπολογίσετε το μήκος γραμμής C# για πολύγωνα
Ένα `Polygon` στο Aspose.GIS αποτελείται από ένα εξωτερικό `LinearRing` που ορίζει το όριό του και προαιρετικούς εσωτερικούς δακτύλους για τρύπες, αντιπροσωπεύοντας περιοχές όπως οικόπεδα, λίμνες ή διοικητικές ζώνες μέσα σε μια συγκεκριμένη χωρική αναφορά.  
Δημιουργήστε το εξωτερικό `LinearRing` παρέχοντας τα σημεία γωνίας του πολυγώνου, στη συνέχεια δημιουργήστε ένα `Polygon` με αυτόν τον δακτύλιο· η κλήση του `GetLength()` στο πολύγωνο υπολογίζει το συνολικό περίμετρο, χρήσιμο για εκτιμήσεις μήκους φράχτη, αναφορές ορίων ή μετατροπή τιμών περιμέτρου σε άλλες μονάδες.

### Βήμα 3: Δημιουργία γεωμετρίας πολυγώνου
Αναλόγως, μπορείτε να δημιουργήσετε αντικείμενα γεωμετρίας πολυγώνου χρησιμοποιώντας τις κλάσεις `Polygon` και `LinearRing`.

```csharp
var rectangle = new Polygon(new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 1),
    new Point(1, 1),
    new Point(1, 0),
    new Point(0, 0),
}));
```

### Βήμα 4: Λήψη μήκους πολυγώνου
Για πολύγωνα, η μέθοδος `GetLength()` επιστρέφει το περίμετρο, που είναι ουσιαστικά το **how to get length** του σχήματος.

```csharp
Console.WriteLine("{0:F}", rectangle.GetLength()); // Output: 4.00
```

## Συνηθισμένα προβλήματα και λύσεις
| Πρόβλημα | Λύση |
|----------|------|
| **Απροσδόκητο μηδενικό μήκος** | Επαληθεύστε ότι το σύστημα συντεταγμένων της γεωμετρίας ταιριάζει με τα δεδομένα που παρείχατε· διπλότυπα σημεία μπορούν να προκαλέσουν τμήματα μηδενικού μήκους. |
| **Λανθασμένες μονάδες** | Θυμηθείτε ότι η `GetLength()` επιστρέφει τιμές στις μονάδες του CRS. Μετατρέψτε σε μέτρα/πόδια αν χρειάζεται. |
| **Απόδοση με μεγάλα σύνολα δεδομένων** | Επαναχρησιμοποιήστε αντικείμενα γεωμετρίας όταν είναι δυνατόν και αποφύγετε τη δημιουργία χιλιάδων προσωρινών σημείων μέσα σε σφιχτούς βρόχους. |

## Συχνές ερωτήσεις

**Q: Είναι το Aspose.GIS για .NET συμβατό με όλα τα .NET frameworks;**  
A: Το Aspose.GIS για .NET είναι συμβατό με .NET Framework 4.6.1 ή μεταγενέστερες εκδόσεις, καθώς και με .NET 5/6/7.

**Q: Μπορώ να δοκιμάσω το Aspose.GIS για .NET πριν το αγοράσω;**  
A: Ναι, μπορείτε να αποκτήσετε μια δωρεάν δοκιμή του Aspose.GIS για .NET από [εδώ](https://releases.aspose.com/).

**Q: Πού μπορώ να βρω υποστήριξη για το Aspose.GIS για .NET;**  
A: Μπορείτε να βρείτε υποστήριξη και βοήθεια από το φόρουμ της κοινότητας Aspose.GIS [εδώ](https://forum.aspose.com/c/gis/33).

**Q: Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.GIS για .NET;**  
A: Μπορείτε να αποκτήσετε μια προσωρινή άδεια από [εδώ](https://purchase.aspose.com/temporary-license/).

**Q: Μπορώ να προσαρμόσω τη μορφή εξόδου για τους υπολογισμούς μήκους γεωμετρίας;**  
A: Ναι, το Aspose.GIS για .NET παρέχει διάφορες επιλογές μορφοποίησης για να προσαρμόσετε τη μορφή εξόδου σύμφωνα με τις απαιτήσεις σας.

## Συμπέρασμα
Σε αυτό το tutorial καλύψαμε **how to calculate geometry length .NET** για γραμμές και πολύγωνα χρησιμοποιώντας το Aspose.GIS για .NET. Ακολουθώντας τα βήμα‑βήμα παραδείγματα, μπορείτε τώρα να ενσωματώσετε ακριβείς χωρικές μετρήσεις σε οποιαδήποτε εφαρμογή .NET, είτε πρόκειται για εργαλείο desktop GIS, υπηρεσία web ή pipeline επεξεργασίας δεδομένων backend.

---

**Last Updated:** 2026-08-13  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose

## Σχετικά Μαθήματα

- [Μάθετε πώς να δημιουργήσετε γεωμετρία LineString με το Aspose.GIS για .NET](/gis/net/geometry-creation/create-linestring-geometry/)
- [Πώς να υπολογίσετε το εμβαδόν με το Aspose.GIS για .NET](/gis/net/geometry-analysis/get-geometry-area/)
- [Πώς να δημιουργήσετε γεωμετρία Point και να λάβετε τον τύπο γεωμετρίας με το Aspose.GIS για .NET](/gis/net/geometry-analysis/get-geometry-type/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}