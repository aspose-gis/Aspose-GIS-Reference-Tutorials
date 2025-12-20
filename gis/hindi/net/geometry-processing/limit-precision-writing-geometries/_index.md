---
date: 2025-12-20
description: Aspose.GIS for .NET का उपयोग करके ज्यामितियों को लिखते समय सटीकता को
  सीमित करना सीखें। यह चरण‑दर‑चरण गाइड आपको सटीक निर्देशांक नियंत्रण के साथ स्थानिक
  डेटा प्रबंधित करने में मदद करता है।
linktitle: Limit Precision Writing Geometries
second_title: Aspose.GIS .NET API
title: Aspose.GIS के साथ ज्यामितियों को लिखते समय सटीकता को कैसे सीमित करें
url: /hi/net/geometry-processing/limit-precision-writing-geometries/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS के साथ ज्यामितियों को लिखते समय सटीकता को सीमित कैसे करें

यदि आप .NET GIS एप्लिकेशन में ज्यामितियों को लिखते समय **सटीकता को कैसे सीमित करें** के बारे में सोच रहे हैं, तो Aspose.GIS for .NET समन्वय (coordinate) राउंडिंग को नियंत्रित करने का एक सरल, उच्च‑प्रदर्शन तरीका प्रदान करता है। इस ट्यूटोरियल में हम पूरी प्रक्रिया को चरण‑दर‑चरण देखेंगे—पर्यावरण सेटअप से लेकर यह सत्यापित करने तक कि आउटपुट आपके द्वारा निर्धारित सटीकता नियमों का पालन करता है।

## त्वरित उत्तर
- **“limit precision” का क्या अर्थ है?** यह स्पैशियल फ़ाइल लिखते समय समन्वय मानों को परिभाषित संख्या के दशमलव अंकों तक राउंड करता है।  
- **उदाहरण में कौन सा फ़ॉर्मेट उपयोग किया गया है?** GeoJSON, लेकिन वही विकल्प अन्य समर्थित फ़ॉर्मेट्स पर भी लागू होते हैं।  
- **क्या इसे आज़माने के लिए लाइसेंस आवश्यक है?** विकास और परीक्षण के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए एक व्यावसायिक लाइसेंस आवश्यक है।  
- **कौन से .NET संस्करण समर्थित हैं?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7।  
- **क्या मैं Z‑समन्वय की सटीकता को अलग से नियंत्रित कर सकता हूँ?** हाँ—सटीक या राउंडेड मान सेट करने के लिए `ZPrecisionModel` का उपयोग करें।

## ज्यामितियों को लिखते समय सटीकता को कैसे सीमित करें
सटीकता को सीमित करना आवश्यक है जब आपको विभिन्न GIS टूल्स के बीच निरंतर समन्वय प्रतिनिधित्व चाहिए, फ़ाइल आकार कम करना हो, या डेटा‑एक्सचेंज मानकों का पालन करना हो। नीचे हम सटीकता विकल्पों को परिभाषित करेंगे, एक ज्यामिति लिखेंगे, और फिर राउंडिंग की पुष्टि करने के लिए उसे पढ़ेंगे।

## पूर्वापेक्षाएँ

### 1. डाउनलोड और इंस्टॉलेशन
आधिकारिक साइट से नवीनतम Aspose.GIS for .NET पैकेज प्राप्त करें: [download link](https://releases.aspose.com/gis/net/). इंस्टॉलेशन गाइड का पालन करके अपने प्रोजेक्ट में NuGet पैकेज जोड़ें।

### 2. नेमस्पेस इम्पोर्ट
आवश्यक नेमस्पेस जोड़ें ताकि आप GIS क्लासेस और हेल्पर यूटिलिटीज़ तक पहुंच सकें।

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

## स्टेप‑बाय‑स्टेप गाइड

### स्टेप 1: सटीकता विकल्प निर्धारित करें
`GeoJsonOptions` का एक इंस्टेंस बनाएं और Aspose.GIS को बताएं कि आप X/Y और Z समन्वयों के लिए कितने दशमलव अंकों की आवश्यकता रखते हैं।

```csharp
var options = new GeoJsonOptions
{
    // Limit X and Y coordinates to 3 fractional digits.
    XYPrecisionModel = PrecisionModel.Rounding(3),

    // Write all fractional digits of the Z coordinate.
    ZPrecisionModel = PrecisionModel.Exact
};
```

### स्टेप 2: आउटपुट पाथ सेट करें
निर्दिष्ट करें कि परिणामी GeoJSON फ़ाइल कहाँ सहेजी जाएगी।

```csharp
var path = "Your Document Directory" + "LimitPrecisionWhenWritingGeometries_out.json";
```

### स्टेप 3: ज्यामिति बनाएं और भरें
ऊपर परिभाषित विकल्पों के साथ एक नया `VectorLayer` खोलें, एक `Point` ज्यामिति बनाएं, और उसे लेयर में जोड़ें।

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

### स्टेप 4: सटीकता पढ़ें और सत्यापित करें
आपने अभी जो फ़ाइल बनाई है उसे खोलें और समन्वय प्रिंट करें। आपको X/Y मान तीन दशमलव स्थानों तक राउंडेड दिखने चाहिए, जबकि Z मान सटीक रहेगा।

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.GeoJson))
{
    var point = (IPoint)layer[0].Geometry;

    // Output: 1.889, 1.001, 1.123456789
    Console.WriteLine("{0}, {1}, {2}", point.X, point.Y, point.Z);
}
```

## सामान्य समस्याएँ और टिप्स
- **पाथ त्रुटियाँ:** `path` में डायरेक्टरी मौजूद है यह सुनिश्चित करें या सुरक्षित फ़ाइल पाथ बनाने के लिए `Path.Combine` को `Environment.CurrentDirectory` के साथ उपयोग करें।  
- **सटीकता लागू नहीं हुई:** लेयर बनाते समय `GeoJsonOptions` ऑब्जेक्ट पास किया गया है यह सत्यापित करें; अन्यथा डिफ़ॉल्ट सटीकता (पूर्ण डबल) उपयोग की जाएगी।  
- **बड़े डेटा सेट:** बड़े ऑपरेशन्स के लिए, एक ही `VectorLayer` इंस्टेंस को पुन: उपयोग करने और बैच‑ऐडिंग फीचर्स करने पर विचार करें ताकि प्रदर्शन बेहतर हो।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या Aspose.GIS for .NET अन्य GIS फ़ॉर्मेट्स के साथ संगत है?**  
A: हाँ, यह Shapefile, GeoJSON, KML, GML, और कई अन्य को समर्थन देता है, जिससे फ़ॉर्मेट्स के बीच सहज रूपांतरण संभव होता है।

**Q: क्या मैं Aspose.GIS for .NET को खरीदने से पहले आज़मा सकता हूँ?**  
A: बिल्कुल। डाउनलोड पेज से एक मुफ्त ट्रायल उपलब्ध है, जो आपको मूल्यांकन के लिए सभी फीचर्स तक पूर्ण पहुँच देता है।

**Q: परीक्षण के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?**  
A: Aspose लाइसेंस पोर्टल के माध्यम से अस्थायी मूल्यांकन लाइसेंस उत्पन्न किए जा सकते हैं; वे 30 दिनों के लिए वैध होते हैं।

**Q: यदि मुझे समस्याएँ आती हैं तो मदद कहाँ से मिल सकती है?**  
A: Aspose.GIS फ़ोरम और Stack Overflow टैग `aspose-gis` प्रश्न पूछने और सामुदायिक समाधान खोजने के लिए बेहतरीन स्थान हैं।

**Q: क्या लाइब्रेरी छोटे स्क्रिप्ट्स और एंटरप्राइज़‑स्तर के एप्लिकेशन्स दोनों के लिए काम करती है?**  
A: हाँ, Aspose.GIS को तेज़ प्रोटोटाइप से लेकर उच्च‑थ्रूपुट सर्वर एप्लिकेशन्स तक सब कुछ संभालने के लिए डिज़ाइन किया गया है।

## निष्कर्ष
उपरोक्त चरणों का पालन करके, अब आप जानते हैं **ज्यामितियों को लिखते समय सटीकता को कैसे सीमित करें** Aspose.GIS for .NET के साथ। समन्वय राउंडिंग को नियंत्रित करने से आपका स्पैशियल डेटा साफ़, इंटरऑपरेबल और स्टोरेज‑कुशल रहता है—जो किसी भी GIS‑केंद्रित प्रोजेक्ट के लिए मुख्य लाभ हैं।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**अंतिम अपडेट:** 2025-12-20  
**परीक्षण किया गया:** Aspose.GIS 24.11 for .NET  
**लेखक:** Aspose