---
date: 2026-11-12
description: Μάθετε πώς να μετατρέψετε geojson σε topojson με ομαδοποίηση, να ορίσετε
  το χαρακτηριστικό ονόματος αντικειμένου και να ομαδοποιήσετε χαρακτηριστικά GeoJSON
  χρησιμοποιώντας το Aspose.GIS για .NET.
images:
- /net/geo-data-conversion/convert-geojson-to-topojson-with-grouping/og-image.png
keywords:
- convert geojson to topojson
- how to group features
- group features by attribute
- group geojson features
- asp.net core geojson
lastmod: 2026-11-12
linktitle: Πώς να μετατρέψετε GeoJSON σε TopoJSON με ομαδοποίηση χρησιμοποιώντας το
  Aspose.GIS
og_description: Μάθετε πώς να μετατρέψετε geojson σε topojson με ομαδοποίηση, να ορίσετε
  το χαρακτηριστικό ονόματος αντικειμένου και να ομαδοποιήσετε αποδοτικά χαρακτηριστικά
  GeoJSON χρησιμοποιώντας το Aspose.GIS για .NET.
og_image_alt: Screenshot of Aspose.GIS conversion code showing GeoJSON to TopoJSON
  with grouping
og_title: Μετατροπή geojson σε topojson με ομαδοποίηση χρησιμοποιώντας το Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-11-12'
  description: Learn how to convert geojson to topojson with grouping, set object
    name attribute, and group GeoJSON features using Aspose.GIS for .NET.
  headline: How to convert geojson to topojson with grouping using Aspose.GIS
  type: TechArticle
- description: Learn how to convert geojson to topojson with grouping, set object
    name attribute, and group GeoJSON features using Aspose.GIS for .NET.
  name: How to convert geojson to topojson with grouping using Aspose.GIS
  steps:
  - name: Define file paths
    text: 'Specify where the source GeoJSON lives and where the TopoJSON should be
      written: > **Pro tip:** Use `Path.Combine` for cross‑platform path building
      if you target .NET Core.'
  - name: Configure conversion options (set object name attribute)
    text: '`ConversionOptions` is the Aspose.GIS class that defines how a conversion
      should be performed, including grouping and precision settings. It lets you
      set the grouping attribute, define a default object name, and tweak topology
      precision. The `ObjectNameAttribute` property (string) defines the GeoJSON field
      used for grouping, while `De'
  - name: Perform the conversion (convert GeoJSON to TopoJSON)
    text: '`Conversion.Convert` is a static method that reads the source file, applies
      the provided options, and writes the converted TopoJSON output. It internally
      builds a topology graph, deduplicates shared edges, and writes the result in
      the compact TopoJSON format.'
  type: HowTo
- questions:
  - answer: Yes, you can concatenate several fields into a single virtual attribute
      or run multiple conversion passes with different `ObjectNameAttribute` values.
    question: Can I group features based on multiple attributes?
  - answer: Absolutely – the library works with ASP.NET Core, .NET 5, .NET 6, and
      the classic .NET Framework.
    question: Is Aspose.GIS compatible with ASP.NET Core?
  - answer: Yes, Aspose.GIS supports more than 30 input and output formats—including
      Shapefile, KML, GML, CSV, and DXF—for both import and export.
    question: Can I convert other geographic formats besides GeoJSON?
  - answer: Yes, you can get a free trial of Aspose.GIS from the [Aspose.GIS free
      trial page](https://releases.aspose.com/).
    question: Does Aspose.GIS offer a free trial?
  - answer: You can get support from the Aspose.GIS community forum [Aspose.GIS community
      forum](https://forum.aspose.com/c/gis/33).
    question: Where can I get support for Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert geojson
- Aspose.GIS
- C# GIS processing
- geojson conversion
- topojson grouping
title: Πώς να μετατρέψετε geojson σε topojson με ομαδοποίηση χρησιμοποιώντας το Aspose.GIS
url: /el/net/geo-data-conversion/convert-geojson-to-topojson-with-grouping/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να μετατρέψετε geojson σε topojson με ομαδοποίηση χρησιμοποιώντας Aspose.GIS

## Εισαγωγή

Σε αυτό το βήμα‑βήμα tutorial θα μάθετε **πώς να μετατρέψετε geojson σε topojson** ενώ ομαδοποιείτε τα χαρακτηριστικά βάσει μιας επιλεγμένης ιδιότητας. Η χρήση του Aspose.GIS .NET API κάνει τη μετατροπή γρήγορη (επεξεργάζεται έως και 2 000 χαρακτηριστικά ανά δευτερόλεπτο) και πλήρως ελεγχόμενη από τον κώδικα C#. Είτε δημιουργείτε μια υπηρεσία μετατροπής geojson για ASP.NET Core, ένα desktop GIS εργαλείο, ή μια αυτοματοποιημένη pipeline δεδομένων, αυτός ο οδηγός σας δείχνει ακριβώς τι πρέπει να κάνετε για **να μετατρέψετε geojson σε topojson** αποδοτικά και αξιόπιστα.

## Γρήγορες απαντήσεις

- **Ποια βιβλιοθήκη διαχειρίζεται τη μετατροπή;** Aspose.GIS for .NET  
- **Πόσο διαρκεί η υλοποίηση;** Συνήθως 5‑10 λεπτά για μια βασική ρύθμιση  
- **Χρειάζομαι άδεια για παραγωγή;** Ναι, απαιτείται εμπορική άδεια (διατίθεται δωρεάν δοκιμή)  
- **Μπορώ να ομαδοποιήσω χαρακτηριστικά με βάση οποιαδήποτε ιδιότητα;** Ναι – ορίστε το `ObjectNameAttribute` στο πεδίο που θέλετε να ομαδοποιήσετε  
- **Υποστηρίζεται το .NET Core;** Απόλυτα – το API λειτουργεί με .NET Core, .NET 5/6, και το κλασικό .NET Framework  

## Πώς να μετατρέψετε geojson σε topojson με ομαδοποίηση σε C#

Φορτώστε το πηγαίο GeoJSON, διαμορφώστε το `ConversionOptions` με το επιθυμητό `ObjectNameAttribute` και καλέστε το `Conversion.Convert` – αυτή η μοναδική κλήση παράγει ένα πλήρως ομαδοποιημένο αρχείο TopoJSON σε λιγότερο από ένα δευτερόλεπτο για τυπικά σύνολα δεδομένων σε κλίμακα πόλης. Μπορείτε να ενσωματώσετε αυτό το μοτίβο σε μια εφαρμογή κονσόλας, μια υπηρεσία παρασκηνίου ή ένα endpoint μετατροπής geojson σε ASP.NET Core. Το API αφαιρεί όλους τους χαμηλού επιπέδου υπολογισμούς τοπολογίας, ώστε να εστιάσετε στη λογική της επιχείρησης αντί στη μαθηματική γεωμετρία.

## Τι είναι το GeoJSON και το TopoJSON;

Το GeoJSON είναι μια μορφή βασισμένη σε JSON που κωδικοποιεί γεωγραφικά χαρακτηριστικά όπως σημεία, γραμμές και πολύγωνα. Το TopoJSON επεκτείνεται από το GeoJSON αποθηκεύοντας κοινά τμήματα γραμμών (τοπολογία) αντί να επαναλαμβάνει συντεταγμένες για κάθε χαρακτηριστικό. Αυτό μειώνει το μέγεθος του αρχείου, εξαλείφει την πλεοναστικότητα και βελτιώνει την απόδοση της απόδοσης σε χάρτες ιστού.

## Γιατί να ομαδοποιήσετε χαρακτηριστικά GeoJSON;

Η ομαδοποίηση των χαρακτηριστικών GeoJSON κατά τη μετατροπή δημιουργεί ονομαστικά αντικείμενα στο αρχείο TopoJSON, επιτρέποντας στα επόμενα εργαλεία χαρτογράφησης να αντιμετωπίζουν σχετικές γεωμετρίες ως ένα ενιαίο στρώμα. Αυτό απλοποιεί το στυλ, μειώνει τον αριθμό των κλήσεων σχεδίασης και εξαλείφει τα διπλότυπα δεδομένα συνόρων μεταξύ γειτονικών χαρακτηριστικών, οδηγώντας σε ταχύτερη απόδοση και μικρότερα αρχεία.

## Ορίστε την ιδιότητα ονόματος αντικειμένου για ομαδοποίηση

Το `ObjectNameAttribute` λέει στο Aspose.GIS ποια ιδιότητα στο πηγαίο GeoJSON πρέπει να χρησιμοποιηθεί ως όνομα αντικειμένου στην έξοδο TopoJSON. Η σωστή ρύθμιση αυτής της ιδιότητας είναι το κλειδί για επιτυχημένη **ομαδοποίηση χαρακτηριστικών geojson**.

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα παρακάτω προαπαιτούμενα:

1. **Aspose.GIS for .NET** – κατεβάστε και εγκαταστήστε από τη [Aspose.GIS for .NET release page](https://releases.aspose.com/gis/net/).  
2. **Περιβάλλον ανάπτυξης** – Visual Studio, Visual Studio Code, ή οποιοδήποτε IDE που υποστηρίζει C#.  
3. **Δείγμα αρχείου GeoJSON** – ένα αρχείο που περιέχει τα χαρακτηριστικά που θέλετε να μετατρέψετε.  

## Εισαγωγή ονομάτων χώρων

Πρώτα, συμπεριλάβετε τα απαραίτητα namespaces στο πρότζεκτ σας:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
```

## Οδηγός βήμα‑βήμα

### Βήμα 1: Ορισμός διαδρομών αρχείων

Καθορίστε πού βρίσκεται το πηγαίο GeoJSON και πού πρέπει να γραφτεί το TopoJSON:

```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithGrouping_out.topojson";
```

> **Συμβουλή:** Χρησιμοποιήστε το `Path.Combine` για δημιουργία διαδρομών δια‑πλατφόρμας εάν στοχεύετε σε .NET Core.

### Βήμα 2: Διαμόρφωση επιλογών μετατροπής (ορισμός ιδιότητας ονόματος αντικειμένου)

`ConversionOptions` είναι η κλάση του Aspose.GIS που ορίζει πώς πρέπει να εκτελείται μια μετατροπή, συμπεριλαμβανομένων των ρυθμίσεων ομαδοποίησης και ακρίβειας. Σας επιτρέπει να ορίσετε την ιδιότητα ομαδοποίησης, να ορίσετε ένα προεπιλεγμένο όνομα αντικειμένου και να ρυθμίσετε την ακρίβεια της τοπολογίας.

Η ιδιότητα `ObjectNameAttribute` (string) ορίζει το πεδίο GeoJSON που χρησιμοποιείται για ομαδοποίηση, ενώ το `DefaultObjectName` (string) παρέχει ένα εναλλακτικό όνομα για χαρακτηριστικά που δεν έχουν την ιδιότητα. Αυτός είναι ο τρόπος ομαδοποίησης χαρακτηριστικών με βάση την ιδιότητα χρησιμοποιώντας την ιδιότητα ObjectNameAttribute. Αντικαταστήστε το `"group"` με το πραγματικό όνομα της ιδιότητας στο GeoJSON που θέλετε να χρησιμοποιήσετε για **ομαδοποίηση χαρακτηριστικών geojson**. Το `DefaultObjectName` εξασφαλίζει ότι κάθε χαρακτηριστικό θα καταλήξει σε ένα αντικείμενο TopoJSON, ακόμη και αν λείπει η ιδιότητα.

```csharp
var options = new ConversionOptions
{
    DestinationDriverOptions = new TopoJsonOptions
    {
        // Specify the attribute in GeoJSON layer by which we are going to group into objects
        ObjectNameAttribute = "group",
        // Specify the default object name for features with unknown attribute values
        DefaultObjectName = "unnamed",
    }
};
```

### Βήμα 3: Εκτέλεση της μετατροπής (μετατροπή GeoJSON σε TopoJSON)

`Conversion.Convert` είναι μια στατική μέθοδος που διαβάζει το πηγαίο αρχείο, εφαρμόζει τις παρεχόμενες επιλογές και γράφει το μετατρεπόμενο αρχείο TopoJSON. Εσωτερικά δημιουργεί ένα γράφημα τοπολογίας, αφαιρεί διπλότυπες κοινές ακμές και γράφει το αποτέλεσμα σε συμπαγή μορφή TopoJSON.

```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```

Μετά την εκτέλεση, το `convertedSampleWithGrouping_out.topojson` θα περιέχει την αναπαράσταση TopoJSON, με τα χαρακτηριστικά ομαδοποιημένα σύμφωνα με την ιδιότητα που καθορίσατε.

## Συχνά προβλήματα και αντιμετώπιση

| Σύμπτωμα | Πιθανή αιτία | Διόρθωση |
|---------|--------------|-----|
| **All features end up in “unnamed”** | `ObjectNameAttribute` δεν ταιριάζει με καμία ιδιότητα στο GeoJSON | Επαληθεύστε το ακριβές όνομα της ιδιότητας (διάκριση πεζών‑κεφαλαίων) και ενημερώστε την επιλογή |
| **Output file is empty** | Λανθασμένη διαδρομή αρχείου ή έλλειψη δικαιωμάτων ανάγνωσης | Χρησιμοποιήστε απόλυτες διαδρομές ή βεβαιωθείτε ότι η εφαρμογή έχει πρόσβαση στο σύστημα αρχείων |
| **Conversion throws `NotSupportedException`** | Προσπάθεια μετατροπής GeoJSON με μη υποστηριζόμενους τύπους γεωμετρίας (π.χ., GeometryCollection) | Απλοποιήστε τα πηγαία δεδομένα ή αναβαθμίστε στην πιο πρόσφατη έκδοση του Aspose.GIS |

## Καλές πρακτικές μετατροπής GeoJSON σε C#

- **Επικυρώστε το πηγαίο GeoJSON** πριν τη μετατροπή για να εντοπίσετε νωρίς ελλιπείς ιδιότητες.  
- **Χρησιμοποιήστε το `Path.Combine`** για διαδρομές αρχείων ώστε να αποφύγετε προβλήματα διαχωριστών ειδικών για πλατφόρμα.  
- **Τυλίξτε την κλήση μετατροπής σε μπλοκ try‑catch** για να διαχειρίζεστε τα σφάλματα I/O με χάρη.  
- **Καταγράψτε τις εμφανίσεις του `DefaultObjectName`**· μπορούν να υποδεικνύουν προβλήματα ποιότητας δεδομένων που ίσως θέλετε να διορθώσετε στο upstream.  

## Συχνές ερωτήσεις

**Q: Μπορώ να ομαδοποιήσω χαρακτηριστικά βάσει πολλαπλών ιδιοτήτων;**  
A: Ναι, μπορείτε να συνδυάσετε πολλά πεδία σε μια εικονική ιδιότητα ή να εκτελέσετε πολλαπλές μετατροπές με διαφορετικές τιμές `ObjectNameAttribute`.

**Q: Είναι το Aspose.GIS συμβατό με ASP.NET Core;**  
A: Απόλυτα – η βιβλιοθήκη λειτουργεί με ASP.NET Core, .NET 5, .NET 6, και το κλασικό .NET Framework.

**Q: Μπορώ να μετατρέψω άλλες γεωγραφικές μορφές εκτός από GeoJSON;**  
A: Ναι, το Aspose.GIS υποστηρίζει περισσότερες από 30 μορφές εισόδου και εξόδου — συμπεριλαμβανομένων των Shapefile, KML, GML, CSV και DXF για εισαγωγή και εξαγωγή.

**Q: Προσφέρει το Aspose.GIS δωρεάν δοκιμή;**  
A: Ναι, μπορείτε να λάβετε δωρεάν δοκιμή του Aspose.GIS από τη [Aspose.GIS free trial page](https://releases.aspose.com/).

**Q: Πού μπορώ να λάβω υποστήριξη για το Aspose.GIS;**  
A: Μπορείτε να λάβετε υποστήριξη από το φόρουμ της κοινότητας Aspose.GIS [Aspose.GIS community forum](https://forum.aspose.com/c/gis/33).

## Συμπέρασμα

Τώρα έχετε μια πλήρη, έτοιμη για παραγωγή συνταγή για **convert geojson to topojson** με ομαδοποίηση χαρακτηριστικών χρησιμοποιώντας το Aspose.GIS for .NET. Ορίζοντας το `ObjectNameAttribute`, ελέγχετε πώς οργανώνονται τα χαρακτηριστικά, κάτι που απλοποιεί το στυλ και την αλληλεπίδραση σε χάρτες ιστού. Μη διστάσετε να εξερευνήσετε άλλους οδηγούς, να πειραματιστείτε με διαφορετικές ιδιότητες ομαδοποίησης και να ενσωματώσετε αυτή τη μετατροπή σε μεγαλύτερους GIS pipelines.

---

**Τελευταία ενημέρωση:** 2026-11-12  
**Δοκιμάστηκε με:** Aspose.GIS for .NET (latest release)  
**Συγγραφέας:** Aspose  

---

## Σχετικά tutorials

- [Πώς να μετατρέψετε GeoJSON σε TopoJSON με Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Πώς να μετατρέψετε GeoJSON σε TopoJSON με συγκεκριμένο όνομα αντικειμένου](/gis/net/geo-data-conversion/convert-geojson-to-topojson-with-specific-object-name/)
- [Αποκάλυψη χαρακτηριστικών TopoJSON με Aspose.GIS για .NET](/gis/net/layer-management/access-features-in-topojson/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}