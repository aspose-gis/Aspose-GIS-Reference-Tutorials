---
title: Δημιουργία νέου αρχείου σχήματος
linktitle: Δημιουργία νέου αρχείου σχήματος
second_title: Aspose.GIS .NET API
description: Μάθετε πώς να δημιουργείτε ένα νέο shapefile χρησιμοποιώντας το Aspose.GIS για .NET. Ακολουθήστε τον βήμα προς βήμα οδηγό μας και ξεκλειδώστε τη δύναμη του χειρισμού χωρικών δεδομένων.
weight: 12
url: /el/net/layer-management/create-new-shapefile/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία νέου αρχείου σχήματος

## Εισαγωγή
Εάν εμβαθύνετε στην ανάπτυξη συστημάτων γεωγραφικών πληροφοριών (GIS) με το .NET, το Aspose.GIS είναι η ιδανική λύση. Αυτή η ισχυρή βιβλιοθήκη δίνει τη δυνατότητα στους προγραμματιστές να εργάζονται απρόσκοπτα με χωρικά δεδομένα και σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία δημιουργίας ενός νέου shapefile χρησιμοποιώντας το Aspose.GIS για .NET.
## Προαπαιτούμενα
Πριν προχωρήσουμε στο σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Βασική κατανόηση της γλώσσας προγραμματισμού C#.
- Το Visual Studio είναι εγκατεστημένο στον υπολογιστή σας.
-  Aspose.GIS για τη βιβλιοθήκη .NET. Μπορείτε να το κατεβάσετε[εδώ](https://releases.aspose.com/gis/net/).
## Εισαγωγή χώρων ονομάτων
Ξεκινήστε εισάγοντας τους απαραίτητους χώρους ονομάτων για να αξιοποιήσετε τη λειτουργικότητα του Aspose.GIS:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Βήμα 1: Ρύθμιση του έργου σας
Ξεκινήστε δημιουργώντας ένα νέο έργο C# στο Visual Studio και συμπεριλάβετε τη βιβλιοθήκη Aspose.GIS.
## Βήμα 2: Ορίστε τον Κατάλογο Εγγράφων
```csharp
string dataDir = "Your Document Directory";
```
Αντικαταστήστε το "Ο Κατάλογος Εγγράφων σας" με την πραγματική διαδρομή όπου θέλετε να αποθηκεύσετε το νέο σας αρχείο σχήματος.
## Βήμα 3: Δημιουργήστε ένα VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    //προσθέστε χαρακτηριστικά πριν προσθέσετε χαρακτηριστικά
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
Αυτό το τμήμα κώδικα ρυθμίζει το διανυσματικό επίπεδο και ορίζει χαρακτηριστικά για τα χαρακτηριστικά σας.
## Βήμα 4: Προσθήκη δυνατοτήτων
### Περίπτωση 1: Ορίζει τις τιμές μεμονωμένα
```csharp
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
firstFeature.SetValue("dob", new DateTime(1982, 2, 5, 16, 30, 0));
layer.Add(firstFeature);
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
secondFeature.SetValue("dob", new DateTime(1984, 12, 15, 15, 30, 0));
layer.Add(secondFeature);
```
### Περίπτωση 2: Ορίζει νέες τιμές για όλα τα χαρακτηριστικά
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
## συμπέρασμα
 Συγχαρητήρια! Δημιουργήσατε με επιτυχία ένα νέο shapefile χρησιμοποιώντας το Aspose.GIS για .NET. Αυτό το σεμινάριο κάλυψε τα βασικά της ρύθμισης του έργου σας, τον καθορισμό χαρακτηριστικών και την προσθήκη χαρακτηριστικών. Καθώς εξερευνάτε περαιτέρω, ανατρέξτε στο[τεκμηρίωση](https://reference.aspose.com/gis/net/) για προηγμένες δυνατότητες και λειτουργίες.
## Συχνές Ερωτήσεις
### Ε: Μπορώ να χρησιμοποιήσω το Aspose.GIS με άλλες γλώσσες προγραμματισμού;
Το Aspose.GIS υποστηρίζει κυρίως .NET, αλλά υπάρχουν διαθέσιμες εκδόσεις και για Java.
### Ε: Υπάρχει δωρεάν δοκιμή διαθέσιμη;
 Ναι, μπορείτε να έχετε πρόσβαση στη δωρεάν δοκιμή[εδώ](https://releases.aspose.com/).
### Ε: Πού μπορώ να βρω υποστήριξη για το Aspose.GIS;
 Επισκέψου το[Φόρουμ Aspose.GIS](https://forum.aspose.com/c/gis/33) για κοινοτική υποστήριξη και συζητήσεις.
### Ε: Πώς μπορώ να αποκτήσω προσωρινή άδεια;
 Πάρτε την προσωρινή σας άδεια[εδώ](https://purchase.aspose.com/temporary-license/).
### Ε: Πού μπορώ να αγοράσω το Aspose.GIS για .NET;
 Μπορείτε να αγοράσετε τη βιβλιοθήκη[εδώ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
