---
title: Aspose.GIS के साथ ज्यामिति में ज्यामिति की गणना करें
linktitle: ज्यामिति में ज्यामिति की गणना करें
second_title: Aspose.GIS .NET एपीआई
description: .NET के लिए Aspose.GIS का उपयोग करके ज्यामिति में ज्यामिति की गणना करना सीखें। डेवलपर्स के लिए कोड उदाहरणों के साथ चरण-दर-चरण ट्यूटोरियल।
weight: 23
url: /hi/net/geometry-creation/count-geometries-in-geometry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS के साथ ज्यामिति में ज्यामिति की गणना करें

## परिचय
.NET के लिए Aspose.GIS उन डेवलपर्स के लिए एक शक्तिशाली उपकरण है जो अपने .NET अनुप्रयोगों में भू-स्थानिक कार्यक्षमता को शामिल करना चाहते हैं। चाहे आप मैपिंग सॉफ़्टवेयर, स्थान-आधारित सेवाएँ, या स्थानिक विश्लेषण उपकरण बना रहे हों, Aspose.GIS आपकी आवश्यकताओं को पूरा करने के लिए सुविधाओं का एक व्यापक सेट प्रदान करता है। इस ट्यूटोरियल में, हम यह पता लगाएंगे कि .NET के लिए Aspose.GIS का उपयोग करके ज्यामिति के भीतर ज्यामिति की गणना कैसे करें।
## आवश्यक शर्तें
इस ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
1. विजुअल स्टूडियो: सुनिश्चित करें कि आपके सिस्टम पर विजुअल स्टूडियो स्थापित है।
2. .NET के लिए Aspose.GIS: .NET के लिए Aspose.GIS को डाउनलोड और इंस्टॉल करें[डाउनलोड पेज](https://releases.aspose.com/gis/net/).
3. C# का बुनियादी ज्ञान: C# प्रोग्रामिंग भाषा की बुनियादी बातों से खुद को परिचित करें।

## नामस्थान आयात करें
इससे पहले कि आप कोडिंग शुरू करें, आपको Aspose.GIS कार्यक्षमता तक पहुंचने के लिए आवश्यक नामस्थान आयात करने की आवश्यकता है।

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## चरण 2: बिंदु ज्यामिति बनाएं
```csharp
Point point = new Point(40.7128, -74.006);
```
 यहां, हम एक बनाते हैं`Point` अक्षांश 40.7128 और देशांतर -74.006 के साथ ज्यामिति।
## चरण 3: लाइनस्ट्रिंग ज्योमेट्री बनाएं
```csharp
LineString line = new LineString();
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```
 यह कदम एक बनाता है`LineString` ज्यामिति और इसमें दो बिंदु जोड़ता है।
## चरण 4: ज्यामिति संग्रह बनाएं
```csharp
GeometryCollection geometryCollection = new GeometryCollection();
geometryCollection.Add(point);
geometryCollection.Add(line);
```
 फिर हम एक बनाते हैं`GeometryCollection` और इसमें पहले से निर्मित बिंदु और रेखा ज्यामिति जोड़ें।
## चरण 5: ज्यामिति की गणना करें
```csharp
int geometriesCount = geometryCollection.Count;
```
 यह चरण भीतर ज्यामितियों की संख्या की गणना करता है`GeometryCollection`.
## चरण 6: गिनती प्रदर्शित करें
```csharp
Console.WriteLine(geometriesCount); // 2
```
 अंत में, हम ज्यामिति की गिनती प्रिंट करते हैं, जो इस मामले में है`2`.

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.GIS का उपयोग करके ज्यामिति के भीतर ज्यामिति की गणना कैसे करें। इन चरणों का पालन करके, आप आसानी से अपने .NET अनुप्रयोगों में भू-स्थानिक कार्यक्षमता को शामिल कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या .NET के लिए Aspose.GIS डेस्कटॉप और वेब एप्लिकेशन दोनों के लिए उपयुक्त है?
हाँ, .NET के लिए Aspose.GIS का उपयोग डेस्कटॉप और वेब दोनों अनुप्रयोगों में निर्बाध रूप से किया जा सकता है।
### क्या मैं .NET के लिए Aspose.GIS का उपयोग करके स्थानिक क्वेरी कर सकता हूँ?
बिल्कुल, .NET के लिए Aspose.GIS ज्यामिति पर स्थानिक क्वेरी करने के लिए मजबूत समर्थन प्रदान करता है।
### क्या .NET के लिए Aspose.GIS विभिन्न GIS फ़ाइल स्वरूपों का समर्थन करता है?
हाँ, .NET के लिए Aspose.GIS SHP, KML और जियोJSON सहित GIS फ़ाइल स्वरूपों की एक विस्तृत श्रृंखला का समर्थन करता है।
### क्या .NET के लिए Aspose.GIS का निःशुल्क परीक्षण उपलब्ध है?
 हाँ, आप नि:शुल्क परीक्षण डाउनलोड कर सकते हैं[वेबसाइट](https://releases.aspose.com/).
### मुझे .NET के लिए Aspose.GIS के लिए समर्थन कहां मिल सकता है?
 आप पर समर्थन पा सकते हैं[Aspose.GIS फोरम](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
