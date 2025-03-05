---
title: सिंगल लेयर के साथ फाइल GDB बनाएं
linktitle: सिंगल लेयर के साथ फाइल GDB बनाएं
second_title: Aspose.GIS .NET एपीआई
description: Aspose.GIS के साथ .NET में भू-स्थानिक डेटा प्रबंधन की क्षमता को अनलॉक करें। चरण-दर-चरण फ़ाइल जियोडेटाबेस और परतें बनाना सीखें। अब डाउनलोड करो!
type: docs
weight: 11
url: /hi/net/layer-management/create-file-gdb-with-single-layer/
---
## परिचय
क्या आप मजबूत फ़ाइल जियोडेटाबेस और परतों के साथ अपने भू-स्थानिक अनुप्रयोगों को उन्नत करने के लिए तैयार हैं? .NET के लिए Aspose.GIS से आगे न देखें। इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.GIS का उपयोग करके एकल परत के साथ फ़ाइल जियोडेटाबेस (GDB) बनाने की प्रक्रिया के बारे में बताएंगे। अपने .NET अनुप्रयोगों में स्थानिक डेटा प्रबंधन और विज़ुअलाइज़ेशन की शक्ति का सहजता से उपयोग करें।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
1.  .NET के लिए Aspose.GIS: सुनिश्चित करें कि आपके पास Aspose.GIS लाइब्रेरी स्थापित है। आप इसे यहां से डाउनलोड कर सकते हैं[.NET डाउनलोड पेज के लिए Aspose.GIS](https://releases.aspose.com/gis/net/).
2. विकास परिवेश: अपनी मशीन पर एक कार्यशील .NET विकास परिवेश स्थापित करें।
3. दस्तावेज़ निर्देशिका: अपने सिस्टम पर एक निर्देशिका चुनें या बनाएं जहां आप अपनी भू-स्थानिक डेटा फ़ाइलें संग्रहीत करेंगे।
## नामस्थान आयात करें
आरंभ करने के लिए, आपको अपने .NET प्रोजेक्ट में आवश्यक नेमस्पेस आयात करना होगा। ये नामस्थान Aspose.GIS कार्यात्मकताओं तक पहुंच प्रदान करेंगे। अपनी कोड फ़ाइल की शुरुआत में निम्नलिखित पंक्तियाँ जोड़ें:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```
## चरण 1: अपनी दस्तावेज़ निर्देशिका सेट करें
```csharp
string dataDir = "Your Document Directory";
```
"आपकी दस्तावेज़ निर्देशिका" को उस निर्देशिका के पथ से बदलें जहां आप अपनी भू-स्थानिक डेटा फ़ाइलों को संग्रहीत करना चाहते हैं।
## चरण 2: एक परत के साथ एक फ़ाइल जियोडेटाबेस बनाएं
```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
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
यह कोड स्निपेट एक परत के साथ एक फ़ाइल जियोडेटाबेस बनाता है और इसमें एक लाइन सुविधा जोड़ता है।
## चरण 3: फ़ाइल जियोडेटाबेस खोलें और परत जानकारी पुनः प्राप्त करें
```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // आउटपुट: सुविधाओं की संख्या: 1
}
```
इस चरण में, हम बनाई गई फ़ाइल जियोडेटाबेस को खोलते हैं, "लेयर" नामक परत को पुनः प्राप्त करते हैं और परत में सुविधाओं की गिनती प्रिंट करते हैं।
## निष्कर्ष
बधाई हो! आपने .NET के लिए Aspose.GIS का उपयोग करके एकल परत वाला फ़ाइल जियोडेटाबेस सफलतापूर्वक बना लिया है। अपने अनुप्रयोगों में स्थानिक डेटा प्रबंधन की विशाल क्षमताओं का आसानी से अन्वेषण करें।
## अक्सर पूछे जाने वाले प्रश्नों
### क्या मैं अपने मौजूदा .NET प्रोजेक्ट्स में .NET के लिए Aspose.GIS का उपयोग कर सकता हूँ?
हां, .NET के लिए Aspose.GIS को आपके मौजूदा .NET प्रोजेक्ट्स में सहजता से एकीकृत किया जा सकता है।
### क्या .NET के लिए Aspose.GIS का कोई परीक्षण संस्करण उपलब्ध है?
 हां, आप डाउनलोड करके .NET के लिए Aspose.GIS की विशेषताओं का पता लगा सकते हैं[निःशुल्क परीक्षण संस्करण](https://releases.aspose.com/).
### मुझे .NET के लिए Aspose.GIS के लिए विस्तृत दस्तावेज़ कहाँ मिल सकते हैं?
 को देखें[प्रलेखन](https://reference.aspose.com/gis/net/) .NET के लिए Aspose.GIS पर व्यापक जानकारी के लिए।
### मैं .NET के लिए Aspose.GIS के लिए समर्थन कैसे प्राप्त कर सकता हूँ?
 दौरा करना[Aspose.GIS फोरम](https://forum.aspose.com/c/gis/33) सामुदायिक समर्थन और सहायता के लिए।
### क्या .NET के लिए Aspose.GIS के लिए अस्थायी लाइसेंस उपलब्ध हैं?
 हाँ, आप प्राप्त कर सकते हैं[अस्थायी लाइसेंस](https://purchase.aspose.com/temporary-license/) .NET के लिए Aspose.GIS के लिए।