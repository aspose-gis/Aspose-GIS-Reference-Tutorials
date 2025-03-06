---
title: जाँच करें कि ज्यामिति में एक और शामिल है
linktitle: जाँच करें कि ज्यामिति में एक और शामिल है
second_title: Aspose.GIS .NET एपीआई
description: अपने .NET अनुप्रयोगों में निर्बाध भू-स्थानिक डेटा एकीकरण के लिए एक मजबूत लाइब्रेरी .NET के लिए Aspose.GIS का अन्वेषण करें।
weight: 14
url: /hi/net/geometry-analysis/check-geometry-contains-another/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जाँच करें कि ज्यामिति में एक और शामिल है

## परिचय
.NET के लिए Aspose.GIS एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को उनके .NET अनुप्रयोगों के भीतर भू-स्थानिक डेटा के साथ निर्बाध रूप से काम करने में सक्षम बनाती है। चाहे आप मैपिंग एप्लिकेशन बना रहे हों, भू-स्थानिक विश्लेषण कर रहे हों, या अपने सॉफ़्टवेयर में स्थान-आधारित सुविधाओं को एकीकृत कर रहे हों, Aspose.GIS सहज एपीआई और मजबूत कार्यक्षमता प्रदान करके प्रक्रिया को सरल बनाता है।
## आवश्यक शर्तें
.NET के लिए Aspose.GIS का उपयोग करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
### 1. .NET विकास पर्यावरण सेटअप
सुनिश्चित करें कि आपकी मशीन पर एक कार्यशील .NET विकास वातावरण स्थापित है। इसमें .NET SDK को स्थापित और ठीक से कॉन्फ़िगर करना शामिल है।
### 2. Aspose.GIS इंस्टालेशन
 रिलीज़ पृष्ठ से लाइब्रेरी डाउनलोड करके .NET के लिए Aspose.GIS स्थापित करें[यहाँ](https://releases.aspose.com/gis/net/) . दस्तावेज़ में दिए गए इंस्टॉलेशन निर्देशों का पालन करें[यहाँ](https://reference.aspose.com/gis/net/)Aspose.GIS को अपने प्रोजेक्ट में एकीकृत करने के लिए।
### 3. C# की बुनियादी समझ
C# प्रोग्रामिंग भाषा से खुद को परिचित करें क्योंकि .NET के लिए Aspose.GIS का उपयोग मुख्य रूप से C# के साथ किया जाता है।

## नामस्थान आयात करें
अपने C# प्रोजेक्ट में, Aspose.GIS कार्यात्मकताओं का उपयोग करने के लिए आवश्यक नामस्थान आयात करें:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## चरण 1: ज्यामिति वस्तुओं को परिभाषित करें
सबसे पहले, Aspose.GIS कक्षाओं का उपयोग करके ज्यामिति वस्तुओं को परिभाषित करें:
```csharp
var geometry1 = new Polygon();
geometry1.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 4),
    new Point(4, 4),
    new Point(4, 0),
    new Point(0, 0),
});
geometry1.AddInteriorRing(new LinearRing(new[]
{
    new Point(1, 1),
    new Point(1, 3),
    new Point(3, 3),
    new Point(3, 1),
    new Point(1, 1),
}));
var geometry2 = new Point(2, 2);
```
## चरण 2: स्थानिक रोकथाम की जाँच करें
इसके बाद, जांचें कि क्या एक ज्यामिति में दूसरा शामिल है:
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry2)); // असत्य
```
## चरण 3: अन्य ज्यामिति को परिभाषित करें
किसी अन्य ज्यामिति वस्तु को परिभाषित करें:
```csharp
var geometry3 = new Point(0.5, 0.5);
```
## चरण 4: स्थानिक रोकथाम की फिर से जाँच करें
जांचें कि क्या नई परिभाषित ज्यामिति पहली ज्यामिति में समाहित है:
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry3)); // सत्य
```
## चरण 5: समतुल्य कार्यक्षमता
 समझो उसको`a.SpatiallyContains(b)` के बराबर है`b.Within(a)`:
```csharp
Console.WriteLine(geometry3.Within(geometry1)); // सत्य
```

## निष्कर्ष
अंत में, .NET के लिए Aspose.GIS .NET अनुप्रयोगों में भू-स्थानिक डेटा को संभालने के लिए शक्तिशाली उपकरण प्रदान करता है। इस गाइड का पालन करके और दिए गए उदाहरण का उपयोग करके, आप कुशलतापूर्वक स्थानिक रोकथाम जांच कर सकते हैं और अपनी परियोजनाओं के भीतर अन्य भू-स्थानिक कार्यात्मकताओं का लाभ उठा सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### Q1: क्या Aspose.GIS .NET कोर के साथ संगत है?
उत्तर: हां, Aspose.GIS पूरी तरह से .NET कोर का समर्थन करता है, जिससे आप विभिन्न प्लेटफार्मों पर भू-स्थानिक एप्लिकेशन विकसित कर सकते हैं।
### Q2: क्या मैं Aspose.GIS का उपयोग करके भू-स्थानिक विश्लेषण कर सकता हूँ?
उत्तर: बिल्कुल, Aspose.GIS भू-स्थानिक विश्लेषण के लिए विभिन्न कार्यक्षमताएँ प्रदान करता है, जिसमें स्थानिक प्रश्न, दूरी की गणना और ज्यामिति जोड़-तोड़ शामिल हैं।
### Q3: Aspose.GIS के लिए अपडेट कितनी बार जारी किए जाते हैं?
उत्तर: Aspose.GIS प्रदर्शन में सुधार करने, नई सुविधाएँ जोड़ने और किसी भी रिपोर्ट की गई समस्या के समाधान के लिए नियमित रूप से अपडेट जारी करता है। आप रिलीज़ पेज पर जाकर अपडेट रह सकते हैं।
### Q4: क्या Aspose.GIS उपयोगकर्ताओं के लिए कोई सामुदायिक मंच है?
उत्तर: हां, आप Aspose.GIS सामुदायिक मंच में शामिल हो सकते हैं[यहाँ](https://forum.aspose.com/c/gis/33) अन्य उपयोगकर्ताओं से जुड़ने, प्रश्न पूछने और अपने अनुभव साझा करने के लिए।
### Q5: क्या मैं खरीदने से पहले Aspose.GIS आज़मा सकता हूँ?
 उ: निश्चित रूप से, आप नि:शुल्क परीक्षण डाउनलोड करके Aspose.GIS का पता लगा सकते हैं[यहाँ](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
