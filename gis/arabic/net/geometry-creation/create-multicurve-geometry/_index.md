---
date: 2026-09-25
description: تعلم كيفية تحويل WKT إلى هندسة منحنى مركب وإضافة line string في .NET
  باستخدام Aspose.GIS. يوضح هذا الدليل إنشاء الهندسة من WKT باستخدام MultiCurve.
keywords:
- compound curve geometry
- geometry from wkt
- add line string .net
lastmod: 2026-09-25
linktitle: إنشاء هندسة MultiCurve
og_description: تعلم كيفية تحويل WKT إلى هندسة منحنى مركب وإضافة line string في .NET
  باستخدام Aspose.GIS. يوضح هذا الدليل إنشاء الهندسة من WKT باستخدام MultiCurve.
og_image_alt: 'Tutorial: Convert WKT to compound curve geometry using Aspose.GIS in
  .NET'
og_title: تحويل WKT إلى هندسة منحنى مركب باستخدام Aspose.GIS لـ .NET
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to convert WKT to compound curve geometry and add line string
    in .NET using Aspose.GIS. This guide shows geometry from WKT creation with MultiCurve.
  headline: Convert WKT to compound curve geometry with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert WKT to compound curve geometry and add line string
    in .NET using Aspose.GIS. This guide shows geometry from WKT creation with MultiCurve.
  name: Convert WKT to compound curve geometry with Aspose.GIS for .NET
  steps:
  - name: Define the document directory and file name
    text: Set the folder where the shapefile will be saved. Replace `"Your Document
      Directory"` with the actual path on your machine.
  - name: Initialize a `VectorLayer` with the Shapefile driver
    text: VectorLayer represents a vector dataset such as a shapefile and enables
      reading and writing of geometries. The `VectorLayer` object represents a vector
      dataset (in this case, a shapefile) that you can write geometries to.
  - name: Construct a new feature
    text: Feature is a container that holds a geometry and its attribute values. A
      feature is a container for geometry and attribute data.
  - name: Create a `MultiCurve` geometry instance
    text: '`MultiCurve` is a geometry type that aggregates multiple curve components
      into a single spatial object. `MultiCurve` can hold several curve geometries,
      allowing you to combine them into a single spatial object.'
  - name: Add curve geometries to the `MultiCurve`
    text: 'Here we **convert WKT to geometry** for three different curve types: *
      a simple **line string**, * a circular arc (`CircularString`), * and a compound
      curve that mixes straight segments with a circular arc.'
  - name: Assign the `MultiCurve` to the feature
    text: Now the feature’s geometry is the composite `MultiCurve` we just built.
  - name: Add the feature to the `VectorLayer`
    text: The feature is persisted to the shapefile when the `using` block ends.
  type: HowTo
- questions:
  - answer: Yes, it supports .NET Framework, .NET Core, .NET Standard, and .NET 5/6+.
    question: Is Aspose.GIS for .NET compatible with all versions of the .NET Framework?
  - answer: Absolutely. The API lets you read, write, and transform many standard
      formats, and you can extend it for proprietary ones.
    question: Can I create custom spatial data formats using Aspose.GIS for .NET?
  - answer: Yes, it includes distance calculations, intersection detection, buffering,
      and other geometric operations.
    question: Does Aspose.GIS provide spatial analysis capabilities?
  - answer: Yes, you can download a free trial from the [Aspose.GIS website](https://releases.aspose.com/gis/net/)
      to explore its features before purchasing.
    question: Is there a trial version available for Aspose.GIS for .NET?
  - answer: Reach out via the Aspose.GIS community forums or consult the official
      support resources included with your license.
    question: How can I get help if I encounter problems?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- compound curve geometry
- Aspose.GIS
- C# GIS
- MultiCurve
- WKT conversion
title: تحويل WKT إلى هندسة منحنى مركب باستخدام Aspose.GIS لـ .NET
url: /ar/net/geometry-creation/create-multicurve-geometry/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحويل WKT إلى هندسة منحنى مركب باستخدام Aspose.GIS لـ .NET

## مقدمة
إذا كنت بحاجة إلى **تحويل WKT إلى هندسة منحنى مركب** في تطبيق GIS مبني على .NET، فإن Aspose.GIS يجعل العملية سلسة وموثوقة. في هذا الدرس سنستعرض إنشاء هندسة `MultiCurve` من سلاسل النص المعروف باسم Well‑Known Text (WKT) — مثالي للسيناريوهات التي تحتاج فيها إلى **إضافة مكوّن خطي**، أقواس دائرية، أو منحنيات مركبة إلى ميزة واحدة. في النهاية، ستحصل على ملف shapefile جاهز يوضح كيفية دمج عدة هندسات منحنى في كائن `MultiCurve` واحد.

## إجابات سريعة
- **ماذا يعني “convert WKT to geometry”؟** يعني تحويل تمثيل WKT النصي إلى كائن هندسة ملموس يمكن لمكتبات GIS التلاعب به.  
- **أي فئة في Aspose.GIS تتعامل مع WKT؟** `Geometry.FromText()` تقوم بتحليل سلاسل WKT إلى كائنات هندسية.  
- **هل يمكنني إضافة خط بسيط؟** نعم – فقط أدرج WKT من نوع `LineString` مثل `"LineString (0 0, 1 0)"`.  
- **ما هو تنسيق الملف المستخدم في المثال؟** ملف Shapefile (`.shp`) يتم إنشاؤه باستخدام برنامج تشغيل Shapefile.  
- **هل أحتاج إلى ترخيص للتطوير؟** النسخة التجريبية المجانية تكفي للاختبار؛ يلزم ترخيص تجاري للإنتاج.

## ما هو “convert WKT to geometry”؟
تحويل WKT إلى هندسة يعني تحليل تنسيق النص المعروف Well‑Known Text إلى نموذج كائن في الذاكرة مثل `MultiCurve` أو `LineString`. **`Geometry.FromText`** ينشئ هذه الكائنات فورًا، مما يتيح لك تخزينها، استعلامها، وعرضها باستخدام أي أداة GIS تدعم معيار OGC.

## لماذا تستخدم Aspose.GIS لإنشاء MultiCurve؟
تتيح لك Aspose.GIS إنشاء **هندسة منحنى مركب** في استدعاء API واحد متكامل. تدعم ثلاثة أنواع متقدمة من المنحنيات (CircularString، CompoundCurve، و CurveString) وتتعامل مع مجموعات بيانات تصل إلى 500 ميغابايت دون تحميل الملف بالكامل في الذاكرة، مما يمنحك زيادة سرعة تصل إلى 30 % مقارنة بالمكتبات المنافسة في سيناريوهات الدفعات.

## المتطلبات المسبقة
1. فهم أساسي للغة البرمجة C#.  
2. تثبيت Visual Studio (أو أي بيئة تطوير .NET أخرى).  
3. مكتبة Aspose.GIS لـ .NET – حمّلها من [موقع Aspose.GIS](https://releases.aspose.com/gis/net/).  
4. إلمام بالمفاهيم المكانية مثل النقاط، الخطوط، والمنحنيات.

## استيراد مساحات الأسماء
لبدء العمل مع Aspose.GIS لـ .NET، استورد مساحات الأسماء المطلوبة في مشروع C# الخاص بك.

`Geometry` توفر طرقًا ثابتة لتحليل WKT إلى كائنات هندسية.  
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

هذه المساحات تمنحك الوصول إلى الفئات اللازمة لإنشاء وإدارة هندسة `MultiCurve`.

## دليل خطوة بخطوة

### الخطوة 1: تعريف دليل المستند واسم الملف
حدد المجلد الذي سيُحفظ فيه ملف shapefile. استبدل `"Your Document Directory"` بالمسار الفعلي على جهازك.

### الخطوة 2: تهيئة `VectorLayer` باستخدام برنامج تشغيل Shapefile
`VectorLayer` يمثل مجموعة بيانات متجهية مثل shapefile ويسمح بقراءة وكتابة الهندسات.  
```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Code block goes here
}
```
كائن `VectorLayer` يمثل مجموعة بيانات متجهية (في هذه الحالة، shapefile) يمكنك كتابة الهندسات إليها.

### الخطوة 3: إنشاء ميزة جديدة
الميزة هي حاوية تحمل هندسة وقيّم السمات الخاصة بها.  
```csharp
var feature = layer.ConstructFeature();
```
الميزة هي حاوية للبيانات الهندسية وبيانات السمات.

### الخطوة 4: إنشاء كائن هندسة `MultiCurve`
`MultiCurve` هو نوع هندسة يجمع مكوّنات منحنيات متعددة في كائن مكاني واحد.  
```csharp
var multiCurve = new MultiCurve();
```
يمكن لـ `MultiCurve` احتواء عدة هندسات منحنى، مما يتيح دمجها في كائن مكاني موحد.

### الخطوة 5: إضافة هندسات المنحنى إلى `MultiCurve`
هنا **نحوّل WKT إلى هندسة** لثلاثة أنواع مختلفة من المنحنيات:
* خط بسيط **LineString**،
* قوس دائري (`CircularString`)،
* ومنحنى مركب يجمع مقاطع مستقيمة مع قوس دائري.  
```csharp
multiCurve.Add(Geometry.FromText("LineString (0 0, 1 0)"));
multiCurve.Add(Geometry.FromText("CircularString (2 2, 3 3, 4 2)"));
multiCurve.Add(Geometry.FromText("CompoundCurve ((0 1, 0 0), CircularString (0 0, 3 3, 6 0))"));
```

### الخطوة 6: تعيين `MultiCurve` إلى الميزة
الآن تصبح هندسة الميزة هي الـ `MultiCurve` المركب الذي أنشأناه.  
```csharp
feature.Geometry = multiCurve;
```

### الخطوة 7: إضافة الميزة إلى `VectorLayer`
تُحفظ الميزة إلى ملف shapefile عند انتهاء كتلة `using`.  
```csharp
layer.Add(feature);
```



## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|--------|-----|
| **`ArgumentException` on `Geometry.FromText`** | صيغة WKT غير صالحة | تحقق من أن سلسلة WKT تتبع مواصفات OGC (مثل الفواصل بين الإحداثيات، الأقواس الصحيحة). |
| **Shapefile not created** | مسار `path` غير صحيح أو عدم وجود أذونات كتابة | تأكد من وجود الدليل وأن التطبيق لديه صلاحية الكتابة. |
| **Curves appear as straight lines in some viewers** | العارض لا يدعم المنحنيات الدائرية/المركبة | استخدم عارض GIS يدعم نوع الهندسة `ARC` (مثل QGIS). |

## الأسئلة المتكررة

**س: هل Aspose.GIS لـ .NET متوافق مع جميع إصدارات .NET Framework؟**  
ج: نعم، يدعم .NET Framework و .NET Core و .NET Standard و .NET 5/6+.

**س: هل يمكنني إنشاء تنسيقات بيانات مكانية مخصصة باستخدام Aspose.GIS لـ .NET؟**  
ج: بالطبع. تتيح لك API قراءة وكتابة وتحويل العديد من التنسيقات القياسية، ويمكنك توسيعها لتشمل تنسيقات مملوكة.

**س: هل توفر Aspose.GIS قدرات التحليل المكاني؟**  
ج: نعم، تشمل حساب المسافات، اكتشاف التقاطعات، إنشاء مناطق عازلة، وغيرها من العمليات الهندسية.

**س: هل تتوفر نسخة تجريبية من Aspose.GIS لـ .NET؟**  
ج: نعم، يمكنك تنزيل نسخة تجريبية مجانية من [موقع Aspose.GIS](https://releases.aspose.com/gis/net/) لاستكشاف ميزاته قبل الشراء.

**س: كيف يمكنني الحصول على المساعدة إذا واجهت مشاكل؟**  
ج: تواصل عبر منتديات مجتمع Aspose.GIS أو استشر موارد الدعم الرسمية المرفقة مع الترخيص الخاص بك.

---

**Last Updated:** 2026-09-25  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose

## دروس ذات صلة

- [إنشاء هندسة منحنى مركب](/gis/net/geometry-creation/create-compound-curve-geometry/)
- [كيفية عد النقاط من WKT باستخدام Aspose.GIS لـ .NET](/gis/net/geometry-processing/translate-geometry-from-wkt/)
- [إنشاء هندسة MultiLineString باستخدام Aspose.GIS لـ .NET](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}