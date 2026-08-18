---
date: 2026-08-18
description: Aspose.GIS for .NET का उपयोग करके दशमलव डिग्री को DMS में बदलें। यह चरण‑दर‑चरण
  C# गाइड दिखाता है कि latitude/longitude, दशमलव डिग्री को DMS और अधिक कैसे बदलें।
keywords:
- decimal degrees to dms
- convert coordinates dms
- gis coordinate conversion
- convert lat long dms
- c# convert lat long
lastmod: 2026-08-18
linktitle: निर्देशांक परिवर्तित करें
og_description: Aspose.GIS for .NET के साथ दशमलव डिग्री से DMS रूपांतरण आसान बना।
  सीखें कि latitude‑longitude मानों को मिनट में DMS प्रारूप में कैसे बदलें।
og_image_alt: Guide showing decimal degrees to DMS conversion using Aspose.GIS in
  C#
og_title: Aspose.GIS for .NET के साथ दशमलव डिग्री को DMS में बदलें
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  headline: How to convert decimal degrees to dms with Aspose.GIS for .NET
  type: TechArticle
- description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  name: How to convert decimal degrees to dms with Aspose.GIS for .NET
  steps:
  - name: start the conversion process
    text: We print a friendly message so you know the demo has begun.
  - name: convert to decimal degrees
    text: Even though the final goal is DMS, we start by showing the original decimal
      representation. This also demonstrates the **decimal degrees to dms** path you’ll
      later follow.
  - name: convert to degree decimal minutes
    text: This format (`DD°MM.m'`) is a common intermediate step when you need to
      **convert lat long degree minutes**.
  - name: convert to degree minutes seconds (dms)
    text: Here’s the core of our tutorial—**convert coordinates to dms**.
  - name: convert to GeoRef
    text: For completeness, we also demonstrate the `GeoRef` format, useful in remote‑sensing
      workflows.
  type: HowTo
- questions:
  - answer: Aspose.GIS primarily targets .NET developers, but a Java version is also
      available.
    question: Is Aspose.GIS compatible with other programming languages?
  - answer: Yes, you can access a free trial of Aspose.GIS from the [website](https://releases.aspose.com/).
    question: Can I try Aspose.GIS before purchasing?
  - answer: You can seek assistance from the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How can I get support for Aspose.GIS?
  - answer: Yes, temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses available for Aspose.GIS?
  - answer: You can purchase Aspose.GIS from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert coordinates
- Aspose.GIS
- .NET GIS processing
title: Aspose.GIS for .NET के साथ दशमलव डिग्री को DMS में कैसे बदलें
url: /hi/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS के साथ दशमलव डिग्री को DMS में कैसे बदलें

## परिचय
इस ट्यूटोरियल में आप .NET के लिए शक्तिशाली Aspose.GIS लाइब्रेरी का उपयोग करके **दशमलव डिग्री को DMS में कैसे बदलें** सीखेंगे। चाहे आपको **c# convert lat long** की आवश्यकता हो, रिपोर्टों के लिए मानव‑पठनीय स्थान स्ट्रिंग्स बनानी हों, या विभिन्न निर्देशांक स्वरूपों का अन्वेषण करना हो, यह गाइड स्पष्ट व्याख्याओं और तैयार‑चलाने योग्य C# स्निपेट्स के साथ आपको हर चरण में ले जाता है।

## त्वरित उत्तर
- **“convert coordinates to dms” का क्या अर्थ है?** यह संख्यात्मक अक्षांश/देशांतर मानों को पारंपरिक डिग्री‑मिनट‑सेकंड नोटेशन में बदलता है।  
- **कौन सी लाइब्रेरी परिवर्तन को संभालती है?** Aspose.GIS for .NET `GeoConvert` क्लास प्रदान करता है जिसमें अंतर्निहित फ़ॉर्मेट समर्थन है।  
- **क्या इसे आज़माने के लिए लाइसेंस चाहिए?** एक मुफ्त ट्रायल उपलब्ध है; उत्पादन उपयोग के लिए व्यावसायिक लाइसेंस आवश्यक है।  
- **कौन से .NET संस्करण समर्थित हैं?** .NET Framework 4.5+, .NET Core 3.1+, और .NET 5/6+.  
- **क्या मैं वही कोड अन्य फ़ॉर्मेट्स के लिए उपयोग कर सकता हूँ?** हाँ—सिर्फ `PointFormats` enum मान को बदलें (जैसे, `DecimalDegrees`, `GeoRef`)।

## कोऑर्डिनेट को DMS में बदलना क्या है?
कोऑर्डिनेट को DMS में बदलना दशमलव अक्षांश और देशांतर मानों को `25°30'00"N 45°30'00"E` जैसे स्वरूप में पुनः लिखता है। प्रक्रिया प्रत्येक दशमलव डिग्री को पूर्ण डिग्री, मिनट (डिग्री का एक‑साठवाँ भाग), और सेकंड (मिनट का एक‑साठवाँ भाग) में विभाजित करती है, फिर उपयुक्त गोलार्ध संकेत (N, S, E, W) जोड़ती है। यह मानव‑पठनीय रूप कई पुरानी डेटासेट्स और दशमलव नोटेशन पर निर्भर किए बिना सटीक स्थान संप्रेषित करने के लिए आवश्यक है।

## कोऑर्डिनेट परिवर्तन के लिए Aspose.GIS क्यों उपयोग करें?
Aspose.GIS **50+ इनपुट और आउटपुट फ़ॉर्मेट्स** का समर्थन करता है और पूरी डेटासेट को मेमोरी में लोड किए बिना कई‑सौ‑पृष्ठ GIS फ़ाइलों को प्रोसेस कर सकता है। API नकारात्मक मानों और गोलार्ध संकेतकों जैसे किनारी मामलों के लिए सब‑मिलीमीटर सटीकता प्रदान करता है, और यह Windows, Linux, और macOS .NET रनटाइम्स पर लगातार चलता है।

## पूर्वापेक्षाएँ
Before you start, make sure you have:

1. **C# का बुनियादी ज्ञान** – वेरिएबल्स, मेथड कॉल्स, और कंसोल आउटपुट की परिचितता।  
2. **Aspose.GIS installed** – नवीनतम पैकेज को [Aspose.GIS वेबसाइट](https://releases.aspose.com/gis/net/) से डाउनलोड करें। आप मुख्य Aspose रिलीज़ साइट को भी [Aspose रिलीज़ वेबसाइट](https://releases.aspose.com/) पर देख सकते हैं।  

## नामस्थान आयात करें
First, import the namespaces required for GIS operations:

Import Namespaces प्लेसहोल्डर अपरिवर्तित रहता है।

## कदम‑दर‑कदम मार्गदर्शिका

### GeoConvert क्लास क्या है?
`GeoConvert` क्लास स्थैतिक मेथड्स प्रदान करता है जो दशमलव डिग्री, DMS, और GeoRef जैसे कोऑर्डिनेट फ़ॉर्मेट्स के बीच परिवर्तन करते हैं। इसमें ओवरलोड्स शामिल हैं जो कच्चे संख्यात्मक मान या `Point` ऑब्जेक्ट्स को स्वीकार करते हैं और फ़ॉर्मेटेड स्ट्रिंग्स या नए `Point` इंस्टेंस लौटाते हैं। नकारात्मक कोऑर्डिनेट्स और राउंडिंग जैसे किनारी मामलों को संभालकर, क्लास यह सुनिश्चित करता है कि आउटपुट मानक GIS विनिर्देशों के अनुरूप हो, जिससे किसी भी .NET मैपिंग एप्लिकेशन में एकीकरण सरल हो जाता है।

### चरण 1: परिवर्तन प्रक्रिया शुरू करें
हम एक मैत्रीपूर्ण संदेश प्रिंट करते हैं ताकि आपको पता चले कि डेमो शुरू हो गया है।

```csharp
using System;
using Aspose.Gis;
```

### चरण 2: दशमलव डिग्री में बदलें
हालांकि अंतिम लक्ष्य DMS है, हम मूल दशमलव प्रतिनिधित्व दिखाकर शुरू करते हैं। यह **decimal degrees to dms** पथ को भी दर्शाता है जिसे आप बाद में अनुसरण करेंगे।

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### चरण 3: डिग्री दशमलव मिनट में बदलें
यह स्वरूप (`DD°MM.m'`) एक सामान्य मध्यवर्ती चरण है जब आपको **convert lat long degree minutes** की आवश्यकता होती है।

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### चरण 4: डिग्री मिनट सेकंड (dms) में बदलें
यह हमारे ट्यूटोरियल का मुख्य भाग है—**convert coordinates to dms**।

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### चरण 5: GeoRef में बदलें
पूरा करने के लिए, हम `GeoRef` स्वरूप को भी दर्शाते हैं, जो रिमोट‑सेंसिंग कार्यप्रवाहों में उपयोगी है।

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

## सामान्य समस्याएँ और समाधान
- **गलत गोलार्ध अक्षर** – सुनिश्चित करें कि आप उत्तर/पूर्व के लिए सकारात्मक मान और दक्षिण/पश्चिम के लिए नकारात्मक मान पास कर रहे हैं; API स्वचालित रूप से सही प्रत्यय जोड़ता है।  
- **अप्रत्याशित खाली आउटपुट** – `Aspose.Gis` असेंबली सही ढंग से संदर्भित है और प्रोजेक्ट समर्थित .NET संस्करण को लक्षित कर रहा है, यह सत्यापित करें।  
- **लाइसेंस नहीं मिला** – अपनी लाइसेंस फ़ाइल को एप्लिकेशन रूट में रखें या प्रोग्रामेटिकली सेट करें `License license = new License(); license.SetLicense("Aspose.GIS.lic");` के साथ।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या Aspose.GIS अन्य प्रोग्रामिंग भाषाओं के साथ संगत है?**  
A: Aspose.GIS मुख्य रूप से .NET डेवलपर्स को लक्षित करता है, लेकिन एक Java संस्करण भी उपलब्ध है।

**Q: क्या मैं खरीदने से पहले Aspose.GIS आज़मा सकता हूँ?**  
A: हाँ, आप Aspose.GIS का मुफ्त ट्रायल [website](https://releases.aspose.com/) से एक्सेस कर सकते हैं।

**Q: मैं Aspose.GIS के लिए समर्थन कैसे प्राप्त कर सकता हूँ?**  
A: आप Aspose.GIS समुदाय फ़ोरम से सहायता ले सकते हैं [here](https://forum.aspose.com/c/gis/33)।

**Q: क्या Aspose.GIS के लिए अस्थायी लाइसेंस उपलब्ध हैं?**  
A: हाँ, अस्थायी लाइसेंस [temporary license page](https://purchase.aspose.com/temporary-license/) से प्राप्त किए जा सकते हैं।

**Q: मैं Aspose.GIS कहाँ से खरीद सकता हूँ?**  
A: आप Aspose.GIS को [purchase page](https://purchase.aspose.com/buy) से खरीद सकते हैं।

## निष्कर्ष
इन चरणों का पालन करके, आप अब Aspose.GIS for .NET का उपयोग करके **decimal degrees to dms** और अन्य सामान्य GIS फ़ॉर्मेट्स को कैसे बदलें, जानते हैं। यह क्षमता आपको मानव‑पठनीय स्थान स्ट्रिंग्स को मैपिंग एप्लिकेशन, रिपोर्टों, या किसी भी स्पैशियल डेटा वर्कफ़्लो में सहजता से एकीकृत करने देती है। विभिन्न अक्षांश/देशांतर मानों के साथ प्रयोग करने और `GeoConvert` क्लास द्वारा प्रदान किए गए अन्य फ़ॉर्मेट्स का अन्वेषण करने में संकोच न करें।

---

**अंतिम अपडेट:** 2026-08-18  
**परीक्षित संस्करण:** Aspose.GIS 24.11 for .NET  
**लेखक:** Aspose  

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## संबंधित ट्यूटोरियल

- [Aspose.GIS for .NET के साथ पॉइंट जियोमेट्री बनाना और जियोमेट्री टाइप प्राप्त करना](/gis/net/geometry-analysis/get-geometry-type/)
- [GeoJSON कैसे कनवर्ट करें – Aspose.GIS for .NET](/gis/net/geo-data-conversion/)
- [Aspose.GIS के साथ .NET में मल्टीपॉइंट जियोमेट्री बनाएं](/gis/net/geometry-creation/create-multipoint-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}