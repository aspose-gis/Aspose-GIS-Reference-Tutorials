---
title: जियोजसन फाइल जीडीबी रूपांतरण रहस्योद्घाटन के लिए
linktitle: जियोसन लेयर को फाइल जीडीबी में बदलें
second_title: Aspose.GIS .NET एपीआई
description: .NET के लिए Aspose.GIS के साथ भू-स्थानिक चमत्कारों को अनलॉक करें! आसानी से जियोसन परतों को फ़ाइल जियोडेटाबेस में परिवर्तित करें। अब इसे आजमाओ! #मान लीजिए #जीआईएस
weight: 17
url: /hi/net/layer-management/convert-geojson-layer-to-file-gdb/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जियोजसन फाइल जीडीबी रूपांतरण रहस्योद्घाटन के लिए

## परिचय
भौगोलिक सूचना प्रणाली (जीआईएस) के गतिशील क्षेत्र में, विभिन्न प्रारूपों के बीच डेटा को निर्बाध रूप से परिवर्तित करने की क्षमता महत्वपूर्ण है। .NET के लिए Aspose.GIS एक शक्तिशाली सहयोगी के रूप में उभरता है, जो भू-स्थानिक डेटा को सहजता से संभालने के लिए उपकरणों का एक व्यापक सूट पेश करता है। इस ट्यूटोरियल में, हम .NET के लिए Aspose.GIS का उपयोग करके एक जियोसन परत को एक फ़ाइल जियोडेटाबेस (फ़ाइल GDB) में परिवर्तित करने की प्रक्रिया के बारे में विस्तार से जानेंगे।
## आवश्यक शर्तें
इस भू-स्थानिक यात्रा पर निकलने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
- .NET प्रोग्रामिंग का कार्यसाधक ज्ञान।
-  .NET के लिए Aspose.GIS स्थापित। यदि नहीं, तो इसे यहां से डाउनलोड करें[यहाँ](https://releases.aspose.com/gis/net/) और स्थापना निर्देशों का पालन करें.
## नामस्थान आयात करें
रूपांतरण प्रक्रिया शुरू करने के लिए, आवश्यक नामस्थान आयात करके प्रारंभ करें:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
अब, आइए इस प्रक्रिया को चरण-दर-चरण मार्गदर्शिका में विभाजित करें:
## चरण 1: जियोसन लेयर सेट करें
प्रासंगिक विशेषताओं और सुविधाओं के साथ एक जियोसन परत बनाकर शुरुआत करें। आपका मार्गदर्शन करने के लिए यहां एक स्निपेट दिया गया है:
```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    // विशेषताएँ जोड़ें
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    //निर्माण करें और सुविधाएँ जोड़ें
    Feature firstFeature = layer.ConstructFeature();
    firstFeature.Geometry = new Point(33.97, -118.25);
    firstFeature.SetValue("name", "John");
    firstFeature.SetValue("age", 23);
    layer.Add(firstFeature);
    Feature secondFeature = layer.ConstructFeature();
    secondFeature.Geometry = new Point(35.81, -96.28);
    secondFeature.SetValue("name", "Mary");
    secondFeature.SetValue("age", 54);
    layer.Add(secondFeature);
}
```
## चरण 2: परीक्षण डेटासेट की प्रतिलिपि बनाएँ
अपने परीक्षण डेटा की अखंडता को बनाए रखने के लिए, डेटासेट की एक प्रति बनाएं। निम्नलिखित कोड स्निपेट का उपयोग करें:
```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```
## चरण 3: जियोसन को फ़ाइल जीडीबी में बदलें
अब, रूपांतरण करने का समय आ गया है। निम्नलिखित कोड का उपयोग करें:
```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        // विशेषताएँ कॉपी करें
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        // फ़ीचर जोड़ें
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```
## निष्कर्ष
इस ट्यूटोरियल में, हमने .NET के लिए Aspose.GIS का उपयोग करके एक जियोसन परत को फ़ाइल जियोडेटाबेस में परिवर्तित करने के दिलचस्प इलाके को नेविगेट किया। इस ज्ञान से लैस, अब आप अपने .NET अनुप्रयोगों में भू-स्थानिक डेटा में निर्बाध रूप से हेरफेर करने के लिए सुसज्जित हैं।
## पूछे जाने वाले प्रश्न
### क्या Aspose.GIS नवीनतम .NET फ्रेमवर्क के साथ संगत है?
हां, Aspose.GIS नवीनतम .NET फ्रेमवर्क संस्करणों के साथ संगत है।
### क्या मैं Aspose.GIS का उपयोग करके अन्य भू-स्थानिक प्रारूपों को परिवर्तित कर सकता हूँ?
बिल्कुल! Aspose.GIS बहुमुखी डेटा हेरफेर के लिए भू-स्थानिक प्रारूपों की एक विस्तृत श्रृंखला का समर्थन करता है।
### क्या Aspose.GIS के लिए कोई परीक्षण संस्करण उपलब्ध है?
 हां, आप परीक्षण संस्करण डाउनलोड करके Aspose.GIS की कार्यक्षमताओं का पता लगा सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं Aspose.GIS-संबंधित प्रश्नों के लिए समर्थन कैसे प्राप्त कर सकता हूं?
 Aspose.GIS पर जाएं[मंच](https://forum.aspose.com/c/gis/33) समर्पित समर्थन के लिए.
### क्या मैं Aspose.GIS के लिए अस्थायी लाइसेंस प्राप्त कर सकता हूँ?
 हाँ, आप एक अस्थायी लाइसेंस सुरक्षित कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
