---
date: 2026-06-10
description: Aspose.GIS for .NET के साथ ExtendedPostGis variant का उपयोग करके .NET
  में linestring geometry कैसे बनाएं और geometry को WKB में परिवर्तित करें, यह जानें।
keywords:
- create linestring geometry .net
- WKB variant Aspose GIS
- EWKB conversion .NET
linktitle: अनुवाद में WKB Variant निर्दिष्ट करें
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  headline: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  name: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  steps:
  - name: Creating a Geometry Object
    text: The `Geometry` class is Aspose.GIS's base type that represents any spatial
      object in memory. Linestring represents a series of connected points forming
      a linear geometry. In this step we instantiate a `Linestring` with a collection
      of coordinate pairs that model a simple road segment.
  - name: Generating WKB Representation
    text: '`WkbVariant.ExtendedPostGis` is the enum value that tells Aspose.GIS to
      include SRID in the output binary. Here we call the `AsBinary` method, passing
      the EWKB variant, which returns a `byte[]` containing the full binary representation.'
  - name: Writing to File
    text: '`File.WriteAllBytes` writes the binary array to disk. The resulting file
      (`EWkbFile.ewkb`) can be imported directly into a PostGIS table using the `ST_GeomFromEWKB`
      function.'
  type: HowTo
- questions:
  - answer: Yes, the `ExtendedPostGis` variant produces EWKB that includes SRID, which
      PostGIS reads directly via `ST_GeomFromEWKB`.
    question: Can I use the EWKB file with PostGIS?
  - answer: Absolutely. Use `Geometry.FromBinary(byteArray)` to reconstruct the geometry
      from its binary form.
    question: Is it possible to read a WKB file back into a geometry object?
  - answer: Yes, Aspose.GIS handles points, linestrings, polygons, multipolygons,
      and many more spatial types.
    question: Does the library support other geometry types like polygons?
  - answer: Set the `SRID` property on the geometry object before calling `AsBinary`,
      e.g., `linestring.SRID = 4326;`.
    question: How do I specify a different SRID when creating the geometry?
  - answer: Yes, the same API works across .NET Framework, .NET Core, and .NET 5/6
      without modification.
    question: Will this code work on .NET Core?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET में Linestring Geometry और WKB Variant बनाएं
url: /hi/net/geometry-processing/specify-wkb-variant-on-translation/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET में Linestring ज्योमेट्री और WKB वैरिएंट बनाएं

## परिचय
यदि आपको **.NET में linestring geometry बनानी है** और फिर उस ज्योमेट्री को बाइनरी रूप में परिवर्तित करना है, तो Aspose.GIS for .NET एक साफ़, उच्च‑प्रदर्शन API प्रदान करता है जो .NET Framework, .NET Core, और .NET 5/6+ के साथ काम करता है। इस ट्यूटोरियल में हम हर चरण को विस्तार से देखेंगे—नेमस्पेस इम्पोर्ट करने से लेकर EWKB फ़ाइल लिखने तक—ताकि आप SRID जानकारी को संरक्षित रख सकें और GIS डेटा को PostgreSQL/PostGIS या किसी भी बाइनरी‑आधारित वर्कफ़्लो में बिना किसी परेशानी के इंटीग्रेट कर सकें।

## त्वरित उत्तर
- **WKB का मतलब क्या है?** Well‑Known Binary, ज्योमेट्रिक ऑब्जेक्ट्स का एक कॉम्पैक्ट बाइनरी प्रतिनिधित्व।  
- **कौन सा WKB वैरिएंट SRID संग्रहीत करता है?** `ExtendedPostGis` (EWKB) वैरिएंट बाइनरी में सीधे SRID एम्बेड करता है।  
- **क्या मुझे लाइसेंस चाहिए?** प्रोडक्शन डिप्लॉयमेंट के लिए एक टेम्पररी या फुल Aspose.GIS लाइसेंस आवश्यक है।  
- **कौन से .NET संस्करण समर्थित हैं?** .NET Framework 4.5+, .NET Core 3.1+, और .NET 5/6+।  
- **इम्प्लीमेंटेशन में कितना समय लगेगा?** बेसिक उदाहरण के लिए आमतौर पर 10 मिनट से कम।

## Linestring ज्योमेट्री क्या है?
Linestring ज्योमेट्री एक सरल आकार है जो बिंदुओं की क्रमबद्ध सूची से बना होता है, जहाँ प्रत्येक बिंदु को सीधी रेखा खंडों द्वारा जोड़ा जाता है। यह सड़कों, पाइपलाइनों, या नदी के मार्ग जैसी रैखिक विशेषताओं का प्रतिनिधित्व करने के लिए सबसे उपयुक्त रूप है।

## WKB वैरिएंट क्यों निर्दिष्ट करें?
सही WKB वैरिएंट का उपयोग करने से यह सुनिश्चित होता है कि महत्वपूर्ण मेटाडाटा—विशेषकर Spatial Reference System Identifier (SRID)—आपकी ज्योमेट्री के साथ ही रहता है। `ExtendedPostGis` (EWKB) वैरिएंट बाइनरी पेलोड में SRID संग्रहीत करता है, जिससे PostGIS, Oracle Spatial, या किसी भी SRID‑सचेत बाइनरी की अपेक्षा करने वाले सिस्टम के साथ सहज राउंड‑ट्रिपिंग संभव होती है।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

### Aspose.GIS for .NET की इंस्टॉलेशन
1. Aspose.GIS डाउनलोड करें: नवीनतम पैकेज प्राप्त करने के लिए [डाउनलोड लिंक](https://releases.aspose.com/gis/net/) पर जाएँ।  
2. अपने प्रोजेक्ट में NuGet पैकेज जोड़ें (उदा., `Install-Package Aspose.GIS`)।  

### C# प्रोग्रामिंग से परिचितता
- C# सिंटैक्स और प्रोजेक्ट स्ट्रक्चर की बुनियादी समझ।  
- .NET कंसोल या क्लास‑लाइब्रेरी प्रोजेक्ट चलाने की क्षमता।

## नेमस्पेस इम्पोर्ट करें
`Aspose.GIS` नेमस्पेस आपको सभी ज्योमेट्री‑संबंधित क्लासेज़ तक पहुंच देता है।  

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

ये नेमस्पेस कोर GIS कार्यक्षमता प्रदान करते हैं, जिसमें ज्योमेट्री निर्माण, ट्रांसफ़ॉर्मेशन, और बाइनरी सीरियलाइज़ेशन शामिल हैं।

## Linestring ज्योमेट्री कैसे बनाएं?
Linestring बनाने के लिए, एक `Linestring` ऑब्जेक्ट को बिंदुओं की क्रमबद्ध सूची के साथ इंस्टैंशिएट करें, आवश्यक होने पर उसका SRID सेट करें, और फिर इच्छित WKB वैरिएंट में सीरियलाइज़ करें। प्रक्रिया में तीन चरण शामिल हैं: ज्योमेट्री बनाना, SRID को बनाए रखने के लिए `ExtendedPostGis` वैरिएंट चुनना, और परिणामी बाइट एरे को फ़ाइल में लिखना।

### चरण 1: ज्योमेट्री ऑब्जेक्ट बनाना
`Geometry` क्लास Aspose.GIS की बेस टाइप है जो मेमोरी में किसी भी स्पैशियल ऑब्जेक्ट का प्रतिनिधित्व करती है।  
Linestring बिंदुओं की श्रृंखला को जोड़कर एक रैखिक ज्योमेट्री बनाता है।  

```csharp
IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
```
इस चरण में हम एक `Linestring` को बिंदु युग्मों के संग्रह के साथ इंस्टैंशिएट करते हैं जो एक सरल सड़क खंड को मॉडल करता है।

### चरण 2: WKB प्रतिनिधित्व उत्पन्न करना
`WkbVariant.ExtendedPostGis` वह enum वैल्यू है जो Aspose.GIS को आउटपुट बाइनरी में SRID शामिल करने के लिए बताती है।  

```csharp
byte[] wkb = geometry.AsBinary(WkbVariant.ExtendedPostGis);
```
यहाँ हम `AsBinary` मेथड को EWKB वैरिएंट के साथ कॉल करते हैं, जो एक `byte[]` लौटाता है जिसमें पूर्ण बाइनरी प्रतिनिधित्व होता है।

### चरण 3: फ़ाइल में लिखना
`File.WriteAllBytes` बाइनरी एरे को डिस्क पर लिखता है।  

```csharp
File.WriteAllBytes(Path.Combine("Your Document Directory", "EWkbFile.ewkb"), wkb);
```
परिणामी फ़ाइल (`EWkbFile.ewkb`) को `ST_GeomFromEWKB` फ़ंक्शन का उपयोग करके सीधे PostGIS टेबल में इम्पोर्ट किया जा सकता है।

## सामान्य समस्याएँ और समाधान
| समस्या | कारण | समाधान |
|--------|------|----------|
| **फ़ाइल खाली है** | `Path.Combine` किसी गैर‑मौजूद डायरेक्टरी की ओर इशारा कर रहा है। | सुनिश्चित करें कि लक्ष्य डायरेक्टरी मौजूद है या `Directory.CreateDirectory` से उसे बनाएँ। |
| **गलत SRID** | डिफ़ॉल्ट `WkbVariant.Standard` उपयोग करने से SRID हट जाता है। | जब SRID संरक्षण आवश्यक हो, हमेशा `WkbVariant.ExtendedPostGis` का उपयोग करें। |
| **लाइसेंस अपवाद** | प्रोडक्शन में वैध लाइसेंस के बिना चलाया गया। | प्रोडक्शन वातावरण में कोड चलाने से पहले एक टेम्पररी या फुल लाइसेंस लागू करें। |

## अक्सर पूछे जाने वाले प्रश्न
**प्र: क्या मैं EWKB फ़ाइल को PostGIS के साथ उपयोग कर सकता हूँ?**  
उ: हाँ, `ExtendedPostGis` वैरिएंट EWKB उत्पन्न करता है जिसमें SRID शामिल होता है, जिसे PostGIS सीधे `ST_GeomFromEWKB` के माध्यम से पढ़ता है।  

**प्र: क्या WKB फ़ाइल को वापस ज्योमेट्री ऑब्जेक्ट में पढ़ना संभव है?**  
उ: बिल्कुल। `Geometry.FromBinary(byteArray)` का उपयोग करके आप बाइनरी रूप से ज्योमेट्री को पुनः निर्मित कर सकते हैं।  

**प्र: क्या लाइब्रेरी अन्य ज्योमेट्री प्रकारों जैसे पॉलीगॉन को सपोर्ट करती है?**  
उ: हाँ, Aspose.GIS पॉइंट्स, linestrings, polygons, multipolygons, और कई अन्य स्पैशियल टाइप्स को संभालता है।  

**प्र: ज्योमेट्री बनाते समय अलग SRID कैसे निर्दिष्ट करें?**  
उ: बाइनरी बनाने से पहले ज्योमेट्री ऑब्जेक्ट की `SRID` प्रॉपर्टी सेट करें, जैसे `linestring.SRID = 4326;`।  

**प्र: क्या यह कोड .NET Core पर काम करेगा?**  
उ: हाँ, वही API .NET Framework, .NET Core, और .NET 5/6 पर बिना किसी संशोधन के काम करता है।

---

**अंतिम अपडेट:** 2026-06-10  
**परीक्षित संस्करण:** Aspose.GIS for .NET 23.9 (लेखन समय उपलब्ध नवीनतम)  
**लेखक:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [Aspose.GIS for .NET के साथ Geometry को WKB फ़ॉर्मेट में ट्रांसलेट करना](/gis/net/geometry-processing/translate-geometry-to-wkb/)
- [Aspose.GIS का उपयोग करके ट्रांसलेशन पर WKT वैरिएंट निर्दिष्ट करना](/gis/net/geometry-processing/specify-wkt-variant-on-translation/)
- [Aspose.GIS for .NET के साथ MultiLineString ज्योमेट्री बनाना](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}