---
date: 2026-09-15
description: تعرف على كيفية تعيين نظام الإحداثيات، وضبط نسخة WKT والتحكم في دقة الكسور
  العشرية عند إنشاء هندسة نقطة في C# باستخدام Aspose.GIS لـ .NET.
keywords:
- assign coordinate system
- assign spatial reference
- set decimal precision
- create point geometry
- set numeric format
lastmod: 2026-09-15
linktitle: تحديد نسخة WKT على الترجمة
og_description: تعرف على كيفية تعيين نظام الإحداثيات، وضبط نسخة WKT والتحكم في دقة
  الكسور العشرية عند إنشاء هندسة نقطة في C# باستخدام Aspose.GIS لـ .NET.
og_image_alt: Developer guide showing C# code to assign coordinate system and configure
  WKT output with Aspose.GIS
og_title: تعيين نظام الإحداثيات، ضبط نسخة WKT باستخدام Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-09-15'
  description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  headline: Assign coordinate system, set WKT variant using Aspose.GIS
  type: TechArticle
- description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  name: Assign coordinate system, set WKT variant using Aspose.GIS
  steps:
  - name: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
    text: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
  - name: A .NET development environment (Visual Studio, VS Code, or Rider).
    text: A .NET development environment (Visual Studio, VS Code, or Rider).
  - name: Basic familiarity with C# and the .NET framework.
    text: Basic familiarity with C# and the .NET framework.
  type: HowTo
- questions:
  - answer: It binds a geometry to a specific coordinate reference system such as
      WGS‑84.
    question: What does “assign coordinate system” mean?
  - answer: Iso, SimpleFeatureAccessOutdated, and ExtendedPostGis.
    question: Which WKT variants are supported?
  - answer: Use the `NumericFormat` enum (`General`, `RoundTrip`, `Flat`).
    question: How can I control decimal precision?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license for Aspose.GIS?
  - answer: .NET Framework 4.0+ and .NET Core/5/6+.
    question: What .NET versions are compatible?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- assign coordinate system
- Aspose.GIS
- C# geometry
- WKT variant
title: تعيين نظام الإحداثيات، ضبط نسخة WKT باستخدام Aspose.GIS
url: /ar/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تعيين نظام الإحداثيات، وضبط نوع WKT باستخدام Aspose.GIS

## مقدمة
في هذا البرنامج التعليمي ستتعلم كيفية **تعيين نظام الإحداثيات**، اختيار نوع WKT المناسب، والتحكم في دقة الأرقام العشرية عند **إنشاء هندسة نقطة** بلغة C# باستخدام Aspose.GIS لـ .NET. سواءً كنت تبني خدمة رسم خرائط، أو تجري تحليلات مكانية، أو تتبادل البيانات بين منصات GIS، فإن هذه الإعدادات تضمن أن يكون ناتجك متوافقًا وسهل القراءة. دعنا نستعرض العملية خطوة بخطوة.

## إجابات سريعة
- **ماذا يعني “تعيين نظام الإحداثيات”؟** يربط الهندسة بنظام إسناد إحداثيات محدد مثل WGS‑84.  
- **ما هي أنواع WKT المدعومة؟** Iso، SimpleFeatureAccessOutdated، وExtendedPostGis.  
- **كيف يمكنني التحكم في دقة الأرقام العشرية؟** استخدم تعداد `NumericFormat` (`General`، `RoundTrip`، `Flat`).  
- **هل أحتاج إلى ترخيص لـ Aspose.GIS؟** يتوفر نسخة تجريبية مجانية؛ يتطلب الاستخدام في الإنتاج ترخيصًا تجاريًا.  
- **ما إصدارات .NET المتوافقة؟** .NET Framework 4.0+ و .NET Core/5/6+.

## ما هو “تعيين نظام الإحداثيات”؟
إن تعيين إشارة مكانية (أو نظام الإشارة المكانية، SRS) يخبر برنامج GIS كيفية تفسير قيم إحداثيات الهندسة، ربط الأرقام بنظام إحداثيات حقيقي مثل WGS‑84. بدون SRS، لا تحمل أرقام خطوط العرض والطول للنقطة أي معنى في العالم الحقيقي.

## لماذا التحكم في نوع WKT وتنسيق الأرقام؟
أكثر من 30 أداة GIS تتوقع صيغ WKT محددة، لذا اختيار النوع المناسب يمنع أخطاء الاستيراد. ضبط تنسيق الأرقام يقلل من ضوضاء التقريب ويحافظ على اختصار الناتج، وهو أمر مهم خصوصًا عندما يتم تحليل السجلات أو الملفات برمجيًا.

## المتطلبات المسبقة
1. Aspose.GIS لـ .NET – قم بتنزيله من [صفحة التنزيل](https://releases.aspose.com/gis/net/).  
2. بيئة تطوير .NET (Visual Studio، VS Code، أو Rider).  
3. إلمام أساسي بلغة C# وإطار عمل .NET.

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

## كيفية تعيين نظام الإحداثيات لنقطة؟
حمّل كائن `Point`، ثم أرفق نظام إشارة مكانية (SRS) باستخدام فئة `SpatialReference`. يضمن هذا النمط ذو الخطوتين أن تحمل الهندسة بيانات تعريف نظام إحداثياتها عند التصدير، مما يسمح للأدوات اللاحقة بتفسير الإحداثيات بشكل صحيح. تمثل فئة `Point` موقعًا واحدًا يُحدَّد بإحداثيات X (خط الطول) و Y (خط العرض).

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## الخطوة 2: تعيين نظام الإشارة المكانية (SRS)
الآن نقوم **بتعيين الإشارة المكانية** للنقطة. تمثل فئة `SpatialReference` نظام إسناد إحداثيات يُحدَّد بواسطة SRID. هنا نستخدم نظام WGS‑84 المدعوم على نطاق واسع (SRID 4326):

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## الخطوة 3: تحديد نوع WKT المطلوب
اختر نوع WKT الذي يتوافق مع تطبيقك اللاحق:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## كيفية ضبط دقة الأرقام العشرية لإخراج WKT؟
تحكم في عدد الأرقام التي تظهر في السلسلة النهائية باستخدام تعداد `NumericFormat`، الذي يحدد قواعد التنسيق مثل `General`، `RoundTrip` أو `Flat`. اختيار `RoundTrip` يحافظ على دقة الإحداثيات بالكامل في سيناريوهات النقل المتكرر، بينما يوفر `General` تمثيلًا مختصرًا مناسبًا لمعظم مهام التصور. يتحكم تعداد `NumericFormat` في طريقة تنسيق أرقام الإحداثيات في ناتج WKT.

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### الأخطاء الشائعة والنصائح
- **خطأ شائع:** نسيان ضبط SRS قبل استدعاء `AsText` قد يؤدي إلى فقدان معلومات SRID.  
- **نصيحة:** استخدم `NumericFormat.RoundTrip` عندما تحتاج إلى نقل إحداثيات بدون فقدان.  
- **نصيحة:** نوع `Iso` هو الأكثر قابلية للنقل؛ اختر `ExtendedPostGis` فقط عندما تحتاج إلى تضمين SRID.

## الخلاصة
أنت الآن تعرف كيفية **تعيين نظام الإحداثيات**، اختيار نوع WKT المناسب، و**ضبط دقة الأرقام العشرية** عند **إنشاء هندسة نقطة** باستخدام Aspose.GIS. تمنحك هذه الضوابط المرونة لتلبية المتطلبات الدقيقة لأي سير عمل GIS، من التصور البسيط إلى التحليل المكاني عالي الدقة.

## الأسئلة المتكررة

**س:** هل Aspose.GIS متوافق مع جميع إصدارات .NET؟  
**ج:** نعم، يدعم Aspose.GIS .NET Framework 4.0 وما فوق، بالإضافة إلى .NET Core/5/6.

**س:** هل يمكنني استخدام Aspose.GIS في المشاريع التجارية؟  
**ج:** بالطبع. يتطلب الاستخدام في الإنتاج ترخيصًا تجاريًا، لكن تتوفر نسخة تجريبية مجانية للتقييم.

**س:** هل يدعم Aspose.GIS صيغ بيانات مكانية أخرى؟  
**ج:** نعم، يعمل مع أكثر من 30 صيغة، بما في ذلك ESRI Shapefile، GeoJSON، KML، CSV، والعديد غيرها.

**س:** أين يمكنني تنزيل نسخة تجريبية مجانية؟  
**ج:** يمكنك تنزيل نسخة تجريبية مجانية من Aspose.GIS من [صفحة تنزيل النسخة التجريبية المجانية لـ Aspose.GIS](https://releases.aspose.com/).

**س:** كيف أحصل على المساعدة إذا واجهت مشاكل؟  
**ج:** انشر أسئلتك على منتدى مجتمع Aspose.GIS [المنتدى](https://forum.aspose.com/c/gis/33) حيث يمكن للموظفين في Aspose وأعضاء المجتمع المساعدة.

**آخر تحديث:** 2026-09-15  
**تم الاختبار مع:** Aspose.GIS لـ .NET (أحدث إصدار)  
**المؤلف:** Aspose

## دروس ذات صلة

- [إنشاء طبقة متجهة وتعيين نظام إسنادها المكاني](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [كيفية تحويل الهندسة إلى WKT باستخدام Aspose.GIS لـ .NET](/gis/net/geometry-processing/translate-geometry-to-wkt/)
- [كيفية تحديد الدقة عند كتابة الهندسات باستخدام Aspose.GIS](/gis/net/geometry-processing/limit-precision-writing-geometries/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}