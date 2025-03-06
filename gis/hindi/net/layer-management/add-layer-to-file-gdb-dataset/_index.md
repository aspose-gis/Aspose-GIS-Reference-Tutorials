---
title: जीआईएस महारत - .NET के लिए Aspose.GIS के साथ GDB में परतें जोड़ें
linktitle: फ़ाइल GDB डेटासेट में परत जोड़ें
second_title: Aspose.GIS .NET एपीआई
description: .NET के लिए Aspose.GIS के साथ GIS की शक्ति को अनलॉक करें! इस चरण-दर-चरण ट्यूटोरियल में जानें कि फ़ाइल GDB डेटासेट में परतें कैसे जोड़ें। #भौगोलिक डेटा #असपोज़ #जीआईएस
weight: 16
url: /hi/net/layer-management/add-layer-to-file-gdb-dataset/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जीआईएस महारत - .NET के लिए Aspose.GIS के साथ GDB में परतें जोड़ें

## परिचय
क्या आप .NET के लिए Aspose.GIS का उपयोग करके अपनी GIS क्षमताओं को बढ़ाने के लिए तैयार हैं? इस चरण-दर-चरण मार्गदर्शिका में, हम आपको फ़ाइल जियोडेटाबेस (जीडीबी) डेटासेट में एक परत जोड़ने की प्रक्रिया के बारे में बताएंगे। .NET के लिए Aspose.GIS भौगोलिक जानकारी में हेरफेर करने के लिए शक्तिशाली सुविधाएँ प्रदान करता है, और इस ट्यूटोरियल के साथ, आप अपने डेटासेट में अतिरिक्त परतों को सहजता से एकीकृत करने में सक्षम होंगे।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
-  .NET लाइब्रेरी के लिए Aspose.GIS: लाइब्रेरी को डाउनलोड और इंस्टॉल करें[.NET दस्तावेज़ीकरण के लिए Aspose.GIS](https://reference.aspose.com/gis/net/).
- दस्तावेज़ निर्देशिका: जीआईएस-संबंधित फ़ाइलों को संग्रहीत और प्रबंधित करने के लिए अपनी मशीन पर एक समर्पित दस्तावेज़ निर्देशिका बनाएं।
## नामस्थान आयात करें
अपने .NET प्रोजेक्ट में, Aspose.GIS कार्यात्मकताओं तक पहुँचने के लिए आवश्यक नामस्थान आयात करना सुनिश्चित करें। निम्नलिखित कोड स्निपेट का उपयोग करें:
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
## चरण 1: निर्देशिका की प्रतिलिपि बनाएँ
आगे बढ़ने से पहले, अपने GDB डेटासेट वाली निर्देशिका की नकल करें। यह चरण सुनिश्चित करता है कि मूल डेटासेट बरकरार रहे। दिए गए कोड स्निपेट का उपयोग करें:
```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```
## चरण 2: डेटासेट खोलें और निर्माण क्षमता की जांच करें
 डुप्लिकेट किए गए डेटासेट को खोलें और जांचें कि क्या यह परतें बना सकता है। की उपस्थिति से इसकी पुष्टि होती है`True` कंसोल आउटपुट में.
```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // सत्य
```
## चरण 3: एक नई परत बनाएं और आबाद करें
डेटासेट के भीतर एक नई परत बनाएं, इसकी स्थानिक संदर्भ प्रणाली, विशेषताओं और एक नमूना सुविधा को परिभाषित करें। यह कोड स्निपेट प्रक्रिया को प्रदर्शित करता है:
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
## चरण 4: जोड़ी गई परत को खोलें और मान्य करें
आपके द्वारा अभी बनाई गई परत खोलें और उसकी सामग्री को सत्यापित करें। निम्नलिखित कोड का उपयोग करके गिनती की जाँच करें और विशेषता मान पुनः प्राप्त करें:
```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "नाम_1"
}
```
## निष्कर्ष
बधाई हो! आपने .NET के लिए Aspose.GIS का उपयोग करके फ़ाइल GDB डेटासेट में एक परत जोड़ने का तरीका सफलतापूर्वक सीख लिया है। इन नए कौशलों के साथ, आप अपनी जीआईएस परियोजनाओं में भौगोलिक डेटा में कुशलतापूर्वक हेरफेर कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्नों
### प्रश्न: क्या मैं अन्य जीआईएस पुस्तकालयों के साथ .NET के लिए Aspose.GIS का उपयोग कर सकता हूं?
.NET के लिए Aspose.GIS को स्वतंत्र रूप से काम करने के लिए डिज़ाइन किया गया है, लेकिन इसे उन्नत कार्यक्षमता के लिए अन्य पुस्तकालयों के साथ एकीकृत किया जा सकता है।
### प्रश्न: क्या परीक्षण उद्देश्यों के लिए अस्थायी लाइसेंस उपलब्ध है?
 हां, आप यहां से अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/) परीक्षण और मूल्यांकन के लिए.
### प्रश्न: .NET समर्थन के लिए Aspose.GIS कौन से स्थानिक संदर्भ सिस्टम का समर्थन करता है?
.NET के लिए Aspose.GIS स्थानिक संदर्भ प्रणालियों की एक विस्तृत श्रृंखला का समर्थन करता है, जो भौगोलिक डेटा प्रबंधन में लचीलापन प्रदान करता है।
### प्रश्न: क्या मैं Aspose.GIS समुदाय में योगदान कर सकता हूँ?
 बिल्कुल! चर्चा में शामिल हों और अपने अनुभव साझा करें[Aspose.GIS फोरम](https://forum.aspose.com/c/gis/33).
### प्रश्न: मुझे .NET के लिए Aspose.GIS के लिए विस्तृत दस्तावेज़ कहां मिल सकते हैं?
 व्यापक दस्तावेज़ीकरण का अन्वेषण करें[यहाँ](https://reference.aspose.com/gis/net/) .NET के लिए Aspose.GIS पर गहन जानकारी के लिए।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
