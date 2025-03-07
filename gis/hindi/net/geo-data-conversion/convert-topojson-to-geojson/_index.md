---
title: TopoJSON को जियोJSON में बदलें
linktitle: TopoJSON को जियोJSON में बदलें
second_title: Aspose.GIS .NET एपीआई
description: जानें कि .NET के लिए Aspose.GIS का उपयोग करके TopoJSON को जियोJSON में कैसे परिवर्तित किया जाए। कुशल भौगोलिक डेटा प्रबंधन के लिए हमारे चरण-दर-चरण ट्यूटोरियल का पालन करें।
weight: 16
url: /hi/net/geo-data-conversion/convert-topojson-to-geojson/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# TopoJSON को जियोJSON में बदलें

## परिचय
इस ट्यूटोरियल में, हम .NET के लिए Aspose.GIS का उपयोग करके TopoJSON से जियोJSON में रूपांतरण प्रक्रिया के बारे में विस्तार से जानेंगे। Aspose.GIS एक शक्तिशाली एपीआई है जिसे .NET अनुप्रयोगों के भीतर भौगोलिक सूचना प्रसंस्करण की सुविधा के लिए डिज़ाइन किया गया है। TopoJSON और जियोJSON भौगोलिक डेटा का प्रतिनिधित्व करने के लिए व्यापक रूप से उपयोग किए जाने वाले प्रारूप हैं, और उनके बीच परिवर्तित करने में सक्षम होना विभिन्न जीआईएस अनुप्रयोगों के लिए आवश्यक है।
## आवश्यक शर्तें
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यकताएँ हैं:
1.  .NET के लिए Aspose.GIS: सुनिश्चित करें कि आपने .NET लाइब्रेरी के लिए Aspose.GIS को डाउनलोड और इंस्टॉल कर लिया है। आप इसे यहां से डाउनलोड कर सकते हैं[Aspose.GIS वेबसाइट](https://releases.aspose.com/gis/net/).
2. विकास परिवेश: आपको .NET स्थापित के साथ एक कार्यशील विकास परिवेश की आवश्यकता है।
3. नमूना TopoJSON फ़ाइल: रूपांतरण के लिए एक नमूना TopoJSON फ़ाइल तैयार रखें। यदि आपके पास कोई नहीं है, तो आप इसे विभिन्न स्रोतों से बना या प्राप्त कर सकते हैं।

## नामस्थान आयात करें
रूपांतरण के साथ आगे बढ़ने से पहले, अपने प्रोजेक्ट में आवश्यक नामस्थान आयात करें। ये नामस्थान TopoJSON से जियोJSON रूपांतरण के लिए आवश्यक कार्यक्षमता तक पहुंच प्रदान करेंगे।

   ```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

अब जब आपने अपना परिवेश स्थापित कर लिया है और आवश्यक नामस्थान आयात कर लिया है, तो आइए TopoJSON को जियोJSON में परिवर्तित करने की प्रक्रिया को चरण-दर-चरण निर्देशों में विभाजित करें।
## चरण 1: इनपुट और आउटपुट पथ निर्दिष्ट करें

इनपुट TopoJSON फ़ाइल और आउटपुट जियोJSON फ़ाइल के लिए पथ परिभाषित करें।
```csharp
var sampleTopoJsonPath = "Your Document Directory" + "sample.topojson";
var outputFilePath = "Your Document Directory" + "convertedSample_out.geojson";
```
##  चरण 2: रूपांतरण का उपयोग करें`VectorLayer.Convert` method to convert TopoJSON to GeoJSON.
```csharp
VectorLayer.Convert(sampleTopoJsonPath, Drivers.TopoJson, outputFilePath, Drivers.GeoJson);
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने पता लगाया कि .NET के लिए Aspose.GIS का उपयोग करके TopoJSON को जियोJSON में कैसे परिवर्तित किया जाए। उल्लिखित चरणों का पालन करके और Aspose.GIS लाइब्रेरी का उपयोग करके, आप अपने .NET अनुप्रयोगों के भीतर भौगोलिक डेटा रूपांतरणों को सहजता से संभाल सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या Aspose.GIS बड़े भौगोलिक डेटासेट को संभाल सकता है?
हां, Aspose.GIS इष्टतम प्रदर्शन सुनिश्चित करते हुए बड़े भौगोलिक डेटासेट को कुशलतापूर्वक संसाधित करने में सक्षम है।
### क्या Aspose.GIS विभिन्न GIS फ़ाइल स्वरूपों के साथ संगत है?
बिल्कुल, Aspose.GIS GIS फ़ाइल स्वरूपों की एक विस्तृत श्रृंखला का समर्थन करता है, जिसमें TopoJSON, जियोJSON, शेपफाइल और बहुत कुछ शामिल हैं।
### क्या Aspose.GIS दस्तावेज़ीकरण और सहायता प्रदान करता है?
 हाँ, व्यापक दस्तावेज़ीकरण और सहायता इसके माध्यम से उपलब्ध है[Aspose.GIS फोरम](https://forum.aspose.com/c/gis/33).
### क्या मैं खरीदने से पहले Aspose.GIS आज़मा सकता हूँ?
 हाँ, आप नि:शुल्क परीक्षण का लाभ उठा सकते हैं[Aspose वेबसाइट](https://releases.aspose.com/).
### मैं Aspose.GIS के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूँ?
 आप से अस्थायी लाइसेंस प्राप्त कर सकते हैं[Aspose खरीद पृष्ठ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
