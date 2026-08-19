---
date: 2026-06-25
description: Aspose.GIS for .NET का उपयोग करके shapefile को पढ़ना और polygon shapefile
  को linestring में बदलना सीखें। स्पष्ट चरण‑दर‑चरण मार्गदर्शन के साथ अपने GIS विकास
  को बढ़ाएँ।
keywords:
- how to read shapefile
- convert polygon to line
- shapefile to geojson c#
- extract lines from polygon
linktitle: Polygon Shapefile को Linestring में बदलें
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to read shapefile and convert a polygon shapefile to a linestring
    using Aspose.GIS for .NET. Boost your GIS development with clear step‑by‑step
    guidance.
  headline: How to Read Shapefile C# – Convert Polygon Shapefile to Linestring
  type: TechArticle
- description: Learn how to read shapefile and convert a polygon shapefile to a linestring
    using Aspose.GIS for .NET. Boost your GIS development with clear step‑by‑step
    guidance.
  name: How to Read Shapefile C# – Convert Polygon Shapefile to Linestring
  steps:
  - name: Set the Document Directory
    text: Replace `"Your Document Directory"` with the actual path where your shapefile
      resides.
  - name: Open the Source Shapefile
    text: This line opens the source Polygon Shapefile so you can read its features.
  - name: Create the Destination Linestring Shapefile
    text: Here we create a new Linestring Shapefile that will store the converted
      geometries.
  - name: Iterate Through Source Features
    text: The loop walks through each polygon feature in the original file.
  - name: Convert Polygon to Linestring and Write to Destination
    text: The `ExteriorRing` property returns the outer boundary of a polygon as a
      `LineString`. In this block we convert polygon to line (`LineString`) and add
      the new feature to the destination shapefile.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS supports .NET Framework 4.5+, .NET Core 3.1+, and .NET
      5/6/7, ensuring seamless integration with modern development stacks.
    question: Is Aspose.GIS compatible with all versions of .NET?
  - answer: Yes, you can. Purchase a license [here](https://purchase.aspose.com/buy)
      to remove evaluation limitations and obtain full support.
    question: Can I use Aspose.GIS for commercial projects?
  - answer: Yes, you can find comprehensive documentation and code samples on the
      [documentation page](https://reference.aspose.com/gis/net/).
    question: Are there any examples or documentation available?
  - answer: Absolutely – explore Aspose.GIS with a free trial by visiting [this link](https://releases.aspose.com/).
    question: Is there a trial version available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      assistance and official support.
    question: Where can I seek help or support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Shapefile C# को कैसे पढ़ें – Polygon Shapefile को Linestring में बदलें
url: /hi/net/layer-management/convert-polygon-shapefile-to-linestring/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Shapefile पढ़ें C# – Polygon Shapefile को Linestring में बदलें

## परिचय
यदि आपको .NET वातावरण में **how to read shapefile** डेटा पढ़ने की आवश्यकता है, तो आप सही जगह पर हैं। Aspose.GIS for .NET Shapefile के लो‑लेवल बाइनरी फॉर्मेट को एब्स्ट्रैक्ट करता है, जिससे आप कुछ ही API कॉल्स से जियोग्राफिक फीचर्स को लोड, क्वेरी और ट्रांसफ़ॉर्म कर सकते हैं। Polygon Shapefile को Linestring में बदलना विशेष रूप से उपयोगी है जब आप रूटिंग, नेटवर्क विश्लेषण, या सरल विज़ुअलाइज़ेशन के लिए रैखिक प्रतिनिधित्व निकालना चाहते हैं।

## त्वरित उत्तर
- **कौन सी लाइब्रेरी आपको shapefile c# पढ़ने में मदद करती है?** Aspose.GIS for .NET – यह 50+ GIS फ़ॉर्मेट्स को सपोर्ट करता है और कई सौ मेगाबाइट तक की फ़ाइलों को पूरी फ़ाइल को मेमोरी में लोड किए बिना संभालता है।  
- **क्या आप एक polygon को line में बदल सकते हैं?** हाँ – polygon की exterior ring पर `LineString` कॉल करें और परिणाम को नई shapefile में लिखें।  
- **क्या उत्पादन के लिए लाइसेंस की आवश्यकता है?** उत्पादन परिनियोजन के लिए एक व्यावसायिक लाइसेंस आवश्यक है; मूल्यांकन के लिए एक मुफ्त ट्रायल काम करता है।  
- **कौन से .NET संस्करण समर्थित हैं?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **क्या ट्रायल उपलब्ध है?** बिल्कुल – Aspose साइट से एक मुफ्त ट्रायल डाउनलोड करें।

`LineString` एक ज्योमेट्री प्रकार है जो जुड़े हुए रेखा खंडों की श्रृंखला का प्रतिनिधित्व करता है।

## “read shapefile c#” क्या है?
`Document` वह कोर क्लास है जो एक GIS डेटासेट का प्रतिनिधित्व करती है और इसकी फ़ीचर्स तक पहुँच प्रदान करती है।  
C# में shapefile पढ़ना मतलब `.shp` फ़ाइल को मेमोरी में लोड करना है ताकि आप उसकी ज्योमेट्रीज़ को क्वेरी, संशोधित या ट्रांसफ़ॉर्म कर सकें। **आप बस `Document` क्लास को फ़ाइल पाथ के साथ इंस्टैंशिएट करते हैं, और Aspose.GIS आपके लिए बाइनरी स्ट्रक्चर को पार्स करता है**, जिससे आसान‑से‑उपयोग कलेक्शन के माध्यम से फ़ीचर्स उपलब्ध होते हैं। यह तरीका लो‑लेवल फ़ाइल हेडर या कोऑर्डिनेट एरेज़ के साथ मैन्युअल काम करने की आवश्यकता को समाप्त करता है।

## Aspose.GIS के साथ polygon को line में क्यों बदलें?
Polygon को Linestring में बदलने से बाहरी सीमा ठीक वैसी ही रहती है जबकि अंदरूनी रिंग्स हट जाती हैं, जिससे आपको एक साफ़ रैखिक प्रतिनिधित्व मिलता है। Aspose.GIS **डेटासेट्स को 500 MB तक 2 सेकंड से कम समय में प्रोसेस करता है**, जिससे बैच रूपांतरण तेज़ और मेमोरी‑कुशल होते हैं। लाइब्रेरी मूल स्पैशियल रेफ़रेंस को भी बरकरार रखती है, इसलिए परिणामी लाइन्स किसी भी मौजूदा GIS लेयर के साथ पूरी तरह संरेखित होती हैं।

## पूर्वापेक्षाएँ
ट्यूटोरियल शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित उपलब्ध हों:

- **Aspose.GIS Library** – Aspose.GIS लाइब्रेरी को [वेबसाइट](https://releases.aspose.com/gis/net/) से डाउनलोड और इंस्टॉल करें।  
- **Shapefile Data** – रूपांतरण के लिए एक Polygon Shapefile तैयार रखें। यदि आपके पास नहीं है, तो आप नमूना डेटा पा सकते हैं या अपना स्वयं का बना सकते हैं।  
- **Development Environment** – आवश्यक टूल्स (Visual Studio, .NET SDK, आदि) के साथ अपना .NET विकास वातावरण सेट अप करें।

## नेमस्पेस इम्पोर्ट करें
`Document` क्लास Aspose.GIS का कोर ऑब्जेक्ट है जो एक GIS डेटासेट का प्रतिनिधित्व करता है और shapefile पढ़ने‑लिखने के मेथड्स प्रदान करता है। अपने कोड फ़ाइल की शुरुआत में निम्नलिखित नेमस्पेस जोड़ें:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## shapefile कैसे पढ़ें और polygon को linestring में बदलें?
स्रोत polygon shapefile लोड करें, प्रत्येक polygon की exterior ring निकालें, उस रिंग से एक `LineString` बनाएं, और परिणाम को नई shapefile में लिखें – यह पाँच सरल चरणों में किया जा सकता है। यह पैटर्न किसी भी आकार के डेटासेट के लिए काम करता है और स्रोत के कोऑर्डिनेट सिस्टम को लक्ष्य में संरक्षित रखता है।

### चरण 1: Document डायरेक्टरी सेट करें
```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```
`"Your Document Directory"` को उस वास्तविक पाथ से बदलें जहाँ आपका shapefile स्थित है।

### चरण 2: स्रोत Shapefile खोलें
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
यह लाइन स्रोत Polygon Shapefile को खोलती है ताकि आप उसकी फ़ीचर्स पढ़ सकें।

### चरण 3: लक्ष्य Linestring Shapefile बनाएं
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
यहाँ हम एक नई Linestring Shapefile बनाते हैं जो रूपांतरित ज्योमेट्रीज़ को संग्रहीत करेगी।

### चरण 4: स्रोत फ़ीचर्स पर इटररेट करें
```csharp
foreach (Feature sourceFeature in source)
{
    // Rest of the code will go here
}
```
यह लूप मूल फ़ाइल में प्रत्येक polygon फ़ीचर के माध्यम से चलता है।

### चरण 5: Polygon को Linestring में बदलें और लक्ष्य में लिखें
`ExteriorRing` प्रॉपर्टी एक polygon की बाहरी सीमा को `LineString` के रूप में लौटाती है।  
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
इस ब्लॉक में हम polygon को line (`LineString`) में बदलते हैं और नई फ़ीचर को लक्ष्य shapefile में जोड़ते हैं।

## सामान्य समस्याएँ और टिप्स
- **Coordinate System Mismatch** – सुनिश्चित करें कि स्रोत और लक्ष्य दोनों लेयर्स एक ही स्पैशियल रेफ़रेंस का उपयोग करें; अन्यथा लाइन्स विस्थापित दिख सकती हैं।  
- **Large Files** – बहुत बड़े shapefiles को प्रोसेस करते समय सभी फ़ीचर्स को एक साथ मेमोरी में लोड करने के बजाय स्ट्रीमिंग पर विचार करें।  
- **Null Geometries** – खाली ज्योमेट्री वाले फ़ीचर्स से बचें ताकि रन‑टाइम एक्सेप्शन न आए।  
- **Extract lines from polygon** – यदि आपको केवल exterior ring चाहिए, तो `ExteriorRing` प्रॉपर्टी का उपयोग करें; अंदरूनी रिंग्स के लिए `InteriorRings` को इटररेट करें।  

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या Aspose.GIS सभी .NET संस्करणों के साथ संगत है?**  
उत्तर: हाँ, Aspose.GIS .NET Framework 4.5+, .NET Core 3.1+, और .NET 5/6/7 को सपोर्ट करता है, जिससे आधुनिक विकास स्टैक के साथ सहज एकीकरण सुनिश्चित होता है।

**प्रश्न: क्या मैं Aspose.GIS को व्यावसायिक प्रोजेक्ट्स में उपयोग कर सकता हूँ?**  
उत्तर: हाँ, आप कर सकते हैं। मूल्यांकन सीमाओं को हटाने और पूर्ण समर्थन प्राप्त करने के लिए [यहाँ](https://purchase.aspose.com/buy) लाइसेंस खरीदें।

**प्रश्न: क्या कोई उदाहरण या दस्तावेज़ उपलब्ध हैं?**  
उत्तर: हाँ, आप व्यापक दस्तावेज़ीकरण और कोड नमूने [documentation page](https://reference.aspose.com/gis/net/) पर पा सकते हैं।

**प्रश्न: क्या ट्रायल संस्करण उपलब्ध है?**  
उत्तर: बिल्कुल – [इस लिंक](https://releases.aspose.com/) पर जाकर मुफ्त ट्रायल के साथ Aspose.GIS का अन्वेषण करें।

**प्रश्न: मैं सहायता या समर्थन कहाँ प्राप्त कर सकता हूँ?**  
उत्तर: समुदाय सहायता और आधिकारिक समर्थन के लिए [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) देखें।

---

**Last Updated:** 2026-06-25  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [How to Convert Shapefile to GeoJSON using Aspose.GIS for .NET](/gis/net/layer-management/extract-features-to-geojson/)
- [How to Read GeoJSON from Stream with Aspose.GIS for .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [How to Create Polygon Geometry with Aspose.GIS for .NET](/gis/net/geometry-creation/create-polygon-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}