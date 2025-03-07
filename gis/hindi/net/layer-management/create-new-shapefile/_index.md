---
title: नई शेपफाइल बनाएं
linktitle: नई शेपफाइल बनाएं
second_title: Aspose.GIS .NET एपीआई
description: जानें कि .NET के लिए Aspose.GIS का उपयोग करके एक नई शेपफाइल कैसे बनाएं। हमारे चरण-दर-चरण मार्गदर्शिका का पालन करें और स्थानिक डेटा हेरफेर की शक्ति को अनलॉक करें।
weight: 12
url: /hi/net/layer-management/create-new-shapefile/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# नई शेपफाइल बनाएं

## परिचय
यदि आप .NET के साथ भौगोलिक सूचना प्रणाली (जीआईएस) विकास में गहराई से उतर रहे हैं, तो Aspose.GIS आपके लिए उपयुक्त समाधान है। यह शक्तिशाली लाइब्रेरी डेवलपर्स को स्थानिक डेटा के साथ निर्बाध रूप से काम करने के लिए सशक्त बनाती है, और इस ट्यूटोरियल में, हम .NET के लिए Aspose.GIS का उपयोग करके एक नई शेपफाइल बनाने की प्रक्रिया में आपका मार्गदर्शन करेंगे।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में आगे बढ़ें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
- C# प्रोग्रामिंग भाषा की बुनियादी समझ।
- आपकी मशीन पर विज़ुअल स्टूडियो स्थापित है।
-  .NET लाइब्रेरी के लिए Aspose.GIS। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/gis/net/).
## नामस्थान आयात करें
Aspose.GIS की कार्यक्षमता का लाभ उठाने के लिए आवश्यक नामस्थान आयात करके प्रारंभ करें:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## चरण 1: अपना प्रोजेक्ट सेट करें
विज़ुअल स्टूडियो में एक नया C# प्रोजेक्ट बनाकर शुरुआत करें और Aspose.GIS लाइब्रेरी को शामिल करें।
## चरण 2: दस्तावेज़ निर्देशिका को परिभाषित करें
```csharp
string dataDir = "Your Document Directory";
```
"आपकी दस्तावेज़ निर्देशिका" को उस वास्तविक पथ से बदलें जहाँ आप अपनी नई शेपफ़ाइल सहेजना चाहते हैं।
## चरण 3: एक वेक्टरलेयर बनाएं
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    //सुविधाएँ जोड़ने से पहले विशेषताएँ जोड़ें
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
यह कोड खंड वेक्टर परत सेट करता है और आपकी सुविधाओं के लिए विशेषताओं को परिभाषित करता है।
## चरण 4: सुविधाएँ जोड़ें
### केस 1: मानों को व्यक्तिगत रूप से सेट करता है
```csharp
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
firstFeature.SetValue("dob", new DateTime(1982, 2, 5, 16, 30, 0));
layer.Add(firstFeature);
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
secondFeature.SetValue("dob", new DateTime(1984, 12, 15, 15, 30, 0));
layer.Add(secondFeature);
```
### केस 2: सभी विशेषताओं के लिए नए मान सेट करता है
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
## निष्कर्ष
 बधाई हो! आपने .NET के लिए Aspose.GIS का उपयोग करके सफलतापूर्वक एक नया शेपफ़ाइल बनाया है। इस ट्यूटोरियल में आपके प्रोजेक्ट को स्थापित करने, विशेषताओं को परिभाषित करने और सुविधाओं को जोड़ने की मूल बातें शामिल हैं। जैसे-जैसे आप आगे अन्वेषण करें, देखें[प्रलेखन](https://reference.aspose.com/gis/net/) उन्नत सुविधाओं और कार्यक्षमताओं के लिए।
## अक्सर पूछे जाने वाले प्रश्नों
### प्रश्न: क्या मैं Aspose.GIS का उपयोग अन्य प्रोग्रामिंग भाषाओं के साथ कर सकता हूँ?
Aspose.GIS मुख्य रूप से .NET का समर्थन करता है, लेकिन जावा के लिए भी संस्करण उपलब्ध हैं।
### प्रश्न: क्या कोई निःशुल्क परीक्षण उपलब्ध है?
 हाँ, आप नि:शुल्क परीक्षण का उपयोग कर सकते हैं[यहाँ](https://releases.aspose.com/).
### प्रश्न: मुझे Aspose.GIS के लिए समर्थन कहां मिल सकता है?
 दौरा करना[Aspose.GIS फोरम](https://forum.aspose.com/c/gis/33) सामुदायिक समर्थन और चर्चा के लिए।
### प्रश्न: मैं अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 अपना अस्थायी लाइसेंस प्राप्त करें[यहाँ](https://purchase.aspose.com/temporary-license/).
### प्रश्न: मैं .NET के लिए Aspose.GIS कहां से खरीद सकता हूं?
 आप लाइब्रेरी खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
