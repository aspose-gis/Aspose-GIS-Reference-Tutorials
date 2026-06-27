---
date: 2026-05-05
description: تعلم كيفية الحصول على حجم خلية الصورة النقطية وكيفية تحويل صيغ الصور
  النقطية باستخدام Aspose.GIS لـ .NET. دليل خطوة بخطوة لتصوير البيانات المكانية.
keywords:
- get raster cell size
- how to warp raster
- Aspose GIS raster
linktitle: صيغ الراستر المشوهة
second_title: Aspose.GIS .NET API
title: الحصول على حجم خلية الراستر – تحويل صيغ الراستر باستخدام Aspose.GIS
url: /ar/net/layer-data-operations/warp-raster-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# احصل على حجم خلية الراستر – تحويل صيغ الراستر

## مقدمة
مرحبًا بك في عالم البرمجة الجغرافية المثير مع Aspose.GIS for .NET! في هذا البرنامج التعليمي، ستحصل على **حجم خلية الراستر** بعد تحويل الراستر، وتتعلم **كيفية تحويل صيغ الراستر** خطوة بخطوة. سواء كنت مطورًا متمرسًا أو مبتدئًا، استعد للغوص في تفاصيل معالجة GeoTIFF، ومنح بياناتك المكانية منظورًا جديدًا تمامًا.

## إجابات سريعة
- **ما هو الهدف الأساسي؟** الحصول على حجم خلية الراستر بعد تنفيذ عملية التحويل.  
- **ما المكتبة المستخدمة؟** Aspose.GIS for .NET.  
- **هل أحتاج إلى ترخيص؟** يتوفر نسخة تجريبية مجانية؛ يلزم وجود ترخيص للاستخدام في الإنتاج.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **كم من الوقت يستغرق تشغيل المثال؟** أقل من دقيقة على جهاز عادي.

## المتطلبات المسبقة
قبل أن نبدأ هذه الرحلة، تأكد من توفر المتطلبات التالية:
- Aspose.GIS for .NET: إذا لم تقم بذلك بعد، قم بتحميل وتثبيت مكتبة Aspose.GIS. يمكنك العثور على أحدث نسخة [هنا](https://releases.aspose.com/gis/net/).
- دليل المستندات الخاص بك: أنشئ دليلًا لتخزين مستنداتك. سيكون هذا أمرًا حيويًا لإدارة الملفات أثناء عملية تحويل الراستر.

الآن بعد أن أصبحنا مستعدين، دعونا نغوص في الكود.

## استيراد مساحات الأسماء
أولًا، لنتأكد من أن لدينا الأدوات المناسبة تحت تصرفنا. استورد مساحات الأسماء الضرورية لبدء مغامرتك الجغرافية:
```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Raster;
using Aspose.Gis.SpatialReferencing;
```

## الخطوة 1: تهيئة المسار
ابدأ بتعيين المسار إلى دليل المستندات الخاص بك. هذا هو المكان الذي سيحدث فيه كل السحر:
```csharp
string dataDir = "Your Document Directory";
```

## الخطوة 2: فتح طبقة الراستر
افتح طبقة GeoTiff الراستر وقم بتحضيرها للتحويل. هذه الخطوة تمهيدًا لعملية التحويل اللاحقة:
```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(dataDir, "raster_float32.tif")))
```

## الخطوة 3: تحويل الراستر
الآن، لنقم بتنفيذ عملية التحويل. حدد الأبعاد المستهدفة ونظام الإسناد المكاني لإضفاء حياة جديدة على بيانات الراستر الخاصة بك:
```csharp
using (var warped = layer.Warp(new WarpOptions(){Height = 40, Width = 40, TargetSpatialReferenceSystem = SpatialReferenceSystem.Wgs84}))
```

## الخطوة 4: استخراج معلومات الراستر
حان الوقت لكشف أسرار الراستر المُحوَّل. استخرج المعلومات الأساسية مثل حجم الخلية، نظام الإسناد المكاني، الحدود، وعدد النطاقات:
```csharp
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
var bandCount = warped.BandCount;
```

## الخطوة 5: طباعة تفاصيل الراستر
لنطبع التفاصيل المهمة التي اكتشفناها، لتوفير نظرة عميقة على الراستر المُحوَّل:
```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
Console.WriteLine($"bandCount: {bandCount}");
```

## الخطوة 6: استكشاف نطاقات الراستر
تعمق في النطاقات الفردية للراستر، مكشفًا عن أنواع البيانات، الإحصاءات، ووجود قيم NoData:
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

## لماذا الحصول على حجم خلية الراستر؟
معرفة حجم الخلية بعد التحويل يساعدك على فهم الدقة المكانية للمجموعة الناتجة. هذا أمر أساسي عندما تحتاج إلى محاذاة طبقات متعددة، إجراء تحليلات تعتمد على المسافة الأرضية، أو ببساطة التحقق من أن التحويل حافظ على مستوى التفاصيل المقصود.

## كيفية تحويل صيغ الراستر بكفاءة
طريقة `Warp` تُجرد من تعقيدات إعادة الإسقاط، مما يتيح لك التركيز على معلمات الإدخال مثل الأبعاد المستهدفة ونظام الإسناد المكاني المستهدف. هذا يجعل تحويل البيانات بين أنظمة الإحداثيات، إعادة العينة إلى دقة مختلفة، أو قصها إلى منطقة محددة أمرًا بسيطًا.

## المشكلات الشائعة والحلول
- **قيم حجم الخلية غير المتوقعة:** تأكد من أن معلمات `Height` و `Width` تتطابق مع الدقة المطلوبة للإخراج.  
- **المرجع المكاني مفقود:** إذا كان `spatialRefSys` يُعيد null، تحقق من أن GeoTIFF المصدر يحتوي على بيانات تعريف CRS صحيحة.  
- **معالجة NoData:** استخدم `warped.NoDataValues.IsNull()` لاكتشاف البيانات المفقودة؛ يمكنك أيضًا تعيين قيمة NoData مخصصة قبل التحويل.

## الأسئلة المتكررة

**س: هل Aspose.GIS متوافق مع جميع صيغ الراستر؟**  
ج: نعم، يدعم Aspose.GIS مجموعة واسعة من صيغ الراستر، مما يوفر مرونة في التعامل مع مجموعات البيانات المكانية المختلفة.

**س: هل يمكنني إجراء تحويل الراستر على صور غير مرجعية جغرافياً؟**  
ج: تم تصميم Aspose.GIS للتعامل مع البيانات المرجعية جغرافياً، مما يضمن تحويلات دقيقة. تأكد من أن صور الراستر الخاصة بك تحتوي على معلومات مرجعية مكانية صحيحة.

**س: كيف يمكنني المساهمة في مجتمع Aspose.GIS؟**  
ج: انضم إلى النقاش في [منتدى Aspose.GIS](https://forum.aspose.com/c/gis/33) لمشاركة تجاربك، طرح الأسئلة، والتعاون مع المطورين الآخرين.

**س: هل تتوفر نسخة تجريبية مجانية لـ Aspose.GIS؟**  
ج: نعم، يمكنك استكشاف إمكانيات Aspose.GIS بتحميل نسخة تجريبية مجانية [هنا](https://releases.aspose.com/).

**س: هل تتوفر تراخيص مؤقتة لـ Aspose.GIS؟**  
ج: نعم، إذا كنت بحاجة إلى ترخيص مؤقت، يمكنك الحصول عليه [هنا](https://purchase.aspose.com/temporary-license/).

---

**آخر تحديث:** 2026-05-05  
**تم الاختبار مع:** Aspose.GIS for .NET (latest release)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}