---
title: नई फ़ाइल GDB डेटासेट बनाएं
linktitle: नई फ़ाइल GDB डेटासेट बनाएं
second_title: Aspose.GIS .NET एपीआई
description: आसानी से जीआईएस डेटासेट बनाने और प्रबंधित करने के लिए .NET के लिए Aspose.GIS का अन्वेषण करें। निर्बाध भू-स्थानिक विकास के लिए अभी डाउनलोड करें। #मान लीजिए #जीआईएस
weight: 10
url: /hi/net/layer-management/create-new-file-gdb-dataset/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# नई फ़ाइल GDB डेटासेट बनाएं

## परिचय
भू-स्थानिक विकास के क्षेत्र में, .NET के लिए Aspose.GIS भौगोलिक सूचना प्रणाली (GIS) डेटा के प्रबंधन और हेरफेर के लिए एक शक्तिशाली टूलकिट के रूप में सामने आता है। चाहे आप एक अनुभवी डेवलपर हों या जीआईएस में अपनी यात्रा शुरू कर रहे हों, यह ट्यूटोरियल आपको .NET के लिए Aspose.GIS का उपयोग करके एक नई फ़ाइल जियोडेटाबेस (GDB) डेटासेट बनाने की प्रक्रिया से परिचित कराएगा।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
-  .NET के लिए Aspose.GIS: सुनिश्चित करें कि आपके पास .NET लाइब्रेरी के लिए Aspose.GIS स्थापित है। आप इसे यहां से डाउनलोड कर सकते हैं[.NET डाउनलोड पेज के लिए Aspose.GIS](https://releases.aspose.com/gis/net/).
- विकास परिवेश: अपने विकास परिवेश को विज़ुअल स्टूडियो जैसे संगत आईडीई के साथ सेट करें, और .NET प्रोग्रामिंग की बुनियादी समझ रखें।
- दस्तावेज़ निर्देशिका: कोड स्निपेट में "आपकी दस्तावेज़ निर्देशिका" को उचित पथ से बदलें जहाँ आप अपना GDB डेटासेट संग्रहीत करना चाहते हैं।
- C# से परिचित: यह ट्यूटोरियल मानता है कि आप C# प्रोग्रामिंग भाषा से परिचित हैं।
## नामस्थान आयात करें
प्रारंभिक चरणों में, अपने .NET एप्लिकेशन में Aspose.GIS कार्यक्षमता का लाभ उठाने के लिए आवश्यक नामस्थान आयात करें:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## चरण 1: एक नई फ़ाइल GDB डेटासेट बनाएं
```csharp
string dataDir = "Your Document Directory";
using (var dataset = Dataset.Create(dataDir, Drivers.FileGdb))
{
    Console.WriteLine(dataset.LayersCount); // आउटपुट: 0
    // अगले चरणों के साथ जारी रखें...
}
```
 स्पष्टीकरण: इस चरण में, हम इसका उपयोग करके एक नया GDB डेटासेट बनाते हैं`Dataset.Create` तरीका। हम फ़ाइल जियोडेटाबेस बनाने के लिए पथ और ड्राइवर (फ़ाइलजीडीबी) निर्दिष्ट करते हैं। कंसोल आउटपुट प्रारंभिक परत गणना प्रदर्शित करता है, जो इस बिंदु पर शून्य है।
## चरण 2: लेयर_1 बनाएं और भरें
```csharp
using (var layer = dataset.CreateLayer("layer_1"))
{
    layer.Attributes.Add(new FeatureAttribute("value", AttributeDataType.Integer));
    for (int i = 0; i < 10; ++i)
    {
        var feature = layer.ConstructFeature();
        feature.SetValue("value", i);
        feature.Geometry = new Point(i, i);
        layer.Add(feature);
    }
}
```
स्पष्टीकरण: इस चरण में डेटासेट के भीतर "लेयर_1" नामक एक परत बनाना शामिल है। यह पूर्णांक प्रकार के "मान" नामक एक विशेषता को परिभाषित करता है और परत को दस विशेषताओं से भर देता है, जिनमें से प्रत्येक में एक बिंदु ज्यामिति होती है।
## चरण 3: लेयर_2 बनाएं और पॉप्युलेट करें
```csharp
using (var layer = dataset.CreateLayer("layer_2"))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```
स्पष्टीकरण: यहां, हम "लेयर_2" नामक एक दूसरी परत बनाते हैं और लाइन स्ट्रिंग ज्यामिति के साथ एक एकल सुविधा जोड़ते हैं।
## चरण 4: अद्यतन परतों की संख्या की जाँच करें
```csharp
Console.WriteLine(dataset.LayersCount); // आउटपुट: 2
```
स्पष्टीकरण: अंत में, हम दो परतों को जोड़ने के बाद अद्यतन परतों की संख्या की जांच करते हैं। इस स्थिति में, आउटपुट 2 होना चाहिए।
## निष्कर्ष
बधाई हो! आपने सफलतापूर्वक एक नया फ़ाइल GDB डेटासेट बनाया है और .NET के लिए Aspose.GIS का उपयोग करके इसे परतों से भर दिया है। यह ट्यूटोरियल .NET वातावरण में भू-स्थानिक डेटा के साथ काम करने की मूलभूत समझ प्रदान करता है।
## अक्सर पूछे जाने वाले प्रश्नों
### प्रश्न: क्या मैं अन्य जीआईएस पुस्तकालयों के साथ .NET के लिए Aspose.GIS का उपयोग कर सकता हूं?
.NET के लिए Aspose.GIS एक स्टैंडअलोन टूलकिट है; हालाँकि, कार्यक्षमता बढ़ाने के लिए आप इसे अन्य .NET लाइब्रेरी के साथ एकीकृत कर सकते हैं।
### प्रश्न: क्या Aspose.GIS समर्थन के लिए कोई सामुदायिक मंच है?
 हाँ, आप इस पर समर्थन और चर्चाएँ पा सकते हैं[Aspose.GIS फोरम](https://forum.aspose.com/c/gis/33).
### प्रश्न: मैं Aspose.GIS के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 दौरा करना[अस्थायी लाइसेंस](https://purchase.aspose.com/temporary-license/) अस्थायी लाइसेंस प्राप्त करने की जानकारी के लिए पृष्ठ।
### प्रश्न: क्या अतिरिक्त उदाहरण और दस्तावेज़ उपलब्ध हैं?
 पता लगाएं[Aspose.GIS दस्तावेज़ीकरण](https://reference.aspose.com/gis/net/) अधिक उदाहरणों और विस्तृत जानकारी के लिए।
### प्रश्न: मैं .NET के लिए Aspose.GIS कहां से खरीद सकता हूं?
 आप .NET के लिए Aspose.GIS खरीद सकते हैं[खरीद पृष्ठ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
