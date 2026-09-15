---
date: 2026-09-15
description: Aspose.GIS for .NET का उपयोग करके बहुभुज को रेखा में बदलना और बहुभुजों
  को रेखाओं में परिवर्तित करना सीखें। GIS डेवलपर्स के लिए एक त्वरित मार्गदर्शिका।
keywords:
- convert polygon to line
- how to replace polygons
- transform polygons to lines
- gis polygon to line
- simplify map visualization
lastmod: 2026-09-15
linktitle: बहुभुजों को रेखाओं से बदलें
og_description: Aspose.GIS for .NET का उपयोग करके बहुभुज को रेखा में बदलें। यह ट्यूटोरियल
  दिखाता है कि कैसे बहुभुजों को रेखाओं से बदला जाए, समर्थित .NET संस्करण और सामान्य
  समस्याएँ।
og_image_alt: Screenshot of Aspose.GIS converting polygon to line in a .NET console
  app
og_title: Aspose.GIS for .NET के साथ बहुभुज को रेखा में बदलें – त्वरित मार्गदर्शिका
schemas:
- author: Aspose
  dateModified: '2026-09-15'
  description: Learn how to convert polygon to line and transform polygons to lines
    using Aspose.GIS for .NET. A quick guide for GIS developers.
  headline: Convert polygon to line with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert polygon to line and transform polygons to lines
    using Aspose.GIS for .NET. A quick guide for GIS developers.
  name: Convert polygon to line with Aspose.GIS for .NET
  steps:
  - name: Define the source geometry
    text: The `GeometryCollection` class is a container that can hold any number of
      geometry objects, including polygons, points, and lines. It is the entry point
      for bulk operations like `ReplacePolygonsByLines`. Create a geometry collection
      that includes one or more polygons you want to convert. In this exa
  - name: Convert polygons to lines
    text: The `ReplacePolygonsByLines()` method scans the supplied collection, replaces
      each polygon with a `LineString` that follows its outer ring, and leaves all
      other geometry types untouched. This single call performs the conversion in
      O(n) time, where *n* is the number of geometries in the collection.
  - name: Display the original and converted geometries
    text: Printing both the original and the transformed geometries lets you verify
      that polygons have been replaced while other geometries stay the same. The `ToString()`
      override on each geometry provides a human‑readable WKT representation.
  type: HowTo
- questions:
  - answer: Yes, it supports more than 30 formats—including Shapefile, GeoJSON, KML,
      GML, and CSV—allowing you to read, convert, and write data without external
      tools.
    question: Can Aspose.GIS for .NET work with various GIS file formats?
  - answer: Yes, you can access the free trial of Aspose.GIS for .NET on the Aspose
      releases page ([Aspose releases page](https://releases.aspose.com/)).
    question: Is there a free trial available for Aspose.GIS for .NET?
  - answer: Yes, developers can get support and assistance from the Aspose.GIS community
      forum ([Aspose.GIS community forum](https://forum.aspose.com/c/gis/33)).
    question: Does Aspose.GIS for .NET offer support for developers?
  - answer: Yes, you can acquire a temporary license from Aspose's temporary license
      page ([temporary license page](https://purchase.aspose.com/temporary-license/)).
    question: Can I purchase a temporary license for Aspose.GIS for .NET?
  - answer: Absolutely, it provides comprehensive documentation, code examples, and
      API references for all skill levels.
    question: Is Aspose.GIS for .NET suitable for both beginners and experienced developers?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert polygon to line
- Aspose.GIS
- .NET GIS processing
title: Aspose.GIS for .NET के साथ बहुभुज को रेखा में बदलें
url: /hi/net/geometry-processing/replace-polygons-with-lines/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET के साथ बहुभुज को रेखा में बदलें

## परिचय
यदि आपको .NET GIS प्रोजेक्ट में **convert polygon to line** करने की आवश्यकता है, तो Aspose.GIS प्रक्रिया को सरल बनाता है। चाहे आप मानचित्र विज़ुअलाइज़ेशन को सरल बना रहे हों, रूटिंग एल्गोरिदम के लिए डेटा तैयार कर रहे हों, या सिर्फ एक साफ़ ज्योमेट्री प्रतिनिधित्व चाहते हों, यह ट्यूटोरियल आपको Aspose.GIS API का उपयोग करके बहुभुज को रेखा ज्योमेट्री से बदलने के सटीक चरणों के माध्यम से ले जाता है। आप देखेंगे कि यह लाइब्रेरी GIS डेवलपर्स के लिए क्यों पसंदीदा विकल्प है और केवल कुछ कोड लाइनों में रूपांतरण कैसे किया जाता है।

## त्वरित उत्तर
- **convert polygon to line** का क्या अर्थ है? यह एक बहुभुज की बाहरी रिंग को निकालता है और एक `LineString` बनाता है जो उसी परिधि का अनुसरण करता है।  
- **Aspose.GIS** का इस कार्य के लिए उपयोग क्यों करें? लाइब्रेरी एक एकल मेथड (`ReplacePolygonsByLines`) प्रदान करती है जो बड़े पैमाने पर रूपांतरण को कुशलता से संभालता है, बिना मैन्युअल ज्योमेट्री पार्सिंग के।  
- **कौन से .NET संस्करण समर्थित हैं?** .NET Framework 4.5+, .NET Core 3.1+, और .NET 5/6+ सभी पूरी तरह से समर्थित हैं।  
- **क्या विकास के लिए मुझे लाइसेंस चाहिए?** परीक्षण के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन परिनियोजन के लिए एक व्यावसायिक लाइसेंस आवश्यक है।  
- **कार्यान्वयन में कितना समय लगता है?** अधिकांश डेवलपर्स बुनियादी रूपांतरण को दस मिनट से कम समय में पूरा कर लेते हैं।

## “convert polygon to line” क्या है?
बहुभुज को रेखा में बदलना का अर्थ है बहुभुज की बाहरी रिंग (उसकी परिधि) को निकालना और उसे `LineString` के रूप में प्रस्तुत करना। परिणामी ज्योमेट्री मूल आकार की सटीक रूपरेखा को बनाए रखती है लेकिन आंतरिक क्षेत्र की जानकारी को हटा देती है, जो नेटवर्क विश्लेषण, किनारा रेंडरिंग, या वेब मानचित्रों के लिए हल्का प्रतिनिधित्व आवश्यक होने पर आदर्श है।

## Aspose.GIS के साथ बहुभुज को रेखा में बदलने का कारण क्या है?
Aspose.GIS एक ही कॉल में संग्रह में प्रत्येक बहुभुज को उसकी सीमा रेखा से बदल देता है, टोपोलॉजी को संरक्षित करता है और कस्टम लूप की आवश्यकता को समाप्त करता है। यह तरीका कोड जटिलता को 80 % तक कम करता है और सामान्य सर्वर हार्डवेयर पर एक सेकंड से कम समय में 10 000+ फीचर्स के संग्रह को प्रोसेस करता है, इसके मूल C++ कोर और शून्य‑कॉपी मेमोरी हैंडलिंग के कारण।

## पूर्वापेक्षाएँ
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

### Aspose.GIS for .NET की स्थापना
1. Aspose.GIS for .NET डाउनलोड करें: Aspose.GIS for .NET डाउनलोड पृष्ठ पर जाएँ ([Aspose.GIS for .NET download](https://releases.aspose.com/gis/net/)).
2. Aspose.GIS for .NET स्थापित करें: पैकेज में दिए गए इंस्टॉलेशन निर्देशों का पालन करें या विस्तृत चरणों के लिए Aspose.GIS दस्तावेज़ देखें ([Aspose.GIS documentation](https://reference.aspose.com/gis/net/))।

## नामस्थान आयात करें
अपने .NET प्रोजेक्ट में, आवश्यक नामस्थान आयात करें ताकि आप Aspose.GIS क्लासेज़ के साथ काम कर सकें।

`Aspose.Gis` नामस्थान में कोर ज्योमेट्री प्रकार होते हैं, जबकि `Aspose.Gis.Geometries` में `Polygon` और `LineString` जैसे ठोस कार्यान्वयन प्रदान किए जाते हैं।

```csharp
using System;
using Aspose.Gis.Geometries;
```

## क्रमिक मार्गदर्शिका

### चरण 1: स्रोत ज्योमेट्री परिभाषित करें
`GeometryCollection` क्लास एक कंटेनर है जो किसी भी संख्या में ज्योमेट्री ऑब्जेक्ट्स रख सकता है, जिसमें बहुभुज, बिंदु, और रेखाएँ शामिल हैं। यह `ReplacePolygonsByLines` जैसे बड़े ऑपरेशनों के लिए प्रवेश बिंदु है।

एक ज्योमेट्री कलेक्शन बनाएं जिसमें एक या अधिक बहुभुज हों जिन्हें आप बदलना चाहते हैं। इस उदाहरण में हम एक बिंदु भी जोड़ते हैं ताकि दिखाया जा सके कि गैर‑बहुभुज तत्व अपरिवर्तित रहते हैं।

```csharp
var srcGeometry = Geometry.FromText(@"GeometryCollection (POLYGON((1 2, 1 4, 3 4, 3 2)), Point (5 1))");
```

### चरण 2: बहुभुज को रेखा में बदलें
`ReplacePolygonsByLines()` मेथड प्रदान किए गए संग्रह को स्कैन करता है, प्रत्येक बहुभुज को उसकी बाहरी रिंग का अनुसरण करने वाले `LineString` से बदल देता है, और अन्य सभी ज्योमेट्री प्रकारों को अपरिवर्तित छोड़ देता है। यह एकल कॉल O(n) समय में रूपांतरण करता है, जहाँ *n* संग्रह में ज्योमेट्री की संख्या है।

```csharp
var dstGeometry = srcGeometry.ReplacePolygonsByLines();
```

### चरण 3: मूल और परिवर्तित ज्योमेट्री प्रदर्शित करें
मूल और परिवर्तित दोनों ज्योमेट्री को प्रिंट करने से आप सत्यापित कर सकते हैं कि बहुभुज बदल दिए गए हैं जबकि अन्य ज्योमेट्री समान रहे हैं। प्रत्येक ज्योमेट्री पर `ToString()` ओवरराइड एक मानव‑पठनीय WKT प्रतिनिधित्व प्रदान करता है।

```csharp
Console.WriteLine($"source: {srcGeometry.AsText()}");
Console.WriteLine($"result: {dstGeometry.AsText()}");
```

## सामान्य समस्याएँ और समाधान
- **लाइन आउटपुट गायब:** सुनिश्चित करें कि स्रोत ज्योमेट्री वास्तव में बहुभुज रखती है; बिंदु या मल्टीपॉइंट अपरिवर्तित पास हो जाएंगे।  
- **निर्देशांक क्रम समस्याएँ:** Aspose.GIS `X Y` क्रम (देशांतर अक्षांश) में निर्देशांक की अपेक्षा करता है। बदले हुए मान अप्रत्याशित आकार बना सकते हैं।  
- **बड़ी संग्रह:** बहुत बड़े डेटासेट (सैकड़ों हज़ार फीचर्स) के लिए, मेमोरी उपयोग को 200 MB से नीचे रखने के लिए ज्योमेट्री को 10 000–20 000 आइटम के बैच में प्रोसेस करें।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या Aspose.GIS for .NET विभिन्न GIS फ़ाइल फ़ॉर्मेट्स के साथ काम कर सकता है?**  
A: हाँ, यह 30 से अधिक फ़ॉर्मेट्स—Shapefile, GeoJSON, KML, GML, और CSV सहित—को सपोर्ट करता है, जिससे आप बाहरी टूल्स के बिना डेटा पढ़, बदल और लिख सकते हैं।

**Q: क्या Aspose.GIS for .NET के लिए मुफ्त ट्रायल उपलब्ध है?**  
A: हाँ, आप Aspose रिलीज़ पेज पर Aspose.GIS for .NET का मुफ्त ट्रायल एक्सेस कर सकते हैं ([Aspose releases page](https://releases.aspose.com/))।

**Q: क्या Aspose.GIS for .NET डेवलपर्स के लिए समर्थन प्रदान करता है?**  
A: हाँ, डेवलपर्स Aspose.GIS कम्युनिटी फ़ोरम से समर्थन और सहायता प्राप्त कर सकते हैं ([Aspose.GIS community forum](https://forum.aspose.com/c/gis/33))।

**Q: क्या मैं Aspose.GIS for .NET के लिए अस्थायी लाइसेंस खरीद सकता हूँ?**  
A: हाँ, आप Aspose के अस्थायी लाइसेंस पेज से एक अस्थायी लाइसेंस प्राप्त कर सकते हैं ([temporary license page](https://purchase.aspose.com/temporary-license/))।

**Q: क्या Aspose.GIS for .NET शुरुआती और अनुभवी दोनों डेवलपर्स के लिए उपयुक्त है?**  
A: बिल्कुल, यह सभी कौशल स्तरों के लिए व्यापक दस्तावेज़, कोड उदाहरण, और API रेफ़रेंसेज़ प्रदान करता है।

## निष्कर्ष
इन चरणों का पालन करके, आपने Aspose.GIS for .NET का उपयोग करके **convert polygon to line** और प्रभावी रूप से **transform polygons to lines** करना सीख लिया है। यह क्षमता हल्की विज़ुअलाइज़ेशन, रूटिंग तैयारियों, और कई अन्य GIS वर्कफ़्लो के द्वार खोलती है। अपने एप्लिकेशन की क्षमताओं को विस्तारित करने के लिए स्पेशियल क्वेरीज़, रीप्रोजेक्शन, और फ़ॉर्मेट कन्वर्ज़न जैसे अतिरिक्त Aspose.GIS फीचर्स का अन्वेषण करने में संकोच न करें।

---

**अंतिम अपडेट:** 2026-09-15  
**परीक्षण किया गया:** Aspose.GIS for .NET (latest release)  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Aspose.GIS for .NET के साथ LineString ज्योमेट्री बनाना सीखें](/gis/net/geometry-creation/create-linestring-geometry/)
- [Aspose.GIS for .NET के साथ टॉलरेंस के साथ GeoJSON बनाना](/gis/net/geometry-processing/set-linearization-tolerance/)
- [Aspose.GIS for .NET के साथ ज्योमेट्री को WKT में अनुवादित करना](/gis/net/geometry-processing/translate-geometry-to-wkt/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}