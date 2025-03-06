---
title: एसआरएस के साथ वेक्टर लेयर बनाएं
linktitle: एसआरएस के साथ वेक्टर लेयर बनाएं
second_title: Aspose.GIS .NET एपीआई
description: .NET के लिए Aspose.GIS का अन्वेषण करें - निर्बाध GIS एकीकरण की कुंजी। निर्दिष्ट स्थानिक संदर्भ प्रणालियों के साथ सहजता से वेक्टर परतें बनाएं। अब डाउनलोड करो!
weight: 13
url: /hi/net/layer-management/create-vector-layer-with-srs/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# एसआरएस के साथ वेक्टर लेयर बनाएं

## परिचय
.NET के लिए Aspose.GIS एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को .NET अनुप्रयोगों में भौगोलिक सूचना प्रणाली (GIS) डेटा के साथ निर्बाध रूप से काम करने में सक्षम बनाती है। इस ट्यूटोरियल में, हम एक स्थानिक संदर्भ प्रणाली (एसआरएस) के साथ एक वेक्टर परत बनाने पर ध्यान केंद्रित करेंगे। इस गाइड के अंत तक, आप आसानी से जीआईएस क्षमताओं को अपने .NET प्रोजेक्ट में एकीकृत करने में सक्षम होंगे।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
- C# और .NET विकास का बुनियादी ज्ञान।
-  .NET लाइब्रेरी के लिए Aspose.GIS स्थापित। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/gis/net/).
- एक विकास वातावरण स्थापित और तैयार है।
## नामस्थान आयात करें
सुनिश्चित करें कि आपने अपनी C# फ़ाइल की शुरुआत में आवश्यक नामस्थान आयात किए हैं:
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## चरण 1: प्रक्षेपित स्थानिक संदर्भ प्रणाली स्थापित करें
आइए एक उदाहरण के रूप में वर्ल्ड मर्केटर प्रोजेक्शन का उपयोग करके एक अनुमानित स्थानिक संदर्भ प्रणाली (एसआरएस) बनाएं। इन चरणों का पालन करें:
```csharp
var parameters = new ProjectedSpatialReferenceSystemParameters
{
    Name = "WGS 84 / World Mercator",
    Base = SpatialReferenceSystem.Wgs84,
    ProjectionMethodName = "Mercator_1SP",
    LinearUnit = Unit.Meter,
    XAxis = new Axis("Easting", AxisDirection.East),
    YAxis = new Axis("Northing", AxisDirection.North),
    AxisesOrder = ProjectedAxisesOrder.XY,
};
parameters.AddProjectionParameter("central_meridian", 0);
parameters.AddProjectionParameter("scale_factor", 1);
parameters.AddProjectionParameter("false_easting", 0);
parameters.AddProjectionParameter("false_northing", 0);
var projectedSrs = SpatialReferenceSystem.CreateProjected(parameters, Identifier.Epsg(3395));
```
## चरण 2: एक वेक्टर परत बनाएं और सुविधाएँ जोड़ें
अब, आइए एक शेपफाइल बनाएं और निर्दिष्ट एसआरएस के साथ विशेषताएं जोड़ें:
```csharp
using (var layer = Drivers.Shapefile.CreateLayer(dataDir + "filepath_out.shp", new ShapefileOptions(), projectedSrs))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2);
    layer.Add(feature);
    feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2) { SpatialReferenceSystem = SpatialReferenceSystem.Nad83 };
    try
    {
        layer.Add(feature); // यह एक अपवाद फेंक देगा क्योंकि ज्यामिति में एक अलग एसआरएस है
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```
## चरण 3: स्थानिक संदर्भ प्रणाली सत्यापित करें
अंत में, आइए परत खोलें और इसकी स्थानिक संदर्भ प्रणाली को सत्यापित करें:
```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "डब्ल्यूजीएस 84/वर्ल्ड मर्केटर"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // सच लौटना चाहिए
}
```
इन चरणों का पालन करके, आपने .NET के लिए Aspose.GIS का उपयोग करके एक निर्दिष्ट स्थानिक संदर्भ प्रणाली के साथ सफलतापूर्वक एक वेक्टर परत बनाई है।
## निष्कर्ष
Aspose.GIS को धन्यवाद, आपके .NET अनुप्रयोगों में GIS कार्यक्षमता को एकीकृत करना इतना आसान कभी नहीं रहा। आसानी से वेक्टर परतें बनाने और स्थानिक संदर्भ प्रणालियों को प्रबंधित करने की क्षमता के साथ, आप अपनी परियोजनाओं को शक्तिशाली भू-स्थानिक क्षमताओं के साथ बढ़ा सकते हैं।
## पूछे जाने वाले प्रश्न
### क्या Aspose.GIS सभी GIS फ़ाइल स्वरूपों के साथ संगत है?
 Aspose.GIS विभिन्न GIS प्रारूपों का समर्थन करता है, जिनमें शेपफाइल, जियोजसन, KML और बहुत कुछ शामिल हैं। जाँचें[प्रलेखन](https://reference.aspose.com/gis/net/) पूरी सूची के लिए.
### क्या मैं वेब एप्लिकेशन में Aspose.GIS का उपयोग कर सकता हूं?
बिल्कुल! .NET के लिए Aspose.GIS बहुमुखी है और इसका उपयोग वेब एप्लिकेशन, डेस्कटॉप एप्लिकेशन और यहां तक कि मोबाइल एप्लिकेशन में भी किया जा सकता है।
### मुझे Aspose.GIS के लिए समर्थन कहाँ से मिल सकता है?
 आप यहां एक सहायक समुदाय पा सकते हैं[Aspose.GIS फोरम](https://forum.aspose.com/c/gis/33) आपके सामने आने वाले किसी भी प्रश्न या समस्या के लिए।
### क्या कोई निःशुल्क परीक्षण उपलब्ध है?
 हाँ, आप निःशुल्क परीक्षण प्राप्त करके Aspose.GIS की विशेषताओं का पता लगा सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं Aspose.GIS के लिए लाइसेंस कैसे खरीद सकता हूँ?
 लाइसेंस खरीदने के लिए, पर जाएँ[खरीद पृष्ठ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
