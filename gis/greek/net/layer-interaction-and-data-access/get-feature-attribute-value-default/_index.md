---
date: 2026-01-05
description: Μάθετε πώς να λαμβάνετε τιμές χαρακτηριστικών και να ορίζετε προεπιλογές
  στο Aspose.GIS για .NET. Αυτός ο οδηγός βήμα‑βήμα δείχνει τη δημιουργία επιπέδων
  GeoJSON και την κατασκευή χαρακτηριστικών GIS.
linktitle: How to Get Attribute Value (Default)
second_title: Aspose.GIS .NET API
title: Πώς να λάβετε την τιμή του χαρακτηριστικού (προεπιλογή) με το Aspose.GIS για
  .NET
url: /el/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Λάβετε Τιμή Ιδιότητας (Προεπιλογή) με Aspise.GIS για .NET

## Εισαγωγή
Σε αυτό το ολοκληρωμένο tutorial θα ανακαλύψετε **πώς να λάβετε τιμές ιδιότητας** από ένα GIS feature χρησιμοποιώντας Aspose.GIS για .NET, και πώς να εργαστείτε με προεπιλεγμένες τιμές όταν μια ιδιότητα λείπει. Είτε δημιουργείτε μια μηχανή χωρικής ανάλυσης είτε έναν απλό προβολέα χαρτών, η κατανόηση της ανάκτησης ιδιοτήτων και της διαχείρισης προεπιλογών είναι απαραίτητη για αξιόπιστες GIS εφαρμογές.

## Γρήγορες Απαντήσεις
- **Ποια είναι η κύρια μέθοδος;** `Feature.GetValueOrDefault<T>()`  
- **Μπορώ να ορίσω προσαρμοσμένη προεπιλογή;** Ναι, μέσω του overload που δέχεται μια προεπιλεγμένη τιμή ή ορίζοντας `DefaultValue` στην ιδιότητα.  
- **Χρειάζεται άδεια για ανάπτυξη;** Μια δωρεάν δοκιμή λειτουργεί για δοκιμές· απαιτείται εμπορική άδεια για παραγωγή.  
- **Υποστηριζόμενες μορφές γεωμετρίας;** GeoJSON, Shapefile, GML και πολλές άλλες μέσω των drivers του Aspose.GIS.  
- **Λειτουργεί με .NET Core/.NET 6+;** Απόλυτα – η βιβλιοθήκη είναι cross‑platform.

## Προαπαιτούμενα
Πριν προχωρήσουμε, βεβαιωθείτε ότι έχετε:

- Βασική εξοικείωση με C# και το οικοσύστημα .NET.  
- Εγκατεστημένο το Aspose.GIS για .NET. Αν δεν το έχετε κάνει ακόμη, κατεβάστε το από [εδώ](https://releases.aspose.com/gis/net/).  
- Έναν επεξεργαστή κώδικα όπως το Visual Studio ή το Visual Studio Code.

## Εισαγωγή Χώρων Ονομάτων
Προσθέστε τις απαιτούμενες δηλώσεις `using` στο αρχείο C# ώστε οι τύποι του API να είναι διαθέσιμοι:

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Τώρα ας περάσουμε από κάθε παράδειγμα βήμα‑βήμα.

## Πώς να Λάβετε Τιμή Ιδιότητας (Προεπιλογή)
### Βήμα 1: Ρύθμιση Περιβάλλοντος
Ορίστε τη διαδρομή προς το φάκελο που περιέχει τα δοκιμαστικά έγγραφα:

```csharp
string dataDir = "Your Document Directory";
```

### Βήμα 2: Δημιουργία Στρώματος GeoJSON
Θα **δημιουργήσουμε ένα στρώμα geojson** — το πρώτο σημείο όπου ορίζουμε μια ιδιότητα που μπορεί να είναι null ή ακαθόριστη:

```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```

### Βήμα 3: Κατασκευή GIS Feature
Τώρα **κατασκευάζουμε ένα GIS feature** — αυτό μας δίνει ένα νέο αντικείμενο feature που σέβεται το σχήμα ιδιοτήτων που μόλις ορίσαμε:

```csharp
    Feature feature = layer.ConstructFeature();
```

### Βήμα 4: Ανάκτηση Τιμών
Τέλος, **λαμβάνουμε τιμές ιδιότητας** του feature χρησιμοποιώντας διάφορα σενάρια, δείχνοντας πώς λειτουργούν οι προεπιλογές:

```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // value == null
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // value == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // value == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```

## Πώς να Ορίσετε Προεπιλεγμένες Τιμές
### Βήμα 1: Δημιουργία Άλλου Στρώματος GeoJSON
Αυτή τη φορά **ορίζουμε προεπιλογή ιδιότητας** απευθείας στο σχήμα:

```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```

### Βήμα 2: Κατασκευή GIS Feature (Ξανά)
```csharp
    Feature feature = layer.ConstructFeature();
```

### Βήμα 3: Ανάκτηση και Ορισμός Τιμών
Ανακτούμε την προεπιλογή, έπειτα την αλλάζουμε για να δούμε το αποτέλεσμα του **πώς να ορίσετε προεπιλογή** σε χρόνο εκτέλεσης:

```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); // value == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); // value == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); // value == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```

## Συνηθισμένα Παγίδες & Συμβουλές
- **Ποτέ μην ξεχάσετε να κλείσετε το μπλοκ `using`.** Το στρώμα διαχειρίζεται αυτόματα την απελευθέρωση των χειριστών αρχείων.  
- **Όταν το `CanBeNull` είναι false, το `GetValueOrDefault` θα επιστρέφει πάντα μια τιμή** (είτε την αποθηκευμένη είτε την ορισμένη προεπιλογή).  
- **Χρησιμοποιήστε το γενικό overload** (`GetValueOrDefault<T>`) για να αποφύγετε το boxing/unboxing των τύπων τιμής.  
- **Pro tip:** Αν χρειάζεται να ελέγξετε αν μια ιδιότητα είναι πραγματικά ορισμένη, χρησιμοποιήστε `feature.IsAttributeSet("attribute")` πριν καλέσετε το `GetValueOrDefault`.

## Συχνές Ερωτήσεις
### Είναι το Aspose.GIS συμβατό με .NET Core;
Ναι, το Aspose.GIS είναι πλήρως συμβατό με .NET Core, παρέχοντας υποστήριξη cross‑platform.

### Μπορώ να χρησιμοποιήσω το Aspose.GIS για εμπορικά έργα;
Απολύτως! Το Aspose.GIS διαθέτει εμπορική άδεια που σας επιτρέπει να το χρησιμοποιήσετε σε εμπορικές εφαρμογές χωρίς περιορισμούς.

### Πού μπορώ να βρω επιπλέον υποστήριξη και πόρους;
Επισκεφθείτε το [φόρουμ Aspose.GIS](https://forum.aspose.com/c/gis/33) για υποστήριξη από την κοινότητα και εξερευνήστε την [τεκμηρίωση](https://reference.aspose.com/gis/net/) για λεπτομερείς πληροφορίες.

### Υπάρχει διαθέσιμη δωρεάν δοκιμή;
Ναι, μπορείτε να δοκιμάσετε το Aspose.GIS με δωρεάν δοκιμή. Κατεβάστε το [εδώ](https://releases.aspose.com/).

### Πώς να αποκτήσω προσωρινή άδεια για δοκιμαστικούς σκοπούς;
Για προσωρινές άδειες, επισκεφθείτε [εδώ](https://purchase.aspose.com/temporary-license/).

## Πρόσθετες Συχνές Ερωτήσεις
**Ε: Τι συμβαίνει αν καλέσω το `GetValueOrDefault` σε μια ιδιότητα που δεν υπάρχει;**  
Α: Η μέθοδος ρίχνει `ArgumentException`. Πάντα επαληθεύετε το όνομα της ιδιότητας ή χρησιμοποιήστε πρώτα το `feature.HasAttribute("name")`.

**Ε: Μπορώ να αλλάξω την προεπιλεγμένη τιμή μετά τη δημιουργία του στρώματος;**  
Α: Ναι, μπορείτε να τροποποιήσετε το `attribute.DefaultValue` και στη συνέχεια να καλέσετε `layer.UpdateAttribute(attribute)` για να αποθηκεύσετε την αλλαγή.

**Ε: Υποστηρίζει το Aspose.GIS μαζικές ενημερώσεις τιμών ιδιοτήτων;**  
Α: Μπορείτε να διατρέξετε μια συλλογή features και να καλέσετε `SetValue` σε κάθε feature· για μεγάλα σύνολα δεδομένων, σκεφτείτε τη χρήση του API `FeatureCursor` για καλύτερη απόδοση.

## Συμπέρασμα
Σε αυτόν τον οδηγό καλύψαμε **πώς να λάβετε τιμές ιδιότητας**, πώς να ορίσετε και να παρακάμψετε προεπιλογές, και πώς να **δημιουργήσετε σχήματα στρωμάτων GeoJSON** που ταιριάζουν στις ανάγκες της εφαρμογής σας. Με αυτές τις τεχνικές μπορείτε να χτίσετε αξιόπιστες GIS λύσεις που διαχειρίζονται ομαλά τα ελλιπή ή προαιρετικά δεδομένα.

---

**Τελευταία Ενημέρωση:** 2026-01-05  
**Δοκιμάστηκε Με:** Aspose.GIS 24.11 για .NET  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}