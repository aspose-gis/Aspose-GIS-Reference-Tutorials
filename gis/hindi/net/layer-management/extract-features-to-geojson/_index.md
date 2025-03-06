---
title: जियोजसन में सुविधाएँ निकालें
linktitle: जियोजसन में सुविधाएँ निकालें
second_title: Aspose.GIS .NET एपीआई
description: जियोजसन में सुविधाएं निकालने के लिए .NET के लिए Aspose.GIS का उपयोग करने पर चरण-दर-चरण मार्गदर्शिका देखें। जीआईएस की शक्ति का आसानी से उपयोग करें! #मान लीजिए #जीआईएस
weight: 23
url: /hi/net/layer-management/extract-features-to-geojson/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जियोजसन में सुविधाएँ निकालें

## परिचय
.NET के लिए Aspose.GIS का उपयोग करके जियोजसन में सुविधाएँ निकालने पर हमारे चरण-दर-चरण ट्यूटोरियल में आपका स्वागत है! चाहे आप एक अनुभवी डेवलपर हों या जीआईएस प्रोग्रामिंग में अपनी यात्रा शुरू कर रहे हों, यह मार्गदर्शिका आपको इस प्रक्रिया से गुजराएगी, यह सुनिश्चित करते हुए कि आप .NET के लिए Aspose.GIS की पूरी शक्ति का उपयोग करें।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
-  .NET के लिए Aspose.GIS: सुनिश्चित करें कि आपके पास लाइब्रेरी स्थापित है। यदि नहीं, तो आप इसे यहां से डाउनलोड कर सकते हैं[.NET पेज के लिए Aspose.GIS](https://releases.aspose.com/gis/net/).
-  शेपफाइल डेटा: इनपुट के लिए शेपफाइल तैयार रखें। यदि आपको नमूना डेटा की आवश्यकता है, तो आप इसे यहां पा सकते हैं[Aspose.GIS दस्तावेज़ीकरण](https://reference.aspose.com/gis/net/).
- .NET वातावरण: दिए गए कोड को चलाने के लिए एक .NET वातावरण सेट करें।
- दस्तावेज़ निर्देशिका: कोड स्निपेट में अपनी दस्तावेज़ निर्देशिका का पथ परिभाषित करें।
अब जब आपके पास सब कुछ है, तो आइए जियोजसन में सुविधाएं निकालना शुरू करें!
## नामस्थान आयात करें
सबसे पहले, अपने कोड में आवश्यक नामस्थान शामिल करें:
```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
Aspose.GIS कार्यात्मकताओं के साथ काम करने के लिए ये नामस्थान आवश्यक हैं।
## चरण 1: इनपुट शेपफाइल खोलें
```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // इनपुट शेपफ़ाइल को संसाधित करने के लिए आपका कोड यहां जाता है
}
```
 का उपयोग करके इनपुट शेपफाइल खोलें`VectorLayer.Open` तरीका।
## चरण 2: आउटपुट जियोजसन बनाएं
```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // आउटपुट जियोजसन बनाने के लिए आपका कोड यहां दिया गया है
}
```
 का उपयोग करके आउटपुट जियोजसन बनाएं`VectorLayer.Create` तरीका।
## चरण 3: विशेषताएँ कॉपी करें
```csharp
outputLayer.CopyAttributes(inputLayer);
```
 का उपयोग करके इनपुट परत से आउटपुट परत तक विशेषताओं को कॉपी करें`CopyAttributes` तरीका।
## चरण 4: प्रक्रिया सुविधाएँ
```csharp
foreach (Feature inputFeature in inputLayer)
{
    // प्रत्येक इनपुट सुविधा को संसाधित करने के लिए आपका कोड यहां जाता है
}
```
इनपुट परत में प्रत्येक सुविधा के माध्यम से पुनरावृति करें और उन्हें व्यक्तिगत रूप से संसाधित करें।
## चरण 5: तिथि के अनुसार सुविधाओं को फ़िल्टर करें
```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```
दिनांक स्थिति के आधार पर सुविधाओं को फ़िल्टर करें। इस उदाहरण में, यह 1982 से पहले की जन्मतिथि वाली सुविधाओं को छोड़ देता है।
## चरण 6: एक नई सुविधा का निर्माण करें
```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```
इनपुट सुविधा से ज्यामिति और मानों की प्रतिलिपि बनाकर आउटपुट परत के लिए एक नई सुविधा का निर्माण करें।
बधाई हो! आपने .NET के लिए Aspose.GIS का उपयोग करके जियोजसन में सफलतापूर्वक सुविधाएँ निकाली हैं।
## निष्कर्ष
इस ट्यूटोरियल में, हमने .NET के लिए Aspose.GIS का उपयोग करके जियोजसन में सुविधाएँ निकालने की प्रक्रिया का पता लगाया। यह शक्तिशाली पुस्तकालय जीआईएस विकास के लिए संभावनाओं की दुनिया खोलता है। Aspose.GIS की पूरी क्षमता को अनलॉक करने के लिए विभिन्न डेटासेट और कार्यात्मकताओं के साथ प्रयोग करें।
## पूछे जाने वाले प्रश्न
### प्रश्न: मुझे और दस्तावेज़ कहां मिल सकते हैं?
 दौरा करना[Aspose.GIS दस्तावेज़ीकरण](https://reference.aspose.com/gis/net/) गहन जानकारी के लिए.
### प्रश्न: मैं अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
### प्रश्न: मैं कहां सहायता मांग सकता हूं?
 शामिल होना[Aspose.GIS फोरम](https://forum.aspose.com/c/gis/33) सामुदायिक समर्थन और चर्चा के लिए।
### प्रश्न: क्या कोई निःशुल्क परीक्षण उपलब्ध है?
 हाँ, आप निःशुल्क परीक्षण पा सकते हैं[यहाँ](https://releases.aspose.com/).
### प्रश्न: मैं .NET के लिए Aspose.GIS कहां से खरीद सकता हूं?
 आप उत्पाद खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
