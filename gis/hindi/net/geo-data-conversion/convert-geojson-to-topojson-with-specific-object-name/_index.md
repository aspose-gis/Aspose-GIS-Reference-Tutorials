---
title: विशिष्ट ऑब्जेक्ट नाम के साथ जियोजसन को टोपोजसन में बदलें
linktitle: विशिष्ट ऑब्जेक्ट नाम के साथ जियोजसन को टोपोजसन में बदलें
second_title: Aspose.GIS .NET एपीआई
description: .NET के लिए Aspose.GIS का उपयोग करके एक विशिष्ट ऑब्जेक्ट नाम के साथ जियोजसन को टोपोजसन में परिवर्तित करने का तरीका जानें। यह ट्यूटोरियल कुशल भौगोलिक डेटा हेरफेर के लिए चरण-दर-चरण मार्गदर्शिका प्रदान करता है।
weight: 12
url: /hi/net/geo-data-conversion/convert-geojson-to-topojson-with-specific-object-name/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# विशिष्ट ऑब्जेक्ट नाम के साथ जियोजसन को टोपोजसन में बदलें

## परिचय
.NET के लिए Aspose.GIS, .NET अनुप्रयोगों में भौगोलिक डेटा के साथ काम करने के लिए एक शक्तिशाली उपकरण है। चाहे आप मैपिंग एप्लिकेशन विकसित कर रहे हों, स्थानिक डेटा का विश्लेषण कर रहे हों, या जियोजोन फ़ाइलों में हेरफेर कर रहे हों, Aspose.GIS आपके वर्कफ़्लो को सुव्यवस्थित करने के लिए सुविधाओं का एक व्यापक सेट प्रदान करता है।
## आवश्यक शर्तें
इससे पहले कि हम .NET के लिए Aspose.GIS का उपयोग करके एक विशिष्ट ऑब्जेक्ट नाम के साथ जियोजसन को टोपोजसन में परिवर्तित करें, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
### 1. .NET के लिए Aspose.GIS स्थापित करें
 की ओर जाएं[डाउनलोड पेज](https://releases.aspose.com/gis/net/) और .NET के लिए Aspose.GIS का नवीनतम संस्करण प्राप्त करें।
### 2. अपना विकास परिवेश स्थापित करें
सुनिश्चित करें कि आपके सिस्टम पर विज़ुअल स्टूडियो या कोई अन्य .NET विकास वातावरण स्थापित है।
### 3. अपनी जियोसन फ़ाइल तैयार करें
आपके पास एक जियोजसन फ़ाइल है जिसे आप TopoJSON में कनवर्ट करना चाहते हैं। यदि आपके पास एक नहीं है, तो आप इस ट्यूटोरियल के लिए किसी भी नमूना जियोसन फ़ाइल का उपयोग कर सकते हैं।

## नामस्थान आयात करें
रूपांतरण प्रक्रिया शुरू करने से पहले, आइए आवश्यक नामस्थान आयात करें:
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## चरण 1: फ़ाइल पथ परिभाषित करें
```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithObjectName_out.topojson";
```
 प्रतिस्थापित करें`"Your Document Directory"`वास्तविक निर्देशिका पथ के साथ जहां आपकी जियोजसन फ़ाइल स्थित है और जहां आप परिवर्तित टॉपोजॉन फ़ाइल को सहेजना चाहते हैं।
## चरण 2: रूपांतरण विकल्प सेट करें
```csharp
var options = new ConversionOptions
{
    DestinationDriverOptions = new TopoJsonOptions
    {
        // उस ऑब्जेक्ट का नाम निर्दिष्ट करें जहां विशेषताएं लिखी जानी चाहिए
        DefaultObjectName = "name_of_the_object",
    }
};
```
 इस चरण में, हम एक बनाते हैं`ConversionOptions` आपत्ति करें और निर्दिष्ट करें`DefaultObjectName`, जो उस ऑब्जेक्ट का नाम है जहां परिणामी TopoJSON फ़ाइल में विशेषताएं लिखी जानी चाहिए।
## चरण 3: रूपांतरण करें
```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```
 अंत में, हम कॉल करते हैं`Convert` उसकि विधि`VectorLayer` क्लास, इनपुट जियोजसन फ़ाइल के पथ में गुजरना, इनपुट और आउटपुट ड्राइवर, और रूपांतरण विकल्प।

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा है कि .NET के लिए Aspose.GIS का उपयोग करके एक विशिष्ट ऑब्जेक्ट नाम के साथ जियोजसन को टोपोजसन में कैसे परिवर्तित किया जाए। इन चरणों का पालन करके, आप अपने .NET अनुप्रयोगों में भौगोलिक डेटा को कुशलतापूर्वक प्रबंधित और हेरफेर कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं अपनी व्यावसायिक परियोजनाओं में .NET के लिए Aspose.GIS का उपयोग कर सकता हूँ?
हां, आप वाणिज्यिक और व्यक्तिगत दोनों परियोजनाओं में .NET के लिए Aspose.GIS का उपयोग कर सकते हैं।
### क्या .NET के लिए Aspose.GIS का निःशुल्क परीक्षण उपलब्ध है?
हाँ, आप नि:शुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मुझे .NET के लिए Aspose.GIS के लिए समर्थन कहां मिल सकता है?
 से आपको सहयोग मिल सकता है[Aspose.GIS फोरम](https://forum.aspose.com/c/gis/33).
### मैं .NET के लिए Aspose.GIS का लाइसेंस कैसे खरीद सकता हूँ?
 आप यहां से लाइसेंस खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).
### क्या मुझे मूल्यांकन के लिए अस्थायी लाइसेंस की आवश्यकता है?
 हाँ, आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
