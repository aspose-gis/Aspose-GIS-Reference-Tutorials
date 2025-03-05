---
title: التحقق من الهندسة يحتوي على آخر
linktitle: التحقق من الهندسة يحتوي على آخر
second_title: Aspose.GIS .NET API
description: استكشف Aspose.GIS for .NET، وهي مكتبة قوية للتكامل السلس للبيانات الجغرافية المكانية في تطبيقات .NET الخاصة بك.
type: docs
weight: 14
url: /ar/net/geometry-analysis/check-geometry-contains-another/
---
## مقدمة
Aspose.GIS for .NET هي مكتبة قوية تمكن المطورين من العمل مع البيانات الجغرافية المكانية بسلاسة داخل تطبيقات .NET الخاصة بهم. سواء كنت تقوم بإنشاء تطبيق رسم خرائط، أو إجراء تحليل جغرافي مكاني، أو دمج الميزات المستندة إلى الموقع في برنامجك، فإن Aspose.GIS يبسط العملية من خلال توفير واجهات برمجة التطبيقات البديهية والوظائف القوية.
## المتطلبات الأساسية
قبل الغوص في استخدام Aspose.GIS for .NET، تأكد من أن لديك المتطلبات الأساسية التالية:
### 1. إعداد بيئة تطوير .NET
تأكد من إعداد بيئة تطوير .NET عاملة على جهازك. يتضمن ذلك تثبيت .NET SDK وتكوينه بشكل صحيح.
### 2. تركيب Aspose.GIS
 قم بتثبيت Aspose.GIS for .NET عن طريق تنزيل المكتبة من صفحة الإصدار[هنا](https://releases.aspose.com/gis/net/) . اتبع تعليمات التثبيت المتوفرة في الوثائق[هنا](https://reference.aspose.com/gis/net/)لدمج Aspose.GIS في مشروعك.
### 3. الفهم الأساسي لـ C#
تعرف على لغة البرمجة C# حيث يتم استخدام Aspose.GIS for .NET بشكل أساسي مع C#.

## استيراد مساحات الأسماء
في مشروع C# الخاص بك، قم باستيراد مساحات الأسماء اللازمة للاستفادة من وظائف Aspose.GIS:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## الخطوة 1: تحديد الكائنات الهندسية
أولاً، حدد الكائنات الهندسية باستخدام فئات Aspose.GIS:
```csharp
var geometry1 = new Polygon();
geometry1.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 4),
    new Point(4, 4),
    new Point(4, 0),
    new Point(0, 0),
});
geometry1.AddInteriorRing(new LinearRing(new[]
{
    new Point(1, 1),
    new Point(1, 3),
    new Point(3, 3),
    new Point(3, 1),
    new Point(1, 1),
}));
var geometry2 = new Point(2, 2);
```
## الخطوة 2: التحقق من الاحتواء المكاني
بعد ذلك، تحقق مما إذا كانت إحدى الأشكال الهندسية تحتوي على أخرى:
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry2)); // خطأ شنيع
```
## الخطوة 3: تحديد هندسة أخرى
تعريف كائن هندسي آخر:
```csharp
var geometry3 = new Point(0.5, 0.5);
```
## الخطوة 4: التحقق من الاحتواء المكاني مرة أخرى
تحقق مما إذا كانت الهندسة المحددة حديثًا موجودة ضمن الشكل الهندسي الأول:
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry3)); // حقيقي
```
## الخطوة 5: الوظيفة المكافئة
 أفهم أن`a.SpatiallyContains(b)` يعادل`b.Within(a)`:
```csharp
Console.WriteLine(geometry3.Within(geometry1)); // حقيقي
```

## خاتمة
في الختام، يوفر Aspose.GIS for .NET أدوات قوية للتعامل مع البيانات الجغرافية المكانية في تطبيقات .NET. باتباع هذا الدليل واستخدام المثال المقدم، يمكنك إجراء فحوصات الاحتواء المكاني بكفاءة والاستفادة من الوظائف الجغرافية المكانية الأخرى داخل مشاريعك.
## الأسئلة الشائعة
### س1: هل Aspose.GIS متوافق مع .NET Core؟
ج: نعم، Aspose.GIS يدعم بشكل كامل .NET Core، مما يسمح لك بتطوير التطبيقات الجغرافية المكانية عبر منصات مختلفة.
### س2: هل يمكنني إجراء التحليل الجغرافي المكاني باستخدام Aspose.GIS؟
ج: بالتأكيد، يقدم Aspose.GIS وظائف متنوعة للتحليل الجغرافي المكاني، بما في ذلك الاستعلامات المكانية وحسابات المسافة والتلاعب الهندسي.
### س3: ما مدى تكرار إصدار التحديثات لـ Aspose.GIS؟
ج: يقوم Aspose.GIS بإصدار تحديثات بانتظام لتحسين الأداء وإضافة ميزات جديدة ومعالجة أي مشكلات تم الإبلاغ عنها. يمكنك البقاء على اطلاع من خلال زيارة صفحة الإصدار.
### س4: هل يوجد منتدى مجتمعي لمستخدمي Aspose.GIS؟
ج: نعم، يمكنك الانضمام إلى منتدى مجتمع Aspose.GIS[هنا](https://forum.aspose.com/c/gis/33) للتواصل مع المستخدمين الآخرين وطرح الأسئلة ومشاركة تجاربك.
### س5: هل يمكنني تجربة Aspose.GIS قبل الشراء؟
 ج: بالتأكيد، يمكنك استكشاف Aspose.GIS عن طريق تنزيل النسخة التجريبية المجانية من[هنا](https://releases.aspose.com/).