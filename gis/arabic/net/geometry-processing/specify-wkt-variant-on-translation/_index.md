---
date: 2026-04-09
description: تعلم كيفية تعيين المرجع المكاني وتحديد الدقة العشرية عند إنشاء نقطة C#
  باستخدام Aspose.GIS لـ .NET في تطبيقات .NET الخاصة بك.
keywords:
- assign spatial reference
- set decimal precision
- create point c#
linktitle: حدد نوع WKT عند الترجمة
second_title: Aspose.GIS .NET API
title: تعيين المرجع المكاني وتحديد نسخة WKT باستخدام Aspose.GIS
url: /ar/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تعيين المرجع المكاني وتعيين نوع WKT باستخدام Aspose.GIS

## مقدمة
في هذا البرنامج التعليمي ستتعلم كيفية **تعيين المرجع المكاني** إلى شكل هندسي والتحكم في تنسيق إخراج WKT الدقيق باستخدام Aspose.GIS لـ .NET. سواء كنت بحاجة إلى **إنشاء كائنات point C#** للتخطيط أو التحليل أو تبادل البيانات، فإن القدرة على اختيار نوع WKT المناسب ودقة الأرقام يجعل بياناتك المكانية قابلة للتبادل وسهلة القراءة. دعنا نستعرض العملية خطوة بخطوة.

## إجابات سريعة
- **ماذا يعني “assign spatial reference”؟** يربط الشكل الهندسي بنظام إحداثيات محدد مثل WGS‑84.  
- **ما هي أنواع WKT المدعومة؟** Iso، SimpleFeatureAccessOutdated، و ExtendedPostGis.  
- **كيف يمكنني التحكم في دقة الكسور العشرية؟** استخدم خيارات `NumericFormat` مثل `General`، `RoundTrip`، أو `Flat`.  
- **هل أحتاج إلى ترخيص؟** يتوفر نسخة تجريبية مجانية؛ الترخيص التجاري مطلوب للإنتاج.  
- **ما إصدارات .NET المتوافقة؟** .NET Framework 4.0+ و .NET Core/5/6+.

## ما هو “assign spatial reference”؟
تعيين المرجع المكاني (أو نظام المرجع المكاني، SRS) يخبر برامج GIS كيفية تفسير قيم الإحداثيات لشكل هندسي. بدون SRS، لا تكون أرقام خط العرض‑خط الطول للنقطة ذات معنى في العالم الحقيقي.

## لماذا التحكم في نوع WKT وتنسيق الأرقام؟
تتوقع أدوات GIS المختلفة صيغ WKT متفاوتة قليلاً. اختيار النوع المناسب يضمن تبادل بيانات سلس، بينما ضبط دقة الكسور العشرية يمنع أخطاء التقريب أو الأرقام الطويلة التي تملأ السجلات والملفات.

## المتطلبات المسبقة
1. Aspose.GIS لـ .NET – قم بتنزيله من [صفحة التنزيل](https://releases.aspose.com/gis/net/).  
2. بيئة تطوير .NET (Visual Studio، VS Code، أو Rider).  
3. إلمام أساسي بـ C# وإطار عمل .NET.

## استيراد مساحات الأسماء
قبل استخدام أي فئات Aspose.GIS، استورد مساحات الأسماء المطلوبة:

```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```

## الخطوة 1: إنشاء كائن Point (create point C#)
نبدأ بإنشاء كائن `Point` مع خط العرض، خط الطول، وقيمة قياس اختيارية (M):

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## الخطوة 2: تعيين نظام المرجع المكاني (SRS)
الآن **نقوم بتعيين المرجع المكاني** للنقطة. هنا نستخدم نظام WGS‑84 الشائع (SRID 4326):

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## الخطوة 3: تحديد نوع WKT المطلوب
اختر نوع WKT الذي يتطابق مع تطبيقك اللاحق:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## الخطوة 4: تعيين دقة الأعداد العشرية لإخراج WKT
تحكم في عدد الأرقام التي تظهر في السلسلة النهائية باستخدام `NumericFormat`:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### الأخطاء الشائعة والنصائح
- **خطأ:** نسيان تعيين SRS قبل استدعاء `AsText` قد يؤدي إلى فقدان معلومات SRID.  
- **نصيحة:** استخدم `NumericFormat.RoundTrip` عندما تحتاج إلى نقل إحداثيات بدون فقدان.  
- **نصيحة:** النوع `Iso` هو الأكثر قابلية للنقل؛ اختر `ExtendedPostGis` فقط عندما تحتاج إلى تضمين SRID.

## الخلاصة
أنت الآن تعرف كيفية **تعيين المرجع المكاني**، اختيار نوع WKT المناسب، و**تعيين دقة الأعداد العشرية** عند **إنشاء كائنات point C#** باستخدام Aspose.GIS. تمنحك هذه الضوابط المرونة لتلبية المتطلبات الدقيقة لأي سير عمل GIS، من التصور البسيط إلى التحليل المكاني عالي الدقة.

## الأسئلة المتكررة

**س:** هل Aspose.GIS متوافق مع جميع إصدارات .NET؟  
**ج:** نعم، يدعم Aspose.GIS .NET Framework 4.0 وما فوق، بالإضافة إلى .NET Core/5/6.

**س:** هل يمكنني استخدام Aspose.GIS في مشاريع تجارية؟  
**ج:** بالتأكيد. الترخيص التجاري مطلوب للاستخدام في الإنتاج، لكن نسخة تجريبية مجانية متاحة للتقييم.

**س:** هل يدعم Aspose.GIS صيغ بيانات مكانية أخرى؟  
**ج:** نعم، يعمل مع ESRI Shapefile، GeoJSON، KML، والعديد من الصيغ الأخرى.

**س:** أين يمكنني تنزيل نسخة تجريبية مجانية؟  
**ج:** يمكنك تنزيل نسخة تجريبية مجانية من Aspose.GIS من [هنا](https://releases.aspose.com/).

**س:** كيف أحصل على مساعدة إذا واجهت مشاكل؟  
**ج:** انشر أسئلتك في منتدى مجتمع Aspose.GIS [المنتدى](https://forum.aspose.com/c/gis/33) حيث يمكن للموظفين وأعضاء المجتمع المساعدة.

---

**آخر تحديث:** 2026-04-09  
**تم الاختبار مع:** Aspose.GIS for .NET (latest release)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}