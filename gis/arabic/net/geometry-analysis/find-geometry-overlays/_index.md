---
date: 2025-12-07
description: تعرّف على كيفية تنفيذ عمليات التراكب في هذا الدرس المتعلق بالتراكب المكاني
  باستخدام Aspose.GIS لـ .NET. إتقن التقاطع، الاتحاد، الفرق، والفرق المتماثل.
language: ar
linktitle: Find Geometry Overlays
second_title: Aspose.GIS .NET API
title: كيفية تنفيذ عمليات التراكب باستخدام Aspose.GIS لـ .NET
url: /net/geometry-analysis/find-geometry-overlays/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تنفيذ عمليات التراكب باستخدام Aspose.GIS لـ .NET

## مقدمة
تحليل التراكب هو تقنية أساسية في أي **دروس التراكب المكاني** — فهو يتيح لك دمج، مقارنة، واستخلاص رؤى من طبقات جغرافية متعددة. في هذا الدليل ستتعلم **كيفية تنفيذ عمليات التراكب** مثل التقاطع (Intersection)، الاتحاد (Union)، الفرق (Difference)، والفرق المتناظر (Symmetric Difference) باستخدام مكتبة Aspose.GIS القوية لـ .NET. بنهاية الدرس ستكون قادرًا على تطبيق هذه الأساليب على مشكلات GIS حقيقية مثل تخطيط استخدام الأراضي، دراسات الأثر البيئي، وتحسين المسارات.

## إجابات سريعة
- **ما هي عملية التراكب؟** طريقة مكانية تجمع بين شكلين هندسيين لإنتاج شكل جديد (تقاطع، اتحاد، إلخ).  
- **أي مكتبة تتعامل مع عمليات التراكب في .NET؟** Aspose.GIS لـ .NET.  
- **كم يستغرق تنفيذ العملية؟** تقريبًا 10‑15 دقيقة للمثال الأساسي.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية مجانية؛ الترخيص التجاري مطلوب للإنتاج.  
- **هل يمكن تشغيلها على .NET Core / .NET 6+؟** نعم — Aspose.GIS يدعم جميع إصدارات .NET الحديثة.

## ما هي عملية التراكب؟
عملية التراكب تأخذ شكلين هندسيين وتحسب شكلاً جديدًا بناءً على علاقتهما المكانية.  
- **التقاطع (Intersection)** يُعيد المنطقة المشتركة بين الشكلين.  
- **الاتحاد (Union)** يدمج الشكلين في شكل هندسي واحد.  
- **الفرق (Difference)** يطرح أحد الشكلين من الآخر.  
- **الفرق المتناظر (Symmetric Difference)** يُعيد الأجزاء التي تنتمي إلى أحد الشكلين ولكن ليس إلى كليهما.

## لماذا نستخدم Aspose.GIS للتراكب؟
توفر Aspose.GIS واجهة برمجة تطبيقات (API) نظيفة ومُدارة بالكامل تُجردك من الرياضيات منخفضة المستوى، مما يتيح لك التركيز على منطق الأعمال. تعمل عبر الأنظمة، تتعامل مع مجموعات بيانات كبيرة بكفاءة، وتندمج بسلاسة مع مكونات .NET الأخرى.

## المتطلبات المسبقة
- بيئة تطوير .NET تعمل (Visual Studio، VS Code، أو .NET CLI).  
- مكتبة Aspose.GIS لـ .NET – حمّل أحدث نسخة من [الموقع الرسمي](https://releases.aspose.com/gis/net/).  

### استيراد المساحات الاسمية
قبل أن تبدأ في استخدام Aspose.GIS لـ .NET، تحتاج إلى استيراد المساحات الاسمية الضرورية إلى مشروعك.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## كيفية تنفيذ عمليات التراكب في .NET
فيما يلي شرح خطوة بخطوة لإنشاء مضلعين وتطبيق كل طريقة تراكب.

### الخطوة 1: إنشاء كائنات المضلع
أولاً، نعرّف مضلعين مربعين بسيطين يتداخلان جزئيًا. سيُستخدمان كبيانات اختبار.

```csharp
var polygon1 = new Polygon();
polygon1.ExteriorRing = new LinearRing(new[]
{
	 new Point(0, 0),
	 new Point(0, 2),
	 new Point(2, 2),
	 new Point(2, 0),
	 new Point(0, 0),
 });
var polygon2 = new Polygon();
polygon2.ExteriorRing = new LinearRing(new[]
{
	new Point(1, 1),
	new Point(1, 3),
	new Point(3, 3),
	new Point(3, 1),
	new Point(1, 1),
});
```

### الخطوة 2: تنفيذ عملية التقاطع
الـ **Intersection** يُعطينا المنطقة المتداخلة بين المضلعين.

```csharp
var intersection = polygon1.Intersection(polygon2);
Console.WriteLine("Intersection type is {0}", intersection.GeometryType); // Polygon
```

### الخطوة 3: طباعة نقاط التقاطع
نستخدم طريقة مساعدة (`PrintRing`) لعرض إحداثيات المضلع الناتج.

```csharp
PrintRing(((IPolygon)intersection).ExteriorRing);
```

### الخطوة 4: تنفيذ عملية الاتحاد
الـ **Union** يدمج كلا المضلعين في شكل واحد يغطي كل المنطقة التي يغطيها أي منهما.

```csharp
var union = polygon1.Union(polygon2);
Console.WriteLine("Union type is {0}", union.GeometryType); // Polygon
```

### الخطوة 5: طباعة نقاط الاتحاد
إخراج إحداثيات الشكل المدمج.

```csharp
PrintRing(((IPolygon)union).ExteriorRing);
```

### الخطوة 6: تنفيذ عملية الفرق
الـ **Difference** يطرح `polygon2` من `polygon1`، تاركًا الجزء من `polygon1` الذي لا يتقاطع مع `polygon2`.

```csharp
var difference = polygon1.Difference(polygon2);
Console.WriteLine("Difference type is {0}", difference.GeometryType); // Polygon
```

### الخطوة 7: طباعة نقاط الفرق
عرض الرؤوس المتبقية بعد الطرح.

```csharp
PrintRing(((IPolygon)difference).ExteriorRing);
```

### الخطوة 8: تنفيذ عملية الفرق المتناظر
الـ **Symmetric Difference** يُعيد المناطق التي تنتمي إلى أحد المضلعين ولكن ليس إلى كليهما. النتيجة هي `MultiPolygon`.

```csharp
var symDifference = polygon1.SymDifference(polygon2);
Console.WriteLine("Symmetric Difference type is {0}", symDifference.GeometryType); // MultiPolygon
```

### الخطوة 9: طباعة مضلعات الفرق المتناظر
التكرار عبر كل مضلع في الـ `MultiPolygon` وطباعة نقاطه.

```csharp
var multiPolygon = (IMultiPolygon)symDifference;
Console.WriteLine("Polygons count is {0}", multiPolygon.Count); // 2
PrintRing(((IPolygon)multiPolygon[0]).ExteriorRing);
PrintRing(((IPolygon)multiPolygon[1]).ExteriorRing);
```

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|----------------|-----|
| نتيجة `null` من `Intersection` | لا يتقاطع المضلعات فعليًا. | تحقق من الإحداثيات أو استخدم فحص `Intersects` قبل استدعاء `Intersection`. |
| `MultiPolygon` غير متوقع من `SymDifference` | يمكن للفرق المتناظر إنتاج مكونات منفصلة. | حوّل إلى `IMultiPolygon` وتكرّر كما هو موضح. |
| بطء الأداء مع مجموعات بيانات كبيرة | كل عملية تعيد حساب الشكل من الصفر. | أعد استخدام النتائج الوسيطة أو بسط الأشكال باستخدام `Simplify()` قبل التراكب. |

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.GIS لـ .NET في مشاريعي التجارية؟**  
ج: نعم، يمكن استخدام Aspose.GIS لـ .NET في المشاريع التجارية وغير التجارية مع ترخيص صالح.

**س: هل تتوفر نسخة تجريبية من Aspose.GIS لـ .NET؟**  
ج: نعم، يمكنك تنزيل نسخة تجريبية مجانية من [هنا](https://releases.aspose.com/).

**س: كيف يمكنني الحصول على دعم لـ Aspose.GIS لـ .NET؟**  
ج: يمكنك الحصول على الدعم من منتدى مجتمع Aspose.GIS [هنا](https://forum.aspose.com/c/gis/33).

**س: هل هناك تراخيص مؤقتة متاحة لـ Aspose.GIS لـ .NET؟**  
ج: نعم، تتوفر تراخيص مؤقتة للاختبار والتقييم. يمكنك الحصول عليها من [هنا](https://purchase.aspose.com/temporary-license/).

**س: هل يمكنني شراء Aspose.GIS لـ .NET مباشرة؟**  
ج: نعم، يمكنك شراء Aspose.GIS لـ .NET من الموقع [هنا](https://purchase.aspose.com/buy).

---

**آخر تحديث:** 2025-12-07  
**تم الاختبار مع:** Aspose.GIS 24.11 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}