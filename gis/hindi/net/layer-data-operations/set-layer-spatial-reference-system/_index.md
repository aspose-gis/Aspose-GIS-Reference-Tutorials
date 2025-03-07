---
title: परत स्थानिक संदर्भ प्रणाली सेट करें
linktitle: परत स्थानिक संदर्भ प्रणाली सेट करें
second_title: Aspose.GIS .NET एपीआई
description: .NET के लिए Aspose.GIS के साथ मास्टर सेटिंग लेयर स्पैटियल रेफरेंस सिस्टम। इस चरण-दर-चरण ट्यूटोरियल के साथ अपनी जीआईएस परियोजनाओं को उन्नत करें।
weight: 19
url: /hi/net/layer-data-operations/set-layer-spatial-reference-system/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# परत स्थानिक संदर्भ प्रणाली सेट करें

## परिचय
भौगोलिक सूचना प्रणाली (जीआईएस) के विशाल परिदृश्य में, .NET के लिए Aspose.GIS डेवलपर्स के लिए एक मजबूत और बहुमुखी उपकरण के रूप में खड़ा है। यह ट्यूटोरियल आपको .NET के लिए Aspose.GIS का उपयोग करके लेयर स्पैटियल रेफरेंस सिस्टम सेट करने की प्रक्रिया में मार्गदर्शन करेगा। चाहे आप एक अनुभवी डेवलपर हों या जीआईएस विकास में नए हों, यह चरण-दर-चरण मार्गदर्शिका आपकी स्थानिक डेटा प्रबंधन क्षमताओं को बढ़ाने के लिए Aspose.GIS की शक्ति का उपयोग करने में आपकी सहायता करेगी।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
- .NET प्रोग्रामिंग का कार्यसाधक ज्ञान।
- आपके सिस्टम पर विज़ुअल स्टूडियो स्थापित है।
-  .NET लाइब्रेरी के लिए Aspose.GIS, जिसे आप डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/gis/net/).
- जीआईएस में स्थानिक संदर्भ प्रणालियों की बुनियादी समझ।
## नामस्थान आयात करें
अपने .NET प्रोजेक्ट में, Aspose.GIS द्वारा प्रदान की गई कार्यक्षमताओं तक पहुँचने के लिए आवश्यक नामस्थान आयात करके प्रारंभ करें। निम्नलिखित कोड स्निपेट का उपयोग करें:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```
## चरण 1: दस्तावेज़ निर्देशिका निर्दिष्ट करें
अपनी दस्तावेज़ निर्देशिका का पथ निर्दिष्ट करके प्रारंभ करें। यह वह स्थान होगा जहां आपकी स्थानिक डेटा फ़ाइलें संग्रहीत की जाएंगी।
```csharp
string dataDir = "Your Document Directory";
```
## चरण 2: स्थानिक संदर्भ प्रणाली बनाएं और सेट करें
शेपफाइल के लिए पथ को परिभाषित करें, और ईपीएसजी कोड (इस उदाहरण में 26918) का उपयोग करके एक नया स्थानिक संदर्भ सिस्टम बनाएं।
```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```
## चरण 3: वेक्टर लेयर बनाएं
निर्दिष्ट शेपफाइल पथ, ड्राइवर प्रकार (शेपफाइल), और स्थानिक संदर्भ प्रणाली के साथ एक वेक्टर लेयर बनाने के लिए Aspose.GIS का उपयोग करें।
```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // परत पर आगे के संचालन के लिए आपका कोड यहां जाता है
}
```
## चरण 4: परत में फ़ीचर जोड़ें
एक नई सुविधा का निर्माण करें और इसकी ज्यामिति सेट करें (इस मामले में, निर्देशांक 60, 24 वाला एक बिंदु)। फीचर को वेक्टर लेयर में जोड़ें।
```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```
## चरण 5: स्थानिक संदर्भ प्रणाली जानकारी प्राप्त करें
वेक्टर परत खोलें और स्थानिक संदर्भ प्रणाली के बारे में जानकारी पुनः प्राप्त करें।
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```
अपने विशिष्ट उपयोग के मामले के अनुसार इन चरणों को दोहराएं, और आप .NET के लिए Aspose.GIS के साथ लेयर स्पैटियल रेफरेंस सिस्टम सेट करने की कला में महारत हासिल करने की राह पर होंगे।
## निष्कर्ष
इस ट्यूटोरियल में, हमने .NET के लिए Aspose.GIS का उपयोग करके लेयर स्पैटियल रेफरेंस सिस्टम सेट करने के लिए आवश्यक चरणों का पता लगाया। अपनी सहज एपीआई और शक्तिशाली सुविधाओं के साथ, Aspose.GIS डेवलपर्स को स्थानिक डेटा को निर्बाध रूप से संभालने में सक्षम बनाता है। अपनी स्थानिक डेटा प्रोसेसिंग क्षमताओं को बढ़ाने के लिए इन तकनीकों को अपनी जीआईएस परियोजनाओं में शामिल करें।
## अक्सर पूछे जाने वाले प्रश्नों
### क्या Aspose.GIS अन्य GIS पुस्तकालयों के साथ संगत है?
हाँ, Aspose.GIS अन्य GIS पुस्तकालयों के साथ अच्छी तरह से एकीकृत होता है और उनके साथ संयोजन में उपयोग किया जा सकता है।
### क्या मैं डेस्कटॉप और वेब एप्लिकेशन दोनों के लिए Aspose.GIS का उपयोग कर सकता हूं?
बिल्कुल! Aspose.GIS बहुमुखी है और इसका उपयोग डेस्कटॉप और वेब-आधारित अनुप्रयोगों दोनों में किया जा सकता है।
### क्या Aspose.GIS के लिए कोई लाइसेंसिंग विकल्प उपलब्ध हैं?
 हां, आप लाइसेंसिंग विकल्प तलाश सकते हैं और खरीदारी कर सकते हैं[यहाँ](https://purchase.aspose.com/buy).
### क्या Aspose.GIS के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 निश्चित रूप से! आप नि:शुल्क परीक्षण संस्करण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं Aspose.GIS-संबंधित प्रश्नों के लिए सहायता कहाँ से प्राप्त कर सकता हूँ?
 किसी भी सहायता या प्रश्न के लिए, पर जाएँ[Aspose.GIS फोरम](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
