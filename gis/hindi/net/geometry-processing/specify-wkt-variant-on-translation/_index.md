---
date: 2026-09-15
description: Aspose.GIS for .NET के साथ C# में point geometry बनाते समय coordinate
  system असाइन करना, WKT variant सेट करना और decimal precision को नियंत्रित करना सीखें।
keywords:
- assign coordinate system
- assign spatial reference
- set decimal precision
- create point geometry
- set numeric format
lastmod: 2026-09-15
linktitle: अनुवाद पर WKT Variant निर्दिष्ट करें
og_description: Aspose.GIS for .NET के साथ C# में point geometry बनाते समय coordinate
  system असाइन करना, WKT variant सेट करना और decimal precision को नियंत्रित करना सीखें।
og_image_alt: Developer guide showing C# code to assign coordinate system and configure
  WKT output with Aspose.GIS
og_title: Aspose.GIS का उपयोग करके coordinate system असाइन करें और WKT variant सेट
  करें
schemas:
- author: Aspose
  dateModified: '2026-09-15'
  description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  headline: Assign coordinate system, set WKT variant using Aspose.GIS
  type: TechArticle
- description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  name: Assign coordinate system, set WKT variant using Aspose.GIS
  steps:
  - name: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
    text: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
  - name: A .NET development environment (Visual Studio, VS Code, or Rider).
    text: A .NET development environment (Visual Studio, VS Code, or Rider).
  - name: Basic familiarity with C# and the .NET framework.
    text: Basic familiarity with C# and the .NET framework.
  type: HowTo
- questions:
  - answer: It binds a geometry to a specific coordinate reference system such as
      WGS‑84.
    question: What does “assign coordinate system” mean?
  - answer: Iso, SimpleFeatureAccessOutdated, and ExtendedPostGis.
    question: Which WKT variants are supported?
  - answer: Use the `NumericFormat` enum (`General`, `RoundTrip`, `Flat`).
    question: How can I control decimal precision?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license for Aspose.GIS?
  - answer: .NET Framework 4.0+ and .NET Core/5/6+.
    question: What .NET versions are compatible?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- assign coordinate system
- Aspose.GIS
- C# geometry
- WKT variant
title: Aspose.GIS का उपयोग करके coordinate system असाइन करें और WKT variant सेट करें
url: /hi/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# कोऑर्डिनेट सिस्टम असाइन करें, Aspose.GIS का उपयोग करके WKT वैरिएंट सेट करें

## परिचय
इस ट्यूटोरियल में आप सीखेंगे कि **assign coordinate system** कैसे किया जाता है, सही WKT वैरिएंट कैसे चुना जाता है, और C# में Aspose.GIS for .NET के साथ **create point geometry** करते समय दशमलव सटीकता को कैसे नियंत्रित किया जाता है। चाहे आप मैपिंग सेवा बना रहे हों, स्पैशियल एनालिटिक्स कर रहे हों, या GIS प्लेटफ़ॉर्म के बीच डेटा का आदान‑प्रदान कर रहे हों, ये सेटिंग्स सुनिश्चित करती हैं कि आपका आउटपुट दोनों ही इंटरऑपरेबल और पढ़ने में आसान हो। चलिए प्रक्रिया को चरण‑दर‑चरण देखते हैं।

## त्वरित उत्तर
- **What does “assign coordinate system” mean?** यह एक जियोमेट्री को WGS‑84 जैसे विशिष्ट कॉर्डिनेट रेफरेंस सिस्टम से बाइंड करता है।  
- **Which WKT variants are supported?** Iso, SimpleFeatureAccessOutdated, और ExtendedPostGis.  
- **How can I control decimal precision?** डेसिमल प्रिसीजन को नियंत्रित करने के लिए `NumericFormat` enum (`General`, `RoundTrip`, `Flat`) का उपयोग करें।  
- **Do I need a license for Aspose.GIS?** एक फ्री ट्रायल उपलब्ध है; प्रोडक्शन उपयोग के लिए एक कमर्शियल लाइसेंस आवश्यक है।  
- **What .NET versions are compatible?** .NET Framework 4.0+ और .NET Core/5/6+.

## “assign coordinate system” क्या है?
स्पैशियल रेफ़रेंस (या स्पैशियल रेफ़रेंस सिस्टम, SRS) असाइन करने से GIS सॉफ़्टवेयर को पता चलता है कि जियोमेट्री के कॉर्डिनेट मानों की व्याख्या कैसे करनी है, जिससे संख्याओं को WGS‑84 जैसे वास्तविक दुनिया के कॉर्डिनेट सिस्टम से जोड़ा जाता है। बिना SRS के, किसी पॉइंट के लैटिट्यूड‑लॉन्गिट्यूड मानों का वास्तविक दुनिया में कोई अर्थ नहीं रहता।

## क्यों नियंत्रित करें WKT वैरिएंट और न्यूमेरिक फ़ॉर्मेट?
30 से अधिक GIS टूल्स विशिष्ट WKT सिंटैक्स की अपेक्षा करते हैं, इसलिए सही वैरिएंट चुनने से इम्पोर्ट एरर से बचा जा सकता है। न्यूमेरिक फ़ॉर्मेट सेट करने से राउंडिंग नॉइज़ कम होती है और आउटपुट संक्षिप्त रहता है, जो विशेष रूप से तब महत्वपूर्ण है जब लॉग्स या फ़ाइलों को प्रोग्रामेटिकली पार्स किया जाता है।

## पूर्वापेक्षाएँ
1. Aspose.GIS for .NET – डाउनलोड करें [download page](https://releases.aspose.com/gis/net/).  
2. .NET विकास पर्यावरण (Visual Studio, VS Code, या Rider).  
3. C# और .NET फ्रेमवर्क की बुनियादी परिचितता।

## नेमस्पेस इम्पोर्ट करें
किसी भी Aspose.GIS क्लास का उपयोग करने से पहले, आवश्यक नेमस्पेस इम्पोर्ट करें:

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

## पॉइंट को कोऑर्डिनेट सिस्टम कैसे असाइन करें?
एक `Point` इंस्टेंस लोड करें, फिर `SpatialReference` क्लास का उपयोग करके स्पैशियल रेफ़रेंस सिस्टम (SRS) अटैच करें। यह दो‑स्टेप पैटर्न सुनिश्चित करता है कि जियोमेट्री एक्सपोर्ट होने पर अपने कोऑर्डिनेट सिस्टम मेटाडेटा को ले जाए, जिससे डाउनस्ट्रीम टूल्स कोऑर्डिनेट्स को सही ढंग से समझ सकें। `Point` क्लास एकल लोकेशन को दर्शाती है जो X (longitude) और Y (latitude) कॉर्डिनेट्स द्वारा परिभाषित होती है।

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## चरण 2: स्पैशियल रेफ़रेंस सिस्टम (SRS) असाइन करें
अब हम पॉइंट को **assign spatial reference** करते हैं। `SpatialReference` एक कोऑर्डिनेट रेफ़रेंस सिस्टम को दर्शाता है जो SRID द्वारा पहचाना जाता है। यहाँ हम व्यापक रूप से समर्थित WGS‑84 सिस्टम (SRID 4326) का उपयोग करते हैं:

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## चरण 3: वांछित WKT वैरिएंट निर्दिष्ट करें
ऐसा WKT वैरिएंट चुनें जो आपके डाउनस्ट्रीम एप्लिकेशन से मेल खाता हो:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## WKT आउटपुट के लिए दशमलव सटीकता कैसे सेट करें?
अंतिम स्ट्रिंग में कितने अंक दिखेंगे, इसे `NumericFormat` enum का उपयोग करके नियंत्रित करें, जो `General`, `RoundTrip`, या `Flat` जैसे फ़ॉर्मेटिंग नियम निर्धारित करता है। `RoundTrip` चुनने से राउंड‑ट्रिपिंग परिदृश्यों के लिए पूर्ण कोऑर्डिनेट फ़िडेलिटी बनी रहती है, जबकि `General` अधिकांश विज़ुअलाइज़ेशन कार्यों के लिए संक्षिप्त प्रतिनिधित्व प्रदान करता है। `NumericFormat` enum यह नियंत्रित करता है कि WKT आउटपुट में कोऑर्डिनेट नंबर कैसे फ़ॉर्मेट किए जाएँ।

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### सामान्य जाल और टिप्स
- **Pitfall:** `AsText` कॉल करने से पहले SRS सेट करना भूलने से SRID जानकारी गायब हो सकती है।  
- **Tip:** जब आपको कोऑर्डिनेट्स का लॉसलेस राउंड‑ट्रिप चाहिए, तो `NumericFormat.RoundTrip` का उपयोग करें।  
- **Tip:** `Iso` वैरिएंट सबसे पोर्टेबल है; केवल तब `ExtendedPostGis` चुनें जब आपको SRID एम्बेडेड चाहिए।

## निष्कर्ष
अब आप जानते हैं कि Aspose.GIS के साथ **assign coordinate system**, उपयुक्त WKT वैरिएंट कैसे चुनें, और **create point geometry** करते समय **set decimal precision** कैसे करें। ये नियंत्रण आपको किसी भी GIS वर्कफ़्लो की सटीक आवश्यकताओं को पूरा करने की लचीलापन देते हैं, सरल विज़ुअलाइज़ेशन से लेकर हाई‑प्रेसिशन स्पैशियल एनालिसिस तक।

## अक्सर पूछे जाने वाले प्रश्न

**Q:** क्या Aspose.GIS सभी .NET संस्करणों के साथ संगत है?  
**A:** हाँ, Aspose.GIS .NET Framework 4.0 और उससे ऊपर, साथ ही .NET Core/5/6 को सपोर्ट करता है।

**Q:** क्या मैं Aspose.GIS को व्यावसायिक प्रोजेक्ट्स में उपयोग कर सकता हूँ?  
**A:** बिल्कुल। प्रोडक्शन उपयोग के लिए एक कमर्शियल लाइसेंस आवश्यक है, लेकिन मूल्यांकन के लिए एक फ्री ट्रायल उपलब्ध है।

**Q:** क्या Aspose.GIS अन्य स्पैशियल डेटा फ़ॉर्मेट्स को सपोर्ट करता है?  
**A:** हाँ, यह 30+ फ़ॉर्मेट्स के साथ काम करता है, जिसमें ESRI Shapefile, GeoJSON, KML, CSV, और कई अन्य शामिल हैं।

**Q:** मैं फ्री ट्रायल कहाँ डाउनलोड कर सकता हूँ?  
**A:** आप Aspose.GIS का फ्री ट्रायल संस्करण [Aspose.GIS free trial download page](https://releases.aspose.com/) से डाउनलोड कर सकते हैं।

**Q:** यदि मुझे समस्याएँ आती हैं तो मैं मदद कैसे प्राप्त करूँ?  
**A:** आप अपने प्रश्न Aspose.GIS कम्युनिटी [forum](https://forum.aspose.com/c/gis/33) पर पोस्ट कर सकते हैं जहाँ Aspose स्टाफ और कम्युनिटी सदस्य मदद करेंगे।

---

**अंतिम अपडेट:** 2026-09-15  
**परीक्षित संस्करण:** Aspose.GIS for .NET (latest release)  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [एक वेक्टर लेयर बनाएं और उसका स्पैशियल रेफ़रेंस सिस्टम सेट करें](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Aspose.GIS for .NET के साथ जियोमेट्री को WKT में कैसे ट्रांसलेट करें](/gis/net/geometry-processing/translate-geometry-to-wkt/)
- [Aspose.GIS के साथ जियोमेट्री लिखते समय प्रिसीजन को कैसे लिमिट करें](/gis/net/geometry-processing/limit-precision-writing-geometries/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}