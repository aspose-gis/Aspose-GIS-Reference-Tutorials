---
date: 2026-04-09
description: अपने .NET एप्लिकेशनों में Aspose.GIS for .NET का उपयोग करके C# में पॉइंट
  बनाते समय स्पैशियल रेफ़रेंस असाइन करना और दशमलव सटीकता सेट करना सीखें।
keywords:
- assign spatial reference
- set decimal precision
- create point c#
linktitle: अनुवाद में WKT वैरिएंट निर्दिष्ट करें
second_title: Aspose.GIS .NET API
title: Aspose.GIS का उपयोग करके स्पैशियल रेफ़रेंस असाइन करें और WKT वेरिएंट सेट करें
url: /hi/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# स्पैशियल रेफ़रेंस असाइन करें और Aspose.GIS का उपयोग करके WKT वैरिएंट सेट करें

## परिचय
इस ट्यूटोरियल में आप सीखेंगे कि कैसे एक ज्योमेट्री को **assign spatial reference** किया जाए और Aspose.GIS for .NET के साथ सटीक WKT आउटपुट फ़ॉर्मेट को नियंत्रित किया जाए। चाहे आपको मैपिंग, एनालिटिक्स, या डेटा एक्सचेंज के लिए **create point C#** ऑब्जेक्ट्स बनाने की आवश्यकता हो, सही WKT वैरिएंट और संख्यात्मक प्रिसीजन चुनना आपके स्पैशियल डेटा को इंटरऑपरेबल और पढ़ने में आसान बनाता है। चलिए प्रक्रिया को चरण दर चरण देखते हैं।

## त्वरित उत्तर
- **What does “assign spatial reference” mean?** यह एक ज्योमेट्री को WGS‑84 जैसे विशिष्ट कोऑर्डिनेट सिस्टम से बाइंड करता है।  
- **Which WKT variants are supported?** Iso, SimpleFeatureAccessOutdated, और ExtendedPostGis।  
- **How can I control decimal precision?** `NumericFormat` विकल्पों जैसे `General`, `RoundTrip`, या `Flat` का उपयोग करें।  
- **Do I need a license?** एक फ्री ट्रायल उपलब्ध है; उत्पादन के लिए एक कमर्शियल लाइसेंस आवश्यक है।  
- **What .NET versions are compatible?** .NET Framework 4.0+ और .NET Core/5/6+।

## “assign spatial reference” क्या है?
स्पैशियल रेफ़रेंस (या स्पैशियल रेफ़रेंस सिस्टम, SRS) असाइन करने से GIS सॉफ़्टवेयर को यह पता चलता है कि किसी ज्योमेट्री के कोऑर्डिनेट मानों की व्याख्या कैसे करनी है। बिना SRS के, किसी पॉइंट के लैटिट्यूड‑लॉन्गिट्यूड संख्याओं का वास्तविक दुनिया में कोई अर्थ नहीं होता।

## WKT वैरिएंट और संख्यात्मक फ़ॉर्मेट को क्यों नियंत्रित करें?
विभिन्न GIS टूल्स थोड़ी अलग WKT सिंटैक्स की अपेक्षा करते हैं। उचित वैरिएंट का चयन सहज डेटा एक्सचेंज सुनिश्चित करता है, जबकि दशमलव प्रिसीजन सेट करने से राउंडिंग त्रुटियों या बहुत लंबे संख्याओं से बचा जा सकता है जो लॉग और फ़ाइलों को अव्यवस्थित कर देते हैं।

## पूर्वापेक्षाएँ
1. Aspose.GIS for .NET – डाउनलोड करें [download page](https://releases.aspose.com/gis/net/) से।  
2. .NET विकास वातावरण (Visual Studio, VS Code, या Rider)।  
3. C# और .NET फ्रेमवर्क की बुनियादी परिचितता।

## नेमस्पेस आयात करें
Aspose.GIS क्लासेज़ का उपयोग करने से पहले, आवश्यक नेमस्पेस आयात करें:

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

## चरण 1: पॉइंट ऑब्जेक्ट बनाएं (create point C#)
`Point` को लैटिट्यूड, लॉन्गिट्यूड, और एक वैकल्पिक माप (M) मान के साथ बनाकर शुरू करते हैं:

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## चरण 2: स्पैशियल रेफ़रेंस सिस्टम (SRS) असाइन करें
अब हम पॉइंट को **assign spatial reference** करते हैं। यहाँ हम व्यापक रूप से समर्थित WGS‑84 सिस्टम (SRID 4326) का उपयोग करते हैं:

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## चरण 3: इच्छित WKT वैरिएंट निर्दिष्ट करें
अपने डाउनस्ट्रीम एप्लिकेशन से मेल खाने वाला WKT वैरिएंट चुनें:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## चरण 4: WKT आउटपुट के लिए दशमलव प्रिसीजन सेट करें
`NumericFormat` का उपयोग करके अंतिम स्ट्रिंग में कितने अंक दिखेंगे, इसे नियंत्रित करें:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### सामान्य जाल और सुझाव
- **Pitfall:** `AsText` कॉल करने से पहले SRS सेट करना भूल जाने पर SRID जानकारी गायब हो सकती है।  
- **Tip:** जब आपको कॉर्डिनेट्स का लॉसलेस राउंड‑ट्रिप चाहिए तो `NumericFormat.RoundTrip` का उपयोग करें।  
- **Tip:** `Iso` वैरिएंट सबसे पोर्टेबल है; केवल तब `ExtendedPostGis` चुनें जब आपको SRID एम्बेडेड चाहिए।

## निष्कर्ष
अब आप जानते हैं कि कैसे **assign spatial reference** किया जाए, उपयुक्त WKT वैरिएंट चुना जाए, और Aspose.GIS के साथ **create point C#** ऑब्जेक्ट्स बनाते समय **set decimal precision** किया जाए। ये नियंत्रण आपको किसी भी GIS वर्कफ़्लो की सटीक आवश्यकताओं को पूरा करने की लचीलापन देते हैं, सरल विज़ुअलाइज़ेशन से लेकर हाई‑प्रेसिशन स्पैशियल एनालिसिस तक।

## अक्सर पूछे जाने वाले प्रश्न

**Q:** क्या Aspose.GIS सभी .NET संस्करणों के साथ संगत है?  
**A:** हाँ, Aspose.GIS .NET Framework 4.0 और उससे ऊपर, साथ ही .NET Core/5/6 को सपोर्ट करता है।

**Q:** क्या मैं Aspose.GIS को व्यावसायिक प्रोजेक्ट्स में उपयोग कर सकता हूँ?  
**A:** बिल्कुल। उत्पादन उपयोग के लिए एक कमर्शियल लाइसेंस आवश्यक है, लेकिन मूल्यांकन के लिए एक फ्री ट्रायल उपलब्ध है।

**Q:** क्या Aspose.GIS अन्य स्पैशियल डेटा फ़ॉर्मेट्स को सपोर्ट करता है?  
**A:** हाँ, यह ESRI Shapefile, GeoJSON, KML, और कई अन्य फ़ॉर्मेट्स के साथ काम करता है।

**Q:** मैं फ्री ट्रायल कहाँ डाउनलोड कर सकता हूँ?  
**A:** आप Aspose.GIS का फ्री ट्रायल संस्करण [here](https://releases.aspose.com/) से डाउनलोड कर सकते हैं।

**Q:** अगर मुझे समस्याएँ आती हैं तो मदद कैसे प्राप्त करूँ?  
**A:** अपने प्रश्न Aspose.GIS कम्युनिटी के [forum](https://forum.aspose.com/c/gis/33) पर पोस्ट करें जहाँ Aspose स्टाफ और कम्युनिटी सदस्य मदद करेंगे।

---

**अंतिम अपडेट:** 2026-04-09  
**परीक्षित संस्करण:** Aspose.GIS for .NET (latest release)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}