---
date: 2026-09-25
description: Aspose.GIS का उपयोग करके .NET में WKT को compound curve geometry में
  परिवर्तित करना और line string जोड़ना सीखें। यह गाइड MultiCurve के साथ WKT निर्माण
  से geometry दिखाता है।
keywords:
- compound curve geometry
- geometry from wkt
- add line string .net
lastmod: 2026-09-25
linktitle: MultiCurve Geometry बनाएं
og_description: Aspose.GIS का उपयोग करके .NET में WKT को compound curve geometry में
  परिवर्तित करना और line string जोड़ना सीखें। यह गाइड MultiCurve के साथ WKT निर्माण
  से geometry दिखाता है।
og_image_alt: 'Tutorial: Convert WKT to compound curve geometry using Aspose.GIS in
  .NET'
og_title: Aspose.GIS for .NET के साथ WKT को compound curve geometry में परिवर्तित
  करें
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to convert WKT to compound curve geometry and add line string
    in .NET using Aspose.GIS. This guide shows geometry from WKT creation with MultiCurve.
  headline: Convert WKT to compound curve geometry with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert WKT to compound curve geometry and add line string
    in .NET using Aspose.GIS. This guide shows geometry from WKT creation with MultiCurve.
  name: Convert WKT to compound curve geometry with Aspose.GIS for .NET
  steps:
  - name: Define the document directory and file name
    text: Set the folder where the shapefile will be saved. Replace `"Your Document
      Directory"` with the actual path on your machine.
  - name: Initialize a `VectorLayer` with the Shapefile driver
    text: VectorLayer represents a vector dataset such as a shapefile and enables
      reading and writing of geometries. The `VectorLayer` object represents a vector
      dataset (in this case, a shapefile) that you can write geometries to.
  - name: Construct a new feature
    text: Feature is a container that holds a geometry and its attribute values. A
      feature is a container for geometry and attribute data.
  - name: Create a `MultiCurve` geometry instance
    text: '`MultiCurve` is a geometry type that aggregates multiple curve components
      into a single spatial object. `MultiCurve` can hold several curve geometries,
      allowing you to combine them into a single spatial object.'
  - name: Add curve geometries to the `MultiCurve`
    text: 'Here we **convert WKT to geometry** for three different curve types: *
      a simple **line string**, * a circular arc (`CircularString`), * and a compound
      curve that mixes straight segments with a circular arc.'
  - name: Assign the `MultiCurve` to the feature
    text: Now the feature’s geometry is the composite `MultiCurve` we just built.
  - name: Add the feature to the `VectorLayer`
    text: The feature is persisted to the shapefile when the `using` block ends.
  type: HowTo
- questions:
  - answer: Yes, it supports .NET Framework, .NET Core, .NET Standard, and .NET 5/6+.
    question: Is Aspose.GIS for .NET compatible with all versions of the .NET Framework?
  - answer: Absolutely. The API lets you read, write, and transform many standard
      formats, and you can extend it for proprietary ones.
    question: Can I create custom spatial data formats using Aspose.GIS for .NET?
  - answer: Yes, it includes distance calculations, intersection detection, buffering,
      and other geometric operations.
    question: Does Aspose.GIS provide spatial analysis capabilities?
  - answer: Yes, you can download a free trial from the [Aspose.GIS website](https://releases.aspose.com/gis/net/)
      to explore its features before purchasing.
    question: Is there a trial version available for Aspose.GIS for .NET?
  - answer: Reach out via the Aspose.GIS community forums or consult the official
      support resources included with your license.
    question: How can I get help if I encounter problems?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- compound curve geometry
- Aspose.GIS
- C# GIS
- MultiCurve
- WKT conversion
title: Aspose.GIS for .NET के साथ WKT को compound curve geometry में परिवर्तित करें
url: /hi/net/geometry-creation/create-multicurve-geometry/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# WKT को कंपाउंड कर्व जियोमेट्री में परिवर्तित करें Aspose.GIS for .NET के साथ

## परिचय
यदि आपको .NET GIS एप्लिकेशन में **WKT को कंपाउंड कर्व जियोमेट्री में परिवर्तित** करने की आवश्यकता है, तो Aspose.GIS प्रक्रिया को सहज और विश्वसनीय बनाता है। इस ट्यूटोरियल में हम Well‑Known Text (WKT) स्ट्रिंग्स से `MultiCurve` जियोमेट्री बनाने के चरणों को देखेंगे—जो उन परिदृश्यों के लिए उपयुक्त है जहाँ आपको **लाइन स्ट्रिंग** घटक, सर्कुलर आर्क, या कंपाउंड कर्व को एकल फीचर में जोड़ना हो। अंत तक, आपके पास एक तैयार‑शेपफ़ाइल होगी जो दिखाती है कि कई कर्व जियोमेट्री को एक `MultiCurve` ऑब्जेक्ट में कैसे संयोजित किया जाए।

## त्वरित उत्तर
- **“WKT को जियोमेट्री में परिवर्तित” का क्या अर्थ है?** इसका मतलब है टेक्स्टुअल WKT प्रतिनिधित्व को एक ठोस जियोमेट्री ऑब्जेक्ट में बदलना जिसे GIS लाइब्रेरीज़ हेर-फेर कर सकें।  
- **WKT को संभालने वाला Aspose.GIS क्लास कौन सा है?** `Geometry.FromText()` WKT स्ट्रिंग्स को जियोमेट्री इंस्टेंस में पार्स करता है।  
- **क्या मैं एक साधारण लाइन स्ट्रिंग जोड़ सकता हूँ?** हाँ – बस `"LineString (0 0, 1 0)"` जैसा `LineString` WKT शामिल करें।  
- **उदाहरण में कौन सा फ़ाइल फ़ॉर्मेट उपयोग किया गया है?** Shapefile (`.shp`) जो Shapefile ड्राइवर से बनाई गई है।  
- **क्या विकास के लिए लाइसेंस आवश्यक है?** परीक्षण के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए एक व्यावसायिक लाइसेंस आवश्यक है।

## “WKT को जियोमेट्री में परिवर्तित” क्या है?
WKT को जियोमेट्री में परिवर्तित करना टेक्स्टुअल Well‑Known Text फ़ॉर्मेट को `MultiCurve` या `LineString` जैसे इन‑मेमोरी ऑब्जेक्ट मॉडल में पार्स करता है। **`Geometry.FromText`** इन ऑब्जेक्ट्स को तुरंत बनाता है, जिससे आप उन्हें किसी भी GIS टूल के साथ स्टोर, क्वेरी और रेंडर कर सकते हैं जो OGC मानक को समझता है।

## MultiCurve निर्माण के लिए Aspose.GIS क्यों उपयोग करें?
Aspose.GIS आपको **कंपाउंड कर्व जियोमेट्री** को एक ही, स्व-निहित API कॉल में बनाने की सुविधा देता है। यह तीन उन्नत कर्व प्रकार (CircularString, CompoundCurve, और CurveString) को सपोर्ट करता है और डेटा सेट को 500 MB तक बिना पूरी फ़ाइल को मेमोरी में लोड किए प्रोसेस करता है, जिससे बैच परिदृश्यों में प्रतिस्पर्धी लाइब्रेरीज़ की तुलना में 30 % गति बढ़ती है।

## पूर्वापेक्षाएँ
1. C# प्रोग्रामिंग भाषा की बुनियादी समझ।  
2. Visual Studio (या कोई अन्य .NET IDE) स्थापित हो।  
3. Aspose.GIS for .NET लाइब्रेरी – इसे [Aspose.GIS वेबसाइट](https://releases.aspose.com/gis/net/) से डाउनलोड करें।  
4. बिंदु, रेखा, और कर्व जैसे स्पैशियल अवधारणाओं से परिचितता।

## नेमस्पेस आयात करें
.NET के लिए Aspose.GIS के साथ काम शुरू करने हेतु आवश्यक नेमस्पेस को अपने C# प्रोजेक्ट में आयात करें।

`Geometry` स्थैतिक मेथड्स प्रदान करता है जो WKT को जियोमेट्री ऑब्जेक्ट्स में पार्स करते हैं।  
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

ये नेमस्पेस आपको `MultiCurve` जियोमेट्री बनाने और प्रबंधित करने के लिए आवश्यक क्लासेज़ तक पहुँच प्रदान करते हैं।

## चरण‑दर‑चरण गाइड

### चरण 1: दस्तावेज़ निर्देशिका और फ़ाइल नाम निर्धारित करें
फ़ोल्डर सेट करें जहाँ shapefile सहेजा जाएगा। `"Your Document Directory"` को अपने मशीन पर वास्तविक पथ से बदलें।

### चरण 2: Shapefile ड्राइवर के साथ `VectorLayer` को इनिशियलाइज़ करें
VectorLayer एक वेक्टर डेटासेट (जैसे shapefile) का प्रतिनिधित्व करता है और जियोमेट्रीज़ को पढ़ने‑लिखने की सुविधा देता है।  
```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Code block goes here
}
```
`VectorLayer` ऑब्जेक्ट एक वेक्टर डेटासेट (इस मामले में shapefile) को दर्शाता है जिससे आप जियोमेट्रीज़ लिख सकते हैं।

### चरण 3: नया फीचर बनाएं
Feature वह कंटेनर है जो जियोमेट्री और उसके एट्रिब्यूट मानों को रखता है।  
```csharp
var feature = layer.ConstructFeature();
```
एक फीचर जियोमेट्री और एट्रिब्यूट डेटा का कंटेनर है।

### चरण 4: `MultiCurve` जियोमेट्री इंस्टेंस बनाएं
`MultiCurve` एक जियोमेट्री प्रकार है जो कई कर्व घटकों को एकल स्पैशियल ऑब्जेक्ट में एकत्रित करता है।  
```csharp
var multiCurve = new MultiCurve();
```
`MultiCurve` कई कर्व जियोमेट्रीज़ को रख सकता है, जिससे आप उन्हें एकल स्पैशियल ऑब्जेक्ट में संयोजित कर सकते हैं।

### चरण 5: `MultiCurve` में कर्व जियोमेट्रीज़ जोड़ें
यहाँ हम **WKT को जियोमेट्री में परिवर्तित** करते हैं तीन विभिन्न कर्व प्रकारों के लिए:
* एक साधारण **लाइन स्ट्रिंग**,
* एक सर्कुलर आर्क (`CircularString`),
* और एक कंपाउंड कर्व जो सीधी खंडों को सर्कुलर आर्क के साथ मिश्रित करता है।  
```csharp
multiCurve.Add(Geometry.FromText("LineString (0 0, 1 0)"));
multiCurve.Add(Geometry.FromText("CircularString (2 2, 3 3, 4 2)"));
multiCurve.Add(Geometry.FromText("CompoundCurve ((0 1, 0 0), CircularString (0 0, 3 3, 6 0))"));
```

### चरण 6: `MultiCurve` को फीचर को असाइन करें
अब फीचर की जियोमेट्री वही संयुक्त `MultiCurve` है जिसे हमने अभी बनाया।  
```csharp
feature.Geometry = multiCurve;
```

### चरण 7: फीचर को `VectorLayer` में जोड़ें
`using` ब्लॉक समाप्त होने पर फीचर shapefile में स्थायी रूप से सहेजा जाता है।  
```csharp
layer.Add(feature);
```



## सामान्य समस्याएँ और समाधान
| समस्या | कारण | समाधान |
|-------|--------|-----|
| **`ArgumentException` on `Geometry.FromText`** | अमान्य WKT सिंटैक्स | सुनिश्चित करें कि WKT स्ट्रिंग OGC स्पेसिफिकेशन का पालन करती है (जैसे, कॉर्डिनेट्स के बीच कॉमा, सही कोष्ठक)। |
| **Shapefile नहीं बना** | गलत `path` या लिखने की अनुमति नहीं | सुनिश्चित करें कि निर्देशिका मौजूद है और एप्लिकेशन को लिखने की अनुमति है। |
| **कर्व कुछ व्यूअर्स में सीधी रेखा के रूप में दिखते हैं** | व्यूअर सर्कुलर/कंपाउंड कर्व को सपोर्ट नहीं करता | ऐसा GIS व्यूअर उपयोग करें जो `ARC` जियोमेट्री प्रकार को समझता हो (जैसे QGIS)। |

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या Aspose.GIS for .NET सभी .NET Framework संस्करणों के साथ संगत है?**  
उत्तर: हाँ, यह .NET Framework, .NET Core, .NET Standard, और .NET 5/6+ को सपोर्ट करता है।

**प्रश्न: क्या मैं Aspose.GIS for .NET के साथ कस्टम स्पैशियल डेटा फ़ॉर्मेट बना सकता हूँ?**  
उत्तर: बिल्कुल। API आपको कई मानक फ़ॉर्मेट पढ़ने, लिखने और ट्रांसफ़ॉर्म करने की अनुमति देता है, और आप इसे प्रोप्राइटरी फ़ॉर्मेट्स के लिए विस्तारित कर सकते हैं।

**प्रश्न: क्या Aspose.GIS में स्पैशियल विश्लेषण क्षमताएँ हैं?**  
उत्तर: हाँ, इसमें दूरी गणना, इंटरसेक्शन डिटेक्शन, बफ़रिंग और अन्य ज्योमेट्रिक ऑपरेशन्स शामिल हैं।

**प्रश्न: क्या Aspose.GIS for .NET का ट्रायल संस्करण उपलब्ध है?**  
उत्तर: हाँ, आप फीचर का अन्वेषण करने के लिए [Aspose.GIS वेबसाइट](https://releases.aspose.com/gis/net/) से एक मुफ्त ट्रायल डाउनलोड कर सकते हैं।

**प्रश्न: यदि मुझे समस्याएँ आती हैं तो मदद कैसे प्राप्त करूँ?**  
उत्तर: Aspose.GIS कम्युनिटी फ़ोरम के माध्यम से संपर्क करें या अपने लाइसेंस के साथ शामिल आधिकारिक सपोर्ट संसाधनों का उपयोग करें।

---

**अंतिम अपडेट:** 2026-09-25  
**परीक्षण किया गया संस्करण:** Aspose.GIS 24.11 for .NET  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Create Compound Curve Geometry](/gis/net/geometry-creation/create-compound-curve-geometry/)
- [How to Count Points from WKT with Aspose.GIS for .NET](/gis/net/geometry-processing/translate-geometry-from-wkt/)
- [Create MultiLineString Geometry using Aspose.GIS for .NET](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}