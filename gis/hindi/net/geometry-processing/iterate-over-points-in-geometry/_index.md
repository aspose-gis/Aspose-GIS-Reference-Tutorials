---
date: 2026-06-10
description: Aspose.GIS for .NET का उपयोग करके, .NET डेवलपर्स के लिए शक्तिशाली GIS
  टूलकिट, geometry पर इटररेट करते हुए shape में points जोड़ना और coordinates जोड़ना
  सीखें।
keywords:
- how to add points
- add coordinates to shape
- Aspose.GIS geometry
linktitle: कैसे Points जोड़ें और .NET में Geometry पर इटररेट करें
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to add points and add coordinates to shape while iterating
    over geometry using Aspose.GIS for .NET, the powerful GIS toolkit for .NET developers.
  headline: How to Add Points and Iterate Over Geometry in .NET
  type: TechArticle
- description: Learn how to add points and add coordinates to shape while iterating
    over geometry using Aspose.GIS for .NET, the powerful GIS toolkit for .NET developers.
  name: How to Add Points and Iterate Over Geometry in .NET
  steps:
  - name: Create a `LineString` object
    text: '`LineString` is Aspose.GIS''s geometry type that represents an ordered
      collection of points forming a polyline.'
  - name: Add points to the `LineString`
    text: The `AddPoint` method inserts a new vertex (longitude, latitude) at the
      end of the line. Call it repeatedly to **add coordinates to shape** objects.
  - name: Iterate over the points
    text: '`LineString` implements `IEnumerable<IPoint>`, allowing you to loop through
      each point with a `foreach` statement. This makes extracting X (longitude) and
      Y (latitude) values trivial. The loop prints each point’s X (longitude) and
      Y (latitude) values to the console, allowing you to verify that the p'
  type: HowTo
- questions:
  - answer: '`LineString`'
    question: What is the primary class for point collections?
  - answer: Use `AddPoint(longitude, latitude)`
    question: How do you add a point?
  - answer: Yes, `LineString` implements `IEnumerable<IPoint>`
    question: Can you iterate with a foreach loop?
  - answer: .NET 6+ (or .NET Core 3.1/Framework 4.6+) and Aspose.GIS for .NET library
    question: Prerequisites?
  - answer: Building routes, visualizing tracks, or preprocessing data for spatial
      analysis
    question: Typical use case?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: कैसे Points जोड़ें और .NET में Geometry पर इटररेट करें
url: /hi/net/geometry-processing/iterate-over-points-in-geometry/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET में बिंदु जोड़ना और ज्यामिति पर इटररेट करना

## परिचय

यदि आप .NET पर्यावरण में GIS डेटा के साथ काम कर रहे हैं, तो आपको सबसे पहले यह जानना होगा कि **बिंदु कैसे जोड़ें** एक ज्यामिति में और फिर उन बिंदुओं के साथ काम करें। Aspose.GIS for .NET एक साफ़, ऑब्जेक्ट‑ओरिएंटेड API प्रदान करता है जो इस प्रक्रिया को सरल बनाता है। इस ट्यूटोरियल में हम `LineString` बनाने, उसमें बिंदु जोड़ने, और उन बिंदुओं पर इटररेट करने के चरणों से गुजरेंगे ताकि आप समन्वय निकाल सकें या आगे का विश्लेषण कर सकें। आप यह भी देखेंगे कि **shape में समन्वय जोड़ें** ऑब्जेक्ट्स में कुशलतापूर्वक।

## त्वरित उत्तर
- **बिंदु संग्रह के लिए मुख्य क्लास कौन सी है?** `LineString`
- **आप बिंदु कैसे जोड़ते हैं?** `AddPoint(longitude, latitude)` का उपयोग करें
- **क्या आप foreach लूप के साथ इटररेट कर सकते हैं?** हां, `LineString` implements `IEnumerable<IPoint>`
- **पूर्वापेक्षाएँ?** .NET 6+ (or .NET Core 3.1/Framework 4.6+) and Aspose.GIS for .NET library
- **सामान्य उपयोग मामला?** मार्ग बनाना, ट्रैक को विज़ुअलाइज़ करना, या स्थानिक विश्लेषण के लिए डेटा पूर्व-प्रसंस्करण
- **IPoint** एक एकल बिंदु ज्यामिति का प्रतिनिधित्व करता है जिसमें X (longitude) और Y (latitude) समन्वय होते हैं।

## GIS में “बिंदु जोड़ना” क्या है?
बिंदु जोड़ना का अर्थ है व्यक्तिगत समन्वय युग्म (longitude, latitude) को एक ज्यामितीय कंटेनर जैसे `LineString`, `Polygon`, या `MultiPoint` में सम्मिलित करना। प्रत्येक बिंदु एक वर्टेक्स बन जाता है जो आप द्वारा मॉडल किए जा रहे आकार या पथ को परिभाषित करता है, जिससे स्थानिक संचालन और विज़ुअलाइज़ेशन संभव होते हैं। इन वर्टेक्स को बाद में विश्लेषण के लिए एक्सेस किया जा सकता है, विभिन्न GIS फ़ॉर्मैट्स में निर्यात किया जा सकता है, या दूरी मापन या इंटरसेक्शन परीक्षण जैसे स्थानिक गणनाओं में उपयोग किया जा सकता है।

## Aspose.GIS के साथ बिंदु क्यों जोड़ें?
आप Aspose.GIS के साथ बिंदु जोड़ते हैं क्योंकि यह लाइब्रेरी **टाइप‑सेफ ज्यामिति हैंडलिंग** की गारंटी देती है, **30+ वेक्टर और रास्टर फ़ॉर्मैट्स** का समर्थन करती है, और **सैकड़ों पृष्ठों वाले डेटासेट** को पूरी फ़ाइल को मेमोरी में लोड किए बिना प्रोसेस कर सकती है। API में बिल्ट‑इन इटररेशन, स्थानिक संचालन, और फ़ॉर्मैट रूपांतरण (Shapefile, GeoJSON, KML, आदि) भी प्रत्येक समर्थित प्लेटफ़ॉर्म पर उपलब्ध है।

## पूर्वापेक्षाएँ
- Visual Studio 2022 (या कोई भी C# IDE)  
- Aspose.GIS for .NET NuGet पैकेज स्थापित  
- C# सिंटैक्स की बुनियादी समझ  

## नेमस्पेस इम्पोर्ट करें
अपने .NET एप्लिकेशन में Aspose.GIS कार्यक्षमताओं तक पहुँचने के लिए आवश्यक नेमस्पेस इम्पोर्ट करके शुरू करें:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ज्यामिति में बिंदु कैसे जोड़ें?
आप बिंदु जोड़ते हैं `LineString` इंस्टेंस बनाकर, प्रत्येक समन्वय युग्म के लिए उसकी `AddPoint` मेथड को कॉल करके, और आवश्यकता पड़ने पर संग्रह पर इटररेट करके। यह तीन‑चरणीय पैटर्न निर्माण, जनसंख्या, और ट्रैवर्सल को संक्षिप्त, पठनीय तरीके से कवर करता है। **LineString एक ज्यामिति प्रकार है जो पॉलीलाइन बनाते हुए बिंदुओं के क्रमबद्ध संग्रह का प्रतिनिधित्व करता है।** यह तरीका सुनिश्चित करता है कि ज्यामिति वैध बनी रहे और आगे के स्थानिक संचालन जैसे लंबाई गणना या निर्यात के लिए तैयार रहे।

### चरण 1: एक `LineString` ऑब्जेक्ट बनाएं  
`LineString` Aspose.GIS का वह ज्यामिति प्रकार है जो पॉलीलाइन बनाते हुए बिंदुओं के क्रमबद्ध संग्रह का प्रतिनिधित्व करता है।

```csharp
LineString line = new LineString();
```

### चरण 2: `LineString` में बिंदु जोड़ें  
`AddPoint` मेथड लाइन के अंत में एक नया वर्टेक्स (longitude, latitude) सम्मिलित करता है। इसे बार‑बार कॉल करके **shape** ऑब्जेक्ट्स में समन्वय जोड़ें।

```csharp
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```

### चरण 3: बिंदुओं पर इटररेट करें  
`LineString` `IEnumerable<IPoint>` को इम्प्लीमेंट करता है, जिससे आप `foreach` स्टेटमेंट के साथ प्रत्येक बिंदु पर लूप कर सकते हैं। यह X (longitude) और Y (latitude) मानों को निकालना आसान बनाता है।

```csharp
foreach (IPoint point in line)
{
    Console.WriteLine(point.X + "," + point.Y);
}
```

लूप प्रत्येक बिंदु के X (longitude) और Y (latitude) मानों को कंसोल पर प्रिंट करता है, जिससे आप यह सत्यापित कर सकते हैं कि बिंदु सही ढंग से जोड़े गए हैं।

## सामान्य उपयोग मामलों
- **मार्ग योजना** – GPS लॉग्स से एक पथ बनाएं और फिर वेपॉइंट्स के बीच दूरी का विश्लेषण करें।  
- **डेटा वैधता** – बिंदुओं पर इटररेट करें ताकि यह सुनिश्चित हो सके कि वे अपेक्षित सीमाओं के भीतर हैं (जैसे, किसी देश की सीमा के भीतर)।  
- **विज़ुअलाइज़ेशन** – `LineString` को GeoJSON या Shapefile में निर्यात करें ताकि मैपिंग टूल्स में उपयोग किया जा सके।

## अक्सर पूछे जाने वाले प्रश्न
**Q1: क्या Aspose.GIS for .NET `LineString` के अलावा अन्य ज्यामितीय आकारों को संभाल सकता है?**  
A: हां, Aspose.GIS `Point`, `Polygon`, `MultiLineString`, `MultiPolygon`, और कई अन्य ज्यामिति प्रकारों का समर्थन करता है।

**Q2: क्या Aspose.GIS व्यावसायिक और व्यक्तिगत दोनों प्रोजेक्ट्स के लिए उपयुक्त है?**  
A: बिल्कुल। लाइसेंसिंग विकल्प व्यावसायिक, व्यक्तिगत, और शैक्षिक उपयोग मामलों को कवर करते हैं।

**Q3: क्या Aspose.GIS for .NET शुरुआती लोगों के लिए व्यापक दस्तावेज़ीकरण प्रदान करता है?**  
A: हां, उत्पाद में विस्तृत दस्तावेज़, API रेफ़रेंसेज़, और कई कोड उदाहरण शामिल हैं जो आपको जल्दी शुरू करने में मदद करते हैं।

**Q4: क्या मैं कस्टम विकास के माध्यम से Aspose.GIS for .NET की कार्यक्षमता को विस्तारित कर सकता हूं?**  
A: आप एक्सटेंशन मेथड्स बना सकते हैं या Aspose.GIS क्लासेज़ को रैप कर सकते हैं ताकि विशिष्ट वर्कफ़्लो में फिट हो, जिससे आपको कस्टम जियोस्पेशियल समाधान पर पूर्ण नियंत्रण मिलता है।

**Q5: क्या Aspose.GIS उपयोगकर्ताओं के लिए तकनीकी समर्थन उपलब्ध है?**  
A: Aspose फोरम और टिकटिंग सिस्टम के माध्यम से समर्पित तकनीकी समर्थन प्रदान किया जाता है, जिससे आपको शीघ्र सहायता मिलती है।

**अंतिम अपडेट:** 2026-06-10  
**परीक्षित संस्करण:** Aspose.GIS for .NET 24.5 (latest at time of writing)  
**लेखक:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल
- [Aspose.GIS for .NET के साथ ज्यामिति में बिंदुओं की गिनती कैसे करें](/gis/net/geometry-creation/count-points-in-geometry/)
- [Aspose.GIS के साथ LineString में बिंदु कैसे जोड़ें और ज्यामिति को संपादन योग्य फ़ॉर्मेट में कैसे बदलें](/gis/net/geometry-creation/convert-geometry-to-editable/)
- [Aspose.GIS for .NET के साथ MultiPoint ज्यामिति बनाएं](/gis/net/geometry-creation/create-multipoint-geometry/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}