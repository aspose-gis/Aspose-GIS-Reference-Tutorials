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

# spatial reference wgs84 – Aspose.GIS का इस्तेमाल करके GDB में लेयर जोड़ें

## परिचय
क्या आप .NET के लिए Aspose.GIS के साथ अपने GIS वर्कफ़्लो को तेज़ करने के लिए तैयार हैं? इस ट्यूटोरियल में, आप सीखेंगे कि spatial reference wgs84 कोऑर्डिनेट सिस्टम के साथ काम करते हुए GDB डेटा सेट में फ़ाइल में लेयर कैसे जोड़ें। हम डेटा फ़ोल्डर तैयार करने से लेकर नई बनाई गई लेयर को वैलिडेट करने तक, हर स्टेप को विस्तार से समझाएंगे, ताकि आप भरोसे के साथ जियोग्राफ़िक डेटा में बदलाव कर सकें।

## तुरंत जवाब
- **प्राथमिक कॉर्डिट्स स्वास्थ्य कौन सी ऊंचाई की गई है?** spatial reference wgs84 (WGS84)
- **कौन सी बिलबोर्ड API इस्तेमाल करती है?** Aspose.GIS for .NET
- **திற்று के लिए मेज लिचिन की देखभाल है?** है – एक ट्युल्क Aspose लिचिसन है।
- **क्या में नाई लेयर में आट्रियुट फूट गुटो है?** बेशक, आप किसी भी नंबर में फीचर एट्रिब्यूट्स को डिफाइन कर सकते हैं।

- **.NET के कौन से एट्रिब्यूट्स गुद्धान हैं?** .NET Framework4.5+, .NET Core3.1+, .NET5/6.

## स्पेशल रेफरेंस wgs84 क्या है?
स्पेशल रेफरेंस wgs84 (वर्ल्ड जियोडेटिक सिस्टम 1984) सबसे बड़े रूप से उच्य किया जाने वाला गोफ्रोगिक कोऑर्डिनेट सिस्टम है। यह लैटीट्यूड और लॉन्गीट्यूड को डिग्री में डिफाइन करता है और कई GIS डेटासेट के लिए डिफ़ॉल्ट CRS के रूप में काम करता है, जिसमें वह डेटासेट भी शामिल है जिसे हम इस गाइड में बनाएंगे।

## लेयर जोड़ने के लिए Aspose.GIS का इस्तेमाल क्यों करें?

- **कोई बारजी अपनीताई नहीं:** शुद्ध .NET कोड के साथ विष्टिक काम करता है।

- **स्कीमा पर पूर्ण केंद्र:** अप कुस्थम एट्रिब्यूट और जूम डेस्कटॉप विष्ट करें।

- **Кросс‑платформ:** Windows, Linux, और macOS राजटाइम्स के साथ संगततः.

- **मजबूत लिक्सिनिंग:** तथा लिक्सन अपका है फील्ड फेल्य फैलिया करने है।

## ज़रूरी शर्तें
शुरू करने से पहले, पक्का करें कि आपके पास ये हैं:

Aspose.GIS for .NET Library
- डॉक्यूमेंट डायरेक्टरी: अपनी मशीन पर GIS फ़ाइलें स्टोर करने के लिए एक डेडिकेटेड फ़ोल्डर बनाएँ।

## नेमस्पेस इंपोर्ट करें
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

## स्टेप 1: डायरेक्टरी कॉपी करें
पहले, उस फ़ोल्डर की एक प्रतिलिपि बनाएं जिसमें मूल GDB डेटासेट मौजूद है। एक कॉपी रखना स्रोत डेटा को सुरक्षित रखता है जबकि आप प्रयोग कर रहे होते हैं।

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## स्टेप 2: डेटासेट खोलें और क्रिएशन कैपेबिलिटी वेरिफ़ाई करें
नई कॉपी किए गए डेटासेट को खोलें और पुष्टि करें कि यह नई लेयर्स बना सकता है। `CanCreateLayers` प्रॉपर्टी **True** लौटानी चाहिए।

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## स्टेप 3: स्पेशल रेफरेंस wgs84 के साथ एक नई लेयर बनाएं और पॉप्युलेट करें
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

## स्टेप 4: जोड़ी गई लेयर को खोलें और वेरिफाई करें
अंत में, वह लेयर खोलें जिसे आपने अभी बनाया है और उसकी सामग्री को सत्यापित करें। कंसोल दिखाएगा कि लेयर में एक फीचर है और **Name** एट्रिब्यूट वही है जो हमने सेट किया था।

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## आम दिक्कतें और टिप्स
- **गलत रास्ता:** पक्का करें कि `dataDir` रास्ता एक सेपरेटर (`/` या `\`) के साथ खत्म हो ताकि कम्पाइल किए गए स्ट्रिंग एक वैलिड फ़ाइल रास्ता बन जाएं।
- **लाइसेंस एरर:** अगर आपको लाइसेंसिंग वॉर्निंग दिखे, तो कोड चलाने से पहले Aspose पोर्टल से एक टेम्पररी लाइसेंस अप्लाई करें।
- **CRS इनकम्पैटिबिलिटी:** जब आप बाद में किसी दूसरे GIS टूल में लेयर खोलें, तो पक्का करें कि टूल WGS84 (EPSG:4326) को एक कोऑर्डिनेट सिस्टम के तौर पर पहचानता है।

## अक्सर पूछे जाने वाले सवाल
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

---

**अंतिम अपडेट:** 2026-01-13  
**परीक्षित संस्करण:** Aspose.GIS for .NET (latest stable version)  
**लेखक:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
