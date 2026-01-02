---
date: 2026-01-02
description: Aspose.GIS for .NET का उपयोग करके C# में GeoJSON को स्ट्रीम में लिखना
  सीखें। GeoJSON C# उदाहरण दिखाएँ और अपने जियोस्पेशियल ऐप्स को सुदृढ़ बनाएं।
linktitle: Write GeoJSON to Stream
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET के साथ GeoJSON को स्ट्रीम में लिखने का तरीका
url: /hi/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GeoJSON को स्ट्रीम में लिखने का तरीका

## परिचय
यदि आपको .NET एप्लिकेशन में मेमोरी या फ़ाइल स्ट्रीम में सीधे **how to write geojson** लिखने की आवश्यकता है, तो आप सही जगह पर हैं। इस ट्यूटोरियल में हम Aspose.GIS for .NET लाइब्रेरी का उपयोग करके GeoJSON को स्ट्रीम में लिखने के सटीक चरणों को दिखाएंगे, और साथ ही **display GeoJSON C#** आउटपुट को कंसोल में कैसे दिखाया जाए, भी बताएंगे। अंत तक, आपके पास एक पुन: उपयोग योग्य पैटर्न होगा जिसे आप किसी भी जियोस्पेशियल प्रोजेक्ट में लागू कर सकते हैं।

## त्वरित उत्तर
- **“write GeoJSON to stream” का क्या अर्थ है?** इसका मतलब है एक वेक्टर लेयर को GeoJSON फ़ॉर्मेट में सीरियलाइज़ करना और बाइट्स को `Stream` ऑब्जेक्ट (जैसे, `MemoryStream`) में भेजना।  
- **कौन सी लाइब्रेरी यह संभालती है?** Aspose.GIS for .NET एक बिल्ट‑इन GeoJSON ड्राइवर प्रदान करती है।  
- **क्या विकास के लिए लाइसेंस चाहिए?** विकास के लिए एक फ्री ट्रायल काम करता है; उत्पादन के लिए एक कमर्शियल लाइसेंस आवश्यक है।  
- **क्या इसे Linux पर चलाया जा सकता है?** हाँ – Aspose.GIS क्रॉस‑प्लेटफ़ॉर्म है और Windows, Linux, तथा macOS पर काम करता है।  
- **कौन से .NET संस्करण समर्थित हैं?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7।

## .NET में “how to write geojson” क्या है?
Aspose.GIS आपको एक `VectorLayer` बनाने, फीचर जोड़ने, और फिर `Drivers.GeoJson` ड्राइवर का उपयोग करके लेयर को सीरियलाइज़ करने की सुविधा देता है। ड्राइवर GeoJSON टेक्स्ट को सीधे किसी भी `Stream` में लिखता है, जिससे आप डेटा को मेमोरी, फ़ाइल, नेटवर्क आदि में जहाँ चाहें, भेज सकते हैं।

## इस कार्य के लिए Aspose.GIS क्यों उपयोग करें?
- **Zero‑dependency serialization** – कोई बाहरी JSON लाइब्रेरी आवश्यक नहीं।  
- **Full GeoJSON spec compliance** – FeatureCollections, properties, और coordinate precision को सपोर्ट करता है।  
- **Cross‑platform** – Windows, Linux, और macOS पर समान रूप से काम करता है।  
- **Performance‑optimized** – मध्यवर्ती स्ट्रिंग्स के बिना सीधे स्ट्रीम में लिखता है।

## पूर्वापेक्षाएँ
1. **Aspose.GIS for .NET** – इसे [यहाँ](https://releases.aspose.com/gis/net/) से डाउनलोड करें।  
2. **Document directory** – तय करें कि आप अस्थायी फ़ाइलें या आउटपुट स्ट्रीम कहाँ रखना चाहते हैं।

अब, चलिए कोड में डुबकी लगाते हैं।

## नेमस्पेस आयात करें
पहले उन नेमस्पेसेज़ को शामिल करें जो आपको Aspose.GIS क्लासेज़ और मानक .NET I/O यूटिलिटीज़ तक पहुँच प्रदान करते हैं:

```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## चरण 1: दस्तावेज़ डायरेक्टरी सेट करें
उस फ़ोल्डर को परिभाषित करें जो किसी भी अस्थायी फ़ाइलों की मेज़बानी करेगा जिसकी आपको आवश्यकता हो सकती है।

```csharp
string dataDir = "Your Document Directory";
```

`"Your Document Directory"` को अपने मशीन पर वास्तविक पथ से बदलें।

## चरण 2: मेमोरी स्ट्रीम बनाएं
एक `MemoryStream` आपको GeoJSON को मेमोरी में रखने देता है, जो APIs के लिए या जब आप डेटा को सीधे क्लाइंट को लौटाना चाहते हैं, बिल्कुल उपयुक्त है।

```csharp
using (var memoryStream = new MemoryStream())
{
    // Subsequent steps will be placed inside this block
}
```

## चरण 3: GeoJSON ड्राइवर के साथ वेक्टर लेयर बनाएं
मेमोरी‑स्ट्रीम ब्लॉक के भीतर, एक `VectorLayer` बनाएं जो GeoJSON ड्राइवर का उपयोग करता है। यह Aspose.GIS को लेयर को GeoJSON के रूप में सीरियलाइज़ करने के लिए बताता है।

```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Feature creation goes here
}
```

## चरण 4: फीचर एट्रिब्यूट्स परिभाषित करें
ऐसे एट्रिब्यूट डिफ़िनिशन जोड़ें जो अंतिम GeoJSON आउटपुट में प्रॉपर्टीज़ के रूप में दिखाई देंगे।

```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## चरण 5: फीचर बनाएं और जोड़ें
दो नमूना पॉइंट बनाएं, एट्रिब्यूट वैल्यू असाइन करें, और उन्हें लेयर में जोड़ें।

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

## चरण 6: GeoJSON C# आउटपुट दिखाएं
लेयर भरने के बाद, स्ट्रीम के बाइट्स को UTF‑8 स्ट्रिंग में बदलें और कंसोल में लिखें। यह दर्शाता है कि **display GeoJSON C#** परिणाम कैसे दिखाए जाएँ।

```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

आपको टर्मिनल में एक वैध GeoJSON FeatureCollection प्रिंट होता दिखेगा।

## सामान्य समस्याएँ और समाधान
| समस्या | क्यों होता है | समाधान |
|--------|--------------|--------|
| खाली आउटपुट | पढ़ते समय स्ट्रीम की पोज़िशन अंत में होती है | स्ट्रिंग में बदलने से पहले `memoryStream.Position = 0;` कॉल करें। |
| अमान्य ज्योमेट्री | निर्देशांक वैध रेंज से बाहर हैं | जाँचें कि अक्षांश -90 से 90 के बीच और देशांतर -180 से 180 के बीच हो। |
| लाइसेंस अपवाद | उत्पादन में वैध लाइसेंस के बिना चलाना | `License license = new License(); license.SetLicense("Aspose.GIS.lic");` का उपयोग करके अस्थायी या पूर्ण लाइसेंस लागू करें। |

## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं Aspose.GIS for .NET को Windows और Linux दोनों वातावरण में उपयोग कर सकता हूँ?
हाँ, Aspose.GIS for .NET Windows और Linux दोनों सिस्टमों के साथ संगत है।  

### क्या कोई फ्री ट्रायल उपलब्ध है?
बिल्कुल! आप एक फ्री ट्रायल [यहाँ](https://releases.aspose.com/) से एक्सप्लोर कर सकते हैं।  

### विस्तृत दस्तावेज़ीकरण कहाँ मिल सकता है?
दस्तावेज़ीकरण देखें [यहाँ](https://reference.aspose.com/gis/net/)।  

### अस्थायी लाइसेंस कैसे प्राप्त करूँ?
अस्थायी लाइसेंस उपलब्ध हैं [यहाँ](https://purchase.aspose.com/temporary-license/)।  

### सहायता चाहिए या और प्रश्न हैं?
हमारे सपोर्ट फ़ोरम पर जाएँ [यहाँ](https://forum.aspose.com/c/gis/33)।

## FAQ
**प्रश्न: क्या मैं मेमोरी स्ट्रीम के बजाय सीधे फ़ाइल में GeoJSON लिख सकता हूँ?**  
**उत्तर:** हाँ—`MemoryStream` को `FileStream` से बदलें और फ़ाइल पाथ प्रदान करें। वही ड्राइवर काम करेगा।

**प्रश्न: उत्पन्न GeoJSON की इंडेंटेशन या फ़ॉर्मेटिंग कैसे नियंत्रित करूँ?**  
**उत्तर:** Aspose.GIS डिफ़ॉल्ट रूप से कॉम्पैक्ट JSON लिखता है। प्रीटी‑प्रिंटेड आउटपुट के लिए, स्ट्रिंग को `JsonSerializerOptions { WriteIndented = true }` के साथ पोस्ट‑प्रोसेस करें।

**प्रश्न: क्या लेयर में अधिक जटिल ज्योमेट्री (जैसे, पॉलीगॉन) जोड़ना संभव है?**  
**उत्तर:** बिल्कुल। एक `Polygon` या `LineString` ऑब्जेक्ट बनाएं, उसे `Feature.Geometry` को असाइन करें, और ऊपर दिखाए अनुसार फीचर जोड़ें।

**प्रश्न: क्या बड़े डेटा सेट `MemoryStream` में फिट हो पाएँगे?**  
**उत्तर:** बहुत बड़े कलेक्शन के लिए, सीधे फ़ाइल में स्ट्रीम करने या `BufferedStream` का उपयोग करने पर विचार करें ताकि मेमोरी उपयोग कम रहे।

**प्रश्न: क्या GeoJSON ड्राइवर CRS (Coordinate Reference System) परिभाषाओं को सपोर्ट करता है?**  
**उत्तर:** हाँ—यदि आपको गैर‑WGS84 CRS चाहिए तो फीचर जोड़ने से पहले लेयर की `SpatialReferenceSystem` प्रॉपर्टी सेट करें।

## निष्कर्ष
अब आपके पास Aspose.GIS का उपयोग करके किसी भी .NET स्ट्रीम में **how to write geojson** करने के लिए एक पूर्ण, प्रोडक्शन‑रेडी पैटर्न है। चाहे आप वेब API से GeoJSON लौटाना चाहते हों, फ़ाइल में सेव करना हो, या बस कंसोल में दिखाना हो, ऊपर दिए गए चरण पूरे वर्कफ़्लो को कवर करते हैं। लाइब्रेरी के साथ शैपफ़ाइल, KML, या GML जैसे अन्य फ़ॉर्मेट्स को भी एक्सप्लोर करें, और अधिक समृद्ध जियोस्पेशियल एप्लिकेशन बनाते रहें।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**अंतिम अपडेट:** 2026-01-02  
**परीक्षित संस्करण:** Aspose.GIS 24.11 for .NET  
**लेखक:** Aspose  

---