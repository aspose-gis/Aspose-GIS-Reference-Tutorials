---
date: 2026-07-05
description: Aspose.GIS for .NET के साथ लेयर फीचर्स को क्रॉप करना सीखें, जिसमें raster
  को polygon के साथ क्रॉप करना, raster cell size निकालना, और raster extent प्राप्त
  करना शामिल है। अभी अपना free trial डाउनलोड करें।
keywords:
- how to crop layer
- extract raster extent
- get raster cell size
- crop raster layer
- crop raster with polygon
linktitle: लेयर फीचर्स को कैसे क्रॉप करें
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to crop layer features with Aspose.GIS for .NET, including
    how to crop raster with polygon, extract raster cell size, and retrieve raster
    extent. Download your free trial now.
  headline: How to Crop Layer Features with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Is a temporary license available for Aspose.GIS for .NET?
  - answer: The documentation is available [here](https://reference.aspose.com/gis/net/).
    question: Where can I find comprehensive documentation for Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for support
      and community engagement.
    question: How can I seek support or connect with the community for Aspose.GIS
      for .NET?
  - answer: Yes, you can download a free trial [here](https://releases.aspose.com/).
    question: Can I download a free trial of Aspose.GIS for .NET?
  - answer: You can purchase the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET के साथ लेयर फीचर्स को कैसे क्रॉप करें
url: /hi/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# लेयर फीचर्स को कैसे क्रॉप करें

## परिचय
इस ट्यूटोरियल में आप Aspose.GIS for .NET का उपयोग करके **how to crop layer** फीचर्स को सीखेंगे, जो एक शक्तिशाली लाइब्रेरी है जो आपको **crop raster with polygon**, **extract raster cell size**, और **retrieve raster extent** को सटीक जियोस्पेशियल विश्लेषण के लिए प्रदान करती है। चाहे आप वेब मैप के लिए डेटा तैयार कर रहे हों, सैटेलाइट इमेजरी को ट्रिम कर रहे हों, या रुचि के क्षेत्र को अलग कर रहे हों, यह चरण‑दर‑चरण गाइड आपको जल्दी और भरोसेमंद तरीके से काम पूरा करने का सही तरीका दिखाता है।

## त्वरित उत्तर
- **crop layer का क्या अर्थ है?** यह एक रास्टर या वेक्टर लेयर को प्रदान की गई ज्योमेट्री की सीमाओं तक सीमित कर देता है, और बाहर की सभी चीज़ों को हटा देता है।  
- **इस उदाहरण में कौन सी ज्योमेट्री उपयोग की गई है?** WKT (Well‑Known Text) फ़ॉर्मेट में परिभाषित एक बहुभुज।  
- **क्रॉपिंग के बाद मैं सेल साइज निकाल सकता हूँ?** Yes – the `CellSize` property returns the width and height of a raster cell.  
- **कोड चलाने के लिए मुझे लाइसेंस चाहिए?** A temporary license works for evaluation; a full license is required for production use.  
- **कौन से .NET संस्करण समर्थित हैं?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## “how to crop layer” क्या है?
**लेयर को क्रॉप करना मतलब डेटासेट को एक विशिष्ट भौगोलिक क्षेत्र तक सीमित करना है, और बाहर की सभी चीज़ों को हटाना है।** यह ऑपरेशन फ़ाइल आकार को कम करता है, बाद की प्रोसेसिंग को तेज़ बनाता है, और आपके द्वारा महत्व दिए गए क्षेत्र पर विश्लेषण को केंद्रित करता है। डेटा को रुचि के क्षेत्र तक सीमित करके, आप स्टाइलिंग, विश्लेषण, और प्रकाशन जैसे डाउनस्ट्रीम वर्कफ़्लो को भी सरल बनाते हैं, जबकि मूल कोऑर्डिनेट रेफ़रेंस सिस्टम और मेटाडेटा को संरक्षित रखते हैं।

## क्रॉपिंग के लिए Aspose.GIS क्यों उपयोग करें?
**Aspose.GIS रास्टर फ़ाइलों को 2 GB तक बिना पूरी इमेज को मेमोरी में लोड किए प्रोसेस करता है और 30 से अधिक रास्टर फ़ॉर्मेट्स को सपोर्ट करता है, जिसमें GeoTIFF, JPEG2000, और PNG शामिल हैं।** लाइब्रेरी एक सिंगल‑लाइन `Crop` कॉल, ऑटोमैटिक CRS हैंडलिंग, और मल्टी‑थ्रेडेड परफ़ॉर्मेंस प्रदान करती है जो सामान्य सर्वर पर 500‑MB GeoTIFF को एक सेकंड से कम समय में ट्रिम कर सकती है।

## पूर्वापेक्षाएँ
जियोस्पेशियल मैनिपुलेशन के जादू में डुबकी लगाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

- Aspose.GIS for .NET लाइब्रेरी: सुनिश्चित करें कि आपके .NET प्रोजेक्ट में Aspose.GIS लाइब्रेरी स्थापित है। आप इसे [here](https://releases.aspose.com/gis/net/) से डाउनलोड कर सकते हैं।  
- डॉक्यूमेंट डायरेक्टरी: अपने दस्तावेज़ों को संग्रहीत करने के लिए एक डायरेक्टरी सेट करें। प्रदान किए गए कोड में `"Your Document Directory"` को अपने वास्तविक डॉक्यूमेंट डायरेक्टरी पाथ से बदलें।

अब, चलिए चरण‑दर‑चरण गाइड में डुबकी लगाते हैं।

## नेमस्पेसेस इम्पोर्ट करें
`Aspose.Gis` नेमस्पेस रास्टर और वेक्टर हैंडलिंग के सभी कोर टाइप्स को शामिल करता है। इसे इम्पोर्ट करके आप `Layer`, `Geometry`, और संबंधित क्लासेज़ तक पहुंच प्राप्त कर सकते हैं।

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## एक बहुभुज के साथ लेयर को कैसे क्रॉप करें?
`Crop` `Layer` क्लास की एक मेथड है जो जियोमेट्री द्वारा परिभाषित रास्टर उपसमुच्चय को निकालती है।  
स्रोत रास्टर लोड करें, एक बहुभुज जियोमेट्री परिभाषित करें, और `Crop` मेथड को कॉल करें – पूरी प्रक्रिया एक ही लाइन के कोड में पूरी होती है। यह मेथड एक नया रास्टर रिटर्न करता है जिसमें केवल बहुभुज के अंदर के पिक्सेल होते हैं, और मूल स्पैशियल रेफ़रेंस को ऑटोमैटिकली संरक्षित करता है।

## चरण 1: लेयर खोलें और क्रॉप करें (crop raster with polygon)
`Layer` एक रास्टर डेटासेट को दर्शाता है जिसे खोला, क्वेरी किया और एडिट किया जा सकता है।  
`Layer` क्लास एक रास्टर डेटासेट को दर्शाता है जिसे खोला, क्वेरी किया और एडिट किया जा सकता है। GeoTIFF को खोलना और उसे बहुभुज के साथ क्रॉप करना कुछ ही स्टेटमेंट्स में रुचि के क्षेत्र को अलग करता है।

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## चरण 2: रास्टर जानकारी प्राप्त करें (extract raster cell size & retrieve raster extent)
`CellSize` प्रत्येक रास्टर सेल की चौड़ाई और ऊँचाई को कोऑर्डिनेट यूनिट्स में प्रदान करता है।  
`Extent` रास्टर का भौगोलिक बाउंडिंग बॉक्स रिटर्न करता है।  
`CellSize` प्रॉपर्टी प्रत्येक रास्टर सेल की चौड़ाई और ऊँचाई को कोऑर्डिनेट यूनिट्स में प्रदान करती है, जबकि `Extent` प्रॉपर्टी क्रॉप किए गए रास्टर का भौगोलिक बाउंडिंग बॉक्स रिटर्न करती है। दोनों जानकारी क्षेत्र माप या री‑प्रोजेक्शन जैसे डाउनस्ट्रीम कैलकुलेशन के लिए आवश्यक हैं।

```csharp
// read and print raster
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
```

## चरण 3: जानकारी प्रदर्शित करें
क्रॉपिंग प्रक्रिया के आपके जियोस्पेशियल डेटा पर प्रभाव को समझने के लिए निकाली गई जानकारी को प्रिंट करें।

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"source extent: {layer.GetExtent()}");
Console.WriteLine($"target extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
```

इन चरणों को आवश्यकतानुसार दोहराएँ ताकि आप अपने जियोस्पेशियल डेटा को विशिष्ट प्रोजेक्ट आवश्यकताओं के अनुसार परिष्कृत और अनुकूलित कर सकें।

## सामान्य समस्याएँ और समाधान
| समस्या | समाधान |
|-------|----------|
| **गलत बहुभुज अभिविन्यास** | सुनिश्चित करें कि WKT बहुभुज दाएँ‑हाथ नियम (बाहरी रिंग के लिए विपरीत‑घड़ी) का पालन करता है। |
| **स्पैशियल रेफ़रेंस गायब** | जाँचें कि स्रोत GeoTiff में CRS मौजूद है; यदि नहीं, तो क्रॉप करने से पहले मैन्युअली सेट करें। |
| **बड़े रास्टर पर प्रदर्शन में गिरावट** | `layer.Crop` को डाउन‑सैंपल्ड कॉपी पर उपयोग करें या रास्टर को टाइल्स में प्रोसेस करें। |

## अक्सर पूछे जाने वाले प्रश्न
**Q: Aspose.GIS for .NET के लिए एक टेम्पररी लाइसेंस उपलब्ध है?**  
A: हाँ, आप एक टेम्पररी लाइसेंस [here](https://purchase.aspose.com/temporary-license/) से प्राप्त कर सकते हैं।

**Q: Aspose.GIS for .NET के लिए व्यापक दस्तावेज़ीकरण कहाँ मिल सकता है?**  
A: दस्तावेज़ीकरण [here](https://reference.aspose.com/gis/net/) उपलब्ध है।

**Q: Aspose.GIS for .NET के लिए सपोर्ट कैसे प्राप्त करें या समुदाय से जुड़ें?**  
A: सपोर्ट और समुदाय सहभागिता के लिए [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) देखें।

**Q: क्या मैं Aspose.GIS for .NET का फ्री ट्रायल डाउनलोड कर सकता हूँ?**  
A: हाँ, आप फ्री ट्रायल [here](https://releases.aspose.com/) से डाउनलोड कर सकते हैं।

**Q: Aspose.GIS for .NET कहाँ खरीद सकते हैं?**  
A: आप लाइब्रेरी [here](https://purchase.aspose.com/buy) से खरीद सकते हैं।

**Q: क्या मैं एक ही रन में कई लेयर्स को क्रॉप कर सकता हूँ?**  
A: हाँ—प्रत्येक लेयर पर लूप करें और वांछित जियोमेट्री के साथ समान `Crop` कॉल लागू करें।

**Q: क्या API अन्य रास्टर फ़ॉर्मेट्स (जैसे JPEG2000) को सपोर्ट करता है?**  
A: Aspose.GIS सभी फ़ॉर्मेट्स को सपोर्ट करता है जो अंतर्निहित GDAL ड्राइवर द्वारा एक्सपोज़ किए जाते हैं, जिसमें JPEG2000, PNG, और अधिक शामिल हैं।

## निष्कर्ष
इस गाइड को फॉलो करके आप अब **how to crop layer** फीचर्स को Aspose.GIS for .NET के साथ कुशलतापूर्वक करना जानते हैं। आप आसानी से **crop raster with polygon**, **extract raster cell size**, और **retrieve raster extent** कर सकते हैं ताकि किसी भी प्रोजेक्ट की जरूरतों को पूरा किया जा सके। री‑प्रोजेक्शन, रास्टर स्टाइलिंग, और वेक्टर एनालिसिस के लिए आगे के API का अन्वेषण करें और अपने जियोस्पेशियल वर्कफ़्लो की पूरी क्षमता को अनलॉक करें।

---

**अंतिम अपडेट:** 2026-07-05  
**परीक्षण किया गया:** Aspose.GIS 24.10 for .NET  
**लेखक:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [Aspose.GIS for .NET के साथ बहुभुज ज्योमेट्री कैसे बनाएं](/gis/net/geometry-creation/create-polygon-geometry/)
- [लेयर एट्रिब्यूट प्राप्त करें – Aspose.GIS for .NET के साथ लेयर एट्रिब्यूट जानकारी प्राप्त करें](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [C# में बहुभुज ज्योमेट्री बनाएं और Aspose.GIS for .NET के साथ इंटरसेक्शन जांचें](/gis/net/geometry-analysis/check-geometries-intersection/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}