---
date: 2026-09-05
description: Aspose.GIS for .NET का उपयोग करके एक polygon interior ring में hole बनाने
  का तरीका सीखें। यह गाइड आपको दिखाता है कि कैसे एक polygon में hole जोड़ें और डेटा
  के साथ काम करें।
keywords:
- polygon interior ring
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
lastmod: 2026-09-05
linktitle: hole geometry के साथ Polygon बनाएं
og_description: Aspose.GIS for .NET का उपयोग करके एक polygon interior ring में hole
  बनाने का तरीका सीखें। यह गाइड आपको दिखाता है कि कैसे एक polygon में hole जोड़ें
  और डेटा के साथ काम करें।
og_image_alt: Guide showing how to create a polygon interior ring with a hole using
  Aspose.GIS
og_title: Aspose.GIS का उपयोग करके एक polygon interior ring में hole बनाएं
schemas:
- author: Aspose
  dateModified: '2026-09-05'
  description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  headline: Create a polygon interior ring with a hole using Aspose.GIS
  type: TechArticle
- description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  name: Create a polygon interior ring with a hole using Aspose.GIS
  steps:
  - name: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
    text: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
  - name: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
    text: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
  - name: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
    text: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
  - name: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
    text: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
  - name: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
    text: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
  type: HowTo
- questions:
  - answer: It means building a polygon that contains one or more interior rings (holes)
      that are excluded from the area.
    question: What does “create polygon with hole” mean?
  - answer: Aspose.GIS for .NET provides full support for exterior and interior rings.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  - answer: Typically under 10 minutes to implement and test.
    question: How long does it take?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- polygon interior ring
- Aspose.GIS
- geospatial .NET
- create polygon with hole
- GIS development
title: Aspose.GIS का उपयोग करके एक polygon interior ring में hole बनाएं
url: /hi/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS का उपयोग करके एक छेद के साथ बहुभुज आंतरिक रिंग बनाएं

## परिचय
इस ट्यूटोरियल में आप सीखेंगे कि **बहुभुज आंतरिक रिंग बनाना** जो एक छेद रखता है, Aspose.GIS for .NET का उपयोग करके। चाहे आप मैपिंग एप्लिकेशन बना रहे हों, स्पैशियल विश्लेषण कर रहे हों, या GIS सेवाओं के लिए डेटा तैयार कर रहे हों, बहुभुज के भीतर एक छेद एम्बेड करना एक मूलभूत कौशल है। हम पूरे वर्कफ़्लो को चरणबद्ध तरीके से दिखाएंगे—डेवलपमेंट एनवायरनमेंट सेट अप करने से लेकर एक वैध बहुभुज ऑब्जेक्ट जेनरेट करने तक, जिसे किसी भी समर्थित जियोस्पेशियल फ़ॉर्मेट में सहेजा जा सकता है।

## त्वरित उत्तर
- **“create polygon with hole” का क्या अर्थ है?** It means building a polygon that contains one or more interior rings (holes) that are excluded from the area.  
- **कौन सी लाइब्रेरी इसे संभालती है?** Aspose.GIS for .NET provides full support for exterior and interior rings.  
- **क्या मुझे लाइसेंस की आवश्यकता है?** A free trial works for development; a commercial license is required for production.  
- **कौन से .NET संस्करण समर्थित हैं?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **यह करने में कितना समय लगेगा?** Typically under 10 minutes to implement and test.

## Aspose.GIS का उपयोग करके बहुभुज में छेद कैसे जोड़ें
अपने GIS एनवायरनमेंट को लोड करें, एक बाहरी रिंग परिभाषित करें, फिर एक या अधिक आंतरिक रिंग्स संलग्न करें। Aspose.GIS स्वचालित रूप से रिंग्स की दिशा निर्धारित करता है और ज्यामिति को वैध करता है, इसलिए आप उन निर्देशांक पर ध्यान केंद्रित कर सकते हैं जो आवश्यक शून्य को दर्शाते हैं।

## बहुभुज आंतरिक रिंग क्या है?
A **polygon interior ring** एक आंतरिक सीमा है जो बहुभुज की बाहरी आकृति से क्षेत्र घटाती है।  
आप इसे बिंदुओं की एक बंद क्रम परिभाषित करके बनाते हैं जिसे Aspose.GIS एक छेद के रूप में मानता है, जो क्षेत्रफल की गणना या आकृति रेंडर करने पर बाहर रखा जाता है।

## Aspose.GIS का उपयोग करके बहुभुज आंतरिक रिंग क्यों बनाएं?
Aspose.GIS सामान्य 200‑बिंदु बहुभुजों के लिए 5 ms से कम समय में रिंग की दिशा को वैध करता और सुधारता है, जिससे कस्टम वैधता कोड की आवश्यकता समाप्त हो जाती है। यह **30+ geospatial file formats** (Shapefile, GeoJSON, GML, KML, आदि) का समर्थन भी करता है और पूरी फ़ाइल को मेमोरी में लोड किए बिना 10,000 बिंदुओं तक के बहुभुज को प्रोसेस कर सकता है, जिससे आपको गति और स्केलेबिलिटी दोनों मिलती हैं।

## छेद वाले बहुभुजों के वास्तविक‑विश्व परिदृश्य
1. **आंतरिक झील वाला भूमि खंड** – झील को एक छेद के रूप में मॉडल किया जाता है ताकि वह खंड के क्षेत्र में गिना न जाए।  
2. **आंगनों के साथ भवन पदचिह्न** – आंगन को भवन के पदचिह्न से बाहर रखा जाता है।  
3. **बड़े संरक्षण क्षेत्र के भीतर संरक्षित क्षेत्र** – आप अलग लेयर बनाए बिना प्रतिबंधित भागों को बाहर रख सकते हैं।

## पूर्वापेक्षाएँ
Before we begin, make sure you have the following prerequisites:
1. Aspose.GIS for .NET लाइब्रेरी: आप इसे **Aspose.GIS for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)) से डाउनलोड कर सकते हैं।  
2. डेवलपमेंट एनवायरनमेंट: सुनिश्चित करें कि आपके पास Visual Studio या किसी अन्य .NET IDE स्थापित के साथ एक विकास वातावरण सेट अप है।

## नेमस्पेस आयात करें
`Aspose.Gis` नेमस्पेस में सभी जियोमेट्री प्रकार शामिल हैं जिनकी आपको आवश्यकता होगी, जैसे `Polygon`, `LinearRing`, और वैधता के लिए हेल्पर मेथड्स।

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

अब, चलिए Aspose.GIS for .NET का उपयोग करके छेद वाली बहुभुज ज्यामिति बनाते हैं।

## चरण 1: बहुभुज ऑब्जेक्ट बनाएं
`Polygon` Aspose.GIS का जियोमेट्री प्रकार है जो वैकल्पिक आंतरिक रिंग्स के साथ एक प्लेनर बहुभुज का प्रतिनिधित्व करता है। हम एक खाली `Polygon` ऑब्जेक्ट को इंस्टैंशिएट करके शुरू करते हैं, जो बाद में बाहरी और आंतरिक दोनों रिंग्स को रखेगा।

```csharp
Polygon polygon = new Polygon();
```

## चरण 2: बाहरी रिंग परिभाषित करें
`LinearRing` वह क्लास है जो बाहरी और आंतरिक दोनों सीमाओं के लिए उपयोग की जाती है। बाहरी रिंग बहुभुज की बाहरी सीमा को परिभाषित करती है। बंद आकृति बनाने के लिए बिंदुओं को घड़ी की दिशा में जोड़ें।

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## चरण 3: आंतरिक रिंग (छेद) परिभाषित करें
`LinearRing` आंतरिक रिंग्स को भी दर्शाता है। आंतरिक रिंग **छेद** है जो बहुभुज के क्षेत्र से बाहर रखा जाएगा। बिंदुओं को सामान्यतः उल्टी‑घड़ी दिशा में जोड़ा जाता है, लेकिन Aspose.GIS स्वचालित रूप से दिशा को संभालता है।

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## चरण 4: बाहरी रिंग असाइन करें और बहुभुज में आंतरिक रिंग जोड़ें
`AddInteriorRing` मेथड एक या अधिक आंतरिक रिंग्स को `Polygon` से जोड़ता है। इसे `ExteriorRing` प्रॉपर्टी सेट करने के बाद कॉल करें; आप कई छेद जोड़ने के लिए इस कॉल को दोहरा सकते हैं।

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## टिप्स और सर्वोत्तम प्रथाएँ
- **पढ़ने की सुविधा के लिए दिशा महत्वपूर्ण है** – जबकि Aspose.GIS स्वचालित रूप से दिशा को सुधारता है, बाहरी रिंग्स को घड़ी की दिशा में और आंतरिक रिंग्स को उल्टी‑घड़ी दिशा में रखना जियोमेट्री को GIS व्यूअर्स में जांचने में आसान बनाता है।  
- **प्रत्येक रिंग को बंद करें** – हमेशा पहले कोऑर्डिनेट को अंतिम बिंदु के रूप में दोहराएँ; यह एक वैध बंद आकृति सुनिश्चित करता है।  
- **निर्माण के बाद वैधता जांचें** – आप `polygon.IsValid` को कॉल करके सहेजने से पहले जियोमेट्री को OGC मानकों के अनुरूप सुनिश्चित कर सकते हैं।

## सामान्य समस्याएँ और समाधान
| समस्या | कारण | समाधान |
|-------|--------|-----|
| GIS व्यूअर में छेद नहीं दिख रहा है | आंतरिक रिंग की दिशा उल्टी है | बिंदुओं को बाहरी रिंग की विपरीत दिशा (उल्टी‑घड़ी) में जोड़ें। |
| बहुभुज अमान्य त्रुटि | रिंग्स बंद नहीं हैं (पहला ≠ अंतिम बिंदु) | प्रत्येक रिंग में पहला बिंदु को अंतिम बिंदु के रूप में दोहराएँ (जैसा ऊपर दिखाया गया है)। |
| अप्रत्याशित खाली जियोमेट्री | आंतरिक रिंग्स जोड़ने से पहले `ExteriorRing` असाइन करना भूल गए | पहले `polygon.ExteriorRing` सेट करें, फिर `AddInteriorRing` कॉल करें। |

## अक्सर पूछे जाने वाले प्रश्न
### 1. Aspose.GIS क्या है?
Aspose.GIS एक .NET लाइब्रेरी है जो डेवलपर्स को जियोस्पेशियल डेटा के साथ काम करने में सक्षम बनाती है, जिससे वे विभिन्न जियोस्पेशियल फ़ाइल फ़ॉर्मेट को बना, पढ़ और संशोधित कर सकते हैं।

### 2. क्या मैं Aspose.GIS को वाणिज्यिक प्रोजेक्ट्स के लिए उपयोग कर सकता हूँ?
हाँ, आप लाइसेंस खरीदकर Aspose.GIS को व्यक्तिगत और वाणिज्यिक दोनों प्रोजेक्ट्स में उपयोग कर सकते हैं। अधिक विवरण के लिए **Aspose.GIS purchase page**([https://purchase.aspose.com/buy](https://purchase.aspose.com/buy)) देखें।

### 3. क्या Aspose.GIS के लिए मुफ्त ट्रायल उपलब्ध है?
हाँ, आप **Aspose.GIS free trial download page**([https://releases.aspose.com/](https://releases.aspose.com/)) से Aspose.GIS का मुफ्त ट्रायल प्राप्त कर सकते हैं।

### 4. मैं Aspose.GIS के लिए समर्थन कहाँ पा सकता हूँ?
आप Aspose.GIS के लिए समर्थन [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) पर पा सकते हैं।

### 5. मैं Aspose.GIS के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूँ?
आप **Aspose.GIS temporary license page**([https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/)) से Aspose.GIS के लिए अस्थायी लाइसेंस प्राप्त कर सकते हैं।

---

**अंतिम अपडेट:** 2026-09-05  
**परीक्षण किया गया:** Aspose.GIS 24.11 for .NET  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Aspose.GIS for .NET के साथ बहुभुज ज्यामिति कैसे बनाएं](/gis/net/geometry-creation/create-polygon-geometry/)
- [Aspose.GIS के साथ मल्टीपॉलिगन ज्यामिति कैसे बनाएं सीखें](/gis/net/geometry-creation/create-multipolygon-geometry/)
- [Aspose.GIS for .NET के साथ बहुभुज को लाइन में बदलें](/gis/net/geometry-processing/replace-polygons-with-lines/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}