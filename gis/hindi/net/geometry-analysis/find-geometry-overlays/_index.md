---
title: .NET के लिए Aspose.GIS के साथ ज्योमेट्री ओवरले में महारत हासिल करना
linktitle: ज्योमेट्री ओवरले खोजें
second_title: Aspose.GIS .NET एपीआई
description: .NET के लिए Aspose.GIS का उपयोग करके ज्यामितीय ओवरले ऑपरेशन करना सीखें। मास्टर प्रतिच्छेदन, संघ, अंतर, और सममित अंतर संचालन।
type: docs
weight: 16
url: /hi/net/geometry-analysis/find-geometry-overlays/
---
## परिचय
भौगोलिक सूचना प्रणाली (जीआईएस) के क्षेत्र में, ओवरले संचालन स्थानिक विश्लेषण के लिए मौलिक हैं। वे मूल्यवान अंतर्दृष्टि प्राप्त करने के लिए विभिन्न स्थानिक डेटासेट की तुलना और संयोजन को सक्षम करते हैं। .NET के लिए Aspose.GIS ज्यामितीय ओवरले को कुशलतापूर्वक निष्पादित करने के लिए मजबूत कार्यक्षमता प्रदान करता है। इस ट्यूटोरियल में, हम .NET के लिए Aspose.GIS का उपयोग करके विभिन्न ओवरले ऑपरेशंस जैसे इंटरसेक्शन, यूनियन, डिफरेंस और सिमेट्रिक डिफरेंस के बारे में विस्तार से जानेंगे।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
### 1. .NET विकास पर्यावरण
सुनिश्चित करें कि आपकी मशीन पर .NET विकास वातावरण स्थापित है। आप .NET वेबसाइट से .NET SDK डाउनलोड और इंस्टॉल कर सकते हैं।
### 2. .NET लाइब्रेरी के लिए Aspose.GIS
 .NET लाइब्रेरी के लिए Aspose.GIS को डाउनलोड और इंस्टॉल करें[वेबसाइट](https://releases.aspose.com/gis/net/).
## नामस्थान आयात करें
इससे पहले कि आप .NET के लिए Aspose.GIS का उपयोग शुरू कर सकें, आपको अपने प्रोजेक्ट में आवश्यक नेमस्पेस आयात करना होगा।
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## चरण 1: बहुभुज ऑब्जेक्ट बनाएं
सबसे पहले, हम स्थानिक क्षेत्रों का प्रतिनिधित्व करने वाली दो बहुभुज वस्तुओं को परिभाषित करेंगे।
```csharp
var polygon1 = new Polygon();
polygon1.ExteriorRing = new LinearRing(new[]
{
	 new Point(0, 0),
	 new Point(0, 2),
	 new Point(2, 2),
	 new Point(2, 0),
	 new Point(0, 0),
 });
var polygon2 = new Polygon();
polygon2.ExteriorRing = new LinearRing(new[]
{
	new Point(1, 1),
	new Point(1, 3),
	new Point(3, 3),
	new Point(3, 1),
	new Point(1, 1),
});
```
## चरण 2: इंटरसेक्शन ऑपरेशन करें
आगे, आइए दो बहुभुजों का प्रतिच्छेदन ज्ञात करें।
```csharp
var intersection = polygon1.Intersection(polygon2);
Console.WriteLine("Intersection type is {0}", intersection.GeometryType); // बहुभुज
```
## चरण 3: इंटरसेक्शन पॉइंट प्रिंट करें
हम प्रतिच्छेदन बहुभुज के बिंदुओं को मुद्रित करेंगे।
```csharp
PrintRing(((IPolygon)intersection).ExteriorRing);
```
## चरण 4: यूनियन ऑपरेशन करें
अब, आइए दो बहुभुजों का मिलन ज्ञात करें।
```csharp
var union = polygon1.Union(polygon2);
Console.WriteLine("Union type is {0}", union.GeometryType); // बहुभुज
```
## चरण 5: यूनियन पॉइंट प्रिंट करें
संघ बहुभुज के बिंदुओं को प्रिंट करें।
```csharp
PrintRing(((IPolygon)union).ExteriorRing);
```
## चरण 6: अंतर ऑपरेशन करें
आगे, आइए दोनों बहुभुजों के बीच अंतर खोजें।
```csharp
var difference = polygon1.Difference(polygon2);
Console.WriteLine("Difference type is {0}", difference.GeometryType); // बहुभुज
```
## चरण 7: अंतर बिंदु प्रिंट करें
अंतर बहुभुज के बिंदुओं को प्रिंट करें।
```csharp
PrintRing(((IPolygon)difference).ExteriorRing);
```
## चरण 8: सममित अंतर ऑपरेशन करें
अंत में, आइए दोनों बहुभुजों के बीच सममित अंतर ज्ञात करें।
```csharp
var symDifference = polygon1.SymDifference(polygon2);
Console.WriteLine("Symmetric Difference type is {0}", symDifference.GeometryType); // बहुबहुभुज
```
## चरण 9: सममित अंतर बहुभुज प्रिंट करें
सममित अंतर में प्रत्येक बहुभुज के बिंदुओं को प्रिंट करें।
```csharp
var multiPolygon = (IMultiPolygon)symDifference;
Console.WriteLine("Polygons count is {0}", multiPolygon.Count); // 2
PrintRing(((IPolygon)multiPolygon[0]).ExteriorRing);
PrintRing(((IPolygon)multiPolygon[1]).ExteriorRing);
```
## निष्कर्ष
स्थानिक विश्लेषण में ज्यामिति ओवरले में महारत हासिल करना महत्वपूर्ण है और .NET के लिए Aspose.GIS इन कार्यों को कुशलतापूर्वक करने के लिए उपकरणों का एक व्यापक सेट प्रदान करता है। इस ट्यूटोरियल का अनुसरण करके, आपने सीखा है कि ज्यामितीय आकृतियों पर प्रतिच्छेदन, संघ, अंतर और सममित अंतर संचालन करने के लिए .NET के लिए Aspose.GIS का उपयोग कैसे करें।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं अपनी व्यावसायिक परियोजनाओं में .NET के लिए Aspose.GIS का उपयोग कर सकता हूँ?
हाँ, .NET के लिए Aspose.GIS का उपयोग वाणिज्यिक और गैर-व्यावसायिक दोनों परियोजनाओं में किया जा सकता है।
### प्रश्न: क्या .NET के लिए Aspose.GIS का कोई परीक्षण संस्करण उपलब्ध है?
 हां, आप यहां से नि:शुल्क परीक्षण संस्करण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).
### प्रश्न: मैं .NET के लिए Aspose.GIS के लिए समर्थन कैसे प्राप्त कर सकता हूं?
 आप Aspose.GIS सामुदायिक मंच से सहायता प्राप्त कर सकते हैं[यहाँ](https://forum.aspose.com/c/gis/33).
### प्रश्न: क्या .NET के लिए Aspose.GIS के लिए कोई अस्थायी लाइसेंस उपलब्ध है?
 हाँ, अस्थायी लाइसेंस परीक्षण और मूल्यांकन उद्देश्यों के लिए उपलब्ध हैं। आप इन्हें यहां से प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
### प्रश्न: क्या मैं सीधे .NET के लिए Aspose.GIS खरीद सकता हूँ?
 हां, आप वेबसाइट से .NET के लिए Aspose.GIS खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).