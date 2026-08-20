---
date: 2026-06-30
description: تعرف على كيفية إنشاء طبقة متجهة بنظام الإحداثيات المرجعية باستخدام Aspose.GIS
  لـ .NET. دليل خطوة بخطوة، شروحات بدون كود، وأسئلة شائعة.
keywords:
- how to create vector layer
- Aspose.GIS spatial reference
- .NET GIS tutorial
linktitle: كيفية إنشاء طبقة متجهة مع نظام الإحداثيات المرجعية (SRS) باستخدام Aspose.GIS
  لـ .NET
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create vector layer with a spatial reference system using
    Aspose.GIS for .NET. Step‑by‑step guide, code‑free explanations, and FAQs.
  headline: How to Create Vector Layer with SRS using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS throws a `GisException`. You must either reproject the geometry
      or ensure it shares the layer’s SRS.
    question: What happens if I try to add a geometry with a different SRS?
  - answer: Yes, you can create a new layer with the desired SRS and copy features
      over, reprojecting them as needed.
    question: Can I change the SRS of an existing layer?
  - answer: Aspose.GIS supports Z‑coordinates; just use geometry constructors that
      accept a Z value.
    question: Is it possible to work with 3D coordinates?
  - answer: When you reproject geometries using `Geometry.Transform`, Aspose.GIS performs
      the necessary datum shift.
    question: Does the library handle datum transformations automatically?
  - answer: The library is tested with .NET Framework 4.5+, .NET Core 3.1+, and .NET
      5/6/7.
    question: Which .NET versions are officially tested?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: كيفية إنشاء طبقة متجهة مع نظام الإحداثيات المرجعية (SRS) باستخدام Aspose.GIS
  لـ .NET
url: /ar/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء طبقة متجهة مع نظام الإحداثيات المرجعي (SRS) باستخدام Aspose.GIS لـ .NET

## مقدمة
في هذا الدرس ستكتشف **كيفية إنشاء طبقة متجهة** التي تتضمن نظام إحداثيات مرجعي (SRS) باستخدام Aspose.GIS لـ .NET. سنستعرض السبب وراء تعيين SRS، ونظهر الخطوات الدقيقة لتعيينه، ونشرح الفوائد العملية مثل القياسات الدقيقة والدمج السلس مع بيانات GIS الأخرى. في النهاية، ستكون جاهزًا لتضمين وظائف GIS قوية في أي تطبيق .NET.

## إجابات سريعة
- **ما هو الهدف الأساسي من هذا الدرس؟** توضيح كيفية إنشاء طبقة متجهة مع SRS محدد باستخدام Aspose.GIS لـ .NET.  
- **أي إسقاط يُستخدم في المثال؟** World Mercator (EPSG:3395).  
- **هل أحتاج إلى ترخيص لتشغيل الكود؟** النسخة التجريبية المجانية تعمل للتطوير؛ يلزم ترخيص تجاري للإنتاج.  
- **هل يمكنني استخدام نفس النهج مع صيغ GIS أخرى؟** نعم، معالجة SRS نفسها تنطبق على Shapefile، GeoJSON، KML، إلخ.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6/7.

## ما هي الطبقة المتجهة ولماذا يتم تعيين مرجعها المكاني؟
تخزن **الطبقة المتجهة** ميزات هندسية (نقاط، خطوط، مضلعات) مع بيانات السمات. تعيين **نظام الإحداثيات المرجعي** يخبر برنامج GIS كيف يطابق تلك الإحداثيات مع سطح الأرض، مما يضمن حسابات مسافة دقيقة، ومحاذاة طبقة صحيحة، وعرض خريطة موثوق.

## لماذا يتم تعيين نظام الإحداثيات المرجعي؟
استخدام SRS معرف يقلل من أخطاء تحويل الإحداثيات بنسبة تصل إلى 95 % عند دمج طبقات من مصادر مختلفة. يدعم Aspose.GIS **أكثر من 20** صيغة إدخال وإخراج — بما في ذلك Shapefile، GeoJSON، KML، وGML — مع معالجة مجموعات بيانات مكونة من مئات الصفحات دون تحميل الملف بالكامل في الذاكرة.

## المتطلبات المسبقة
- معرفة أساسية بـ C# وتطوير .NET.  
- مكتبة Aspose.GIS لـ .NET مثبتة. يمكنك تنزيلها **[هنا](https://releases.aspose.com/gis/net/)**.  
- بيئة تطوير (Visual Studio، VS Code، أو أي IDE لـ C#).  

## استيراد مساحات الأسماء
تأكد من استيراد مساحات الأسماء الضرورية في أعلى ملف C# الخاص بك:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## كيفية تعيين المرجع المكاني (SRS) – الخطوة 1
حمّل SRS المُسقَّط في سطرين: أنشئ كائن `ProjectedSpatialReferenceSystem`، واضبط معلمات إسقاط Mercator، وستكون جاهزًا لإرفاقه بطبقة.

`ProjectedSpatialReferenceSystem` هي فئة تصف نظام إحداثيات مرجعي مسقَّط.  
`ProjectedSpatialReferenceSystemParameters` يحتوي على المعلمات اللازمة لتكوين SRS مسقَّط مثل خط الزوال المركزي وعامل المقياس.

لننشئ **نظام إحداثيات مرجعي مسقَّط** باستخدام إسقاط World Mercator كمثال. هذا يوضح **كيفية تعيين srs** لطبقة.

```csharp
var parameters = new ProjectedSpatialReferenceSystemParameters
{
    Name = "WGS 84 / World Mercator",
    Base = SpatialReferenceSystem.Wgs84,
    ProjectionMethodName = "Mercator_1SP",
    LinearUnit = Unit.Meter,
    XAxis = new Axis("Easting", AxisDirection.East),
    YAxis = new Axis("Northing", AxisDirection.North),
    AxisesOrder = ProjectedAxisesOrder.XY,
};
parameters.AddProjectionParameter("central_meridian", 0);
parameters.AddProjectionParameter("scale_factor", 1);
parameters.AddProjectionParameter("false_easting", 0);
parameters.AddProjectionParameter("false_northing", 0);
var projectedSrs = SpatialReferenceSystem.CreateProjected(parameters, Identifier.Epsg(3395));
```

## كيفية إنشاء الطبقة – الخطوة 2
أنشئ طبقة Shapefile، ومرّر `projectedSrs` المعرفة مسبقًا، ثم أضف الأشكال التي يتطابق `SpatialReferenceSystem` لها مع SRS الخاص بالطبقة.

`Layer` (مثل Shapefile) تمثل مجموعة من الميزات المخزنة في ملف GIS واحد.  
الآن سنقوم **بإنشاء طبقة متجهة** (Shapefile) وإضافة ميزات تستخدم SRS الذي عرّفناه للتو. هذا الجزء يجيب على **كيفية إنشاء طبقة** باستخدام Aspose.GIS.

```csharp
using (var layer = Drivers.Shapefile.CreateLayer(dataDir + "filepath_out.shp", new ShapefileOptions(), projectedSrs))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2);
    layer.Add(feature);
    feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2) { SpatialReferenceSystem = SpatialReferenceSystem.Nad83 };
    try
    {
        layer.Add(feature); // This will throw an exception as the geometry has a different SRS
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```

## التحقق من نظام الإحداثيات المرجعي – الخطوة 3
افتح الطبقة التي تم إنشاؤها حديثًا، استرجع `SpatialReferenceSystem` الخاصة بها، وقارنها بـ `projectedSrs` الأصلي باستخدام `IsEquivalent`. نتيجة `true` تؤكد أن SRS تم تطبيقه بشكل صحيح.

`IsEquivalent` يتحقق مما إذا كان نظاما إحداثيين مرجعيين يمثلان نفس نظام الإحداثيات.  
أخيرًا، افتح الطبقة وتأكد من أن SRS تم تطبيقه بشكل صحيح.

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

إذا أعادت الدالة `IsEquivalent` القيمة `true`، فقد نجحت في **إنشاء طبقة متجهة** مع المرجع المكاني المطلوب.

## المشكلات الشائعة والحلول
| المشكلة | سبب حدوثها | الحل |
|-------|----------------|-----|
| `GisException` عند إضافة ميزة | الجيومتري يستخدم SRS مختلف عن الطبقة | عيّن `feature.Geometry.SpatialReferenceSystem` إلى SRS الخاص بالطبقة قبل الإضافة |
| الطبقة تظهر فارغة في برنامج GIS | تم إنشاء shapefile بدون ملف `.prj` صحيح | تأكد من تمرير كائن `projectedSrs` عند إنشاء الطبقة |
| قيم إحداثيات غير متوقعة | معلمات إسقاط خاطئة (مثل خط الزوال المركزي) | تحقق مرة أخرى من المعلمات الممررة إلى `AddProjectionParameter` |

## الأسئلة المتكررة
### هل Aspose.GIS متوافق مع جميع صيغ ملفات GIS؟
يدعم Aspose.GIS **أكثر من 20** صيغة GIS، بما في ذلك Shapefile، GeoJSON، KML، GML، وغيرها. راجع **[التوثيق](https://reference.aspose.com/gis/net/)** للقائمة الكاملة.

### هل يمكنني استخدام Aspose.GIS في تطبيق ويب؟
بالطبع! يعمل Aspose.GIS لـ .NET في ASP.NET، ASP.NET Core، وأي بيئة .NET على الخادم.

### أين يمكنني الحصول على دعم Aspose.GIS؟
يمكنك العثور على مجتمع مفيد في **[منتدى Aspose.GIS](https://forum.aspose.com/c/gis/33)** لأي استفسارات أو مشكلات قد تواجهها.

### هل هناك نسخة تجريبية مجانية متاحة؟
نعم، يمكنك استكشاف ميزات Aspose.GIS بالحصول على نسخة تجريبية مجانية **[هنا](https://releases.aspose.com/)**.

### كيف يمكنني شراء ترخيص لـ Aspose.GIS؟
لشراء ترخيص، زر **[صفحة الشراء](https://purchase.aspose.com/buy)**.

## الأسئلة المتكررة (إضافية)

**س: ماذا يحدث إذا حاولت إضافة شكل هندسي ب SRS مختلف؟**  
ج: يطرح Aspose.GIS استثناء `GisException`. يجب إما إعادة إسقاط الشكل أو التأكد من أنه يشارك SRS الخاص بالطبقة.

**س: هل يمكنني تغيير SRS لطبقة موجودة؟**  
ج: نعم، يمكنك إنشاء طبقة جديدة بالـ SRS المطلوب ونسخ الميزات إليها، مع إعادة إسقاطها حسب الحاجة.

**س: هل من الممكن العمل بإحداثيات ثلاثية الأبعاد؟**  
ج: يدعم Aspose.GIS إحداثيات Z؛ فقط استخدم مُنشئات الشكل التي تقبل قيمة Z.

**س: هل تتعامل المكتبة مع تحويلات الداتوم تلقائيًا؟**  
ج: عند إعادة إسقاط الأشكال باستخدام `Geometry.Transform`، يقوم Aspose.GIS بتنفيذ تحويل الداتوم اللازم.

**س: أي إصدارات .NET تم اختبارها رسميًا؟**  
ج: تم اختبار المكتبة مع .NET Framework 4.5+، .NET Core 3.1+، و .NET 5/6/7.

## الخلاصة
لقد تعلمت الآن **كيفية إنشاء طبقة متجهة** بنظام إحداثيات مرجعي مخصص باستخدام Aspose.GIS لـ .NET. من خلال تعيين SRS الصحيح، ومعالجة الأشكال بشكل متسق، والتحقق من بيانات تعريف الطبقة، يمكنك بناء تطبيقات GIS قوية تتفاعل مع أي برنامج GIS قياسي.

---

**آخر تحديث:** 2026-06-30  
**تم الاختبار مع:** Aspose.GIS 24.11 for .NET (latest at time of writing)  
**المؤلف:** Aspose

## الدروس ذات الصلة

- [إنشاء طبقة متجهة وتعيين نظام الإحداثيات المرجعي للطبقة](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [إنشاء طبقة متجهة في File GDB – درس Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [كيفية تعديل الطبقة – تفاعل طبقة Aspose.GIS .NET](/gis/net/layer-interaction-and-data-access/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}