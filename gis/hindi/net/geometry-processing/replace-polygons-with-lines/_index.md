---
date: 2025-12-23
description: Aspose.GIS for .NET का उपयोग करके बहुभुज से रेखा बनाना और बहुभुज को रेखाओं
  में बदलना सीखें। GIS डेटा हेरफेर को जल्दी से महारत हासिल करें।
linktitle: Replace Polygons with Lines
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET के साथ बहुभुज से रेखा कैसे बनाएं
url: /hi/net/geometry-processing/replace-polygons-with-lines/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET के साथ बहुभुज से रेखा बनाएं

## परिचय
यदि आपको GIS एप्लिकेशन में **create line from polygon** करने की आवश्यकता है, तो Aspose.GIS for .NET एक सरल, एक‑लाइन विधि प्रदान करता है जो परिवर्तन को करता है। बहुभुज ज्यामितियों को रेखा ज्यामितियों में बदलना एक सामान्य कदम है जब आप सीमाओं को दृश्य बनाना चाहते हैं, रैखिक विश्लेषण करना चाहते हैं, या डेटा जटिलता को कम करना चाहते हैं। इस ट्यूटोरियल में आप देखेंगे कि बहुभुज को रेखाओं से कैसे बदलें, यह क्यों महत्वपूर्ण है, और इसे अपने .NET प्रोजेक्ट्स में कैसे एकीकृत करें।

## त्वरित उत्तर
- **create line from polygon का क्या अर्थ है?** यह बंद बहुभुज आकारों को उनके घटक सीमा रेखाओं में बदल देता है।  
- **कौन सी विधि परिवर्तन करती है?** Aspose.GIS Geometry API से `ReplacePolygonsByLines()`।  
- **क्या कोड चलाने के लिए लाइसेंस चाहिए?** मूल्यांकन के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए एक व्यावसायिक लाइसेंस आवश्यक है।  
- **कौन से .NET संस्करण समर्थित हैं?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7।  
- **क्या इसे अन्य GIS फ़ॉर्मैट्स के साथ उपयोग कर सकता हूँ?** हाँ – यही तरीका Shapefile, GeoJSON, KML आदि के साथ काम करता है।

## “create line from polygon” क्या है?
बहुभुज से रेखा बनाना बहुभुज की किनारों को `LineString` संग्रह के रूप में निकालता है। इस ऑपरेशन को अक्सर *polygon to line* रूपांतरण कहा जाता है और यह नेटवर्क विश्लेषण, मानचित्र रेंडरिंग, और डेटा सरलीकरण जैसे कार्यों के लिए उपयोगी है।

## इस रूपांतरण के लिए Aspose.GIS का उपयोग क्यों करें?
- **बिल्ट‑इन मेथड** – कस्टम ज्यामिति पार्सिंग कोड लिखने की आवश्यकता नहीं।  
- **उच्च प्रदर्शन** – बड़े डेटा सेट्स के लिए अनुकूलित।  
- **क्रॉस‑फ़ॉर्मैट समर्थन** – कई GIS फ़ाइल प्रकारों के साथ काम करता है।  
- **व्यापक दस्तावेज़ीकरण** – शुरू करना आसान।

## पूर्वापेक्षाएँ
कोड में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित तैयार हैं:

### Aspose.GIS for .NET स्थापित करना
1. Aspose.GIS for .NET डाउनलोड करें: नवीनतम संस्करण डाउनलोड करने के लिए [this link](https://releases.aspose.com/gis/net/) पर जाएँ।  
2. Aspose.GIS for .NET स्थापित करें: पैकेज में दिए गए इंस्टॉलेशन निर्देशों का पालन करें या विस्तृत चरणों के लिए [documentation](https://reference.aspose.com/gis/net/) देखें।

## नेमस्पेस आयात करें
अपने .NET प्रोजेक्ट में, आवश्यक नेमस्पेस आयात करें ताकि आप Aspose.GIS ज्यामिति क्लासेज़ के साथ काम कर सकें।

```csharp
using System;
using Aspose.Gis.Geometries;
```

## बहुभुज को रेखाओं से बदलने के लिए चरण‑दर‑चरण गाइड

### चरण 1: स्रोत ज्यामिति परिभाषित करें
एक ज्यामिति संग्रह बनाएं जिसमें वे बहुभुज हों जिन्हें आप बदलना चाहते हैं।

```csharp
var srcGeometry = Geometry.FromText(@"GeometryCollection (POLYGON((1 2, 1 4, 3 4, 3 2)), Point (5 1))");
```

### चरण 2: बहुभुज को रेखाओं में बदलें
`ReplacePolygonsByLines()` मेथड का उपयोग करके **बहुभुज को रेखाओं में बदलें**। यह *create line from polygon* ऑपरेशन का मूल है।

```csharp
var dstGeometry = srcGeometry.ReplacePolygonsByLines();
```

### चरण 3: परिणाम प्रदर्शित करें
परिवर्तन की पुष्टि करने के लिए मूल और परिवर्तित दोनों ज्यामितियों को प्रिंट करें।

```csharp
Console.WriteLine($"source: {srcGeometry.AsText()}");
Console.WriteLine($"result: {dstGeometry.AsText()}");
```

## सामान्य कठिनाइयाँ और समस्या निवारण
- **खाली ज्यामिति संग्रह** – सुनिश्चित करें कि आपका स्रोत ज्यामिति वास्तव में बहुभुज रखता है; अन्यथा `ReplacePolygonsByLines()` मूल ज्यामिति को अपरिवर्तित लौटाता है।  
- **मिश्रित ज्यामिति प्रकार** – यह मेथड केवल बहुभुज को प्रभावित करता है; अन्य ज्यामिति प्रकार (जैसे पॉइंट्स) अपरिवर्तित रहेंगे।  
- **संस्करण संगतता** – पुरानी API समस्याओं से बचने के लिए नवीनतम Aspose.GIS NuGet पैकेज का उपयोग करें।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या Aspose.GIS for .NET विभिन्न GIS फ़ाइल फ़ॉर्मैट्स के साथ काम कर सकता है?**  
A: हाँ, Aspose.GIS for .NET Shapefile, GeoJSON, KML आदि जैसे फ़ॉर्मैट्स को पढ़ने और लिखने का समर्थन करता है।

**Q: क्या Aspose.GIS for .NET के लिए मुफ्त ट्रायल उपलब्ध है?**  
A: हाँ, आप Aspose.GIS for .NET का मुफ्त ट्रायल [here](https://releases.aspose.com/) से एक्सेस कर सकते हैं।

**Q: क्या Aspose.GIS for .NET डेवलपर्स के लिए समर्थन प्रदान करता है?**  
A: हाँ, डेवलपर्स Aspose.GIS कम्युनिटी फ़ोरम से समर्थन और सहायता प्राप्त कर सकते हैं [here](https://forum.aspose.com/c/gis/33)।

**Q: क्या मैं Aspose.GIS for .NET के लिए अस्थायी लाइसेंस खरीद सकता हूँ?**  
A: हाँ, आप अस्थायी लाइसेंस [here](https://purchase.aspose.com/temporary-license/) से प्राप्त कर सकते हैं।

**Q: क्या Aspose.GIS for .NET शुरुआती और अनुभवी दोनों डेवलपर्स के लिए उपयुक्त है?**  
A: बिल्कुल, Aspose.GIS for .NET सभी स्तरों के डेवलपर्स को लक्षित करता है, व्यापक दस्तावेज़ीकरण और समर्थन प्रदान करता है।

---

**अंतिम अपडेट:** 2025-12-23  
**परीक्षण किया गया:** Aspose.GIS for .NET 24.12 (latest at time of writing)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}