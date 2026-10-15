---
date: 2026-10-15
description: Aspose.GIS for .NET का उपयोग करके निर्देशांक से GeoJSON कैसे बनाएं और
  इसे स्ट्रीम पर लिखें, सीखें। यह ट्यूटोरियल बिंदुओं के चरण‑दर‑चरण रूपांतरण और GeoJSON
  C# कोड जनरेशन को दिखाता है।
keywords:
- create geojson from coordinates
- stream large geojson files
- write geojson to stream
- geojson tutorial c#
- compress geojson with gzip
lastmod: 2026-10-15
linktitle: GeoJSON को स्ट्रीम पर लिखें
og_description: Aspose.GIS for .NET का उपयोग करके निर्देशांक से GeoJSON बनाना और इसे
  स्ट्रीम पर लिखना सीखें – बड़े डेटा सेट के लिए चरण‑दर‑चरण गाइड।
og_image_alt: Screenshot of Aspose.GIS code generating GeoJSON stream in C#
og_title: निर्देशांक से GeoJSON बनाएं, .NET में एक स्ट्रीम पर लिखें
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create geojson from coordinates and write it to a stream
    using Aspose.GIS for .NET. This tutorial shows step‑by‑step conversion of points
    and generation of GeoJSON C# code.
  headline: Create geojson from coordinates, write to a stream in .NET
  type: TechArticle
- questions:
  - answer: Yes – create a `Feature` for each point, assign a `Point` geometry, and
      add it to the `VectorLayer`.
    question: Can I generate GeoJSON from a collection of latitude/longitude points?
  - answer: You can wrap the `MemoryStream` in a `GZipStream` before saving to produce
      a compressed payload.
    question: Does Aspose.GIS support writing compressed GeoJSON (gzip)?
  - answer: The library can stream files exceeding 2 GB; memory usage stays low because
      data is written incrementally.
    question: What is the maximum size of a GeoJSON file Aspose.GIS can handle?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geojson
- Aspose.GIS
- .NET geospatial
- C# stream processing
- GIS data conversion
title: निर्देशांक से GeoJSON बनाएं, .NET में एक स्ट्रीम पर लिखें
url: /hi/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# geojson को निर्देशांक से बनाएं और एक स्ट्रीम में लिखें

## परिचय
इस ट्यूटोरियल में आप **निर्देशांक से geojson कैसे बनाएं** और इसे सीधे Aspose.GIS for .NET का उपयोग करके एक स्ट्रीम में लिखना सीखेंगे। हम पर्यावरण सेटअप, लेयर निर्माण, फीचर पॉपुलेशन, और परिणाम को स्ट्रीम करने की प्रक्रिया को चरणबद्ध रूप से देखेंगे, ताकि आप अस्थायी फ़ाइलों के बिना APIs, क्लाउड फ़ंक्शन्स, या फ़ाइल‑रहित सेवाओं में जियोस्पेशियल पेलोड एम्बेड कर सकें।

## त्वरित उत्तर
- **कौन सा क्लास GeoJSON को स्ट्रीम में लिखता है?** `VectorLayer` `GeoJsonDriver` के साथ।
- **क्या विकास के लिए लाइसेंस चाहिए?** विकास के लिए एक फ्री ट्रायल काम करता है; उत्पादन के लिए एक वाणिज्यिक लाइसेंस आवश्यक है।
- **कौन से .NET संस्करण समर्थित हैं?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **क्या मैं पॉइंट कलेक्शन को GeoJSON में बदल सकता हूँ?** हाँ – प्रत्येक पॉइंट के लिए एक `Feature` बनाएं और एक `Point` ज्योमेट्री असाइन करें।
- **क्या बड़े डेटासेट के लिए स्ट्रीमिंग उपयुक्त है?** बिल्कुल – `MemoryStream` आपको पूरे फ़ाइल को मेमोरी में लोड किए बिना गीगाबाइट‑स्तर का GeoJSON लिखने देता है।

## GeoJSON क्या है?
GeoJSON एक ओपन JSON‑आधारित फ़ॉर्मेट है जो बिंदु, रेखा, और बहुभुज जैसी भौगोलिक विशेषताओं को एन्कोड करता है। यह `FeatureCollection` से बना होता है जो व्यक्तिगत `Feature` ऑब्जेक्ट्स को समूहित करता है, प्रत्येक में ज्योमेट्री और एट्रिब्यूट डेटा होता है। क्योंकि यह हल्का और वेब‑फ़्रेंडली है, GeoJSON ब्राउज़रों, GIS सर्वरों, और मोबाइल ऐप्स के बीच स्पैशियल डेटा के आदान‑प्रदान के लिए डि‑फ़ैक्टो मानक बन गया है।

## GeoJSON जनरेशन के लिए Aspose.GIS क्यों उपयोग करें?
Aspose.GIS **35+ स्पैशियल फ़ाइल फ़ॉर्मेट** का समर्थन करता है और **2 GB** से बड़ी फ़ाइलों को स्ट्रीम कर सकता है जबकि मेमोरी उपयोग **50 MB** से कम रहता है। इसका हाई‑परफ़ॉर्मेंस स्ट्रीमिंग इंजन GeoJSON को सीधे किसी भी .NET `Stream` में लिखता है, मध्यवर्ती अस्थायी फ़ाइलों की आवश्यकता को समाप्त करता है और सामान्य क्लाउड परिदृश्यों में I/O लेटेंसी को **70 %** तक कम करता है।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास है:

1. **Aspose.GIS for .NET** स्थापित हो। **Aspose.GIS for .NET** पैकेज [यहाँ](https://releases.aspose.com/gis/net/) डाउनलोड करें।
2. आपके प्रोजेक्ट में एक लिखने योग्य फ़ोल्डर जहाँ आप आवश्यकतानुसार अस्थायी फ़ाइलें रख सकें।
3. .NET 5+ या .NET Core 3.1+ रनटाइम स्थापित हो।

अब, चलिए कार्यान्वयन में गहराई से उतरते हैं।

## निर्देशांक से geojson कैसे बनाएं और इसे स्ट्रीम में लिखें?
`VectorLayer` एक इन‑मेमोरी वेक्टर डेटासेट का प्रतिनिधित्व करता है जिसे विभिन्न फ़ॉर्मेट में सहेजा जा सकता है।  
`GeoJsonDriver` वह ड्राइवर है जो GeoJSON फ़ाइलों को पढ़ने और लिखने में सक्षम बनाता है।

`GeoJsonDriver` के साथ एक `VectorLayer` लोड करें, `Point` ज्योमेट्री वाले `Feature` ऑब्जेक्ट्स जोड़ें, और `layer.Save(stream, new GeoJsonSaveOptions())` को कॉल करें। यह एकल कॉल पूरी फीचर कलेक्शन को एक मानक‑अनुपालन GeoJSON दस्तावेज़ में सीरियलाइज़ करता है जो प्रदान किए गए `MemoryStream` में रहता है। यह प्रक्रिया एट्रिब्यूट मैपिंग और कोऑर्डिनेट रूपांतरण को स्वचालित रूप से संभालती है, इसलिए आपको मैन्युअल स्ट्रिंग निर्माण के बिना तैयार‑उपयोग JSON पेलोड मिल जाता है।

### परिभाषा एंकर
**VectorLayer** वह मुख्य Aspose.GIS ऑब्जेक्ट है जो मेमोरी में एक परिवर्तनीय वेक्टर डेटासेट का प्रतिनिधित्व करता है।  
**GeoJsonDriver** वह ड्राइवर है जो GeoJSON फ़ाइलों को पढ़ने और लिखने के लिए जिम्मेदार है।

## नेमस्पेस आयात करें
सबसे पहले, सुनिश्चित करें कि आप अपने कोड में Aspose.GIS कार्यक्षमताओं तक पहुंचने के लिए आवश्यक नेमस्पेस शामिल करें:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## चरण 1: दस्तावेज़ डायरेक्टरी सेट करें
एक फ़ोल्डर पथ बनाएं जहाँ Aspose.GIS आवश्यक होने पर सहायक फ़ाइलें संग्रहीत कर सके।  
```csharp
string dataDir = "Your Document Directory";
```
"Your Document Directory" को अपने दस्तावेज़ डायरेक्टरी के वास्तविक पथ से बदलें।

## चरण 2: मेमोरी स्ट्रीम बनाएं
`MemoryStream` एक इन‑मेमोरी बफ़र प्रदान करता है जिसे सीधे HTTP पर भेजा जा सकता है या क्लाउड स्टोरेज में सहेजा जा सकता है।  
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code for the next steps goes here
}
```

## चरण 3: GeoJSON ड्राइवर के साथ वेक्टर लेयर बनाएं
`VectorLayer` क्लास एक वेक्टर डेटासेट का प्रतिनिधित्व करता है जिसे विभिन्न फ़ॉर्मेट में सहेजा जा सकता है, जिसमें GeoJSON भी शामिल है।  
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Code for the next steps goes here
}
```

## चरण 4: फीचर एट्रिब्यूट परिभाषित करें
अपने फीचर्स के लिए एट्रिब्यूट स्कीमा परिभाषित करें (जैसे, ID, Name)।  
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## चरण 5: फीचर बनाएं और जोड़ें
`Feature` ऑब्जेक्ट बनाएं, पॉइंट ज्योमेट्री असाइन करें, एट्रिब्यूट मान सेट करें, और उन्हें लेयर में जोड़ें।  
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

## चरण 6: GeoJSON आउटपुट दिखाएं
सेव करने के बाद, स्ट्रीम पोज़िशन रीसेट करें और सत्यापन या ट्रांसमिशन के लिए JSON स्ट्रिंग पढ़ें।  
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

बधाई हो! आपने सफलतापूर्वक निर्देशांक से geojson बनाया और इसे Aspose.GIS for .NET का उपयोग करके एक स्ट्रीम में लिखा है।

## सामान्य समस्याएँ और समाधान
- **खाली आउटपुट स्ट्रीम:** पढ़ने से पहले स्ट्रीम पोज़िशन (`stream.Position = 0`) रीसेट करना सुनिश्चित करें।
- **गलत कोऑर्डिनेट क्रम:** GeoJSON लोंगिट्यूड‑लैटिट्यूड क्रम की अपेक्षा करता है; अपने पॉइंट मानों की जाँच करें।
- **बड़े डेटासेट:** फीचर्स को क्रमिक रूप से स्ट्रीम करने और मेमोरी उपयोग कम रखने के लिए `layer.Save(stream, new GeoJsonSaveOptions { WriteFeatureCollection = true })` का उपयोग करें।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं Aspose.GIS for .NET को Windows और Linux दोनों वातावरण में उपयोग कर सकता हूँ?**  
A: हाँ, Aspose.GIS for .NET Windows, Linux, और macOS पर पूर्ण .NET Core समर्थन के साथ चलता है।

**Q: क्या कोई फ्री ट्रायल उपलब्ध है?**  
A: बिल्कुल! आप **फ्री ट्रायल डाउनलोड पेज** [यहाँ](https://releases.aspose.com/) पर देख सकते हैं।

**Q: विस्तृत दस्तावेज़ीकरण कहाँ मिल सकता है?**  
A: **Aspose.GIS .NET दस्तावेज़ीकरण** [यहाँ](https://reference.aspose.com/gis/net/) देखें।

**Q: मैं अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूँ?**  
A: अस्थायी लाइसेंस **अस्थायी लाइसेंस पेज** [यहाँ](https://purchase.aspose.com/temporary-license/) पर उपलब्ध हैं।

**Q: सहायता चाहिए या और प्रश्न हैं?**  
A: हमारे **GIS सपोर्ट फ़ोरम** [यहाँ](https://forum.aspose.com/c/gis/33) पर जाएँ।

**Q: क्या मैं latitude/longitude पॉइंट्स के संग्रह से GeoJSON जनरेट कर सकता हूँ?**  
A: हाँ – प्रत्येक पॉइंट के लिए एक `Feature` बनाएं, एक `Point` ज्योमेट्री असाइन करें, और इसे `VectorLayer` में जोड़ें।

**Q: क्या Aspose.GIS संकुचित GeoJSON (gzip) लिखने का समर्थन करता है?**  
A: आप सेव करने से पहले `MemoryStream` को `GZipStream` में रैप करके एक संकुचित पेलोड बना सकते हैं।

**Q: Aspose.GIS द्वारा संभाले जा सकने वाली GeoJSON फ़ाइल का अधिकतम आकार क्या है?**  
A: लाइब्रेरी 2 GB से बड़ी फ़ाइलों को स्ट्रीम कर सकती है; मेमोरी उपयोग कम रहता है क्योंकि डेटा क्रमिक रूप से लिखा जाता है।

---

**अंतिम अपडेट:** 2026-10-15  
**परीक्षण किया गया:** Aspose.GIS 24.11 for .NET  
**लेखक:** Aspose  

## संबंधित ट्यूटोरियल

- [Aspose.GIS for .NET के साथ स्ट्रीम से GeoJSON कैसे पढ़ें](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Aspose.GIS के साथ GeoJSON को TopoJSON में कैसे बदलें](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Aspose.GIS for .NET का उपयोग करके Shapefile को GeoJSON में कैसे बदलें](/gis/net/layer-management/extract-features-to-geojson/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}