---
date: 2026-05-31
description: Aspose.GIS for .NET के साथ ज्यामितियों को लिखते समय सटीकता को सीमित करना
  सीखें, जिससे GeoJSON का आकार घटे और निर्देशांक नियंत्रण बना रहे।
keywords:
- how to limit precision
- reduce geojson size
- Aspose.GIS precision control
linktitle: ज्यामितियों को लिखते समय सटीकता को सीमित करें
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to limit precision when writing geometries with Aspose.GIS
    for .NET, reducing GeoJSON size and keeping coordinate control.
  headline: How to Limit Precision Writing Geometries with Aspose.GIS
  type: TechArticle
- description: Learn how to limit precision when writing geometries with Aspose.GIS
    for .NET, reducing GeoJSON size and keeping coordinate control.
  name: How to Limit Precision Writing Geometries with Aspose.GIS
  steps:
  - name: Define Precision Options
    text: The `GeoJsonOptions` class lets you specify how many fractional digits to
      keep for X/Y and Z coordinates. `PrecisionModel` defines how coordinate values
      are rounded or kept exact during writing.
  - name: Set Output Path
    text: Specify where the resulting GeoJSON file will be saved. `VectorLayer` is
      Aspose.GIS's container for a collection of features that share the same schema;
      it writes to the path you provide using the options set earlier.
  - name: Create and Populate Geometry
    text: Open a new `VectorLayer` with the options defined above, construct a `Point`
      geometry, and add it to the layer. `Point` represents a single coordinate (X,
      Y, optional Z) in a spatial reference system. It is the simplest geometry type
      and is used here to demonstrate precision rounding.
  - name: Read and Verify Precision
    text: Open the file you just created and print the coordinates. You should see
      the X/Y values rounded to three decimal places while the Z value remains exact.
      When you read the file back, Aspose.GIS parses the rounded values directly,
      so the in‑memory `Point` reflects the precision you defined during writ
  type: HowTo
- questions:
  - answer: Yes, it supports **50+** formats—including Shapefile, GeoJSON, KML, GML,
      and CSV—allowing seamless conversion between them.
    question: Is Aspose.GIS for .NET compatible with other GIS formats?
  - answer: Absolutely. A free trial is available from the download page, giving you
      full access to all features for evaluation.
    question: Can I try Aspose.GIS for .NET before purchasing?
  - answer: Temporary evaluation licenses can be generated via the Aspose license
      portal; they are valid for 30 days.
    question: How do I obtain a temporary license for testing?
  - answer: The Aspose.GIS forum and Stack Overflow tag `aspose-gis` are great places
      to ask questions and find community solutions.
    question: Where can I get help if I run into issues?
  - answer: Yes, Aspose.GIS is designed to handle everything from quick prototypes
      to high‑throughput server workloads, processing multi‑gigabyte datasets with
      low memory overhead.
    question: Does the library work for both small scripts and enterprise‑scale applications?
  type: FAQPage
second_title: Aspise.GIS .NET API
title: Aspose.GIS के साथ ज्यामितियों को लिखते समय सटीकता को सीमित करने का तरीका
url: /hi/net/geometry-processing/limit-precision-writing-geometries/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS के साथ जियोमेट्रीज़ लिखते समय सटीकता को सीमित करना

यदि आप .NET GIS एप्लिकेशन में जियोमेट्रीज़ लिखते समय **सटीकता को कैसे सीमित करें** के बारे में सोच रहे हैं, तो Aspose.GIS for .NET एक सरल, उच्च‑प्रदर्शन तरीका प्रदान करता है जिससे आप निर्देशांक राउंडिंग को नियंत्रित कर सकते हैं। इस ट्यूटोरियल में हम पूरी प्रक्रिया को चरण‑दर‑चरण देखेंगे—पर्यावरण सेटअप से लेकर यह सत्यापित करने तक कि आउटपुट आपके द्वारा निर्धारित सटीकता नियमों का पालन करता है।

## त्वरित उत्तर
- **“limit precision” का क्या अर्थ है?** यह एक स्पैशियल फ़ाइल लिखते समय निर्देशांक मानों को परिभाषित संख्या के दशमलव अंकों तक राउंड करता है।  
- **उदाहरण में कौन सा फ़ॉर्मेट उपयोग किया गया है?** GeoJSON, लेकिन वही विकल्प अन्य समर्थित फ़ॉर्मेट्स पर भी लागू होते हैं।  
- **क्या इसे आज़माने के लिए लाइसेंस चाहिए?** विकास और परीक्षण के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए एक व्यावसायिक लाइसेंस आवश्यक है।  
- **कौन से .NET संस्करण समर्थित हैं?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7।  
- **क्या मैं Z‑कोऑर्डिनेट सटीकता को अलग से नियंत्रित कर सकता हूँ?** हाँ—सटीक या राउंडेड मान सेट करने के लिए `ZPrecisionModel` का उपयोग करें।

## जियोमेट्रीज़ लिखते समय सटीकता को कैसे सीमित करें

अपना GeoJSON राइटर `GeoJsonOptions` ऑब्जेक्ट के साथ लोड करें जो वांछित X/Y और Z सटीकता को निर्दिष्ट करता है, फिर जियोमेट्री लिखें और उसे पढ़ें—यह संपूर्ण वर्कफ़्लो दस लाइनों के कोड से कम में फिट हो जाता है और यह सुनिश्चित करता है कि सभी निर्देशांक ठीक उसी तरह राउंड किए जाएँ जैसा आपने परिभाषित किया है।

सटीकता को सीमित करना आवश्यक है जब आपको विभिन्न GIS टूल्स के बीच समान निर्देशांक प्रतिनिधित्व चाहिए, फ़ाइल आकार कम करना हो, या डेटा‑एक्सचेंज मानकों का पालन करना हो। नीचे हम सटीकता विकल्पों को परिभाषित करेंगे, एक जियोमेट्री लिखेंगे, और फिर राउंडिंग की पुष्टि के लिए उसे पढ़ेंगे।

## सटीकता सीमित करना क्या है?

सटीकता सीमित करना वह प्रक्रिया है जिसमें जियोमेट्री को फ़ाइल फ़ॉर्मेट में सहेजने से पहले निर्देशांक मानों के दशमलव भाग को निश्चित संख्या के अंकों तक राउंड किया जाता है। इससे यह सुनिश्चित होता है कि फ़ाइल के प्रत्येक उपभोक्ता को समान संख्यात्मक मान दिखें, जिससे छोटे अंतर जो टोपोलॉजी त्रुटियों का कारण बन सकते हैं, उनसे बचा जा सके।

## सटीकता नियंत्रण के लिए Aspose.GIS क्यों उपयोग करें?

Aspose.GIS **50+** इनपुट और आउटपुट फ़ॉर्मेट्स—जैसे GeoJSON, Shapefile, KML, और GML—को समर्थन देता है और **सैकड़ों हज़ार फीचर्स** वाली फ़ाइलों को पूरी डेटा सेट को मेमोरी में लोड किए बिना प्रोसेस कर सकता है। इसके बिल्ट‑इन प्रिसीजन मॉडल आपको एक ही कॉल में निर्देशांक राउंड करने की सुविधा देते हैं, जिससे मैन्युअल पोस्ट‑प्रोसेसिंग स्क्रिप्ट्स की आवश्यकता समाप्त हो जाती है।

## पूर्वापेक्षाएँ

### 1. डाउनलोड और इंस्टॉलेशन
आधिकारिक साइट से नवीनतम Aspose.GIS for .NET पैकेज प्राप्त करें: [download link](https://releases.aspose.com/gis/net/). इंस्टॉलेशन गाइड का पालन करके अपने प्रोजेक्ट में NuGet पैकेज जोड़ें।

### 2. नेमस्पेस इम्पोर्ट
आवश्यक नेमस्पेस जोड़ें ताकि आप GIS क्लासेज़ और हेल्पर यूटिलिटीज़ तक पहुँच सकें।

## चरण‑दर‑चरण गाइड

### चरण 1: सटीकता विकल्प निर्धारित करें
`GeoJsonOptions` क्लास आपको X/Y और Z निर्देशांक के लिए कितने दशमलव अंकों को रखना है, यह निर्दिष्ट करने की अनुमति देती है।

`PrecisionModel` निर्धारित करता है कि लिखते समय निर्देशांक मान कैसे राउंड किए जाएँगे या सटीक रखे जाएँगे।  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### चरण 2: आउटपुट पाथ सेट करें
निर्दिष्ट करें कि परिणामी GeoJSON फ़ाइल कहाँ सहेजी जाएगी।

`VectorLayer` Aspose.GIS का कंटेनर है जो समान स्कीमा साझा करने वाले फीचर संग्रह को रखता है; यह पहले सेट किए गए विकल्पों का उपयोग करके आपके द्वारा प्रदान किए गए पाथ पर लिखता है।  

```csharp
var options = new GeoJsonOptions
{
    // Limit X and Y coordinates to 3 fractional digits.
    XYPrecisionModel = PrecisionModel.Rounding(3),

    // Write all fractional digits of the Z coordinate.
    ZPrecisionModel = PrecisionModel.Exact
};
```

### चरण 3: जियोमेट्री बनाएं और भरें
ऊपर परिभाषित विकल्पों के साथ एक नया `VectorLayer` खोलें, एक `Point` जियोमेट्री बनाएं, और उसे लेयर में जोड़ें।

`Point` एक स्पैशियल रेफ़रेंस सिस्टम में एकल निर्देशांक (X, Y, वैकल्पिक Z) को दर्शाता है। यह सबसे सरल जियोमेट्री प्रकार है और यहाँ सटीकता राउंडिंग को दर्शाने के लिए उपयोग किया गया है।  

```csharp
var path = "Your Document Directory" + "LimitPrecisionWhenWritingGeometries_out.json";
```

### चरण 4: सटीकता पढ़ें और सत्यापित करें
आपके द्वारा अभी बनाई गई फ़ाइल खोलें और निर्देशांक प्रिंट करें। आपको X/Y मान तीन दशमलव स्थानों तक राउंडेड दिखने चाहिए जबकि Z मान सटीक रहेगा।

जब आप फ़ाइल को फिर से पढ़ते हैं, तो Aspose.GIS सीधे राउंडेड मानों को पार्स करता है, इसलिए मेमोरी में मौजूद `Point` लिखते समय आपने जो सटीकता निर्धारित की थी, उसे दर्शाता है।  

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    var point = new Point();
    point.X = 1.8888888;
    point.Y = 1.00123;
    point.Z = 1.123456789;

    Feature feature = layer.ConstructFeature();
    feature.Geometry = point;
    layer.Add(feature);
}
```

## सामान्य समस्याएँ और सुझाव

- **पाथ त्रुटियाँ:** सुनिश्चित करें कि `path` में डायरेक्टरी मौजूद है या सुरक्षित फ़ाइल पाथ बनाने के लिए `Path.Combine` को `Environment.CurrentDirectory` के साथ उपयोग करें।  
- **सटीकता लागू नहीं हुई:** लेयर बनाते समय `GeoJsonOptions` ऑब्जेक्ट पास किया गया है या नहीं, यह जांचें; अन्यथा डिफ़ॉल्ट सटीकता (पूरा डबल) उपयोग होगी।  
- **बड़ी डेटा सेट:** बल्क ऑपरेशन्स के लिए, एक ही `VectorLayer` इंस्टेंस को पुन: उपयोग करने और फीचर्स को बैच‑ऐड करने पर विचार करें ताकि प्रदर्शन सुधरे।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या Aspose.GIS for .NET अन्य GIS फ़ॉर्मेट्स के साथ संगत है?**  
A: हाँ, यह **50+** फ़ॉर्मेट्स—Shapefile, GeoJSON, KML, GML, और CSV सहित—को समर्थन देता है, जिससे उनके बीच सहज रूपांतरण संभव होता है।

**Q: क्या मैं Aspose.GIS for .NET को खरीदने से पहले आज़मा सकता हूँ?**  
A: बिल्कुल। डाउनलोड पेज से एक मुफ्त ट्रायल उपलब्ध है, जो आपको मूल्यांकन के लिए सभी फीचर्स तक पूर्ण पहुँच देता है।

**Q: परीक्षण के लिए मैं अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूँ?**  
A: अस्थायी मूल्यांकन लाइसेंस Aspose लाइसेंस पोर्टल के माध्यम से उत्पन्न किए जा सकते हैं; वे 30 दिनों के लिए वैध होते हैं।

**Q: यदि मुझे समस्याएँ आती हैं तो मैं मदद कहाँ से प्राप्त कर सकता हूँ?**  
A: Aspose.GIS फ़ोरम और Stack Overflow टैग `aspose-gis` प्रश्न पूछने और समुदाय समाधान खोजने के लिए उत्कृष्ट स्थान हैं।

**Q: क्या लाइब्रेरी छोटे स्क्रिप्ट्स और एंटरप्राइज़‑स्तर के एप्लिकेशन्स दोनों के लिए काम करती है?**  
A: हाँ, Aspose.GIS को तेज़ प्रोटोटाइप से लेकर हाई‑थ्रूपुट सर्वर वर्कलोड तक सब कुछ संभालने के लिए डिज़ाइन किया गया है, जो कम मेमोरी ओवरहेड के साथ मल्टी‑गिगाबाइट डेटा सेट्स को प्रोसेस करता है।

---

**अंतिम अद्यतन:** 2026-05-31  
**परीक्षण किया गया:** Aspose.GIS 24.11 for .NET  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल्स

- [वेक्टर लेयर बनाएं, Aspose.GIS for .NET के साथ सटीकता सीमित करें](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [GeoJSON कैसे कनवर्ट करें – Aspose.GIS for .NET](/gis/net/geo-data-conversion/)
- [Aspose.GIS for .NET के साथ जियोमेट्री कैसे जांचें](/gis/net/geometry-analysis/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.GeoJson))
{
    var point = (IPoint)layer[0].Geometry;

    // Output: 1.889, 1.001, 1.123456789
    Console.WriteLine("{0}, {1}, {2}", point.X, point.Y, point.Z);
}
```

{{< /blocks/products/pf/main-wrap-class >}}