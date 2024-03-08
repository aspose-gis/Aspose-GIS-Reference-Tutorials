---
title: ज्यामिति की जाँच करें अन्य को कवर करता है
linktitle: ज्यामिति की जाँच करें अन्य को कवर करता है
second_title: Aspose.GIS .NET एपीआई
description: भौगोलिक डेटा के साथ कुशलता से काम करने, स्थानिक जानकारी का विश्लेषण करने और अपने .NET अनुप्रयोगों में मैपिंग सुविधाओं को एकीकृत करने के लिए .NET के लिए Aspose.GIS का उपयोग करना सीखें।
type: docs
weight: 15
url: /hi/net/geometry-analysis/check-geometry-covers-another/
---
## परिचय
.NET के लिए Aspose.GIS एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को उनके .NET अनुप्रयोगों के भीतर भौगोलिक डेटा के साथ कुशलतापूर्वक काम करने के लिए उपकरण प्रदान करती है। चाहे आप मैपिंग एप्लिकेशन बना रहे हों, स्थानिक डेटा का विश्लेषण कर रहे हों, या भौगोलिक विशेषताओं को अपने सॉफ़्टवेयर में एकीकृत कर रहे हों, Aspose.GIS आपकी विकास प्रक्रिया को सुव्यवस्थित करने के लिए कार्यात्मकताओं का एक व्यापक सेट प्रदान करता है।
## आवश्यक शर्तें
.NET के लिए Aspose.GIS का उपयोग करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ स्थापित हैं:
### 1. विजुअल स्टूडियो स्थापित करें
सुनिश्चित करें कि आपके सिस्टम पर विजुअल स्टूडियो स्थापित है। .NET के लिए Aspose.GIS विज़ुअल स्टूडियो के साथ सहजता से एकीकृत होता है, जो एक सहज विकास अनुभव प्रदान करता है।
### 2. .NET के लिए Aspose.GIS प्राप्त करें
 .NET लाइब्रेरी के लिए Aspose.GIS डाउनलोड करें[वेबसाइट](https://releases.aspose.com/gis/net/). आप या तो लाइब्रेरी को सीधे डाउनलोड कर सकते हैं या इसे अपने प्रोजेक्ट में इंस्टॉल करने के लिए NuGet जैसे पैकेज मैनेजर का उपयोग कर सकते हैं।
### 3. .NET फ्रेमवर्क से परिचित होना
.NET के लिए Aspose.GIS का प्रभावी ढंग से उपयोग करने के लिए .NET फ्रेमवर्क और C# प्रोग्रामिंग भाषा का बुनियादी ज्ञान आवश्यक है।
### 4. दस्तावेज़ीकरण और समर्थन तक पहुंच
 को देखें[प्रलेखन](https://reference.aspose.com/gis/net/) Aspose.GIS API और कार्यप्रणाली पर विस्तृत जानकारी के लिए। यदि आपको कोई समस्या आती है या कोई प्रश्न है, तो इसका उपयोग करें[Aspose.GIS फोरम](https://forum.aspose.com/c/gis/33) सहायता के लिए।
### 5. वैकल्पिक: अस्थायी लाइसेंस
 यदि आप .NET के लिए Aspose.GIS की खोज कर रहे हैं, तो आप एक अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/) पुस्तकालय की विशेषताओं का मूल्यांकन करना।

## नामस्थान आयात करें
अपने प्रोजेक्ट में .NET के लिए Aspose.GIS का उपयोग करने से पहले, आपको आवश्यक नामस्थान आयात करने होंगे:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

अब, यह समझने के लिए कि .NET के लिए Aspose.GIS का उपयोग करके एक ज्यामिति दूसरे को कवर करती है या नहीं, यह समझने के लिए दिए गए उदाहरण को कई चरणों में तोड़ते हैं।
## चरण 1: लाइनस्ट्रिंग ऑब्जेक्ट बनाएं
```csharp
var line = new LineString();
```
 यहां, हम एक नया इंस्टेंट करते हैं`LineString` वस्तु, जो द्वि-आयामी अंतरिक्ष में जुड़े रेखा खंडों के अनुक्रम का प्रतिनिधित्व करती है।
## चरण 2: लाइनस्ट्रिंग में पॉइंट जोड़ें
```csharp
line.AddPoint(0, 0);
line.AddPoint(1, 1);
```
 हम इसमें अंक जोड़ते हैं`LineString` का उपयोग`AddPoint` तरीका। इस उदाहरण में, हम दो बिंदु जोड़ते हैं: (0, 0) और (1, 1), जिससे एक रेखाखंड बनता है।
## चरण 3: प्वाइंट ऑब्जेक्ट बनाएं
```csharp
var point = new Point(0, 0);
```
 त्वरित करें ए`Point` द्वि-आयामी अंतरिक्ष में एक बिंदु का प्रतिनिधित्व करने वाली वस्तु। यहां, हम निर्देशांक (0, 0) पर एक बिंदु बनाते हैं।
## चरण 4: जांचें कि क्या रेखा बिंदु को कवर करती है
```csharp
Console.WriteLine(line.Covers(point));    // सत्य
```
 उपयोग`Covers` यह जांचने की विधि कि रेखा बिंदु को कवर करती है या नहीं। इस स्थिति में, यह वापस आ जाता है`True` क्योंकि बिंदु (0, 0) रेखा पर स्थित है।
## चरण 5: जांचें कि क्या बिंदु रेखा से ढका हुआ है
```csharp
Console.WriteLine(point.CoveredBy(line)); // सत्य
```
इसी प्रकार, का उपयोग करें`CoveredBy` यह जांचने की विधि कि बिंदु रेखा से ढका हुआ है या नहीं। चूँकि बिंदु (0, 0) रेखा पर स्थित है, यह वापस लौट आता है`True`.

## निष्कर्ष
अंत में, .NET के लिए Aspose.GIS .NET अनुप्रयोगों में भौगोलिक डेटा के साथ काम करने के लिए शक्तिशाली उपकरण प्रदान करता है। ऊपर बताए गए चरणों का पालन करके, आप यह जांचने के लिए Aspose.GIS कार्यक्षमताओं का कुशलतापूर्वक उपयोग कर सकते हैं कि क्या एक ज्यामिति दूसरे को कवर करती है, जिससे आपके सॉफ़्टवेयर की स्थानिक विश्लेषण क्षमताओं में वृद्धि होती है।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं अपनी व्यावसायिक परियोजनाओं में .NET के लिए Aspose.GIS का उपयोग कर सकता हूँ?
हाँ, आप उचित लाइसेंस प्राप्त करने के बाद वाणिज्यिक और गैर-व्यावसायिक दोनों परियोजनाओं में .NET के लिए Aspose.GIS का उपयोग कर सकते हैं।
### क्या .NET के लिए Aspose.GIS .NET कोर के साथ संगत है?
हां, .NET के लिए Aspose.GIS .NET फ्रेमवर्क और .NET कोर वातावरण दोनों के साथ संगत है।
### क्या .NET के लिए Aspose.GIS विभिन्न GIS प्रारूपों का समर्थन करता है?
हां, .NET के लिए Aspose.GIS शेपफाइल, जियोजसन, KML और अन्य सहित GIS प्रारूपों की एक विस्तृत श्रृंखला का समर्थन करता है।
### क्या मैं .NET के लिए Aspose.GIS के विकास में योगदान दे सकता हूँ?
.NET के लिए Aspose.GIS Aspose द्वारा विकसित एक मालिकाना लाइब्रेरी है, इसलिए बाहरी डेवलपर्स से योगदान स्वीकार नहीं किया जाता है। हालाँकि, आप लाइब्रेरी को बेहतर बनाने के लिए फीडबैक और सुझाव दे सकते हैं।
### .NET के लिए Aspose.GIS के लिए अपडेट कितनी बार जारी किए जाते हैं?
 .NET के लिए Aspose.GIS के अपडेट नई सुविधाओं, संवर्द्धन और बग फिक्स को पेश करने के लिए नियमित रूप से जारी किए जाते हैं। जाँचें[वेबसाइट](https://releases.aspose.com/gis/net/) नवीनतम रिलीज़ के लिए.