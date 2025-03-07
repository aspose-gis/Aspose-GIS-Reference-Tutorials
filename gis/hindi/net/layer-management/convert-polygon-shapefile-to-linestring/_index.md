---
title: पॉलीगॉन शेपफाइल को लाइनस्ट्रिंग में बदलें
linktitle: पॉलीगॉन शेपफाइल को लाइनस्ट्रिंग में बदलें
second_title: Aspose.GIS .NET एपीआई
description: .NET के लिए Aspose.GIS की शक्ति का अन्वेषण करें और आसानी से पॉलीगॉन शेपफाइल्स को लाइनस्ट्रिंग्स में परिवर्तित करें। आज ही अपने जीआईएस विकास को बढ़ावा दें!
weight: 18
url: /hi/net/layer-management/convert-polygon-shapefile-to-linestring/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# पॉलीगॉन शेपफाइल को लाइनस्ट्रिंग में बदलें

## परिचय
यदि आप .NET में भौगोलिक सूचना प्रणाली (GIS) के साथ काम कर रहे हैं, तो Aspose.GIS एक शक्तिशाली लाइब्रेरी है जो आपके कार्यों को सरल बना सकती है। इस ट्यूटोरियल में, हम आपको Aspose.GIS का उपयोग करके पॉलीगॉन शेपफाइल को लिनेस्ट्रिंग में बदलने की प्रक्रिया के बारे में मार्गदर्शन करेंगे। यह विशेष रूप से तब उपयोगी हो सकता है जब आपको रूट प्लानिंग या नेटवर्क विश्लेषण जैसे विभिन्न अनुप्रयोगों के लिए बहुभुज डेटा से रैखिक विशेषताएं निकालने की आवश्यकता होती है।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित स्थान हैं:
-  Aspose.GIS लाइब्रेरी: Aspose.GIS लाइब्रेरी को डाउनलोड और इंस्टॉल करें[वेबसाइट](https://releases.aspose.com/gis/net/).
- शेपफ़ाइल डेटा: रूपांतरण के लिए एक बहुभुज शेपफ़ाइल तैयार रखें। यदि आपके पास कोई नहीं है, तो आप नमूना डेटा ढूंढ सकते हैं या अपना स्वयं का डेटा बना सकते हैं।
- विकास परिवेश: आवश्यक उपकरणों के साथ अपना .NET विकास परिवेश स्थापित करें।
## नामस्थान आयात करें
अपने C# कोड में, आपको आवश्यक कक्षाओं और विधियों तक पहुँचने के लिए Aspose.GIS नेमस्पेस को आयात करना होगा। अपनी कोड फ़ाइल की शुरुआत में निम्नलिखित नामस्थान जोड़ें:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## चरण 1: दस्तावेज़ निर्देशिका सेट करें
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "Your Document Directory";
```
"आपकी दस्तावेज़ निर्देशिका" को उस निर्देशिका के पथ से बदलें जहां आपकी शेपफ़ाइल स्थित है।
## चरण 2: सोर्स शेपफाइल खोलें
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // बाकी कोड यहां जाएगा
}
```
यह चरण पढ़ने के लिए स्रोत पॉलीगॉन शेपफाइल को खोलता है।
## चरण 3: डेस्टिनेशन लिनेस्ट्रिंग शेपफाइल बनाएं
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // बाकी कोड यहां जाएगा
}
```
यहां, हम परिवर्तित डेटा लिखने के लिए एक नया लाइनस्ट्रिंग शेपफाइल बनाते हैं।
## चरण 4: स्रोत सुविधाओं के माध्यम से पुनरावृति
```csharp
foreach (Feature sourceFeature in source)
{
    // बाकी कोड यहां जाएगा
}
```
यह लूप स्रोत पॉलीगॉन शेपफ़ाइल में प्रत्येक सुविधा के माध्यम से पुनरावृत्त होता है।
## चरण 5: बहुभुज को लिनेस्ट्रिंग में बदलें और गंतव्य पर लिखें
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
इस चरण में, प्रत्येक बहुभुज सुविधा को एक लाइनस्ट्रिंग में बदल दिया जाता है, और परिणामी लाइनस्ट्रिंग सुविधा को गंतव्य शेपफाइल पर लिखा जाता है।
## निष्कर्ष
इन चरणों का पालन करके, आप .NET के लिए Aspose.GIS का उपयोग करके आसानी से पॉलीगॉन शेपफाइल को लाइनस्ट्रिंग में परिवर्तित कर सकते हैं। यह प्रक्रिया जीआईएस अनुप्रयोगों में डेटा विश्लेषण और विज़ुअलाइज़ेशन के लिए नई संभावनाएं खोलती है।

## पूछे जाने वाले प्रश्न
### क्या Aspose.GIS .NET के सभी संस्करणों के साथ संगत है?
हां, Aspose.GIS आपके विकास परिवेश के साथ अनुकूलता सुनिश्चित करते हुए, .NET के विभिन्न संस्करणों का समर्थन करता है।
### क्या मैं व्यावसायिक परियोजनाओं के लिए Aspose.GIS का उपयोग कर सकता हूँ?
 हाँ तुम कर सकते हो। व्यावसायिक परियोजनाओं में Aspose.GIS का उपयोग करने के लिए, लाइसेंस खरीदने पर विचार करें[यहाँ](https://purchase.aspose.com/buy).
### क्या कोई उदाहरण या दस्तावेज़ उपलब्ध हैं?
 हां, आप यहां व्यापक दस्तावेज़ और उदाहरण पा सकते हैं[दस्तावेज़ीकरण पृष्ठ](https://reference.aspose.com/gis/net/).
### क्या कोई परीक्षण संस्करण उपलब्ध है?
 हाँ, आप Aspose.GIS पर जाकर नि:शुल्क परीक्षण के साथ एक्सप्लोर कर सकते हैं[इस लिंक](https://releases.aspose.com/).
### मैं सहायता या सहायता कहां मांग सकता हूं?
 दौरा करना[Aspose.GIS फोरम](https://forum.aspose.com/c/gis/33) किसी भी सहायता या समर्थन-संबंधित प्रश्न के लिए।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
