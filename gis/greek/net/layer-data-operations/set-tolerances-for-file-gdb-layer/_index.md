---
date: 2025-12-31
description: Εξερευνήστε το Aspose.GIS για .NET και μάθετε πώς να δημιουργείτε σύνολο
  δεδομένων file GDB και να ορίζετε ανοχές χωρίς κόπο, με καθοδήγηση βήμα‑προς‑βήμα.
  Βελτιώστε τις .NET εφαρμογές σας.
linktitle: Set Tolerances for File GDB Layer
second_title: Aspose.GIS .NET API
title: Δημιουργία συνόλου δεδομένων File GDB και ορισμός ανοχών για ένα στρώμα
url: /el/net/layer-data-operations/set-tolerances-for-file-gdb-layer/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία συνόλου δεδομένων File GDB και ορισμός ανοχών για ένα στρώμα

## Introduction
Αν χρειάζεστε να **create file GDB dataset** και να ελέγξετε την ακρίβειά του, βρίσκεστε στο σωστό μέρος. Σε αυτό το tutorial θα περάσουμε από όλη τη διαδικασία — ξεκινώντας από τη ρύθμιση του .NET project σας, τη δημιουργία ενός File Geodatabase (GDB) dataset, και στη συνέχεια την εφαρμογή ανοχών XY, Z και M σε ένα νέο στρώμα. Στο τέλος θα έχετε ένα έτοιμο‑για‑χρήση σύνολο δεδομένων που λειτουργεί ομαλά με τα εργαλεία ArcGIS και άλλες GIS εφαρμογές.

## Quick Answers
- **Τι σημαίνει “create file GDB dataset”;** Δημιουργεί ένα νέο κοντέινερ File Geodatabase στο δίσκο που μπορεί να περιέχει πολλαπλά GIS στρώματα.  
- **Γιατί ορίζονται ανοχές;** Οι ανοχές ορίζουν την ακρίβεια για γεωμετρικές λειτουργίες, αποτρέποντας σφάλματα στρογγυλοποίησης στην χωρική ανάλυση.  
- **Ποια κλάση Aspose.GIS χρησιμοποιείται;** `Dataset.Create` μαζί με `FileGdbOptions`.  
- **Χρειάζομαι άδεια για ανάπτυξη;** Μια προσωρινή άδεια αρκεί για δοκιμές· απαιτείται πλήρης άδεια για παραγωγή.  
- **Ποιες εκδόσεις .NET υποστηρίζονται;** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## What is a File GDB Dataset?
Ένα File Geodatabase (GDB) είναι ένας αποθηκευτικός χώρος βασισμένος σε φάκελο που περιέχει GIS στρώματα, πίνακες και σχέσεις. Χρησιμοποιώντας το Aspose.GIS μπορείτε προγραμματιστικά **create file GDB dataset** χωρίς να χρειάζεται εγκατεστημένο ArcGIS, καθιστώντας το ιδανικό για αυτοματοποιημένες γραμμές επεξεργασίας ή προσαρμοσμένες εφαρμογές.

## Why set tolerances for a layer?
Ο ορισμός ανοχών εξασφαλίζει ότι οι γεωμετρικοί υπολογισμοί (όπως τομές, buffer ή snapping) σέβονται την ακρίβεια που χρειάζεστε. Αυτό είναι ιδιαίτερα σημαντικό όταν εργάζεστε με δεδομένα υψηλής ανάλυσης ή όταν εξάγετε σε άλλες GIS πλατφόρμες που απαιτούν συγκεκριμένες τιμές ανοχής.

## Prerequisites
Πριν βουτήξουμε στον κώδικα, βεβαιωθείτε ότι έχετε τα εξής:

- **Aspose.GIS for .NET Library** – Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη Aspose.GIS από το [download link](https://releases.aspose.com/gis/net/). Αν δεν την έχετε αποκτήσει ακόμη, μπορείτε να εξερευνήσετε τη βιβλιοθήκη περαιτέρω στην [documentation](https://reference.aspose.com/gis/net/).
- **Development Environment** – Visual Studio, Rider ή οποιοδήποτε IDE που υποστηρίζει ανάπτυξη .NET.
- **A valid license** – Χρησιμοποιήστε μια προσωρινή άδεια για δοκιμές ή μια πλήρη άδεια για παραγωγή (δείτε τους συνδέσμους στην ενότητα FAQ).

Τώρα που έχετε όλα έτοιμα, ας εισάγουμε τα namespaces που θα χρειαστούμε.

## Import Namespaces
Στην .NET εφαρμογή σας, συμπεριλάβετε τα παρακάτω namespaces για να αξιοποιήσετε τις λειτουργίες του Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Text;
```

Με τα namespaces στη θέση τους, μπορούμε να αρχίσουμε να δημιουργούμε το σύνολο δεδομένων.

## Step‑by‑Step Guide

### Step 1: Define Your Document Directory
Πρώτα, κατευθύνετε τον κώδικα στον φάκελο όπου θέλετε να δημιουργηθεί το File GDB:

```csharp
string dataDir = "Your Document Directory";
```

> **Pro tip:** Χρησιμοποιήστε `Path.Combine` αν χρειάζεται να δημιουργήσετε τη διαδρομή με ανεξάρτητο από την πλατφόρμα τρόπο.

### Step 2: Create a File GDB Dataset
Τώρα δημιουργούμε πραγματικά **create file GDB dataset** στο δίσκο. Η μέθοδος `Dataset.Create` παίρνει τη πλήρη διαδρομή και τον τύπο οδηγού (`Drivers.FileGdb`).

```csharp
var path = dataDir + "TolerancesForFileGdbLayer_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

> Το μπλοκ `using` εξασφαλίζει ότι το σύνολο δεδομένων κλείνει σωστά και αποθηκεύεται στο δίσκο όταν τελειώσετε.

### Step 3: Set Tolerances using `FileGdbOptions`
Πριν δημιουργήσετε ένα στρώμα, ορίστε τις ανοχές που χρειάζεστε. Το `FileGdbOptions` σας επιτρέπει να καθορίσετε ανοχές XY, Z και M.

```csharp
var options = new FileGdbOptions
{
    XYTolerance = 0.001,
    ZTolerance = 0.1,
    MTolerance = 0.1,
};
```

Αυτές οι τιμές είναι τυπικές για δεδομένα υψηλής ακρίβειας μηχανικής, αλλά μπορείτε να τις προσαρμόσετε ώστε να ταιριάζουν στο έργο σας.

### Step 4: Create a Layer with the Specified Tolerances
Τέλος, δημιουργήστε ένα νέο στρώμα μέσα στο σύνολο δεδομένων, περνώντας το αντικείμενο επιλογών που μόλις διαμορφώσαμε.

```csharp
using (var layer = dataset.CreateLayer("layer_name", options))
{
    // The layer is created with the provided tolerances, ready for use in ArcGIS features/tools.
}
```

Όταν το μπλοκ `using` τελειώσει, το στρώμα αποθηκεύεται με τις ανοχές που ορίσατε.

## Common Issues & Solutions
| Πρόβλημα | Γιατί συμβαίνει | Διόρθωση |
|----------|------------------|----------|
| **Dataset path not found** | Η μεταβλητή `dataDir` δείχνει σε φάκελο που δεν υπάρχει. | Βεβαιωθείτε ότι ο φάκελος υπάρχει ή δημιουργήστε τον με `Directory.CreateDirectory(dataDir)`. |
| **Invalid tolerance values** | Οι ανοχές πρέπει να είναι μη‑αρνητικούς αριθμοί. | Χρησιμοποιήστε θετικές τιμές· αποφύγετε το μηδέν εκτός αν θέλετε σκόπιμα να μην υπάρχει ανοχή. |
| **License error** | Μια δοκιμαστική ή προσωρινή άδεια έχει λήξει. | Εφαρμόστε μια νέα προσωρινή άδεια ή αναβαθμίστε σε πλήρη άδεια. |

## Frequently Asked Questions

**Ε: Μπορώ να χρησιμοποιήσω το Aspose.GIS για .NET με άλλες GIS βιβλιοθήκες;**  
Α: Ναι, το Aspose.GIS υποστηρίζει διαλειτουργικότητα, επιτρέποντάς σας να το ενσωματώσετε με βιβλιοθήκες όπως NetTopologySuite ή GDAL.

**Ε: Υπάρχει δοκιμαστική έκδοση του Aspose.GIS για .NET;**  
Α: Απόλυτα! Μπορείτε να εξερευνήσετε τις δυνατότητες με τη [free trial version](https://releases.aspose.com/).

**Ε: Πώς μπορώ να λάβω υποστήριξη για το Aspose.GIS για .NET;**  
Α: Επισκεφθείτε το [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) για να συνδεθείτε με την κοινότητα και να ζητήσετε βοήθεια.

**Ε: Χρειάζομαι προσωρινή άδεια για δοκιμές;**  
Α: Ναι, μπορείτε να αποκτήσετε μια [temporary license](https://purchase.aspose.com/temporary-license/) για δοκιμές και αξιολόγηση.

**Ε: Πού μπορώ να αγοράσω την άδεια Aspose.GIS για .NET;**  
Α: Μπορείτε να αγοράσετε την άδεια από τη [buy page](https://purchase.aspose.com/buy).

## Conclusion
Σε αυτόν τον οδηγό καλύψαμε πώς να **create file GDB dataset**, να ρυθμίσουμε τις ανοχές γεωμετρίας και να αποθηκεύσουμε ένα έτοιμο‑για‑χρήση στρώμα με το Aspose.GIS για .NET. Αυτά τα βήματα σας παρέχουν ακριβή έλεγχο των χωρικών δεδομένων, καθιστώντας τις GIS εφαρμογές σας πιο αξιόπιστες και διαλειτουργικές.

---  
**Τελευταία ενημέρωση:** 2025-12-31  
**Δοκιμάστηκε με:** Aspose.GIS for .NET 24.11 (latest at time of writing)  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}