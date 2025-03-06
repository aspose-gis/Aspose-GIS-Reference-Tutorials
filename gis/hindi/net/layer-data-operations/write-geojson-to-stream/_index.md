---
title: स्ट्रीम करने के लिए जियोजसन लिखें
linktitle: स्ट्रीम करने के लिए जियोजसन लिखें
second_title: Aspose.GIS .NET एपीआई
description: .NET के लिए Aspose.GIS की शक्ति का अन्वेषण करें! सहजता से स्ट्रीम करने के लिए जियोजसन लिखें। निर्बाध भू-स्थानिक एकीकरण के लिए अभी डाउनलोड करें।
weight: 25
url: /hi/net/layer-data-operations/write-geojson-to-stream/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# स्ट्रीम करने के लिए जियोजसन लिखें

## परिचय
क्या आप Aspose.GIS का उपयोग करके अपने .NET एप्लिकेशन में जियोजसन की शक्ति का उपयोग करना चाह रहे हैं? खैर, आप सही जगह पर हैं! यह चरण-दर-चरण मार्गदर्शिका आपको .NET के लिए Aspose.GIS की मजबूत क्षमताओं का लाभ उठाते हुए, एक स्ट्रीम में जियोजसन लिखने की प्रक्रिया से गुजराएगी।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
1. .NET लाइब्रेरी के लिए Aspose.GIS: सुनिश्चित करें कि आपके पास .NET लाइब्रेरी के लिए Aspose.GIS स्थापित है। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/gis/net/).
2. दस्तावेज़ निर्देशिका: अपने प्रोजेक्ट में एक दस्तावेज़ निर्देशिका स्थापित करें और उसका पथ नोट कर लें।
अब, आइए ट्यूटोरियल के साथ शुरुआत करें!
## नामस्थान आयात करें
सबसे पहली बात, अपने कोड में Aspose.GIS कार्यात्मकताओं तक पहुँचने के लिए आवश्यक नामस्थान शामिल करना सुनिश्चित करें:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```
## चरण 1: दस्तावेज़ निर्देशिका सेट करें
```csharp
string dataDir = "Your Document Directory";
```
"आपकी दस्तावेज़ निर्देशिका" को अपनी दस्तावेज़ निर्देशिका के वास्तविक पथ से बदलें।
## चरण 2: एक मेमोरी स्ट्रीम बनाएं
```csharp
using (var memoryStream = new MemoryStream())
{
    // अगले चरणों के लिए कोड यहां दिया गया है
}
```
## चरण 3: जियोसन ड्राइवर के साथ एक वेक्टर लेयर बनाएं
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // अगले चरणों के लिए कोड यहां दिया गया है
}
```
## चरण 4: फ़ीचर विशेषताओं को परिभाषित करें
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```
## चरण 5: सुविधाएँ बनाएँ और जोड़ें
```csharp
// पहली विशेषता
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);
// दूसरी विशेषता
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```
## चरण 6: जियोसन आउटपुट प्रदर्शित करें
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```
बधाई हो! आपने .NET के लिए Aspose.GIS का उपयोग करके एक स्ट्रीम में जियोजसन को सफलतापूर्वक लिखा है।
## निष्कर्ष
इस ट्यूटोरियल में, हमने आपके प्रोजेक्ट में .NET के लिए Aspose.GIS को एकीकृत करने के बुनियादी चरणों को कवर किया है, विशेष रूप से एक स्ट्रीम में जियोजसन लिखने पर ध्यान केंद्रित किया है। इन सरल लेकिन शक्तिशाली चरणों के साथ, आप अपने एप्लिकेशन की भू-स्थानिक क्षमताओं को बढ़ा सकते हैं।
## अक्सर पूछे जाने वाले प्रश्नों
### क्या मैं Windows और Linux दोनों परिवेशों में .NET के लिए Aspose.GIS का उपयोग कर सकता हूँ?
हां, .NET के लिए Aspose.GIS विंडोज और लिनक्स दोनों सिस्टम के साथ संगत है।
### क्या कोई निःशुल्क परीक्षण उपलब्ध है?
 बिल्कुल! आप नि:शुल्क परीक्षण का पता लगा सकते हैं[यहाँ](https://releases.aspose.com/).
### मुझे विस्तृत दस्तावेज कहां मिल सकते हैं?
 दस्तावेज़ीकरण की जाँच करें[यहाँ](https://reference.aspose.com/gis/net/).
### मैं अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूँ?
 अस्थायी लाइसेंस उपलब्ध हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
### सहायता की आवश्यकता है या आपके पास और प्रश्न हैं?
 हमारे सहायता मंच पर जाएँ[यहाँ](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
