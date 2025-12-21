---
date: 2025-12-21
description: Aspose.GIS for .NET का उपयोग करके वेक्टर लेयर बनाना, लीनियराइज़ेशन टॉलरेंस
  सेट करना, और लेयर में फीचर जोड़ना सीखें। GeoJSON फ़ाइलों को निर्यात करने के लिए
  इस चरण‑दर‑चरण गाइड का पालन करें।
linktitle: Set Linearization Tolerance
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET का उपयोग करके वेक्टर लेयर बनाएं और लीनियराइज़ेशन टोलरेंस
  सेट करें
url: /hi/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET का उपयोग करके वेक्टर लेयर बनाएं और लीनियराइज़ेशन टॉलरेंस सेट करें

## Introduction
यदि आपको **create vector layer** फ़ाइलें बनानी हैं, कर्व की सटीकता नियंत्रित करनी है, और परिणाम को GeoJSON दस्तावेज़ के रूप में निर्यात करना है, तो Aspose.GIS for .NET इसे सरल बनाता है। इस ट्यूटोरियल में आप सीखेंगे कि GeoJSON विकल्पों को कैसे कॉन्फ़िगर करें, लीनियराइज़ेशन टॉलरेंस सेट करें, और **add feature to layer** ऑब्जेक्ट्स को कैसे जोड़ें—साथ ही कोड को साफ़ और प्रोडक्शन‑रेडी रखें।

## Quick Answers
- **“create vector layer” क्या मतलब है?** यह एक नया GIS वेक्टर डेटासेट बनाता है (जैसे, एक GeoJSON फ़ाइल) जो ज्यामितियों और एट्रिब्यूट्स को संग्रहीत कर सकता है।  
- **टॉलरेंस कैसे सेट करें?** `GeoJsonOptions` की `LinearizationTolerance` प्रॉपर्टी का उपयोग करें।  
- **क्या मैं GeoJSON फ़ाइल निर्यात कर सकता हूँ?** हाँ—सिर्फ `Drivers.GeoJson` ड्राइवर के साथ एक `VectorLayer` बनाएं।  
- **क्या मुझे लाइसेंस चाहिए?** एक वैध Aspose.GIS लाइसेंस सभी फीचर अनलॉक करता है; एक अस्थायी लाइसेंस मूल्यांकन के लिए काम करता है।  
- **कौनसे .NET संस्करण समर्थित हैं?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## “create vector layer” क्या है?
वेक्टर लेयर बनाना मतलब एक नया GIS कंटेनर (जैसे GeoJSON फ़ाइल) को इनिशियलाइज़ करना है जो बिंदु, रेखा, और बहुभुज जैसी ज्यामितीय फीचर को रख सकता है। यह लेयर उन सभी ज्यामितियों और एट्रिब्यूट्स के लिए लक्ष्य बन जाता है जिन्हें आप बनाते हैं और संलग्न करते हैं।

## GeoJSON विकल्पों को कॉन्फ़िगर क्यों करें?
GeoJSON विकल्पों को कॉन्फ़िगर करना—विशेषकर **linearization tolerance**—यह सुनिश्चित करता है कि कर्व्ड ज्यामितियों (जैसे `CircularString`) को ऐसी सटीकता के साथ निकटतम रूप में प्रस्तुत किया जाए जो आपके एप्लिकेशन की सटीकता आवश्यकताओं को पूरा करे। यह चरण तब महत्वपूर्ण हो जाता है जब आप बाद में **export GeoJSON file** वेब मैप्स या स्पेशियल एनालिसिस में उपयोग के लिए करते हैं।

## आवश्यकताएँ
1. **Visual Studio** स्थापित है (कोई भी नवीनतम संस्करण)।  
2. **Aspose.GIS license** (या एक अस्थायी मूल्यांकन कुंजी)।  
3. **Aspose.GIS for .NET** लाइब्रेरी डाउनलोड की गई है और आपके प्रोजेक्ट में रेफ़रेंस की गई है।  
4. **C#** की बुनियादी परिचितता।

## नेमस्पेस इम्पोर्ट करें
पहले, आवश्यक नेमस्पेस इम्पोर्ट करें ताकि कंपाइलर को पता चल सके कि GIS क्लासेज़ कहाँ मिलेंगी:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## चरण‑दर‑चरण गाइड

### चरण 1: GeoJSON विकल्प कॉन्फ़िगर करें (टॉलरेंस कैसे सेट करें)
हम एक `GeoJsonOptions` ऑब्जेक्ट बनाएँगे और Aspose.GIS को बताएँगे कि लीनियराइज़्ड ज्यामिति को मूल कर्व से कितनी निकट होना चाहिए।

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### चरण 2: आउटपुट पाथ निर्धारित करें (GeoJSON कैसे निर्यात करें)
निर्दिष्ट करें कि परिणामी फ़ाइल कहाँ सहेजी जाएगी। प्लेसहोल्डर को अपने वास्तविक फ़ोल्डर से बदलें।

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### चरण 3: कॉन्फ़िगर किए गए विकल्पों के साथ **Create Vector Layer**
अब हम वास्तव में `VectorLayer.Create` मेथड का उपयोग करके **create vector layer** करेंगे। `using` ब्लॉक संसाधनों के उचित निपटान को सुनिश्चित करता है।

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### चरण 4: जियोमेट्री बनाएं (जैसे, एक circular string)
यहाँ हम एक नमूना जियोमेट्री बनाते हैं—एक `CircularString`। आप इसे किसी भी वैध WKT से बदल सकते हैं।

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### चरण 5: **Add Feature to Layer** और सहेजें
अंत में, हम एक फीचर बनाते हैं, जियोमेट्री असाइन करते हैं, और इसे लेयर में जोड़ते हैं। यह **add feature to layer** ऑपरेशन का मुख्य भाग है।

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

जब `using` ब्लॉक समाप्त होता है, तो लेयर स्वचालित रूप से `path` में परिभाषित फ़ाइल में लिखी जाती है, जिससे आपको एक तैयार‑उपयोग GeoJSON फ़ाइल मिलती है।

## सामान्य समस्याएँ और सुझाव
- **Incorrect path** – सुनिश्चित करें कि डायरेक्टरी मौजूद है और आपके पास लिखने की अनुमति है।  
- **Tolerance too low** – `LinearizationTolerance` को बहुत छोटे मान पर सेट करने से फ़ाइल आकार बहुत बढ़ सकता है। अपनी सटीकता आवश्यकताओं के अनुसार समायोजित करें।  
- **License errors** – यदि आप लाइसेंसिंग चेतावनियाँ देखते हैं, तो किसी भी Aspose.GIS कॉल से पहले लाइसेंस फ़ाइल को सही ढंग से लोड किया गया है, यह सत्यापित करें।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या Aspose.GIS for .NET अन्य .NET फ्रेमवर्क्स के साथ संगत है?**  
A: हाँ, यह .NET Framework, .NET Core, और .NET 5/6/7 के साथ काम करता है।

**Q: क्या मैं Aspose.GIS को व्यावसायिक प्रोजेक्ट्स में उपयोग कर सकता हूँ?**  
A: बिल्कुल। एक व्यावसायिक लाइसेंस सभी मूल्यांकन प्रतिबंधों को हटा देता है।

**Q: क्या Aspose.GIS GeoJSON के अलावा अन्य GIS फ़ॉर्मैट्स का समर्थन करता है?**  
A: हाँ, यह Shapefile, KML, GML, और कई अन्य को सपोर्ट करता है।

**Q: क्या कोई ट्रायल संस्करण उपलब्ध है?**  
A: आप Aspose वेबसाइट से एक मुफ्त ट्रायल डाउनलोड कर सकते हैं।

**Q: मुझे समर्थन कहाँ मिल सकता है?**  
A: Aspose फ़ोरम या संसाधन सेक्शन में समर्थन लिंक का उपयोग करें।

## निष्कर्ष
इन चरणों का पालन करके अब आप जानते हैं कि **create vector layer** कैसे बनाएं, लीनियराइज़ेशन टॉलरेंस को कॉन्फ़िगर करें, और **add feature to layer** करके सहज **export GeoJSON file** निर्माण करें। अतिरिक्त जियोमेट्री प्रकारों और एट्रिब्यूट हैंडलिंग का अन्वेषण करें ताकि आप अपने .NET GIS प्रोजेक्ट्स में Aspose.GIS का पूर्ण लाभ उठा सकें।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**अंतिम अपडेट:** 2025-12-21  
**परीक्षित संस्करण:** Aspose.GIS 24.11 for .NET  
**लेखक:** Aspose