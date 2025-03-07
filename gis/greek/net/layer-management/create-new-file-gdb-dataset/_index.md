---
title: Δημιουργία νέου αρχείου GDB Dataset
linktitle: Δημιουργία νέου αρχείου GDB Dataset
second_title: Aspose.GIS .NET API
description: Εξερευνήστε το Aspose.GIS για .NET για να δημιουργήσετε και να διαχειριστείτε εύκολα σύνολα δεδομένων GIS. Κάντε λήψη τώρα για απρόσκοπτη γεωχωρική ανάπτυξη. #Αποθέστε #GIS
weight: 10
url: /el/net/layer-management/create-new-file-gdb-dataset/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία νέου αρχείου GDB Dataset

## Εισαγωγή
Στον τομέα της γεωχωρικής ανάπτυξης, το Aspose.GIS για .NET ξεχωρίζει ως μια ισχυρή εργαλειοθήκη για τη διαχείριση και τον χειρισμό δεδομένων του Συστήματος Γεωγραφικών Πληροφοριών (GIS). Είτε είστε έμπειρος προγραμματιστής είτε μόλις ξεκινάτε το ταξίδι σας στο GIS, αυτό το σεμινάριο θα σας καθοδηγήσει στη διαδικασία δημιουργίας ενός νέου συνόλου δεδομένων File Geodatabase (GDB) χρησιμοποιώντας το Aspose.GIS για .NET.
## Προαπαιτούμενα
Πριν βουτήξετε στο σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
-  Aspose.GIS για .NET: Βεβαιωθείτε ότι έχετε εγκαταστήσει τη βιβλιοθήκη Aspose.GIS για .NET. Μπορείτε να το κατεβάσετε από το[Σελίδα λήψης Aspose.GIS για .NET](https://releases.aspose.com/gis/net/).
- Περιβάλλον ανάπτυξης: Ρυθμίστε το περιβάλλον ανάπτυξής σας με ένα συμβατό IDE, όπως το Visual Studio, και έχετε βασική κατανόηση του προγραμματισμού .NET.
- Κατάλογος εγγράφων: Αντικαταστήστε τον "Κατάλογο εγγράφων σας" στο απόσπασμα κώδικα με την κατάλληλη διαδρομή όπου θέλετε να αποθηκεύσετε το σύνολο δεδομένων GDB.
- Εξοικείωση με την C#: Αυτό το σεμινάριο προϋποθέτει ότι είστε εξοικειωμένοι με τη γλώσσα προγραμματισμού C#.
## Εισαγωγή χώρων ονομάτων
Στα αρχικά βήματα, εισαγάγετε τους απαραίτητους χώρους ονομάτων για να αξιοποιήσετε τη λειτουργικότητα του Aspose.GIS στην εφαρμογή σας .NET:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Βήμα 1: Δημιουργήστε ένα νέο σύνολο δεδομένων GDB αρχείου
```csharp
string dataDir = "Your Document Directory";
using (var dataset = Dataset.Create(dataDir, Drivers.FileGdb))
{
    Console.WriteLine(dataset.LayersCount); // Έξοδος: 0
    // Συνεχίστε με τα επόμενα βήματα...
}
```
 Επεξήγηση: Σε αυτό το βήμα, δημιουργούμε ένα νέο σύνολο δεδομένων GDB χρησιμοποιώντας το`Dataset.Create` μέθοδος. Καθορίζουμε τη διαδρομή και το πρόγραμμα οδήγησης (FileGdb) για τη δημιουργία μιας βάσης γεωγραφικών δεδομένων αρχείου. Η έξοδος της κονσόλας εμφανίζει τον αρχικό αριθμό επιπέδων, ο οποίος είναι μηδέν σε αυτό το σημείο.
## Βήμα 2: Δημιουργία και συμπλήρωση επιπέδου_1
```csharp
using (var layer = dataset.CreateLayer("layer_1"))
{
    layer.Attributes.Add(new FeatureAttribute("value", AttributeDataType.Integer));
    for (int i = 0; i < 10; ++i)
    {
        var feature = layer.ConstructFeature();
        feature.SetValue("value", i);
        feature.Geometry = new Point(i, i);
        layer.Add(feature);
    }
}
```
Επεξήγηση: Αυτό το βήμα περιλαμβάνει τη δημιουργία ενός επιπέδου με το όνομα "layer_1" μέσα στο σύνολο δεδομένων. Ορίζει ένα χαρακτηριστικό με το όνομα "τιμή" ακέραιου τύπου και συμπληρώνει το επίπεδο με δέκα χαρακτηριστικά, καθένα από τα οποία έχει μια γεωμετρία σημείου.
## Βήμα 3: Δημιουργήστε και συμπληρώστε το Layer_2
```csharp
using (var layer = dataset.CreateLayer("layer_2"))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```
Επεξήγηση: Εδώ, δημιουργούμε ένα δεύτερο επίπεδο με το όνομα "layer_2" και προσθέτουμε ένα μοναδικό χαρακτηριστικό με γεωμετρία συμβολοσειράς γραμμής.
## Βήμα 4: Ελέγξτε τον αριθμό των ενημερωμένων επιπέδων
```csharp
Console.WriteLine(dataset.LayersCount); // Έξοδος: 2
```
Επεξήγηση: Τέλος, ελέγχουμε τον αριθμό των ενημερωμένων επιπέδων αφού προσθέσουμε τα δύο επίπεδα. Σε αυτήν την περίπτωση, η έξοδος πρέπει να είναι 2.
## συμπέρασμα
Συγχαρητήρια! Δημιουργήσατε με επιτυχία ένα νέο σύνολο δεδομένων αρχείου GDB και το συμπληρώσατε με επίπεδα χρησιμοποιώντας το Aspose.GIS για .NET. Αυτό το σεμινάριο παρέχει μια βασική κατανόηση της εργασίας με γεωχωρικά δεδομένα σε περιβάλλον .NET.
## Συχνές Ερωτήσεις
### Ε: Μπορώ να χρησιμοποιήσω το Aspose.GIS για .NET με άλλες βιβλιοθήκες GIS;
Το Aspose.GIS για .NET είναι μια αυτόνομη εργαλειοθήκη. Ωστόσο, μπορείτε να το ενσωματώσετε με άλλες βιβλιοθήκες .NET για να βελτιώσετε τη λειτουργικότητα.
### Ε: Υπάρχει κάποιο φόρουμ κοινότητας για υποστήριξη Aspose.GIS;
 Ναι, μπορείτε να βρείτε υποστήριξη και συζητήσεις για το[Aspose.GIS Forum](https://forum.aspose.com/c/gis/33).
### Ε: Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.GIS;
 Επισκέψου το[Προσωρινή Άδεια](https://purchase.aspose.com/temporary-license/) σελίδα για πληροφορίες σχετικά με την απόκτηση προσωρινής άδειας.
### Ε: Υπάρχουν διαθέσιμα επιπλέον παραδείγματα και τεκμηρίωση;
 Εξερευνήστε το[Τεκμηρίωση Aspose.GIS](https://reference.aspose.com/gis/net/) για περισσότερα παραδείγματα και λεπτομερείς πληροφορίες.
### Ε: Πού μπορώ να αγοράσω το Aspose.GIS για .NET;
 Μπορείτε να αγοράσετε το Aspose.GIS για .NET στο[σελίδα αγοράς](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
