---
date: 2025-12-23
description: تعلم كيفية إنشاء خط من مضلع وتحويل المضلع إلى خطوط باستخدام Aspose.GIS
  لـ .NET. إتقان معالجة بيانات GIS بسرعة.
linktitle: Replace Polygons with Lines
second_title: Aspose.GIS .NET API
title: كيفية إنشاء خط من مضلع باستخدام Aspose.GIS لـ .NET
url: /ar/net/geometry-processing/replace-polygons-with-lines/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء خط من مضلع باستخدام Aspose.GIS لـ .NET

## المقدمة
إذا كنت بحاجة إلى **إنشاء خط من مضلع** في تطبيق GIS، فإن Aspose.GIS لـ .NET يوفر طريقة بسيطة من سطر واحد للقيام بالتحويل. تحويل أشكال المضلعات إلى أشكال خطوط هو خطوة شائعة عندما تريد تصور الحدود، إجراء تحليلات خطية، أو تقليل تعقيد البيانات. في هذا البرنامج التعليمي ستتعرف بالضبط على كيفية استبدال المضلعات بالخطوط، لماذا يهم ذلك، وكيفية دمج الحل في مشاريع .NET الخاصة بك.

## إجابات سريعة
- **ماذا يعني “إنشاء خط من مضلع”؟** يحول الأشكال المغلقة للمضلعات إلى خطوط حدودها المكوّنة.  
- **أي طريقة تقوم بالتحويل؟** `ReplacePolygonsByLines()` من Aspose.GIS Geometry API.  
- **هل أحتاج إلى ترخيص لتشغيل الكود؟** النسخة التجريبية المجانية تكفي للتقييم؛ الترخيص التجاري مطلوب للإنتاج.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6/7.  
- **هل يمكنني استخدامه مع صيغ GIS أخرى؟** نعم – النهج نفسه يعمل مع Shapefile، GeoJSON، KML، إلخ.

## ما هو “create line from polygon”؟
إنشاء خط من مضلع يستخرج حواف المضلع كمجموعة `LineString`. غالبًا ما يُطلق على هذه العملية اسم تحويل *مضلع إلى خط* وتكون مفيدة لمهام مثل تحليل الشبكات، عرض الخرائط، وتبسيط البيانات.

## لماذا نستخدم Aspose.GIS لهذا التحويل؟
- **Built‑in method** – لا حاجة لكتابة كود مخصص لتحليل الهندسة.  
- **High performance** – مُحسّن للتعامل مع مجموعات بيانات كبيرة.  
- **Cross‑format support** – يعمل مع العديد من صيغ ملفات GIS.  
- **Comprehensive documentation** – سهل البدء.

## المتطلبات المسبقة
قبل الغوص في الكود، تأكد من أن لديك ما يلي جاهزًا:

### تثبيت Aspose.GIS لـ .NET
1. تحميل Aspose.GIS لـ .NET: زر [this link](https://releases.aspose.com/gis/net/) لتنزيل أحدث نسخة.  
2. تثبيت Aspose.GIS لـ .NET: اتبع تعليمات التثبيت الموجودة في الحزمة أو راجع [documentation](https://reference.aspose.com/gis/net/) للحصول على خطوات مفصلة.

## استيراد المساحات الاسمية
في مشروع .NET الخاص بك، استورد المساحات الاسمية المطلوبة حتى تتمكن من العمل مع فئات هندسة Aspose.GIS.

```csharp
using System;
using Aspose.Gis.Geometries;
```

## دليل خطوة بخطوة لاستبدال المضلعات بالخطوط

### الخطوة 1: تعريف الهندسة المصدر
إنشاء مجموعة هندسة تحتوي على المضلعات التي تريد تحويلها.

```csharp
var srcGeometry = Geometry.FromText(@"GeometryCollection (POLYGON((1 2, 1 4, 3 4, 3 2)), Point (5 1))");
```

### الخطوة 2: تحويل المضلع إلى خطوط
استخدم طريقة `ReplacePolygonsByLines()` **لتحويل المضلع إلى خطوط**. هذه هي جوهر عملية *create line from polygon*.

```csharp
var dstGeometry = srcGeometry.ReplacePolygonsByLines();
```

### الخطوة 3: عرض النتائج
اطبع كلًا من الهندسة الأصلية والهندسة المحوّلة للتحقق من التحويل.

```csharp
Console.WriteLine($"source: {srcGeometry.AsText()}");
Console.WriteLine($"result: {dstGeometry.AsText()}");
```

## المشكلات الشائعة واستكشاف الأخطاء وإصلاحها
- **Empty geometry collection** – تأكد من أن الهندسة المصدر تحتوي فعليًا على مضلعات؛ وإلا ستعيد `ReplacePolygonsByLines()` الهندسة الأصلية دون تغيير.  
- **Mixed geometry types** – الطريقة تؤثر فقط على المضلعات؛ الأنواع الهندسية الأخرى (مثل النقاط) تمر دون تعديل.  
- **Version compatibility** – استخدم أحدث حزمة NuGet لـ Aspose.GIS لتجنب مشاكل API القديمة.

## الأسئلة المتكررة

**س: هل يمكن لـ Aspose.GIS لـ .NET العمل مع صيغ ملفات GIS مختلفة؟**  
ج: نعم، يدعم Aspose.GIS لـ .NET قراءة وكتابة صيغ مثل Shapefile، GeoJSON، KML، والمزيد.

**س: هل تتوفر نسخة تجريبية مجانية لـ Aspose.GIS لـ .NET؟**  
ج: نعم، يمكنك الوصول إلى النسخة التجريبية المجانية من Aspose.GIS لـ .NET [here](https://releases.aspose.com/).

**س: هل يقدم Aspose.GIS لـ .NET دعمًا للمطورين؟**  
ج: نعم، يمكن للمطورين الحصول على الدعم والمساعدة من منتدى مجتمع Aspose.GIS [here](https://forum.aspose.com/c/gis/33).

**س: هل يمكنني شراء ترخيص مؤقت لـ Aspose.GIS لـ .NET؟**  
ج: نعم، يمكنك الحصول على ترخيص مؤقت من [here](https://purchase.aspose.com/temporary-license/).

**س: هل Aspose.GIS لـ .NET مناسب للمبتدئين والمطورين ذوي الخبرة؟**  
ج: بالتأكيد، يلبي Aspose.GIS لـ .NET احتياجات المطورين على جميع المستويات، مع وثائق شاملة ودعم.

---

**آخر تحديث:** 2025-12-23  
**تم الاختبار مع:** Aspose.GIS لـ .NET 24.12 (أحدث نسخة وقت الكتابة)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}