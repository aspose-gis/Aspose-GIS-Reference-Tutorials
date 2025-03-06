---
title: फ़ीचर विशेषता मान प्राप्त करें (डिफ़ॉल्ट)
linktitle: फ़ीचर विशेषता मान प्राप्त करें (डिफ़ॉल्ट)
second_title: Aspose.GIS .NET एपीआई
description: .NET के लिए Aspose.GIS की शक्ति अनलॉक करें! इस चरण-दर-चरण मार्गदर्शिका के साथ सुविधा विशेषता मानों को आसानी से पुनर्प्राप्त और हेरफेर करें। अपना परीक्षण अभी डाउनलोड करें!
weight: 14
url: /hi/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# फ़ीचर विशेषता मान प्राप्त करें (डिफ़ॉल्ट)

## परिचय
.NET के लिए Aspose.GIS की दुनिया में आपका स्वागत है! इस व्यापक मार्गदर्शिका में, हम Aspose.GIS की शक्तिशाली क्षमताओं का उपयोग करके फीचर विशेषता मानों को पुनर्प्राप्त करने की जटिलताओं के बारे में जानेंगे। चाहे आप एक अनुभवी डेवलपर हों या अभी शुरुआत कर रहे हों, यह ट्यूटोरियल आपको चरण-दर-चरण पूर्वाभ्यास प्रदान करेगा, यह सुनिश्चित करते हुए कि आप इस उल्लेखनीय टूल की पूरी क्षमता का उपयोग करें।
## आवश्यक शर्तें
इससे पहले कि हम इस कोडिंग साहसिक कार्य को शुरू करें, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
- C# और .NET फ्रेमवर्क का कार्यसाधक ज्ञान।
-  .NET के लिए Aspose.GIS स्थापित। यदि नहीं, तो इसे यहां से डाउनलोड करें[यहाँ](https://releases.aspose.com/gis/net/).
- एक कोड संपादक, जैसे विज़ुअल स्टूडियो, निर्बाध रूप से अनुसरण करने के लिए।
## नामस्थान आयात करें
अपने C# प्रोजेक्ट में, आवश्यक नामस्थान शामिल करना सुनिश्चित करें:
```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
अब, आइए प्रत्येक उदाहरण को पालन करने में आसान चरणों की श्रृंखला में विभाजित करें।
## फ़ीचर विशेषता मान प्राप्त करें (डिफ़ॉल्ट)
### चरण 1: पर्यावरण स्थापित करें
अपनी दस्तावेज़ निर्देशिका का पथ परिभाषित करके प्रारंभ करें:
```csharp
string dataDir = "Your Document Directory";
```
### चरण 2: एक जियोसन लेयर बनाएं
एक जियोसन परत बनाएं और डिफ़ॉल्ट मानों के साथ एक विशेषता परिभाषित करें:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```
### चरण 3: एक फ़ीचर का निर्माण करें
परिभाषित विशेषता का उपयोग करके एक सुविधा का निर्माण करें:
```csharp
    Feature feature = layer.ConstructFeature();
```
### चरण 4: मान पुनर्प्राप्त करें
विभिन्न परिदृश्यों के साथ विशेषता मान पुनर्प्राप्त करें:
```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // मान == शून्य
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // मान == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // मान == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```
## डिफ़ॉल्ट मान सेट करना
### चरण 1: एक और जियोसन लेयर बनाएं
एक अलग जियोसन परत और एक दोहरी विशेषता के साथ प्रक्रिया को दोहराएं:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```
### चरण 2: एक फ़ीचर का निर्माण करें (फिर से)
```csharp
    Feature feature = layer.ConstructFeature();
```
### चरण 3: मान पुनर्प्राप्त करें और सेट करें
डिफ़ॉल्ट प्रदर्शित करते हुए विशेषता मान पुनर्प्राप्त करें और सेट करें:
```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); // मान == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); // मान == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); // मान == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```
बधाई हो! आपने फीचर विशेषता मानों को पुनः प्राप्त करने और उनमें हेरफेर करने में .NET के लिए Aspose.GIS की शक्ति का सफलतापूर्वक उपयोग किया है।
## निष्कर्ष
इस ट्यूटोरियल में, हमने .NET के लिए Aspose.GIS का उपयोग करके फीचर विशेषता मान पुनर्प्राप्त करने की बारीकियों का पता लगाया है। अपनी सहज एपीआई और मजबूत क्षमताओं के साथ, Aspose.GIS .NET वातावरण में GIS विकास के लिए संभावनाओं की दुनिया खोलता है।
## अक्सर पूछे जाने वाले प्रश्नों
### क्या Aspose.GIS .NET कोर के साथ संगत है?
हां, Aspose.GIS .NET कोर के साथ पूरी तरह से संगत है, जो क्रॉस-प्लेटफ़ॉर्म समर्थन प्रदान करता है।
### क्या मैं व्यावसायिक परियोजनाओं के लिए Aspose.GIS का उपयोग कर सकता हूँ?
बिल्कुल! Aspose.GIS एक वाणिज्यिक लाइसेंस के साथ आता है जो आपको इसे बिना किसी प्रतिबंध के अपने व्यावसायिक अनुप्रयोगों में उपयोग करने की अनुमति देता है।
### मुझे अतिरिक्त सहायता और संसाधन कहां मिल सकते हैं?
 दौरा करना[Aspose.GIS फोरम](https://forum.aspose.com/c/gis/33) सामुदायिक समर्थन के लिए और अन्वेषण करें[प्रलेखन](https://reference.aspose.com/gis/net/) गहन जानकारी के लिए.
### क्या कोई निःशुल्क परीक्षण उपलब्ध है?
 हाँ, आप नि:शुल्क परीक्षण के साथ Aspose.GIS का अन्वेषण कर सकते हैं। इसे डाउनलोड करें[यहाँ](https://releases.aspose.com/).
### मैं परीक्षण प्रयोजनों के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूँ?
 अस्थायी लाइसेंस के लिए, यहां जाएं[यहाँ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
