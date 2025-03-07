---
title: Aspose.GIS का उपयोग करके छेद ज्यामिति के साथ बहुभुज बनाएं
linktitle: छेद ज्यामिति के साथ बहुभुज बनाएं
second_title: Aspose.GIS .NET एपीआई
description: .NET के लिए Aspose.GIS का उपयोग करके छेद ज्यामिति के साथ बहुभुज बनाना सीखें। कोड उदाहरणों के साथ चरण-दर-चरण ट्यूटोरियल।
weight: 13
url: /hi/net/geometry-creation/create-polygon-with-hole-geometry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS का उपयोग करके छेद ज्यामिति के साथ बहुभुज बनाएं

## परिचय
इस ट्यूटोरियल में, हम .NET के लिए Aspose.GIS का उपयोग करके एक छेद ज्यामिति के साथ बहुभुज बनाने की प्रक्रिया से गुजरेंगे। Aspose.GIS एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को उनके .NET अनुप्रयोगों में भू-स्थानिक डेटा के साथ काम करने में सक्षम बनाती है। 
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
1. .NET लाइब्रेरी के लिए Aspose.GIS: आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/gis/net/).
2. विकास परिवेश: सुनिश्चित करें कि आपके पास विज़ुअल स्टूडियो या किसी अन्य .NET IDE स्थापित के साथ एक विकास परिवेश स्थापित है।
## नामस्थान आयात करें
सबसे पहले, आपको Aspose.GIS कार्यात्मकताओं के साथ काम करने के लिए आवश्यक नामस्थान आयात करने की आवश्यकता है। इसे करने का तरीका यहां बताया गया है:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

अब, आइए .NET के लिए Aspose.GIS का उपयोग करके एक छेद ज्यामिति वाला बहुभुज बनाने के लिए आगे बढ़ें।
## चरण 1: बहुभुज ऑब्जेक्ट बनाएं
```csharp
Polygon polygon = new Polygon();
```
## चरण 2: बाहरी रिंग को परिभाषित करें
```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```
## चरण 3: आंतरिक रिंग (छेद) को परिभाषित करें
```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```
## चरण 4: बाहरी रिंग निर्दिष्ट करें और आंतरिक रिंग को बहुभुज में जोड़ें
```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```
## निष्कर्ष
बधाई हो! आपने .NET के लिए Aspose.GIS का उपयोग करके छेद ज्यामिति के साथ बहुभुज बनाना सफलतापूर्वक सीख लिया है। यह ज्ञान विभिन्न भू-स्थानिक अनुप्रयोगों के लिए फायदेमंद होगा जहां ऐसी ज्यामिति आवश्यक हैं।
## अक्सर पूछे जाने वाले प्रश्न
### 1. Aspose.GIS क्या है?
Aspose.GIS एक .NET लाइब्रेरी है जो डेवलपर्स को भू-स्थानिक डेटा के साथ काम करने में सक्षम बनाती है, जिससे उन्हें विभिन्न भू-स्थानिक फ़ाइल स्वरूपों को बनाने, पढ़ने और हेरफेर करने की अनुमति मिलती है।
### 2. क्या मैं व्यावसायिक परियोजनाओं के लिए Aspose.GIS का उपयोग कर सकता हूँ?
 हां, आप लाइसेंस खरीदकर व्यक्तिगत और व्यावसायिक दोनों परियोजनाओं के लिए Aspose.GIS का उपयोग कर सकते हैं। मिलने जाना[यहाँ](https://purchase.aspose.com/buy) अधिक जानकारी के लिए।
### 3. क्या Aspose.GIS के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 हाँ, आप Aspose.GIS के निःशुल्क परीक्षण का लाभ उठा सकते हैं[यहाँ](https://releases.aspose.com/).
### 4. मुझे Aspose.GIS के लिए समर्थन कहां मिल सकता है?
 आप Aspose.GIS के लिए समर्थन पा सकते हैं[Aspose.GIS फोरम](https://forum.aspose.com/c/gis/33).
### 5. मैं Aspose.GIS के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 आप Aspose.GIS के लिए एक अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
