---
date: 2026-01-15
description: استكشف Aspose.GIS لـ .NET لإنشاء طبقة متجهة بنظام إسناد مكاني. تعلّم
  كيفية ضبط نظام الإسناد المكاني، وإنشاء الطبقة، وإدارة بيانات GIS. حمّل الآن!
linktitle: Create Vector Layer with SRS
second_title: Aspose.GIS .NET API
title: إنشاء طبقة متجهة بنظام الإحداثيات المرجعي
url: /ar/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء طبقة متجهة مع نظام الإسناد المكاني (SRS)

## المقدمة
Aspose.GIS for .NET هي مكتبة قوية تمكّن المطورين من **إنشاء طبقة متجهة** والعمل مع بيانات نظام المعلومات الجغرافية (GIS) بسلاسة في تطبيقات .NET. في هذا الدرس، سنستعرض كيفية إنشاء طبقة متجهة مع نظام إسناد مكاني (SRS)، ولماذا قد ترغب في تعيين إسناد مكاني، وما الفوائد التي يجلبها ذلك للمشاريع الواقعية. بنهاية هذا الدليل، ستكون قادرًا على دمج قدرات GIS في حلول .NET الخاصة بك بثقة.

## إجابات سريعة
- **ما هو الهدف الأساسي من هذا الدرس؟** إظهار كيفية إنشاء طبقة متجهة مع نظام إسناد مكاني محدد باستخدام Aspose.GIS for .NET.  
- **أي إسقاط يُستخدم في المثال؟** World Mercator (EPSG:3395).  
- **هل أحتاج إلى ترخيص لتشغيل الشيفرة؟** النسخة التجريبية المجانية تكفي للتطوير؛ يلزم ترخيص تجاري للإنتاج.  
- **هل يمكنني استخدام نفس النهج مع صيغ GIS أخرى؟** نعم، معالجة الـ SRS نفسها تنطبق على Shapefile، GeoJSON، KML، إلخ.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6/7.

## ما هي الطبقة المتجهة ولماذا نحدد إسنادها المكاني؟
**الطبقة المتجهة** تخزن الميزات الهندسية (نقاط، خطوط، مضلعات) مع بيانات السمات. تعيين **الإسناد المكاني** (SRS) يخبر برامج GIS كيف تفسّر تلك الإحداثيات على سطح الأرض. ضبط الـ SRS الصحيح يضمن قياسات دقيقة، وتراكب صحيح مع طبقات أخرى، وعرض خرائط موثوق.

## المتطلبات المسبقة
قبل المتابعة، تأكد من وجود:

- معرفة أساسية بـ C# وتطوير .NET.  
- مكتبة Aspose.GIS for .NET مثبتة. يمكنك تنزيلها **[من هنا](https://releases.aspose.com/gis/net/)**.  
- بيئة تطوير (Visual Studio، VS Code، أو أي IDE يدعم C#).  

## استيراد المساحات الاسمية
تأكد من استيراد المساحات الاسمية اللازمة في أعلى ملف C# الخاص بك:

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

## كيفية تعيين الإسناد المكاني (SRS) – الخطوة 1
لنقم بإنشاء **نظام إسناد مكاني مُسقَّط** باستخدام إسقاط World Mercator كمثال. هذا يوضح **كيفية تعيين الـ srs** للطبقة.

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
الآن سنقوم **بإنشاء طبقة متجهة** (Shapefile) وإضافة ميزات تستخدم الـ SRS الذي عرّفناه للتو. هذا الجزء يجيب على **كيفية إنشاء طبقة** باستخدام Aspose.GIS.

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

> **نصيحة احترافية:** تأكد دائمًا من أن `SpatialReferenceSystem` الخاص بالهندسة يطابق الـ SRS للطبقة قبل إضافتها. قيم الـ SRS غير المتطابقة تُثير استثناء `GisException`، كما هو موضح أعلاه.

## التحقق من نظام الإسناد المكاني – الخطوة 3
أخيرًا، افتح الطبقة وتأكد من أن الـ SRS تم تطبيقه بشكل صحيح.

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

إذا أعاد استدعاء `IsEquivalent` القيمة `true`، فقد نجحت في **إنشاء طبقة متجهة** مع الإسناد المكاني المطلوب.

## المشكلات الشائعة والحلول
| المشكلة | لماذا يحدث | الحل |
|-------|----------------|-----|
| `GisException` عند إضافة ميزة | الهندسة تستخدم SRS مختلف عن طبقة الـ layer | عيّن `feature.Geometry.SpatialReferenceSystem` إلى SRS الخاص بالطبقة قبل الإضافة |
| الطبقة تظهر فارغة في برنامج GIS | تم إنشاء ملف shapefile بدون ملف `.prj` صحيح | تأكد من تمرير كائن `projectedSrs` عند إنشاء الطبقة |
| قيم إحداثيات غير متوقعة | معلمات الإسقاط خاطئة (مثل خط الطول المركزي) | راجع المعلمات الممررة إلى `AddProjectionParameter` |

## الأسئلة المتكررة
### هل Aspose.GIS متوافق مع جميع صيغ ملفات GIS؟
Aspose.GIS يدعم صيغ GIS متعددة، بما في ذلك Shapefile، GeoJSON، KML، وغيرها. راجع **[الوثائق](https://reference.aspose.com/gis/net/)** للقائمة الكاملة.

### هل يمكنني استخدام Aspose.GIS في تطبيق ويب؟
بالطبع! Aspose.GIS for .NET مرن ويمكن استخدامه في تطبيقات الويب، تطبيقات سطح المكتب، وحتى التطبيقات المحمولة.

### أين يمكنني الحصول على دعم لـ Aspose.GIS؟
يمكنك العثور على مجتمع مساعد في **[منتدى Aspose.GIS](https://forum.aspose.com/c/gis/33)** لأي استفسارات أو مشكلات قد تواجهها.

### هل هناك نسخة تجريبية مجانية متاحة؟
نعم، يمكنك استكشاف ميزات Aspose.GIS بالحصول على نسخة تجريبية مجانية **[من هنا](https://releases.aspose.com/)**.

### كيف يمكنني شراء ترخيص لـ Aspose.GIS؟
لشراء ترخيص، زر **[صفحة الشراء](https://purchase.aspose.com/buy)**.

## أسئلة شائعة إضافية

**س: ماذا يحدث إذا حاولت إضافة هندسة بــ SRS مختلف؟**  
ج: Aspose.GIS يطلق استثناء `GisException`. يجب إما إعادة إسقاط الهندسة أو التأكد من أنها تشترك في SRS الخاص بالطبقة.

**س: هل يمكنني تغيير SRS لطبقة موجودة؟**  
ج: نعم، يمكنك إنشاء طبقة جديدة بالـ SRS المطلوب ونسخ الميزات إليها مع إعادة إسقاطها حسب الحاجة.

**س: هل يمكن العمل بإحداثيات ثلاثية الأبعاد؟**  
ج: Aspose.GIS يدعم إحداثيات Z؛ فقط استخدم مُنشئات الهندسة التي تقبل قيمة Z.

**س: هل المكتبة تتعامل مع تحويلات الداتوم تلقائيًا؟**  
ج: عند إعادة إسقاط الهندسات باستخدام `Geometry.Transform`، تقوم Aspose.GIS بتنفيذ التحويلات الداتومية اللازمة.

**س: أي إصدارات .NET تم اختبارها رسميًا؟**  
ج: تم اختبار المكتبة مع .NET Framework 4.5+، .NET Core 3.1+، و .NET 5/6/7.

## الخاتمة
لقد تعلمت الآن كيفية **إنشاء طبقة متجهة** بنظام إسناد مكاني مخصص باستخدام Aspose.GIS for .NET. من خلال ضبط الـ SRS الصحيح، ومعالجة الهندسة بشكل متسق، والتحقق من بيانات تعريف الطبقة، يمكنك بناء تطبيقات GIS قوية تتكامل مع أي برنامج GIS قياسي.

---

**آخر تحديث:** 2026-01-15  
**تم الاختبار مع:** Aspose.GIS 24.11 for .NET (أحدث نسخة وقت الكتابة)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}