---
date: 2026-01-18
description: تعلم كيفية إضافة المدن إلى الخريطة وتوليد خريطة SVG باستخدام Aspose.GIS
  لـ .NET. أنشئ تصورات مذهلة بسرعة.
linktitle: Render a Map
second_title: Aspose.GIS .NET API
title: كيفية إضافة المدن إلى الخريطة باستخدام Aspose.GIS لـ .NET
url: /ar/net/map-rendering/render-a-map/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة المدن إلى الخريطة باستخدام Aspose.GIS لـ .NET

## المقدمة
مرحبًا بك في عالم Aspose.GIS لـ .NET المثير! في هذا الدليل خطوة بخطوة، ستتعلم **كيفية إضافة المدن إلى الخريطة** وتوليد مخرجات SVG عالية الجودة. سواءً كنت تبني لوحة تحكم سطح مكتب أو بوابة GIS على الويب، يوضح لك هذا الدرس كيفية رسم طبقات متجهة، تحديد أبعاد الخريطة، وتحميل خريطة GeoJSON بسهولة.

## الإجابات السريعة
- **ما الذي يغطيه هذا الدرس؟** إضافة المدن إلى الخريطة وتصديرها كملف SVG.  
- **ما المكتبة المطلوبة؟** Aspose.GIS لـ .NET.  
- **هل أحتاج إلى ترخيص؟** تتوفر نسخة تجريبية مجانية؛ يلزم وجود ترخيص للإنتاج.  
- **هل يمكنني استخدام هذا في تطبيقات الويب؟** نعم – يعمل نفس الكود في ASP.NET وBlazor وغيرها من أطر عمل .NET للويب.  
- **ما هو تنسيق الإخراج الناتج؟** خريطة SVG يمكن عرضها في المتصفحات أو تعديلها لاحقًا.

## المتطلبات المسبقة
قبل الغوص في الدرس، تأكد من توفر المتطلبات التالية:
- مكتبة Aspose.GIS لـ .NET: تأكد من تثبيت مكتبة Aspose.GIS لـ .NET. يمكنك تنزيلها [هنا](https://releases.aspose.com/gis/net/).
- ملفات البيانات: جهّز ملفات shapefile وبيانات GeoJSON اللازمة للدرس. يمكنك العثور على بيانات نموذجية في الوثائق أو استخدام ملفاتك الخاصة.
- بيئة التطوير: احرص على إعداد بيئة تطوير .NET، بما في ذلك محرر شفرة مثل Visual Studio.

## استيراد مساحات الأسماء
للبدء، استورد مساحات الأسماء المطلوبة في مشروع .NET الخاص بك. هذه المساحات ضرورية للعمل مع وظائف Aspose.GIS.

```csharp
using Aspose.Gis;
using Aspose.Gis.Rendering;
using Aspose.Gis.Rendering.Symbolizers;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.Drawing.Text;
using System.IO;
using System.Linq;
```

## الخطوة 1: إعداد الخريطة (تحديد أبعاد الخريطة)
```csharp
string dataDir = "Your Document Directory";
using (var map = new Map(800, 476))
{
    // Additional code for map setup can be added here.
}
```
في هذه الخطوة، نقوم بإنشاء خريطة جديدة بعرض 800 بكسل وارتفاع 476 بكسل. عدّل الأبعاد وفقًا لمتطلبات التصميم الخاصة بك.

## الخطوة 2: إضافة خريطة أساسية (رسم طبقة متجهة)
```csharp
var baseMapSymbolizer = new SimpleFill { FillColor = Color.Salmon, StrokeWidth = 0.75 };
map.Add(VectorLayer.Open(dataDir + "basemap.shp", Drivers.Shapefile), baseMapSymbolizer);
```
هنا، نقوم **برسم طبقة متجهة** للخريطة الأساسية باستخدام ملف shapefile. لا تتردد في تعديل خصائص `SimpleFill` لتتناسب مع النمط البصري الخاص بك.

## الخطوة 3: إضافة المدن إلى الخريطة (إضافة مدن إلى الخريطة، تحميل خريطة GeoJSON)
```csharp
var citiesSymbolizer = new SimpleMarker() { FillColor = Color.LightBlue };
citiesSymbolizer.FeatureBasedConfiguration = (feature, symbolizer) =>
{
    // Additional configuration logic can be added here.
};
map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), citiesSymbolizer);
```
في هذه الخطوة يتم تحميل ملف GeoJSON يحتوي على بيانات نقاط المدن و**إضافة المدن إلى الخريطة**. يمكنك تحسين المفوض `FeatureBasedConfiguration` لتنسيق المدن بناءً على سمات مثل عدد السكان.

## الخطوة 4: تصيير الخريطة (تصدير خريطة SVG، إنشاء خريطة SVG)
```csharp
map.Render(dataDir + "cities_out.svg", Renderers.Svg);
```
أخيرًا، نقوم **بتصدير الخريطة كملف SVG**. يمكن فتح الملف الناتج `cities_out.svg` في أي متصفح حديث أو محرر رسومات متجهة.

## الخاتمة
تهانينا! لقد نجحت في **إضافة المدن إلى الخريطة** وإنشاء خريطة SVG باستخدام Aspose.GIS لـ .NET. يوضح هذا الدرس كيفية تحديد أبعاد الخريطة، رسم طبقات متجهة، تحميل بيانات GeoJSON، وتصدير النتيجة كملف SVG قابل للتوسيع—مناسب لكل من سيناريوهات الويب والطباعة.

## الأسئلة المتكررة
### هل يمكنني استخدام Aspose.GIS لـ .NET في تطبيقاتي الويب؟
نعم، Aspose.GIS لـ .NET مناسب لكل من تطبيقات سطح المكتب والويب.

### هل تتوفر نسخة تجريبية؟
نعم، يمكنك استكشاف النسخة التجريبية المجانية [هنا](https://releases.aspose.com/).

### أين يمكنني العثور على الدعم لـ Aspose.GIS لـ .NET؟
قم بزيارة [منتدى Aspose.GIS](https://forum.aspose.com/c/gis/33) لأي مساعدة أو استفسارات.

### هل يمكنني شراء ترخيص مؤقت للمشروعات قصيرة الأجل؟
نعم، يتوفر ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

### هل هناك دروس إضافية متاحة لـ Aspose.GIS لـ .NET؟
نعم، تحقق من [الوثائق](https://reference.aspose.com/gis/net/) للحصول على دروس وشروحات شاملة.

---

**Last Updated:** 2026-01-18  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}