---
date: 2026-06-15
description: Aspose.GIS for .NET के साथ vector layer बनाना और layer spatial reference
  system सेट करना सीखें। spatial reference को परिभाषित करना, point feature जोड़ना,
  और EPSG code प्राप्त करना में निपुण बनें।
keywords:
- create vector layer
- add point feature
- set layer coordinate system
- define epsg code
- how to set crs
linktitle: Layer Spatial Reference System सेट करें
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  headline: Create Vector Layer and Set Layer Spatial Reference System
  type: TechArticle
- description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  name: Create Vector Layer and Set Layer Spatial Reference System
  steps:
  - name: Specify the Document Directory
    text: Begin by specifying the path to your document directory. This will be the
      location where your spatial data files are stored.
  - name: Define Spatial Reference and Set Shapefile Coordinate System
    text: SpatialReferenceSystem represents the CRS of a layer, identified by an EPSG
      code. Define the path for the Shapefile, and **define spatial reference** using
      the EPSG code (26918 in this example). This step **sets the shapefile coordinate
      system** for the layer.
  - name: Create Vector Layer
    text: '`ConstructFeature` creates a new feature object that can hold geometry
      and attribute data. Now **create vector layer** with the specified Shapefile
      path, driver type (Shapefile), and the spatial reference system you just defined.'
  - name: Add Point Feature to the Layer
    text: Construct a new feature and **add point feature** by setting its geometry
      (a `Point` with coordinates 60, 24). Then add the feature to the vector layer.
  - name: Retrieve Spatial Reference System Information (Retrieve EPSG Code)
    text: Open the Vector Layer and retrieve information about the spatial reference
      system, such as the EPSG code and the human‑readable name. This demonstrates
      how to **retrieve EPSG code** and **set layer CRS**.
  type: HowTo
- questions:
  - answer: Open the layer, create a new `SpatialReferenceSystem` with the desired
      EPSG code, assign it to `layer.SpatialReferenceSystem`, then save the layer.
    question: How do I change the CRS of an existing Shapefile?
  - answer: Yes—replace `new Point(x, y)` with `new Polygon(...)` or `new LineString(...)`
      as needed.
    question: Can I add other geometry types (e.g., polygons) using the same approach?
  - answer: Use streaming APIs (`VectorLayer.Create` with `FeatureCollection`) and
      dispose layers promptly to free resources.
    question: Is it possible to work with large datasets efficiently?
  - answer: Yes—use `Geometry.Transform(targetSrs)` to reproject geometries between
      different spatial references.
    question: Does Aspose.GIS support coordinate transformation?
  - answer: Aspose.GIS works with .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Vector Layer बनाएं और Layer Spatial Reference System सेट करें
url: /hi/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# वेक्टर लेयर बनाएं और लेयर स्पैटियल रेफ़रेंस सिस्टम सेट करें

## परिचय
भौगोलिक सूचना प्रणाली (GIS) के विशाल परिदृश्य में, **Aspose.GIS for .NET** एक मजबूत, उच्च‑प्रदर्शन लाइब्रेरी के रूप में उभरती है जो **70+** वेक्टर और रास्टर फ़ॉर्मेट का समर्थन करती है और **10 GB** से बड़े फ़ाइलों को पूरी डेटा सेट को मेमोरी में लोड किए बिना प्रोसेस कर सकती है। इस ट्यूटोरियल में आप **वेक्टर लेयर बनाएँगे**, उसका स्पैटियल रेफ़रेंस निर्धारित करेंगे, **पॉइंट फीचर जोड़ेंगे**, और EPSG कोड प्राप्त करेंगे—सभी स्पष्ट, चरण‑दर‑चरण मार्गदर्शन के साथ। चाहे आप मैपिंग सेवा, डेटा‑कन्वर्ज़न पाइपलाइन, या स्पैटियल एनालिटिक्स इंजन बना रहे हों, इन मूलभूत बातों में निपुणता आपके शैपफ़ाइल कोऑर्डिनेट सिस्टम को सटीक रखेगी और आपका GIS वर्कफ़्लो विश्वसनीय रहेगा।

## त्वरित उत्तर
- **“create vector layer” का क्या अर्थ है?** यह एक नया GIS लेयर (जैसे, Shapefile) बनाता है जो पॉइंट, लाइन, या पॉलीगॉन जैसी ज्योमेट्रीज़ को संग्रहीत कर सकता है।  
- **उदाहरण में कौन सा EPSG कोड उपयोग किया गया है?** EPSG 26918 (NAD83 / UTM zone 18N).  
- **लेयर बनाने के बाद क्या मैं पॉइंट फीचर जोड़ सकता हूँ?** हाँ—`ConstructFeature()` का उपयोग करें और एक `Point` ज्योमेट्री असाइन करें।  
- **लेयर का CRS कैसे प्राप्त करूँ?** `layer.SpatialReferenceSystem.EpsgCode` या `.Name` पढ़ें।  
- **क्या मुझे Aspose.GIS के लिए लाइसेंस चाहिए?** एक मुफ्त ट्रायल उपलब्ध है; उत्पादन उपयोग के लिए लाइसेंस आवश्यक है।  

## वेक्टर लेयर बनाना क्या है?
**create vector layer** ऑपरेशन एक नया वेक्टर डेटासेट (जैसे Shapefile) बनाता है जो ज्यामितीय फीचर और एट्रिब्यूट डेटा रख सकता है। Aspose.GIS में, यह एक `VectorLayer` ऑब्जेक्ट को ड्राइवर और स्पैटियल रेफ़रेंस सिस्टम के साथ इंस्टैंसिएट करके किया जाता है।

## लेयर कोऑर्डिनेट सिस्टम (CRS) सही ढंग से सेट क्यों करें?
सही कोऑर्डिनेट रेफ़रेंस सिस्टम (CRS) सेट करने से यह सुनिश्चित होता है कि आप द्वारा संग्रहीत प्रत्येक ज्योमेट्री अन्य स्पैटियल डेटासेट्स के साथ संरेखित हो। Aspose.GIS के साथ आप एक मानक EPSG कोड का उपयोग करके CRS को परिभाषित कर सकते हैं, जो विश्वभर के GIS सॉफ़्टवेयर के साथ इंटरऑपरेबिलिटी की गारंटी देता है। उदाहरण के लिए, EPSG 26918 NAD83 / UTM zone 18N को परिभाषित करता है, जो संयुक्त राज्य के पूर्वी भाग में डेटा के लिए एक सामान्य प्रोजेक्शन है।

## पूर्वापेक्षाएँ
- .NET विकास अनुभव (C# या VB.NET)।  
- Visual Studio 2022 या बाद का संस्करण।  
- Aspose.GIS for .NET लाइब्रेरी – इसे **[here](https://releases.aspose.com/gis/net/)** से डाउनलोड करें।  
- स्पैटियल रेफ़रेंस सिस्टम (CRS/EPSG) की बुनियादी समझ।

## नेमस्पेस आयात करें
`Aspose.Gis` नेमस्पेस कोर GIS क्लासेस प्रदान करता है, जबकि `Aspose.Gis.Geometries` आपको `Point` जैसी ज्योमेट्री टाइप्स देता है।

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## Aspose.GIS for .NET में वेक्टर लेयर कैसे बनाते हैं?
`VectorLayer` एक वेक्टर डेटासेट (जैसे Shapefile) का प्रतिनिधित्व करता है और फीचर बनाने, पढ़ने और संपादित करने के लिए मेथड्स प्रदान करता है।  
`SpatialReferenceSystem` EPSG कोड का उपयोग करके कोऑर्डिनेट रेफ़रेंस सिस्टम को परिभाषित करता है।

टार्गेट फ़ोल्डर लोड करें, EPSG‑कोडेड `SpatialReferenceSystem` परिभाषित करें, और Shapefile ड्राइवर के साथ `VectorLayer.Create` को कॉल करें। यह एकल कॉल एक नई `.shp` फ़ाइल बनाता है, साथ की `.shx` और `.dbf` फ़ाइलें लिखता है, और CRS मेटाडाटा एम्बेड करता है, जिससे फीचर इन्सर्शन कुशलता से तैयार हो जाता है।

### चरण 1: दस्तावेज़ डायरेक्टरी निर्दिष्ट करें
सबसे पहले अपने दस्तावेज़ डायरेक्टरी का पाथ निर्दिष्ट करें। यह वह स्थान होगा जहाँ आपके स्पैटियल डेटा फ़ाइलें संग्रहीत होंगी।

```csharp
string dataDir = "Your Document Directory";
```

### चरण 2: स्पैटियल रेफ़रेंस परिभाषित करें और Shapefile कोऑर्डिनेट सिस्टम सेट करें
`SpatialReferenceSystem` एक लेयर के CRS को दर्शाता है, जो EPSG कोड द्वारा पहचाना जाता है।  

Shapefile का पाथ परिभाषित करें, और EPSG कोड (इस उदाहरण में 26918) का उपयोग करके **स्पैटियल रेफ़रेंस परिभाषित** करें। यह चरण लेयर के लिए **shapefile कोऑर्डिनेट सिस्टम सेट** करता है।

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## वेक्टर लेयर में पॉइंट फीचर कैसे जोड़ें?
`Point` एक ज्योमेट्री टाइप है जो एकल X/Y कॉर्डिनेट जोड़ी का प्रतिनिधित्व करता है।  

एक नया फीचर बनाएं, इच्छित X/Y कॉर्डिनेट्स के साथ एक `Point` ज्योमेट्री असाइन करें, और इस फीचर को खुले `VectorLayer` में जोड़ें। यह ऑपरेशन ज्योमेट्री को `.shp` फ़ाइल में और एट्रिब्यूट रिकॉर्ड को `.dbf` फ़ाइल में एक ही ट्रांज़ैक्शन में लिखता है।

### चरण 3: वेक्टर लेयर बनाएं
`ConstructFeature` एक नया फीचर ऑब्जेक्ट बनाता है जो ज्योमेट्री और एट्रिब्यूट डेटा रख सकता है।  

अब आप निर्दिष्ट Shapefile पाथ, ड्राइवर टाइप (Shapefile), और अभी परिभाषित किए गए स्पैटियल रेफ़रेंस सिस्टम के साथ **वेक्टर लेयर बनाएं**।

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

### चरण 4: लेयर में पॉइंट फीचर जोड़ें
एक नया फीचर बनाएं और उसकी ज्योमेट्री (कोऑर्डिनेट 60, 24 वाला `Point`) सेट करके **पॉइंट फीचर जोड़ें**। फिर इस फीचर को वेक्टर लेयर में जोड़ें।

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

### चरण 5: स्पैटियल रेफ़रेंस सिस्टम जानकारी प्राप्त करें (EPSG कोड प्राप्त करें)
Vector Layer खोलें और स्पैटियल रेफ़रेंस सिस्टम की जानकारी प्राप्त करें, जैसे EPSG कोड और मानव‑पठनीय नाम। यह दर्शाता है कि कैसे **EPSG कोड प्राप्त करें** और **लेयर CRS सेट करें**।

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

## सामान्य समस्याएँ और समाधान
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **लेयर खोलने में विफल** | गलत ड्राइवर या भ्रष्ट फ़ाइल पाथ | सुनिश्चित करें कि `Drivers.Shapefile` सही है और `path` मौजूदा `.shp` फ़ाइल की ओर इशारा करता है। |
| **गलत CRS प्रदर्शित** | गलत EPSG कोड का उपयोग करना | प्राधिकृत स्रोत (जैसे, EPSG.io) से EPSG कोड दोबारा जांचें। |
| **फ़ीचर सहेजा नहीं गया** | `using` ब्लॉक के भीतर `layer.Add(feature)` नहीं कॉल किया गया | लेयर डिस्पोज़ होने से पहले `Add` मेथड को निष्पादित करना सुनिश्चित करें। |

## अक्सर पूछे जाने वाले प्रश्न
**Q: मौजूदा Shapefile का CRS कैसे बदलें?**  
A: लेयर खोलें, इच्छित EPSG कोड के साथ एक नया `SpatialReferenceSystem` बनाएं, उसे `layer.SpatialReferenceSystem` को असाइन करें, फिर लेयर को सहेजें।

**Q: क्या मैं उसी तरीके से अन्य ज्योमेट्री टाइप्स (जैसे, polygons) जोड़ सकता हूँ?**  
A: हाँ—ज़रूरत अनुसार `new Point(x, y)` को `new Polygon(...)` या `new LineString(...)` से बदलें।

**Q: क्या बड़े डेटासेट्स के साथ कुशलता से काम करना संभव है?**  
A: स्ट्रीमिंग API (`VectorLayer.Create` साथ `FeatureCollection`) का उपयोग करें और संसाधनों को मुक्त करने के लिए लेयर्स को तुरंत डिस्पोज़ करें।

**Q: क्या Aspose.GIS कोऑर्डिनेट ट्रांसफ़ॉर्मेशन का समर्थन करता है?**  
A: हाँ—विभिन्न स्पैटियल रेफ़रेंस के बीच ज्योमेट्री को रीप्रोजेक्ट करने के लिए `Geometry.Transform(targetSrs)` का उपयोग करें।

**Q: कौन से .NET संस्करण समर्थित हैं?**  
A: Aspose.GIS .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7 के साथ काम करता है।

---

**अंतिम अपडेट:** 2026-06-15  
**परीक्षित संस्करण:** Aspose.GIS 24.11 for .NET  
**लेखक:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [Aspose.GIS for .NET का उपयोग करके वेक्टर लेयर बनाएं और लीनियराइज़ेशन टॉलरेंस सेट करें](/gis/net/geometry-processing/set-linearization-tolerance/)
- [फ़ाइल GDB में वेक्टर लेयर बनाएं – Aspose.GIS .NET ट्यूटोरियल](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [स्पैटियल रेफ़रेंस wgs84 – Aspose.GIS का उपयोग करके GDB में लेयर जोड़ें](/gis/net/layer-management/add-layer-to-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}