---
date: 2026-06-30
description: Aspose.GIS का उपयोग करके WGS84 स्पैशियल रेफ़रेंस के साथ File GDB डेटासेट
  में लेयर जोड़ना सीखें। .NET में लेयर जोड़ने के लिए इस चरण‑दर‑चरण गाइड का पालन करें।
keywords:
- how to add layer
- spatial reference wgs84
- Aspose.GIS .NET
- File GDB dataset
linktitle: File GDB डेटासेट में लेयर जोड़ें
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to add layer to a File GDB dataset using Aspose.GIS with
    spatial reference WGS84. Follow this step‑by‑step guide to add a layer in .NET.
  headline: How to Add Layer to File GDB Dataset with spatial reference WGS84 using
    Aspose.GIS
  type: TechArticle
- questions:
  - answer: spatial reference wgs84 (WGS 84)
    question: What is the primary coordinate system used?
  - answer: Aspose.GIS for .NET
    question: Which library provides the API?
  - answer: Yes – a temporary Aspose license is available.
    question: Do I need a license for testing?
  - answer: Absolutely, you can define any number of feature attributes.
    question: Can I add attributes to the new layer?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Aspose.GIS का उपयोग करके WGS84 स्पैशियल रेफ़रेंस के साथ File GDB डेटासेट में
  लेयर कैसे जोड़ें
url: /hi/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# लेयर कैसे जोड़ें – स्पैशियल रेफ़रेंस wgs84 के साथ Aspose.GIS

## परिचय
क्या आप Aspose.GIS for .NET के साथ अपने GIS कार्यप्रवाह को बढ़ाने के लिए तैयार हैं? इस ट्यूटोरियल में आप **लेयर कैसे जोड़ें** सीखेंगे एक File GDB डेटासेट में जबकि **स्पैशियल रेफ़रेंस WGS84** कोऑर्डिनेट सिस्टम के साथ काम करेंगे। हम प्रत्येक चरण को समझेंगे, आपके डेटा फ़ोल्डर को तैयार करने से लेकर नई बनाई गई लेयर को वैध करने तक, ताकि आप आत्मविश्वास और दक्षता के साथ भौगोलिक डेटा को हेरफेर करना शुरू कर सकें।

## त्वरित उत्तर
- **प्राथमिक कोऑर्डिनेट सिस्टम कौन सा उपयोग किया जाता है?** spatial reference wgs84 (WGS 84)  
- **कौन सी लाइब्रेरी API प्रदान करती है?** Aspose.GIS for .NET  
- **परीक्षण के लिए मुझे लाइसेंस चाहिए?** हाँ – एक अस्थायी Aspose लाइसेंस उपलब्ध है।  
- **क्या मैं नई लेयर में एट्रिब्यूट जोड़ सकता हूँ?** बिल्कुल, आप फीचर एट्रिब्यूट्स की कोई भी संख्या परिभाषित कर सकते हैं।  
- **कौन से .NET संस्करण समर्थित हैं?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## स्पैशियल रेफ़रेंस wgs84 क्या है?
स्पैशियल रेफ़रेंस wgs84 (World Geodetic System 1984) सबसे अधिक उपयोग किया जाने वाला भौगोलिक कोऑर्डिनेट सिस्टम है। यह अक्षांश और देशांतर को डिग्री में परिभाषित करता है और कई GIS डेटासेट्स के लिए डिफ़ॉल्ट CRS के रूप में कार्य करता है, जिसमें वह भी शामिल है जिसे हम इस गाइड में बनाएंगे।

## लेयर जोड़ने के लिए Aspose.GIS क्यों उपयोग करें?
तीसरे‑पक्ष बाइनरीज़ के बिना अपने GIS डेटा को लोड करें और स्कीमा परिभाषा पर पूर्ण नियंत्रण रखें। Aspose.GIS **40+ स्पैशियल रेफ़रेंस सिस्टम** का समर्थन करता है, **2 GB** से बड़े फ़ाइलों को पूरी डेटासेट को मेमोरी में लोड किए बिना प्रोसेस कर सकता है, और Windows, Linux, तथा macOS पर चलता है। यह इसे एंटरप्राइज़‑ग्रेड GIS ऑटोमेशन के लिए एक विश्वसनीय, क्रॉस‑प्लेटफ़ॉर्म समाधान बनाता है।

## आवश्यकताएँ
- Aspose.GIS for .NET लाइब्रेरी: लाइब्रेरी को [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/) से डाउनलोड और इंस्टॉल करें।  
- डॉक्यूमेंट डायरेक्टरी: अपने मशीन पर GIS फ़ाइलें संग्रहीत करने के लिए एक समर्पित फ़ोल्डर बनाएं।  
- एक अस्थायी Aspose लाइसेंस (मूल्यांकन के लिए वैकल्पिक) – डाउनलोड लिंक के लिए नीचे FAQ देखें।

## नेमस्पेस इम्पोर्ट करें
अपने C# प्रोजेक्ट में आवश्यक `using` स्टेटमेंट्स जोड़ें ताकि आप Aspose.GIS क्लासेज़ तक पहुंच सकें:

*कोई कोड ब्लॉक आवश्यक नहीं है; बस निम्नलिखित लाइनों को अपनी फ़ाइल के शीर्ष पर जोड़ें:*

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.Geometries.Collections;
using Aspose.Gis.SpatialReference;
```

## चरण 1: डायरेक्टरी कॉपी करें
**Definition anchor:** एक File GDB डेटासेट एक फ़ोल्डर‑आधारित ESRI जियोडेटाबेस है जो स्पैशियल डेटा को फ़ाइलों के सेट में संग्रहीत करता है।  
पहले, मूल GDB डेटासेट वाले फ़ोल्डर की प्रतिलिपि बनाएं। एक कॉपी रखना स्रोत डेटा की सुरक्षा करता है जबकि आप प्रयोग करते हैं।

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## चरण 2: डेटासेट खोलें और निर्माण क्षमता सत्यापित करें
`Dataset` एक File GDB में संग्रहीत GIS लेयर्स के संग्रह का प्रतिनिधित्व करता है। नई कॉपी किए गए डेटासेट को खोलें और पुष्टि करें कि यह नई लेयर्स बना सकता है। `CanCreateLayers` प्रॉपर्टी **True** लौटानी चाहिए। **`CanCreateLayers` एक बूलियन प्रॉपर्टी है जो दर्शाती है कि डेटासेट नई लेयर्स बनाने का समर्थन करता है।**

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## चरण 3: स्पैशियल रेफ़रेंस wgs84 के साथ नई लेयर बनाएं और भरें
अब हम **data** नाम की एक लेयर बनाते हैं और स्पष्ट रूप से उसकी स्पैशियल रेफ़रेंस को **Wgs84** सेट करते हैं। हम एक सरल एट्रिब्यूट **Name** भी जोड़ते हैं और एक पॉइंट फीचर सम्मिलित करते हैं। **`CreateLayer` डेटासेट में निर्दिष्ट नाम और स्पैशियल रेफ़रेंस के साथ नई लेयर बनाता है।** **`SpatialReference` वह कोऑर्डिनेट सिस्टम दर्शाता है जो लेयर द्वारा उपयोग किया जाता है।** **`Feature` एक व्यक्तिगत भौगोलिक वस्तु (पॉइंट, लाइन, या पॉलीगॉन) है जो लेयर में संग्रहीत होती है।**

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## चरण 4: जोड़ी गई लेयर खोलें और सत्यापित करें
अंत में, आप द्वारा अभी बनाई गई लेयर खोलें और उसकी सामग्री सत्यापित करें। कंसोल दिखाएगा कि लेयर में एक फीचर है और **Name** एट्रिब्यूट वही है जो हमने सेट किया था। **`Layer.Open` मौजूदा लेयर को पढ़ने या संपादित करने के लिए खोलता है।** यह पुष्टि करता है कि लेयर सही ढंग से जोड़ी गई है और स्पैशियल रेफ़रेंस WGS84 है।

```csharp
using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
{
    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
    var feature = layer.ConstructFeature();
    feature.SetValue("Name", "Name_1");
    feature.Geometry = new Point(12.21, 23.123, 20, -200);
    layer.Add(feature);
}
```

## File GDB डेटासेट में लेयर कैसे जोड़ें?
डेटासेट लोड करें, इच्छित नाम और स्पैशियल रेफ़रेंस के साथ `CreateLayer` को कॉल करें, एट्रिब्यूट स्कीमा परिभाषित करें, और फिर फीचर्स सम्मिलित करें। यह सब कुछ कुछ Aspose.GIS मेथड कॉल्स से किया जा सकता है, और API फ़ाइल लॉकिंग और स्कीमा वैधता को स्वचालित रूप से संभालता है। यह प्रक्रिया सुनिश्चित करती है कि नई लेयर डेटासेट के स्पैशियल रेफ़रेंस के अनुरूप हो, एट्रिब्यूट परिभाषाएँ लेयर के स्कीमा में संग्रहीत हों, और डेटा किसी भी GIS सॉफ़्टवेयर द्वारा एक्सेस किया जा सके जो File GDB का समर्थन करता है।

## सामान्य समस्याएँ और टिप्स
- **Incorrect path:** सुनिश्चित करें कि `dataDir` पाथ सेपरेटर (`/` या `\`) के साथ समाप्त हो ताकि संयोजित स्ट्रिंग्स वैध फ़ाइल पाथ बनाएं।  
- **License errors:** यदि आपको लाइसेंसिंग चेतावनियाँ दिखती हैं, तो कोड चलाने से पहले Aspose पोर्टल से एक अस्थायी लाइसेंस लागू करें।  
- **CRS mismatch:** जब आप लेयर को किसी अन्य GIS टूल में बाद में खोलते हैं, तो पुष्टि करें कि टूल WGS 84 (EPSG:4326) को कोऑर्डिनेट सिस्टम के रूप में पहचानता है।  
- **Large datasets:** 1 GB से बड़े डेटासेट्स के लिए, मेमोरी उपयोग कम करने हेतु `Dataset.OpenReadOnly` उपयोग करने पर विचार करें।

## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं Aspose.GIS for .NET को अन्य GIS लाइब्रेरीज़ के साथ उपयोग कर सकता हूँ?
उत्तर: हाँ, Aspose.GIS स्वतंत्र रूप से काम करता है लेकिन उन्नत प्रोसेसिंग के लिए GDAL या NetTopologySuite जैसी लाइब्रेरीज़ के साथ जोड़ा जा सकता है।

### प्रश्न: क्या परीक्षण उद्देश्यों के लिए एक अस्थायी लाइसेंस उपलब्ध है?
उत्तर: हाँ, आप परीक्षण और मूल्यांकन के लिए [यहाँ](https://purchase.aspose.com/temporary-license/) से एक अस्थायी लाइसेंस प्राप्त कर सकते हैं।

### प्रश्न: Aspose.GIS for .NET कौन से स्पैशियल रेफ़रेंस सिस्टम का समर्थन करता है?
उत्तर: Aspose.GIS **40 EPSG कोड** से अधिक का समर्थन करता है, जिसमें लोकप्रिय सिस्टम जैसे WGS84 (EPSG:4326), Web Mercator (EPSG:3857), और NAD83 (EPSG:4269) शामिल हैं। व्यापक दस्तावेज़ीकरण [यहाँ](https://reference.aspose.com/gis/net/) देखें।

### प्रश्न: क्या मैं Aspose.GIS समुदाय में योगदान दे सकता हूँ?
उत्तर: बिल्कुल! चर्चाओं में भाग लें और अपने अनुभव [Aspose.GIS फ़ोरम](https://forum.aspose.com/c/gis/33) पर साझा करें।

### प्रश्न: Aspose.GIS for .NET की विस्तृत दस्तावेज़ीकरण कहाँ मिल सकती है?
उत्तर: सभी क्लासेज़, मेथड्स, और सर्वोत्तम प्रथाओं पर विस्तृत जानकारी के लिए व्यापक दस्तावेज़ीकरण [यहाँ](https://reference.aspose.com/gis/net/) देखें।

---

**अंतिम अपडेट:** 2026-06-30  
**परीक्षित संस्करण:** Aspose.GIS for .NET (latest stable version)  
**लेखक:** Aspose

{{< blocks/products/products-backtop-button >}}

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## संबंधित ट्यूटोरियल

- [Aspose.GIS के साथ फ़ाइल जियोडेटाबेस .NET डेटासेट बनाएं](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [फ़ाइल GDB में वेक्टर लेयर बनाएं – Aspose.GIS .NET ट्यूटोरियल](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [फ़ाइल GDB डेटासेट बनाएं और लेयर के लिए टॉलरेंस सेट करें](/gis/net/layer-data-operations/set-tolerances-for-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}