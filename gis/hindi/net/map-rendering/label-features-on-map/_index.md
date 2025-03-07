---
title: .NET के लिए Aspose.GIS के साथ फ़ीचर लेबलिंग में महारत हासिल करना
linktitle: मानचित्र पर विशेषताएँ लेबल करें
second_title: Aspose.GIS .NET एपीआई
description: .NET के लिए Aspose.GIS का अन्वेषण करें और मानचित्रों पर फीचर लेबलिंग की कला में महारत हासिल करें। अपने भू-स्थानिक विज़ुअलाइज़ेशन को सहजता से बढ़ाएं। #मान लीजिए #जीआईएस
weight: 11
url: /hi/net/map-rendering/label-features-on-map/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET के लिए Aspose.GIS के साथ फ़ीचर लेबलिंग में महारत हासिल करना

## परिचय
भू-स्थानिक डेटा विज़ुअलाइज़ेशन की दुनिया में, मानचित्र पर सुविधाओं को लेबल करना जानकारी को प्रभावी ढंग से संप्रेषित करने में महत्वपूर्ण भूमिका निभाता है। .NET के लिए Aspose.GIS इसे निर्बाध रूप से प्राप्त करने के लिए एक शक्तिशाली टूलकिट प्रदान करता है। इस ट्यूटोरियल में, हम Aspose.GIS का उपयोग करके मानचित्र पर बिंदुओं को लेबल करने के विभिन्न तरीकों का पता लगाएंगे, जो जानकारीपूर्ण लेबल के साथ आपके मानचित्र विज़ुअलाइज़ेशन को बढ़ाएंगे।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
- C# और .NET फ्रेमवर्क का कार्यसाधक ज्ञान।
-  .NET के लिए Aspose.GIS स्थापित। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/gis/net/).
- एक जियोजसन फ़ाइल जिसमें बिंदु डेटा होता है। यदि आपके पास एक नहीं है, तो आप परीक्षण के लिए एक नमूना फ़ाइल का उपयोग कर सकते हैं।
## नामस्थान आयात करें
अपने C# कोड में, सुनिश्चित करें कि आप Aspose.GIS के साथ काम करने के लिए आवश्यक नेमस्पेस आयात करते हैं:
```csharp
using System;
using System.Drawing;
using Aspose.Gis;
using Aspose.Gis.Rendering;
using Aspose.Gis.Rendering.Labelings;
using Aspose.Gis.Rendering.Symbolizers;
using Aspose.GIS.Examples.CSharp;
using FontStyle = Aspose.Gis.Rendering.Labelings.FontStyle;
```
अब, आइए चरण-दर-चरण मार्गदर्शिका प्रारूप में प्रत्येक उदाहरण को कई चरणों में विभाजित करें।
##  अंक लेबलिंग

### चरण 1: अपनी दस्तावेज़ निर्देशिका के लिए पथ सेट करें:
```csharp
string dataDir = "Your Document Directory";
```
### चरण 2: एक साधारण मार्कर प्रतीक के साथ एक मानचित्र बनाएं:
```csharp
using (var map = new Map(500, 200))
{
    var symbol = new SimpleMarker
    {
        FillColor = Color.LightGray,
        StrokeStyle = StrokeStyle.None
    };
    var labeling = new SimpleLabeling(labelAttribute: "name");
    // 3. एक वेक्टर परत जोड़ें और लेबलिंग लागू करें
    map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), symbol, labeling);
    map.Padding = 50;
    // 4. मानचित्र को SVG फ़ाइल में प्रस्तुत करें
    map.Render(dataDir + "points_labeling_out.svg", Renderers.Svg);
}
```
## पॉइंट लेबलिंग स्टाइल

पिछले उदाहरण से चरण 1 और 2 का पालन करें।

### चरण 1: लेबलिंग शैली को अनुकूलित करें:
```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 2,
    HaloColor = Color.LightGray,
    FontSize = 15,
    FontStyle = FontStyle.Italic,
};
// बाकी चरण वही रहेंगे
```
## पॉइंट लेबलिंग लगाई गई

पहले उदाहरण से चरण 1 और 2 का पालन करें।
### चरण 2: लेबल प्लेसमेंट को अनुकूलित करें:
```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 1,
    Placement = new PointLabelPlacement
    {
        VerticalAnchorPoint = VerticalAnchor.Bottom,
        HorizontalAnchorPoint = HorizontalAnchor.Left,
        HorizontalOffset = 2,
        VerticalOffset = 2,
        Rotation = 10,
    }
};
// बाकी चरण वही रहेंगे
```
## फ़ीचर आधारित पॉइंट लेबलिंग

पहले उदाहरण से चरण 1 और 2 का पालन करें।

### चरण 1: सुविधा-आधारित लेबलिंग लागू करें:
```csharp
var pointLabeling = new SimpleLabeling("name")
{
    HaloSize = 1,
    Placement = new PointLabelPlacement
    {
        VerticalAnchorPoint = VerticalAnchor.Bottom,
        HorizontalAnchorPoint = HorizontalAnchor.Left,
        VerticalOffset = 4,
        HorizontalOffset = 4,
    },
    FeatureBasedConfiguration = (feature, labeling) =>
    {
        // फ़ीचर से जनसंख्या पुनर्प्राप्त करें.
        var population = feature.GetValue<int>("population");
        // फ़ॉन्ट आकार की गणना की जाती है और यह जनसंख्या पर आधारित है।
        labeling.FontSize = Math.Min(20, 5 * population / 1000);
        // लेबल की प्राथमिकता जनसंख्या पर भी आधारित है।
        // प्राथमिकता जितनी अधिक होगी, आउटपुट छवि पर लेबल दिखाई देने की संभावना उतनी ही अधिक होगी।
        labeling.Priority = population;
    }
};
// बाकी चरण वही रहेंगे
```
## निष्कर्ष
बधाई हो! आपने सीखा है कि .NET के लिए Aspose.GIS का उपयोग करके सुविधाओं को लेबल करके अपने मानचित्र विज़ुअलाइज़ेशन को कैसे बढ़ाया जाए। अपने डेटा के अनुरूप आकर्षक मानचित्र बनाने के लिए विभिन्न शैलियों और प्लेसमेंट के साथ प्रयोग करें।
## पूछे जाने वाले प्रश्न
### क्या मैं कस्टम फ़ॉन्ट का उपयोग करके सुविधाओं को लेबल कर सकता हूँ?
हाँ, आप लेबलिंग कॉन्फ़िगरेशन में फ़ॉन्ट शैली और आकार को अनुकूलित कर सकते हैं।
### क्या Aspose.GIS अन्य GIS डेटा प्रारूपों के साथ संगत है?
Aspose.GIS विभिन्न भू-स्थानिक प्रारूपों का समर्थन करता है, जिसमें जियोजसन, शेपफाइल और बहुत कुछ शामिल हैं।
### मैं लेबलिंग के लिए बड़े डेटासेट कैसे संभाल सकता हूं?
Aspose.GIS को प्रदर्शन के लिए अनुकूलित किया गया है, लेकिन डेटा विशेषताओं के आधार पर लेबल को प्राथमिकता देने के लिए फीचर-आधारित कॉन्फ़िगरेशन का उपयोग करने पर विचार करें।
### क्या उन्नत लेबल प्लेसमेंट विकल्प उपलब्ध हैं?
हां, आप रोटेशन, एंकर पॉइंट और ऑफसेट जैसे विकल्पों का उपयोग करके लेबल प्लेसमेंट को ठीक कर सकते हैं।
### क्या मैं बैच प्रक्रिया में लेबल निर्माण को स्वचालित कर सकता हूँ?
बिल्कुल, आप बैच लेबल निर्माण के लिए Aspose.GIS को अपने स्वचालित वर्कफ़्लो में एकीकृत कर सकते हैं।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
