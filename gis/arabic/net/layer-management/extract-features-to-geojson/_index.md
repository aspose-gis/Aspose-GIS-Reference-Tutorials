---
date: 2026-07-05
description: تعلم كيفية تحويل shapefile إلى geojson باستخدام Aspose.GIS لـ .NET. يغطي
  الدليل أيضًا نسخ السمات بين الطبقات وتوليد ملف geojson باستخدام c#.
keywords:
- convert shapefile to geojson
- export shapefile as geojson
- aspose gis conversion
- read shapefile c#
- write geojson c#
linktitle: استخراج الميزات إلى GeoJSON
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  headline: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  name: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  steps:
  - name: Open Input Shapefile
    text: The `VectorLayer.Open` method reads a Shapefile and returns an enumerable
      collection of `Feature` objects that you can iterate over.
  - name: Create Output GeoJSON
    text: '`VectorLayer.Create` with the `Drivers.GeoJson` driver creates an empty
      GeoJSON file ready to receive features.'
  - name: Copy Attributes Between Layers
    text: '`CopyAttributes` copies the attribute schema (field names and data types)
      from the source Shapefile to the new GeoJSON layer in a single call.'
  - name: Process Features
    text: Iterate through each feature in the Shapefile so you can apply any custom
      logic before writing it out.
  - name: Filter Features by Date
    text: In this example we skip records whose `dob` (date of birth) field is missing
      or earlier than 1 Jan 1982. Adjust the filter to match your own data requirements.
  - name: Construct a New Feature (C# Generate GeoJSON File)
    text: A `Feature` represents a single spatial element containing geometry and
      attribute data. Here we build a new `Feature` for the GeoJSON layer, copy the
      geometry and attribute values, and add it to the output. This is the core of
      *c# generate geojson file*. Congratulations! You’ve successfully **conver
  type: HowTo
- questions:
  - answer: Visit the [Aspose.GIS documentation](https://reference.aspose.com/gis/net/)
      for in‑depth information.
    question: Where can I find more documentation?
  - answer: You can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I get a temporary license?
  - answer: Join the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I seek support?
  - answer: Yes, you can find the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: You can buy the product [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: تحويل Shapefile إلى GeoJSON باستخدام Aspose.GIS لـ .NET
url: /ar/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحويل ملف Shapefile إلى GeoJSON باستخدام Aspose.GIS لـ .NET

## مقدمة
في هذا الدرس الشامل خطوة بخطوة ستتعلم **كيفية تحويل shapefile إلى geojson** باستخدام مكتبة Aspose.GIS القوية لـ .NET. سواءً كنت تبني خدمة ويب للخرائط، أو تُعد بيانات لتطبيق GIS على الجوال، أو تحتاج ببساطة إلى تبادل البيانات بين الصيغ، يوضح لك هذا الدليل ما يجب فعله، ولماذا كل خطوة مهمة، وكيفية تجنب الأخطاء الشائعة.

## إجابات سريعة
- **ما الذي يغطيه هذا الدرس؟** تحويل Shapefile إلى ملف GeoJSON، نسخ السمات بين الطبقات، وإنشاء المخرجات باستخدام C#.
- **ما المكتبة المطلوبة؟** Aspose.GIS لـ .NET.
- **هل أحتاج إلى ترخيص؟** يتطلب ترخيص مؤقت أو كامل للإنتاج؛ النسخة التجريبية المجانية تكفي للتقييم.
- **كم من الوقت تستغرق العملية؟** حوالي 10‑15 دقيقة للتحويل الأساسي.
- **هل يمكن تشغيله على .NET Core/.NET 6؟** نعم – الكود يعمل على جميع إصدارات .NET المدعومة.

## ما هو تحويل Shapefile إلى GeoJSON؟
تحويل Shapefile إلى GeoJSON يعني قراءة الكائنات المتجهة من صيغة ESRI Shapefile الكلاسيكية وكتابتها كوثيقة GeoJSON حديثة صديقة للويب. يتيح لك هذا التحويل إدخال بيانات GIS مباشرةً في مكتبات رسم الخرائط JavaScript مثل Leaflet أو Mapbox GL، ويُبسّط تبادل البيانات بين أدوات GIS المكتبية وواجهات برمجة التطبيقات الويب.

## لماذا نستخدم Aspose.GIS لهذا التحويل؟
تُجرد Aspose.GIS عملية التحليل الثنائي منخفض المستوى، وتدعم أكثر من 50 صيغة إدخال وإخراج، ويمكنها معالجة مجموعات بيانات مئات الصفحات دون تحميل الملف بالكامل في الذاكرة. كما توفر المكتبة واجهة برمجة تطبيقات كائنية نظيفة تعمل عبر .NET Framework و .NET Core و .NET 5/6، مما يتيح لك التركيز على منطق الأعمال بدلاً من تفاصيل الصيغ.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من وجود ما يلي:

- Aspose.GIS لـ .NET: تأكد من تثبيت المكتبة. إذا لم تكن مثبتة، يمكنك تنزيلها من [صفحة Aspose.GIS لـ .NET](https://releases.aspose.com/gis/net/).
- بيانات Shapefile: احرص على وجود ملف Shapefile جاهز للإدخال. إذا كنت تحتاج إلى بيانات نموذجية، يمكنك العثور عليها في [توثيق Aspose.GIS](https://reference.aspose.com/gis/net/).
- بيئة .NET: قم بإعداد بيئة .NET لتشغيل الكود المقدم.
- دليل المستندات: عرّف المسار إلى دليل المستندات الخاص بك في مقتطف الكود.

الآن بعد أن أصبحت كل الأمور جاهزة، لنبدأ بتحويل Shapefile إلى GeoJSON!

## كيفية تحويل Shapefile إلى GeoJSON
حمّل Shapefile المصدر، أنشئ طبقة GeoJSON هدف، انسخ مخطط السمات، صَفِّ السجلات، واكتب النتائج—كل ذلك في بضع خطوات مختصرة. يتناسب سير العمل الكامل بسهولة داخل كتلة `using` واحدة، مما يضمن تحرير الموارد تلقائيًا.

### الخطوة 1: فتح ملف Shapefile الإدخالي
طريقة `VectorLayer.Open` تقرأ Shapefile وتعيد مجموعة قابلة للتعداد من كائنات `Feature` التي يمكنك التكرار عليها.

```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```

### الخطوة 2: إنشاء ملف GeoJSON الناتج
`VectorLayer.Create` مع السائق `Drivers.GeoJson` ينشئ ملف GeoJSON فارغ جاهز لاستقبال الكائنات.

```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```

### الخطوة 3: نسخ السمات بين الطبقات
`CopyAttributes` ينسخ مخطط السمات (أسماء الحقول وأنواع البيانات) من Shapefile المصدر إلى طبقة GeoJSON الجديدة في مكالمة واحدة.

```csharp
outputLayer.CopyAttributes(inputLayer);
```

### الخطوة 4: معالجة الكائنات
تكرّر عبر كل كائن في Shapefile حتى تتمكن من تطبيق أي منطق مخصص قبل كتابته.

```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```

### الخطوة 5: تصفية الكائنات حسب التاريخ
في هذا المثال نتخطى السجلات التي يكون حقل `dob` (تاريخ الميلاد) فيها مفقودًا أو أقدم من 1 يناير 1982. عدّل الفلتر ليتناسب مع متطلبات بياناتك الخاصة.

```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```

### الخطوة 6: إنشاء كائن Feature جديد (C# إنشاء ملف GeoJSON)
`Feature` يمثل عنصرًا مكانيًا واحدًا يحتوي على الهندسة وبيانات السمات.  
هنا نبني `Feature` جديد لطبقة GeoJSON، ننسخ الهندسة وقيم السمات، ونضيفه إلى المخرج. هذا هو جوهر *c# generate geojson file*.

```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```

تهانينا! لقد نجحت في **تحويل Shapefile إلى GeoJSON** وتعلمت كيفية **نسخ السمات بين الطبقات** على طول الطريق.

## المشكلات الشائعة والحلول
| المشكلة | سبب حدوثها | الحل |
|-------|----------------|-----|
| ملف الإخراج فارغ | تم استدعاء `CopyAttributes` بعد إغلاق طبقة الإخراج | تأكد من بقاء كتلة `using` الخاصة بـ `outputLayer` مفتوحة حتى بعد إضافة جميع الكائنات. |
| تصفية التاريخ تزيل جميع السجلات | اسم الحقل غير صحيح أو تنسيق تاريخ غير متوقع | تحقق من اسم السمة (`dob`) واستخدم `GetValue<string>` إذا كانت التواريخ مخزنة كسلاسل نصية. |
| استثناء الترخيص | تشغيل بدون ترخيص Aspose.GIS صالح في بيئة الإنتاج | طبق ترخيصًا مؤقتًا أو كاملًا كما هو موضح في وثائق Aspose. |

## الأسئلة المتكررة
**س: أين يمكنني العثور على مزيد من الوثائق؟**  
ج: زر [توثيق Aspose.GIS](https://reference.aspose.com/gis/net/) للحصول على معلومات متعمقة.

**س: كيف يمكنني الحصول على ترخيص مؤقت؟**  
ج: يمكنك الحصول على ترخيص مؤقت [من هنا](https://purchase.aspose.com/temporary-license/).

**س: أين يمكنني طلب الدعم؟**  
ج: انضم إلى [منتدى Aspose.GIS](https://forum.aspose.com/c/gis/33) للحصول على دعم المجتمع والنقاشات.

**س: هل هناك نسخة تجريبية مجانية متاحة؟**  
ج: نعم، يمكنك العثور على النسخة التجريبية [من هنا](https://releases.aspose.com/).

**س: أين يمكنني شراء Aspose.GIS لـ .NET؟**  
ج: يمكنك شراء المنتج [من هنا](https://purchase.aspose.com/buy).

## الخاتمة
في هذا الدرس استعرضنا العملية الكاملة لـ **تحويل Shapefile إلى GeoJSON** باستخدام Aspose.GIS لـ .NET، وأظهرنا كيفية **نسخ السمات بين الطبقات**، وبيّنّا طريقة نظيفة لـ *c# generate geojson file*. جرّب فلاتر مختلفة، مجموعات بيانات أكبر، أو تحويلات هندسية إضافية لاستغلال إمكانات المكتبة بالكامل.

---

**آخر تحديث:** 2026-07-05  
**تم الاختبار مع:** Aspose.GIS لـ .NET (أحدث إصدار ثابت)  
**المؤلف:** Aspose

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## دروس ذات صلة

- [كيفية تحويل GeoJSON إلى File GDB باستخدام Aspose.GIS لـ .NET](/gis/net/layer-management/convert-geojson-layer-to-file-gdb/)
- [كيفية قراءة GeoJSON من Stream باستخدام Aspose.GIS لـ .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [كيفية تحويل GeoJSON إلى TopoJSON باستخدام Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}