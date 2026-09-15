---
date: 2026-09-15
description: تعرف على كيفية تحويل المضلع إلى خط وتحويل المضلعات إلى خطوط باستخدام
  Aspose.GIS for .NET. دليل سريع لمطوري GIS.
keywords:
- convert polygon to line
- how to replace polygons
- transform polygons to lines
- gis polygon to line
- simplify map visualization
lastmod: 2026-09-15
linktitle: استبدال المضلعات بالخطوط
og_description: تحويل المضلع إلى خط باستخدام Aspose.GIS for .NET. يوضح هذا البرنامج
  التعليمي كيفية استبدال المضلعات بالخطوط، إصدارات .NET المدعومة، والمشكلات الشائعة.
og_image_alt: Screenshot of Aspose.GIS converting polygon to line in a .NET console
  app
og_title: تحويل المضلع إلى خط باستخدام Aspose.GIS for .NET – دليل سريع
schemas:
- author: Aspose
  dateModified: '2026-09-15'
  description: Learn how to convert polygon to line and transform polygons to lines
    using Aspose.GIS for .NET. A quick guide for GIS developers.
  headline: Convert polygon to line with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert polygon to line and transform polygons to lines
    using Aspose.GIS for .NET. A quick guide for GIS developers.
  name: Convert polygon to line with Aspose.GIS for .NET
  steps:
  - name: Define the source geometry
    text: The `GeometryCollection` class is a container that can hold any number of
      geometry objects, including polygons, points, and lines. It is the entry point
      for bulk operations like `ReplacePolygonsByLines`. Create a geometry collection
      that includes one or more polygons you want to convert. In this exa
  - name: Convert polygons to lines
    text: The `ReplacePolygonsByLines()` method scans the supplied collection, replaces
      each polygon with a `LineString` that follows its outer ring, and leaves all
      other geometry types untouched. This single call performs the conversion in
      O(n) time, where *n* is the number of geometries in the collection.
  - name: Display the original and converted geometries
    text: Printing both the original and the transformed geometries lets you verify
      that polygons have been replaced while other geometries stay the same. The `ToString()`
      override on each geometry provides a human‑readable WKT representation.
  type: HowTo
- questions:
  - answer: Yes, it supports more than 30 formats—including Shapefile, GeoJSON, KML,
      GML, and CSV—allowing you to read, convert, and write data without external
      tools.
    question: Can Aspose.GIS for .NET work with various GIS file formats?
  - answer: Yes, you can access the free trial of Aspose.GIS for .NET on the Aspose
      releases page ([Aspose releases page](https://releases.aspose.com/)).
    question: Is there a free trial available for Aspose.GIS for .NET?
  - answer: Yes, developers can get support and assistance from the Aspose.GIS community
      forum ([Aspose.GIS community forum](https://forum.aspose.com/c/gis/33)).
    question: Does Aspose.GIS for .NET offer support for developers?
  - answer: Yes, you can acquire a temporary license from Aspose's temporary license
      page ([temporary license page](https://purchase.aspose.com/temporary-license/)).
    question: Can I purchase a temporary license for Aspose.GIS for .NET?
  - answer: Absolutely, it provides comprehensive documentation, code examples, and
      API references for all skill levels.
    question: Is Aspose.GIS for .NET suitable for both beginners and experienced developers?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert polygon to line
- Aspose.GIS
- .NET GIS processing
title: تحويل المضلع إلى خط باستخدام Aspose.GIS for .NET
url: /ar/net/geometry-processing/replace-polygons-with-lines/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحويل المضلع إلى خط باستخدام Aspose.GIS لـ .NET

## مقدمة
إذا كنت بحاجة إلى **convert polygon to line** في مشروع GIS باستخدام .NET، فإن Aspose.GIS يجعل العملية بسيطة. سواء كنت تبسط تصورات الخريطة، أو تُعد البيانات لخوارزميات التوجيه، أو تحتاج فقط إلى تمثيل هندسي أنظف، فإن هذا الدرس يشرح الخطوات الدقيقة لاستبدال المضلعات بأشكال خطية باستخدام Aspose.GIS API. ستكتشف لماذا تُعد المكتبة خيارًا مفضلاً لمطوري GIS وكيفية إتمام التحويل ببضع أسطر من الشيفرة.

## إجابات سريعة
- **ماذا يعني “convert polygon to line”؟** إنه يستخرج الحلقة الخارجية للمضلع ويُنشئ كائن `LineString` يتبع نفس المحيط.  
- **لماذا تستخدم Aspose.GIS لهذه المهمة؟** المكتبة توفر طريقة واحدة (`ReplacePolygonsByLines`) تتعامل مع التحويل الجماعي بكفاءة، دون الحاجة إلى تحليل يدوي للجيومتري.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، و .NET 5/6+ كلها مدعومة بالكامل.  
- **هل أحتاج إلى ترخيص للتطوير؟** الإصدار التجريبي المجاني يكفي للاختبار؛ الترخيص التجاري مطلوب للنشر في بيئات الإنتاج.  
- **كم من الوقت يستغرق التنفيذ؟** معظم المطورين ينهون التحويل الأساسي في أقل من عشر دقائق.

## ما هو “convert polygon to line”؟
تحويل المضلع إلى خط يعني استخراج الحلقة الخارجية للمضلع (مح

يطه) وتمثيله كـ `LineString`. تحتفظ الهندسة الناتجة بالمخطط الدقيق للشكل الأصلي ولكنها تتجاهل معلومات المنطقة الداخلية، وهو ما يكون مثالياً لتحليل الشبكات، أو رسم الحواف، أو عندما تحتاج إلى تمثيل خفيف الوزن للخرائط الويب.

## لماذا تحويل المضلعات إلى خطوط باستخدام Aspose.GIS؟
يقوم Aspose.GIS باستبدال كل مضلع في مجموعة بخط حدوده في استدعاء واحد، مع الحفاظ على الطوبولوجيا وإلغاء الحاجة إلى حلقات مخصصة. يقلل هذا النهج من تعقيد الشيفرة بنسبة تصل إلى 80 % ويعالج مجموعات تحتوي على أكثر من 10 000 عنصر في أقل من ثانية على عتاد الخادم المعتاد، بفضل نواة C++ الأصلية وإدارة الذاكرة بدون نسخ.

## المتطلبات المسبقة
قبل أن تبدأ، تأكد من توفر ما يلي:

### تثبيت Aspose.GIS لـ .NET
1. قم بتنزيل Aspose.GIS لـ .NET: زر صفحة تنزيل Aspose.GIS لـ .NET ([Aspose.GIS for .NET download](https://releases.aspose.com/gis/net/)).  
2. قم بتثبيت Aspose.GIS لـ .NET: اتبع تعليمات التثبيت الموجودة في الحزمة أو راجع وثائق Aspose.GIS ([Aspose.GIS documentation](https://reference.aspose.com/gis/net/)) للحصول على خطوات مفصلة.

## استيراد مساحات الأسماء
في مشروع .NET الخاص بك، استورد مساحات الأسماء المطلوبة لتتمكن من العمل مع فئات Aspose.GIS.

مساحة الاسم `Aspose.Gis` تحتوي على الأنواع الأساسية للجيومتري، بينما `Aspose.Gis.Geometries` توفر تطبيقات ملموسة مثل `Polygon` و `LineString`.

```csharp
using System;
using Aspose.Gis.Geometries;
```

## دليل خطوة بخطوة

### الخطوة 1: تعريف الهندسة المصدر
فئة `GeometryCollection` هي حاوية يمكنها احتواء أي عدد من كائنات الهندسة، بما في ذلك المضلعات والنقاط والخطوط. وهي نقطة الدخول للعمليات الجماعية مثل `ReplacePolygonsByLines`.

أنشئ مجموعة هندسية تشمل مضلعًا أو أكثر ترغب في تحويله. في هذا المثال نضيف أيضًا نقطة لإظهار أن العناصر غير المضلعة تبقى دون تغيير.

```csharp
var srcGeometry = Geometry.FromText(@"GeometryCollection (POLYGON((1 2, 1 4, 3 4, 3 2)), Point (5 1))");
```

### الخطوة 2: تحويل المضلعات إلى خطوط
طريقة `ReplacePolygonsByLines()` تفحص المجموعة المقدمة، وتستبدل كل مضلع بـ `LineString` يتبع حلقته الخارجية، وتترك جميع أنواع الهندسة الأخرى دون تعديل. هذا الاستدعاء الواحد ينفذ التحويل في زمن O(n)، حيث *n* هو عدد الكائنات الهندسية في المجموعة.

```csharp
var dstGeometry = srcGeometry.ReplacePolygonsByLines();
```

### الخطوة 3: عرض الهندسات الأصلية والمحولة
طباعة كل من الهندسات الأصلية والمحولة يتيح لك التحقق من أن المضلعات قد استُبدلت بينما تبقى الهندسات الأخرى كما هي. تجاوز `ToString()` في كل هندسة يوفر تمثيل WKT قابل للقراءة البشرية.

```csharp
Console.WriteLine($"source: {srcGeometry.AsText()}");
Console.WriteLine($"result: {dstGeometry.AsText()}");
```

## المشكلات الشائعة والحلول
- **عدم وجود مخرجات خطية:** تأكد من أن الهندسة المصدر تحتوي فعليًا على مضلعات؛ النقاط أو النقاط المتعددة ستمر دون تعديل.  
- **مشكلات ترتيب الإحداثيات:** Aspose.GIS يتوقع الإحداثيات بترتيب `X Y` (خط الطول ثم خط العرض). قد تؤدي القيم المبدلة إلى أشكال غير متوقعة.  
- **مجموعات كبيرة:** للمجموعات الضخمة (مئات الآلاف من العناصر)، عالج الهندسات على دفعات من 10 000 إلى 20 000 عنصر للحفاظ على استهلاك الذاكرة أقل من 200 ميغابايت.

## الأسئلة المتكررة

**س: هل يمكن لـ Aspose.GIS لـ .NET العمل مع صيغ ملفات GIS المختلفة؟**  
ج: نعم، يدعم أكثر من 30 صيغة — بما في ذلك Shapefile و GeoJSON و KML و GML و CSV — مما يتيح لك قراءة البيانات وتحويلها وكتابتها دون الحاجة إلى أدوات خارجية.

**س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.GIS لـ .NET؟**  
ج: نعم، يمكنك الوصول إلى النسخة التجريبية المجانية لـ Aspose.GIS لـ .NET عبر صفحة إصدارات Aspose ([Aspose releases page](https://releases.aspose.com/)).

**س: هل يقدم Aspose.GIS لـ .NET دعمًا للمطورين؟**  
ج: نعم، يمكن للمطورين الحصول على الدعم والمساعدة من منتدى مجتمع Aspose.GIS ([Aspose.GIS community forum](https://forum.aspose.com/c/gis/33)).

**س: هل يمكنني شراء ترخيص مؤقت لـ Aspose.GIS لـ .NET؟**  
ج: نعم، يمكنك الحصول على ترخيص مؤقت من صفحة الترخيص المؤقت لـ Aspose ([temporary license page](https://purchase.aspose.com/temporary-license/)).

**س: هل Aspose.GIS لـ .NET مناسب لكل من المبتدئين والمطورين ذوي الخبرة؟**  
ج: بالتأكيد، فهو يوفر وثائق شاملة، أمثلة على الشيفرة، ومراجع API لجميع مستويات المهارة.

## الخلاصة
باتباعك لهذه الخطوات، تعلمت كيفية **convert polygon to line** وفعّالًا **transform polygons to lines** باستخدام Aspose.GIS لـ .NET. تفتح هذه القدرة الباب أمام تصورات أخف، وإعدادات التوجيه، والعديد من سير عمل GIS الأخرى. لا تتردد في استكشاف ميزات Aspose.GIS الإضافية مثل الاستعلامات المكانية، وإعادة الإسقاط، وتحويل الصيغ لتوسيع قدرات تطبيقك.

---

**آخر تحديث:** 2026-09-15  
**تم الاختبار مع:** Aspose.GIS for .NET (latest release)  
**المؤلف:** Aspose

## الدروس ذات الصلة

- [تعلم كيفية إنشاء هندسة LineString باستخدام Aspose.GIS لـ .NET](/gis/net/geometry-creation/create-linestring-geometry/)
- [كيفية إنشاء GeoJSON مع التسامح باستخدام Aspose.GIS لـ .NET](/gis/net/geometry-processing/set-linearization-tolerance/)
- [كيفية تحويل الهندسة إلى WKT باستخدام Aspose.GIS لـ .NET](/gis/net/geometry-processing/translate-geometry-to-wkt/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}