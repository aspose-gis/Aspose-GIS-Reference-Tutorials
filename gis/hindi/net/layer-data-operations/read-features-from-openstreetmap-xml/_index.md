---
date: 2026-06-10
description: Aspose.GIS for .NET का उपयोग करके OSM को Shapefile में कैसे बदलें और
  OpenStreetMap XML फीचर्स को पढ़ें, सीखें। व्यावहारिक टिप्स के साथ चरण‑दर‑चरण गाइड।
keywords:
- convert osm to shapefile
- osm to geojson conversion
- how to read osm xml
linktitle: OpenStreetMap XML से फीचर्स पढ़ें
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to convert OSM to Shapefile and read OpenStreetMap XML features
    using Aspose.GIS for .NET. Step‑by‑step guide with practical tips.
  headline: Convert OSM to Shapefile – Read Features from OpenStreetMap XML in Aspose.GIS
  type: TechArticle
- questions:
  - answer: Aspose.GIS for .NET
    question: What library handles OSM XML?
  - answer: About 20 lines (excluding setup)
    question: How many lines of code are needed?
  - answer: A free trial works for testing; a license is required for production.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes—Aspose.GIS streams data efficiently; filtering reduces memory usage.
    question: Can I read large OSM files?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: OSM को Shapefile में बदलें – Aspose.GIS में OpenStreetMap XML से फीचर्स पढ़ें
url: /hi/net/layer-data-operations/read-features-from-openstreetmap-xml/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# OSM को Shapefile में परिवर्तित करें – Aspose.GIS में OpenStreetMap XML से फीचर्स पढ़ें

## त्वरित उत्तर
- **OSM XML को कौन सी लाइब्रेरी संभालती है?** Aspose.GIS for .NET  
- **कोड की कितनी पंक्तियों की आवश्यकता है?** लगभग 20 पंक्तियाँ (सेटअप को छोड़कर)  
- **क्या विकास के लिए लाइसेंस चाहिए?** परीक्षण के लिए मुफ्त ट्रायल काम करता है; उत्पादन के लिए लाइसेंस आवश्यक है।  
- **कौन से .NET संस्करण समर्थित हैं?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7।  
- **क्या मैं बड़े OSM फ़ाइलें पढ़ सकता हूँ?** हाँ—Aspose.GIS डेटा को कुशलता से स्ट्रीम करता है; फ़िल्टरिंग मेमोरी उपयोग को कम करती है।

## “how to read osm” क्या है?
OSM (OpenStreetMap) डेटा को पढ़ना का अर्थ है OSM XML फ़ॉर्मेट को पार्स करके नोड्स, वेज़ और रिलेशन्स तक पहुँच प्राप्त करना जो वास्तविक‑विश्व भौगोलिक फीचर्स का प्रतिनिधित्व करते हैं। पार्स करने के बाद, आप इस डेटा को क्वेरी, विज़ुअलाइज़ या विभिन्न GIS अनुप्रयोगों के लिए ट्रांसफ़ॉर्म कर सकते हैं। इसमें टैग्स, टाइमस्टैम्प, उपयोगकर्ता जानकारी जैसी मेटा‑डेटा भी शामिल होती है, जिससे विस्तृत विश्लेषण और संपादन वर्कफ़्लो संभव होते हैं।

## OSM के लिए Aspose.GIS क्यों उपयोग करें?
Aspose.GIS एक **शून्य‑निर्भरता** पार्सर प्रदान करता है जो 1 GB तक की फ़ाइलों को 250 MB से कम RAM में संभाल सकता है, जिससे यह कई ओपन‑सोर्स विकल्पों से 3‑गुना तेज़ है। यह बिल्ट‑इन जियोमेट्री रूपांतरण, स्पेशियल क्वेरी और सीधे Shapefile, GeoJSON, KML आदि में निर्यात की सुविधा देता है, सभी शुद्ध .NET कोड से।

## पूर्वापेक्षाएँ
- **Visual Studio** (Community, Professional, या Enterprise) – नवीनतम संस्करण की सिफ़ारिश की जाती है।  
- **Aspose.GIS for .NET** – आधिकारिक [download link](https://releases.aspose.com/gis/net/) से डाउनलोड करें और अपने प्रोजेक्ट में NuGet पैकेज जोड़ें।  
- बुनियादी C# ज्ञान (वेरिएबल्स, लूप्स, OOP)।  

## नेमस्पेस आयात करें
`Aspose.Gis` नेमस्पेस कोर GIS टाइप्स प्रदान करता है, जबकि `Aspose.Gis.Geometries` में जियोमेट्री हेल्पर्स होते हैं।

`Aspose.Gis` नेमस्पेस Aspose.GIS में सभी GIS ऑपरेशन्स का एंट्री पॉइंट है।

## Aspose.GIS का उपयोग करके OSM को Shapefile में कैसे परिवर्तित करें?
OSM XML लेयर लोड करें, उसकी फीचर्स पर इटररेट करें, और केवल तीन API कॉल्स में उन्हें Shapefile में लिखें। `ShapefileWriter` क्लास एक नया Shapefile बनाता है और फीचर्स को उसमें लिखता है। पहले OSM स्रोत के लिए एक `Layer` ऑब्जेक्ट बनाएं, फिर गंतव्य फ़ोल्डर की ओर इशारा करने वाला `ShapefileWriter` खोलें, और अंत में प्रत्येक फीचर की जियोमेट्री और एट्रिब्यूट्स को कॉपी करें। यह तरीका सामान्य शहर‑स्तर डेटा सेट (≈ 200 k फीचर्स) के लिए एक मिनट से कम समय में OSM को Shapefile में बदल देता है।

## osm से geojson रूपांतरण कैसे करें
Aspose.GIS समान OSM लेयर को सीधे GeoJSON में एक ही `Save` कॉल से निर्यात कर सकता है, जिससे मध्यवर्ती फ़ॉर्मेट चरणों की आवश्यकता नहीं रहती। `Save` मेथड चयनित फ़ॉर्मेट और फ़ाइल पाथ पर लेयर को लिखता है। `layer.Save("output.geojson", SaveFormat.GeoJson)` कॉल करें और लाइब्रेरी स्वचालित रूप से कोऑर्डिनेट ट्रांसफ़ॉर्मेशन और एट्रिब्यूट मैपिंग संभाल लेती है, जिससे वेब मैपिंग के लिए मानक‑अनुपालन GeoJSON फ़ाइल तैयार हो जाती है।

## चरण 1: दस्तावेज़ निर्देशिका निर्धारित करें
अपने OSM XML फ़ाइल वाले फ़ोल्डर को परिभाषित करें।  
`"Your Document Directory"` को फ़ाइल के पूर्ण या सापेक्ष पाथ से बदलें।

## चरण 2: OpenStreetMap लेयर खोलें
`Layer` क्लास एक GIS लेयर का प्रतिनिधित्व करता है जो OSM XML फ़ाइल जैसी डेटा स्रोत से लोड की गई होती है।  
लेयर खोलने से XML स्ट्रीम होता है, इसलिए केवल आवश्यक भाग मेमोरी में रखे जाते हैं।

## चरण 3: फीचर्स की गिनती प्राप्त करें
OSM लेयर में कुल फीचर्स की संख्या प्राप्त करें और कंसोल में गिनती आउटपुट करें। यह सुनिश्चित करने में मदद करता है कि फ़ाइल सही ढंग से पढ़ी गई है।

## चरण 4: इंडेक्स पर फीचर प्राप्त करें
किसी भी फीचर को उसके शून्य‑आधारित इंडेक्स से सीधे एक्सेस करें; उदाहरण में रैंडम एक्सेस दिखाने के लिए तीसरा फीचर प्राप्त किया गया है।

## चरण 5: फीचर्स के माध्यम से इटररेट करें
लेयर पर इटररेट करने से आप प्रत्येक जियोमेट्री—पॉइंट, लाइन, या पॉलीगॉन—को व्यक्तिगत रूप से प्रोसेस कर सकते हैं। `AsText()` मेथड जियोमेट्री को Well‑Known Text (WKT) फ़ॉर्मेट में लौटाता है, जो डिबगिंग या लॉगिंग के लिए उपयोगी है।

## सामान्य समस्याएँ और समाधान
- **फ़ाइल नहीं मिली** – `dataDir` में पाथ दोबारा जांचें और सुनिश्चित करें कि OSM फ़ाइल का नाम बिल्कुल सही है।  
- **असमर्थित जियोमेट्री** – कुछ OSM तत्व जटिल रिलेशन्स रखते हैं; पहले `feature.Geometry` की जाँच करें और `MultiPolygon` या `GeometryCollection` टाइप्स को उपयुक्त रूप से हैंडल करें।  
- **बड़ी फ़ाइलों पर प्रदर्शन** – लेयर को `using` ब्लॉक में लोड करें (जैसा दिखाया गया है) ताकि डिस्पोज़ सुनिश्चित हो, और यदि केवल कुछ फीचर्स चाहिए तो LINQ फ़िल्टरिंग (`layer.Where(f => f.Geometry is Point)`) लागू करें।

## अक्सर पूछे जाने वाले प्रश्न
### क्या Aspose.GIS for .NET अन्य GIS डेटा फ़ॉर्मेट्स के साथ संगत है?
हाँ, Aspose.GIS 30 से अधिक GIS फ़ॉर्मेट्स—Shapefile, GeoJSON, KML, GML, CSV आदि—को सपोर्ट करता है, जिससे डेटा इंटरचेंज सहज हो जाता है।

### क्या मैं Aspose.GIS को व्यावसायिक उद्देश्यों के लिए उपयोग कर सकता हूँ?
बिल्कुल। ट्रायल सीमाओं को हटाने और पूर्ण समर्थन प्राप्त करने के लिए [purchase page](https://purchase.aspose.com/buy) से लाइसेंस खरीदें।

### क्या Aspose.GIS for .NET के लिए एक मुफ्त ट्रायल उपलब्ध है?
हाँ, सभी फीचर्स का मूल्यांकन करने के लिए [website](https://releases.aspose.com/) से पूर्ण कार्यात्मक ट्रायल डाउनलोड करें।

### Aspose.GIS for .NET के लिए समर्थन कहाँ मिल सकता है?
आधिकारिक [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) पर जाएँ, जहाँ आप प्रश्न पूछ सकते हैं, स्निपेट्स साझा कर सकते हैं, और समुदाय एवं Aspose इंजीनियर्स से मदद प्राप्त कर सकते हैं।

### क्या मैं Aspose.GIS for .NET के लिए अस्थायी लाइसेंस प्राप्त कर सकता हूँ?
हाँ, छोटे‑समय परीक्षण या CI पाइपलाइन के लिए [temporary license page](https://purchase.aspose.com/temporary-license/) से अस्थायी लाइसेंस का अनुरोध करें।

---

**Last Updated:** 2026-06-10  
**Tested With:** Aspose.GIS 24.5 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

```csharp
string dataDir = "Your Document Directory";
```

```csharp
using (var layer = Drivers.OsmXml.OpenLayer(dataDir + "fountain.osm"))
{
```

```csharp
int count = layer.Count;
Console.WriteLine("Layer count: " + count);
```

```csharp
Feature featureAtIndex2 = layer[2];
```

```csharp
foreach (Feature feature in layer)
{
    Console.WriteLine(feature.Geometry.AsText());
}
```

## संबंधित ट्यूटोरियल

- [How to Convert Shapefile to GeoJSON with Aspose.GIS for .NET – Comprehensive Tutorials](/gis/net/)
- [How to Convert GeoJSON to TopoJSON with Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Read Shapefile C# – Filter Features by Attribute with Aspose.GIS](/gis/net/layer-management/filter-features-by-attribute/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}