---
date: 2025-12-23
description: Aspose.GIS for .NET का उपयोग करके विभिन्न विकल्पों के साथ ज्यामिति को
  WKT में कैसे बदलें, संख्यात्मक स्वरूप सेट करें और दशमलव सटीकता को समायोजित करें,
  सीखें।
linktitle: Convert Geometry to WKT
second_title: Aspose.GIS .NET API
title: Aspose.GIS का उपयोग करके ज्यामिति को WKT वैरिएंट विकल्पों में परिवर्तित करें
url: /hi/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS का उपयोग करके जियोमेट्री को WKT वैरिएंट विकल्पों में परिवर्तित करें

## परिचय
आधुनिक .NET अनुप्रयोगों में, **जियोमेट्री को WKT में बदलना** एक सामान्य चरण है जब आपको स्थानिक डेटा को अन्य सिस्टमों के साथ आदान‑प्रदान करना होता है या इसे टेक्स्ट‑आधारित फ़ॉर्मेट में संग्रहीत करना होता है। Aspose.GIS for .NET इस परिवर्तन को सहज बनाता है और आपको WKT वैरिएंट, संख्यात्मक फ़ॉर्मेट और दशमलव सटीकता पर पूर्ण नियंत्रण देता है। इस ट्यूटोरियल में आप सीखेंगे कि जियोमेट्री को WKT में कैसे बदलें, सही वैरिएंट कैसे चुनें, और आउटपुट को अपने प्रोजेक्ट की सटीक आवश्यकताओं के अनुसार कैसे ट्यून करें।

## त्वरित उत्तर
- **“जियोमेट्री को WKT में बदलना” का क्या अर्थ है?** यह ज्यामितीय ऑब्जेक्ट्स (बिंदु, रेखा, बहुभुज) को Well‑Known Text प्रतिनिधित्व में परिवर्तित करता है।  
- **कौन से WKT वैरिएंट समर्थित हैं?** `Iso`, `SimpleFeatureAccessOutdated`, और `ExtendedPostGis`।  
- **मैं दशमलव सटीकता को कैसे नियंत्रित कर सकता हूँ?** `NumericFormat` विकल्पों जैसे `General`, `RoundTrip`, या `Flat` का उपयोग करें।  
- **उत्पादन के लिए लाइसेंस की आवश्यकता है क्या?** हाँ, गैर‑ट्रायल उपयोग के लिए एक व्यावसायिक लाइसेंस आवश्यक है।  
- **कौन से .NET संस्करण संगत हैं?** .NET Framework 4.0+ और .NET 5/6/7।

## “जियोमेट्री को WKT में बदलना” क्या है?
जियोमेट्री को WKT में बदलने से एक मानव‑पठनीय स्ट्रिंग बनती है जो स्थानिक ऑब्जेक्ट्स का वर्णन करती है। यह फ़ॉर्मेट GIS टूल्स, डेटाबेस और वेब सर्विसेज द्वारा व्यापक रूप से स्वीकार किया जाता है, जिससे डेटा इंटरचेंज के लिए यह आदर्श बन जाता है।

## इस परिवर्तन के लिए Aspose.GIS क्यों उपयोग करें?
- **सटीकता नियंत्रण** – तय करें कि कितने दशमलव स्थान आउटपुट में शामिल हों।  
- **वैरिएंट लचीलापन** – आपके डाउनस्ट्रीम सिस्टम द्वारा आवश्यक सटीक WKT डायलैक्ट से मेल करें।  
- **कोई बाहरी निर्भरताएँ नहीं** – शुद्ध .NET लाइब्रेरी, कोई नेटिव बाइनरी नहीं।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हों:

1. **Aspose.GIS for .NET** – इसे [download page](https://releases.aspose.com/gis/net/) से डाउनलोड करके इंस्टॉल करें।  
2. **डेवलपमेंट एनवायरनमेंट** – Visual Studio या VS Code का कोई भी नवीनतम संस्करण, जिसमें .NET SDK स्थापित हो।  
3. **बेसिक C# ज्ञान** – क्लासेज, ऑब्जेक्ट्स और .NET फ्रेमवर्क की परिचितता।

## नेमस्पेस आयात करें
पहले, आवश्यक नेमस्पेस को स्कोप में लाएँ:

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

## चरण 1: एक पॉइंट ऑब्जेक्ट बनाएं
एक `Point` बनाएँ जिसे आप बाद में **जियोमेट्री को WKT में बदलेंगे**। इस पॉइंट में अक्षांश, देशांतर और एक वैकल्पिक माप (M) मान शामिल है:

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## चरण 2: स्पैशियल रेफ़रेंस सिस्टम (SRS) सेट करें
एक स्पैशियल रेफ़रेंस सिस्टम असाइन करें ताकि WKT आउटपुट को पता हो कि किस कोऑर्डिनेट सिस्टम का संदर्भ देना है। यहाँ हम सामान्य WGS84 सिस्टम का उपयोग करते हैं:

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## चरण 3: WKT वैरिएंट निर्दिष्ट करें
जब आप **जियोमेट्री को WKT में बदलते** हैं तो उपयुक्त WKT वैरिएंट चुनें। प्रत्येक वैरिएंट आउटपुट को थोड़ा अलग फ़ॉर्मेट में प्रस्तुत करता है:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## चरण 4: संख्यात्मक फ़ॉर्मेट नियंत्रित करें (Set Numeric Format & Adjust Decimal Precision)
कोऑर्डिनेट्स के संख्यात्मक प्रतिनिधित्व को फाइन‑ट्यून करें। `NumericFormat` क्लास आपको **संख्यात्मक फ़ॉर्मेट सेट** करने और **दशमलव सटीकता समायोजित** करने की अनुमति देता है:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

## सामान्य समस्याएँ और सुझाव
- **M मान अनुपलब्ध** – यदि आपको माप की आवश्यकता नहीं है, तो `M` प्रॉपर्टी को छोड़ दें; ISO वैरिएंट इसे स्वचालित रूप से हटा देगा।  
- **अप्रत्याशित सटीकता** – दोबारा जांचें कि आप सही `NumericFormat` उपयोग कर रहे हैं; `General` पूरी डबल सटीकता बनाए रखता है, जबकि `Flat` निर्दिष्ट दशमलव स्थानों तक राउंड करता है।  
- **SRID प्रदर्शित नहीं हो रहा** – केवल `ExtendedPostGis` वैरिएंट आउटपुट के पहले `SRID=` जोड़ता है। जब आपका लक्ष्य सिस्टम SRID की अपेक्षा करता है, तो इस वैरिएंट को चुनें।

## निष्कर्ष
इन चरणों का पालन करके अब आप जानते हैं कि **जियोमेट्री को WKT में कैसे बदलें**, सही वैरिएंट कैसे चुनें, और संख्यात्मक आउटपुट को सटीक रूप से कैसे नियंत्रित करें। यह आपको Aspose.GIS को किसी भी GIS वर्कफ़्लो, डेटाबेस या वेब सर्विस के साथ एकीकृत करने की लचीलापन देता है जो WKT को उपभोग करता है।

## अक्सर पूछे जाने वाले प्रश्न
### क्या Aspose.GIS सभी .NET संस्करणों के साथ संगत है?
हाँ, Aspose.GIS .NET Framework 4.0 और उससे ऊपर के संस्करणों का समर्थन करता है।  

### क्या मैं Aspose.GIS को वाणिज्यिक प्रोजेक्ट्स में उपयोग कर सकता हूँ?
हाँ, Aspose.GIS को व्यक्तिगत और वाणिज्यिक दोनों प्रकार के प्रोजेक्ट्स में उपयोग किया जा सकता है।  

### क्या Aspose.GIS अन्य स्थानिक डेटा फ़ॉर्मेट्स का समर्थन करता है?
हाँ, Aspose.GIS कई स्थानिक डेटा फ़ॉर्मेट्स का समर्थन करता है, जैसे ESRI Shapefile, GeoJSON, और KML।  

### क्या Aspose.GIS के लिए कोई मुफ्त ट्रायल उपलब्ध है?
हाँ, आप Aspose.GIS का मुफ्त ट्रायल संस्करण [here](https://releases.aspose.com/) से डाउनलोड कर सकते हैं।  

### Aspose.GIS के लिए सहायता या सपोर्ट कहाँ प्राप्त कर सकता हूँ?
आप अपने प्रश्न पोस्ट कर सकते हैं या Aspose.GIS समुदाय से सहायता प्राप्त कर सकते हैं [forum](https://forum.aspose.com/c/gis/33) पर।

## Frequently Asked Questions
**Q: मैं एक Geometry कलेक्शन को एकल WKT स्ट्रिंग में कैसे एक्सपोर्ट करूँ?**  
A: कलेक्शन में प्रत्येक जियोमेट्री पर इटररेट करें और उनके `AsText` परिणामों को जोड़ें, वैकल्पिक रूप से कॉमा या नई पंक्तियों से अलग करें।

**Q: क्या मैं SRID को बिना कोऑर्डिनेट्स बदले बदल सकता हूँ?**  
A: हाँ, `SpatialReferenceSystem` प्रॉपर्टी को इच्छित SRID पर सेट करें; कोऑर्डिनेट मान अपरिवर्तित रहेंगे।

**Q: यदि मैं असमर्थित WKT वैरिएंट उपयोग करता हूँ तो क्या होगा?**  
A: Aspose.GIS एक `ArgumentException` फेंकेगा। हमेशा `WktVariant` enum मानों के विरुद्ध वैरिएंट को वैध करें।

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}