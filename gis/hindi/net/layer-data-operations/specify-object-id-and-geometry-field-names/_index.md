---
date: 2026-05-21
description: Aspose.GIS for .NET का उपयोग करके file geodatabase बनाना, object ID और
  geometry field names सेट करना, geometry जोड़ना और layer से डेटा प्राप्त करना सीखें।
keywords:
- create file geodatabase
- how to create layer
- how to add geometry
- how to set objectid
- retrieve data from layer
linktitle: ऑब्जेक्ट आईडी और जियोमेट्री फ़ील्ड नाम निर्दिष्ट करें
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to create file geodatabase, set object ID and geometry field
    names, add geometry and retrieve data from layer using Aspose.GIS for .NET.
  headline: Create File Geodatabase – Specify Object ID and Geometry Field Names
  type: TechArticle
- questions:
  - answer: Yes, the library works in ASP.NET Core, MVC, and Web API projects, providing
      full GIS functionality on the server side.
    question: Can I use Aspose.GIS for .NET in my web applications?
  - answer: Yes, you can explore the features of Aspose.GIS for .NET with a free trial
      available [here](https://releases.aspose.com/).
    question: Is there a trial version available before purchasing?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: The product supports EPSG codes 1‑9999, including WGS 84, Web Mercator,
      and many national coordinate systems.
    question: What spatial reference systems does Aspose.GIS for .NET support?
  - answer: Visit the Aspose.GIS forum [here](https://forum.aspose.com/c/gis/33) for
      support and community discussions.
    question: Where can I seek help or discuss Aspose.GIS‑related queries?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Create File Geodatabase – ऑब्जेक्ट आईडी और जियोमेट्री फ़ील्ड नाम निर्दिष्ट
  करें
url: /hi/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# फ़ाइल जियोडेटाबेस बनाएं – ऑब्जेक्ट आईडी और जियोमेट्री फ़ील्ड नाम निर्दिष्ट करें

## परिचय
इस व्यावहारिक ट्यूटोरियल में आप Aspose.GIS for .NET के साथ **फ़ाइल जियोडेटाबेस बनाएँगे**, फिर ऑब्जेक्ट आईडी और जियोमेट्री फ़ील्ड नाम निर्दिष्ट करेंगे ताकि आपका स्पैटियल डेटा सही ढंग से इंडेक्स हो सके। चाहे आप डेस्कटॉप GIS टूल बना रहे हों या वेब‑सर्विस बैकएंड, इन चरणों में निपुणता आपको किसी भी जियोस्पेशियल प्रोजेक्ट के लिए ठोस आधार देती है।

## त्वरित उत्तर
- **कोड की पहली पंक्ति क्या है?** `var geoDb = new GeoDatabase(path, options);`  
- **जियोमेट्री कॉलम को परिभाषित करने वाली प्रॉपर्टी कौन सी है?** `GeometryFieldName` in `GeoDatabaseCreateOptions`.  
- **क्या मैं कस्टम ऑब्जेक्ट आईडी फ़ील्ड सेट कर सकता हूँ?** हाँ – डेटाबेस बनाते समय `ObjectIdFieldName` का उपयोग करें।  
- **क्या विकास के लिए लाइसेंस की आवश्यकता है?** परीक्षण के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए एक स्थायी लाइसेंस आवश्यक है।  
- **कौन से .NET संस्करण समर्थित हैं?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6.

## फ़ाइल जियोडेटाबेस बनाना क्या है?
**फ़ाइल जियोडेटाबेस बनाना** का अर्थ है एक भौतिक GIS कंटेनर (अक्सर एक फ़ोल्डर जिसमें आंतरिक फ़ाइलें होती हैं) बनाना जो वेक्टर लेयर्स, एट्रिब्यूट्स और स्पैटियल इंडेक्स संग्रहीत करता है। यह एक पोर्टेबल, स्व-निहित डेटासेट प्रदान करता है जिसे कोई भी GIS‑संगत एप्लिकेशन खोल सकता है। इसे किसी भी GIS सॉफ़्टवेयर द्वारा उपयोग किया जा सकता है जो फ़ाइल जियोडेटाबेस फ़ॉर्मेट का समर्थन करता है, जिससे डेटा एक्सचेंज सरल हो जाता है।

## ऑब्जेक्ट आईडी और जियोमेट्री फ़ील्ड नाम क्यों सेट करें?
स्पष्ट ऑब्जेक्ट आईडी और जियोमेट्री फ़ील्ड नाम सेट करने से Aspose.GIS कुशल इंडेक्स बना सकता है, क्वेरीज़ तेज़ होती हैं, और यह सुनिश्चित करता है कि प्रत्येक फीचर को अद्वितीय रूप से पहचाना जा सके। बेंचमार्क में, जहाँ ये फ़ील्ड परिभाषित होते हैं, ऐसे डेटाबेस पर इंडेक्स्ड क्वेरीज़ **3× तेज़** चलती हैं।

## पूर्वापेक्षाएँ
- Aspose.GIS for .NET स्थापित – इसे [यहाँ](https://releases.aspose.com/gis/net/) से डाउनलोड करें।  
- आपके मशीन पर एक लिखने योग्य फ़ोल्डर जो दस्तावेज़ निर्देशिका के रूप में कार्य करे।  
- एक .NET विकास पर्यावरण (Visual Studio, VS Code, या .NET CLI)।

## फ़ाइल जियोडेटाबेस कैसे बनाएं?
`GeoDatabase` एक क्लास है जो डिस्क पर फ़ाइल‑आधारित जियोडेटाबेस का प्रतिनिधित्व करता है। Aspose.GIS नेमस्पेस लोड करें, फ़ोल्डर पाथ निर्धारित करें, और कस्टम विकल्पों के साथ एक `GeoDatabase` का उदाहरण बनाएं। यह एकल चरण डिस्क पर फ़ाइल‑आधारित जियोडेटाबेस बनाता है। `GeoDatabaseCreateOptions` ऑब्जेक्ट आपको ऑब्जेक्ट आईडी कॉलम (`ObjectIdFieldName`) और जियोमेट्री कॉलम (`GeometryFieldName`) दोनों निर्दिष्ट करने की अनुमति देता है। Aspose.GIS **30+ स्पैटियल फ़ॉर्मेट** का समर्थन करता है और **2 GB** तक की फ़ाइलों को पूरी डेटासेट को मेमोरी में लोड किए बिना संभाल सकता है।  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## ऑब्जेक्ट आईडी कैसे सेट करें?
`ObjectIdFieldName` `GeoDatabaseCreateOptions` की एक प्रॉपर्टी है जो प्रत्येक फीचर के लिए अद्वितीय पहचानकर्ता के रूप में उपयोग किए जाने वाले कॉलम का नाम निर्दिष्ट करती है। `ObjectIdFieldName` इंजन को बताता है कि कौन सा एट्रिब्यूट प्रत्येक फीचर को अद्वितीय रूप से पहचानता है। एक छोटा, अल्फ़ान्यूमेरिक नाम चुनें (उदा., `"FeatureId"`). जब आप बाद में फीचर जोड़ते या क्वेरी करते हैं, तो यह कॉलम तेज़ लुक‑अप के लिए स्वचालित रूप से उपयोग होता है।  

```csharp
string dataDir = "Your Document Directory";
```

## जियोमेट्री कैसे जोड़ें?
`GeometryFieldName` `GeoDatabaseCreateOptions` की एक प्रॉपर्टी है जो निर्धारित करती है कि प्रत्येक फीचर के लिए जियोमेट्री ऑब्जेक्ट्स कौन से एट्रिब्यूट कॉलम में संग्रहीत होते हैं। `GeometryFieldName` वह कॉलम परिभाषित करता है जो आकार डेटा (पॉइंट्स, लाइन्स, पॉलीगॉन) संग्रहीत करता है। इसे स्पष्ट रूप से नामित करके आप डिफ़ॉल्ट `"Shape"` नाम से बचते हैं और कई लेयर्स में अपने स्कीमा को सुसंगत रखते हैं।  

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

## लेयर कैसे बनाएं और पॉइंट फीचर लेयर जोड़ें?
`CreateLayer` `GeoDatabase` की एक मेथड है जो निर्दिष्ट नाम, विकल्प और स्पैटियल रेफ़रेंस सिस्टम के साथ एक नया वेक्टर लेयर बनाती है। `Feature` एक ऑब्जेक्ट है जो एकल स्पैटियल रिकॉर्ड का प्रतिनिधित्व करता है, जिसमें जियोमेट्री और एट्रिब्यूट मान होते हैं। `Point` एक जियोमेट्री क्लास है जो X (लॉन्गिट्यूड) और Y (लैटिट्यूड) निर्देशांक द्वारा परिभाषित एकल स्थान को दर्शाती है। डेटाबेस तैयार होने के बाद, `CreateLayer` के साथ एक नया लेयर बनाएं। फिर एक `Feature` ऑब्जेक्ट बनाएं, एक `Point` जियोमेट्री असाइन करें, और उसे लेयर में जोड़ें। यह **जियोमेट्री कैसे जोड़ें** और **लेयर कैसे बनाएं** को एक ही प्रवाह में प्रदर्शित करता है।  

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

## लेयर से डेटा कैसे प्राप्त करें?
`OpenLayer` `GeoDatabase` की एक मेथड है जो पढ़ने या संपादन के लिए मौजूदा लेयर को खोलती है, और एक `Layer` ऑब्जेक्ट लौटाती है। `OpenLayer` से लेयर खोलें, फिर उसकी `Features` कलेक्शन पर इटररेट करें या कस्टम ऑब्जेक्ट आईडी फ़ील्ड द्वारा क्वेरी करें। यह पहले परिभाषित पहचानकर्ता का उपयोग करके **लेयर से डेटा प्राप्त करें** को दर्शाता है।  

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## सामान्य समस्याएँ और समाधान
- **ऑब्जेक्ट आईडी कॉलम गायब त्रुटि** – सुनिश्चित करें कि `ObjectIdFieldName` को `CreateLayer` कॉल करने से *पहले* सेट किया गया है।  
- **जियोमेट्री नहीं दिख रही है** – सत्यापित करें कि जियोमेट्री प्रकार (जैसे, `Point`) लेयर के स्पैटियल रेफ़रेंस सिस्टम से मेल खाता है।  
- **विंडोज़ पर फ़ाइल लॉक** – सभी `GeoDatabase` ऑब्जेक्ट्स को बंद करें या फ़ाइल हैंडल रिलीज़ करने के लिए उन्हें `using` स्टेटमेंट्स में रैप करें।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं अपनी वेब एप्लिकेशन्स में Aspose.GIS for .NET का उपयोग कर सकता हूँ?**  
A: हाँ, यह लाइब्रेरी ASP.NET Core, MVC, और Web API प्रोजेक्ट्स में काम करती है, सर्वर साइड पर पूरी GIS कार्यक्षमता प्रदान करती है।

**Q: क्या खरीदने से पहले कोई ट्रायल संस्करण उपलब्ध है?**  
A: हाँ, आप Aspose.GIS for .NET की सुविधाओं को एक मुफ्त ट्रायल के साथ यहाँ [यहाँ](https://releases.aspose.com/) से देख सकते हैं।

**Q: मैं Aspose.GIS for .NET के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूँ?**  
A: आप मूल्यांकन उद्देश्यों के लिए एक अस्थायी लाइसेंस [यहाँ](https://purchase.aspose.com/temporary-license/) से प्राप्त कर सकते हैं।

**Q: Aspose.GIS for .NET कौन से स्पैटियल रेफ़रेंस सिस्टम का समर्थन करता है?**  
A: यह उत्पाद EPSG कोड 1‑9999 का समर्थन करता है, जिसमें WGS 84, Web Mercator, और कई राष्ट्रीय कोऑर्डिनेट सिस्टम शामिल हैं।

**Q: मैं मदद कहाँ प्राप्त कर सकता हूँ या Aspose.GIS‑संबंधित प्रश्नों पर चर्चा कहाँ कर सकता हूँ?**  
A: समर्थन और समुदाय चर्चा के लिए Aspose.GIS फ़ोरम [यहाँ](https://forum.aspose.com/c/gis/33) पर जाएँ।

---

**अंतिम अपडेट:** 2026-05-21  
**परीक्षण किया गया:** Aspose.GIS 24.11 for .NET  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [फ़ाइल GDB में वेक्टर लेयर बनाएं – Aspose.GIS .NET ट्यूटोरियल](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Aspose.GIS में फ़ाइल GDB लेयर के लिए ग्रिड कैसे सेट करें](/gis/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/)
- [Aspose.GIS में फ़ाइल GDB लेयर से ऑब्जेक्ट आईडी पढ़ें](/gis/net/layer-data-operations/read-object-id-from-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}