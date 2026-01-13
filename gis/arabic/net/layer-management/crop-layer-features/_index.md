---
date: 2026-01-13
description: تعلم كيفية قص ميزات الطبقة باستخدام Aspose.GIS لـ .NET، بما في ذلك كيفية
  قص الصورة النقطية باستخدام مضلع، استخراج حجم خلية الصورة النقطية، واسترجاع نطاق
  الصورة النقطية. حمّل نسخة التجربة المجانية الآن.
linktitle: How to Crop Layer Features
second_title: Aspose.GIS .NET API
title: كيفية قص ميزات الطبقة باستخدام Aspose.GIS لـ .NET
url: /ar/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية قص ميزات الطبقة

## المقدمة
في هذا البرنامج التعليمي ستتعلم **how to crop layer** باستخدام Aspose.GIS for .NET، وهو نهج قوي يتيح لك **crop raster with polygon**، **extract raster cell size**، و **retrieve raster extent** لتحليل جغرافي دقيق. سواء كنت تُعد البيانات لخريطة ويب، أو تقصّ صور الأقمار الصناعية، أو تعزل منطقة اهتمام، فإن هذا الدليل خطوة بخطوة يوضح لك بالضبط كيفية إنجاز المهمة.

## الإجابات السريعة
- **ماذا يعني “crop layer”?** يقص طبقة raster أو vector إلى حدود الهندسة المقدمة.  
- **أي هندسة تُستخدم في هذا المثال؟** مضلّع معرف بصيغة WKT.  
- **هل يمكنني استخراج حجم الخلية بعد القص؟** نعم – خاصية `CellSize` توفر هذه المعلومات.  
- **هل أحتاج إلى ترخيص لتشغيل الكود؟** ترخيص مؤقت يعمل للتقييم؛ يتطلب الترخيص الكامل للإنتاج.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## ما هو “how to crop layer”؟
قص الطبقة يعني تقييد مجموعة البيانات بمنطقة جغرافية محددة، وإزالة كل ما هو خارج الشكل المحدد. هذا يقلل من حجم الملف، يسرّع المعالجة، ويركّز التحليل على المنطقة التي تهمك.

## لماذا تستخدم Aspose.GIS للقص؟
- **معالجة raster عالية الأداء** – مثالية لملفات GeoTiff الكبيرة.  
- **API بسيط** – استدعاء `Crop` سطر واحد مع أي هندسة.  
- **توافق كامل مع .NET** – يعمل في تطبيقات سطح المكتب، الخادم، والسحابة.  
- **معالجة دقيقة للمرجع المكاني** – يحافظ على معلومات CRS تلقائيًا.

## المتطلبات المسبقة
قبل الغوص في سحر معالجة البيانات الجغرافية، تأكد من توفر المتطلبات المسبقة التالية:

- Aspose.GIS for .NET Library: تأكد من تثبيت مكتبة Aspose.GIS في مشروع .NET الخاص بك. يمكنك تنزيلها من [here](https://releases.aspose.com/gis/net/).  
- Document Directory: أنشئ دليلًا لتخزين مستنداتك. استبدل `"Your Document Directory"` في الكود المقدم بالمسار الفعلي لدليل المستندات.

الآن، دعنا نغوص في الدليل خطوة بخطوة.

## استيراد مساحات الأسماء
ابدأ باستيراد مساحات الأسماء الضرورية للاستفادة من القوة الكاملة لـ Aspose.GIS:

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## الخطوة 1: فتح وقص الطبقة (crop raster with polygon)
ابدأ بفتح طبقة GeoTiff وقصها بناءً على مضلع معرف. هذا يضمن أن بياناتك الجغرافية مخصصة لمنطقة اهتمام محددة.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## الخطوة 2: استرجاع معلومات raster (extract raster cell size & retrieve raster extent)
بعد قص الطبقة، استخرج المعلومات الأساسية حول بيانات raster، مثل حجم الخلية، نظام المرجع المكاني، والحدود.

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
|---------|------|
| **اتجاه المضلع غير الصحيح** | تأكد من أن مضلع WKT يتبع قاعدة اليد اليمنى (عكس اتجاه عقارب الساعة للدوائر الخارجية). |
| **المرجع المكاني مفقود** | تحقق من أن GeoTiff المصدر يحتوي على CRS؛ وإلا، قم بتعيينه يدويًا قبل القص. |
| **تباطؤ الأداء على rasters الضخمة** | استخدم `layer.Crop` على نسخة مُخفضة العينة أو عالج raster على شكل بلاطات. |

## الأسئلة المتكررة
### س: هل يتوفر ترخيص مؤقت لـ Aspose.GIS for .NET؟
نعم، يمكنك الحصول على ترخيص مؤقت [here](https://purchase.aspose.com/temporary-license/).

### س: أين يمكنني العثور على وثائق شاملة لـ Aspose.GIS for .NET؟
الوثائق متاحة [here](https://reference.aspose.com/gis/net/).

### س: كيف يمكنني طلب الدعم أو التواصل مع المجتمع لـ Aspose.GIS for .NET؟
زر [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) للحصول على الدعم والتفاعل مع المجتمع.

### س: هل يمكنني تنزيل نسخة تجريبية مجانية من Aspose.GIS for .NET؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية [here](https://releases.aspose.com/).

### س: أين يمكنني شراء Aspose.GIS for .NET؟
يمكنك شراء المكتبة [here](https://purchase.aspose.com/buy).

### س: هل يمكنني قص طبقات متعددة في تشغيل واحد؟
نعم—قم بالتكرار على كل طبقة وطبق نفس استدعاء `Crop` مع الهندسة المطلوبة.

### س: هل يدعم API صيغ raster أخرى (مثل JPEG2000)؟
Aspose.GIS يدعم جميع الصيغ التي تكشف عنها برامج تشغيل GDAL الأساسية، بما في ذلك JPEG2000، PNG، وأكثر.

## الخلاصة
باتباع هذا الدليل، أصبحت الآن تعرف **how to crop layer** الميزات بفعالية باستخدام Aspose.GIS for .NET. يمكنك بسهولة **crop raster with polygon**، **extract raster cell size**، و **retrieve raster extent** لتلبية احتياجات أي مشروع. استكشف المزيد من APIs لإعادة الإسقاط، تنسيق raster، وتحليل المتجهات لإطلاق الإمكانات الكاملة لتدفقات عملك الجغرافي.

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-13  
**Tested With:** Aspose.GIS 24.10 for .NET  
**Author:** Aspose  

---