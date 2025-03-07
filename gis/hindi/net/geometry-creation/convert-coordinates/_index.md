---
title: Aspose.GIS के साथ रूपांतरण समन्वयित करें
linktitle: निर्देशांक परिवर्तित करें
second_title: Aspose.GIS .NET एपीआई
description: जानें कि .NET के लिए Aspose.GIS के साथ निर्देशांक कैसे परिवर्तित करें। चरण-दर-चरण मार्गदर्शिका, पूर्वापेक्षाएँ और अक्सर पूछे जाने वाले प्रश्न प्रदान किए गए।
weight: 25
url: /hi/net/geometry-creation/convert-coordinates/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS के साथ रूपांतरण समन्वयित करें

## परिचय
इस ट्यूटोरियल में, हम .NET के लिए शक्तिशाली Aspose.GIS लाइब्रेरी का उपयोग करके भौगोलिक सूचना प्रणाली (GIS) की दुनिया में गहराई से उतरेंगे। Aspose.GIS एक व्यापक टूलकिट है जो डेवलपर्स को स्थानिक डेटा के साथ सहजता से काम करने का अधिकार देता है। चाहे आप एक अनुभवी डेवलपर हों या अभी शुरुआत कर रहे हों, यह ट्यूटोरियल आपको निर्देशांक को प्रभावी ढंग से परिवर्तित करने के लिए Aspose.GIS का उपयोग करने की प्रक्रिया में मार्गदर्शन करेगा।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
1. C# का बुनियादी ज्ञान: दिए गए कोड उदाहरणों को समझने और लागू करने के लिए C# प्रोग्रामिंग भाषा से परिचित होना आवश्यक है।
  
2.  Aspose.GIS की स्थापना: सुनिश्चित करें कि आपने .NET के लिए Aspose.GIS लाइब्रेरी को डाउनलोड और इंस्टॉल कर लिया है। आप इसे यहां से डाउनलोड कर सकते हैं[Aspose.GIS वेबसाइट](https://releases.aspose.com/gis/net/).

## नामस्थान आयात करें
शुरू करने से पहले, आइए Aspose.GIS की कार्यक्षमताओं तक पहुँचने के लिए आवश्यक नामस्थान आयात करें:
```csharp
using System;
using Aspose.Gis;
```

आइए स्पष्ट समझ के लिए दिए गए उदाहरण को कई चरणों में तोड़ें:
## चरण 1: रूपांतरण प्रक्रिया प्रारंभ करें
```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```
यह पंक्ति बस एक संदेश प्रदर्शित करती है जो समन्वय रूपांतरण प्रक्रिया की शुरुआत का संकेत देती है।
## चरण 2: दशमलव डिग्री में कनवर्ट करें
```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```
 यहां, हम निर्देशांक (25.5, 45.5) को दशमलव डिग्री प्रारूप में परिवर्तित करते हैं`AsPointText` विधि के साथ`PointFormats.DecimalDegrees` पैरामीटर. फिर परिणाम कंसोल पर मुद्रित होता है।
## चरण 3: डिग्री दशमलव मिनटों में बदलें
```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```
यह चरण निर्देशांक को डिग्री दशमलव मिनट प्रारूप में परिवर्तित करता है और परिणाम प्रिंट करता है।
## चरण 4: डिग्री मिनट सेकंड में कनवर्ट करें
```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```
इसी प्रकार, हम निर्देशांक को डिग्री मिनट सेकंड प्रारूप में परिवर्तित करते हैं और आउटपुट प्रदर्शित करते हैं।
## चरण 5: जियोरेफ में कनवर्ट करें
```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```
अंत में, हम निर्देशांक को जियोरेफ प्रारूप में परिवर्तित करते हैं और परिणाम प्रिंट करते हैं।

## निष्कर्ष
इस ट्यूटोरियल में, हमने .NET के लिए Aspose.GIS का उपयोग करके निर्देशांक परिवर्तित करने की प्रक्रिया का पता लगाया है। चरण-दर-चरण मार्गदर्शिका का पालन करके और Aspose.GIS लाइब्रेरी का उपयोग करके, आप अपने .NET अनुप्रयोगों के भीतर स्थानिक डेटा में कुशलतापूर्वक हेरफेर कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या Aspose.GIS अन्य प्रोग्रामिंग भाषाओं के साथ संगत है?
Aspose.GIS मुख्य रूप से .NET डेवलपर्स को लक्षित करता है, लेकिन यह जावा के लिए Aspose.GIS के माध्यम से जावा के साथ इंटरऑपरेबिलिटी प्रदान करता है।
### क्या मैं खरीदने से पहले Aspose.GIS आज़मा सकता हूँ?
 हां, आप यहां से Aspose.GIS का निःशुल्क परीक्षण प्राप्त कर सकते हैं[वेबसाइट](https://releases.aspose.com/).
### मैं Aspose.GIS के लिए समर्थन कैसे प्राप्त कर सकता हूँ?
 आप Aspose.GIS सामुदायिक मंच से सहायता ले सकते हैं[यहाँ](https://forum.aspose.com/c/gis/33).
### क्या Aspose.GIS के लिए अस्थायी लाइसेंस उपलब्ध हैं?
 हां, अस्थायी लाइसेंस यहां से प्राप्त किया जा सकता है[अस्थायी लाइसेंस पृष्ठ](https://purchase.aspose.com/temporary-license/).
### मैं Aspose.GIS कहां से खरीद सकता हूं?
 आप Aspose.GIS को यहां से खरीद सकते हैं[खरीद पृष्ठ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
