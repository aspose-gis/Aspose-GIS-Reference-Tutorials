---
title: .NET के लिए Aspose.GIS के साथ स्ट्रीम से जियोसन पढ़ना
linktitle: स्ट्रीम से जियोजसन पढ़ें
second_title: Aspose.GIS .NET एपीआई
description: .NET के लिए Aspose.GIS का उपयोग करके स्ट्रीम से जियोजसन को पढ़ने का तरीका जानें। अपने अनुप्रयोगों में भू-स्थानिक के निर्बाध एकीकरण के लिए हमारी चरण-दर-चरण मार्गदर्शिका का पालन करें।
weight: 14
url: /hi/net/layer-data-operations/read-geojson-from-stream/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET के लिए Aspose.GIS के साथ स्ट्रीम से जियोसन पढ़ना

## परिचय
एक स्ट्रीम से जियोजसन को पढ़ने के लिए .NET के लिए Aspose.GIS का उपयोग करने पर हमारी चरण-दर-चरण मार्गदर्शिका में आपका स्वागत है। Aspose.GIS एक शक्तिशाली एपीआई है जो .NET अनुप्रयोगों को भू-स्थानिक क्षमताएं प्रदान करता है, जिससे आप विभिन्न जीआईएस प्रारूपों के साथ निर्बाध रूप से काम कर सकते हैं। इस ट्यूटोरियल में, हम आपको Aspose.GIS का उपयोग करके एक स्ट्रीम से जियोसन डेटा पढ़ने की प्रक्रिया के बारे में बताएंगे, स्पष्टता और समझने में आसानी के लिए प्रत्येक चरण को तोड़ेंगे।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
1. C# का बुनियादी ज्ञान: आपको C# प्रोग्रामिंग भाषा और इसके सिंटैक्स से परिचित होना चाहिए।
2.  Aspose.GIS की स्थापना: सुनिश्चित करें कि आपने .NET के लिए Aspose.GIS स्थापित किया है। यदि नहीं, तो आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/gis/net/).
3. विकास परिवेश: अपना पसंदीदा विकास परिवेश सेट करें, जैसे विज़ुअल स्टूडियो या जेटब्रेन राइडर।

## नामस्थान आयात करें
आरंभ करने के लिए, आइए आपके C# कोड में आवश्यक नामस्थान आयात करें:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## चरण 1: जियोसन डेटा को परिभाषित करें
सबसे पहले, हमें अपने C# कोड में जियोसन डेटा को एक स्ट्रिंग के रूप में परिभाषित करने की आवश्यकता है। उदाहरण के लिए:
```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```
## चरण 2: स्ट्रीम से जियोजसन पढ़ें
इसके बाद, हम Aspose.GIS का उपयोग करके एक स्ट्रीम से जियोसन डेटा पढ़ेंगे:
```csharp
using (var memoryStream = new MemoryStream(Encoding.UTF8.GetBytes(geoJson)))
using (var layer = VectorLayer.Open(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    Console.WriteLine(layer.Count); // आउटपुट: 2
    Console.WriteLine(layer[1].GetValue<string>("name")); // आउटपुट: मैरी
}
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.GIS का उपयोग करके स्ट्रीम से जियोजसन डेटा कैसे पढ़ा जाए। ऊपर बताए गए चरणों का पालन करके, आप भू-स्थानिक क्षमताओं को अपने .NET अनुप्रयोगों में आसानी से एकीकृत कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या Aspose.GIS अन्य GIS प्रारूपों के साथ संगत है?
हाँ, Aspose.GIS विभिन्न GIS प्रारूपों जैसे कि जियोसन, शेपफाइल, KML और बहुत कुछ का समर्थन करता है।
### क्या मैं खरीदने से पहले Aspose.GIS आज़मा सकता हूँ?
 हां, आप Aspose.GIS का निःशुल्क परीक्षण यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मुझे Aspose.GIS के लिए दस्तावेज़ कहाँ मिल सकते हैं?
 आप Aspose.GIS के लिए दस्तावेज़ पा सकते हैं[यहाँ](https://reference.aspose.com/gis/net/).
### मैं Aspose.GIS के लिए समर्थन कैसे प्राप्त कर सकता हूँ?
 आप Aspose मंचों पर Aspose.GIS के लिए समर्थन प्राप्त कर सकते हैं[यहाँ](https://forum.aspose.com/c/gis/33).
### क्या मुझे Aspose.GIS का उपयोग करने के लिए अस्थायी लाइसेंस की आवश्यकता है?
 आप Aspose.GIS के लिए एक अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
