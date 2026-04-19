---
date: 2026-01-10
description: Aspose.GIS for .NET का उपयोग करके shapefile को C# में पढ़ना और एक polygon
  shapefile को linestring में बदलना सीखें। स्पष्ट चरण‑दर‑चरण मार्गदर्शन के साथ अपने
  GIS विकास को तेज़ बनाएं।
linktitle: Convert Polygon Shapefile to Linestring
second_title: Aspose.GIS .NET API
title: Shapefile पढ़ें C# – Polygon Shapefile को Linestring में बदलें
url: /hi/net/layer-management/convert-polygon-shapefile-to-linestring/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Read Shapefile C# – Polygon Shapefile को Linestring में बदलें

## Introduction
यदि आप .NET में जियोग्राफिक इन्फॉर्मेशन सिस्टम्स (GIS) के साथ काम कर रहे हैं, तो **read shapefile c#** डेटा को हेरफेर करने से पहले एक सामान्य पहला कदम है। Aspose.GIS इस प्रक्रिया को सरल बनाता है, जिससे आप कुछ ही कोड लाइनों के साथ एक Polygon Shapefile को Linestring में बदल सकते हैं। यह क्षमता विशेष रूप से तब उपयोगी होती है जब आपको पॉलीगॉन डेटा सेट से रैखिक फीचर निकालने की आवश्यकता होती है, जैसे कि रूट प्लानिंग, नेटवर्क एनालिसिस, या डेटा विज़ुअलाइज़ेशन के लिए।

## Quick Answers
- **कौन सी लाइब्रेरी आपको read shapefile c# पढ़ने में मदद करती है?** Aspose.GIS for .NET  
- **क्या आप पॉलीगॉन को लाइन में बदल सकते हैं?** हाँ – पॉलीगॉन की एक्सटीरियर रिंग के साथ `LineString` का उपयोग करें।  
- **क्या प्रोडक्शन के लिए लाइसेंस चाहिए?** प्रोडक्शन उपयोग के लिए एक कमर्शियल लाइसेंस आवश्यक है।  
- **कौन से .NET संस्करण समर्थित हैं?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+।  
- **क्या ट्रायल उपलब्ध है?** बिल्कुल – Aspose साइट से एक मुफ्त ट्रायल डाउनलोड करें।

## What is “read shapefile c#”?
C# में shapefile पढ़ना मतलब `.shp` फ़ाइल को मेमोरी में लोड करना ताकि आप उसकी ज्योमेट्रीज़ को क्वेरी, मॉडिफ़ाई या ट्रांसफ़ॉर्म कर सकें। Aspose.GIS एक सरल API प्रदान करता है जो लो‑लेवल विवरणों को एब्स्ट्रैक्ट करता है और आपको GIS लॉजिक पर ध्यान केंद्रित करने देता है।

## Why convert polygon to line with Aspose.GIS?
- **टोपोलॉजी बनाए रखें** – परिवर्तन प्रत्येक पॉलीगॉन की सटीक बाहरी सीमा को रखता है।  
- **परफ़ॉर्मेंस** – लाइब्रेरी बड़े डेटा सेट के लिए ऑप्टिमाइज़्ड है, जिससे बैच कन्वर्ज़न तेज़ होते हैं।  
- **लचीलापन** – आप बाद में लाइन्स्ट्रिंग को किसी अन्य shapefile, GeoJSON, या किसी भी समर्थित फ़ॉर्मेट में लिख सकते हैं।

## Prerequisites
ट्यूटोरियल शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित उपलब्ध हों:

- **Aspose.GIS Library** – Aspose.GIS लाइब्रेरी को [website](https://releases.aspose.com/gis/net/) से डाउनलोड और इंस्टॉल करें।  
- **Shapefile Data** – कन्वर्ज़न के लिए एक Polygon Shapefile तैयार रखें। यदि आपके पास नहीं है, तो आप सैंपल डेटा पा सकते हैं या अपना स्वयं का बना सकते हैं।  
- **Development Environment** – आवश्यक टूल्स (Visual Studio, .NET SDK, आदि) के साथ अपना .NET डेवलपमेंट एनवायरनमेंट सेट अप करें।

## Import Namespaces
अपने C# कोड में, आवश्यक क्लास और मेथड्स तक पहुंचने के लिए Aspose.GIS नेमस्पेस को इम्पोर्ट करना होगा। अपने कोड फ़ाइल की शुरुआत में निम्नलिखित नेमस्पेस जोड़ें:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## How to convert shapefile from polygon to line?
नीचे एक चरण‑दर‑चरण गाइड दिया गया है जो **shapefile को पॉलीगॉन से लाइन में बदलने** की प्रक्रिया दिखाता है, Aspose.GIS का उपयोग करके।

### Step 1: Set the Document Directory
```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```
`"Your Document Directory"` को उस वास्तविक पाथ से बदलें जहाँ आपका shapefile स्थित है।

### Step 2: Open the Source Shapefile
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
यह लाइन **स्रोत Polygon Shapefile को खोलती है** ताकि आप उसकी फीचर्स पढ़ सकें।

### Step 3: Create the Destination Linestring Shapefile
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
यहाँ हम **एक नया Linestring Shapefile बनाते हैं** जो परिवर्तित ज्योमेट्रीज़ को संग्रहीत करेगा।

### Step 4: Iterate Through Source Features
```csharp
foreach (Feature sourceFeature in source)
{
    // Rest of the code will go here
}
```
यह लूप मूल फ़ाइल में प्रत्येक पॉलीगॉन फीचर के माध्यम से चलता है।

### Step 5: Convert Polygon to Linestring and Write to Destination
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
इस ब्लॉक में हम **पॉलीगॉन को लाइन में बदलते** हैं (`LineString`) और नई फीचर को लक्ष्य shapefile में जोड़ते हैं।

## Common Issues and Tips
- **Coordinate System Mismatch** – सुनिश्चित करें कि स्रोत और लक्ष्य दोनों लेयर एक ही स्पेशियल रेफ़रेंस का उपयोग करें; अन्यथा लाइन्स विस्थापित दिख सकती हैं।  
- **Large Files** – बहुत बड़े shapefiles को प्रोसेस करते समय सभी फीचर्स को एक बार मेमोरी में लोड करने के बजाय स्ट्रीमिंग पर विचार करें।  
- **Null Geometries** – खाली ज्योमेट्री वाले फीचर्स से बचें ताकि रन‑टाइम एक्सेप्शन न आए।

## Frequently Asked Questions

**Q: क्या Aspose.GIS सभी .NET संस्करणों के साथ संगत है?**  
A: हाँ, Aspose.GIS विभिन्न .NET संस्करणों को सपोर्ट करता है, जिससे आपका डेवलपमेंट एनवायरनमेंट संगत रहता है।

**Q: क्या मैं Aspose.GIS को कमर्शियल प्रोजेक्ट्स में उपयोग कर सकता हूँ?**  
A: हाँ, आप कर सकते हैं। कमर्शियल प्रोजेक्ट्स में Aspose.GIS उपयोग करने के लिए [here](https://purchase.aspose.com/buy) से लाइसेंस खरीदने पर विचार करें।

**Q: क्या कोई उदाहरण या डॉक्यूमेंटेशन उपलब्ध है?**  
A: हाँ, आप व्यापक डॉक्यूमेंटेशन और उदाहरण [documentation page](https://reference.aspose.com/gis/net/) पर पा सकते हैं।

**Q: क्या ट्रायल वर्ज़न उपलब्ध है?**  
A: हाँ, आप मुफ्त ट्रायल के लिए [this link](https://releases.aspose.com/) पर जाकर Aspose.GIS का अन्वेषण कर सकते हैं।

**Q: मैं सहायता या सपोर्ट कहाँ प्राप्त कर सकता हूँ?**  
A: किसी भी सहायता या सपोर्ट‑संबंधी प्रश्नों के लिए [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) पर जाएँ।

---

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}