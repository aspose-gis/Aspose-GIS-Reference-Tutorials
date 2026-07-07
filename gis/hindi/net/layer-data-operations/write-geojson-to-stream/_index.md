---
date: 2026-05-21
description: Aspose.GIS for .NET का उपयोग करके GeoJSON को स्ट्रीम में लिखना सीखें।
  यह GeoJSON ट्यूटोरियल .NET बिंदुओं के चरण‑दर‑चरण रूपांतरण और GeoJSON C# कोड के निर्माण
  को दर्शाता है।
keywords:
- how to write geojson
- convert points geojson
- geojson tutorial .net
- generate geojson c#
linktitle: GeoJSON को स्ट्रीम में लिखें
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to write GeoJSON to stream using Aspose.GIS for .NET. This
    geojson tutorial .net shows step‑by‑step conversion of points and generation of
    GeoJSON C# code.
  headline: How to Write GeoJSON to Stream with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes – create a `Feature` for each point, assign a `Point` geometry, and
      add it to the `VectorLayer`.
    question: Can I generate GeoJSON from a collection of latitude/longitude points?
  - answer: You can wrap the `MemoryStream` in a `GZipStream` before saving to produce
      a compressed payload.
    question: Does Aspose.GIS support writing compressed GeoJSON (gzip)?
  - answer: The library can stream files exceeding 2 GB; memory usage stays low because
      data is written incrementally.
    question: What is the maximum size of a GeoJSON file Aspose.GIS can handle?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET के साथ GeoJSON को स्ट्रीम में लिखने का तरीका
url: /hi/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GeoJSON को स्ट्रीम में लिखें

## परिचय
इस ट्यूटोरियल में आप Aspose.GIS का उपयोग करके .NET एप्लिकेशन में **स्ट्रीम में GeoJSON लिखने** के तरीके सीखेंगे। हम प्रत्येक चरण को विस्तार से देखेंगे, पर्यावरण सेटअप से लेकर एक वैध GeoJSON दस्तावेज़ आउटपुट करने तक, ताकि आप अपने सर्विसेज़ में जियोस्पेशियल डेटा को सहजता से एकीकृत कर सकें।

## त्वरित उत्तर
- **GeoJSON आउटपुट के लिए मुख्य क्लास कौन सी है?** `VectorLayer` साथ में `GeoJsonDriver`।
- **क्या विकास के लिए लाइसेंस की आवश्यकता है?** विकास के लिए एक फ्री ट्रायल काम करता है; उत्पादन के लिए एक व्यावसायिक लाइसेंस आवश्यक है।
- **कौन से .NET संस्करण समर्थित हैं?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **क्या मैं पॉइंट कलेक्शन को GeoJSON में बदल सकता हूँ?** हाँ – `Feature` क्लास का उपयोग करें और पॉइंट जियोमेट्री परिभाषित करें।
- **क्या बड़े डेटासेट के लिए स्ट्रीमिंग समर्थित है?** बिल्कुल; `MemoryStream` आपको मध्यवर्ती फ़ाइलों के बिना लिखने की अनुमति देता है।

## GeoJSON क्या है?
GeoJSON एक ओपन स्टैंडर्ड फ़ॉर्मेट है जो JSON का उपयोग करके विभिन्न भौगोलिक डेटा संरचनाओं को एन्कोड करता है। यह FeatureCollection, Feature, और जियोमेट्री प्रकारों (Point, LineString, Polygon) जैसे ऑब्जेक्ट्स को परिभाषित करता है। यह हल्का, वेब‑फ्रेंडली प्रतिनिधित्व कई प्लेटफ़ॉर्म और प्रोग्रामिंग भाषाओं में स्पैशियल डेटा के आसान आदान‑प्रदान और विज़ुअलाइज़ेशन को सक्षम बनाता है।

## GeoJSON जनरेशन के लिए Aspose.GIS क्यों उपयोग करें?
Aspose.GIS 30 से अधिक स्पैशियल फ़ाइल फ़ॉर्मेट्स को समर्थन देता है और पूरे दस्तावेज़ को मेमोरी में लोड किए बिना 2 GB से बड़ी फ़ाइलों को प्रोसेस कर सकता है। इसका हाई‑परफ़ॉर्मेंस स्ट्रीमिंग इंजन GeoJSON को सीधे स्ट्रीम में लिखता है, जिससे I/O ओवरहेड कम होता है। यह एंटरप्राइज़‑स्तर के जियोस्पेशियल वर्कलोड्स, क्लाउड सर्विसेज़, और रियल‑टाइम एप्लिकेशन्स के लिए आदर्श बनाता है।

## पूर्वापेक्षाएँ
ट्यूटोरियल शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
1. Aspose.GIS for .NET लाइब्रेरी: सुनिश्चित करें कि आपके पास Aspose.GIS for .NET लाइब्रेरी स्थापित है। आप इसे [here](https://releases.aspose.com/gis/net/) से डाउनलोड कर सकते हैं।
2. डॉक्यूमेंट डायरेक्टरी: अपने प्रोजेक्ट में एक डॉक्यूमेंट डायरेक्टरी सेट करें, और उसके पाथ को नोट कर लें।

अब, चलिए ट्यूटोरियल शुरू करते हैं!

## मैं GeoJSON को स्ट्रीम में कैसे लिखूँ?
VectorLayer एक वेक्टर डेटासेट को दर्शाता है जिसे विभिन्न फ़ॉर्मेट्स में सहेजा जा सकता है, जिसमें GeoJSON भी शामिल है।  
GeoJsonDriver वह ड्राइवर है जिसका उपयोग Aspose.GIS GeoJSON फ़ाइलों को पढ़ने और लिखने के लिए करता है।  
`layer.Save` निर्दिष्ट सेव ऑप्शन्स का उपयोग करके लेयर की सामग्री को प्रदान किए गए स्ट्रीम में लिखता है।

`GeoJsonDriver` के साथ एक `VectorLayer` लोड करें, पॉइंट जियोमेट्री वाले फीचर जोड़ें, और फिर `layer.Save(stream, new GeoJsonSaveOptions())` कॉल करें। यह कुछ ही कोड लाइनों में प्रदान किए गए `MemoryStream` में सीधे एक पूर्ण, मानकों‑अनुरूप GeoJSON दस्तावेज़ लिखता है। यह मेथड फीचर कलेक्शन को सीरियलाइज़ करता है, एट्रिब्यूट डेटा और जियोमेट्री रूपांतरण को स्वचालित रूप से संभालता है, जिससे आप मैन्युअल स्ट्रिंग मैनिपुलेशन के बिना तैयार‑उपयोग JSON पेलोड प्राप्त करते हैं।

## नेमस्पेस इम्पोर्ट करें
सबसे पहले, सुनिश्चित करें कि आप अपने कोड में Aspose.GIS कार्यक्षमताओं तक पहुँचने के लिए आवश्यक नेमस्पेस शामिल करें:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## चरण 1: डॉक्यूमेंट डायरेक्टरी सेट अप करें
```csharp
string dataDir = "Your Document Directory";
```
`Your Document Directory` को अपने डॉक्यूमेंट डायरेक्टरी के वास्तविक पाथ से बदलें।

## चरण 2: मेमोरी स्ट्रीम बनाएं
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code for the next steps goes here
}
```

## चरण 3: GeoJSON ड्राइवर के साथ वेक्टर लेयर बनाएं
`VectorLayer` क्लास एक वेक्टर डेटासेट को दर्शाता है जिसे विभिन्न फ़ॉर्मेट्स में, जिसमें GeoJSON भी शामिल है, सहेजा जा सकता है।  
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Code for the next steps goes here
}
```

## चरण 4: फीचर एट्रिब्यूट्स परिभाषित करें
अपने फीचर्स के लिए एट्रिब्यूट स्कीमा परिभाषित करें (जैसे, ID, Name)।
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## चरण 5: फीचर्स बनाएं और जोड़ें
`Feature` ऑब्जेक्ट्स बनाएं, पॉइंट जियोमेट्री असाइन करें, एट्रिब्यूट वैल्यू सेट करें, और उन्हें लेयर में जोड़ें।  
```csharp
// First Feature
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);
// Second Feature
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```

## चरण 6: GeoJSON आउटपुट प्रदर्शित करें
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

बधाई हो! आपने Aspose.GIS for .NET का उपयोग करके सफलतापूर्वक GeoJSON को स्ट्रीम में लिखा है।

## सामान्य समस्याएँ और समाधान
- **खाली आउटपुट स्ट्रीम:** पढ़ने से पहले स्ट्रीम पोजीशन (`stream.Position = 0`) रीसेट करें।
- **गलत कोऑर्डिनेट क्रम:** GeoJSON लोंगिट्यूड‑लैटिट्यूड क्रम की अपेक्षा करता है; अपने पॉइंट वैल्यूज़ की जाँच करें।
- **बड़े डेटासेट:** फीचर्स को क्रमिक रूप से स्ट्रीम करने के लिए `layer.Save(stream, new GeoJsonSaveOptions { WriteFeatureCollection = true })` का उपयोग करें।

## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं Aspose.GIS for .NET को Windows और Linux दोनों वातावरण में उपयोग कर सकता हूँ?
हाँ, Aspose.GIS for .NET दोनों Windows और Linux सिस्टम्स के साथ संगत है।

### क्या एक फ्री ट्रायल उपलब्ध है?
बिल्कुल! आप एक फ्री ट्रायल [here](https://releases.aspose.com/) पर देख सकते हैं।

### विस्तृत दस्तावेज़ीकरण कहाँ मिल सकता है?
दस्तावेज़ीकरण देखें [here](https://reference.aspose.com/gis/net/)।

### मैं अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूँ?
अस्थायी लाइसेंस यहाँ उपलब्ध हैं [here](https://purchase.aspose.com/temporary-license/)।

### सहायता चाहिए या और प्रश्न हैं?
हमारे सपोर्ट फ़ोरम पर जाएँ [here](https://forum.aspose.com/c/gis/33)।

**प्रश्न:** क्या मैं अक्षांश/देशांतर पॉइंट्स के संग्रह से GeoJSON जनरेट कर सकता हूँ?  
**उत्तर:** हाँ – प्रत्येक पॉइंट के लिए एक `Feature` बनाएं, एक `Point` जियोमेट्री असाइन करें, और उसे `VectorLayer` में जोड़ें।

**प्रश्न:** क्या Aspose.GIS संकुचित GeoJSON (gzip) लिखने का समर्थन करता है?  
**उत्तर:** आप `MemoryStream` को `GZipStream` में रैप करके सहेजने से पहले संकुचित पेलोड बना सकते हैं।

**प्रश्न:** Aspose.GIS द्वारा संभाले जा सकने वाली GeoJSON फ़ाइल का अधिकतम आकार क्या है?  
**उत्तर:** लाइब्रेरी 2 GB से बड़ी फ़ाइलों को स्ट्रीम कर सकती है; मेमोरी उपयोग कम रहता है क्योंकि डेटा क्रमिक रूप से लिखा जाता है।

---

**अंतिम अपडेट:** 2026-05-21  
**परीक्षण किया गया:** Aspose.GIS 24.11 for .NET  
**लेखक:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल्स

- [Aspose.GIS for .NET के साथ स्ट्रीम से GeoJSON पढ़ने का तरीका](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Aspose.GIS के साथ GeoJSON को TopoJSON में बदलने का तरीका](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Aspose.GIS for .NET का उपयोग करके Shapefile को GeoJSON में बदलने का तरीका](/gis/net/layer-management/extract-features-to-geojson/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}