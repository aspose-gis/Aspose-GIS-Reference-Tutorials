---
date: 2026-01-15
description: Aspose.GIS for .NET का उपयोग करके स्पैशियल रेफ़रेंस सिस्टम के साथ वेक्टर
  लेयर बनाएं। जानें कैसे SRS सेट करें, लेयर बनाएं और GIS डेटा प्रबंधित करें। अभी डाउनलोड
  करें!
linktitle: Create Vector Layer with SRS
second_title: Aspose.GIS .NET API
title: SRS के साथ वेक्टर लेयर बनाएं
url: /hi/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# SRS के साथ वेक्टर लेयर बनाएं

## परिचय
Aspose.GIS for .NET एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को **create vector layer** ऑब्जेक्ट बनाने और .NET एप्लिकेशन्स में जियोग्राफिक इन्फॉर्मेशन सिस्टम (GIS) डेटा के साथ सहजता से काम करने में सक्षम बनाती है। इस ट्यूटोरियल में, हम दिखाएंगे कि कैसे एक स्पैशियल रेफरेंस सिस्टम (SRS) के साथ वेक्टर लेयर बनाई जाए, स्पैशियल रेफरेंस सेट करने का कारण क्या है, और यह वास्तविक‑दुनिया प्रोजेक्ट्स में क्या लाभ देता है। इस गाइड के अंत तक, आप अपने .NET समाधान में GIS क्षमताओं को आत्मविश्वास के साथ इंटीग्रेट कर पाएँगे।

## त्वरित उत्तर
- **इस ट्यूटोरियल का मुख्य उद्देश्य क्या है?** Aspose.GIS for .NET का उपयोग करके निर्दिष्ट SRS के साथ वेक्टर लेयर बनाने का तरीका दिखाना।  
- **उदाहरण में कौन सा प्रोजेक्शन उपयोग किया गया है?** World Mercator (EPSG:3395)।  
- **कोड चलाने के लिए मुझे लाइसेंस चाहिए?** डेवलपमेंट के लिए फ्री ट्रायल काम करता है; प्रोडक्शन के लिए कमर्शियल लाइसेंस आवश्यक है।  
- **क्या मैं अन्य GIS फॉर्मैट्स के साथ भी यही तरीका उपयोग कर सकता हूँ?** हां, वही SRS हैंडलिंग Shapefile, GeoJSON, KML आदि पर लागू होती है।  
- **कौन से .NET संस्करण समर्थित हैं?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7।

## वेक्टर लेयर क्या है और उसका स्पैशियल रेफरेंस क्यों सेट करें?
एक **vector layer** ज्यामितीय फीचर (बिंदु, रेखा, बहुभुज) को एट्रिब्यूट डेटा के साथ संग्रहीत करता है। **spatial reference** (SRS) असाइन करने से GIS सॉफ़्टवेयर को पता चलता है कि पृथ्वी की सतह पर इन निर्देशांक को कैसे समझा जाए। सही SRS सेट करने से सटीक माप, अन्य लेयर्स के साथ उचित ओवरले, और विश्वसनीय मानचित्र विज़ुअलाइज़ेशन सुनिश्चित होते हैं।

## पूर्वापेक्षाएँ
- C# और .NET विकास का बुनियादी ज्ञान।  
- Aspose.GIS for .NET लाइब्रेरी स्थापित हो। आप इसे **[here](https://releases.aspose.com/gis/net/)** से डाउनलोड कर सकते हैं।  
- एक विकास वातावरण (Visual Studio, VS Code, या कोई भी C# IDE)।

## नेमस्पेसेस इम्पोर्ट करें
सुनिश्चित करें कि आपके C# फ़ाइल के शीर्ष पर आवश्यक नेमस्पेसेस इम्पोर्ट किए गए हैं:

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

## स्पैशियल रेफरेंस (SRS) सेट करने का तरीका – चरण 1
आइए World Mercator प्रोजेक्शन को उदाहरण के रूप में उपयोग करके एक **projected spatial reference system** बनाते हैं। यह लेयर के लिए **how to set srs** दर्शाता है।

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

## लेयर बनाने का तरीका – चरण 2
अब हम **create a vector layer** (एक Shapefile) बनाएँगे और उन फीचर्स को जोड़ेंगे जो हमने अभी परिभाषित किए हुए SRS का उपयोग करते हैं। यह भाग Aspose.GIS के साथ **how to create layer** का उत्तर देता है।

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
        layer.Add(feature); // This will throw an exception as the geometry has a different SRS
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```

> **Pro tip:** हमेशा यह सत्यापित करें कि ज्यामिति का `SpatialReferenceSystem` लेयर के SRS से मेल खाता है या नहीं, जोड़ने से पहले। असंगत SRS मान `GisException` उत्पन्न करते हैं, जैसा कि ऊपर दिखाया गया है।

## स्पैशियल रेफरेंस सिस्टम सत्यापित करें – चरण 3
अंत में, लेयर खोलें और पुष्टि करें कि SRS सही ढंग से लागू हुआ है।

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

यदि `IsEquivalent` कॉल `true` लौटाता है, तो आपने सफलतापूर्वक इच्छित स्पैशियल रेफरेंस के साथ **create vector layer** बना लिया है।

## सामान्य समस्याएँ एवं समाधान
| समस्या | क्यों होता है | समाधान |
|-------|----------------|-----|
| `GisException` जब फीचर जोड़ते हैं | ज्यामिति लेयर से अलग SRS उपयोग करती है | जोड़ने से पहले `feature.Geometry.SpatialReferenceSystem` को लेयर के SRS पर सेट करें |
| लेयर GIS सॉफ़्टवेयर में खाली दिखता है | Shapefile सही `.prj` फ़ाइल के बिना बनाया गया था | लेयर बनाते समय `projectedSrs` ऑब्जेक्ट पास किया गया है, यह सुनिश्चित करें |
| अप्रत्याशित निर्देशांक मान | गलत प्रोजेक्शन पैरामीटर (जैसे, सेंट्रल मेरिडियन) | `AddProjectionParameter` को पास किए गए पैरामीटर को दोबारा जांचें |

## अक्सर पूछे जाने वाले प्रश्न
### क्या Aspose.GIS सभी GIS फ़ाइल फ़ॉर्मैट्स के साथ संगत है?
Aspose.GIS विभिन्न GIS फ़ॉर्मैट्स का समर्थन करता है, जिसमें Shapefile, GeoJSON, KML, आदि शामिल हैं। पूरी सूची के लिए **[documentation](https://reference.aspose.com/gis/net/)** देखें।

### क्या मैं Aspose.GIS को वेब एप्लिकेशन में उपयोग कर सकता हूँ?
बिल्कुल! Aspose.GIS for .NET बहुमुखी है और इसे वेब एप्लिकेशन, डेस्कटॉप एप्लिकेशन, और यहाँ तक कि मोबाइल ऐप्स में भी उपयोग किया जा सकता है।

### Aspose.GIS के लिए समर्थन कहाँ प्राप्त कर सकता हूँ?
आप किसी भी प्रश्न या समस्या के लिए **[Aspose.GIS forum](https://forum.aspose.com/c/gis/33)** पर एक सहायक समुदाय पा सकते हैं।

### क्या कोई फ्री ट्रायल उपलब्ध है?
हां, आप Aspose.GIS की सुविधाओं को फ्री ट्रायल **[here](https://releases.aspose.com/)** प्राप्त करके एक्सप्लोर कर सकते हैं।

### मैं Aspose.GIS के लिए लाइसेंस कैसे खरीद सकता हूँ?
लाइसेंस खरीदने के लिए, **[purchase page](https://purchase.aspose.com/buy)** पर जाएँ।

## अक्सर पूछे जाने वाले प्रश्न (अतिरिक्त)

**प्रश्न: यदि मैं अलग SRS के साथ एक ज्यामिति जोड़ने की कोशिश करता हूँ तो क्या होता है?**  
**उत्तर:** Aspose.GIS `GisException` फेंकता है। आपको या तो ज्यामिति को रीप्रोजेक्ट करना होगा या यह सुनिश्चित करना होगा कि वह लेयर के SRS को साझा करती है।

**प्रश्न: क्या मैं मौजूदा लेयर का SRS बदल सकता हूँ?**  
**उत्तर:** हाँ, आप इच्छित SRS के साथ एक नई लेयर बना सकते हैं और फीचर्स को कॉपी कर सकते हैं, आवश्यकतानुसार उन्हें रीप्रोजेक्ट करते हुए।

**प्रश्न: क्या 3D निर्देशांक के साथ काम करना संभव है?**  
**उत्तर:** Aspose.GIS Z‑coordinates को सपोर्ट करता है; बस ऐसे geometry कंस्ट्रक्टर्स का उपयोग करें जो Z मान स्वीकार करते हैं।

**प्रश्न: क्या लाइब्रेरी डेटम ट्रांसफ़ॉर्मेशन को स्वचालित रूप से संभालती है?**  
**उत्तर:** जब आप `Geometry.Transform` का उपयोग करके ज्यामितियों को रीप्रोजेक्ट करते हैं, तो Aspose.GIS आवश्यक डेटम शिफ्ट को निष्पादित करता है।

**प्रश्न: कौन से .NET संस्करण आधिकारिक रूप से परीक्षण किए गए हैं?**  
**उत्तर:** लाइब्रेरी .NET Framework 4.5+, .NET Core 3.1+, और .NET 5/6/7 के साथ परीक्षण की गई है।

## निष्कर्ष
अब आपने Aspose.GIS for .NET का उपयोग करके कस्टम स्पैशियल रेफरेंस सिस्टम के साथ **create vector layer** बनाना सीख लिया है। सही SRS सेट करके, ज्यामिति को सुसंगत रूप से संभालकर, और लेयर के मेटाडेटा की पुष्टि करके, आप किसी भी मानक GIS सॉफ़्टवेयर के साथ इंटरऑपरेट करने वाले मजबूत GIS-सक्षम एप्लिकेशन बना सकते हैं।

---

**Last Updated:** 2026-01-15  
**Tested With:** Aspose.GIS 24.11 for .NET (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}