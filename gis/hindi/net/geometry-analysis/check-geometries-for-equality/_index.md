---
date: 2026-06-05
description: Aspose.GIS का उपयोग करके .NET में ज्यामितियों की तुलना कैसे करें, डुप्लिकेट
  ज्यामितियों का पता लगाएँ, और अपने अनुप्रयोगों में ज्यामिति समानता जांचें।
keywords:
- how to compare geometries
- detect duplicate geometries
- Aspose.GIS geometry equality
linktitle: ज्यामितियों की समानता की तुलना कैसे करें
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to compare geometries in .NET using Aspose.GIS, detect duplicate
    geometries, and check geometry equality in your applications.
  headline: How to Compare Geometries for Equality using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS works with .NET Framework, .NET Core, and .NET Standard
      projects.
    question: Can I use Aspose.GIS for .NET with other .NET frameworks?
  - answer: Absolutely. Download a trial from the [Aspose.GIS releases page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Detailed docs are on the [Aspose.GIS documentation page](https://reference.aspose.com/gis/net/).
    question: Where can I find the full API documentation?
  - answer: Post your question on the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How do I get help if I run into an issue?
  - answer: Yes, temporary licenses are available on the [purchase page](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET का उपयोग करके ज्यामितियों की समानता की तुलना कैसे करें
url: /hi/net/geometry-analysis/check-geometries-for-equality/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET का उपयोग करके ज्यामितियों की समानता की तुलना कैसे करें

## परिचय
इस ट्यूटोरियल में आप Aspose.GIS for .NET के साथ **ज्यामितियों की तुलना कैसे करें** सीखेंगे, यह कार्य तब आवश्यक हो जाता है जब आपको डुप्लिकेट ज्यामितियों का पता लगाना हो, स्पैशियल डेटा को मान्य करना हो, या टोपोलॉजिकल नियमों को लागू करना हो। चाहे आप मैपिंग सेवा बना रहे हों, बैच स्पैशियल विश्लेषण चला रहे हों, या केवल यह सत्यापित कर रहे हों कि दो आकार एक ही स्थान पर स्थित हैं, यह गाइड आपको साफ़, प्रोडक्शन‑रेडी C# कोड के साथ ज्यामिति समानता को बनाने, संशोधित करने और परीक्षण करने के चरणों से ले जाएगा।

## त्वरित उत्तर
- **“ज्यामितियों की तुलना” क्या मतलब है?** यह जांचता है कि क्या दो ज्यामितीय वस्तुएँ एक ही स्थान पर स्थित हैं, चाहे उन्हें कैसे भी निर्मित किया गया हो।  
- **कौन सी विधि उपयोग की जाती है?** `SpatiallyEquals` Aspose.GIS API से।  
- **क्या विकास के लिए मुझे लाइसेंस चाहिए?** परीक्षण के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए एक वाणिज्यिक लाइसेंस आवश्यक है।  
- **समर्थित .NET संस्करण?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **सामान्य कार्यान्वयन समय?** एक बुनियादी समानता जांच के लिए लगभग 5‑10 मिनट।

## ज्यामिति समानता क्या है?
ज्यामिति समानता, जिसे स्पैशियल समानता भी कहा जाता है, का अर्थ है कि दो ज्यामितियाँ पृथ्वी की सतह पर बिल्कुल समान बिंदुओं का सेट दर्शाती हैं। भले ही एक ज्यामिति `MultiLineString` के रूप में निर्मित हो और दूसरी एकल `LineString` के रूप में, वे समान मानी जाती हैं जब प्रत्येक निर्देशांक परिभाषित सहनशीलता के भीतर मेल खाता है। यह परिभाषा डेवलपर्स को विभिन्न डेटा स्रोतों में डुप्लिकेट ज्यामितियों का विश्वसनीय रूप से पता लगाने की अनुमति देती है।

## ज्यामितियों की तुलना के लिए Aspose.GIS का उपयोग क्यों करें?
Aspose.GIS एक उच्च‑प्रदर्शन, ऑफ़लाइन ज्यामिति इंजन प्रदान करता है जो बाहरी सेवाओं की आवश्यकता को समाप्त करता है। यह **30+ वेक्टर और रास्टर फ़ॉर्मेट्स** (जैसे WKT, GeoJSON, Shapefile, KML, GML) का समर्थन करता है और **सैकड़ों हज़ार वर्टिसेज़** वाली फ़ाइलों को प्रोसेस कर सकता है जबकि मेमोरी उपयोग 50 MB से कम रहता है। लाइब्रेरी की `SpatiallyEquals` विधि सटीकता‑सचेत है, जिससे फ्लोटिंग‑पॉइंट निर्देशांक के साथ भी निर्धारक परिणाम मिलते हैं।

### यह डेवलपर्स के लिए क्यों महत्वपूर्ण है
जब आपको बैच प्रक्रियाओं, रीयल‑टाइम वैलिडेशन पाइपलाइन, या GIS डेटा माइग्रेशन में **डुप्लिकेट ज्यामितियों** का पता लगाना हो, तो एक सिद्ध लाइब्रेरी अनुमान को हटाती है और विभिन्न डेटा प्रदाताओं में निरंतर परिणाम सुनिश्चित करती है।

## पूर्वापेक्षाएँ
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- **.NET Framework या .NET Core स्थापित** – Aspose.GIS द्वारा समर्थित कोई भी संस्करण।  
- **Aspose.GIS for .NET लाइब्रेरी** – [Aspose.GIS डाउनलोड पेज](https://releases.aspose.com/gis/net/) से डाउनलोड करें।  
- **एक विकास IDE** – Visual Studio, Rider, या C# एक्सटेंशन के साथ VS Code।

## नेमस्पेस आयात करें
अपने .NET प्रोजेक्ट में, आवश्यक `using` स्टेटमेंट्स जोड़ें ताकि कंपाइलर को GIS क्लासेज़ का पता चल सके:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## चरण 1: ज्यामितियों को परिभाषित करें
`MultiLineString` रेखा घटकों के संग्रह का प्रतिनिधित्व करता है, जबकि `LineString` एक एकल निरंतर रेखा को परिभाषित करता है। दोनों क्लासेज़ बेस `Geometry` प्रकार से विरासत में मिलती हैं।

पहले, हम दो ज्यामितियाँ बनाते हैं जिन्हें हम तुलना करेंगे। इस उदाहरण में `geometry1` दो रेखा खंडों से बना एक `MultiLineString` है, जबकि `geometry2` एक एकल `LineString` है जो समान प्रारंभ और अंत बिंदुओं को कवर करता है।

```csharp
var geometry1 = new MultiLineString
{
    new LineString(new [] { new Point(0, 0), new Point(1, 1) }),
    new LineString(new [] { new Point(1, 1), new Point(2, 2) }),
};
var geometry2 = new LineString(new[]
{
    new Point(0, 0), new Point(2, 2),
});
```

## चरण 2: ज्यामितियों की समानता जांचें
`SpatiallyEquals` मूल्यांकन करता है कि क्या दो ज्यामितियाँ समान बिंदुओं के सेट को कवर करती हैं, वैकल्पिक रूप से फ्लोटिंग‑पॉइंट असटीकता के लिए सहनशीलता मान स्वीकार करता है।

अब हम `SpatiallyEquals` विधि का उपयोग करते हैं यह देखने के लिए कि क्या GIS इंजन द्वारा दोनों आकार समान माने जाते हैं।

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // True
```

कंसोल `True` प्रिंट करता है क्योंकि, अलग निर्माण के बावजूद, दोनों ज्यामितियाँ (0,0) से (2,2) तक की समान रेखा को कवर करती हैं।

## चरण 3: एक ज्यामिति को संशोधित करें
यह दर्शाने के लिए कि परिवर्तन समानता को कैसे प्रभावित करता है, हम `geometry2` में एक अतिरिक्त बिंदु जोड़ते हैं।

```csharp
geometry2.AddPoint(3, 3);
```

## चरण 4: संशोधन के बाद समानता पुनः जांचें
संशोधन के बाद, ज्यामितियाँ अब समान नहीं रहतीं, इसलिए `SpatiallyEquals` `False` लौटाता है।

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // False
```

आउटपुट `False` यह पुष्टि करता है कि अतिरिक्त बिंदु ने स्पैशियल समानता को तोड़ दिया।

## डुप्लिकेट ज्यामितियों का पता कैसे लगाएँ?
प्रत्येक ज्यामिति को लोड करें, उपयुक्त सहनशीलता के साथ `SpatiallyEquals` को कॉल करें, और उन ज्यामितियों को फ़िल्टर करें जो `True` लौटाती हैं। यह पैटर्न LINQ के साथ अच्छी तरह स्केल करता है, जिससे आप बड़े संग्रह में कुछ ही कोड लाइनों से डुप्लिकेट आकारों की पहचान कर सकते हैं। आप इसे `GroupBy` के साथ भी संयोजित करके समान ज्यामितियों को एकत्रित कर सकते हैं और स्टोरेज लागत को कम कर सकते हैं।

## सामान्य समस्याएँ और सुझाव
- **सटीकता समस्याएँ** – यदि आप बहुत उच्च‑सटीकता वाले निर्देशांक के साथ काम करते हैं, तो राउंडिंग या `SpatiallyEquals` के सहनशीलता ओवरलोड का उपयोग करने पर विचार करें।  
- **विभिन्न SRID** – तुलना से पहले सुनिश्चित करें कि दोनों ज्यामितियों का समान Spatial Reference System Identifier (SRID) हो।  
- **प्रदर्शन** – बड़े संग्रहों के लिए, LINQ या समानांतर लूप्स का उपयोग करके बैच तुलना करने से ओवरहेड को काफी कम किया जा सकता है।

## अक्सर पूछे जाने वाले प्रश्न
**Q: क्या मैं Aspose.GIS for .NET को अन्य .NET फ्रेमवर्क्स के साथ उपयोग कर सकता हूँ?**  
A: हाँ, Aspose.GIS .NET Framework, .NET Core, और .NET Standard प्रोजेक्ट्स के साथ काम करता है।

**Q: क्या कोई मुफ्त ट्रायल उपलब्ध है?**  
A: बिल्कुल। ट्रायल को [Aspose.GIS रिलीज़ पेज](https://releases.aspose.com/) से डाउनलोड करें।

**Q: पूर्ण API दस्तावेज़ कहाँ मिल सकता है?**  
A: विस्तृत दस्तावेज़ [Aspose.GIS दस्तावेज़ पेज](https://reference.aspose.com/gis/net/) पर उपलब्ध हैं।

**Q: यदि मुझे कोई समस्या आती है तो मदद कैसे प्राप्त करूँ?**  
A: अपना प्रश्न Aspose.GIS समुदाय फ़ोरम पर [यहाँ](https://forum.aspose.com/c/gis/33) पोस्ट करें।

**Q: क्या मैं मूल्यांकन के लिए एक अस्थायी लाइसेंस खरीद सकता हूँ?**  
A: हाँ, अस्थायी लाइसेंस [खरीद पेज](https://purchase.aspose.com/temporary-license/) पर उपलब्ध हैं।

## निष्कर्ष
अब आप Aspose.GIS for .NET का उपयोग करके **ज्यामितियों की तुलना कैसे करें** जानते हैं, वस्तुओं को बनाने से लेकर स्पैशियल समानता जांचने और संशोधनों को संभालने तक। यह क्षमता अधिक उन्नत स्पैशियल विश्लेषणों जैसे टोपोलॉजी वैलिडेशन, डुप्लिकेट डिटेक्शन, और ज्यामिति‑आधारित फ़िल्टरिंग के लिए एक निर्माण ब्लॉक है।

---

**अंतिम अपडेट:** 2026-06-05  
**परीक्षण किया गया:** Aspose.GIS for .NET 24.11  
**लेखक:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [C# में पॉलीगॉन ज्यामिति बनाएं और Aspose.GIS for .NET के साथ इंटरसेक्शन जांचें](/gis/net/geometry-analysis/check-geometries-intersection/)
- [Aspose.GIS for .NET के साथ ज्यामितियों का स्पैशियल ओवरलैप विश्लेषण कैसे करें](/gis/net/geometry-analysis/check-geometries-overlap/)
- [नेटवर्क रूटिंग जांच: Aspose.GIS के साथ टचिंग ज्यामितियाँ](/gis/net/geometry-analysis/check-geometries-touching/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}