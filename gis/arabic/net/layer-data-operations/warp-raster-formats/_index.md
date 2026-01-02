---
date: 2026-01-02
description: تعلم كيفية تشويه الصور النقطية باستخدام Aspose.GIS لـ .NET. يوضح لك هذا
  الدليل خطوة بخطوة كيفية تشويه صيغ الصور النقطية، واستخراج البيانات الوصفية، والعمل
  مع نطاقات الصورة النقطية.
linktitle: How to Warp Raster Formats
second_title: Aspose.GIS .NET API
title: كيفية تحويل تنسيقات الراستر باستخدام Aspose.GIS لـ .NET
url: /ar/net/layer-data-operations/warp-raster-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تشويه صيغ الراستر

## المقدمة
في هذا الدرس ستكتشف **كيفية تشويه** بيانات الراستر باستخدام Aspose.GIS for .NET. سواء كنت بحاجة إلى إعادة إسقاط GeoTIFF، أو تغيير دقته، أو مجرد استكشاف التفاصيل الداخلية للراستر، فإن الخطوات أدناه ستقودك عبر العملية بالكامل—من تحميل الملف إلى فحص إحصاءات كل نطاق. لنبدأ!

## إجابات سريعة
- **ماذا يعني “تشويه الراستر”؟** هو عملية إعادة إسقاط وإعادة أخذ عينات بيانات الراستر إلى نظام إحداثيات مكاني جديد أو دقة مختلفة.  
- **أي مكتبة تتولى التشويه؟** Aspose.GIS for .NET توفر طريقة `Warp` على طبقات الراستر.  
- **هل أحتاج إلى ترخيص؟** نسخة تجريبية مجانية تكفي للتطوير؛ الترخيص التجاري مطلوب للإنتاج.  
- **صيغة الإدخال المدعومة؟** يُستخدم GeoTIFF في المثال، لكن Aspose.GIS يدعم العديد من صيغ الراستر.  
- **الوقت التشغيلي المعتاد؟** تشويه راستر صغير 40 × 40 يستغرق أقل من ثانية على جهاز كمبيوتر حديث.

## ما هو تشويه الراستر؟
تشويه الراستر (أو إعادة الإسقاط) يحول خلايا الراستر من نظام إحداثيات إلى آخر مع إمكانية تعديل حجم البكسل. هذا ضروري عندما تجمع طبقات تستخدم مراجع مكانية مختلفة أو عندما تحتاج إلى راستر يتطابق مع مقياس خريطة معين.

## لماذا نستخدم Aspose.GIS لتشويه الراستر؟
- **API نقي لـ .NET** – لا يعتمد على مكونات أصلية، يعمل على Windows وLinux وmacOS.  
- **مميزات كاملة** – يدعم GeoTIFF وJPEG2000 وPNG وغيرها.  
- **إعادة أخذ عينات دقيقة** – يدعم أقرب جار، خطي مزدوج، وتكعيبي (الإعداد الافتراضي هو الخطي المزدوج).  
- **سهولة التكامل** – يعمل مع ASP.NET، تطبيقات سطر الأوامر، أو أي خدمة .NET.

## المتطلبات المسبقة
قبل الغوص في الكود، تأكد من وجود ما يلي:

- Aspose.GIS for .NET مثبت. احصل على أحدث حزمة من صفحة التحميل الرسمية **[هنا](https://releases.aspose.com/gis/net/)**.  
- مجلد على جهازك لتخزين ملف GeoTIFF التجريبي (`raster_float32.tif`).  
- .NET 6 (أو أحدث) SDK مثبت.

## استيراد المساحات الاسمية
أولاً، استدعِ مساحات الأسماء المطلوبة في .NET:

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Raster;
using Aspose.Gis.SpatialReferencing;
```

## الخطوة 1: تهيئة المسار
حدد المسار الذي يشير إلى الدليل الذي يحتوي على ملف الراستر الخاص بك.

```csharp
string dataDir = "Your Document Directory";
```

## الخطوة 2: فتح طبقة الراستر
افتح طبقة GeoTIFF للراستر. هذا يُعد الصورة للعمليات اللاحقة.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(dataDir, "raster_float32.tif")))
```

## الخطوة 3: تشويه الراستر
طبق عملية التشويه. هنا نطلب راستر 40 × 40 في نظام الإحداثيات WGS‑84.

```csharp
using (var warped = layer.Warp(new WarpOptions(){Height = 40, Width = 40, TargetSpatialReferenceSystem = SpatialReferenceSystem.Wgs84}))
```

## الخطوة 4: استخراج معلومات الراستر
استخرج البيانات الوصفية المفيدة من الراستر المشوه.

```csharp
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
var bandCount = warped.BandCount;
```

## الخطوة 5: طباعة تفاصيل الراستر
اعرض المعلومات المستخرجة على وحدة التحكم.

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
Console.WriteLine($"bandCount: {bandCount}");
```

## الخطوة 6: استكشاف نطاقات الراستر
تجول عبر كل نطاق لتعرف نوع البيانات، الإحصاءات، ومعالجة قيم NoData.

```csharp
for (int i = 0; i < warped.BandCount; i++)
{
    var dataType = warped.GetBand(i).DataType;
    var hasNoData = !warped.NoDataValues.IsNull();
    var statistics = warped.GetStatistics(i);
    Console.WriteLine();
    Console.WriteLine($"Band: {i}");
    Console.WriteLine($"dataType: {dataType}");
    Console.WriteLine($"statistics: {statistics}");
    Console.WriteLine($"hasNoData: {hasNoData}");
    if (hasNoData)
        Console.WriteLine($"noData: {warped.NoDataValues[i]}");
}
```

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|----------------|-----|
| **راستر الإخراج فارغ** | نظام الإحداثيات الهدف غير معترف به | تحقق من رمز EPSG (`SpatialReferenceSystem.Wgs84` = 4326) وتأكد من أن الراستر المصدر يحتوي على نظام إحداثيات صالح. |
| **قيم NoData تظهر كصفر** | `NoDataValues` غير مُحددة في المصدر | عيّن قيم NoData صراحةً على الراستر الأصلي أو عالجها بعد التشويه باستخدام `warped.NoDataValues`. |
| **بطء الأداء على الراستر الكبير** | إعادة أخذ العينات الخطية المزدوجة تستهلك CPU | استخدم `WarpOptions.Interpolation = InterpolationMode.NearestNeighbour` للحصول على نتائج أسرع، وإن كانت أقل سلاسة. |

## الخلاصة
أنت الآن تعرف **كيفية تشويه** بيانات الراستر باستخدام Aspose.GIS for .NET، استخراج بياناته الوصفية، وفحص إحصاءات كل نطاق. هذه القدرة تفتح الباب أمام تحليلات مكانية متقدمة، إنتاج خرائط، وتكامل سلس لمجموعات بيانات جغرافية متباينة.

## الأسئلة المتكررة
### هل Aspose.GIS متوافق مع جميع صيغ الراستر؟
نعم، يدعم Aspose.GIS مجموعة واسعة من صيغ الراستر، مما يوفر مرونة في التعامل مع مختلف مجموعات البيانات المكانية.

### هل يمكنني إجراء تشويه للراستر على صور غير مرتبطة جغرافيًا؟
تم تصميم Aspose.GIS للتعامل مع البيانات المرتبطة جغرافيًا، لضمان تحويلات دقيقة. تأكد من أن صور الراستر الخاصة بك تحتوي على معلومات مرجعية مكانية صحيحة.

### كيف يمكنني المساهمة في مجتمع Aspose.GIS؟
انضم إلى النقاش في [منتدى Aspose.GIS](https://forum.aspose.com/c/gis/33) لمشاركة تجاربك، طرح الأسئلة، والتعاون مع مطورين آخرين.

### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.GIS؟
نعم، يمكنك استكشاف إمكانيات Aspose.GIS بتحميل نسخة تجريبية مجانية **[هنا](https://releases.aspose.com/)**.

### هل تتوفر تراخيص مؤقتة لـ Aspose.GIS؟
نعم، إذا كنت بحاجة إلى ترخيص مؤقت، يمكنك الحصول عليه **[هنا](https://purchase.aspose.com/temporary-license/)**.

## أسئلة شائعة

**س: ما صيغ الراستر التي يمكنني تشويهها بخلاف GeoTIFF؟**  
ج: يدعم Aspose.GIS JPEG وPNG وBMP والعديد من صيغ الراستر الشائعة الأخرى. طريقة `Warp` تعمل مع أي صيغة يمكن للمكتبة فتحها.

**س: هل تعدل عملية التشويه الملف الأصلي؟**  
ج: لا. طريقة `Warp` تنشئ راسترًا جديدًا في الذاكرة (`warped`) وتترك الملف المصدر دون تغيير.

**س: كيف أغيّر دقة الإخراج؟**  
ج: عدّل خصائص `Height` و`Width` في `WarpOptions` إلى أبعاد البكسل المطلوبة.

**س: هل يمكنني حفظ الراستر المشوه إلى القرص؟**  
ج: نعم. بعد التشويه، استخدم `warped.Save("output.tif", Drivers.GeoTiff)` لكتابة النتيجة إلى ملف.

**س: هل هناك دعم للأنظمة الإحداثية المخصصة؟**  
ج: بالتأكيد. قدّم كائن `SpatialReferenceSystem` مخصص مع رمز EPSG المناسب أو تعريف WKT.

---

**آخر تحديث:** 2026-01-02  
**تم الاختبار مع:** Aspose.GIS 24.11 for .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}