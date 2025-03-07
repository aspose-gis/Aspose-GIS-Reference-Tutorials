---
title: समानता के लिए ज्यामिति की जाँच करें
linktitle: समानता के लिए ज्यामिति की जाँच करें
second_title: Aspose.GIS .NET एपीआई
description: इस व्यापक ट्यूटोरियल के साथ जानें कि अपने .NET अनुप्रयोगों में समानता के लिए ज्यामिति की जांच करने के लिए .NET के लिए Aspose.GIS का उपयोग कैसे करें।
weight: 10
url: /hi/net/geometry-analysis/check-geometries-for-equality/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# समानता के लिए ज्यामिति की जाँच करें

## परिचय
.NET के लिए Aspose.GIS एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को उनके .NET अनुप्रयोगों में भू-स्थानिक डेटा के साथ कुशलता से काम करने में सक्षम बनाती है। चाहे आप मैपिंग एप्लिकेशन, स्थानिक विश्लेषण उपकरण बना रहे हों, या मौजूदा सॉफ़्टवेयर में भू-स्थानिक कार्यक्षमता को एकीकृत कर रहे हों, Aspose.GIS आपको काम पूरा करने के लिए आवश्यक उपकरण प्रदान करता है।
## आवश्यक शर्तें
.NET के लिए Aspose.GIS का उपयोग करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
### .NET फ्रेमवर्क स्थापित
सुनिश्चित करें कि आपके सिस्टम पर .NET फ्रेमवर्क स्थापित है। आप इसे माइक्रोसॉफ्ट वेबसाइट से डाउनलोड कर सकते हैं।
### .NET लाइब्रेरी के लिए Aspose.GIS
 .NET लाइब्रेरी के लिए Aspose.GIS को डाउनलोड और इंस्टॉल करें[डाउनलोड पेज](https://releases.aspose.com/gis/net/). दस्तावेज़ में दिए गए इंस्टॉलेशन निर्देशों का पालन करें।
### विकास पर्यावरण
.NET विकास के लिए अपना पसंदीदा विकास वातावरण, जैसे विज़ुअल स्टूडियो, सेट करें।

## नामस्थान आयात करें
अपने .NET एप्लिकेशन में, Aspose.GIS कार्यक्षमता का उपयोग करने के लिए आवश्यक नामस्थान आयात करें:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## चरण 1: ज्यामिति को परिभाषित करें
सबसे पहले, उन ज्यामितियों को परिभाषित करें जिनकी आप तुलना करना चाहते हैं। इस उदाहरण में, हमारे पास दो ज्यामिति हैं:`geometry1` और`geometry2`.
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
## चरण 2: समानता के लिए ज्यामिति की जाँच करें
 अब, इसका उपयोग करके जांचें कि ज्यामिति स्थानिक रूप से बराबर हैं या नहीं`SpatiallyEquals` Aspose.GIS द्वारा प्रदान की गई विधि।
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // सत्य
```
 यह प्रिंट हो जाएगा`True` तब से कंसोल के लिए`geometry1` और`geometry2` स्थानिक रूप से समान हैं.
## चरण 3: ज्यामिति को संशोधित करें
 अगला, आइए संशोधित करें`geometry2` एक नया बिंदु जोड़कर.
```csharp
geometry2.AddPoint(3, 3);
```
## चरण 4: समानता की पुनः जाँच करें
अब, संशोधन के बाद ज्यामिति की समानता की पुनः जाँच करें।
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // असत्य
```
 इस बार, आउटपुट होगा`False` चूंकि इसमें किए गए संशोधन के कारण ज्यामिति अब स्थानिक रूप से समान नहीं हैं`geometry2`.

## निष्कर्ष
अंत में, .NET के लिए Aspose.GIS .NET अनुप्रयोगों में भू-स्थानिक डेटा के साथ काम करने के लिए शक्तिशाली उपकरण प्रदान करता है। इस चरण-दर-चरण मार्गदर्शिका का पालन करके, आप Aspose.GIS विधियों का उपयोग करके आसानी से समानता के लिए ज्यामिति की जांच कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं अन्य .NET फ्रेमवर्क के साथ .NET के लिए Aspose.GIS का उपयोग कर सकता हूँ?
हां, .NET के लिए Aspose.GIS .NET कोर और .NET मानक सहित विभिन्न .NET फ्रेमवर्क के साथ संगत है।
### क्या .NET के लिए Aspose.GIS का निःशुल्क परीक्षण उपलब्ध है?
 हाँ, आप नि:शुल्क परीक्षण डाउनलोड कर सकते हैं[पृष्ठ जारी करता है](https://releases.aspose.com/).
### मुझे .NET के लिए Aspose.GIS के लिए दस्तावेज़ कहाँ मिल सकते हैं?
 आप विस्तृत दस्तावेज़ यहां पा सकते हैं[Aspose.GIS दस्तावेज़ीकरण पृष्ठ](https://reference.aspose.com/gis/net/).
### मैं .NET के लिए Aspose.GIS के लिए समर्थन कैसे प्राप्त कर सकता हूँ?
 आप Aspose.GIS सामुदायिक मंच से सहायता प्राप्त कर सकते हैं[यहाँ](https://forum.aspose.com/c/gis/33).
### क्या मैं .NET के लिए Aspose.GIS का अस्थायी लाइसेंस खरीद सकता हूँ?
 हां, आप यहां से अस्थायी लाइसेंस खरीद सकते हैं[खरीद पृष्ठ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
