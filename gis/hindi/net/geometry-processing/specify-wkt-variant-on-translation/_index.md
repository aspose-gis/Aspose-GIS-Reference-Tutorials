---
title: Aspose.GIS का उपयोग करके अनुवाद पर WKT वेरिएंट निर्दिष्ट करें
linktitle: अनुवाद पर WKT संस्करण निर्दिष्ट करें
second_title: Aspose.GIS .NET एपीआई
description: स्थानिक डेटा प्रतिनिधित्व प्रारूप और परिशुद्धता को प्रभावी ढंग से नियंत्रित करने के लिए .NET के लिए Aspose.GIS में WKT वेरिएंट निर्दिष्ट करना सीखें।
weight: 19
url: /hi/net/geometry-processing/specify-wkt-variant-on-translation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS का उपयोग करके अनुवाद पर WKT वेरिएंट निर्दिष्ट करें

## परिचय
.NET के लिए Aspose.GIS एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को उनके .NET अनुप्रयोगों में भौगोलिक सूचना प्रणाली (GIS) डेटा के साथ सहजता से काम करने की अनुमति देती है। Aspose.GIS द्वारा प्रदान की गई आवश्यक सुविधाओं में से एक अनुवाद के दौरान सुप्रसिद्ध पाठ (WKT) संस्करण को निर्दिष्ट करने की क्षमता है, जो उपयोगकर्ताओं को स्थानिक डेटा प्रतिनिधित्व के प्रारूप और सटीकता को नियंत्रित करने में सक्षम बनाता है। इस ट्यूटोरियल में, हम यह पता लगाएंगे कि .NET के लिए Aspose.GIS का उपयोग करके चरण दर चरण WKT वेरिएंट को कैसे निर्दिष्ट किया जाए।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
1. .NET के लिए Aspose.GIS: .NET के लिए Aspose.GIS को डाउनलोड और इंस्टॉल करें[डाउनलोड पेज](https://releases.aspose.com/gis/net/).
2. विकास परिवेश: सुनिश्चित करें कि आपके पास एक .NET विकास परिवेश स्थापित है।
3. बुनियादी ज्ञान: C# प्रोग्रामिंग भाषा और .NET फ्रेमवर्क से परिचित।

## नामस्थान आयात करें
अपने कोड में Aspose.GIS कार्यक्षमता का उपयोग करने से पहले, आवश्यक नामस्थान आयात करें:
```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```
## चरण 1: एक प्वाइंट ऑब्जेक्ट बनाएं
 सबसे पहले, एक बनाएं`Point` अक्षांश, देशांतर और वैकल्पिक माप (एम) मान वाली वस्तु:
```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```
## चरण 2: स्थानिक संदर्भ प्रणाली (एसआरएस) सेट करें
बिंदु वस्तु के लिए एक स्थानिक संदर्भ प्रणाली (एसआरएस) निर्दिष्ट करें। इस उदाहरण में, हम WGS84 स्थानिक संदर्भ प्रणाली का उपयोग करते हैं:
```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```
## चरण 3: WKT वेरिएंट निर्दिष्ट करें
 अब, अनुवाद के लिए WKT संस्करण निर्दिष्ट करें। Aspose.GIS सहित विभिन्न WKT वेरिएंट का समर्थन करता है`Iso`, `SimpleFeatureAccessOutdated` , और`ExtendedPostGis`. अपनी आवश्यकताओं के आधार पर उचित प्रकार चुनें:
```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // बिंदु एम (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // बिंदु (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```
## चरण 4: संख्यात्मक प्रारूप को नियंत्रित करें
आप WKT प्रतिनिधित्व में निर्देशांक के संख्यात्मक प्रारूप को नियंत्रित कर सकते हैं। Aspose.GIS दशमलव परिशुद्धता निर्दिष्ट करने के लिए विकल्प प्रदान करता है:
```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // बिंदु एम (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // बिंदु एम (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // बिंदु एम (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // बिंदु एम (23.573 25.342 40.3)
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.GIS का उपयोग करके अनुवाद पर WKT वेरिएंट कैसे निर्दिष्ट करें। ऊपर बताए गए चरणों का पालन करके, डेवलपर्स अपने .NET अनुप्रयोगों में स्थानिक डेटा प्रतिनिधित्व के प्रारूप और सटीकता को प्रभावी ढंग से नियंत्रित कर सकते हैं, जिससे भौगोलिक सूचना प्रणालियों का लचीलापन और उपयोगिता बढ़ जाती है।
## अक्सर पूछे जाने वाले प्रश्न
### क्या Aspose.GIS .NET के सभी संस्करणों के साथ संगत है?
हाँ, Aspose.GIS .NET Framework 4.0 और उच्चतर का समर्थन करता है।
### क्या मैं व्यावसायिक परियोजनाओं के लिए Aspose.GIS का उपयोग कर सकता हूँ?
हाँ, Aspose.GIS का उपयोग व्यक्तिगत और व्यावसायिक दोनों परियोजनाओं के लिए किया जा सकता है।
### क्या Aspose.GIS अन्य स्थानिक डेटा प्रारूपों के लिए समर्थन प्रदान करता है?
हां, Aspose.GIS ESRI शेपफाइल, जियोजसन और KML सहित स्थानिक डेटा प्रारूपों की एक विस्तृत श्रृंखला का समर्थन करता है।
### क्या Aspose.GIS के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 हां, आप Aspose.GIS का निःशुल्क परीक्षण संस्करण यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मुझे Aspose.GIS के लिए सहायता या समर्थन कहां से मिल सकता है?
 आप अपने प्रश्न यहां पोस्ट कर सकते हैं या Aspose.GIS समुदाय से सहायता मांग सकते हैं[मंच](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
