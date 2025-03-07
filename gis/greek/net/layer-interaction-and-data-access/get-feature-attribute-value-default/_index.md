---
title: Λήψη τιμής χαρακτηριστικού χαρακτηριστικού (προεπιλογή)
linktitle: Λήψη τιμής χαρακτηριστικού χαρακτηριστικού (προεπιλογή)
second_title: Aspose.GIS .NET API
description: Ξεκλειδώστε τη δύναμη του Aspose.GIS για .NET! Ανακτήστε και χειριστείτε τις τιμές των χαρακτηριστικών χαρακτηριστικών χωρίς κόπο με αυτόν τον οδηγό βήμα προς βήμα. Κατεβάστε τη δοκιμή σας τώρα!
weight: 14
url: /el/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Λήψη τιμής χαρακτηριστικού χαρακτηριστικού (προεπιλογή)

## Εισαγωγή
Καλώς ήρθατε στον κόσμο του Aspose.GIS για .NET! Σε αυτόν τον περιεκτικό οδηγό, θα εξετάσουμε τις περιπλοκές της ανάκτησης τιμών χαρακτηριστικών χαρακτηριστικών χρησιμοποιώντας τις ισχυρές δυνατότητες του Aspose.GIS. Είτε είστε έμπειρος προγραμματιστής είτε μόλις ξεκινάτε, αυτό το σεμινάριο θα σας προσφέρει μια αναλυτική περιγραφή βήμα προς βήμα, διασφαλίζοντας ότι αξιοποιείτε πλήρως τις δυνατότητες αυτού του αξιοσημείωτου εργαλείου.
## Προαπαιτούμενα
Πριν ξεκινήσουμε αυτήν την περιπέτεια κωδικοποίησης, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Γνώση εργασίας C# και .NET Framework.
-  Εγκαταστάθηκε το Aspose.GIS για .NET. Αν όχι, κατεβάστε το από[εδώ](https://releases.aspose.com/gis/net/).
- Ένα πρόγραμμα επεξεργασίας κώδικα, όπως το Visual Studio, που θα ακολουθήσει απρόσκοπτα.
## Εισαγωγή χώρων ονομάτων
Στο έργο σας C#, φροντίστε να συμπεριλάβετε τους απαραίτητους χώρους ονομάτων:
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
Τώρα, ας αναλύσουμε κάθε παράδειγμα σε μια σειρά εύκολων βημάτων.
## Λήψη τιμής χαρακτηριστικού χαρακτηριστικού (προεπιλογή)
### Βήμα 1: Ρυθμίστε το Περιβάλλον
Ξεκινήστε ορίζοντας τη διαδρομή προς τον κατάλογο των εγγράφων σας:
```csharp
string dataDir = "Your Document Directory";
```
### Βήμα 2: Δημιουργήστε ένα επίπεδο GeoJson
Δημιουργήστε ένα επίπεδο GeoJson και ορίστε ένα χαρακτηριστικό με προεπιλεγμένες τιμές:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```
### Βήμα 3: Κατασκευάστε ένα χαρακτηριστικό
Κατασκευάστε ένα χαρακτηριστικό χρησιμοποιώντας το καθορισμένο χαρακτηριστικό:
```csharp
    Feature feature = layer.ConstructFeature();
```
### Βήμα 4: Ανάκτηση τιμών
Ανάκτηση τιμών χαρακτηριστικών με διάφορα σενάρια:
```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // τιμή == μηδενική
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // τιμή == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // τιμή == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```
## Ορισμός προεπιλεγμένων τιμών
### Βήμα 1: Δημιουργήστε ένα άλλο επίπεδο GeoJson
Επαναλάβετε τη διαδικασία με ένα διαφορετικό επίπεδο GeoJson και ένα διπλό χαρακτηριστικό:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```
### Βήμα 2: Κατασκευάστε ένα χαρακτηριστικό (ξανά)
```csharp
    Feature feature = layer.ConstructFeature();
```
### Βήμα 3: Ανάκτηση και ορισμός τιμών
Ανακτήστε και ορίστε τιμές χαρακτηριστικών, εμφανίζοντας τις προεπιλογές:
```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); // τιμή == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); // τιμή == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); // τιμή == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```
Συγχαρητήρια! Αξιοποιήσατε με επιτυχία τη δύναμη του Aspose.GIS για .NET για την ανάκτηση και τον χειρισμό τιμών χαρακτηριστικών χαρακτηριστικών.
## συμπέρασμα
Σε αυτό το σεμινάριο, έχουμε εξερευνήσει τις αποχρώσεις της ανάκτησης τιμών χαρακτηριστικών χαρακτηριστικών χρησιμοποιώντας το Aspose.GIS για .NET. Με το διαισθητικό API και τις ισχυρές δυνατότητές του, το Aspose.GIS ανοίγει έναν κόσμο δυνατοτήτων για ανάπτυξη GIS σε περιβάλλοντα .NET.
## Συχνές Ερωτήσεις
### Είναι το Aspose.GIS συμβατό με .NET Core;
Ναι, το Aspose.GIS είναι πλήρως συμβατό με το .NET Core, παρέχοντας υποστήριξη μεταξύ πλατφορμών.
### Μπορώ να χρησιμοποιήσω το Aspose.GIS για εμπορικά έργα;
Απολύτως! Το Aspose.GIS συνοδεύεται από εμπορική άδεια που σας επιτρέπει να το χρησιμοποιείτε στις εμπορικές σας εφαρμογές χωρίς περιορισμούς.
### Πού μπορώ να βρω πρόσθετη υποστήριξη και πόρους;
 Επισκέψου το[Φόρουμ Aspose.GIS](https://forum.aspose.com/c/gis/33) για υποστήριξη της κοινότητας και να εξερευνήσετε το[τεκμηρίωση](https://reference.aspose.com/gis/net/) για εις βάθος πληροφορίες.
### Υπάρχει δωρεάν δοκιμή διαθέσιμη;
 Ναι, μπορείτε να εξερευνήσετε το Aspose.GIS με μια δωρεάν δοκιμή. Κατέβασέ το[εδώ](https://releases.aspose.com/).
### Πώς μπορώ να αποκτήσω μια προσωρινή άδεια για σκοπούς δοκιμής;
 Για προσωρινές άδειες, επισκεφθείτε[εδώ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
