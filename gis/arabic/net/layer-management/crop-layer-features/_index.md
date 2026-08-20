---
date: 2026-07-05
description: تعلم كيفية قص ميزات الطبقة باستخدام Aspose.GIS for .NET، بما في ذلك كيفية
  قص raster باستخدام polygon، استخراج raster cell size، واسترجاع raster extent. حمّل
  نسختك التجريبية المجانية الآن.
keywords:
- how to crop layer
- extract raster extent
- get raster cell size
- crop raster layer
- crop raster with polygon
linktitle: كيفية قص ميزات الطبقة
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to crop layer features with Aspose.GIS for .NET, including
    how to crop raster with polygon, extract raster cell size, and retrieve raster
    extent. Download your free trial now.
  headline: How to Crop Layer Features with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Is a temporary license available for Aspose.GIS for .NET?
  - answer: The documentation is available [here](https://reference.aspose.com/gis/net/).
    question: Where can I find comprehensive documentation for Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for support
      and community engagement.
    question: How can I seek support or connect with the community for Aspose.GIS
      for .NET?
  - answer: Yes, you can download a free trial [here](https://releases.aspose.com/).
    question: Can I download a free trial of Aspose.GIS for .NET?
  - answer: You can purchase the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: كيفية قص ميزات الطبقة باستخدام Aspose.GIS for .NET
url: /ar/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية قص ميزات الطبقة

## مقدمة
في هذا الدرس ستتعلم **كيفية قص ميزات الطبقة** باستخدام Aspose.GIS for .NET، مكتبة قوية تتيح لك **قص الراستر باستخدام مضلع**، **استخراج حجم خلية الراستر**، و**استرجاع امتداد الراستر** لتحليل جغرافي دقيق. سواء كنت تُعد البيانات لخريطة ويب، تقص صور الأقمار الصناعية، أو تعزل منطقة اهتمام، يُظهر لك هذا الدليل خطوة بخطوة كيفية إنجاز المهمة بسرعة وبشكل موثوق.

## إجابات سريعة
- **ماذا يعني “قص الطبقة”؟** يقتطع طبقة راستر أو فيكتور إلى حدود الشكل المقدم، متجاهلاً كل ما هو خارج هذه الحدود.  
- **ما هو الشكل المستخدم في هذا المثال؟** مضلع معرف بصيغة WKT (Well‑Known Text).  
- **هل يمكن استخراج حجم الخلية بعد القص؟** نعم – تُعيد الخاصية `CellSize` عرض وارتفاع خلية الراستر.  
- **هل أحتاج إلى ترخيص لتشغيل الكود؟** ترخيص مؤقت يكفي للتقييم؛ الترخيص الكامل مطلوب للاستخدام الإنتاجي.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6/7.

## ما هو “كيفية قص الطبقة”؟
**قص الطبقة يعني تقييد مجموعة البيانات إلى منطقة جغرافية محددة، متجاهلاً كل ما هو خارجها.** يقلل هذا الإجراء من حجم الملف، يسرّع المعالجة اللاحقة، ويركّز التحليل على المنطقة التي تهمك. من خلال حصر البيانات في منطقة الاهتمام، تُبسّط سير العمل اللاحق مثل التنسيق، التحليل، والنشر، مع الحفاظ على نظام الإحداثيات الأصلي والبيانات الوصفية.

## لماذا نستخدم Aspose.GIS للقص؟
**تُعالج Aspose.GIS ملفات الراستر حتى 2 GB دون تحميل الصورة بالكامل إلى الذاكرة وتدعم أكثر من 30 صيغة راستر، بما في ذلك GeoTIFF، JPEG2000، وPNG.** توفر المكتبة استدعاءً واحدًا `Crop`، معالجة تلقائية لنظام الإحداثيات، وأداءً متعدد الخيوط يمكنه قص ملف GeoTIFF بحجم 500 MB في أقل من ثانية على خادم عادي.

## المتطلبات المسبقة
قبل الخوض في سحر معالجة البيانات الجغرافية، تأكد من توفر المتطلبات التالية:

- مكتبة Aspose.GIS for .NET: تأكد من تثبيت مكتبة Aspose.GIS في مشروع .NET الخاص بك. يمكنك تنزيلها من [هنا](https://releases.aspose.com/gis/net/).  
- دليل المستندات: أنشئ دليلًا لتخزين مستنداتك. استبدل `"Your Document Directory"` في الكود المرفق بالمسار الفعلي لدليل المستندات الخاص بك.

الآن، دعنا ننتقل إلى الدليل خطوة بخطوة.

## استيراد المساحات الاسمية
تحتوي مساحة الأسماء `Aspose.Gis` على جميع الأنواع الأساسية للتعامل مع الراستر والفيكتور. استوردها للحصول على إمكانية الوصول إلى الفئات `Layer`، `Geometry`، وغيرها.

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## كيف أقص طبقة باستخدام مضلع؟
`Crop` هي طريقة في فئة `Layer` تستخرج جزءًا من الراستر معرفًا بواسطة شكل.  
حمّل الراستر المصدر، عرّف شكلًا مضلعًا، واستدعِ طريقة `Crop` – تُنفّذ العملية بالكامل في سطر واحد من الكود. تُعيد الطريقة راسترًا جديدًا يحتوي فقط على البكسلات داخل المضلع، مع الحفاظ تلقائيًا على نظام الإحداثيات الأصلي.

## الخطوة 1: فتح وقص الطبقة (قص الراستر باستخدام مضلع)
`Layer` تمثّل مجموعة بيانات راستر يمكن فتحها، استعلامها، وتعديلها.  
فئة `Layer` تمثّل مجموعة بيانات راستر يمكن فتحها، استعلامها، وتعديلها. فتح ملف GeoTIFF وقصه باستخدام مضلع يعزل منطقة الاهتمام ببضع أسطر فقط.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## الخطوة 2: استرجاع معلومات الراستر (استخراج حجم خلية الراستر واسترجاع امتداد الراستر)
`CellSize` تُوفر عرض وارتفاع كل خلية راستر بوحدات الإحداثيات.  
`Extent` تُعيد الصندوق الحدودي الجغرافي للراستر.  
توفر الخاصية `CellSize` عرض وارتفاع كل خلية راستر بوحدات الإحداثيات، بينما تُعيد الخاصية `Extent` الصندوق الحدودي الجغرافي للراستر المقصوص. كلا المعلومتين أساسيّتين للحسابات اللاحقة مثل قياس المساحة أو إعادة الإسناد.

```csharp
// read and print raster
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
```

## الخطوة 3: عرض المعلومات
اطبع المعلومات المستخرجة لفهم تأثير عملية القص على بياناتك الجغرافية.

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"source extent: {layer.GetExtent()}");
Console.WriteLine($"target extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
```

كرر هذه الخطوات حسب الحاجة لتصقل وتخصّص بياناتك الجغرافية لتلبية متطلبات المشروع المحددة.

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| **اتجاه المضلع غير صحيح** | تأكد من أن مضلع WKT يتبع قاعدة اليد اليمنى (عكس اتجاه عقارب الساعة للدوائر الخارجية). |
| **غياب نظام الإحداثيات** | تحقق من أن ملف GeoTiff المصدر يحتوي على CRS؛ وإلا عيّن واحدًا يدويًا قبل القص. |
| **تباطؤ الأداء على راستر كبير** | استخدم `layer.Crop` على نسخة مُخفضة الدقة أو عالج الراستر على شكل بلاطات. |

## الأسئلة المتكررة
**س: هل يتوفر ترخيص مؤقت لـ Aspose.GIS for .NET؟**  
ج: نعم، يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

**س: أين يمكنني العثور على توثيق شامل لـ Aspose.GIS for .NET؟**  
ج: التوثيق متوفر [هنا](https://reference.aspose.com/gis/net/).

**س: كيف يمكنني طلب الدعم أو التواصل مع المجتمع لـ Aspose.GIS for .NET؟**  
ج: زر منتدى [Aspose.GIS](https://forum.aspose.com/c/gis/33) للحصول على الدعم والتفاعل مع المجتمع.

**س: هل يمكنني تحميل نسخة تجريبية مجانية من Aspose.GIS for .NET؟**  
ج: نعم، يمكنك تحميل نسخة تجريبية مجانية [هنا](https://releases.aspose.com/).

**س: أين يمكنني شراء Aspose.GIS for .NET؟**  
ج: يمكنك شراء المكتبة [هنا](https://purchase.aspose.com/buy).

**س: هل يمكنني قص طبقات متعددة في تشغيل واحد؟**  
ج: نعم—قم بتكرار الحلقة على كل طبقة وطبق نفس استدعاء `Crop` مع الشكل المطلوب.

**س: هل يدعم الـ API صيغ راستر أخرى (مثل JPEG2000)؟**  
ج: تدعم Aspose.GIS جميع الصيغ التي توفرها محركات GDAL الأساسية، بما في ذلك JPEG2000، PNG، وأكثر.

## الخلاصة
باتباع هذا الدليل، أصبحت الآن تعرف **كيفية قص ميزات الطبقة** بفعالية باستخدام Aspose.GIS for .NET. يمكنك بسهولة **قص الراستر باستخدام مضلع**، **استخراج حجم خلية الراستر**، و**استرجاع امتداد الراستر** لتلبية احتياجات أي مشروع. استكشف واجهات برمجة التطبيقات الإضافية لإعادة الإسناد، تنسيق الراستر، وتحليل الفكتور لإطلاق كامل إمكانات سير عملك الجغرافي.

---

**آخر تحديث:** 2026-07-05  
**تم الاختبار مع:** Aspose.GIS 24.10 for .NET  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [How to Create Polygon Geometry with Aspose.GIS for .NET](/gis/net/geometry-creation/create-polygon-geometry/)
- [Get Layer Attributes – Retrieve Layer Attribute Information with Aspose.GIS for .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Create Polygon Geometry C# and Check Intersection with Aspose.GIS for .NET](/gis/net/geometry-analysis/check-geometries-intersection/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}