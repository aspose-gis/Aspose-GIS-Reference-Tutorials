---
title: إتقان تصنيف الميزات باستخدام Aspose.GIS لـ .NET
linktitle: ميزات التسمية على الخريطة
second_title: Aspose.GIS .NET API
description: استكشف Aspose.GIS for .NET وأتقن فن وضع العلامات على الميزات على الخرائط. تعزيز تصوراتك الجغرافية المكانية دون عناء. #Aspose #GIS
type: docs
weight: 11
url: /ar/net/map-rendering/label-features-on-map/
---
## مقدمة
في عالم تصور البيانات الجغرافية المكانية، تلعب ميزات وضع العلامات على الخريطة دورًا حاسمًا في نقل المعلومات بشكل فعال. يوفر Aspose.GIS for .NET مجموعة أدوات قوية لتحقيق ذلك بسلاسة. في هذا البرنامج التعليمي، سوف نستكشف طرقًا مختلفة لوضع العلامات على النقاط على الخريطة باستخدام Aspose.GIS، مما يعزز تصورات الخريطة باستخدام تسميات إعلامية.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- معرفة عملية بـ C# وإطار عمل .NET.
-  تم تثبيت Aspose.GIS لـ .NET. يمكنك تنزيله[هنا](https://releases.aspose.com/gis/net/).
- ملف GeoJSON يحتوي على بيانات النقطة. إذا لم يكن لديك واحد، يمكنك استخدام ملف عينة للاختبار.
## استيراد مساحات الأسماء
في كود C# الخاص بك، تأكد من استيراد مساحات الأسماء اللازمة للعمل مع Aspose.GIS:
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
الآن، دعونا نقسم كل مثال إلى خطوات متعددة بتنسيق دليل خطوة بخطوة.
##  وضع العلامات على النقاط

### الخطوة 1: قم بتعيين المسار إلى دليل المستندات الخاص بك:
```csharp
string dataDir = "Your Document Directory";
```
### الخطوة 2: إنشاء خريطة برمز علامة بسيط:
```csharp
using (var map = new Map(500, 200))
{
    var symbol = new SimpleMarker
    {
        FillColor = Color.LightGray,
        StrokeStyle = StrokeStyle.None
    };
    var labeling = new SimpleLabeling(labelAttribute: "name");
    // 3. أضف طبقة متجهة وقم بتطبيق العلامات
    map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), symbol, labeling);
    map.Padding = 50;
    // 4. اعرض الخريطة إلى ملف SVG
    map.Render(dataDir + "points_labeling_out.svg", Renderers.Svg);
}
```
## وضع العلامات على النقاط

اتبع الخطوتين 1 و2 من المثال السابق.

### الخطوة 1: تخصيص نمط وضع العلامات:
```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 2,
    HaloColor = Color.LightGray,
    FontSize = 15,
    FontStyle = FontStyle.Italic,
};
// تبقى بقية الخطوات كما هي
```
## تم وضع العلامات على النقاط

اتبع الخطوتين 1 و2 من المثال الأول.
### الخطوة 2: تخصيص موضع التسمية:
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
// تبقى بقية الخطوات كما هي
```
## ميزة تصنيف النقاط على أساس

اتبع الخطوتين 1 و2 من المثال الأول.

### الخطوة 1: تنفيذ التصنيف على أساس الميزات:
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
        // استرداد السكان من الميزة.
        var population = feature.GetValue<int>("population");
        // يتم حساب حجم الخط ويعتمد على عدد السكان.
        labeling.FontSize = Math.Min(20, 5 * population / 1000);
        // تعتمد أولوية التسمية أيضًا على عدد السكان.
        // كلما كانت الأولوية أكبر، ستظهر التسمية الأكثر احتمالية على الصورة الناتجة.
        labeling.Priority = population;
    }
};
// تبقى بقية الخطوات كما هي
```
## خاتمة
تهانينا! لقد تعلمت كيفية تحسين تصورات الخريطة الخاصة بك عن طريق تسمية الميزات باستخدام Aspose.GIS for .NET. قم بتجربة أنماط ومواضع مختلفة لإنشاء خرائط جذابة مصممة خصيصًا لبياناتك.
## الأسئلة الشائعة
### هل يمكنني تصنيف الميزات باستخدام خطوط مخصصة؟
نعم، يمكنك تخصيص نمط الخط وحجمه في تكوين التصنيف.
### هل Aspose.GIS متوافق مع تنسيقات بيانات GIS الأخرى؟
يدعم Aspose.GIS العديد من التنسيقات الجغرافية المكانية، بما في ذلك GeoJSON وShapefile والمزيد.
### كيف يمكنني التعامل مع مجموعات البيانات الكبيرة لوضع العلامات عليها؟
تم تحسين Aspose.GIS للأداء، ولكن فكر في استخدام التكوينات القائمة على الميزات لتحديد أولويات التسميات بناءً على سمات البيانات.
### هل تتوفر خيارات متقدمة لوضع الملصقات؟
نعم، يمكنك ضبط موضع التسمية باستخدام خيارات مثل التدوير ونقاط الربط والإزاحات.
### هل يمكنني أتمتة عملية إنشاء الملصقات في عملية مجمعة؟
بالتأكيد، يمكنك دمج Aspose.GIS في سير العمل الآلي الخاص بك لإنشاء الملصقات المجمعة.