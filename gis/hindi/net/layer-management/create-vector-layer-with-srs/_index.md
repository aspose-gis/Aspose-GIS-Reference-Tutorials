---
date: 2026-06-30
description: Aspose.GIS for .NET का उपयोग करके spatial reference system के साथ Vector
  Layer बनाना सीखें। Step‑by‑step guide, code‑free explanations, और FAQs।
keywords:
- how to create vector layer
- Aspose.GIS spatial reference
- .NET GIS tutorial
linktitle: Aspose.GIS for .NET का उपयोग करके SRS के साथ Vector Layer कैसे बनाएं
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create vector layer with a spatial reference system using
    Aspose.GIS for .NET. Step‑by‑step guide, code‑free explanations, and FAQs.
  headline: How to Create Vector Layer with SRS using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS throws a `GisException`. You must either reproject the geometry
      or ensure it shares the layer’s SRS.
    question: What happens if I try to add a geometry with a different SRS?
  - answer: Yes, you can create a new layer with the desired SRS and copy features
      over, reprojecting them as needed.
    question: Can I change the SRS of an existing layer?
  - answer: Aspose.GIS supports Z‑coordinates; just use geometry constructors that
      accept a Z value.
    question: Is it possible to work with 3D coordinates?
  - answer: When you reproject geometries using `Geometry.Transform`, Aspose.GIS performs
      the necessary datum shift.
    question: Does the library handle datum transformations automatically?
  - answer: The library is tested with .NET Framework 4.5+, .NET Core 3.1+, and .NET
      5/6/7.
    question: Which .NET versions are officially tested?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET का उपयोग करके SRS के साथ Vector Layer कैसे बनाएं
url: /hi/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET का उपयोग करके SRS के साथ वेक्टर लेयर कैसे बनाएं

## परिचय
इस ट्यूटोरियल में आप **वेक्टर लेयर कैसे बनाएं** ऑब्जेक्ट्स को खोजेंगे जो Aspose.GIS for .NET के साथ एक spatial reference system (SRS) शामिल करते हैं। हम SRS असाइन करने के कारणों को समझेंगे, इसे सेट करने के सटीक चरण दिखाएंगे, और वास्तविक दुनिया के लाभ जैसे सटीक माप और अन्य GIS डेटा के साथ सहज ओवरले समझाएंगे। अंत तक, आप किसी भी .NET एप्लिकेशन में मजबूत GIS कार्यक्षमता एम्बेड करने के लिए तैयार होंगे।

## त्वरित उत्तर
- **इस ट्यूटोरियल का मुख्य उद्देश्य क्या है?** Aspose.GIS for .NET का उपयोग करके निर्दिष्ट SRS के साथ वेक्टर लेयर बनाने का प्रदर्शन करना।  
- **उदाहरण में कौन सा प्रोजेक्शन उपयोग किया गया है?** World Mercator (EPSG:3395)।  
- **क्या कोड चलाने के लिए लाइसेंस चाहिए?** विकास के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए एक व्यावसायिक लाइसेंस आवश्यक है।  
- **क्या मैं अन्य GIS फ़ॉर्मेट्स के साथ भी यही तरीका उपयोग कर सकता हूँ?** हाँ, वही SRS हैंडलिंग Shapefile, GeoJSON, KML आदि पर लागू होती है।  
- **कौन से .NET संस्करण समर्थित हैं?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7।

## वेक्टर लेयर क्या है और इसका spatial reference क्यों सेट करें?
एक **वेक्टर लेयर** ज्यामितीय फीचर्स (बिंदु, रेखाएँ, बहुभुज) को एट्रिब्यूट डेटा के साथ संग्रहीत करती है। एक **spatial reference system** असाइन करने से GIS सॉफ़्टवेयर को पता चलता है कि इन निर्देशांक को पृथ्वी की सतह पर कैसे मैप किया जाए, जिससे सटीक दूरी गणना, सही लेयर संरेखण, और विश्वसनीय मानचित्र रेंडरिंग सुनिश्चित होती है।

## spatial reference system क्यों सेट करें?
परिभाषित SRS का उपयोग करने से विभिन्न स्रोतों से लेयर्स को ओवरले करने पर कोऑर्डिनेट‑कन्वर्ज़न त्रुटियों को 95 % तक कम किया जा सकता है। Aspose.GIS **20+** इनपुट और आउटपुट फ़ॉर्मेट्स—जैसे Shapefile, GeoJSON, KML, और GML—को सपोर्ट करता है, जबकि सैकड़ों पृष्ठों वाले डेटासेट को पूरी फ़ाइल को मेमोरी में लोड किए बिना प्रोसेस करता है।

## पूर्वापेक्षाएँ
- C# और .NET विकास का बुनियादी ज्ञान।  
- Aspose.GIS for .NET लाइब्रेरी स्थापित है। आप इसे **[here](https://releases.aspose.com/gis/net/)** से डाउनलोड कर सकते हैं।  
- एक विकास वातावरण (Visual Studio, VS Code, या कोई भी C# IDE)।  

## नेमस्पेस इम्पोर्ट करें
सुनिश्चित करें कि आपके C# फ़ाइल के शीर्ष पर आवश्यक नेमस्पेस इम्पोर्ट किए गए हैं:

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

## spatial reference (SRS) सेट करने का तरीका – चरण 1
दो लाइनों में अपना प्रोजेक्टेड SRS लोड करें: एक `ProjectedSpatialReferenceSystem` इंस्टेंस बनाएं, Mercator प्रोजेक्शन पैरामीटर कॉन्फ़िगर करें, और आप इसे लेयर से जोड़ने के लिए तैयार हैं।

`ProjectedSpatialReferenceSystem` एक क्लास है जो प्रोजेक्टेड कोऑर्डिनेट रेफ़रेंस सिस्टम का वर्णन करती है।  
`ProjectedSpatialReferenceSystemParameters` उन पैरामीटरों को रखता है जो प्रोजेक्टेड SRS को कॉन्फ़िगर करने के लिए आवश्यक होते हैं, जैसे सेंट्रल मेरिडियन और स्केल फ़ैक्टर।

आइए World Mercator प्रोजेक्शन का उपयोग करके एक **projected spatial reference system** बनाते हैं। यह लेयर के लिए **srs सेट करने का तरीका** दर्शाता है।

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
एक Shapefile लेयर को इंस्टैंसिएट करें, पहले परिभाषित `projectedSrs` पास करें, और फिर उन ज्योमेट्रीज़ को जोड़ें जिनका `SpatialReferenceSystem` लेयर के SRS से मेल खाता है।

`Layer` (जैसे, एक Shapefile) एकल GIS फ़ाइल में संग्रहीत फीचर्स के संग्रह का प्रतिनिधित्व करता है।  
अब हम **वेक्टर लेयर** (एक Shapefile) बनाएँगे और उन फीचर्स को जोड़ेंगे जो हमने अभी परिभाषित किए हुए SRS का उपयोग करते हैं। यह भाग Aspose.GIS के साथ **लेयर कैसे बनाएं** का उत्तर देता है।

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

## Spatial Reference System सत्यापित करें – चरण 3
नए बनाए गए लेयर को खोलें, उसका `SpatialReferenceSystem` प्राप्त करें, और `IsEquivalent` का उपयोग करके इसे मूल `projectedSrs` से तुलना करें। `true` परिणाम यह पुष्टि करता है कि SRS सही ढंग से लागू हुआ है।

`IsEquivalent` जांचता है कि क्या दो spatial reference systems एक ही कोऑर्डिनेट सिस्टम का प्रतिनिधित्व करते हैं।  
अंत में, लेयर खोलें और पुष्टि करें कि SRS सही ढंग से लागू हुआ है।

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

यदि `IsEquivalent` कॉल `true` लौटाता है, तो आपने सफलतापूर्वक वांछित spatial reference के साथ **वेक्टर लेयर बनायी** है।

## सामान्य समस्याएँ और समाधान
`GisException` वह एक्सेप्शन प्रकार है जो Aspose.GIS द्वारा असंगत SRS जैसी त्रुटियों के लिए फेंका जाता है।

| समस्या | क्यों होता है | समाधान |
|--------|--------------|--------|
| `GisException` जब फीचर जोड़ रहे हों | ज्यामिति लेयर से अलग SRS उपयोग करती है | `feature.Geometry.SpatialReferenceSystem` को जोड़ने से पहले लेयर के SRS पर सेट करें |
| GIS सॉफ़्टवेयर में लेयर खाली दिखती है | Shapefile उचित `.prj` फ़ाइल के बिना बनाई गई थी | लेयर बनाते समय `projectedSrs` ऑब्जेक्ट पास किया गया है, यह सुनिश्चित करें |
| अप्रत्याशित कोऑर्डिनेट मान | गलत प्रोजेक्शन पैरामीटर (जैसे, सेंट्रल मेरिडियन) | `AddProjectionParameter` को पास किए गए पैरामीटरों को दोबारा जांचें |

## अक्सर पूछे जाने वाले प्रश्न
### क्या Aspose.GIS सभी GIS फ़ाइल फ़ॉर्मेट्स के साथ संगत है?
Aspose.GIS **20+** GIS फ़ॉर्मेट्स को सपोर्ट करता है, जिसमें Shapefile, GeoJSON, KML, GML, और अधिक शामिल हैं। पूरी सूची के लिए **[documentation](https://reference.aspose.com/gis/net/)** देखें।

### क्या मैं Aspose.GIS को वेब एप्लिकेशन में उपयोग कर सकता हूँ?
बिल्कुल! Aspose.GIS for .NET ASP.NET, ASP.NET Core, और किसी भी सर्वर‑साइड .NET वातावरण में काम करता है।

### Aspose.GIS के लिए समर्थन कहाँ प्राप्त कर सकता हूँ?
आप किसी भी प्रश्न या समस्या के लिए **[Aspose.GIS forum](https://forum.aspose.com/c/gis/33)** पर एक सहायक समुदाय पा सकते हैं।

### क्या कोई मुफ्त ट्रायल उपलब्ध है?
हां, आप Aspose.GIS की सुविधाओं को एक मुफ्त ट्रायल **[here](https://releases.aspose.com/)** प्राप्त करके देख सकते हैं।

### मैं Aspose.GIS के लिए लाइसेंस कैसे खरीद सकता हूँ?
लाइसेंस खरीदने के लिए, **[purchase page](https://purchase.aspose.com/buy)** पर जाएँ।

## अक्सर पूछे जाने वाले प्रश्न (अतिरिक्त)

**प्र: यदि मैं अलग SRS के साथ एक ज्योमेट्री जोड़ने की कोशिश करता हूँ तो क्या होता है?**  
**उ:** Aspose.GIS एक `GisException` फेंकता है। आपको या तो ज्योमेट्री को पुनःप्रोजेक्ट करना होगा या यह सुनिश्चित करना होगा कि वह लेयर के SRS को साझा करे।

**प्र: क्या मैं मौजूदा लेयर का SRS बदल सकता हूँ?**  
**उ:** हाँ, आप वांछित SRS के साथ एक नई लेयर बना सकते हैं और फीचर्स को कॉपी कर सकते हैं, आवश्यकतानुसार उन्हें पुनःप्रोजेक्ट करते हुए।

**प्र: क्या 3D कोऑर्डिनेट्स के साथ काम करना संभव है?**  
**उ:** Aspose.GIS Z‑कोऑर्डिनेट्स को सपोर्ट करता है; बस ऐसे geometry कंस्ट्रक्टर्स का उपयोग करें जो Z मान स्वीकार करते हैं।

**प्र: क्या लाइब्रेरी डेटम ट्रांसफ़ॉर्मेशन को स्वचालित रूप से संभालती है?**  
**उ:** जब आप `Geometry.Transform` का उपयोग करके ज्योमेट्रीज़ को पुनःप्रोजेक्ट करते हैं, तो Aspose.GIS आवश्यक डेटम शिफ्ट करता है।

**प्र: कौन से .NET संस्करण आधिकारिक रूप से परीक्षण किए गए हैं?**  
**उ:** लाइब्रेरी .NET Framework 4.5+, .NET Core 3.1+, और .NET 5/6/7 के साथ परीक्षण किया गया है।

## निष्कर्ष
आपने अब Aspose.GIS for .NET का उपयोग करके एक कस्टम spatial reference system के साथ **वेक्टर लेयर कैसे बनाएं** सीख लिया है। सही SRS सेट करके, ज्योमेट्री को लगातार संभालकर, और लेयर के मेटाडेटा को सत्यापित करके, आप ऐसे मजबूत GIS‑सक्षम एप्लिकेशन बना सकते हैं जो किसी भी मानक GIS सॉफ़्टवेयर के साथ इंटरऑपरेट कर सकते हैं।

**अंतिम अपडेट:** 2026-06-30  
**परीक्षित संस्करण:** Aspose.GIS 24.11 for .NET (लेखन के समय नवीनतम)  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल
- [वेक्टर लेयर बनाएं और लेयर Spatial Reference System सेट करें](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [File GDB में वेक्टर लेयर बनाएं – Aspose.GIS .NET ट्यूटोरियल](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [लेयर को संशोधित कैसे करें – Aspose.GIS .NET लेयर इंटरैक्शन](/gis/net/layer-interaction-and-data-access/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}