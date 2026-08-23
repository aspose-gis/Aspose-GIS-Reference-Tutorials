---
date: 2026-08-03
description: Aspose.GIS for .NET के साथ linestring c# बनाने, linestring में बिंदु
  जोड़ने, और covers मेथड का उपयोग करके बिंदु‑लाइन जाँच करने का तरीका सीखें।
keywords:
- create linestring c#
- point on line check
- add points to linestring
- use covers method
lastmod: 2026-08-03
linktitle: linestring c# बनाएं – जाँचें कि ज्यामिति दूसरे को कवर करती है
og_description: Aspose.GIS के covers मेथड का उपयोग करके linestring c# बनाएं और बिंदु‑लाइन
  सत्यापित करें। .NET एप्लिकेशन के लिए सटीक ज्यामिति जाँचें सीखें। (150‑160 अक्षर)
og_image_alt: Developer guide showing linestring creation and covers check in C# with
  Aspose.GIS
og_title: linestring c# बनाएं – जाँचें कि ज्यामिति दूसरे को कवर करती है (50‑60 अक्षर)
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to create linestring c# with Aspose.GIS for .NET, add points
    to a linestring, and perform a point on line check using the covers method.
  headline: Create linestring c# – Check geometry covers another
  type: TechArticle
- description: Learn how to create linestring c# with Aspose.GIS for .NET, add points
    to a linestring, and perform a point on line check using the covers method.
  name: Create linestring c# – Check geometry covers another
  steps:
  - name: create a linestring object
    text: The `LineString` class represents a sequence of points connected by straight
      line segments in a two‑dimensional plane. Here, we instantiate a new `LineString`
      object, which represents a sequence of connected line segments in a two‑dimensional
      space.
  - name: add points to linestring
    text: '`AddPoint` appends a coordinate pair to the end of the `LineString` collection,
      preserving the order of insertion. We **add points to linestring** using the
      `AddPoint` method. In this example, we add two points: (0, 0) and (1, 1), forming
      a simple diagonal line segment.'
  - name: create a point object
    text: The `Point` class models a single location in a two‑dimensional coordinate
      system. Instantiate a `Point` object representing a single point in a two‑dimensional
      space. Here, we create a point at coordinates (0, 0).
  - name: perform a point on line check – does the line cover the point?
    text: '`Covers` determines whether the first geometry completely contains the
      second geometry, returning true only when every point of the second geometry
      lies inside the first. Use the `Covers` method to check if the line covers the
      point. In this case, it returns `True` because the point (0, 0) lies exac'
  - name: verify the reverse relationship – is the point covered by the line?
    text: '`CoveredBy` is the inverse of `Covers`; it returns true when the invoking
      geometry is entirely inside the target geometry. Similarly, use the `CoveredBy`
      method to check if the point is covered by the line. Since the point (0, 0)
      lies on the line, it also returns `True`.'
  type: HowTo
- questions:
  - answer: Yes, you can use Aspose.GIS for .NET in both commercial and non‑commercial
      projects after obtaining the appropriate license.
    question: Can I use Aspose.GIS for .NET in my commercial projects?
  - answer: Yes, Aspose.GIS for .NET is compatible with both .NET Framework and .NET
      Core environments.
    question: Is Aspose.GIS for .NET compatible with .NET Core?
  - answer: Yes, Aspose.GIS for .NET supports a wide range of GIS formats including
      Shapefile, GeoJSON, KML, and more.
    question: Does Aspose.GIS for .NET support various GIS formats?
  - answer: Aspose.GIS for .NET is a proprietary library developed by Aspose, so external
      contributions are not accepted. However, you can provide feedback and suggestions
      to improve the library.
    question: Can I contribute to the development of Aspose.GIS for .NET?
  - answer: Updates for Aspose.GIS for .NET are released regularly to introduce new
      features, enhancements, and bug fixes. Check the [website](https://releases.aspose.com/gis/net/)
      for the latest releases.
    question: How often are updates released for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- create linestring
- Aspose.GIS
- C# geometry analysis
title: linestring c# बनाएं – जाँचें कि ज्यामिति दूसरे को कवर करती है
url: /hi/net/geometry-analysis/check-geometry-covers-another/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ज्यामिति एक अन्य को कवर करती है

## परिचय
इस ट्यूटोरियल में आप Aspose.GIS for .NET का उपयोग करके **linestring c# कैसे बनाएं** सीखेंगे, एक linestring में बिंदु जोड़ेंगे, और `Covers` और `CoveredBy` मेथड्स के साथ एक विश्वसनीय **लाइन पर बिंदु जांच** करेंगे। चाहे आप मैपिंग टूल बना रहे हों, स्पेशियल एनालिटिक्स कर रहे हों, या केवल ज्यामितीय संबंधों की पुष्टि करनी हो, इन ऑपरेशनों में निपुणता आपके एप्लिकेशन को आवश्यक सटीकता प्रदान करेगी।

## त्वरित उत्तर
- **“create linestring c#” का क्या अर्थ है?** यह `LineString` ज्यामिति ऑब्जेक्ट को इंस्टैंसिएट करने और उसे निर्देशांक बिंदुओं से भरने का अर्थ है।  
- **कौन सा मेथड जांचता है कि बिंदु लाइन पर स्थित है?** `LineString` पर `Covers` मेथड या `Point` पर `CoveredBy` मेथड का उपयोग करें।  
- **क्या मुझे सैंपल चलाने के लिए लाइसेंस चाहिए?** मूल्यांकन के लिए एक अस्थायी लाइसेंस काम करता है; उत्पादन के लिए पूर्ण लाइसेंस आवश्यक है।  
- **क्या इसे .NET Core के साथ उपयोग किया जा सकता है?** हाँ, Aspose.GIS .NET Framework और .NET Core दोनों का समर्थन करता है।  
- **मैं एक linestring में कितने बिंदु जोड़ सकता हूँ?** कोई कठोर सीमा नहीं है; आप अपनी स्पेशियल विश्लेषण के लिए जितने बिंदु आवश्यक हों, जोड़ सकते हैं।

## create linestring c# क्या है?
`LineString` एक ज्यामितीय आकार है जिसमें बिंदुओं की क्रमबद्ध सूची होती है जो सीधी रेखा खंडों द्वारा जुड़ी होती है। C# में आप इसे `Aspose.Gis.Geometries` नेमस्पेस की `LineString` क्लास को इंस्टैंसिएट करके बनाते हैं और फिर `AddPoint` मेथड का उपयोग करके **linestring में बिंदु जोड़ते** हैं। यह ऑब्जेक्ट किसी भी रैखिक स्पेशियल विश्लेषण, जैसे रूट मैपिंग या नेटवर्क ट्रेसिंग, की नींव के रूप में कार्य करता है।

## लाइन पर बिंदु जांच के लिए Aspose.GIS का उपयोग क्यों करें?
`Covers` एक स्पेशियल प्रेडिकेट मेथड है जो तब true लौटाता है जब पहली ज्यामिति पूरी तरह से दूसरी ज्यामिति को समाहित करती है।  
Aspose.GIS स्पेशियल प्रेडिकेट्स का एक निर्धारक, उच्च‑सटीकता कार्यान्वयन प्रदान करता है। यह 50+ इनपुट और आउटपुट GIS फ़ॉर्मेट्स का समर्थन करता है, पूरे डेटासेट को मेमोरी में लोड किए बिना कई सौ किलोमीटर लंबी लाइन नेटवर्क को संभाल सकता है, और .NET Framework, .NET Core, तथा .NET 5/6+ पर चलता है। इसका `Covers` मेथड उपयोग करने से फ्लोटिंग‑पॉइंट राउंडिंग त्रुटियों को ध्यान में रखा जाता है, जिससे कठिन एंटरप्राइज़ परिदृश्यों में भी विश्वसनीय लाइन‑पर‑बिंदु परिणाम मिलते हैं।

## पूर्वापेक्षाएँ
Aspose.GIS for .NET का उपयोग शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ सेट हैं:

### 1. Visual Studio स्थापित करें
सुनिश्चित करें कि आपके सिस्टम पर Visual Studio स्थापित है। Aspose.GIS for .NET Visual Studio के साथ सहजता से एकीकृत होता है, जिससे विकास का अनुभव सुगम बनता है।

### 2. Aspose.GIS for .NET प्राप्त करें
Aspose.GIS for .NET लाइब्रेरी को [वेबसाइट](https://releases.aspose.com/gis/net/) से डाउनलोड करें। आप लाइब्रेरी को सीधे डाउनलोड कर सकते हैं या NuGet जैसे पैकेज मैनेजर का उपयोग करके इसे अपने प्रोजेक्ट में स्थापित कर सकते हैं।

### 3. .NET Framework की परिचितता
.NET फ्रेमवर्क और C# प्रोग्रामिंग भाषा का बुनियादी ज्ञान Aspose.GIS for .NET का प्रभावी उपयोग करने के लिए आवश्यक है।

### 4. दस्तावेज़ीकरण और समर्थन तक पहुंच
Aspose.GIS APIs और कार्यात्मकताओं के विस्तृत जानकारी के लिए [डॉक्यूमेंटेशन](https://reference.aspose.com/gis/net/) देखें। यदि आपको कोई समस्या आती है या प्रश्न हैं, तो सहायता के लिए [Aspose.GIS फोरम](https://forum.aspose.com/c/gis/33) का उपयोग करें।

### 5. वैकल्पिक: अस्थायी लाइसेंस
यदि आप Aspose.GIS for .NET का परीक्षण कर रहे हैं, तो आप लाइब्रेरी की सुविधाओं का मूल्यांकन करने के लिए [अस्थायी लाइसेंस पेज](https://purchase.aspose.com/temporary-license/) से अस्थायी लाइसेंस प्राप्त कर सकते हैं।

## नामस्थान आयात करें
अपने प्रोजेक्ट में Aspose.GIS for .NET का उपयोग करने से पहले, आपको आवश्यक नामस्थानों को आयात करना होगा:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

अब, हम प्रदान किए गए उदाहरण को कई चरणों में विभाजित करेंगे ताकि Aspose.GIS for .NET का उपयोग करके **ज्यामिति एक अन्य को कवर करती है या नहीं** को समझ सकें।

## linestring c# कैसे बनाएं – चरण‑दर‑चरण मार्गदर्शिका
अपने प्रोजेक्ट को लोड करें, आवश्यक नामस्थानों को आयात करें, और फिर नीचे दिए गए पाँच संक्षिप्त चरणों का पालन करें। कुछ ही कोड लाइनों में आपके पास एक `LineString` ऑब्जेक्ट, एक `Point` ऑब्जेक्ट, और दो बूलियन जांचें होंगी जो बताती हैं कि लाइन बिंदु को कवर करती है या नहीं और बिंदु लाइन द्वारा कवर किया गया है या नहीं।

### चरण 1: linestring ऑब्जेक्ट बनाएं
`LineString` क्लास दो‑आयामी तल में सीधी रेखा खंडों द्वारा जुड़े बिंदुओं की श्रृंखला का प्रतिनिधित्व करती है।  

```csharp
var line = new LineString();
```
यहाँ, हम एक नया `LineString` ऑब्जेक्ट इंस्टैंसिएट करते हैं, जो दो‑आयामी स्थान में जुड़े हुए रेखा खंडों की श्रृंखला का प्रतिनिधित्व करता है।

### चरण 2: linestring में बिंदु जोड़ें
`AddPoint` एक निर्देशांक जोड़ी को `LineString` संग्रह के अंत में जोड़ता है, जिससे सम्मिलन क्रम बना रहता है।  

```csharp
line.AddPoint(0, 0);
line.AddPoint(1, 1);
```
हम `AddPoint` मेथड का उपयोग करके **linestring में बिंदु जोड़ते** हैं। इस उदाहरण में, हम दो बिंदु जोड़ते हैं: (0, 0) और (1, 1), जिससे एक सरल विकर्ण रेखा खंड बनता है।

### चरण 3: point ऑब्जेक्ट बनाएं
`Point` क्लास दो‑आयामी निर्देशांक प्रणाली में एक एकल स्थान को मॉडल करती है।  

```csharp
var point = new Point(0, 0);
```
एक `Point` ऑब्जेक्ट इंस्टैंसिएट करें जो दो‑आयामी स्थान में एक बिंदु का प्रतिनिधित्व करता है। यहाँ, हम (0, 0) निर्देशांक पर एक बिंदु बनाते हैं।

### चरण 4: लाइन पर बिंदु जांच करें – क्या लाइन बिंदु को कवर करती है?
`Covers` निर्धारित करता है कि क्या पहली ज्यामिति पूरी तरह से दूसरी ज्यामिति को समाहित करती है, और केवल तब true लौटाता है जब दूसरी ज्यामिति के सभी बिंदु पहली के भीतर हों।  

```csharp
Console.WriteLine(line.Covers(point));    // True
```
`Covers` मेथड का उपयोग करके जांचें कि क्या लाइन बिंदु को कवर करती है। इस मामले में, यह `True` लौटाता है क्योंकि बिंदु (0, 0) ठीक लाइन पर स्थित है।

### चरण 5: विपरीत संबंध सत्यापित करें – क्या बिंदु लाइन द्वारा कवर किया गया है?
`CoveredBy` `Covers` का उलटा है; यह true लौटाता है जब कॉल करने वाली ज्यामिति पूरी तरह से लक्ष्य ज्यामिति के भीतर हो।  

```csharp
Console.WriteLine(point.CoveredBy(line)); // True
```
इसी तरह, `CoveredBy` मेथड का उपयोग करके जांचें कि क्या बिंदु लाइन द्वारा कवर किया गया है। चूँकि बिंदु (0, 0) लाइन पर स्थित है, यह भी `True` लौटाता है।

## सामान्य समस्याएँ और समाधान
| समस्या | क्यों होता है | समाधान |
|-------|----------------|-----|
| `line.Covers(point)` `False` लौटाता है जबकि बिंदु लाइन पर दिखता है | फ़्लोटिंग‑पॉइंट सटीकता के कारण बिंदु के निर्देशांक बिल्कुल समान नहीं होते। | निर्देशांकों पर `Math.Round` का उपयोग करें या `line.Distance(point) < epsilon` के साथ सहनशीलता‑आधारित जांच लागू करें। |
| `using Aspose.Gis.Geometries;` अनुपलब्ध | नामस्थान आयात नहीं किया गया, जिससे संकलन त्रुटियाँ होती हैं। | आयात कथन मौजूद है यह सुनिश्चित करें (देखें **नामस्थान आयात करें** अनुभाग)। |
| रनटाइम पर लाइसेंस अपवाद | उत्पादन के लिए कोई वैध लाइसेंस लोड नहीं किया गया। | `License license = new License(); license.SetLicense("Aspose.GIS.lic");` का उपयोग करके अस्थायी या पूर्ण लाइसेंस लोड करें। |

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं Aspose.GIS for .NET को अपने व्यावसायिक प्रोजेक्ट्स में उपयोग कर सकता हूँ?**  
A: हाँ, उचित लाइसेंस प्राप्त करने के बाद आप Aspose.GIS for .NET को व्यावसायिक और गैर‑व्यावसायिक दोनों प्रोजेक्ट्स में उपयोग कर सकते हैं।

**Q: क्या Aspose.GIS for .NET .NET Core के साथ संगत है?**  
A: हाँ, Aspose.GIS for .NET .NET Framework और .NET Core दोनों परिवेशों के साथ संगत है।

**Q: क्या Aspose.GIS for .NET विभिन्न GIS फ़ॉर्मेट्स का समर्थन करता है?**  
A: हाँ, Aspose.GIS for .NET कई GIS फ़ॉर्मेट्स का समर्थन करता है जिसमें Shapefile, GeoJSON, KML और अधिक शामिल हैं।

**Q: क्या मैं Aspose.GIS for .NET के विकास में योगदान दे सकता हूँ?**  
A: Aspose.GIS for .NET Aspose द्वारा विकसित एक स्वामित्व वाली लाइब्रेरी है, इसलिए बाहरी योगदान स्वीकार नहीं किए जाते। हालांकि, आप लाइब्रेरी को सुधारने के लिए प्रतिक्रिया और सुझाव दे सकते हैं।

**Q: Aspose.GIS for .NET के अपडेट कितनी बार जारी होते हैं?**  
A: Aspose.GIS for .NET के अपडेट नियमित रूप से जारी किए जाते हैं ताकि नई सुविधाएँ, सुधार और बग फिक्सेस पेश किए जा सकें। नवीनतम रिलीज़ के लिए [वेबसाइट](https://releases.aspose.com/gis/net/) देखें।

## निष्कर्ष
ऊपर दिए गए चरणों का पालन करके, अब आप जानते हैं कि **linestring c# कैसे बनाएं**, **linestring में बिंदु कैसे जोड़ें**, और `Covers` तथा `CoveredBy` मेथड्स का उपयोग करके एक विश्वसनीय **लाइन पर बिंदु जांच** कैसे करें। यह क्षमता आपके सॉफ़्टवेयर की स्पेशियल विश्लेषण सुविधाओं को बढ़ाती है और रूट वैलिडेशन, नेटवर्क टोपोलॉजी जांच, तथा निकटता क्वेरी जैसी अधिक उन्नत GIS ऑपरेशनों का मार्ग खोलती है।

---

**अंतिम अपडेट:** 2026-08-03  
**परीक्षण किया गया:** Aspose.GIS for .NET (latest release)  
**लेखक:** Aspose

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [Aspose.GIS for .NET के साथ LineString ज्योमेट्री बनाना सीखें](/gis/net/geometry-creation/create-linestring-geometry/)
- [Aspose.GIS के साथ LineString में बिंदु जोड़ना और ज्योमेट्री को संपादन योग्य फ़ॉर्मेट में बदलना](/gis/net/geometry-creation/convert-geometry-to-editable/)
- [polygon के अंदर बिंदु c# – ज्योमेट्री एक अन्य को समाहित करती है जांचें](/gis/net/geometry-analysis/check-geometry-contains-another/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}