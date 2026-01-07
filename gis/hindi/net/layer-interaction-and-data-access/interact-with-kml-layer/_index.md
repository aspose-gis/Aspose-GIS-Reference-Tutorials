---
date: 2026-01-07
description: Aspose.GIS for .NET का उपयोग करके KML फ़ाइल लिखना, KML बनाना, बूलियन
  एट्रिब्यूट जोड़ना, और अपने अनुप्रयोगों में लाइन स्ट्रिंग बनाना सीखें।
linktitle: Interact with KML Layer
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET के साथ KML फ़ाइल कैसे लिखें
url: /hi/net/layer-interaction-and-data-access/interact-with-kml-layer/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET के साथ KML फ़ाइल कैसे लिखें

## Introduction
आज के डेटा‑ड्रिवन संसार में, प्रोग्रामेटिक रूप से **write KML file** करने की क्षमता आपको विभिन्न प्लेटफ़ॉर्म पर भौगोलिक जानकारी साझा करने, मानचित्रों पर मार्गों को विज़ुअलाइज़ करने, और लोकेशन डेटा को वेब या मोबाइल ऐप्स में इंटीग्रेट करने की शक्ति देती है। Aspose.GIS for .NET इस प्रक्रिया को सरल बनाता है, जिससे आप फ़ाइल‑फ़ॉर्मेट की जटिलताओं के बजाय लॉजिक पर ध्यान केंद्रित कर सकते हैं। इस ट्यूटोरियल में हम KML लेयर बनाना, एट्रिब्यूट (जिसमें एक boolean एट्रिब्यूट भी शामिल है) जोड़ना, और लाइन स्ट्रिंग जियोमेट्री बनाना—सभी स्पष्ट, चरण‑दर‑चरण कोड के साथ—दिखाएंगे।

## Quick Answers
- **“write KML file” का क्या मतलब है?** एक KML (Keyhole Markup Language) दस्तावेज़ उत्पन्न करना जो बिंदु, रेखा और बहुभुज जैसी भौगोलिक विशेषताओं का वर्णन करता है।  
- **.NET के लिए कौन सी लाइब्रेरी सबसे अच्छी है?** Aspose.GIS for .NET KML फ़ाइलें बनाने और संपादित करने के लिए एक फ्लुएंट API प्रदान करती है।  
- **क्या विकास के लिए लाइसेंस चाहिए?** मूल्यांकन के लिए एक फ्री ट्रायल काम करता है; उत्पादन उपयोग के लिए लाइसेंस आवश्यक है।  
- **क्या मैं कस्टम एट्रिब्यूट जोड़ सकता हूँ?** हाँ – आप प्रत्येक फीचर में स्ट्रिंग, इंटीजर, boolean, और डबल एट्रिब्यूट जोड़ सकते हैं।  
- **क्या जियोमेट्री निर्माण समर्थित है?** बिल्कुल – आप पॉइंट, लाइन स्ट्रिंग, पॉलीगॉन और अधिक बना सकते हैं।

## Prerequisites
इस यात्रा को शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित प्री‑रिक्विज़िट्स मौजूद हैं:
- Aspose.GIS for .NET: लाइब्रेरी को [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/) से डाउनलोड और इंस्टॉल करें।  
- Development Environment: Visual Studio जैसे उपयुक्त विकास वातावरण को सेट अप करें, ताकि Aspose.GIS को आपके .NET प्रोजेक्ट्स में सहजता से इंटीग्रेट किया जा सके।

## Import Namespaces
KML लेयर्स के साथ काम शुरू करने से पहले, अपने प्रोजेक्ट में आवश्यक नेमस्पेस शामिल करना न भूलें। यह कदम सुनिश्चित करता है कि आपके पास जियोस्पेशियल डेटा मैनिपुलेशन के लिए आवश्यक क्लासेज़ और मेथड्स उपलब्ध हों।

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Drawing;
using System.Threading;
using Aspose.Gis.Formats.Kml;
using Aspose.Gis.Formats.Kml.Styles;
using Aspose.Gis.Geometries;
using Point = Aspose.Gis.Geometries.Point;
```

## Step 1: Set the Document Directory
KML फ़ाइलों को संग्रहीत करने वाले दस्तावेज़ डायरेक्टरी का पाथ परिभाषित करें।

```csharp
string dataDir = "Your Document Directory";
```

## Step 2: Create a KML Layer
Aspose.GIS का उपयोग करके एक KML लेयर इनिशियलाइज़ करें, और KML फ़ाइल के पाथ को निर्दिष्ट करें।

```csharp
using (var layer = Drivers.Kml.CreateLayer(dataDir + "Kml_File_out.kml"))
{
```

## Step 3: Define Attributes (add boolean attribute)
KML लेयर में विभिन्न डेटा टाइप्स जैसे स्ट्रिंग, इंटीजर, **boolean**, और डबल को दर्शाने वाले एट्रिब्यूट जोड़ें। यही वह जगह है जहाँ आप प्रत्येक फीचर में “add boolean attribute” करेंगे।

```csharp
layer.Attributes.Add(new FeatureAttribute("string_data", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("int_data", AttributeDataType.Integer));
layer.Attributes.Add(new FeatureAttribute("bool_data", AttributeDataType.Boolean));
layer.Attributes.Add(new FeatureAttribute("float_data", AttributeDataType.Double));
```

## Step 4: Construct and Populate Features (create line string)
भौगोलिक इकाइयों का प्रतिनिधित्व करने वाले फीचर बनाएं और परिभाषित एट्रिब्यूट्स के मान सेट करें। यहाँ हम **create line string** जियोमेट्री बनाते हैं ताकि एक सरल पाथ दर्शाया जा सके।

```csharp
Feature feature = layer.ConstructFeature();
feature.SetValue("string_data", "string value");
feature.SetValue("int_data", 10);
feature.SetValue("bool_data", true);
feature.SetValue("float_data", 3.14);
feature.Geometry = new LineString(new[] { new Point(0, 0), new Point(1, 1) });
layer.Add(feature);
```

## Step 5: Add Another Feature
दूसरा फीचर जोड़ने के लिए प्रक्रिया दोहराएँ, जिसमें अलग एट्रिब्यूट मान और एक null जियोमेट्री हो।

```csharp
Feature feature2 = layer.ConstructFeature();
feature2.SetValue("string_data", "string value2");
feature2.SetValue("int_data", 100);
feature2.SetValue("bool_data", false);
feature2.SetValue("float_data", 3.1415);
feature2.Geometry = Geometry.Null;
layer.Add(feature2);
```

## How to Write KML File – Putting It All Together
ऊपर बताए गए चरणों का पालन करके अब आपके पास एक पूरी तरह कार्यात्मक KML फ़ाइल है जिसमें कस्टम एट्रिब्यूट (एक boolean फ़्लैग सहित) और लाइन स्ट्रिंग जियोमेट्री शामिल है। आप परिणामी `Kml_File_out.kml` को Google Earth, ArcGIS, या किसी भी GIS व्यूअर में खोल सकते हैं जो KML को सपोर्ट करता है।

## Common Issues & Troubleshooting
- **File path errors** – सुनिश्चित करें कि `dataDir` आपके OS के अनुसार एक पाथ सेपरेटर (`\` या `/`) के साथ समाप्त हो।  
- **Missing license** – ट्रायल मूल्यांकन के लिए काम करता है, लेकिन अनलिमिटेड KML फ़ाइल लिखने के लिए लाइसेंस्ड संस्करण आवश्यक है।  
- **Null geometry** – `Geometry.Null` सेट करना उन फीचर्स के लिए इरादतन है जिनमें स्पैटियल डेटा नहीं है; यदि आपको हमेशा जियोमेट्री चाहिए तो इसे हटाएँ।

## Frequently Asked Questions
### क्या Aspose.GIS अन्य GIS फ़ॉर्मैट्स के साथ संगत है?
हाँ, Aspose.GIS विभिन्न GIS फ़ॉर्मैट्स को सपोर्ट करता है, जिसमें shapefile, GeoJSON, और KML शामिल हैं।

### क्या मैं Aspose.GIS द्वारा बनाए गए जियोस्पेशियल डेटा को विज़ुअलाइज़ कर सकता हूँ?
बिल्कुल! Aspose.GIS मैपिंग लाइब्रेरीज़ के साथ सहजता से इंटीग्रेट होता है, जिससे आप अपने जियोस्पेशियल डेटा को विज़ुअलाइज़ कर सकते हैं।

### क्या Aspose.GIS के लिए एक ट्रायल संस्करण उपलब्ध है?
हाँ, आप [free trial version](https://releases.aspose.com/) डाउनलोड करके Aspose.GIS की सुविधाओं का अन्वेषण कर सकते हैं।

### मैं Aspose.GIS के लिए सपोर्ट कैसे प्राप्त करूँ?
समुदाय समर्थन के लिए [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) देखें या प्रीमियम सपोर्ट विकल्पों के लिए [here](https://purchase.aspose.com/buy) पर जाएँ।

### क्या Aspose.GIS के लिए टेम्पररी लाइसेंस उपलब्ध हैं?
हाँ, आप टेम्पररी लाइसेंस [here](https://purchase.aspose.com/temporary-license/) से प्राप्त कर सकते हैं।

## Additional Frequently Asked Questions

**Q: कैसे मैं **how to create KML** फ़ाइलें कस्टम स्टाइलिंग के साथ बनाऊँ?**  
A: फीचर जोड़ने से पहले `Aspose.Gis.Formats.Kml.Styles` नेमस्पेस का उपयोग करके आइकन, लाइन कलर, और लेबल स्टाइल्स को परिभाषित करें।

**Q: क्या मैं बड़े KML फ़ाइलें प्रभावी ढंग से लिख सकता हूँ?**  
A: फीचर्स को बैच में लिखें और मेमोरी उपयोग कम रखने के लिए लेयर को समय‑समय पर फ्लश करें।

**Q: क्या Aspose.GIS .NET Core और .NET 6+ को सपोर्ट करता है?**  
A: हाँ, यह लाइब्रेरी पूरी तरह से .NET Core, .NET 5, और .NET 6 के साथ संगत है।

---

**Last Updated:** 2026-01-07  
**Tested With:** Aspose.GIS 24.10 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}