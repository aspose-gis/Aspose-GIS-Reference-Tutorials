---
date: 2026-01-13
description: Aspose.GIS का उपयोग करके फ़ाइल GDB डेटासेट में लेयर जोड़ना, साथ ही spatial
  reference WGS84 समर्थन के साथ, सीखें। .NET में GDB में लेयर जोड़ने के लिए इस चरण‑दर‑चरण
  गाइड का पालन करें।
linktitle: Add Layer to File GDB Dataset
second_title: Aspose.GIS .NET API
title: स्पैशियल रेफ़रेंस WGS84 – Aspose.GIS का उपयोग करके GDB में लेयर जोड़ें
url: /hi/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# spatial reference wgs84 – Aspose.GIS का उपयोग करके GDB में लेयर जोड़ें

## Introduction
क्या आप Aspose.GIS for .NET के साथ अपने GIS वर्कफ़्लो को तेज़ करने के लिए तैयार हैं? इस ट्यूटोरियल में आप **फ़ाइल GDB डेटासेट में लेयर कैसे जोड़ें** सीखेंगे जबकि **spatial reference wgs84** कॉर्डिनेट सिस्टम के साथ काम करेंगे। हम प्रत्येक चरण को विस्तार से बताएँगे, डेटा फ़ोल्डर तैयार करने से लेकर नई बनाई गई लेयर को वैध करने तक, ताकि आप आत्मविश्वास के साथ भौगोलिक डेटा को हेर-फेर कर सकें।

## Quick Answers
- **प्राथमिक निर्देशांक प्रणाली कौन सी उपयोग की गई है?** spatial reference wgs84 (WGS 84)  
- **कौन सी लाइब्रेरी API प्रदान करती है?** Aspose.GIS for .NET  
- **परीक्षण के लिए मुझे लाइसेंस की आवश्यकता है?** हाँ – एक अस्थायी Aspose लाइसेंस उपलब्ध है।  
- **क्या मैं नई लेयर में एट्रिब्यूट जोड़ सकता हूँ?** बिल्कुल, आप किसी भी संख्या में फीचर एट्रिब्यूट परिभाषित कर सकते हैं।  
- **.NET के कौन से संस्करण समर्थित हैं?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## What is spatial reference wgs84?
spatial reference wgs84 (World Geodetic System 1984) सबसे व्यापक रूप से उपयोग किया जाने वाला भौगोलिक कॉर्डिनेट सिस्टम है। यह अक्षांश और देशांतर को डिग्री में परिभाषित करता है और कई GIS डेटासेट्स के लिए डिफ़ॉल्ट CRS के रूप में कार्य करता है, जिसमें वह डेटासेट भी शामिल है जिसे हम इस गाइड में बनाएँगे।

## Why use Aspose.GIS to add a layer?
- **कोई बाहरी निर्भरताएँ नहीं:** शुद्ध .NET कोड के साथ तुरंत काम करता है।  
- **स्कीमा पर पूर्ण नियंत्रण:** आप कस्टम एट्रिब्यूट और ज्योमेट्री प्रकार परिभाषित कर सकते हैं।  
- **क्रॉस‑प्लेटफ़ॉर्म:** Windows, Linux, और macOS रनटाइम्स के साथ संगत।  
- **मजबूत लाइसेंसिंग:** अस्थायी लाइसेंस आपको प्रतिबद्ध होने से पहले जल्दी मूल्यांकन करने देते हैं।

## Prerequisites
शुरू करने से पहले सुनिश्चित करें कि आपके पास हैं:

- Aspose.GIS for .NET लाइब्रेरी: लाइब्रेरी को [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/) से डाउनलोड और इंस्टॉल करें।  
- डॉक्यूमेंट डायरेक्टरी: अपने मशीन पर GIS फ़ाइलें संग्रहीत करने के लिए एक समर्पित फ़ोल्डर बनाएं।

## Import Namespaces
अपने C# प्रोजेक्ट में आवश्यक `using` स्टेटमेंट जोड़ें ताकि आप Aspose.GIS क्लासेज़ तक पहुंच सकें:

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

## Step 1: Copy Directory
पहले, उस फ़ोल्डर की एक प्रतिलिपि बनाएं जिसमें मूल GDB डेटासेट मौजूद है। एक कॉपी रखना स्रोत डेटा को सुरक्षित रखता है जबकि आप प्रयोग कर रहे होते हैं।

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Step 2: Open Dataset and Verify Creation Capability
नई कॉपी किए गए डेटासेट को खोलें और पुष्टि करें कि यह नई लेयर्स बना सकता है। `CanCreateLayers` प्रॉपर्टी **True** लौटानी चाहिए।

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Step 3: Create and Populate a New Layer with spatial reference wgs84
अब हम **data** नाम की एक लेयर बनाते हैं और स्पष्ट रूप से उसका spatial reference **Wgs84** सेट करते हैं। हम एक सरल एट्रिब्यूट **Name** भी जोड़ते हैं और एक पॉइंट फीचर डालते हैं।

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

## Step 4: Open and Validate the Added Layer
अंत में, वह लेयर खोलें जिसे आपने अभी बनाया है और उसकी सामग्री को सत्यापित करें। कंसोल दिखाएगा कि लेयर में एक फीचर है और **Name** एट्रिब्यूट वही है जो हमने सेट किया था।

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Common Issues & Tips
- **गलत पथ:** सुनिश्चित करें कि `dataDir` पथ विभाजक (`/` या `\`) के साथ समाप्त हो ताकि संयोजित स्ट्रिंग्स वैध फ़ाइल पथ बनें।  
- **लाइसेंस त्रुटियाँ:** यदि आपको लाइसेंसिंग चेतावनियाँ दिखती हैं, तो कोड चलाने से पहले Aspose पोर्टल से एक अस्थायी लाइसेंस लागू करें।  
- **CRS असंगतता:** जब आप बाद में लेयर को किसी अन्य GIS टूल में खोलें, तो सुनिश्चित करें कि टूल WGS 84 (EPSG:4326) को निर्देशांक प्रणाली के रूप में पहचानता है।

## Frequently Asked Questions
### Q: क्या मैं Aspose.GIS for .NET को अन्य GIS लाइब्रेरीज़ के साथ उपयोग कर सकता हूँ?
Aspose.GIS for .NET स्वतंत्र रूप से काम करने के लिए डिज़ाइन किया गया है, लेकिन इसे उन्नत कार्यक्षमता के लिए अन्य लाइब्रेरीज़ के साथ एकीकृत किया जा सकता है।

### Q: क्या परीक्षण उद्देश्यों के लिए एक अस्थायी लाइसेंस उपलब्ध है?
हाँ, आप परीक्षण और मूल्यांकन के लिए [यहाँ](https://purchase.aspose.com/temporary-license/) से एक अस्थायी लाइसेंस प्राप्त कर सकते हैं।

### Q: Aspose.GIS for .NET किन स्पैशियल रेफ़रेंस सिस्टम्स को सपोर्ट करता है?
Aspose.GIS for .NET विभिन्न स्पैशियल रेफ़रेंस सिस्टम्स का व्यापक समर्थन करता है, जिससे भौगोलिक डेटा हैंडलिंग में लचीलापन मिलता है।

### Q: क्या मैं Aspose.GIS समुदाय में योगदान दे सकता हूँ?
बिल्कुल! आप [Aspose.GIS फोरम](https://forum.aspose.com/c/gis/33) पर चर्चा में भाग लेकर अपने अनुभव साझा कर सकते हैं।

### Q: मैं Aspose.GIS for .NET की विस्तृत दस्तावेज़ीकरण कहाँ पा सकता हूँ?
विस्तृत दस्तावेज़ीकरण के लिए [यहाँ](https://reference.aspose.com/gis/net/) देखें, जहाँ Aspose.GIS for .NET पर गहन जानकारी उपलब्ध है।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**अंतिम अपडेट:** 2026-01-13  
**परीक्षित संस्करण:** Aspose.GIS for .NET (latest stable version)  
**लेखक:** Aspose