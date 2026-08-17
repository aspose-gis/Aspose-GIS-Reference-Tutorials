---
date: 2026-05-31
description: تعلم كيفية إنشاء GeoJSON، وتكوين خيارات GeoJSON، وإضافة ميزة إلى الطبقة
  باستخدام Aspose.GIS for .NET. اتبع هذا الدليل خطوة بخطوة.
keywords:
- how to create geojson
- add feature to layer
- configure geojson options
linktitle: تعيين تسامح التخطية
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  headline: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  name: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  steps:
  - name: Configure GeoJSON Options (how to set tolerance)
    text: '`GeoJsonOptions` specifies the serialization settings used when writing
      GeoJSON files. `GeoJsonOptions` defines how Aspose.GIS serializes GeoJSON, including
      linearization tolerance, coordinate precision, and other output settings. We’ll
      create a `GeoJsonOptions` object and tell Aspose.GIS how close '
  - name: Define the Output Path (how to export GeoJSON)
    text: Specify the full file path where the resulting GeoJSON will be saved. Ensure
      the folder exists and the application has write permissions.
  - name: '**Create Vector Layer** with the configured options'
    text: The `VectorLayer` class represents a GIS container that can read and write
      spatial data. `Drivers.GeoJson` is the driver identifier for writing GeoJSON
      format files. Using `VectorLayer.Create` together with the `Drivers.GeoJson`
      driver and the previously configured `GeoJsonOptions` creates a new Geo
  - name: Construct a Geometry (e.g., a circular string)
    text: '`CircularString` is a curved line geometry that Aspose.GIS can linearize
      based on the tolerance you set. You can replace this with any valid WKT representation
      such as `POINT`, `LINESTRING`, or `POLYGON`.'
  - name: '**Add Feature to Layer** and save'
    text: '`Feature` is the object that couples a geometry with attribute data. After
      creating a `Feature` instance, assign the geometry, optionally add attribute
      values, and call `layer.Add(feature)` to persist it. When the `using` block
      ends, the layer is automatically written to the file defined in `path`. '
  type: HowTo
- questions:
  - answer: Yes, it works with .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6/7.
    question: Is Aspose.GIS for .NET compatible with other .NET frameworks?
  - answer: Absolutely. A commercial license removes all evaluation restrictions and
      provides full technical support.
    question: Can I use Aspose.GIS in commercial projects?
  - answer: Yes, it supports over 30 formats—including Shapefile, KML, GML, and CSV—allowing
      seamless conversion between them.
    question: Does Aspose.GIS support other GIS formats besides GeoJSON?
  - answer: You can download a free 30‑day trial from the Aspose website; it includes
      all features.
    question: Is there a trial version available?
  - answer: Use the Aspose forums, the dedicated support portal, or the “Contact Support”
      link in the product dashboard.
    question: Where can I get support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: كيفية إنشاء GeoJSON مع التسامح باستخدام Aspose.GIS for .NET
url: /ar/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء GeoJSON مع التسامح Aspose.GIS لـ .NET

## مقدمة
إذا كنت تريد **تعلم كيفية إنشاء GeoJSON** ملفات، والتحكم في دقة المنحنيات، وتصدير النتيجة كمستند جاهز للاستخدام، يجعل Aspose.GIS لـ .NET العملية بسيطة. في هذا البرنامج التعليمي ستكتشف كيفية تكوين خيارات GeoJSON، وتعيين تسامح الخطية، و**إضافة ميزة إلى الطبقة** مع الحفاظ على نظافة الكود وجاهزيته للإنتاج.

## إجابات سريعة
- **ماذا يعني “create vector layer”؟** يخلق مجموعة بيانات GIS متجهة جديدة (مثل ملف GeoJSON) يمكنها تخزين الأشكال والسمات.  
- **كيف أضبط تسامح الخطية؟** قم بتعيين خاصية `LinearizationTolerance` على كائن `GeoJsonOptions` قبل إنشاء الطبقة.  
- **هل يمكنني تصدير ملف GeoJSON مباشرةً؟** نعم—استخدم `VectorLayer.Create` مع السائق `Drivers.GeoJson` والإعدادات المكوَّنة.  
- **هل أحتاج إلى ترخيص؟** ترخيص Aspose.GIS صالح يفتح جميع الميزات؛ مفتاح تقييم مؤقت يعمل للاختبار.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## ما هو “create vector layer”؟
إنشاء طبقة متجهة يعني تهيئة حاوية GIS جديدة (مثل ملف GeoJSON) يمكنها احتواء النقاط، الخطوط، المضلعات، والبيانات الوصفية المرتبطة. تصبح هذه الطبقة الهدف لأي شكل تقوم بإنشائه وأي سمات تقوم بإرفاقها.

## لماذا تكوين خيارات GeoJSON؟
تكوين خيارات GeoJSON—وخاصة **تسامح الخطية**—يضمن أن الأشكال المنحنية (مثل `CircularString`) يتم تقريبها بدقة تلبي متطلبات الدقة لتطبيقك. التكوين السليم يقلل من حجم الملف مع الحفاظ على الدقة البصرية، وهو أمر حاسم عندما يتم استهلاك GeoJSON بواسطة خرائط الويب أو أدوات التحليل المكاني.

## المتطلبات المسبقة
1. **Visual Studio** (أي نسخة حديثة).  
2. **ترخيص Aspose.GIS** (أو مفتاح تقييم مؤقت).  
3. مكتبة **Aspose.GIS for .NET** مُشار إليها في مشروعك.  
4. إلمام أساسي بـ **C#**.

## استيراد المساحات الاسمية
First, import the required namespaces so the compiler knows where to find the GIS classes:

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

### الخطوة 1: تكوين خيارات GeoJSON (كيفية ضبط التسامح)
`GeoJsonOptions` يحدد إعدادات التسلسل المستخدمة عند كتابة ملفات GeoJSON.  
`GeoJsonOptions` يحدد كيفية تسلسل Aspose.GIS لملفات GeoJSON، بما في ذلك تسامح الخطية، دقة الإحداثيات، وإعدادات الإخراج الأخرى.  
سننشئ كائن `GeoJsonOptions` ونخبر Aspose.GIS إلى أي مدى يجب أن تكون الهندسة الخطية قريبة من المنحنى الأصلي.

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### الخطوة 2: تحديد مسار الإخراج (كيفية تصدير GeoJSON)
حدد مسار الملف الكامل حيث سيتم حفظ GeoJSON الناتج. تأكد من وجود المجلد وأن التطبيق يمتلك أذونات الكتابة.

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### الخطوة 3: **Create Vector Layer** مع الخيارات المكوَّنة
فئة `VectorLayer` تمثل حاوية GIS يمكنها قراءة وكتابة البيانات المكانية.  
`Drivers.GeoJson` هو معرف السائق لكتابة ملفات بصيغة GeoJSON.  
استخدام `VectorLayer.Create` مع السائق `Drivers.GeoJson` ومع `GeoJsonOptions` المكوَّنة مسبقًا ينشئ ملف GeoJSON جديد جاهز لإدراج الميزات.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### الخطوة 4: إنشاء شكل هندسي (مثال: سلسلة دائرية)
`CircularString` هو شكل خط منحني يمكن لـ Aspose.GIS تحويله إلى خطية بناءً على التسامح الذي تحدده. يمكنك استبداله بأي تمثيل WKT صالح مثل `POINT` أو `LINESTRING` أو `POLYGON`.

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### الخطوة 5: **Add Feature to Layer** وحفظها
`Feature` هو الكائن الذي يربط الشكل الهندسي ببيانات السمات. بعد إنشاء مثيل `Feature`، قم بتعيين الشكل الهندسي، وإضافة قيم السمات اختياريًا، واستدعِ `layer.Add(feature)` لحفظه. عندما ينتهي كتلة `using`، يتم كتابة الطبقة تلقائيًا إلى الملف المحدد في `path`.  
عند انتهاء كتلة `using`، تُكتب الطبقة تلقائيًا إلى الملف المحدد في `path`، مما يمنحك ملف GeoJSON جاهزًا للاستخدام.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

## المشكلات الشائعة والنصائح
- **مسار غير صحيح** – تحقق من وجود الدليل وأن لديك أذونات كتابة.  
- **التسامح منخفض جدًا** – ضبط `LinearizationTolerance` إلى قيمة صغيرة جدًا يمكن أن يزيد حجم الملف بشكل كبير؛ عادةً ما يكون التسامح 0.001 هو التوازن بين الدقة والحجم.  
- **أخطاء الترخيص** – إذا رأيت تحذيرات الترخيص، تأكد من تحميل ملف الترخيص قبل أي استدعاءات Aspose.GIS.  
- **ملاحظة الأداء** – يدعم Aspose.GIS معالجة ملفات تصل إلى 2 جيجابايت دون تحميل المستند بالكامل في الذاكرة، بفضل بنية البث الخاصة به.

## الأسئلة المتكررة

**س: هل Aspose.GIS لـ .NET متوافق مع أطر .NET الأخرى؟**  
A: نعم، يعمل مع .NET Framework 4.5+، .NET Core 3.1+، و .NET 5/6/7.

**س: هل يمكنني استخدام Aspose.GIS في المشاريع التجارية؟**  
A: بالتأكيد. يزيل الترخيص التجاري جميع قيود التقييم ويوفر دعمًا فنيًا كاملًا.

**س: هل يدعم Aspose.GIS صيغ GIS أخرى غير GeoJSON؟**  
A: نعم، يدعم أكثر من 30 صيغة—بما في ذلك Shapefile و KML و GML و CSV—مما يتيح تحويلًا سلسًا بينها.

**س: هل هناك نسخة تجريبية متاحة؟**  
A: يمكنك تنزيل نسخة تجريبية مجانية لمدة 30 يومًا من موقع Aspose؛ تشمل جميع الميزات.

**س: أين يمكنني الحصول على الدعم؟**  
A: استخدم منتديات Aspose، بوابة الدعم المخصصة، أو رابط “Contact Support” في لوحة تحكم المنتج.

## الخاتمة
باتباع هذه الخطوات، أنت الآن تعرف **كيفية إنشاء GeoJSON**، وتكوين تسامح الخطية، و**إضافة ميزة إلى الطبقة** لتصدير GeoJSON بسلاسة. استكشف أنواع أشكال هندسية إضافية، ومعالجة السمات، وسيناريوهات المعالجة الجماعية للاستفادة الكاملة من Aspose.GIS في مشاريع GIS الخاصة بـ .NET.

---

**آخر تحديث:** 2026-05-31  
**تم الاختبار مع:** Aspose.GIS 24.11 for .NET  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [كيفية تحويل GeoJSON – Aspose.GIS لـ .NET](/gis/net/geo-data-conversion/)
- [إنشاء طبقة متجهة، تحديد الدقة مع Aspose.GIS لـ .NET](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [إنشاء طبقة متجهة في File GDB – دليل Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}