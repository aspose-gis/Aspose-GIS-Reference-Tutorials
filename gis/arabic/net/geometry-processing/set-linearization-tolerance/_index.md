---
date: 2025-12-21
description: تعلم كيفية إنشاء طبقة متجهة، وضبط تسامح الخطية، وإضافة عنصر إلى الطبقة
  باستخدام Aspose.GIS لـ .NET. اتبع هذا الدليل خطوة بخطوة لتصدير ملفات GeoJSON.
linktitle: Set Linearization Tolerance
second_title: Aspose.GIS .NET API
title: إنشاء طبقة متجهة وتعيين تسامح التخطية باستخدام Aspose.GIS لـ .NET
url: /ar/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء طبقة متجهة وتعيين تسامح الخطية باستخدام Aspose.GIS لـ .NET

## مقدمة
إذا كنت بحاجة إلى **create vector layer** ملفات، والتحكم في دقة المنحنيات، وتصدير النتيجة كمستند GeoJSON، فإن Aspose.GIS لـ .NET يجعل ذلك بسيطًا. في هذا البرنامج التعليمي ستتعلم كيفية تكوين خيارات GeoJSON، وتعيين تسامح الخطية، و**add feature to layer** الكائنات—كل ذلك مع الحفاظ على نظافة الكود وجاهزيته للإنتاج.

## إجابات سريعة
- **ماذا يعني “create vector layer”?** إنه ينشئ مجموعة بيانات متجهة GIS جديدة (مثل ملف GeoJSON) يمكنها تخزين الأشكال والسمات.  
- **كيف يتم تعيين التسامح؟** استخدم الخاصية `LinearizationTolerance` من `GeoJsonOptions`.  
- **هل يمكنني تصدير ملف GeoJSON؟** نعم—فقط أنشئ `VectorLayer` باستخدام السائق `Drivers.GeoJson`.  
- **هل أحتاج إلى ترخيص؟** ترخيص Aspose.GIS صالح يفتح جميع الميزات؛ الترخيص المؤقت يعمل للتقييم.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6/7.

## ما هو “create vector layer”؟
إنشاء طبقة متجهة يعني تهيئة حاوية GIS جديدة (مثل ملف GeoJSON) يمكنها احتواء ميزات هندسية مثل النقاط والخطوط والمضلعات. تصبح هذه الطبقة الهدف لأي شكل تقوم بإنشائه وأي سمات تُرفقها.

## لماذا يتم تكوين خيارات GeoJSON؟
تكوين خيارات GeoJSON—وخاصة **linearization tolerance**—يضمن أن الأشكال المنحنية (مثل `CircularString`) يتم تقريبها بدقة تلبي متطلبات الدقة لتطبيقك. هذه الخطوة حاسمة عندما تقوم لاحقًا **export GeoJSON file** للاستخدام في خرائط الويب أو التحليلات المكانية.

## المتطلبات المسبقة
1. **Visual Studio** مثبت (أي نسخة حديثة).  
2. **Aspose.GIS license** (أو مفتاح تقييم مؤقت).  
3. **Aspose.GIS for .NET** مكتبة تم تحميلها وإدراجها في مشروعك.  
4. إلمام أساسي بـ **C#**.

## استيراد مساحات الأسماء
أولاً، استورد مساحات الأسماء المطلوبة حتى يعرف المترجم أين يجد فئات GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## دليل خطوة بخطوة

### الخطوة 1: تكوين خيارات GeoJSON (كيفية تعيين التسامح)
سننشئ كائن `GeoJsonOptions` ونخبر Aspose.GIS إلى أي مدى يجب أن تكون الهندسة الخطية قريبة من المنحنى الأصلي.

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### الخطوة 2: تحديد مسار الإخراج (كيفية تصدير GeoJSON)
حدد أين سيتم حفظ الملف الناتج. استبدل العنصر النائب بالمجلد الفعلي الخاص بك.

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### الخطوة 3: **Create Vector Layer** باستخدام الخيارات المكوَّنة
الآن نقوم فعليًا **create vector layer** باستخدام طريقة `VectorLayer.Create`. يضمن كتلة `using` التخلص السليم من الموارد.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### الخطوة 4: بناء شكل هندسي (مثل سلسلة دائرية)
هنا نبني شكلًا هندسيًا تجريبيًا—`CircularString`. يمكنك استبداله بأي WKT صالح.

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### الخطوة 5: **Add Feature to Layer** وحفظ
أخيرًا، ننشئ ميزة، نعيّن الشكل الهندسي، ونضيفها إلى الطبقة. هذا هو جوهر عملية **add feature to layer**.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

عند انتهاء كتلة `using`، يتم كتابة الطبقة تلقائيًا إلى الملف المحدد في `path`، مما يمنحك ملف GeoJSON جاهزًا للاستخدام.

## مشكلات شائعة ونصائح
- **Incorrect path** – تأكد من وجود الدليل ولديك أذونات كتابة.  
- **Tolerance too low** – تعيين `LinearizationTolerance` إلى قيمة صغيرة جدًا قد يزيد حجم الملف بشكل كبير. اضبطه بناءً على احتياجات الدقة الخاصة بك.  
- **License errors** – إذا رأيت تحذيرات ترخيص، تحقق من تحميل ملف الترخيص بشكل صحيح قبل أي استدعاءات Aspose.GIS.

## الأسئلة المتكررة

**س: هل Aspose.GIS لـ .NET متوافق مع أطر .NET الأخرى؟**  
ج: نعم، يعمل مع .NET Framework و .NET Core و .NET 5/6/7.

**س: هل يمكنني استخدام Aspose.GIS في مشاريع تجارية؟**  
ج: بالتأكيد. الترخيص التجاري يزيل جميع قيود التقييم.

**س: هل يدعم Aspose.GIS صيغ GIS أخرى غير GeoJSON؟**  
ج: نعم، يدعم Shapefile و KML و GML والعديد غيرها.

**س: هل هناك نسخة تجريبية متاحة؟**  
ج: يمكنك تحميل نسخة تجريبية مجانية من موقع Aspose.

**س: أين يمكنني الحصول على الدعم؟**  
ج: استخدم منتديات Aspose أو رابط الدعم في قسم الموارد.

## الخلاصة
باتباع هذه الخطوات، أصبحت الآن تعرف كيفية **create vector layer**، وتكوين تسامح الخطية، و**add feature to layer** لإنشاء **export GeoJSON file** بسلاسة. استكشف أنواع أشكال هندسية إضافية ومعالجة السمات للاستفادة الكاملة من Aspose.GIS في مشاريع GIS الخاصة بـ .NET.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**آخر تحديث:** 2025-12-21  
**تم الاختبار مع:** Aspose.GIS 24.11 for .NET  
**المؤلف:** Aspose